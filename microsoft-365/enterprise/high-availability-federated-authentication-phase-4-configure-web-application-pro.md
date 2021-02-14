---
title: Autenticação federada de alta disponibilidade Fase 4 Configurar proxies de aplicativos Web
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
ms.assetid: 1c903173-67cd-47da-86d9-d333972dda80
description: 'Resumo: configure os servidores proxy de aplicativo Web para sua autenticação federada de alta disponibilidade para o Microsoft 365 no Microsoft Azure.'
ms.openlocfilehash: fd63274ffb9528cedb88fc2ba77834cfd56664d4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687305"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a><span data-ttu-id="ab379-103">Autenticação federada de alta disponibilidade Fase 4: configurar proxies de aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="ab379-103">High availability federated authentication Phase 4: Configure web application proxies</span></span>

<span data-ttu-id="ab379-104">Nesta fase de implantação da alta disponibilidade da autenticação federada do Microsoft 365 nos serviços de infraestrutura do Azure, você cria um balanceador de carga interno e dois servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="ab379-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="ab379-105">Você deve concluir essa fase antes de passar para a [Fase 5: Configurar a autenticação federada para o Microsoft 365.](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)</span><span class="sxs-lookup"><span data-stu-id="ab379-105">You must complete this phase before moving on to [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="ab379-106">Confira [Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) para todas as fases.</span><span class="sxs-lookup"><span data-stu-id="ab379-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a><span data-ttu-id="ab379-107">Criar o balanceador de carga voltado para a Internet no Azure</span><span class="sxs-lookup"><span data-stu-id="ab379-107">Create the Internet-facing load balancer in Azure</span></span>

