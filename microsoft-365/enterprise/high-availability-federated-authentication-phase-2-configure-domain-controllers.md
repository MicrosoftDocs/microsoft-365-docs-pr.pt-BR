---
title: Autenticação federada de alta disponibilidade Fase 2 Configurar controladores de domínio
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: 'Resumo: Configure os controladores de domínio e o servidor de sincronização de diretórios para sua autenticação federada de alta disponibilidade para Microsoft 365 no Microsoft Azure.'
ms.openlocfilehash: 751d332ce5f5606fe5f833182f002a1f4b6f29ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909805"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a><span data-ttu-id="1edf3-103">Autenticação federada de alta disponibilidade Fase 2: configurar controladores de domínio</span><span class="sxs-lookup"><span data-stu-id="1edf3-103">High availability federated authentication Phase 2: Configure domain controllers</span></span>

<span data-ttu-id="1edf3-104">Nesta fase de implantação de alta disponibilidade para Microsoft 365 autenticação federada nos serviços de infraestrutura do Azure, você configura dois controladores de domínio e o servidor de sincronização de diretórios na rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="1edf3-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you configure two domain controllers and the directory synchronization server in the Azure virtual network.</span></span> <span data-ttu-id="1edf3-105">Solicitações da Web de clientes para autenticação podem então ser autenticadas na rede virtual do Azure, em vez de o tráfego de autenticação ser enviado na conexão de VPN site a site à sua rede local.</span><span class="sxs-lookup"><span data-stu-id="1edf3-105">Client web requests for authentication can then be authenticated in the Azure virtual network, rather than sending that authentication traffic across the site-to-site VPN connection to your on-premises network.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1edf3-106">Os Serviços de Federação do Active Directory (AD FS) não podem usar o Azure Active Directory (Azure AD) como um substituto para controladores de domínio do Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1edf3-106">Active Directory Federation Services (AD FS) cannot use Azure Active Directory (Azure AD) as a substitute for Active Directory Domain Services (AD DS) domain controllers.</span></span> 
  
