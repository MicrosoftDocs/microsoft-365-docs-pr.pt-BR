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
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4906e-103">Identidade federada para o seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4906e-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4906e-104">*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*</span><span class="sxs-lookup"><span data-stu-id="4906e-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4906e-p101">O Microsoft 365 suporta a identidade federada. Isto significa que em vez de executar a validação das credenciais em si, o Microsoft 365 remete o utilizador de ligação a um servidor de autenticação federado que o Microsoft 365 confia. Se as credenciais do usuário estiverem corretas, o servidor de autenticação federado emite um token de segurança que, por sua vez, o cliente envia ao Microsoft 365 como prova de autenticação. A identidade federada permite o descarregamento e a ampliação da autenticação para uma inscrição no Microsoft 365 e cenários avançados de autenticação e segurança.</span><span class="sxs-lookup"><span data-stu-id="4906e-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="4906e-109">Este artigo descreve como configurar a autenticação federada para seu ambiente de teste do Microsoft 365, resultando no seguinte:</span><span class="sxs-lookup"><span data-stu-id="4906e-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![A autenticação federada para o ambiente de teste do Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="4906e-111">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="4906e-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="4906e-112">Uma assinatura de avaliação ou produção do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="4906e-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="4906e-113">Uma intranet de organização simplificada conectada à Internet, que consiste em cinco máquinas virtuais em uma sub-rede de uma rede virtual do Azure (DC1, APP1, CLIENT1, ADFS1 e PROXY1).</span><span class="sxs-lookup"><span data-stu-id="4906e-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="4906e-114">O Azure AD Connect é executado no APP1 para sincronizar a lista de contas no domínio dos serviços de domínio Active Directory para a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4906e-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="4906e-115">O PROXY1 recebe as solicitações de autenticação de entrada.</span><span class="sxs-lookup"><span data-stu-id="4906e-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="4906e-116">ADFS1 valida as credenciais com o DC1 e emite tokens de segurança.</span><span class="sxs-lookup"><span data-stu-id="4906e-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="4906e-117">Configurar esse ambiente de teste envolve cinco fases:</span><span class="sxs-lookup"><span data-stu-id="4906e-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="4906e-118">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4906e-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="4906e-119">Fase 2: Criar o servidor AD FS</span><span class="sxs-lookup"><span data-stu-id="4906e-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="4906e-120">Fase 3: crie o servidor de proxy da web</span><span class="sxs-lookup"><span data-stu-id="4906e-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="4906e-121">Fase 4: crie um certificado autoassinado e configure o ADFS1 e o PROXY1</span><span class="sxs-lookup"><span data-stu-id="4906e-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="4906e-122">Fase 5: configure o Microsoft 365 da identidade federada.</span><span class="sxs-lookup"><span data-stu-id="4906e-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="4906e-123">Você não pode configurar esse ambiente de teste com uma assinatura de avaliação do Azure.</span><span class="sxs-lookup"><span data-stu-id="4906e-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4906e-124">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4906e-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4906e-125">Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4906e-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="4906e-126">A configuração resultante tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="4906e-126">Your resulting configuration looks like this:</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="4906e-128">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="4906e-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="4906e-129">Uma assinatura de avaliação ou pagamento da Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="4906e-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="4906e-130">Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="4906e-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="4906e-131">O Azure AD Connect é executado no APP1 para sincronizar o domínio do AD DS (serviços de domínio Active Directory) do TESTLAB para o locatário do Azure AD de suas assinaturas do Microsoft 365 periodicamente.</span><span class="sxs-lookup"><span data-stu-id="4906e-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="4906e-132">Fase 2: Criar o servidor AD FS</span><span class="sxs-lookup"><span data-stu-id="4906e-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="4906e-133">Um servidor AD FS fornece autenticação federada entre o Microsoft 365 e as contas no domínio corp.contoso.com hospedado no DC1.</span><span class="sxs-lookup"><span data-stu-id="4906e-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="4906e-134">Para criar uma máquina virtual do Azure para ADFS1, preencha o nome da assinatura e do grupo de recursos, o local do Azure para a Configuração da base e execute estes comandos no prompt de comando do Azure PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="4906e-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="4906e-135">Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual do ADFS1 usando o nome da conta e a senha do administrador local do ADFS1, depois abra um prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4906e-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4906e-136">Para verificar a comunicação da rede e a resolução de nome entre o ADFS1 e o DC1, execute o comando **ping dc1.corp.contoso.com** e verifique se há quatro respostas.</span><span class="sxs-lookup"><span data-stu-id="4906e-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="4906e-137">Em seguida, associe a máquina virtual do ADFS1 ao domínio CORP com estes comandos no prompt do Windows PowerShell no ADFS1.</span><span class="sxs-lookup"><span data-stu-id="4906e-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="4906e-138">A configuração resultante tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="4906e-138">Your resulting configuration looks like this:</span></span>
  
![O servidor AD FS adicionado ao DirSync para o ambiente de teste do Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="4906e-140">Fase 3: crie o servidor de proxy da web</span><span class="sxs-lookup"><span data-stu-id="4906e-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="4906e-141">O PROXY1 fornece proxy de mensagens de autenticação entre ADFS1 e os usuários que tentarem se autenticar.</span><span class="sxs-lookup"><span data-stu-id="4906e-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="4906e-142">Para criar uma máquina virtual do Azure para o PROXY1, preencha o nome do grupo de recursos e execute estes comandos no prompt de comando do Azure PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="4906e-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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
> <span data-ttu-id="4906e-143">Um endereço IP estático público é atribuído ao PROXY1 porque você cria um registro DNS público que aponta para ele e não deverá ser alterado ao reiniciar a máquina virtual do PROXY1.</span><span class="sxs-lookup"><span data-stu-id="4906e-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="4906e-144">Em seguida, adicione uma regra ao grupo de segurança de rede para a sub-rede CorpNet para permitir o tráfego de entrada não solicitado da Internet para PROXY1's endereço IP privado e a porta TCP 443.</span><span class="sxs-lookup"><span data-stu-id="4906e-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="4906e-145">Execute estes comandos no prompt de comando do Azure PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="4906e-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="4906e-146">Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual do PROXY1 usando o nome e a senha da conta do administrador local do PROXY1, depois abra um prompt de comando do Windows PowerShell no PROXY1.</span><span class="sxs-lookup"><span data-stu-id="4906e-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="4906e-147">Para verificar a comunicação da rede e a resolução de nome entre o PROXY1 e o DC1, execute o comando **ping dc1.corp.contoso.com** e verifique se há quatro respostas.</span><span class="sxs-lookup"><span data-stu-id="4906e-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="4906e-148">Em seguida, associe a máquina virtual do PROXY1 ao domínio CORP com estes comandos no prompt do Windows PowerShell no PROXY1.</span><span class="sxs-lookup"><span data-stu-id="4906e-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="4906e-149">Exibir o endereço IP público do PROXY1 com estes comandos do Azure PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="4906e-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="4906e-p106">Em seguida, trabalhe com seu provedor de DNS público e crie um novo registro público de DNS A para **fs.testlab.**\<*your DNS domain name*>que resolve para o endereço IP exibido pelo comando **Write-Host**. De agora em diante, o **fs.testlab.**\<*your DNS domain name*>seu nome de domínio DNS> é conhecido como o *FQDN do serviço de federação*.</span><span class="sxs-lookup"><span data-stu-id="4906e-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<*your DNS domain name*> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="4906e-154">Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual DC1 usando as credenciais CORP\\Usuário1 e execute este comando em um prompt de comando do Windows PowerShell de nível de administrador:</span><span class="sxs-lookup"><span data-stu-id="4906e-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="4906e-155">Esses comandos criam um registro de DNS interno para que as máquinas virtuais na rede virtual do Azure possam resolver o FQDN do serviço de Federação interno para o endereço IP privado ADFS1's.</span><span class="sxs-lookup"><span data-stu-id="4906e-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="4906e-156">A configuração resultante tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="4906e-156">Your resulting configuration looks like this:</span></span>
  
![O servidor proxy do aplicativo Web adicionado ao DirSync para o ambiente de teste do Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="4906e-158">Fase 4: crie um certificado autoassinado e configure o ADFS1 e o PROXY1</span><span class="sxs-lookup"><span data-stu-id="4906e-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="4906e-159">Nesta fase, crie um certificado digital autoassinado para o seu FQDN de serviço de federação e configure o ADFS1 e o PROXY1 como um farm do AD FS.</span><span class="sxs-lookup"><span data-stu-id="4906e-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="4906e-160">Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual DC1 usando as credenciais CORP\\Usuário1 e abra um prompt de comando de nível de administrador do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4906e-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4906e-161">Em seguida, crie uma conta de serviço do AD FS com este comando no prompt de comando do Windows PowerShell no DC1:</span><span class="sxs-lookup"><span data-stu-id="4906e-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="4906e-162">Observe que esse comando solicita que você forneça a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="4906e-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="4906e-163">Escolha uma senha forte e grave-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="4906e-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="4906e-164">Você precisará dele para esta fase e para a fase 5.</span><span class="sxs-lookup"><span data-stu-id="4906e-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="4906e-p108">Use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual ADFS1 usando as credenciais CORP\\Usuário1. Abra um prompt de comando do Windows PowerShell de nível de administrador no ADFS1, preencha o FQDN de serviço de Federação e execute estes comandos para criar um certificado autoassinado:</span><span class="sxs-lookup"><span data-stu-id="4906e-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="4906e-167">Em seguida, use estas etapas para salvar o novo certificado autoassinado como um arquivo.</span><span class="sxs-lookup"><span data-stu-id="4906e-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="4906e-168">Selecione **Iniciar**, digite **mmc.exe**e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="4906e-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="4906e-169">Selecione **arquivo**  >  **Adicionar/remover snap-in**.</span><span class="sxs-lookup"><span data-stu-id="4906e-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="4906e-170">Em **Adicionar ou remover snap-ins**, clique duas vezes em **certificados** na lista de snap-ins disponíveis, selecione **conta do computador**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="4906e-171">Em **Selecionar computador**, selecione **concluir**e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4906e-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="4906e-172">No painel da árvore, abra **Certificados (Computador Local) > Pessoal > Certificados**.</span><span class="sxs-lookup"><span data-stu-id="4906e-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="4906e-173">Selecione e segure (ou clique com o botão direito do mouse) o certificado com o FQDN do serviço de Federação, selecione **todas as tarefas**e, em seguida, selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="4906e-174">Na página de **boas-vindas** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="4906e-175">Na página **Exportar chave privada** , selecione **Sim**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="4906e-176">Na página **formato do arquivo de exportação** , selecione **exportar todas as propriedades estendidas**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="4906e-177">Na página **segurança** , selecione **senha** e digite uma senha em **senha** e **Confirmar senha.**</span><span class="sxs-lookup"><span data-stu-id="4906e-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="4906e-178">Na página **arquivo a ser exportado** , selecione **procurar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="4906e-179">Navegue até a pasta **de \\ certificados C:** , digite **SSL** em **nome do arquivo**e selecione **salvar.**</span><span class="sxs-lookup"><span data-stu-id="4906e-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="4906e-180">Na página **arquivo a ser exportado** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="4906e-181">Na página **concluindo o assistente para exportação de certificados** , selecione **concluir**.</span><span class="sxs-lookup"><span data-stu-id="4906e-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="4906e-182">Quando solicitado, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4906e-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="4906e-183">Depois instale o serviço do AD FS usando esse comando no prompt de comando do Windows PowerShell em ADFS1:</span><span class="sxs-lookup"><span data-stu-id="4906e-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="4906e-184">Aguarde a instalação ser concluída.</span><span class="sxs-lookup"><span data-stu-id="4906e-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="4906e-185">Em seguida, configure o serviço do AD FS com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="4906e-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="4906e-186">Selecione **Iniciar**e, em seguida, selecione o ícone **Gerenciador de servidores** .</span><span class="sxs-lookup"><span data-stu-id="4906e-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="4906e-187">No painel de árvore do Gerenciador de servidores, selecione **AD FS**.</span><span class="sxs-lookup"><span data-stu-id="4906e-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="4906e-188">Na barra de ferramentas na parte superior, selecione o símbolo de cuidado laranja e, em seguida, selecione **Configurar o serviço de Federação neste servidor**.</span><span class="sxs-lookup"><span data-stu-id="4906e-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="4906e-189">Na página de **boas-vindas** do assistente de configuração dos serviços de Federação do Active Directory, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="4906e-190">Na página **conectar-se ao AD DS** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="4906e-191">Na página **Especificar Propriedades do Serviço**:</span><span class="sxs-lookup"><span data-stu-id="4906e-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="4906e-192">Para o **certificado SSL**, selecione a seta para baixo e, em seguida, selecione o certificado com o nome do FQDN do serviço de Federação.</span><span class="sxs-lookup"><span data-stu-id="4906e-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="4906e-193">Em **nome de exibição do serviço de Federação**, digite o nome da sua organização fictícia.</span><span class="sxs-lookup"><span data-stu-id="4906e-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="4906e-194">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="4906e-195">Na página **especificar conta de serviço** , selecione **selecionar** para o **nome da conta**.</span><span class="sxs-lookup"><span data-stu-id="4906e-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="4906e-196">Em **Selecionar usuário ou conta de serviço**, digite **ADFS-Service**, selecione **verificar nomes**e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4906e-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="4906e-197">Em **senha da conta**, insira a senha para a conta ADFS-Service e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="4906e-198">Na página **especificar banco de dados de configuração** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="4906e-199">Na página **Opções de revisão** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="4906e-200">Na página **verificações de pré-requisitos** , selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="4906e-201">Na página **resultados** , selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="4906e-202">Selecione **Iniciar**, selecione o ícone de energia, selecione **reiniciar**e selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="4906e-203">No [portal do Azure](https://portal.azure.com), conecte-se ao PROXY1 com as credenciais da conta CORP\\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="4906e-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="4906e-204">Em seguida, use estas etapas para instalar o certificado autoassinado em **ambos PROXY1 e APP1**.</span><span class="sxs-lookup"><span data-stu-id="4906e-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="4906e-205">Selecione **Iniciar**, digite **mmc.exe**e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="4906e-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="4906e-206">Selecione **arquivo > adicionar/remover snap-in**.</span><span class="sxs-lookup"><span data-stu-id="4906e-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="4906e-207">Em **Adicionar ou remover snap-ins**, clique duas vezes em **certificados** na lista de snap-ins disponíveis, selecione **conta do computador**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="4906e-208">Em **Selecionar computador**, selecione **concluir**e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4906e-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="4906e-209">No painel de árvore, abra **certificados (computador local)**  >  **Personal**  >  **certificados**pessoais.</span><span class="sxs-lookup"><span data-stu-id="4906e-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="4906e-210">Selecione e segure (ou clique com o botão direito do mouse) em **pessoal**, selecione **todas as tarefas**e, em seguida, selecione **importar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="4906e-211">Na página de **boas-vindas** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="4906e-212">Na página **arquivo a ser importado** , insira \*\* \\ \\ adfs1 \\ certs \\ SSL. pfx\*\*e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="4906e-213">Na página **proteção de chave privada** , digite a senha do certificado em **senha**e, em seguida, selecione **Avançar.**</span><span class="sxs-lookup"><span data-stu-id="4906e-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="4906e-214">Na página **repositório de certificados** , selecione **Avançar.**</span><span class="sxs-lookup"><span data-stu-id="4906e-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="4906e-215">Na página **concluindo** , selecione **concluir**.</span><span class="sxs-lookup"><span data-stu-id="4906e-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="4906e-216">Na página **repositório de certificados** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="4906e-217">Quando solicitado, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4906e-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="4906e-218">No painel de árvore, selecione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="4906e-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="4906e-219">Selecione e segure (ou clique com o botão direito do mouse) o certificado e, em seguida, selecione **copiar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="4906e-220">No painel de árvore, abra certificados de **autoridades de certificação raiz confiáveis**  >  **Certificates**.</span><span class="sxs-lookup"><span data-stu-id="4906e-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="4906e-221">Mova o ponteiro do mouse abaixo da lista de certificados instalados, selecione e segure (ou clique com o botão direito do mouse) e selecione **colar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="4906e-222">Abra um prompt de comando do Windows PowerShell de nível de administrador e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4906e-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="4906e-223">Aguarde a instalação ser concluída.</span><span class="sxs-lookup"><span data-stu-id="4906e-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="4906e-224">Use estas etapas para configurar o serviço de proxy de aplicativo web para usar o ADFS1 como seu servidor de federação:</span><span class="sxs-lookup"><span data-stu-id="4906e-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="4906e-225">Selecione **Iniciar**e, em seguida, selecione **Gerenciador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="4906e-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="4906e-226">No painel de árvore, selecione **acesso remoto**.</span><span class="sxs-lookup"><span data-stu-id="4906e-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="4906e-227">Na barra de ferramentas na parte superior, selecione o símbolo de cuidado laranja e, em seguida, selecione **abrir o assistente de proxy de aplicativo Web**.</span><span class="sxs-lookup"><span data-stu-id="4906e-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="4906e-228">Na página de **boas-vindas** do assistente de configuração do proxy de aplicativo Web, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="4906e-229">Na página **Servidor de Federação**:</span><span class="sxs-lookup"><span data-stu-id="4906e-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="4906e-230">Na caixa **nome do serviço de Federação** , insira o FQDN do serviço de Federação.</span><span class="sxs-lookup"><span data-stu-id="4906e-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="4906e-231">Na caixa **nome de usuário** , digite \*\* \\ Usuário1 Corp\*\*.</span><span class="sxs-lookup"><span data-stu-id="4906e-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="4906e-232">Na caixa **senha** , digite a senha da conta Usuário1.</span><span class="sxs-lookup"><span data-stu-id="4906e-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="4906e-233">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="4906e-234">Na página **certificado de proxy do AD FS** , selecione a seta para baixo, selecione o certificado com o FQDN do serviço de Federação e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="4906e-235">Na página **confirmação** , selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="4906e-236">Na página **resultados** , selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="4906e-237">Fase 5: configure o Microsoft 365 da identidade federada.</span><span class="sxs-lookup"><span data-stu-id="4906e-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="4906e-238">Use o [portal do Azure](https://portal.azure.com) para conectar a máquina virtual APP1 com as credenciais da conta CORP\\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="4906e-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="4906e-239">Use estas etapas para configurar o Azure AD Connect e sua assinatura do Microsoft 365 da autenticação federada:</span><span class="sxs-lookup"><span data-stu-id="4906e-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="4906e-240">Na área de trabalho, clique duas vezes em **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="4906e-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="4906e-241">Na página **Bem-vindo ao Azure ad Connect** , selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="4906e-242">Na página **tarefas adicionais** , selecione **alterar entrada do usuário**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="4906e-243">Na página **conectar ao Azure ad** , insira o nome e a senha da conta de administrador global e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="4906e-244">Na página **entrada do usuário** , selecione **Federação com AD FS**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="4906e-245">Na página **farm do AD FS** , selecione **usar um farm existente do AD FS**, digite **ADFS1** na caixa **nome do servidor** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="4906e-246">Quando for solicitado as credenciais do servidor, insira as credenciais da conta do Usuário1 do CORP \\ e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4906e-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="4906e-247">Na página credenciais de **administrador de domínio** , **digite \\ Usuário1 de Corp** na caixa **nome de usuário** , digite a senha da conta na caixa **senha** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="4906e-248">Na página **conta de serviço do AD FS** , **digite Corp \\ ADFS-Service** na caixa **nome de usuário do domínio** , digite a senha da conta na caixa senha do usuário do **domínio** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="4906e-249">Na página **domínio do Azure ad** , em **domínio**, selecione o nome do domínio que você criou anteriormente e adicionou à sua assinatura na fase 1 e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="4906e-250">Na página **pronto para configurar** , selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="4906e-251">Na página **instalação concluída** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="4906e-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="4906e-252">Você deve ver mensagens indicando que a configuração de intranet e da Internet foi verificada.</span><span class="sxs-lookup"><span data-stu-id="4906e-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="4906e-253">Na página **instalação concluída** , selecione **sair**.</span><span class="sxs-lookup"><span data-stu-id="4906e-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="4906e-254">Para demonstrar que a autenticação federada está funcionando, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4906e-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="4906e-255">Abra uma nova instância privada no navegador do computador local e acesse [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4906e-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="4906e-256">Para as credenciais de entrada, insira **user1@** \<*the domain created in Phase 1*> .</span><span class="sxs-lookup"><span data-stu-id="4906e-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="4906e-257">Por exemplo, se seu domínio de teste for **testlab.contoso.com**, insira "user1@testlab.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="4906e-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="4906e-258">Pressione a tecla **Tab** ou permita que o Microsoft 365 direcione automaticamente você.</span><span class="sxs-lookup"><span data-stu-id="4906e-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="4906e-259">Agora você deve ver uma página **de conexão não particular** .</span><span class="sxs-lookup"><span data-stu-id="4906e-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="4906e-260">Você está vendo isso porque você instalou um certificado autoassinado no ADFS1 que seu computador desktop não consegue validar.</span><span class="sxs-lookup"><span data-stu-id="4906e-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="4906e-261">Em uma implantação de produção da autenticação federada, você usaria um certificado de uma autoridade de certificação confiável e seus usuários não veriam essa página.</span><span class="sxs-lookup"><span data-stu-id="4906e-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="4906e-262">Na página **sua conexão não é particular** , selecione **avançado**e, em seguida, selecione \*\*prosseguir \<*your federation service FQDN*> para \*\*.</span><span class="sxs-lookup"><span data-stu-id="4906e-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="4906e-263">Na página com o nome da sua organização fictícia, entre com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4906e-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="4906e-264">**CORP\\Usuário1** como o nome</span><span class="sxs-lookup"><span data-stu-id="4906e-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="4906e-265">A senha da conta Usuário1</span><span class="sxs-lookup"><span data-stu-id="4906e-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="4906e-266">Você verá a **home page do Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="4906e-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="4906e-p112">Esse procedimento demonstra que sua assinatura de avaliação está federada com o domínio AD DS corp.contoso.com hospedado no DC1. Aqui estão os conceitos básicos do processo de autenticação:</span><span class="sxs-lookup"><span data-stu-id="4906e-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="4906e-269">Quando você usa o domínio federado criado na Fase 1 no nome da conta de login, o Microsoft 365 redireciona o navegador para o seu serviço de federação FQDN e PROXY1.</span><span class="sxs-lookup"><span data-stu-id="4906e-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="4906e-270">PROXY1 envia a página de entrada da empresa fictícia para o seu computador local.</span><span class="sxs-lookup"><span data-stu-id="4906e-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="4906e-271">Quando você envia CORP\\Usuário1 e a senha PROXY1, ele o encaminha para o ADFS1.</span><span class="sxs-lookup"><span data-stu-id="4906e-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="4906e-272">O ADFS1 valida CORP\\Usuário1 e a senha com o DC1 e envia um token de segurança para o seu computador local.</span><span class="sxs-lookup"><span data-stu-id="4906e-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="4906e-273">Seu computador local envia o token de segurança para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4906e-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="4906e-274">O Microsoft 365 valida que o token de segurança foi criado pelo ADFS1 e permite o acesso.</span><span class="sxs-lookup"><span data-stu-id="4906e-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="4906e-p113">Sua assinatura de avaliação já está configurada com autenticação federada. Você pode usar esse ambiente de desenvolvimento/teste dos cenários de autenticação avançados.</span><span class="sxs-lookup"><span data-stu-id="4906e-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="4906e-277">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="4906e-277">Next step</span></span>

<span data-ttu-id="4906e-278">Quando você estiver pronto para implantar a autenticação federada de alta disponibilidade e pronta para produção para o Microsoft 365 no Azure, confira [implantar a autenticação federada de alta disponibilidade para o microsoft 365 no Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span><span class="sxs-lookup"><span data-stu-id="4906e-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