<span data-ttu-id="ab379-108">Você deve criar um balanceador de carga voltado para a Internet para que o Azure distribua o tráfego de autenticação de cliente de entrada proveniente da Internet uniformemente entre os dois servidores proxy de aplicativos Web.</span><span class="sxs-lookup"><span data-stu-id="ab379-108">You must create an Internet-facing load balancer so that Azure distributes the incoming client authentication traffic from the Internet evenly among the two web application proxy servers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab379-109">[!OBSERVAçãO] O comando a seguir define o uso da versão mais recente do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab379-109">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="ab379-110">Confira [Começar a trabalhar com o Azure PowerShell.](https://docs.microsoft.com/powershell/azure/get-started-azureps)</span><span class="sxs-lookup"><span data-stu-id="ab379-110">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="ab379-111">Quando tiver fornecido os valores de localização e grupo de recursos, execute o bloco resultante no prompt de comando do Azure PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab379-111">When you have supplied location and resource group values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="ab379-112">Para gerar blocos de comandos do PowerShell prontos para execução com base em suas configurações personalizadas, use esta planilha [de configuração do Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="ab379-112">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up key variables
$locName="<your Azure location>"
$rgName="<Table R - Item 4 - Resource group name column>"

$publicIP=New-AzPublicIpAddress -ResourceGroupName $rgName -Name "WebProxyPublicIP" -Location $LocName -AllocationMethod "Static"
$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "WebAppProxyServers-LBFE" -PublicIpAddress $publicIP
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "WebAppProxyServers-LBBE"
$healthProbe=New-AzLoadBalancerProbeConfig -Name "WebServersProbe" -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "WebTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

<span data-ttu-id="ab379-113">Para exibir o endereço IP público atribuído ao seu balanceador de carga voltado para a Internet, execute estes comandos no prompt de comando do Azure PowerShell no computador local:</span><span class="sxs-lookup"><span data-stu-id="ab379-113">To display the public IP address assigned to your Internet-facing load balancer, run these commands at the Azure PowerShell command prompt on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a><span data-ttu-id="ab379-114">Determinar o FQDN do seu serviço de federação e criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="ab379-114">Determine your federation service FQDN and create DNS records</span></span>

<span data-ttu-id="ab379-115">Você precisa determinar o nome DNS para identificar o nome do seu serviço de federação na Internet.</span><span class="sxs-lookup"><span data-stu-id="ab379-115">You need to determine the DNS name to identify your federation service name on the Internet.</span></span> <span data-ttu-id="ab379-116">O Azure AD Connect configurará o Microsoft 365 com esse nome na Fase 5, que se tornará parte da URL que o Microsoft 365 envia aos clientes conectados para obter um token de segurança.</span><span class="sxs-lookup"><span data-stu-id="ab379-116">Azure AD Connect will configure Microsoft 365 with this name in Phase 5, which will become part of the URL that Microsoft 365 sends to connecting clients to get a security token.</span></span> <span data-ttu-id="ab379-117">Um exemplo é fs.contoso.com (fs representa serviço de federação).</span><span class="sxs-lookup"><span data-stu-id="ab379-117">An example is fs.contoso.com (fs stands for federation service).</span></span>
  
<span data-ttu-id="ab379-118">Depois que você tiver o FQDN do serviço de federação, crie para ele um registro A de domínio DNS público que seja resolvido para o endereço IP público do balanceador de carga voltado para a Internet do Azure.</span><span class="sxs-lookup"><span data-stu-id="ab379-118">Once you have your federation service FDQN, create a public DNS domain A record for the federation service FDQN that resolves to the public IP address of the Azure Internet-facing load balancer.</span></span>
  
|<span data-ttu-id="ab379-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ab379-119">**Name**</span></span>|<span data-ttu-id="ab379-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ab379-120">**Type**</span></span>|<span data-ttu-id="ab379-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ab379-121">**TTL**</span></span>|<span data-ttu-id="ab379-122">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ab379-122">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab379-123">FQDN do serviço de federação</span><span class="sxs-lookup"><span data-stu-id="ab379-123">federation service FDQN</span></span>  <br/> |<span data-ttu-id="ab379-124">A</span><span class="sxs-lookup"><span data-stu-id="ab379-124">A</span></span>  <br/> |<span data-ttu-id="ab379-125">3600</span><span class="sxs-lookup"><span data-stu-id="ab379-125">3600</span></span>  <br/> |<span data-ttu-id="ab379-126">endereço IP público do balanceador de carga voltado para a Internet do Azure (exibido pelo comando **Write-Host** na seção anterior)</span><span class="sxs-lookup"><span data-stu-id="ab379-126">public IP address of the Azure Internet-facing load balancer (displayed by the **Write-Host** command in the previous section)</span></span> <br/> |
   
<span data-ttu-id="ab379-127">Este é um exemplo:</span><span class="sxs-lookup"><span data-stu-id="ab379-127">Here is an example:</span></span>
  
|<span data-ttu-id="ab379-128">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ab379-128">**Name**</span></span>|<span data-ttu-id="ab379-129">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ab379-129">**Type**</span></span>|<span data-ttu-id="ab379-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ab379-130">**TTL**</span></span>|<span data-ttu-id="ab379-131">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ab379-131">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab379-132">fs.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab379-132">fs.contoso.com</span></span>  <br/> |<span data-ttu-id="ab379-133">A</span><span class="sxs-lookup"><span data-stu-id="ab379-133">A</span></span>  <br/> |<span data-ttu-id="ab379-134">3600</span><span class="sxs-lookup"><span data-stu-id="ab379-134">3600</span></span>  <br/> |<span data-ttu-id="ab379-135">131.107.249.117</span><span class="sxs-lookup"><span data-stu-id="ab379-135">131.107.249.117</span></span>  <br/> |
   
<span data-ttu-id="ab379-136">Em seguida, adicione um registro de endereço DNS ao namespace DNS particular da sua organização que resolva o FQDN do serviço de federação para o endereço IP privado atribuído ao balanceador de carga interno dos servidores do AD FS (Tabela I, item 4, coluna Valor).</span><span class="sxs-lookup"><span data-stu-id="ab379-136">Next, add a DNS address record to your organization's private DNS namespace that resolves your federation service FQDN to the private IP address assigned to the internal load balancer for the AD FS servers (Table I, item 4, Value column).</span></span>
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a><span data-ttu-id="ab379-137">Criar máquinas virtuais dos servidores proxy de aplicativos Web no Azure</span><span class="sxs-lookup"><span data-stu-id="ab379-137">Create the web application proxy server virtual machines in Azure</span></span>

<span data-ttu-id="ab379-138">Use o seguinte bloco de comandos do Azure PowerShell para criar as máquinas virtuais para os dois servidores proxy de aplicativos Web. </span><span class="sxs-lookup"><span data-stu-id="ab379-138">Use the following block of Azure PowerShell commands to create the virtual machines for the two web application proxy servers.</span></span> 
  
<span data-ttu-id="ab379-139">Observe que o seguinte comando do Azure PowerShell define valores de uso das tabelas a seguir:</span><span class="sxs-lookup"><span data-stu-id="ab379-139">Note that the following Azure PowerShell command sets use values from the following tables:</span></span>
  
- <span data-ttu-id="ab379-140">Tabela M, para suas máquinas virtuais</span><span class="sxs-lookup"><span data-stu-id="ab379-140">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="ab379-141">Tabela R, para seus grupos de recursos</span><span class="sxs-lookup"><span data-stu-id="ab379-141">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="ab379-142">Tabela V, para suas configurações de rede virtual</span><span class="sxs-lookup"><span data-stu-id="ab379-142">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="ab379-143">Tabela S, para suas sub-redes</span><span class="sxs-lookup"><span data-stu-id="ab379-143">Table S, for your subnets</span></span>
    
- <span data-ttu-id="ab379-144">Tabela I, para seu endereço IP estático</span><span class="sxs-lookup"><span data-stu-id="ab379-144">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="ab379-145">Tabela A, para seus conjuntos de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="ab379-145">Table A, for your availability sets</span></span>
    
<span data-ttu-id="ab379-146">Lembre-se de que você definiu a Tabela M na Fase [2: Configurar](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) os controladores de domínio e as Tabelas R, V, S, I e A na [Fase 1: Configurar o Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="ab379-146">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
<span data-ttu-id="ab379-147">Quando tiver fornecido todos os valores apropriados, execute o bloco resultante no prompt de comando do Azure PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab379-147">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 3 - Subnet name column>"
$avName="<Table A - Item 3 - Availability set name column>"
$rgNameTier="<Table R - Item 3 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first web application proxy server virtual machine
$vmName="<Table M - Item 6 - Virtual machine name column>"
$vmSize="<Table M - Item 6 - Minimum size column>"
$staticIP="<Table I - Item 7 - Value column>"
$diskStorageType="<Table M - Item 6 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second web application proxy virtual machine
$vmName="<Table M - Item 7 - Virtual machine name column>"
$vmSize="<Table M - Item 7 - Minimum size column>"
$staticIP="<Table I - Item 8 - Value column>"
$diskStorageType="<Table M - Item 7 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="ab379-p104">Como essas máquinas virtuais são para um aplicativo de intranet, elas não recebem um endereço IP público ou um rótulo de nome de domínio DNS, nem estão expostas à Internet. No entanto, isso também significa que você não pode se conectar a eles no portal do Azure. A opção **Conectar** não está disponível quando você visualiza as propriedades da máquina virtual. Use o acessório Conexão de Área de Trabalho Remota ou outra ferramenta de Área de Trabalho Remota para se conectar à máquina virtual usando seu endereço IP privado ou o nome DNS da intranet e as credenciais da conta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="ab379-p104">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="ab379-152">Veja a seguir a configuração resultante da conclusão bem-sucedida dessa fase, com nomes de computador de espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="ab379-152">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="ab379-153">**Fase 4: O balanceador de carga voltado para a Internet e os servidores proxy de aplicativos Web para a sua infraestrutura de autenticação federada de alta disponibilidade no Azure**</span><span class="sxs-lookup"><span data-stu-id="ab379-153">**Phase 4: The Internet-facing load balancer and web application proxy servers for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 4 da infraestrutura de autenticação federada do Microsoft 365 de alta disponibilidade no Azure com os servidores proxy de aplicativos Web](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a><span data-ttu-id="ab379-155">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ab379-155">Next step</span></span>

<span data-ttu-id="ab379-156">Use [a Fase 5: Configurar a autenticação federada para o Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) para continuar configurando essa carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ab379-156">Use [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab379-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="ab379-157">See Also</span></span>

[<span data-ttu-id="ab379-158">Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure</span><span class="sxs-lookup"><span data-stu-id="ab379-158">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="ab379-159">Identidade federada para seu ambiente de dev/teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab379-159">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="ab379-160">Centro de soluções e arquitetura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab379-160">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

