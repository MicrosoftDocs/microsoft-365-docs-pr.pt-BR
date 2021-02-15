---
title: Configuração base corporativa simulada para Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Use este Guia de Laboratório de Teste para criar um ambiente de teste corporativo simulado para o Microsoft 365 para empresas.
ms.openlocfilehash: e66ec8c48e309daeb15aad5fcc475edcb2b8bb35
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487649"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="f0022-103">A configuração base corporativa simulada</span><span class="sxs-lookup"><span data-stu-id="f0022-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="f0022-104">*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e do Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f0022-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f0022-105">Este artigo descreve como criar um ambiente simplificado para o Microsoft 365 para empresas que inclui:</span><span class="sxs-lookup"><span data-stu-id="f0022-105">This article describes how to create a simplified environment for Microsoft 365 for enterprise that includes:</span></span>

- <span data-ttu-id="f0022-106">Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f0022-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="f0022-107">Uma intranet de organização simplificada conectada à Internet, consistindo em três máquinas virtuais em uma rede virtual do Azure (DC1, APP1 e CLIENT1).</span><span class="sxs-lookup"><span data-stu-id="f0022-107">A simplified organization intranet connected to the internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![A configuração base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="f0022-109">A criação de um ambiente de teste simplificado envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="f0022-109">Creating a simplified test environment involves two phases:</span></span>
- [<span data-ttu-id="f0022-110">Fase 1: criar uma intranet simulada</span><span class="sxs-lookup"><span data-stu-id="f0022-110">Phase 1: Create a simulated intranet</span></span>](#phase-1-create-a-simulated-intranet)
- [<span data-ttu-id="f0022-111">Fase 2: criar sua assinatura do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f0022-111">Phase 2: Create your Microsoft 365 E5 subscription</span></span>](#phase-2-create-your-microsoft-365-e5-subscription)

<span data-ttu-id="f0022-112">Você pode usar o ambiente resultante para testar os recursos e funcionalidades [](m365-enterprise-test-lab-guides.md) do [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise) para empresas com guias de laboratório de teste adicionais ou por conta própria.</span><span class="sxs-lookup"><span data-stu-id="f0022-112">You can use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="f0022-114">Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.</span><span class="sxs-lookup"><span data-stu-id="f0022-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="f0022-115">Fase 1: criar uma intranet simulada</span><span class="sxs-lookup"><span data-stu-id="f0022-115">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="f0022-116">Nesta fase, crie uma intranet simulada nos serviços de infraestrutura do Azure que inclua um controlador de domínio dos Serviços de Domínio do Active Directory (AD DS), um servidor de aplicativos e um computador cliente.</span><span class="sxs-lookup"><span data-stu-id="f0022-116">In this phase, build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span>

<span data-ttu-id="f0022-117">Você usará esses computadores em guias adicionais do Laboratório de Teste do [Microsoft 365](m365-enterprise-test-lab-guides.md) para empresas para configurar e demonstrar a identidade híbrida e outros recursos.</span><span class="sxs-lookup"><span data-stu-id="f0022-117">You'll use these computers in additional [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="f0022-118">Método 1: criar sua intranet simulada com um modelo do Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="f0022-118">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="f0022-119">Nesse método, você usa um modelo do Azure Resource Manager para criar a intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="f0022-119">In this method, you use an Azure Resource Manager template to build out the simulated intranet.</span></span> <span data-ttu-id="f0022-120">Os modelos do Gerenciador de Recursos do Azure contêm todas as instruções para criar a infraestrutura de rede do Azure, as máquinas virtuais e suas configurações.</span><span class="sxs-lookup"><span data-stu-id="f0022-120">Azure Resource Manager templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="f0022-121">Antes de implantar o modelo, leia a página [LEIAME do](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) modelo e tenha as seguintes informações prontas:</span><span class="sxs-lookup"><span data-stu-id="f0022-121">Before deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="f0022-122">O nome de domínio DNS público do seu ambiente de teste (testlab). \<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="f0022-122">The public DNS domain name of your test environment (testlab.\<*your public domain*>).</span></span> <span data-ttu-id="f0022-123">Você inserirá esse nome no campo Nome **de** Domínio da página **implantação** personalizada.</span><span class="sxs-lookup"><span data-stu-id="f0022-123">You'll enter this name in the **Domain Name** field of the **Custom deployment** page.</span></span>
- <span data-ttu-id="f0022-p103">Um prefixo de rótulo DNS das URLs dos endereços de IP públicos das suas máquinas virtuais. Você precisará inserir esse rótulo no campo **Prefixo do rótulo DNS** da página **Implantação personalizada**.</span><span class="sxs-lookup"><span data-stu-id="f0022-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="f0022-126">Depois de ler as instruções, selecione **Implantar no Azure** na página [LEIAME do modelo](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) para começar.</span><span class="sxs-lookup"><span data-stu-id="f0022-126">After you read through the instructions, select **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="f0022-127">A intranet simulada criada pelo modelo do Azure Resource Manager requer uma assinatura paga do Azure.</span><span class="sxs-lookup"><span data-stu-id="f0022-127">The simulated intranet built by the Azure Resource Manager template requires a paid Azure subscription.</span></span>

<span data-ttu-id="f0022-128">Depois que o modelo for concluído, sua configuração será assim:</span><span class="sxs-lookup"><span data-stu-id="f0022-128">After the template is complete, your configuration looks like this:</span></span>

![A intranet simulada nos serviços de infraestrutura do Azure](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="f0022-130">Método 2: criar sua intranet simulada com o Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0022-130">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="f0022-131">Nesse método, use o módulo do Windows PowerShell e do Azure PowerShell para criar a infraestrutura de rede, as máquinas virtuais e suas configurações.</span><span class="sxs-lookup"><span data-stu-id="f0022-131">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="f0022-p104">Use esse método caso deseje obter a experiência de criação de elementos de infraestrutura do Azure uma etapa por vez com o PowerShell. Assim, é possível personalizar os blocos de comando do PowerShell para sua própria implantação de outras máquinas virtuais no Azure.</span><span class="sxs-lookup"><span data-stu-id="f0022-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="f0022-134">Etapa 1: criar DC1</span><span class="sxs-lookup"><span data-stu-id="f0022-134">Step 1: Create DC1</span></span>

<span data-ttu-id="f0022-135">Nesta etapa, você cria uma rede virtual do Azure e adiciona o DC1, uma máquina virtual que é um controlador de domínio para um domínio do AD DS.</span><span class="sxs-lookup"><span data-stu-id="f0022-135">In this step, you create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="f0022-136">Primeiro, inicie o prompt de comando do Windows PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="f0022-136">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0022-p105">O comando a seguir define o uso da versão mais recente do Azure PowerShell. Confira [Introdução aos cmdlets do Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="f0022-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="f0022-139">Entre na sua conta do Azure usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="f0022-139">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="f0022-140">Para obter o nome de sua assinatura, use este comando.</span><span class="sxs-lookup"><span data-stu-id="f0022-140">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="f0022-141">Defina sua assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="f0022-141">Set your Azure subscription.</span></span> <span data-ttu-id="f0022-142">Substitua tudo o que está entre aspas, incluindo os colchetes angulares ("<" e ">"), pelo nome correto.</span><span class="sxs-lookup"><span data-stu-id="f0022-142">Replace everything within the quotation marks, including the angle brackets ("<" and ">"), with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="f0022-p107">Depois, crie um novo grupo de recursos para o laboratório de testes simulado. Para determinar um nome de grupo de recursos exclusivo, use este comando para relacionar os grupos de recurso existentes.</span><span class="sxs-lookup"><span data-stu-id="f0022-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="f0022-145">Crie o novo grupo de recursos com estes comandos.</span><span class="sxs-lookup"><span data-stu-id="f0022-145">Create your new resource group with these commands.</span></span> <span data-ttu-id="f0022-146">Substitua tudo o que está entre aspas, incluindo os colchetes angulares, com os nomes corretos.</span><span class="sxs-lookup"><span data-stu-id="f0022-146">Replace everything within the quotation marks, including the angle brackets, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="f0022-147">Em seguida, crie a rede virtual TestLab que hospedará a sub-rede da rede corporativa do ambiente corporativo simulado e a protegerá com um grupo de segurança de rede.</span><span class="sxs-lookup"><span data-stu-id="f0022-147">Next, create the TestLab virtual network that will host the corporate network subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="f0022-148">Preencha o nome do grupo de recursos e execute estes comandos no prompt de comando do PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="f0022-148">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="f0022-149">Em seguida, você cria a máquina virtual DC1 e a configura como um controlador de domínio para o **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="f0022-149">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="f0022-150">Domínio do AD DS e um servidor DNS para as máquinas virtuais da rede virtual TestLab.</span><span class="sxs-lookup"><span data-stu-id="f0022-150">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="f0022-151">Por exemplo, se seu nome de domínio público for **<span>contoso</span>.com**, a máquina virtual DC 1 será um controlador de domínio para o domínio do **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="f0022-151">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="f0022-152">Para criar uma máquina virtual como DC1, preencha o nome do grupo de recursos e execute estes comandos no prompt de comando do PowerShell, no computador local.</span><span class="sxs-lookup"><span data-stu-id="f0022-152">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="f0022-p111">Será solicitado que você insira um nome de usuário e uma senha para a conta de administrador local na DC1. Use uma senha forte e armazene ambos, a senha e o nome, em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="f0022-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="f0022-155">Em seguida, conecte-se à máquina virtual DC1:</span><span class="sxs-lookup"><span data-stu-id="f0022-155">Next, connect to the DC1 virtual machine:</span></span>
  
1. <span data-ttu-id="f0022-156">No [portal do Azure,](https://portal.azure.com)selecione **Grupos** de > <***o*** nome do seu novo grupo de recursos> > **DC1**  >  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="f0022-156">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <***the name of your new resource group***> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="f0022-157">No painel aberto, selecione **Baixar arquivo RDP.**</span><span class="sxs-lookup"><span data-stu-id="f0022-157">In the open pane, select **Download RDP file**.</span></span> <span data-ttu-id="f0022-158">Abra o arquivo DC1.rdp baixado e selecione **Conectar.**</span><span class="sxs-lookup"><span data-stu-id="f0022-158">Open the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="f0022-159">Especifique o nome da conta de administrador local na DC1:</span><span class="sxs-lookup"><span data-stu-id="f0022-159">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="f0022-160">No Windows 7:</span><span class="sxs-lookup"><span data-stu-id="f0022-160">For Windows 7:</span></span>
    
     <span data-ttu-id="f0022-161">Na caixa de diálogo Segurança do **Windows,** selecione **Usar outra conta.**</span><span class="sxs-lookup"><span data-stu-id="f0022-161">In the **Windows Security** dialog box, select **Use another account**.</span></span> <span data-ttu-id="f0022-162">In **User name**, enter **\\ DC1** local administrator account < *name*>.</span><span class="sxs-lookup"><span data-stu-id="f0022-162">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
   - <span data-ttu-id="f0022-163">No Windows 8 ou Windows 10:</span><span class="sxs-lookup"><span data-stu-id="f0022-163">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="f0022-164">Na caixa de diálogo Segurança do **Windows,** selecione **Mais opções** e, em seguida, **selecione Usar uma conta diferente.**</span><span class="sxs-lookup"><span data-stu-id="f0022-164">In the **Windows Security** dialog box, select **More choices**, and then select **Use a different account**.</span></span> <span data-ttu-id="f0022-165">In **User name**, enter **\\ DC1** local administrator account < *name*>.</span><span class="sxs-lookup"><span data-stu-id="f0022-165">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="f0022-166">Em **Senha,** insira a senha da conta de administrador local e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0022-166">In **Password**, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="f0022-167">Quando solicitado, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f0022-167">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="f0022-168">Em seguida, adicione um disco de dados extra como um novo volume com a letra de unidade F:, com este comando, em um prompt de comando do Windows PowerShell de nível de administrador no DC1.</span><span class="sxs-lookup"><span data-stu-id="f0022-168">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="f0022-169">Em seguida, configure o DC1 como um controlador de domínio e servidor DNS para o **testlab.**\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="f0022-169">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<*your public domain*></span></span> <span data-ttu-id="f0022-170">domínio.</span><span class="sxs-lookup"><span data-stu-id="f0022-170">domain.</span></span> <span data-ttu-id="f0022-171">Especifique seu nome de domínio público, remova os colchetes angulares e execute esses comandos em um prompt de comando do Windows PowerShell de nível de administrador no DC1.</span><span class="sxs-lookup"><span data-stu-id="f0022-171">Specify your public domain name, remove the angle brackets, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="f0022-p116">Será preciso especificar uma senha de administrador no modo de segurança. Armazene essa senha em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="f0022-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="f0022-174">Esses comandos podem levar alguns minutos para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="f0022-174">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="f0022-175">Após a reinicialização da DC1, reconecte-se à máquina virtual DC1.</span><span class="sxs-lookup"><span data-stu-id="f0022-175">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="f0022-176">No portal [do Azure,](https://portal.azure.com)selecione **Grupos** de Recursos > <nome *do* grupo de recursos> > **DC1**  >  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="f0022-176">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <*your resource group name*> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="f0022-177">Execute o arquivo DC1.rdp baixado e selecione **Conectar.**</span><span class="sxs-lookup"><span data-stu-id="f0022-177">Run the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="f0022-178">Na **Segurança do Windows,** selecione **Usar outra conta.**</span><span class="sxs-lookup"><span data-stu-id="f0022-178">In **Windows Security**, select **Use another account**.</span></span> <span data-ttu-id="f0022-179">In **User name**, enter **\\ TESTLAB** local administrator account < *name*>.</span><span class="sxs-lookup"><span data-stu-id="f0022-179">In **User name**, enter **TESTLAB\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="f0022-180">Na caixa **Senha,** digite a senha da conta de administrador local e selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="f0022-180">In the **Password** box, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="f0022-181">Quando solicitado, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f0022-181">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="f0022-182">Em seguida, crie uma conta de usuário no Active Directory que será usada ao entrar em computadores membros do domínio TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="f0022-182">Next, create a user account in Active Directory that will be used when signing in to TESTLAB domain member computers.</span></span> <span data-ttu-id="f0022-183">Execute este comando em um prompt de comando do Windows PowerShell de nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="f0022-183">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="f0022-184">Observe que esse comando solicita que você fornece a senha da conta Usuário1.</span><span class="sxs-lookup"><span data-stu-id="f0022-184">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="f0022-185">Essa conta será usada para conexões de área de trabalho remota para todos os computadores membros do domínio TESTLAB, portanto, escolha uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="f0022-185">This account will be used for remote desktop connections for all TESTLAB domain member computers, so choose a strong password.</span></span> <span data-ttu-id="f0022-186">Armazene a senha da conta Usuário1 e armazene-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="f0022-186">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="f0022-p120">Em seguida, configure a nova conta Usuário1 como um administrador de domínio, corporativo e de esquema. Execute este comando no prompt de comando do Windows PowerShell em nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="f0022-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="f0022-189">Encerre a sessão da Área de Trabalho Remota com a DC1 e reconecte-se usando a conta \\Usuário1 do TestLab.</span><span class="sxs-lookup"><span data-stu-id="f0022-189">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="f0022-190">Em seguida, para permitir o tráfego da ferramenta Ping, execute este comando no prompt de comando de nível de administrador do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0022-190">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="f0022-191">Sua configuração atual tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f0022-191">Your current configuration looks like this:</span></span>
  
![Etapa 1 da configuração da base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="f0022-193">Etapa 2: configurar o APP1</span><span class="sxs-lookup"><span data-stu-id="f0022-193">Step 2: Configure APP1</span></span>

<span data-ttu-id="f0022-194">Nessa etapa, você cria e configura o APP1, que se trata de um servidor de aplicativos que inicialmente fornece serviços de compartilhamento de arquivos e da Web.</span><span class="sxs-lookup"><span data-stu-id="f0022-194">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="f0022-195">Para criar uma Máquina Virtual do Microsoft Azure para a APP1, preencha o nome do grupo de recursos e execute estes comandos no prompt de comando, no computador local.</span><span class="sxs-lookup"><span data-stu-id="f0022-195">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="f0022-196">Em seguida, conecte-se à máquina virtual APP1 usando o nome da conta e a senha do administrador local APP1 e depois abra um prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0022-196">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="f0022-197">Para verificar a resolução de nomes e a comunicação de rede entre APP1 e DC1, execute o **ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="f0022-197">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="f0022-198">comando e verifique se há quatro respostas.</span><span class="sxs-lookup"><span data-stu-id="f0022-198">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="f0022-199">Em seguida, adicione a máquina virtual APP1 ao domínio TestLab com estes comandos, no prompt do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0022-199">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="f0022-200">Observe que, depois de executar o comando **Add-Computer,** você deve fornecer as credenciais da conta de domínio \\ Usuário1 do TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="f0022-200">Note that you after you run the **Add-Computer** command, you must supply the TESTLAB\\User1 domain account credentials.</span></span>
  
<span data-ttu-id="f0022-201">Depois de reiniciar a APP1, conecte-se a ele usando a conta \\Usuário1 do TestLab e abra um prompt de comando do Windows PowerShell em nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="f0022-201">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="f0022-202">Em seguida, transforme a APP1 em um servidor Web usando este comando, em um prompt de comando do Windows PowerShell na APP1.</span><span class="sxs-lookup"><span data-stu-id="f0022-202">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="f0022-203">Em seguida, crie uma pasta compartilhada e um arquivo de texto dentro da pasta da APP1 com estes comandos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0022-203">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="f0022-204">Sua configuração atual tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f0022-204">Your current configuration looks like this:</span></span>
  
![Etapa 2 da configuração da base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="f0022-206">Etapa 3: configurar o CLIENT1</span><span class="sxs-lookup"><span data-stu-id="f0022-206">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="f0022-207">Nessa etapa, você cria e configura o CLIENT1, que atua como um laptop, tablet ou computador típico na intranet.</span><span class="sxs-lookup"><span data-stu-id="f0022-207">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="f0022-p122">O seguinte conjunto de comandos cria a CLIENT1 executando o Windows Server 2016 Datacenter, o que pode ser feito em todos os tipos de assinaturas do Azure. Se você tiver uma assinatura do Azure baseada em Visual Studio, será possível criar a CLIENT1 executando o Windows 10 no [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f0022-p122">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span>
  
<span data-ttu-id="f0022-210">Para criar uma Máquina Virtual do Azure para CLIENT1, preencha o nome do grupo de recursos e execute estes comandos no prompt de comando do computador local.</span><span class="sxs-lookup"><span data-stu-id="f0022-210">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="f0022-211">Em seguida, conecte-se à máquina virtual CLIENT1 usando o nome da conta e a senha do administrador local da CLIENT1 e depois abra um prompt de comando de nível de administrador no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0022-211">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="f0022-212">Para verificar a resolução de nomes e a comunicação de rede entre CLIENT1 e DC1, execute o **ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="f0022-212">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="f0022-213">comando em um prompt de comando do Windows PowerShell e verifique se há quatro respostas.</span><span class="sxs-lookup"><span data-stu-id="f0022-213">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="f0022-214">Em seguida, adicione a máquina virtual do CLIENT1 ao domínio TestLab com estes comandos, no prompt do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0022-214">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="f0022-215">Você deve fornecer as credenciais de conta de domínio \\Usuário1 do TestLab, depois de executar o comando **Add-Computer**.</span><span class="sxs-lookup"><span data-stu-id="f0022-215">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="f0022-216">Depois de reiniciar a CLIENT1, conecte-se a ela usando o nome da conta e a senha do \\Usuário1 do TestLab e abra um prompt de comando do Windows PowerShell em nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="f0022-216">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="f0022-217">Após esse procedimento, verifique se você consegue acessar os recursos de compartilhamento de arquivo e da Web no APP1 a partir do CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="f0022-217">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="f0022-218">No Gerenciador do Servidor, no painel de árvore, selecione **Servidor Local.**</span><span class="sxs-lookup"><span data-stu-id="f0022-218">In Server Manager, in the tree pane, select **Local Server**.</span></span>
    
2. <span data-ttu-id="f0022-219">In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.</span><span class="sxs-lookup"><span data-stu-id="f0022-219">In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="f0022-220">Na **Configuração de Segurança Aprimorada** do Internet Explorer, selecione **Desabilitar** para **Administradores** e **Usuários** e selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="f0022-220">In **Internet Explorer Enhanced Security Configuration**, select **Off** for **Administrators** and **Users**, and then select **OK**.</span></span>
    
4. <span data-ttu-id="f0022-221">Na tela inicial, selecione **Internet Explorer** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0022-221">From the Start screen, select **Internet Explorer**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="f0022-222">Na barra de endereços, insira **http <span>://</span>app1.testab.** \<*your public domain name*> **/** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="f0022-222">In the address bar, enter **http <span>://</span>app1.testab.**\<*your public domain name*>**/**, and then press **Enter**.</span></span> <span data-ttu-id="f0022-223">Você deverá ver a página da Web padrão dos Serviços de informações da Internet do APP1.</span><span class="sxs-lookup"><span data-stu-id="f0022-223">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="f0022-224">Na barra de tarefas da área de trabalho, selecione o ícone explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="f0022-224">On the desktop taskbar, select the File Explorer icon.</span></span>
    
7. <span data-ttu-id="f0022-225">Na barra de endereços, insira **\\ \\ app1 \\ Files** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="f0022-225">In the address bar, enter **\\\\app1\\Files**, and then press **Enter**.</span></span> <span data-ttu-id="f0022-226">Você deverá ver uma janela de pasta com o conteúdo da pasta compartilhada Arquivos.</span><span class="sxs-lookup"><span data-stu-id="f0022-226">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="f0022-p126">Na janela da pasta compartilhada **Arquivos**, clique duas vezes no arquivo **Example.txt**. Você verá o conteúdo do arquivo Example.txt.</span><span class="sxs-lookup"><span data-stu-id="f0022-p126">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="f0022-229">Feche o **Bloco de notas do Example.txt** e a janela da pasta compartilhada **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="f0022-229">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="f0022-230">Sua configuração atual tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f0022-230">Your current configuration looks like this:</span></span>
  
![Etapa 3 da configuração da base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="f0022-232">Fase 2: criar sua assinatura do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f0022-232">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="f0022-p127">Nesta fase, você criará uma nova assinatura do Microsoft 365 E5 que usa um novo locatário do Azure AD, que é separado da sua assinatura de produção. É possível fazer isso de duas formas:</span><span class="sxs-lookup"><span data-stu-id="f0022-p127">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="f0022-235">Use uma assinatura de avaliação do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f0022-235">Use a trial subscription of Microsoft 365 E5.</span></span>

  <span data-ttu-id="f0022-p128">A assinatura de avaliação do Microsoft 365 E5 é de 30 dias e pode ser facilmente estendida por até 60 dias. Quando essa assinatura expira, você deve convertê-la em uma assinatura paga ou criar uma nova assinatura de avaliação. Criar uma nova assinatura de avaliação significa abrir mão de sua configuração, o que pode incluir cenários complexos.</span><span class="sxs-lookup"><span data-stu-id="f0022-p128">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="f0022-239">Use uma assinatura de produção separada do Microsoft 365 E5 com uma pequena quantidade de licenças.</span><span class="sxs-lookup"><span data-stu-id="f0022-239">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="f0022-240">Esse é um custo adicional, mas garante que você tenha um ambiente de teste em funcionamento que não expire; nele, você pode experimentar recursos, configurações e cenários.</span><span class="sxs-lookup"><span data-stu-id="f0022-240">This is an additional cost, but ensures that you have a working test environment that doesn't expire; in it, you can try features, configurations, and scenarios.</span></span> <span data-ttu-id="f0022-241">Você pode usar o mesmo ambiente de teste a longo prazo para prova de conceito, demonstração para colegas e gerenciamento e desenvolvimento e teste de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f0022-241">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="f0022-242">Este é o método recomendado.</span><span class="sxs-lookup"><span data-stu-id="f0022-242">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="f0022-243">Inscrever-se em uma assinatura de avaliação do Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f0022-243">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="f0022-244">No portal do Azure, conecte-se ao CLIENT1 com a conta CORP\User1.</span><span class="sxs-lookup"><span data-stu-id="f0022-244">From the Azure portal, connect to CLIENT1 with the CORP\User1 account.</span></span>

<span data-ttu-id="f0022-245">Para criar uma nova assinatura de avaliação do Office 365 E5, siga as instruções na [Fase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) do Guia de Laboratório de Teste da configuração de base leve.</span><span class="sxs-lookup"><span data-stu-id="f0022-245">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="f0022-246">Para configurar sua nova assinatura de avaliação do Office 365 E5, siga as instruções na [Fase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) do Guia de Laboratório de Teste da configuração de base leve.</span><span class="sxs-lookup"><span data-stu-id="f0022-246">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="f0022-247">Usando um ambiente de teste do Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f0022-247">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="f0022-248">Se você precisar apenas de um ambiente de teste do Office 365, não precisará ler o restante deste artigo.</span><span class="sxs-lookup"><span data-stu-id="f0022-248">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="f0022-249">Para obter guias de laboratório de teste adicionais que se aplicam ao Microsoft 365 e ao Office 365, consulte Guias do Laboratório de Teste do [Microsoft 365](m365-enterprise-test-lab-guides.md)para empresas.</span><span class="sxs-lookup"><span data-stu-id="f0022-249">For additional Test Lab Guides that apply to both Microsoft 365 and Office 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="f0022-250">Adicionar uma assinatura de avaliação do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f0022-250">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="f0022-251">Para adicionar uma assinatura de avaliação do Microsoft 365 E5 e configurar suas contas de usuários com licenças, execute as instruções na Fase [3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) do Guia do Laboratório de Teste de configuração de base leve.</span><span class="sxs-lookup"><span data-stu-id="f0022-251">To add a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="f0022-252">Resultados</span><span class="sxs-lookup"><span data-stu-id="f0022-252">Results</span></span>

<span data-ttu-id="f0022-253">Seu ambiente de teste agora tem:</span><span class="sxs-lookup"><span data-stu-id="f0022-253">Your test environment now has:</span></span>
  
- <span data-ttu-id="f0022-254">Assinatura de avaliação do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f0022-254">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="f0022-255">Todas as suas contas de usuário apropriadas estão habilitadas para usar o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f0022-255">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="f0022-256">Uma intranet simulada e simplificada.</span><span class="sxs-lookup"><span data-stu-id="f0022-256">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="f0022-257">Sua configuração final tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f0022-257">Your final configuration looks like this:</span></span>
  
![Fase 2 da configuração base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="f0022-259">Agora você está pronto para experimentar recursos adicionais do [Microsoft 365 para empresas.](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="f0022-259">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="f0022-260">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f0022-260">Next steps</span></span>

<span data-ttu-id="f0022-261">Explore esses conjuntos adicionais de guias de laboratório de teste:</span><span class="sxs-lookup"><span data-stu-id="f0022-261">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="f0022-262">Identidade</span><span class="sxs-lookup"><span data-stu-id="f0022-262">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="f0022-263">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="f0022-263">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="f0022-264">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="f0022-264">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="f0022-265">Confira também</span><span class="sxs-lookup"><span data-stu-id="f0022-265">See also</span></span>

[<span data-ttu-id="f0022-266">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f0022-266">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f0022-267">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f0022-267">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f0022-268">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f0022-268">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
