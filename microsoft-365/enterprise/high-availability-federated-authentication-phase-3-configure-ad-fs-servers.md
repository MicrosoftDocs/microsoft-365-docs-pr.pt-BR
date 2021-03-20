---
title: Autenticação federada de alta disponibilidade Fase 3 Configurar servidores do AD FS
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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 202b76ff-74a6-4486-ada1-a9bf099dab8f
description: Saiba como criar e configurar os servidores do AD FS para sua autenticação federada de alta disponibilidade para o Microsoft 365 no Microsoft Azure.
ms.openlocfilehash: 388a99aa496c4ecd9145759d4dfb1b9441b4fb2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909793"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a><span data-ttu-id="5d391-103">Autenticação federada de alta disponibilidade Fase 3: configurar servidores de AD FS</span><span class="sxs-lookup"><span data-stu-id="5d391-103">High availability federated authentication Phase 3: Configure AD FS servers</span></span>

<span data-ttu-id="5d391-104">Nesta fase de implantação de alta disponibilidade para autenticação federada do Microsoft 365 nos serviços de infraestrutura do Azure, você cria um balanceador de carga interno e dois servidores AD FS.</span><span class="sxs-lookup"><span data-stu-id="5d391-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="5d391-105">Você deve concluir essa fase antes de passar para a [Fase 4: Configurar proxies de](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="5d391-105">You must complete this phase before moving on to [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span></span> <span data-ttu-id="5d391-106">Consulte [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span><span class="sxs-lookup"><span data-stu-id="5d391-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a><span data-ttu-id="5d391-107">Criar máquinas virtuais dos servidores do AD FS no Azure</span><span class="sxs-lookup"><span data-stu-id="5d391-107">Create the AD FS server virtual machines in Azure</span></span>

<span data-ttu-id="5d391-p102">Use o seguinte bloco de comandos do PowerShell para criar as máquinas virtuais para os dois servidores do AD FS. Este conjunto de comandos do PowerShell usa valores das seguintes tabelas:</span><span class="sxs-lookup"><span data-stu-id="5d391-p102">Use the following block of PowerShell commands to create the virtual machines for the two AD FS servers. This PowerShell command set uses values from the following tables:</span></span>
  
- <span data-ttu-id="5d391-110">Tabela M, para suas máquinas virtuais</span><span class="sxs-lookup"><span data-stu-id="5d391-110">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="5d391-111">Tabela R, para seus grupos de recursos</span><span class="sxs-lookup"><span data-stu-id="5d391-111">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="5d391-112">Tabela V, para suas configurações de rede virtual</span><span class="sxs-lookup"><span data-stu-id="5d391-112">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="5d391-113">Tabela S, para suas sub-redes</span><span class="sxs-lookup"><span data-stu-id="5d391-113">Table S, for your subnets</span></span>
    
- <span data-ttu-id="5d391-114">Tabela I, para seu endereço IP estático</span><span class="sxs-lookup"><span data-stu-id="5d391-114">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="5d391-115">Tabela A, para seus conjuntos de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="5d391-115">Table A, for your availability sets</span></span>
    