<span data-ttu-id="1edf3-107">Você deve concluir essa fase antes de passar para a [Fase 3: Configurar servidores do AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span><span class="sxs-lookup"><span data-stu-id="1edf3-107">You must complete this phase before moving on to [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="1edf3-108">Consulte [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span><span class="sxs-lookup"><span data-stu-id="1edf3-108">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a><span data-ttu-id="1edf3-109">Criar máquinas virtuais de controlador de domínio no Azure</span><span class="sxs-lookup"><span data-stu-id="1edf3-109">Create the domain controller virtual machines in Azure</span></span>

<span data-ttu-id="1edf3-110">Em primeiro lugar, você precisa preencher a coluna **Nome da máquina virtual** da Tabela M e modificar tamanhos de máquina virtual, conforme necessário, na coluna **Tamanho mínimo**.</span><span class="sxs-lookup"><span data-stu-id="1edf3-110">First, you need to fill out the **Virtual machine name** column of Table M and modify virtual machine sizes as needed in the **Minimum size** column.</span></span>
  
|<span data-ttu-id="1edf3-111">**Item**</span><span class="sxs-lookup"><span data-stu-id="1edf3-111">**Item**</span></span>|<span data-ttu-id="1edf3-112">**Nome da máquina virtual**</span><span class="sxs-lookup"><span data-stu-id="1edf3-112">**Virtual machine name**</span></span>|<span data-ttu-id="1edf3-113">**Imagem da galeria**</span><span class="sxs-lookup"><span data-stu-id="1edf3-113">**Gallery image**</span></span>|<span data-ttu-id="1edf3-114">**Tipo de armazenamento**</span><span class="sxs-lookup"><span data-stu-id="1edf3-114">**Storage type**</span></span>|<span data-ttu-id="1edf3-115">**Tamanho mínimo**</span><span class="sxs-lookup"><span data-stu-id="1edf3-115">**Minimum size**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1edf3-116">1.</span><span class="sxs-lookup"><span data-stu-id="1edf3-116">1.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png) <span data-ttu-id="1edf3-118"> (primeiro controlador de domínio, DC1 de exemplo)</span><span class="sxs-lookup"><span data-stu-id="1edf3-118">(first domain controller, example DC1)</span></span>  <br/> |<span data-ttu-id="1edf3-119">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="1edf3-119">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="1edf3-120">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="1edf3-120">Standard_LRS</span></span>  <br/> |<span data-ttu-id="1edf3-121">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="1edf3-121">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="1edf3-122">2.</span><span class="sxs-lookup"><span data-stu-id="1edf3-122">2.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png) <span data-ttu-id="1edf3-124"> (segundo controlador de domínio, DC2 de exemplo)</span><span class="sxs-lookup"><span data-stu-id="1edf3-124">(second domain controller, example DC2)</span></span>  <br/> |<span data-ttu-id="1edf3-125">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="1edf3-125">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="1edf3-126">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="1edf3-126">Standard_LRS</span></span>  <br/> |<span data-ttu-id="1edf3-127">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="1edf3-127">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="1edf3-128">3.</span><span class="sxs-lookup"><span data-stu-id="1edf3-128">3.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png) <span data-ttu-id="1edf3-130">(servidor de sincronização de diretório, exemplo DS1)</span><span class="sxs-lookup"><span data-stu-id="1edf3-130">(directory synchronization server, example DS1)</span></span>  <br/> |<span data-ttu-id="1edf3-131">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="1edf3-131">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="1edf3-132">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="1edf3-132">Standard_LRS</span></span>  <br/> |<span data-ttu-id="1edf3-133">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="1edf3-133">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="1edf3-134">4.</span><span class="sxs-lookup"><span data-stu-id="1edf3-134">4.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png) <span data-ttu-id="1edf3-136">(primeiro servidor do AD FS, exemplo ADFS1)</span><span class="sxs-lookup"><span data-stu-id="1edf3-136">(first AD FS server, example ADFS1)</span></span>  <br/> |<span data-ttu-id="1edf3-137">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="1edf3-137">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="1edf3-138">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="1edf3-138">Standard_LRS</span></span>  <br/> |<span data-ttu-id="1edf3-139">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="1edf3-139">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="1edf3-140">5.</span><span class="sxs-lookup"><span data-stu-id="1edf3-140">5.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png) <span data-ttu-id="1edf3-142">(segundo servidor do AD FS, exemplo ADFS2)</span><span class="sxs-lookup"><span data-stu-id="1edf3-142">(second AD FS server, example ADFS2)</span></span>  <br/> |<span data-ttu-id="1edf3-143">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="1edf3-143">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="1edf3-144">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="1edf3-144">Standard_LRS</span></span>  <br/> |<span data-ttu-id="1edf3-145">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="1edf3-145">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="1edf3-146">6.</span><span class="sxs-lookup"><span data-stu-id="1edf3-146">6.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png) <span data-ttu-id="1edf3-148">(primeiro servidor proxy de aplicativo Web, exemplo WEB1)</span><span class="sxs-lookup"><span data-stu-id="1edf3-148">(first web application proxy server, example WEB1)</span></span>  <br/> |<span data-ttu-id="1edf3-149">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="1edf3-149">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="1edf3-150">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="1edf3-150">Standard_LRS</span></span>  <br/> |<span data-ttu-id="1edf3-151">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="1edf3-151">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="1edf3-152">7.</span><span class="sxs-lookup"><span data-stu-id="1edf3-152">7.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png) <span data-ttu-id="1edf3-154">(segundo servidor proxy de aplicativo Web, exemplo WEB2)</span><span class="sxs-lookup"><span data-stu-id="1edf3-154">(second web application proxy server, example WEB2)</span></span>  <br/> |<span data-ttu-id="1edf3-155">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="1edf3-155">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="1edf3-156">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="1edf3-156">Standard_LRS</span></span>  <br/> |<span data-ttu-id="1edf3-157">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="1edf3-157">Standard_D2</span></span>  <br/> |
   
 <span data-ttu-id="1edf3-158">**Tabela M - Máquinas virtuais para a autenticação federada de alta disponibilidade para Microsoft 365 no Azure**</span><span class="sxs-lookup"><span data-stu-id="1edf3-158">**Table M - Virtual machines for the high availability federated authentication for Microsoft 365 in Azure**</span></span>
  
<span data-ttu-id="1edf3-159">Para obter a lista completa de tamanhos de máquinas virtuais, confira [Tamanhos das máquinas virtuais](/azure/virtual-machines/virtual-machines-windows-sizes).</span><span class="sxs-lookup"><span data-stu-id="1edf3-159">For the complete list of virtual machine sizes, see [Sizes for virtual machines](/azure/virtual-machines/virtual-machines-windows-sizes).</span></span>
  
<span data-ttu-id="1edf3-160">O seguinte bloco de comandos do Azure PowerShell cria as máquinas virtuais para os dois controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="1edf3-160">The following Azure PowerShell command block creates the virtual machines for the two domain controllers.</span></span> <span data-ttu-id="1edf3-161">Especifique os valores das variáveis, removendo os \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="1edf3-161">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="1edf3-162">Observe que este bloco de comandos do Azure PowerShell usa valores para as tabelas a seguir:</span><span class="sxs-lookup"><span data-stu-id="1edf3-162">Note that this Azure PowerShell command block uses values from the following tables:</span></span>
  
- <span data-ttu-id="1edf3-163">Tabela M, para suas máquinas virtuais</span><span class="sxs-lookup"><span data-stu-id="1edf3-163">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="1edf3-164">Tabela R, para seus grupos de recursos</span><span class="sxs-lookup"><span data-stu-id="1edf3-164">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="1edf3-165">Tabela V, para suas configurações de rede virtual</span><span class="sxs-lookup"><span data-stu-id="1edf3-165">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="1edf3-166">Tabela S, para suas sub-redes</span><span class="sxs-lookup"><span data-stu-id="1edf3-166">Table S, for your subnets</span></span>
    
- <span data-ttu-id="1edf3-167">Tabela I, para seu endereço IP estático</span><span class="sxs-lookup"><span data-stu-id="1edf3-167">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="1edf3-168">Tabela A, para seus conjuntos de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="1edf3-168">Table A, for your availability sets</span></span>
    
<span data-ttu-id="1edf3-169">Lembre-se de que você definiu as Tabelas R, V, S, I e A na [Fase 1: Configurar o Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="1edf3-169">Recall that you defined Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1edf3-170">[!OBSERVAçãO] O comando a seguir define o uso da versão mais recente do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1edf3-170">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="1edf3-171">Consulte [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="1edf3-171">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="1edf3-172">Quando tiver fornecido todos os valores corretos, execute o bloco resultante no prompt do Azure PowerShell ou no Ambiente de Script Integrado (ISE) do PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="1edf3-172">When you have supplied all the correct values, run the resulting block at the Azure PowerShell prompt or in the PowerShell Integrated Script Environment (ISE) on your local computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="1edf3-173">Para gerar blocos de comando prontos para execução do PowerShell com base em suas configurações personalizadas, use esta Microsoft Excel de trabalho [de configuração](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="1edf3-173">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="1edf3-p105">Como essas máquinas virtuais são para um aplicativo de intranet, elas não recebem um endereço IP público ou um rótulo de nome de domínio DNS, nem estão expostas à Internet. No entanto, isso também significa que você não pode se conectar a eles no portal do Azure. A opção **Conectar** não está disponível quando você visualiza as propriedades da máquina virtual. Use o acessório Conexão de Área de Trabalho Remota ou outra ferramenta de Área de Trabalho Remota para se conectar à máquina virtual usando seu endereço IP privado ou o nome DNS da intranet.</span><span class="sxs-lookup"><span data-stu-id="1edf3-p105">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
## <a name="configure-the-first-domain-controller"></a><span data-ttu-id="1edf3-178">Configurar o primeiro controlador de domínio</span><span class="sxs-lookup"><span data-stu-id="1edf3-178">Configure the first domain controller</span></span>

<span data-ttu-id="1edf3-p106">Use o cliente de área de trabalho remota de sua preferência e crie uma conexão de área de trabalho remota com a primeira máquina virtual de controlador de domínio. Use seu nome de computador ou DNS de intranet e as credenciais da conta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="1edf3-p106">Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="1edf3-181">Em seguida, adicione o disco de dados extra ao primeiro controlador de domínio com este comando Windows PowerShell prompt de comando na primeira máquina virtual do controlador de **domínio:**</span><span class="sxs-lookup"><span data-stu-id="1edf3-181">Next, add the extra data disk to the first domain controller with this command from a Windows PowerShell command prompt **on the first domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="1edf3-182">Em seguida, teste a conectividade do primeiro controlador de domínio com os locais na rede da sua organização usando o comando **ping** para executar ping em nomes e endereços IP de recursos nessa rede.</span><span class="sxs-lookup"><span data-stu-id="1edf3-182">Next, test the first domain controller's connectivity to locations on your organization network by using the **ping** command to ping names and IP addresses of resources on your organization network.</span></span>
  
<span data-ttu-id="1edf3-p107">Esse procedimento assegura que a resolução de nomes DNS esteja funcionando corretamente (que a máquina virtual esteja corretamente configurada com os servidores DNS locais) e que pacotes possam ser enviados de e para a rede virtual entre locais. Se esse teste básico falhar, entre em contato com seu departamento de TI para solucionar problemas de entrega de pacotes e resolução de nomes DNS.</span><span class="sxs-lookup"><span data-stu-id="1edf3-p107">This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network. If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.</span></span>
  
<span data-ttu-id="1edf3-185">Em seguida, no prompt de comandos do Windows PowerShell no primeiro controlador de domínio, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="1edf3-185">Next, from the Windows PowerShell command prompt on the first domain controller, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

<span data-ttu-id="1edf3-p108">Você será solicitado a fornecer as credenciais de uma conta de administrador de domínio. O computador será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="1edf3-p108">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
## <a name="configure-the-second-domain-controller"></a><span data-ttu-id="1edf3-188">Configurar o segundo controlador de domínio</span><span class="sxs-lookup"><span data-stu-id="1edf3-188">Configure the second domain controller</span></span>

<span data-ttu-id="1edf3-p109">Use o cliente de área de trabalho remota de sua preferência e crie uma conexão de área de trabalho remota com a segunda máquina virtual de controlador de domínio. Use seu nome de computador ou DNS de intranet e as credenciais da conta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="1edf3-p109">Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="1edf3-191">Em seguida, você precisa adicionar o disco de dados extra ao segundo controlador de domínio com este comando Windows PowerShell prompt de comando na segunda máquina **virtual do** controlador de domínio :</span><span class="sxs-lookup"><span data-stu-id="1edf3-191">Next, you need to add the extra data disk to the second domain controller with this command from a Windows PowerShell command prompt **on the second domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="1edf3-192">Em seguida, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="1edf3-192">Next, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

<span data-ttu-id="1edf3-p110">Você será solicitado a fornecer as credenciais de uma conta de administrador de domínio. O computador será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="1edf3-p110">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
<span data-ttu-id="1edf3-195">Em seguida, você precisará atualizar os servidores DNS da sua rede virtual, para que o Azure atribua máquinas virtuais aos endereços IP dos dois novos controladores de domínio para uso como seus servidores DNS.</span><span class="sxs-lookup"><span data-stu-id="1edf3-195">Next, you need to update the DNS servers for your virtual network so that Azure assigns virtual machines the IP addresses of the two new domain controllers to use as their DNS servers.</span></span> <span data-ttu-id="1edf3-196">Preencha as variáveis e execute esses comandos de um prompt de Windows PowerShell de comando no computador local:</span><span class="sxs-lookup"><span data-stu-id="1edf3-196">Fill in the variables and then run these commands from a Windows PowerShell command prompt on your local computer:</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

<span data-ttu-id="1edf3-p112">Observe que reiniciamos os dois controladores de domínio para que eles não sejam configurados com os servidores DNS locais como servidores DNS. Como ambos são servidores DNS, eles foram configurados automaticamente com os servidores DNS locais como encaminhadores de DNS quando foram promovidos para controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="1edf3-p112">Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers. Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.</span></span>
  
<span data-ttu-id="1edf3-p113">Em seguida, precisamos criar um site de replicação do Active Directory para garantir que os servidores na rede virtual do Azure usem os controladores de domínio locais. Conecte a um dos controlador de domínio com uma conta de administrador de domínio e execute os seguintes comandos em um prompt do Windows PowerShell em nível de administrador:</span><span class="sxs-lookup"><span data-stu-id="1edf3-p113">Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers. Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:</span></span>
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a><span data-ttu-id="1edf3-201">Configurar o servidor de sincronização de diretórios</span><span class="sxs-lookup"><span data-stu-id="1edf3-201">Configure the directory synchronization server</span></span>

<span data-ttu-id="1edf3-202">Use o cliente de área de trabalho remota de sua escolha e crie uma conexão de área de trabalho remota com a máquina virtual do servidor de sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="1edf3-202">Use the remote desktop client of your choice and create a remote desktop connection to the directory synchronization server virtual machine.</span></span> <span data-ttu-id="1edf3-203">Use seu nome de computador ou DNS de intranet e as credenciais da conta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="1edf3-203">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="1edf3-204">Em seguida, junte-o ao domínio apropriado do AD DS com esses comandos no prompt Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1edf3-204">Next, join it to the appropriate AD DS domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="1edf3-205">Veja a seguir a configuração resultante da conclusão bem-sucedida dessa fase, com nomes de computador de espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="1edf3-205">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="1edf3-206">**Fase 2: Os controladores de domínio e o servidor de sincronização de diretórios para sua infraestrutura de autenticação federada de alta disponibilidade no Azure**</span><span class="sxs-lookup"><span data-stu-id="1edf3-206">**Phase 2: The domain controllers and directory synchronization server for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 2 da infraestrutura de autenticação Microsoft 365 de autenticação federada no Azure com controladores de domínio](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a><span data-ttu-id="1edf3-208">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1edf3-208">Next step</span></span>

<span data-ttu-id="1edf3-209">Use [a Fase 3: Configurar servidores do AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) para continuar configurando essa carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1edf3-209">Use [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1edf3-210">Confira também</span><span class="sxs-lookup"><span data-stu-id="1edf3-210">See Also</span></span>

[<span data-ttu-id="1edf3-211">Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure</span><span class="sxs-lookup"><span data-stu-id="1edf3-211">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="1edf3-212">Identidade federada para seu ambiente Microsoft 365 dev/test</span><span class="sxs-lookup"><span data-stu-id="1edf3-212">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="1edf3-213">Centro de soluções e arquitetura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1edf3-213">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)