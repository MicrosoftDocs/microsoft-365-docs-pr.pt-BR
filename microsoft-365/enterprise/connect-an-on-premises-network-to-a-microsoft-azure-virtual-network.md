---
title: Conectar uma rede local a uma rede virtual do Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 81190961-5454-4a5c-8b0e-6ae75b9fb035
description: 'Resumo: Aprenda a configurar uma rede virtual Azure entre locais para cargas de trabalho de servidor do Office com uma conexão VPN site a site.'
ms.openlocfilehash: 00fd1c2246e9e9ac3eb55ca5ece9d84ecf49a1d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907703"
---
# <a name="connect-an-on-premises-network-to-a-microsoft-azure-virtual-network"></a><span data-ttu-id="1ad33-103">Conectar uma rede local a uma rede virtual do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="1ad33-103">Connect an on-premises network to a Microsoft Azure virtual network</span></span>

<span data-ttu-id="1ad33-p101">Uma rede virtual entre locais do Azure está conectada à sua rede local, ampliando sua rede para incluir sub-redes e máquinas virtuais hospedadas em serviços na infraestrutura do Azure. Esta conexão permite que os computadores na sua rede local acessem diretamente máquinas virtuais no Azure e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p101">A cross-premises Azure virtual network is connected to your on-premises network, extending your network to include subnets and virtual machines hosted in Azure infrastructure services. This connection lets computers on your on-premises network to directly access virtual machines in Azure and vice versa.</span></span> 

<span data-ttu-id="1ad33-106">Por exemplo, um servidor de sincronização de diretórios em execução em uma máquina virtual do Azure precisa consultar seus controladores de domínio locais para alterações nas contas e sincronizar essas alterações com sua assinatura Microsoft 365 local.</span><span class="sxs-lookup"><span data-stu-id="1ad33-106">For example, a directory synchronization server running on an Azure virtual machine needs to query your on-premises domain controllers for changes to accounts and synchronize those changes with your Microsoft 365 subscription.</span></span> <span data-ttu-id="1ad33-107">Este artigo mostra como configurar uma rede virtual do Azure entre locais usando uma conexão VPN (rede virtual privada) site a site que está pronta para hospedar máquinas virtuais do Azure.</span><span class="sxs-lookup"><span data-stu-id="1ad33-107">This article shows you how to set up a cross-premises Azure virtual network using a site-to-site virtual private network (VPN) connection that is ready to host Azure virtual machines.</span></span>

## <a name="configure-a-cross-premises-azure-virtual-network"></a><span data-ttu-id="1ad33-108">Configurar uma rede virtual entre locais do Azure</span><span class="sxs-lookup"><span data-stu-id="1ad33-108">Configure a cross-premises Azure virtual network</span></span>

<span data-ttu-id="1ad33-p103">Suas máquinas virtuais no Azure não precisam ser isoladas do seu ambiente local. Para conectar as máquinas virtuais do Azure aos recursos da sua rede local, é preciso configurar uma rede virtual do Azure entre locais. O diagrama a seguir mostra os componentes necessários para implantar uma rede virtual do Azure entre locais com uma máquina virtual no Azure.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p103">Your virtual machines in Azure don't have to be isolated from your on-premises environment. To connect Azure virtual machines to your on-premises network resources, you must configure a cross-premises Azure virtual network. The following diagram shows the required components to deploy a cross-premises Azure virtual network with a virtual machine in Azure.</span></span>
  