<span data-ttu-id="5d391-116">Lembre-se de que você definiu a Tabela M na Fase [2: Configurar](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) controladores de domínio e Tabelas R, V, S, I e A na Fase [1: Configurar o Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="5d391-116">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d391-117">[!OBSERVAçãO] O comando a seguir define o uso da versão mais recente do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d391-117">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="5d391-118">Consulte [Começar com o Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="5d391-118">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="5d391-119">Em primeiro lugar, crie um balanceador de carga interno do Azure para os dois servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="5d391-119">First, you create an Azure internal load balancer for the two AD FS servers.</span></span> <span data-ttu-id="5d391-120">Especifique os valores das variáveis, removendo os \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="5d391-120">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="5d391-121">Quando tiver fornecido todos os valores apropriados, execute o bloco resultante no prompt de comando do Azure PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d391-121">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="5d391-122">Para gerar blocos de comando prontos para execução do PowerShell com base em suas configurações personalizadas, use esta planilha de configuração [do Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="5d391-122">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up key variables
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$privIP="<Table I - Item 4 - Value column>"
$rgName=<Table R - Item 4 - Resource group name column>"

$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "ADFSServers-LBFE" -PrivateIPAddress $privIP -Subnet $subnet
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "ADFSServers-LBBE"

$healthProbe=New-AzLoadBalancerProbeConfig -Name WebServersProbe -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "HTTPSTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

<span data-ttu-id="5d391-123">Em seguida, crie máquinas virtuais dos servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="5d391-123">Next, create the AD FS server virtual machines.</span></span>
  
<span data-ttu-id="5d391-124">Quando tiver fornecido todos os valores apropriados, execute o bloco resultante no prompt de comando do Azure PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d391-124">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$avName="<Table A - Item 2 - Availability set name column>"
$rgNameTier="<Table R - Item 2 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first ADFS server virtual machine
$vmName="<Table M - Item 4 - Virtual machine name column>"
$vmSize="<Table M - Item 4 - Minimum size column>"
$staticIP="<Table I - Item 5 - Value column>"
$diskStorageType="<Table M - Item 4 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second AD FS virtual machine
$vmName="<Table M - Item 5 - Virtual machine name column>"
$vmSize="<Table M - Item 5 - Minimum size column>"
$staticIP="<Table I - Item 6 - Value column>"
$diskStorageType="<Table M - Item 5 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

```

> [!NOTE]
> <span data-ttu-id="5d391-p105">Como essas máquinas virtuais são para um aplicativo de intranet, elas não recebem um endereço IP público ou um rótulo de nome de domínio DNS, nem estão expostas à Internet. No entanto, isso também significa que você não pode se conectar a eles no portal do Azure. A opção **Conectar** não está disponível quando você visualiza as propriedades da máquina virtual. Use o acessório Conexão de Área de Trabalho Remota ou outra ferramenta de Área de Trabalho Remota para se conectar à máquina virtual usando seu endereço IP privado ou o nome DNS da intranet.</span><span class="sxs-lookup"><span data-stu-id="5d391-p105">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
<span data-ttu-id="5d391-p106">Para cada máquina virtual, use o cliente de área de trabalho remota de sua preferência e crie uma conexão de área de trabalho remota. Use seu nome de computador ou DNS de intranet e as credenciais da conta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="5d391-p106">For each virtual machine, use the remote desktop client of your choice and create a remote desktop connection. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="5d391-131">Para cada máquina virtual, junte-os ao domínio apropriado dos Serviços de Domínio do Active Directory (AD DS) com esses comandos no prompt Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d391-131">For each virtual machine, join them to the appropriate Active Directory Domain Services (AD DS) domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="5d391-132">Veja a seguir a configuração resultante da conclusão bem-sucedida dessa fase, com nomes de computador de espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="5d391-132">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="5d391-133">**Fase 3: Os servidores do AD FS e o balanceador de carga interno para a sua infraestrutura de autenticação federada de alta disponibilidade no Azure**</span><span class="sxs-lookup"><span data-stu-id="5d391-133">**Phase 3: The AD FS servers and internal load balancer for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 3 da infraestrutura de autenticação federada do Microsoft 365 de alta disponibilidade no Azure com os servidores do AD FS](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a><span data-ttu-id="5d391-135">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5d391-135">Next step</span></span>

<span data-ttu-id="5d391-136">Use [a Fase 4: Configurar proxies de](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) aplicativo Web para continuar configurando essa carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="5d391-136">Use [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d391-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="5d391-137">See Also</span></span>

[<span data-ttu-id="5d391-138">Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure</span><span class="sxs-lookup"><span data-stu-id="5d391-138">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="5d391-139">Identidade federada para seu ambiente de dev/test do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5d391-139">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)