---
title: Identidade federada para o seu ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 'Resumo: configure a autenticação federada para o seu ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487679"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a5440-103">Identidade federada para o seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5440-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a5440-104">*Este Guia de Laboratório de Teste pode ser usado para Microsoft 365 ambientes de teste corporativos e Office 365 Enterprise de teste.*</span><span class="sxs-lookup"><span data-stu-id="a5440-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a5440-p101">O Microsoft 365 suporta a identidade federada. Isto significa que em vez de executar a validação das credenciais em si, o Microsoft 365 remete o utilizador de ligação a um servidor de autenticação federado que o Microsoft 365 confia. Se as credenciais do usuário estiverem corretas, o servidor de autenticação federado emite um token de segurança que, por sua vez, o cliente envia ao Microsoft 365 como prova de autenticação. A identidade federada permite o descarregamento e a ampliação da autenticação para uma inscrição no Microsoft 365 e cenários avançados de autenticação e segurança.</span><span class="sxs-lookup"><span data-stu-id="a5440-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="a5440-109">Este artigo descreve como configurar a autenticação federada para seu Microsoft 365 de teste, resultando no seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5440-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![A autenticação federada para o ambiente de teste do Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="a5440-111">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="a5440-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="a5440-112">Uma Microsoft 365 E5 de avaliação ou de produção.</span><span class="sxs-lookup"><span data-stu-id="a5440-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="a5440-113">Uma intranet de organização simplificada conectada à Internet, consistindo em cinco máquinas virtuais em uma sub-rede de uma rede virtual do Azure (DC1, APP1, CLIENT1, ADFS1 e PROXY1).</span><span class="sxs-lookup"><span data-stu-id="a5440-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="a5440-114">O Azure AD Conexão executado no APP1 para sincronizar a lista de contas no domínio serviços de domínio do Active Directory para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5440-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="a5440-115">PROXY1 recebe as solicitações de autenticação de entrada.</span><span class="sxs-lookup"><span data-stu-id="a5440-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="a5440-116">O ADFS1 valida credenciais com DC1 e emite tokens de segurança.</span><span class="sxs-lookup"><span data-stu-id="a5440-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="a5440-117">A configuração desse ambiente de teste envolve cinco fases:</span><span class="sxs-lookup"><span data-stu-id="a5440-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="a5440-118">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5440-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="a5440-119">Fase 2: Criar o servidor AD FS</span><span class="sxs-lookup"><span data-stu-id="a5440-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="a5440-120">Fase 3: crie o servidor de proxy da web</span><span class="sxs-lookup"><span data-stu-id="a5440-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="a5440-121">Fase 4: crie um certificado autoassinado e configure o ADFS1 e o PROXY1</span><span class="sxs-lookup"><span data-stu-id="a5440-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="a5440-122">Fase 5: configure o Microsoft 365 da identidade federada.</span><span class="sxs-lookup"><span data-stu-id="a5440-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="a5440-123">Não é possível configurar esse ambiente de teste com uma assinatura de Avaliação do Azure.</span><span class="sxs-lookup"><span data-stu-id="a5440-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a5440-124">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5440-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a5440-125">Siga as instruções na [sincronização de hash de senha para Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a5440-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="a5440-126">Sua configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="a5440-126">Your resulting configuration looks like this:</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="a5440-128">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="a5440-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="a5440-129">Uma Microsoft 365 E5 de avaliação ou assinaturas pagas.</span><span class="sxs-lookup"><span data-stu-id="a5440-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="a5440-130">Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="a5440-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="a5440-131">O Azure AD Conexão é executado no APP1 para sincronizar o domínio testlab active directory domain Services (AD DS) com o locatário do Azure AD de suas assinaturas Microsoft 365 periodicamente.</span><span class="sxs-lookup"><span data-stu-id="a5440-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="a5440-132">Fase 2: Criar o servidor AD FS</span><span class="sxs-lookup"><span data-stu-id="a5440-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="a5440-133">Um servidor AD FS fornece autenticação federada entre o Microsoft 365 e as contas no domínio corp.contoso.com hospedado no DC1.</span><span class="sxs-lookup"><span data-stu-id="a5440-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="a5440-134">Para criar uma máquina virtual do Azure para ADFS1, preencha o nome da assinatura e do grupo de recursos, o local do Azure para a Configuração da base e execute estes comandos no prompt de comando do Azure PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="a5440-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="a5440-135">Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual do ADFS1 usando o nome da conta e a senha do administrador local do ADFS1, depois abra um prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5440-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a5440-136">Para verificar a comunicação da rede e a resolução de nome entre o ADFS1 e o DC1, execute o comando **ping dc1.corp.contoso.com** e verifique se há quatro respostas.</span><span class="sxs-lookup"><span data-stu-id="a5440-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="a5440-137">Em seguida, associe a máquina virtual do ADFS1 ao domínio CORP com estes comandos no prompt do Windows PowerShell no ADFS1.</span><span class="sxs-lookup"><span data-stu-id="a5440-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="a5440-138">Sua configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="a5440-138">Your resulting configuration looks like this:</span></span>
  