![Rede local conectada ao Microsoft Azure por meio de uma conexão VPN site a site](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
 
<span data-ttu-id="1ad33-p104">No diagrama, há duas redes conectadas por uma conexão VPN site a site: a rede local e a rede virtual do Azure. A conexão VPN site a site:</span><span class="sxs-lookup"><span data-stu-id="1ad33-p104">In the diagram, there are two networks connected by a site-to-site VPN connection: the on-premises network and the Azure virtual network. The site-to-site VPN connection is:</span></span>

- <span data-ttu-id="1ad33-115">Ocorre entre dois pontos de extremidade endereçáveis ​​e localizados na Internet pública.</span><span class="sxs-lookup"><span data-stu-id="1ad33-115">Between two endpoints that are addressable and located on the public Internet.</span></span>
- <span data-ttu-id="1ad33-116">É encerrada por um dispositivo VPN na rede local e um gateway VPN Azure na rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="1ad33-116">Terminated by a VPN device on the on-premises network and an Azure VPN gateway on the Azure virtual network.</span></span>

<span data-ttu-id="1ad33-p105">A rede virtual do Azure hospeda máquinas virtuais. O tráfego originado das máquinas virtuais na rede virtual do Azure é encaminhado ao gateway VPN que, então, encaminha o tráfego pela conexão VPN site a site para o dispositivo VPN na rede local. A infraestrutura de roteamento da rede local encaminha então o tráfego ao seu destino.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p105">The Azure virtual network hosts virtual machines. Network traffic originating from virtual machines on the Azure virtual network gets forwarded to the VPN gateway, which then forwards the traffic across the site-to-site VPN connection to the VPN device on the on-premises network. The routing infrastructure of the on-premises network then forwards the traffic to its destination.</span></span>

>[!Note]
><span data-ttu-id="1ad33-p106">Você também pode usar o [ExpressRoute](https://azure.microsoft.com/services/expressroute/), que é uma conexão direta entre sua organização e a rede da Microsoft. O tráfego pelo ExpressRoute não viaja pela Internet pública. Este artigo não descreve o uso do ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p106">You can also use [ExpressRoute](https://azure.microsoft.com/services/expressroute/), which is a direct connection between your organization and Microsoft's network. Traffic over ExpressRoute does not travel over the public Internet. This article does not describe the use of ExpressRoute.</span></span>
>
  
<span data-ttu-id="1ad33-123">Para configurar a conexão VPN entre a rede local e sua rede virtual do Azure, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1ad33-123">To set up the VPN connection between your Azure virtual network and your on-premises network, follow these steps:</span></span> 
  
1. <span data-ttu-id="1ad33-124">**Local** Defina e crie um roteamento de rede local para o espaço de endereço da rede virtual do Azure que aponte para o seu dispositivo VPN local.</span><span class="sxs-lookup"><span data-stu-id="1ad33-124">**On-premises:** Define and create an on-premises network route for the address space of the Azure virtual network that points to your on-premises VPN device.</span></span>
    
2. <span data-ttu-id="1ad33-125">**Microsoft Azure:** Crie uma rede virtual do Azure com uma conexão VPN site a site.</span><span class="sxs-lookup"><span data-stu-id="1ad33-125">**Microsoft Azure:** Create an Azure virtual network with a site-to-site VPN connection.</span></span> 
    
3. <span data-ttu-id="1ad33-126">**Local:** Configure o hardware ou software local de seu dispositivo VPN para encerrar a conexão VPN, que usa o protocolo IPsec (segurança).</span><span class="sxs-lookup"><span data-stu-id="1ad33-126">**On premises:** Configure your on-premises hardware or software VPN device to terminate the VPN connection, which uses Internet Protocol security (IPsec).</span></span>
    
<span data-ttu-id="1ad33-127">Depois de estabelecer a conexão VPN de site a site, você pode adicionar máquinas virtuais do Azure às sub-redes da rede virtual.</span><span class="sxs-lookup"><span data-stu-id="1ad33-127">After you establish the site-to-site VPN connection, you add Azure virtual machines to the subnets of the virtual network.</span></span>
  
## <a name="plan-your-azure-virtual-network"></a><span data-ttu-id="1ad33-128">Planejar sua rede virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="1ad33-128">Plan your Azure virtual network</span></span>
<a name="PlanningVirtual"></a>

### <a name="prerequisites"></a><span data-ttu-id="1ad33-129">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1ad33-129">Prerequisites</span></span>
<a name="Prerequisites"></a>

- <span data-ttu-id="1ad33-p107">Uma assinatura do Azure. Para saber mais sobre assinaturas do Azure, vá para a [página Como comprar o Azure](https://azure.microsoft.com/pricing/purchase-options/).</span><span class="sxs-lookup"><span data-stu-id="1ad33-p107">An Azure subscription. For information about Azure subscriptions, go to the [How To Buy Azure page](https://azure.microsoft.com/pricing/purchase-options/).</span></span>
    
- <span data-ttu-id="1ad33-132">Um espaço de endereço IPv4 privado disponível para atribuir à rede virtual e às suas sub-redes, com espaço suficiente para ampliação a fim de acomodar a quantidade de máquinas virtuais necessárias agora e no futuro.</span><span class="sxs-lookup"><span data-stu-id="1ad33-132">An available private IPv4 address space to assign to the virtual network and its subnets, with sufficient room for growth to accommodate the number of virtual machines needed now and in the future.</span></span>
    
- <span data-ttu-id="1ad33-p108">Um dispositivo VPN disponível em sua rede local para encerrar a conexão VPN site a site compatível com os requisitos para IPsec. Para saber mais, confira [VPN para conexões de rede virtual de site a site](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span><span class="sxs-lookup"><span data-stu-id="1ad33-p108">An available VPN device in your on-premises network to terminate the site-to-site VPN connection that supports the requirements for IPsec. For more information, see [About VPN devices for site-to-site virtual network connections](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
    
- <span data-ttu-id="1ad33-135">As alterações realizadas à sua infraestrutura de roteamento para que o tráfego direcionado ao espaço de endereço da rede virtual do Azure seja encaminhado para o dispositivo VPN que hospeda a conexão VPN site a site.</span><span class="sxs-lookup"><span data-stu-id="1ad33-135">Changes to your routing infrastructure so that traffic routed to the address space of the Azure virtual network gets forwarded to the VPN device that hosts the site-to-site VPN connection.</span></span>
    
- <span data-ttu-id="1ad33-136">Um proxy da Web que dê aos computadores conectados à rede local e à rede virtual do Azure acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="1ad33-136">A web proxy that gives computers that are connected to the on-premises network and the Azure virtual network access to the Internet.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="1ad33-137">Suposições de design de arquitetura da solução</span><span class="sxs-lookup"><span data-stu-id="1ad33-137">Solution architecture design assumptions</span></span>

<span data-ttu-id="1ad33-138">A lista a seguir representa as opções de design que foram feitas para a arquitetura dessa solução.</span><span class="sxs-lookup"><span data-stu-id="1ad33-138">The following list represents the design choices that have been made for this solution architecture.</span></span> 
  
- <span data-ttu-id="1ad33-p109">Essa solução usa uma única rede virtual do Azure com uma conexão VPN de site a site. A rede virtual do Azure hospeda uma única sub-rede que pode conter várias máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p109">This solution uses a single Azure virtual network with a site-to-site VPN connection. The Azure virtual network hosts a single subnet that can contain multiple virtual machines.</span></span> 
    
- <span data-ttu-id="1ad33-p110">Você pode usar o RRAS (Serviço de Roteamento e Acesso Remoto) no Windows Server 2016 ou Windows Server 2012 para estabelecer uma conexão VPN IPsec de site a site entre a rede local e a rede virtual do Azure. Você também pode usar outras opções, como dispositivos VPN Cisco ou Juniper Networks.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p110">You can use the Routing and Remote Access Service (RRAS) in Windows Server 2016 or Windows Server 2012 to establish an IPsec site-to-site VPN connection between the on-premises network and the Azure virtual network. You can also use other options, such as Cisco or Juniper Networks VPN devices.</span></span>
    
- <span data-ttu-id="1ad33-p111">A rede local pode ainda ter serviços de rede como o AD (Active Directory) do Windows Server, o DNS (Sistema de Nomes de Domínio) e servidores proxy. Dependendo dos requisitos, pode ser vantajoso colocar alguns desses recursos de rede na rede virtual no Azure.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p111">The on-premises network might still have network services like Active Directory Domain Services (AD DS), Domain Name System (DNS), and proxy servers. Depending on your requirements, it might be beneficial to place some of these network resources in the Azure virtual network.</span></span>
    
<span data-ttu-id="1ad33-p112">Para uma rede virtual do Azure existente com uma ou mais sub-redes, determine se há um espaço de endereço remanescente para uma sub-rede adicional a fim de hospedar as máquinas virtual necessárias, com base em seus requisitos. Se você não tem um espaço de endereço remanescente para uma sub-rede adicional, crie outra rede virtual que tenha sua própria conexão VPN site a site.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p112">For an existing Azure virtual network with one or more subnets, determine whether there is remaining address space for an additional subnet to host your needed virtual machines, based on your requirements. If you don't have remaining address space for an additional subnet, create an additional virtual network that has its own site-to-site VPN connection.</span></span>
  
### <a name="plan-the-routing-infrastructure-changes-for-the-azure-virtual-network"></a><span data-ttu-id="1ad33-147">Planejar as alterações da infraestrutura de roteamento para a rede virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="1ad33-147">Plan the routing infrastructure changes for the Azure virtual network</span></span>

<span data-ttu-id="1ad33-148">Você deve configurar sua infraestrutura de roteamento local para encaminhar o tráfego destinado ao espaço de endereço da rede virtual do Azure no dispositivo VPN local que hospeda a conexão VPN site a site.</span><span class="sxs-lookup"><span data-stu-id="1ad33-148">You must configure your on-premises routing infrastructure to forward traffic destined for the address space of the Azure virtual network to the on-premises VPN device that is hosting the site-to-site VPN connection.</span></span>
  
<span data-ttu-id="1ad33-149">O método exato de atualização da infraestrutura de roteamento depende de como você gerencia suas informações de roteamento, que pode ser:</span><span class="sxs-lookup"><span data-stu-id="1ad33-149">The exact method of updating your routing infrastructure depends on how you manage routing information, which can be:</span></span>
  
- <span data-ttu-id="1ad33-150">Atualizações da tabela de roteamento com base em configuração manual.</span><span class="sxs-lookup"><span data-stu-id="1ad33-150">Routing table updates based on manual configuration.</span></span>
    
- <span data-ttu-id="1ad33-151">Atualizações da tabela de roteamento com base em protocolos de roteamento, como protocolo RIP (Routing Information Protocol) ou protocolo OSPF (Open Shortest Path First).</span><span class="sxs-lookup"><span data-stu-id="1ad33-151">Routing table updates based on routing protocols, such as Routing Information Protocol (RIP) or Open Shortest Path First (OSPF).</span></span>
    
<span data-ttu-id="1ad33-152">Consulte seu especialista em roteamento para garantir que o tráfego destinado à rede virtual do Azure seja encaminhado ao dispositivo VPN local.</span><span class="sxs-lookup"><span data-stu-id="1ad33-152">Consult with your routing specialist to make sure that traffic destined for the Azure virtual network is forwarded to the on-premises VPN device.</span></span>
  
### <a name="plan-for-firewall-rules-for-traffic-to-and-from-the-on-premises-vpn-device"></a><span data-ttu-id="1ad33-153">Planejar regras de firewall para tráfego que entra e sai do dispositivo VPN local</span><span class="sxs-lookup"><span data-stu-id="1ad33-153">Plan for firewall rules for traffic to and from the on-premises VPN device</span></span>

<span data-ttu-id="1ad33-154">Se seu dispositivo VPN está em uma rede de perímetro que tem um firewall entre a rede de perímetro e a Internet, pode ser necessário configurar o firewall com as seguintes regras para possibilitar a conexão VPN de site a site.</span><span class="sxs-lookup"><span data-stu-id="1ad33-154">If your VPN device is on a perimeter network that has a firewall between the perimeter network and the Internet, you might have to configure the firewall for the following rules to allow the site-to-site VPN connection.</span></span>
  
- <span data-ttu-id="1ad33-155">Tráfego para o dispositivo VPN (vindo da Internet):</span><span class="sxs-lookup"><span data-stu-id="1ad33-155">Traffic to the VPN device (incoming from the Internet):</span></span>
    
  - <span data-ttu-id="1ad33-156">Endereço IP de destino do dispositivo VPN e protocolo IP 50</span><span class="sxs-lookup"><span data-stu-id="1ad33-156">Destination IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="1ad33-157">Endereço IP de destino do dispositivo VPN e porta de destino UDP 500</span><span class="sxs-lookup"><span data-stu-id="1ad33-157">Destination IP address of the VPN device and UDP destination port 500</span></span>
    
  - <span data-ttu-id="1ad33-158">Endereço IP de destino do dispositivo VPN e porta de destino UDP 4500</span><span class="sxs-lookup"><span data-stu-id="1ad33-158">Destination IP address of the VPN device and UDP destination port 4500</span></span>
    
- <span data-ttu-id="1ad33-159">Tráfego do dispositivo VPN (indo para a Internet):</span><span class="sxs-lookup"><span data-stu-id="1ad33-159">Traffic from the VPN device (outgoing to the Internet):</span></span>
    
  - <span data-ttu-id="1ad33-160">Endereço IP de origem do dispositivo VPN e protocolo IP 50</span><span class="sxs-lookup"><span data-stu-id="1ad33-160">Source IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="1ad33-161">Endereço IP de origem do dispositivo VPN e porta de origem UDP 500</span><span class="sxs-lookup"><span data-stu-id="1ad33-161">Source IP address of the VPN device and UDP source port 500</span></span>
    
  - <span data-ttu-id="1ad33-162">Endereço IP de origem do dispositivo VPN e porta de origem UDP 4500</span><span class="sxs-lookup"><span data-stu-id="1ad33-162">Source IP address of the VPN device and UDP source port 4500</span></span>
    
### <a name="plan-for-the-private-ip-address-space-of-the-azure-virtual-network"></a><span data-ttu-id="1ad33-163">Planejar para um espaço de endereço IP privado da rede virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="1ad33-163">Plan for the private IP address space of the Azure virtual network</span></span>

<span data-ttu-id="1ad33-164">O espaço de endereço IP privado da rede virtual do Azure deve pode acomodar endereços usados pelo Azure para hospedar a rede virtual e ao menos uma sub-rede que tenha endereços suficientes para suas máquinas virtuais do Azure.</span><span class="sxs-lookup"><span data-stu-id="1ad33-164">The private IP address space of the Azure virtual network must be able to accommodate addresses used by Azure to host the virtual network and with at least one subnet that has enough addresses for your Azure virtual machines.</span></span>
  
<span data-ttu-id="1ad33-165">Para determinar a quantidade de endereços necessários para a sub-rede, conte o número de máquinas virtuais necessárias agora, estime o crescimento futuro e use a tabela a seguir para determinar o tamanho da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="1ad33-165">To determine the number of addresses needed for the subnet, count the number of virtual machines that you need now, estimate for future growth, and then use the following table to determine the size of the subnet.</span></span>
  
|<span data-ttu-id="1ad33-166">**Número de máquinas virtuais necessárias**</span><span class="sxs-lookup"><span data-stu-id="1ad33-166">**Number of virtual machines needed**</span></span>|<span data-ttu-id="1ad33-167">**Número de bits de host necessário**</span><span class="sxs-lookup"><span data-stu-id="1ad33-167">**Number of host bits needed**</span></span>|<span data-ttu-id="1ad33-168">**Tamanho da sub-rede**</span><span class="sxs-lookup"><span data-stu-id="1ad33-168">**Size of the subnet**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ad33-169">1 a 3</span><span class="sxs-lookup"><span data-stu-id="1ad33-169">1-3</span></span>  <br/> |<span data-ttu-id="1ad33-170">3</span><span class="sxs-lookup"><span data-stu-id="1ad33-170">3</span></span>  <br/> |<span data-ttu-id="1ad33-171">/29</span><span class="sxs-lookup"><span data-stu-id="1ad33-171">/29</span></span>  <br/> |
|<span data-ttu-id="1ad33-172">4 a 11</span><span class="sxs-lookup"><span data-stu-id="1ad33-172">4-11</span></span>  <br/> |<span data-ttu-id="1ad33-173">4 </span><span class="sxs-lookup"><span data-stu-id="1ad33-173">4</span></span>  <br/> |<span data-ttu-id="1ad33-174">/28</span><span class="sxs-lookup"><span data-stu-id="1ad33-174">/28</span></span>  <br/> |
|<span data-ttu-id="1ad33-175">12 a 27</span><span class="sxs-lookup"><span data-stu-id="1ad33-175">12-27</span></span>  <br/> |<span data-ttu-id="1ad33-176">5 </span><span class="sxs-lookup"><span data-stu-id="1ad33-176">5</span></span>  <br/> |<span data-ttu-id="1ad33-177">/27</span><span class="sxs-lookup"><span data-stu-id="1ad33-177">/27</span></span>  <br/> |
|<span data-ttu-id="1ad33-178">28 a 59</span><span class="sxs-lookup"><span data-stu-id="1ad33-178">28-59</span></span>  <br/> |<span data-ttu-id="1ad33-179">6 </span><span class="sxs-lookup"><span data-stu-id="1ad33-179">6</span></span>  <br/> |<span data-ttu-id="1ad33-180">/26</span><span class="sxs-lookup"><span data-stu-id="1ad33-180">/26</span></span>  <br/> |
|<span data-ttu-id="1ad33-181">60 a 123</span><span class="sxs-lookup"><span data-stu-id="1ad33-181">60-123</span></span>  <br/> |<span data-ttu-id="1ad33-182">7 </span><span class="sxs-lookup"><span data-stu-id="1ad33-182">7</span></span>  <br/> |<span data-ttu-id="1ad33-183">/25</span><span class="sxs-lookup"><span data-stu-id="1ad33-183">/25</span></span>  <br/> |
   
### <a name="planning-worksheet-for-configuring-your-azure-virtual-network"></a><span data-ttu-id="1ad33-184">Planilha de planejamento para configurar sua rede virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="1ad33-184">Planning worksheet for configuring your Azure virtual network</span></span>
<span data-ttu-id="1ad33-185"><a name="worksheet"> </a></span><span class="sxs-lookup"><span data-stu-id="1ad33-185"><a name="worksheet"> </a></span></span>

<span data-ttu-id="1ad33-186">Antes de criar uma rede virtual do Azure para hospedar máquinas virtuais, você deve determinar as configurações necessárias nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="1ad33-186">Before you create an Azure virtual network to host virtual machines, you must determine the settings needed in the following tables.</span></span>
  
<span data-ttu-id="1ad33-187">Para as configurações da rede virtual, preencha a Tabela V.</span><span class="sxs-lookup"><span data-stu-id="1ad33-187">For the settings of the virtual network, fill in Table V.</span></span>
  
 <span data-ttu-id="1ad33-188">**Tabela V: Configuração de rede virtual entre locais**</span><span class="sxs-lookup"><span data-stu-id="1ad33-188">**Table V: Cross-premises virtual network configuration**</span></span>
  
|<span data-ttu-id="1ad33-189">**Item**</span><span class="sxs-lookup"><span data-stu-id="1ad33-189">**Item**</span></span>|<span data-ttu-id="1ad33-190">**Elemento Configuration**</span><span class="sxs-lookup"><span data-stu-id="1ad33-190">**Configuration element**</span></span>|<span data-ttu-id="1ad33-191">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1ad33-191">**Description**</span></span>|<span data-ttu-id="1ad33-192">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1ad33-192">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ad33-193">1.</span><span class="sxs-lookup"><span data-stu-id="1ad33-193">1.</span></span>  <br/> |<span data-ttu-id="1ad33-194">Nome da rede virtual</span><span class="sxs-lookup"><span data-stu-id="1ad33-194">Virtual network name</span></span>  <br/> |<span data-ttu-id="1ad33-195">Um nome a atribuir à rede virtual do Azure (por exemplo, DirSyncNet).</span><span class="sxs-lookup"><span data-stu-id="1ad33-195">A name to assign to the Azure virtual network (example DirSyncNet).</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png) |
|<span data-ttu-id="1ad33-197">2.</span><span class="sxs-lookup"><span data-stu-id="1ad33-197">2.</span></span>  <br/> |<span data-ttu-id="1ad33-198">Local da rede virtual</span><span class="sxs-lookup"><span data-stu-id="1ad33-198">Virtual network location</span></span>  <br/> |<span data-ttu-id="1ad33-199">O datacenter do Azure que conterá a rede virtual (como Oeste dos EUA).</span><span class="sxs-lookup"><span data-stu-id="1ad33-199">The Azure datacenter that will contain the virtual network (such as West US).</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="1ad33-201">3.</span><span class="sxs-lookup"><span data-stu-id="1ad33-201">3.</span></span>  <br/> |<span data-ttu-id="1ad33-202">Endereço IP do dispositivo VPN</span><span class="sxs-lookup"><span data-stu-id="1ad33-202">VPN device IP address</span></span>  <br/> |<span data-ttu-id="1ad33-p113">O endereço IPv4 público da interface de seu dispositivo VPN na Internet. Trabalhe com seu departamento de TI para determinar este endereço.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p113">The public IPv4 address of your VPN device's interface on the Internet. Work with your IT department to determine this address.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="1ad33-206">4.</span><span class="sxs-lookup"><span data-stu-id="1ad33-206">4.</span></span>  <br/> |<span data-ttu-id="1ad33-207">Espaço de endereço da rede virtual</span><span class="sxs-lookup"><span data-stu-id="1ad33-207">Virtual network address space</span></span>  <br/> |<span data-ttu-id="1ad33-p114">O espaço de endereço (definido em um único prefixo de endereço privado) para a rede virtual. Trabalhe com seu departamento de TI para determinar este espaço de endereço. O espaço de endereço deve estar no formato Roteamento entre Domínios sem Classificação (CIDR), também conhecido como formato de prefixo de rede. 10.24.64.0/20 é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p114">The address space (defined in a single private address prefix) for the virtual network. Work with your IT department to determine this address space. The address space should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format. An example is 10.24.64.0/20.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png) <br/> |
|<span data-ttu-id="1ad33-213">5.</span><span class="sxs-lookup"><span data-stu-id="1ad33-213">5.</span></span>  <br/> |<span data-ttu-id="1ad33-214">Chave compartilhada IPsec</span><span class="sxs-lookup"><span data-stu-id="1ad33-214">IPsec shared key</span></span>  <br/> |<span data-ttu-id="1ad33-p115">Uma cadeia alfanumérica aleatória com 32 caracteres, que será usada para autenticar ambos os lados da conexão VPN site a site. Trabalhe com seu departamento de TI ou de segurança para determinar este valor de chave e armazená-lo em um local seguro. Como alternativa, confira [Criar uma cadeia de caracteres aleatória para uma chave pré-compartilhada IPsec](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ad33-p115">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection. Work with your IT or security department to determine this key value and then store it in a secure location. Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span></span><br/> |![linha](../media/Common-Images/TableLine.png) <br/> |
   
<span data-ttu-id="1ad33-219">Preencha a Tabela S para as sub-redes desta solução.</span><span class="sxs-lookup"><span data-stu-id="1ad33-219">Fill in Table S for the subnets of this solution.</span></span>
  
- <span data-ttu-id="1ad33-p116">Para a primeira sub-rede, determine um espaço de endereço de 28 bits (com um comprimento de prefixo /28) para a sub-rede do gateway do Azure. Confira [Calcular o espaço de endereço da sub-rede do gateway para as redes virtuais do Azure](/archive/blogs/solutions_advisory_board/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks) para instruções sobre como determinar este espaço de endereço.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p116">For the first subnet, determine a 28-bit address space (with a /28 prefix length) for the Azure gateway subnet. See [Calculating the gateway subnet address space for Azure virtual networks](/archive/blogs/solutions_advisory_board/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks) for information about how to determine this address space.</span></span>
    
- <span data-ttu-id="1ad33-222">Para a segunda sub-rede, especifique um nome amigável, um único espaço de endereço IP com base no espaço de endereço da rede virtual e uma finalidade descritiva.</span><span class="sxs-lookup"><span data-stu-id="1ad33-222">For the second subnet, specify a friendly name, a single IP address space based on the virtual network address space, and a descriptive purpose.</span></span>
    
<span data-ttu-id="1ad33-p117">Trabalhe com seu departamento de TI para determinar esses espaços de endereço a partir do espaço de endereço da rede virtual. Ambos os espaços de endereço devem estar no formato CIDR.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p117">Work with your IT department to determine these address spaces from the virtual network address space. Both address spaces should be in CIDR format.</span></span>
  
 <span data-ttu-id="1ad33-225">**Tabela S: Sub-redes na rede virtual**</span><span class="sxs-lookup"><span data-stu-id="1ad33-225">**Table S: Subnets in the virtual network**</span></span>
  
|<span data-ttu-id="1ad33-226">**Item**</span><span class="sxs-lookup"><span data-stu-id="1ad33-226">**Item**</span></span>|<span data-ttu-id="1ad33-227">**Nome da sub-rede**</span><span class="sxs-lookup"><span data-stu-id="1ad33-227">**Subnet name**</span></span>|<span data-ttu-id="1ad33-228">**Espaço de endereço da sub-rede**</span><span class="sxs-lookup"><span data-stu-id="1ad33-228">**Subnet address space**</span></span>|<span data-ttu-id="1ad33-229">**Objetivo**</span><span class="sxs-lookup"><span data-stu-id="1ad33-229">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ad33-230">1.</span><span class="sxs-lookup"><span data-stu-id="1ad33-230">1.</span></span>  <br/> |<span data-ttu-id="1ad33-231">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="1ad33-231">GatewaySubnet</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="1ad33-233">A sub-rede usada pelo gateway do Azure.</span><span class="sxs-lookup"><span data-stu-id="1ad33-233">The subnet used by the Azure gateway.</span></span>  <br/> |
|<span data-ttu-id="1ad33-234">2.</span><span class="sxs-lookup"><span data-stu-id="1ad33-234">2.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="1ad33-p118">Para servidores de DNS locais que você deseja que sejam usados pelas máquinas virtuais da rede virtual, preencha a Tabela D. Dê a cada servidor DNS um nome amigável e um único endereço IP. Esse nome amigável não precisa corresponder ao nome do host ou ao nome do computador do servidor DNS. Observe que duas entradas em branco estão listadas, mas você pode adicionar mais. Trabalhe com seu departamento de TI para determinar esta lista.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p118">For the on-premises DNS servers that you want the virtual machines in the virtual network to use, fill in Table D. Give each DNS server a friendly name and a single IP address. This friendly name does not need to match the host name or computer name of the DNS server. Note that two blank entries are listed, but you can add more. Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="1ad33-242">**Tabela D: servidores DNS locais**</span><span class="sxs-lookup"><span data-stu-id="1ad33-242">**Table D: On-premises DNS servers**</span></span>
  
|<span data-ttu-id="1ad33-243">**Item**</span><span class="sxs-lookup"><span data-stu-id="1ad33-243">**Item**</span></span>|<span data-ttu-id="1ad33-244">**Nome amigável do servidor DNS**</span><span class="sxs-lookup"><span data-stu-id="1ad33-244">**DNS server friendly name**</span></span>|<span data-ttu-id="1ad33-245">**Endereço IP do servidor DNS**</span><span class="sxs-lookup"><span data-stu-id="1ad33-245">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ad33-246">1.</span><span class="sxs-lookup"><span data-stu-id="1ad33-246">1.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="1ad33-249">2.</span><span class="sxs-lookup"><span data-stu-id="1ad33-249">2.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="1ad33-p119">Para direcionar os pacotes da rede virtual do Azure para a rede de sua organização por uma conexão VPN de site a site, é preciso configurar a rede virtual com uma rede local. Essa rede local contém uma lista de espaços de endereço (no formato CIDR) para todos os locais da rede local de sua organização que as máquinas virtuais da rede virtual devem acessar. Essa lista pode conter todos os locais na rede ou em uma sub-rede locais. A lista de espaços de endereço que define sua rede local deve ser exclusiva e não deve coincidir com os espaços de endereço usados para essa rede virtual ou suas outras redes virtuais entre locais.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p119">To route packets from the Azure virtual network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network. This local network has a list of the address spaces (in CIDR format) for all of the locations on your organization's on-premises network that the virtual machines in the virtual network must reach. This can be all of the locations on the on-premises network or a subset. The list of address spaces that define your local network must be unique and must not overlap with the address spaces used for this virtual network or your other cross-premises virtual networks.</span></span>
  
<span data-ttu-id="1ad33-p120">Para o conjunto de espaços de endereço da rede local, preencha a Tabela L. Observe que há três entradas em branco listadas, mas geralmente você precisará de mais. Trabalhe com seu departamento de TI para determinar esta lista.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p120">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more. Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="1ad33-258">**Tabela L: Prefixos de endereço para a rede local**</span><span class="sxs-lookup"><span data-stu-id="1ad33-258">**Table L: Address prefixes for the local network**</span></span>
  
|<span data-ttu-id="1ad33-259">**Item**</span><span class="sxs-lookup"><span data-stu-id="1ad33-259">**Item**</span></span>|<span data-ttu-id="1ad33-260">**Espaço de endereço da rede local**</span><span class="sxs-lookup"><span data-stu-id="1ad33-260">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1ad33-261">1.</span><span class="sxs-lookup"><span data-stu-id="1ad33-261">1.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="1ad33-263">2.</span><span class="sxs-lookup"><span data-stu-id="1ad33-263">2.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="1ad33-265">3.</span><span class="sxs-lookup"><span data-stu-id="1ad33-265">3.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
   
## <a name="deployment-roadmap"></a><span data-ttu-id="1ad33-267">Roteiro de implantação</span><span class="sxs-lookup"><span data-stu-id="1ad33-267">Deployment roadmap</span></span>
<span data-ttu-id="1ad33-268"><a name="DeploymentRoadmap"> </a></span><span class="sxs-lookup"><span data-stu-id="1ad33-268"><a name="DeploymentRoadmap"> </a></span></span>

<span data-ttu-id="1ad33-269">A criação da rede virtual entre locais e a adição de máquinas virtuais no Azure tem três fases:</span><span class="sxs-lookup"><span data-stu-id="1ad33-269">Creating the cross-premises virtual network and adding virtual machines in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="1ad33-270">Fase 1: Preparar sua rede local.</span><span class="sxs-lookup"><span data-stu-id="1ad33-270">Phase 1: Prepare your on-premises network.</span></span>
    
- <span data-ttu-id="1ad33-271">Fase 2: Criar a rede virtual entre locais no Azure.</span><span class="sxs-lookup"><span data-stu-id="1ad33-271">Phase 2: Create the cross-premises virtual network in Azure.</span></span>
    
- <span data-ttu-id="1ad33-272">Fase 3 (Opcional): Adicionar máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="1ad33-272">Phase 3 (Optional): Add virtual machines.</span></span>
    
### <a name="phase-1-prepare-your-on-premises-network"></a><span data-ttu-id="1ad33-273">Fase 1: Preparar sua rede local</span><span class="sxs-lookup"><span data-stu-id="1ad33-273">Phase 1: Prepare your on-premises network</span></span>
<a name="Phase1"></a>

<span data-ttu-id="1ad33-p121">Você deve configurar sua rede local com uma rota que aponte e, por fim, gere tráfego destinado para o espaço de endereço da rede virtual ao roteador na borda da rede local. Confira o administrador da rede para determinar como adicionar a rota à infraestrutura de roteamento da rede local.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p121">You must configure your on-premises network with a route that points to and ultimately delivers traffic destined for the address space of the virtual network to the router on the edge of the on-premises network. Consult with your network administrator to determine how to add the route to the routing infrastructure of your on-premises network.</span></span>
  
<span data-ttu-id="1ad33-276">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="1ad33-276">Here is your resulting configuration.</span></span>
  
![A rede local deve ter uma rota para o espaço de endereço da rede virtual que aponte para o dispositivo VPN.](../media/90bab36b-cb60-4ea5-81d5-4737b696d41c.png)
  
### <a name="phase-2-create-the-cross-premises-virtual-network-in-azure"></a><span data-ttu-id="1ad33-278">Fase 2: criar a rede virtual entre locais no Azure</span><span class="sxs-lookup"><span data-stu-id="1ad33-278">Phase 2: Create the cross-premises virtual network in Azure</span></span>
<a name="Phase2"></a>

<span data-ttu-id="1ad33-p122">Primeiro, abra um prompt do Azure PowerShell. Se o Azure PowerShell ainda não estiver instalado, confira [Introdução ao Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="1ad33-p122">First, open an Azure PowerShell prompt. If you have not installed Azure PowerShell, see [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span>

 
<span data-ttu-id="1ad33-281">Em seguida, entre com sua conta do Azure usando este comando.</span><span class="sxs-lookup"><span data-stu-id="1ad33-281">Next, login to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="1ad33-282">Para obter o nome de sua assinatura, use este comando.</span><span class="sxs-lookup"><span data-stu-id="1ad33-282">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort SubscriptionName | Select SubscriptionName
```

<span data-ttu-id="1ad33-p123">Defina sua assinatura do Azure com esses comandos. Substitua tudo o que está entre aspas, incluindo os caracteres < e >, pelo nome de assinatura correto.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p123">Set your Azure subscription with these commands. Replace everything within the quotes, including the < and > characters, with the correct subscription name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="1ad33-p124">Depois, crie um novo grupo de recursos para sua rede virtual. Para determinar um nome de grupo de recursos exclusivo, use este comando para listar os grupos de recurso existentes.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p124">Next, create a new resource group for your virtual network. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="1ad33-287">Crie o novo grupo de recursos com estes comandos.</span><span class="sxs-lookup"><span data-stu-id="1ad33-287">Create your new resource group with these commands.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<Table V - Item 2 - Value column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="1ad33-288">Em seguida, crie a rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="1ad33-288">Next, you create the Azure virtual network.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V, S, and D
$rgName="<name of your new resource group>"
$locName="<Azure location of your new resource group>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$gwSubnetPrefix="<Table S - Item 1 - Subnet address space column>"
$SubnetName="<Table S - Item 2 - Subnet name column>"
$SubnetPrefix="<Table S - Item 2 - Subnet address space column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the Azure virtual network and a network security group that allows incoming remote desktop connections to the subnet that is hosting virtual machines
$gatewaySubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnetPrefix
$vmSubnet=New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $SubnetPrefix
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gatewaySubnet,$vmSubnet -DNSServer $dnsServers
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName -Location $locShortName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$nsg=Get-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $SubnetName -AddressPrefix $SubnetPrefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="1ad33-289">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="1ad33-289">Here is your resulting configuration.</span></span>
  
![A rede virtual ainda não está conectada à rede local.](../media/54a37782-a6cc-4d48-b38d-73e128b44a82.png)
  
<span data-ttu-id="1ad33-291">Em seguida, use estes comandos para criar os gateways para a conexão VPN site a site.</span><span class="sxs-lookup"><span data-stu-id="1ad33-291">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V and L
$vnetName="<Table V - Item 1 - Value column>"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -SubnetId $vnet.Subnets[0].Id
# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig
# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix
# Create the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway
```

<span data-ttu-id="1ad33-292">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="1ad33-292">Here is your resulting configuration.</span></span>
  
![Agora a rede virtual tem um gateway.](../media/82dd66b2-a4b7-48f6-a89b-cfdd94630980.png)
  
<span data-ttu-id="1ad33-p125">Em seguida, configure seu dispositivo VPN local para se conectar ao gateway de VPN do Azure. Para saber mais, confira [Sobre dispositivos VPN para conexões de rede virtual do Azure de site a site](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span><span class="sxs-lookup"><span data-stu-id="1ad33-p125">Next, configure your on-premises VPN device to connect to the Azure VPN gateway. For more information, see [About VPN Devices for site-to-site Azure Virtual Network connections](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="1ad33-296">Para configurar seu dispositivo VPN, você precisará do seguinte:</span><span class="sxs-lookup"><span data-stu-id="1ad33-296">To configure your VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="1ad33-297">O endereço IPv4 público do gateway VPN do Azure para sua rede virtual.</span><span class="sxs-lookup"><span data-stu-id="1ad33-297">The public IPv4 address of the Azure VPN gateway for your virtual network.</span></span> <span data-ttu-id="1ad33-298">Use o comando **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** para exibir este endereço.</span><span class="sxs-lookup"><span data-stu-id="1ad33-298">Use the **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** command to display this address.</span></span>
    
- <span data-ttu-id="1ad33-299">A chave IPsec pré-compartilhada para a conexão VPN site a site (Tabela V – Item 5 – coluna Valor).</span><span class="sxs-lookup"><span data-stu-id="1ad33-299">The IPsec pre-shared key for the site-to-site VPN connection (Table V- Item 5 - Value column).</span></span>
    
<span data-ttu-id="1ad33-300">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="1ad33-300">Here is your resulting configuration.</span></span>
  
![A rede virtual ainda já está conectada à rede local.](../media/6379c423-4f22-4453-941b-7ff32484a0a5.png)
  
### <a name="phase-3-optional-add-virtual-machines"></a><span data-ttu-id="1ad33-302">Fase 3 (Opcional): Adicionar máquinas virtuais</span><span class="sxs-lookup"><span data-stu-id="1ad33-302">Phase 3 (Optional): Add virtual machines</span></span>

<span data-ttu-id="1ad33-p127">Crie as máquinas virtuais de que você precisa no Azure. Para saber mais, confira [Criar uma máquina virtual do Windows com o portal do Azure](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span><span class="sxs-lookup"><span data-stu-id="1ad33-p127">Create the virtual machines you need in Azure. For more information, see [Create a Windows virtual machine with the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span></span>
  
<span data-ttu-id="1ad33-305">Use as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="1ad33-305">Use the following settings:</span></span>
  
- <span data-ttu-id="1ad33-p128">Na guia **Básico**, selecione a mesma assinatura e grupo de recursos como sua rede virtual. Você precisará dessas informações posteriormente para entrar na máquina virtual. Na seção **Detalhes da instância**, escolha o tamanho apropriado da máquina virtual. Registre o nome de usuário de conta de administrador e a senha em local seguro.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p128">On the **Basics** tab, select the same subscription and resource group as your virtual network. You will need these later to sign in to the virtual machine. In the **Instance details** section, choose the appropriate virtual machine size. Record the administrator account user name and password in a secure location.</span></span> 
    
- <span data-ttu-id="1ad33-p129">Na guia **Rede**, escolha o nome da rede e da sub-rede virtuais para hospedar máquinas virtuais (não a GatewaySubnet). Deixe todas as configurações com os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p129">On the **Networking** tab, select the name of your virtual network and the subnet for hosting virtual machines (not the GatewaySubnet). Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="1ad33-p130">Verifique se a máquina virtual está usando o DNS corretamente (examine o DNS interno) para garantir que os registros de Endereço (A) foram adicionados à sua nova máquina virtual. Para acessar a Internet, suas máquinas virtuais do Azure devem estar configuradas para usar o servidor proxy da sua rede local. Entre em contato com o administrador da rede para etapas de configuração adicionais a executar no servidor.</span><span class="sxs-lookup"><span data-stu-id="1ad33-p130">Verify that your virtual machine is using DNS correctly by checking your internal DNS to ensure that Address (A) records were added for you new virtual machine. To access the Internet, your Azure virtual machines must be configured to use your on-premises network's proxy server. Contact your network administrator for additional configuration steps to perform on the server.</span></span>
  
<span data-ttu-id="1ad33-315">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="1ad33-315">Here is your resulting configuration.</span></span>
  
![Agora a rede virtual hospeda máquinas virtuais que são acessíveis pela rede local.](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
  
## <a name="next-step"></a><span data-ttu-id="1ad33-317">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1ad33-317">Next step</span></span>
  
[<span data-ttu-id="1ad33-318">Implantar Microsoft 365 Sincronização de Diretórios no Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="1ad33-318">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>](deploy-microsoft-365-directory-synchronization-dirsync-in-microsoft-azure.md)