![O servidor AD FS adicionado ao DirSync para o ambiente de teste do Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="a5440-140">Fase 3: crie o servidor de proxy da web</span><span class="sxs-lookup"><span data-stu-id="a5440-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="a5440-141">O PROXY1 fornece proxy de mensagens de autenticação entre ADFS1 e os usuários que tentarem se autenticar.</span><span class="sxs-lookup"><span data-stu-id="a5440-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="a5440-142">Para criar uma máquina virtual do Azure para o PROXY1, preencha o nome do grupo de recursos e execute estes comandos no prompt de comando do Azure PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="a5440-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="a5440-143">Um endereço IP estático público é atribuído ao PROXY1 porque você cria um registro DNS público que aponta para ele e não deverá ser alterado ao reiniciar a máquina virtual do PROXY1.</span><span class="sxs-lookup"><span data-stu-id="a5440-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="a5440-144">Em seguida, adicione uma regra ao grupo de segurança de rede da sub-rede CorpNet para permitir o tráfego de entrada não solicitado da Internet para o endereço IP privado do PROXY1 e a porta TCP 443.</span><span class="sxs-lookup"><span data-stu-id="a5440-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="a5440-145">Execute esses comandos no prompt de Azure PowerShell de comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="a5440-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="a5440-146">Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual do PROXY1 usando o nome e a senha da conta do administrador local do PROXY1, depois abra um prompt de comando do Windows PowerShell no PROXY1.</span><span class="sxs-lookup"><span data-stu-id="a5440-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="a5440-147">Para verificar a comunicação da rede e a resolução de nome entre o PROXY1 e o DC1, execute o comando **ping dc1.corp.contoso.com** e verifique se há quatro respostas.</span><span class="sxs-lookup"><span data-stu-id="a5440-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="a5440-148">Em seguida, associe a máquina virtual do PROXY1 ao domínio CORP com estes comandos no prompt do Windows PowerShell no PROXY1.</span><span class="sxs-lookup"><span data-stu-id="a5440-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="a5440-149">Exibe o endereço IP público de PROXY1 com esses Azure PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="a5440-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="a5440-p106">Em seguida, trabalhe com seu provedor de DNS público e crie um novo registro público de DNS A para **fs.testlab.**\<*your DNS domain name*>que resolve para o endereço IP exibido pelo comando **Write-Host**. De agora em diante, o **fs.testlab.**\<*your DNS domain name*>seu nome de domínio DNS> é conhecido como o *FQDN do serviço de federação*.</span><span class="sxs-lookup"><span data-stu-id="a5440-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<*your DNS domain name*> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="a5440-154">Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual DC1 usando as credenciais CORP\\Usuário1 e execute este comando em um prompt de comando do Windows PowerShell de nível de administrador:</span><span class="sxs-lookup"><span data-stu-id="a5440-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="a5440-155">Esses comandos criam um registro DNS A interno para que máquinas virtuais na rede virtual do Azure possam resolver o FQDN do serviço de federação interno para o endereço IP privado do ADFS1.</span><span class="sxs-lookup"><span data-stu-id="a5440-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="a5440-156">Sua configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="a5440-156">Your resulting configuration looks like this:</span></span>
  
![O servidor proxy do aplicativo Web adicionado ao DirSync para o ambiente de teste do Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="a5440-158">Fase 4: crie um certificado autoassinado e configure o ADFS1 e o PROXY1</span><span class="sxs-lookup"><span data-stu-id="a5440-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="a5440-159">Nesta fase, crie um certificado digital autoassinado para o seu FQDN de serviço de federação e configure o ADFS1 e o PROXY1 como um farm do AD FS.</span><span class="sxs-lookup"><span data-stu-id="a5440-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="a5440-160">Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual DC1 usando as credenciais CORP\\Usuário1 e abra um prompt de comando de nível de administrador do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a5440-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a5440-161">Em seguida, crie uma conta de serviço do AD FS com este comando no prompt de comando Windows PowerShell dc1:</span><span class="sxs-lookup"><span data-stu-id="a5440-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="a5440-162">Observe que esse comando solicita que você fornece a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="a5440-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="a5440-163">Escolha uma senha forte e grave-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="a5440-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="a5440-164">Você precisará dele para esta fase e para a Fase 5.</span><span class="sxs-lookup"><span data-stu-id="a5440-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="a5440-p108">Use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual ADFS1 usando as credenciais CORP\\Usuário1. Abra um prompt de comando do Windows PowerShell de nível de administrador no ADFS1, preencha o FQDN de serviço de Federação e execute estes comandos para criar um certificado autoassinado:</span><span class="sxs-lookup"><span data-stu-id="a5440-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="a5440-167">Em seguida, use estas etapas para salvar o novo certificado autoassinado como um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a5440-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="a5440-168">Selecione **Iniciar,** insira **mmc.exe** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="a5440-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="a5440-169">Selecione   >  **Adicionar/Remover arquivos Ajustar-in**.</span><span class="sxs-lookup"><span data-stu-id="a5440-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="a5440-170">Em **Adicionar ou Remover Ajustar-ins,** clique duas vezes em **Certificados** na lista de snap-ins disponíveis, selecione Conta de computador **e** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a5440-171">Em **Selecionar Computador,** selecione **Concluir** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5440-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="a5440-172">No painel da árvore, abra **Certificados (Computador Local) > Pessoal > Certificados**.</span><span class="sxs-lookup"><span data-stu-id="a5440-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="a5440-173">Selecione e segure (ou clique com o botão direito do mouse) no certificado com o FQDN do serviço de federação, selecione **Todas** as tarefas e selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="a5440-174">Na página **Bem-vindo,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="a5440-175">Na página **Exportar Chave Privada,** selecione **Sim** e, em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="a5440-176">Na página **Exportar Formato de Arquivo,** selecione Exportar todas as propriedades **estendidas** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="a5440-177">Na página **Segurança,** selecione **Senha e** insira uma senha em **Senha** e **Confirmar senha.**</span><span class="sxs-lookup"><span data-stu-id="a5440-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="a5440-178">Na página **Arquivo a Exportar,** selecione **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="a5440-179">Navegue até **a pasta C: \\ Certs,** insira **SSL** em **Nome do** arquivo e selecione **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="a5440-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="a5440-180">Na página **Arquivo a Exportar,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="a5440-181">Na página **Concluindo o Assistente de Exportação de Certificados,** selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a5440-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="a5440-182">Quando solicitado, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5440-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="a5440-183">Depois instale o serviço do AD FS usando esse comando no prompt de comando do Windows PowerShell em ADFS1:</span><span class="sxs-lookup"><span data-stu-id="a5440-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="a5440-184">Aguarde a instalação ser concluída.</span><span class="sxs-lookup"><span data-stu-id="a5440-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="a5440-185">Em seguida, configure o serviço do AD FS com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a5440-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="a5440-186">Selecione **Iniciar** e, em seguida, selecione o **ícone Gerenciador de** Servidores.</span><span class="sxs-lookup"><span data-stu-id="a5440-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="a5440-187">No painel de árvore do Gerenciador do Servidor, selecione **AD FS**.</span><span class="sxs-lookup"><span data-stu-id="a5440-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="a5440-188">Na barra de ferramentas na parte superior, selecione o símbolo de cuidado laranja e selecione Configurar o serviço **de federação neste servidor**.</span><span class="sxs-lookup"><span data-stu-id="a5440-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="a5440-189">Na página **Bem-vindo** do Assistente de Configuração dos Serviços de Federação do Active Directory, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="a5440-190">Na página **Conexão para o AD DS,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="a5440-191">Na página **Especificar Propriedades do Serviço**:</span><span class="sxs-lookup"><span data-stu-id="a5440-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="a5440-192">Para **Certificado SSL,** selecione a seta para baixo e selecione o certificado com o nome do FQDN do serviço de federação.</span><span class="sxs-lookup"><span data-stu-id="a5440-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="a5440-193">Em **Nome de Exibição do Serviço de Federação,** digite o nome da sua organização fictícia.</span><span class="sxs-lookup"><span data-stu-id="a5440-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="a5440-194">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="a5440-195">Na página **Especificar Conta de Serviço,** selecione **Selecionar nome** **da conta**.</span><span class="sxs-lookup"><span data-stu-id="a5440-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="a5440-196">Em **Selecionar Conta de Usuário ou Serviço,** insira **ADFS-Service,** selecione **Verificar Nomes** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5440-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="a5440-197">Em **Senha da** Conta, insira a senha da conta ADFS-Service e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="a5440-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="a5440-198">Na página **Especificar Banco de Dados de Configuração,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="a5440-199">Na página **Opções de Revisão,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="a5440-200">Na página **Verificações de Pré-requisito,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="a5440-201">Na página **Resultados,** selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="a5440-202">Selecione **Iniciar**, selecione o ícone de energia, selecione **Reiniciar** e, em seguida, selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="a5440-203">No [portal do Azure](https://portal.azure.com), conecte-se ao PROXY1 com as credenciais da conta CORP\\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="a5440-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="a5440-204">Em seguida, use estas etapas para instalar o certificado autoassinado em **ambos PROXY1 e APP1**.</span><span class="sxs-lookup"><span data-stu-id="a5440-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="a5440-205">Selecione **Iniciar,** insira **mmc.exe** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="a5440-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="a5440-206">Selecione **Arquivo > Adicionar/Remover Ajustar-in**.</span><span class="sxs-lookup"><span data-stu-id="a5440-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="a5440-207">Em **Adicionar ou Remover Ajustar-ins,** clique duas vezes em **Certificados** na lista de snap-ins disponíveis, selecione Conta de computador **e** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a5440-208">Em **Selecionar Computador,** selecione **Concluir** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5440-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="a5440-209">No painel de árvore, abra **Certificados (Computador Local)**  >    >  **Certificados Pessoais**.</span><span class="sxs-lookup"><span data-stu-id="a5440-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="a5440-210">Selecione e segure (ou clique com o botão direito do mouse) **Pessoal,** selecione **Todas as** tarefas e selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="a5440-211">Na página **Bem-vindo,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="a5440-212">Na página **Arquivo a importar,** insira **\\ \\ adfs1 \\ certs \\ ssl.pfx** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="a5440-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="a5440-213">Na página **Proteção de chave** privada, insira a senha do certificado em **Senha** e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="a5440-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="a5440-214">Na página **Armazenamento de certificados,** selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="a5440-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="a5440-215">Na página **Conclusão,** selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a5440-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="a5440-216">Na página **Armazenamento de Certificados,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="a5440-217">Quando solicitado, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5440-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="a5440-218">No painel de árvore, selecione **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="a5440-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="a5440-219">Selecione e segure (ou clique com o botão direito do mouse) no certificado e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="a5440-220">No painel de árvore, abra **Certificados de Autoridades de Certificação Raiz**  >  **Confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="a5440-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="a5440-221">Mova o ponteiro do mouse para baixo da lista de certificados instalados, selecione e segure (ou clique com o botão direito do mouse) e selecione **Colar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="a5440-222">Abra um prompt de comando do Windows PowerShell de nível de administrador e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a5440-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="a5440-223">Aguarde a instalação ser concluída.</span><span class="sxs-lookup"><span data-stu-id="a5440-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="a5440-224">Use estas etapas para configurar o serviço de proxy de aplicativo web para usar o ADFS1 como seu servidor de federação:</span><span class="sxs-lookup"><span data-stu-id="a5440-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="a5440-225">Selecione **Iniciar** e, em seguida, selecione **Gerenciador do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="a5440-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="a5440-226">No painel de árvore, selecione **Acesso Remoto**.</span><span class="sxs-lookup"><span data-stu-id="a5440-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="a5440-227">Na barra de ferramentas na parte superior, selecione o símbolo de cuidado laranja e, em seguida, selecione Abrir o Assistente de **Proxy de Aplicativo Web**.</span><span class="sxs-lookup"><span data-stu-id="a5440-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="a5440-228">Na página **Bem-vindo** do Assistente de Configuração de Proxy de Aplicativo Web, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="a5440-229">Na página **Servidor de Federação**:</span><span class="sxs-lookup"><span data-stu-id="a5440-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="a5440-230">Na caixa **Nome do serviço de** Federação, insira o FQDN do serviço de federação.</span><span class="sxs-lookup"><span data-stu-id="a5440-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="a5440-231">Na caixa **Nome do** usuário, insira **CORP \\ User1**.</span><span class="sxs-lookup"><span data-stu-id="a5440-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="a5440-232">Na caixa **Senha,** insira a senha da conta User1.</span><span class="sxs-lookup"><span data-stu-id="a5440-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="a5440-233">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="a5440-234">Na página Certificado proxy do **AD FS,** selecione a seta para baixo, selecione o certificado com o FQDN do serviço de federação e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="a5440-235">Na página **Confirmação,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="a5440-236">Na página **Resultados,** selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="a5440-237">Fase 5: configure o Microsoft 365 da identidade federada.</span><span class="sxs-lookup"><span data-stu-id="a5440-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="a5440-238">Use o [portal do Azure](https://portal.azure.com) para conectar a máquina virtual APP1 com as credenciais da conta CORP\\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="a5440-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="a5440-239">Use estas etapas para configurar o Azure AD Connect e sua assinatura do Microsoft 365 da autenticação federada:</span><span class="sxs-lookup"><span data-stu-id="a5440-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="a5440-240">Na área de trabalho, clique duas vezes em **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="a5440-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="a5440-241">Na página **Bem-vindo ao Azure AD Conexão,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="a5440-242">Na página **Tarefas adicionais,** selecione **Alterar a login do** usuário e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a5440-243">Na página **Conexão para o Azure AD,** insira o nome e a senha da sua conta de administrador global e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="a5440-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="a5440-244">Na página **Login do** usuário, selecione Federação **com AD FS** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="a5440-245">Na página do farm do **AD FS,** selecione Usar um farm do **AD FS** existente, insira **ADFS1** na caixa **Nome** do Servidor e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="a5440-246">Quando solicitado para credenciais de servidor, insira as credenciais da conta CORP User1 e selecione \\ **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5440-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="a5440-247">Na página **Credenciais do Administrador** de Domínio,  insira **CORP \\ User1** na  caixa Nome de Usuário, insira a senha da conta na caixa Senha e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="a5440-248">Na página conta de serviço do **AD FS,** insira  **CORP \\ ADFS-Service** na caixa Nome de Usuário do Domínio, insira a senha da conta na caixa Senha do Usuário de **Domínio** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="a5440-249">Na página Domínio **do Azure AD,** em **Domínio,** selecione o nome do domínio que você criou anteriormente e adicionou à sua assinatura na Fase 1 e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a5440-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="a5440-250">Na página **Pronto para configurar,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="a5440-251">Na página **Instalação concluída,** selecione **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="a5440-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="a5440-252">Você deve ver mensagens indicando que a configuração da intranet e da Internet foi verificada.</span><span class="sxs-lookup"><span data-stu-id="a5440-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="a5440-253">Na página **Instalação concluída,** selecione **Sair**.</span><span class="sxs-lookup"><span data-stu-id="a5440-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="a5440-254">Para demonstrar que a autenticação federada está funcionando, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5440-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="a5440-255">Abra uma nova instância privada no navegador do computador local e acesse [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a5440-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="a5440-256">Para as credenciais de entrada, digite **user1@** \<*the domain created in Phase 1*> .</span><span class="sxs-lookup"><span data-stu-id="a5440-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="a5440-257">Por exemplo, se seu domínio de teste **testlab.contoso.com**, você digitará "user1@testlab.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="a5440-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="a5440-258">Pressione a **tecla Tab** ou permita Microsoft 365 redirecionar você automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a5440-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="a5440-259">Agora você deve ver uma **Sua conexão não é uma página** privada.</span><span class="sxs-lookup"><span data-stu-id="a5440-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="a5440-260">Você está vendo isso porque instalou um certificado auto-assinado no ADFS1 que seu computador desktop não pode validar.</span><span class="sxs-lookup"><span data-stu-id="a5440-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="a5440-261">Em uma implantação de produção de autenticação federada, você usaria um certificado de uma autoridade de certificação confiável e seus usuários não veriam esta página.</span><span class="sxs-lookup"><span data-stu-id="a5440-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="a5440-262">Na página **Sua conexão não é** privada, selecione **Avançado** e selecione **Prosseguir para \<*your federation service FQDN*>**.</span><span class="sxs-lookup"><span data-stu-id="a5440-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="a5440-263">Na página com o nome da sua organização fictícia, entre com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5440-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="a5440-264">**CORP\\Usuário1** como o nome</span><span class="sxs-lookup"><span data-stu-id="a5440-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="a5440-265">A senha da conta Usuário1</span><span class="sxs-lookup"><span data-stu-id="a5440-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="a5440-266">Você verá a **home page do Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="a5440-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="a5440-p112">Esse procedimento demonstra que sua assinatura de avaliação está federada com o domínio AD DS corp.contoso.com hospedado no DC1. Aqui estão os conceitos básicos do processo de autenticação:</span><span class="sxs-lookup"><span data-stu-id="a5440-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="a5440-269">Quando você usa o domínio federado criado na Fase 1 no nome da conta de login, o Microsoft 365 redireciona o navegador para o seu serviço de federação FQDN e PROXY1.</span><span class="sxs-lookup"><span data-stu-id="a5440-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="a5440-270">PROXY1 envia a página de entrada da empresa fictícia para o seu computador local.</span><span class="sxs-lookup"><span data-stu-id="a5440-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="a5440-271">Quando você envia CORP\\Usuário1 e a senha PROXY1, ele o encaminha para o ADFS1.</span><span class="sxs-lookup"><span data-stu-id="a5440-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="a5440-272">O ADFS1 valida CORP\\Usuário1 e a senha com o DC1 e envia um token de segurança para o seu computador local.</span><span class="sxs-lookup"><span data-stu-id="a5440-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="a5440-273">Seu computador local envia o token de segurança para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5440-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="a5440-274">O Microsoft 365 valida que o token de segurança foi criado pelo ADFS1 e permite o acesso.</span><span class="sxs-lookup"><span data-stu-id="a5440-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="a5440-p113">Sua assinatura de avaliação já está configurada com autenticação federada. Você pode usar esse ambiente de desenvolvimento/teste dos cenários de autenticação avançados.</span><span class="sxs-lookup"><span data-stu-id="a5440-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="a5440-277">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a5440-277">Next step</span></span>

<span data-ttu-id="a5440-278">Quando estiver pronto para implantar a autenticação federada pronta para produção e alta disponibilidade para Microsoft 365 no Azure, consulte [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span><span class="sxs-lookup"><span data-stu-id="a5440-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
