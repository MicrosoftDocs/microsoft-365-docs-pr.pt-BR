---
title: Autenticação federada de alta disponibilidade fase 1 configurar o Azure
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
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: 'Resumo: Configure a infraestrutura do Microsoft Azure para hospedar a autenticação federada de alta disponibilidade para o Microsoft 365.'
ms.openlocfilehash: a99259e8c60346665f76aeba3a8a440e0f9061f0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687432"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a><span data-ttu-id="ab97f-103">Autenticação federada de alta disponibilidade Fase 1: configurar o Azure</span><span class="sxs-lookup"><span data-stu-id="ab97f-103">High availability federated authentication Phase 1: Configure Azure</span></span>

<span data-ttu-id="ab97f-104">Nesta fase, você cria os grupos de recursos, a rede virtual (VNet) e os conjuntos de disponibilidade no Azure que hospedarão as máquinas virtuais nas etapas 2, 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="ab97f-104">In this phase, you create the resource groups, virtual network (VNet), and availability sets in Azure that will host the virtual machines in phases 2, 3, and 4.</span></span> <span data-ttu-id="ab97f-105">Você deve concluir essa fase antes de passar para [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="ab97f-105">You must complete this phase before moving on to [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="ab97f-106">Consulte [implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) para todas as fases.</span><span class="sxs-lookup"><span data-stu-id="ab97f-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
<span data-ttu-id="ab97f-107">O Azure deve ser provisionado com estes componentes básicos:</span><span class="sxs-lookup"><span data-stu-id="ab97f-107">Azure must be provisioned with these basic components:</span></span>
  
- <span data-ttu-id="ab97f-108">Grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="ab97f-108">Resource groups</span></span>
    
- <span data-ttu-id="ab97f-109">Uma rede virtual do Azure (VNet) entre locais com sub-redes para a hospedagem das máquinas virtuais do Azure</span><span class="sxs-lookup"><span data-stu-id="ab97f-109">A cross-premises Azure virtual network (VNet) with subnets for hosting the Azure virtual machines</span></span>
    
- <span data-ttu-id="ab97f-110">Grupos de segurança de rede para a realização do isolamento de sub-redes</span><span class="sxs-lookup"><span data-stu-id="ab97f-110">Network security groups for performing subnet isolation</span></span>
    
- <span data-ttu-id="ab97f-111">Conjuntos de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="ab97f-111">Availability sets</span></span>
    
## <a name="configure-azure-components"></a><span data-ttu-id="ab97f-112">Configurar componentes do Azure</span><span class="sxs-lookup"><span data-stu-id="ab97f-112">Configure Azure components</span></span>

<span data-ttu-id="ab97f-113">Antes de começar a configurar componentes do Azure, preencha as tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="ab97f-113">Before you begin configuring Azure components, fill in the following tables.</span></span> <span data-ttu-id="ab97f-114">Para auxiliar nos procedimentos de configuração do Azure, imprima esta seção e anote as informações necessárias ou copie esta seção em um documento e preencha em seguida.</span><span class="sxs-lookup"><span data-stu-id="ab97f-114">To assist you in the procedures for configuring Azure, print this section and write down the needed information or copy this section to a document and fill it in.</span></span> <span data-ttu-id="ab97f-115">Para as configurações da VNet, preencha a Tabela V.</span><span class="sxs-lookup"><span data-stu-id="ab97f-115">For the settings of the VNet, fill in Table V.</span></span>
  
|<span data-ttu-id="ab97f-116">**Item**</span><span class="sxs-lookup"><span data-stu-id="ab97f-116">**Item**</span></span>|<span data-ttu-id="ab97f-117">**Definição de configuração**</span><span class="sxs-lookup"><span data-stu-id="ab97f-117">**Configuration setting**</span></span>|<span data-ttu-id="ab97f-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ab97f-118">**Description**</span></span>|<span data-ttu-id="ab97f-119">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ab97f-119">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab97f-120">1.</span><span class="sxs-lookup"><span data-stu-id="ab97f-120">1.</span></span>  <br/> |<span data-ttu-id="ab97f-121">Nome da VNet</span><span class="sxs-lookup"><span data-stu-id="ab97f-121">VNet name</span></span>  <br/> |<span data-ttu-id="ab97f-122">Um nome a ser atribuído à VNet (exemplo FedAuthNet).</span><span class="sxs-lookup"><span data-stu-id="ab97f-122">A name to assign to the VNet (example FedAuthNet).</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-124">2.</span><span class="sxs-lookup"><span data-stu-id="ab97f-124">2.</span></span>  <br/> |<span data-ttu-id="ab97f-125">Localização da VNet</span><span class="sxs-lookup"><span data-stu-id="ab97f-125">VNet location</span></span>  <br/> |<span data-ttu-id="ab97f-126">O datacenter do Azure regional que conterá a rede virtual.</span><span class="sxs-lookup"><span data-stu-id="ab97f-126">The regional Azure datacenter that will contain the virtual network.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-128">3.</span><span class="sxs-lookup"><span data-stu-id="ab97f-128">3.</span></span>  <br/> |<span data-ttu-id="ab97f-129">Endereço IP do dispositivo VPN</span><span class="sxs-lookup"><span data-stu-id="ab97f-129">VPN device IP address</span></span>  <br/> |<span data-ttu-id="ab97f-130">O endereço IPv4 público da interface de seu dispositivo VPN na Internet.</span><span class="sxs-lookup"><span data-stu-id="ab97f-130">The public IPv4 address of your VPN device's interface on the Internet.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-132">4.</span><span class="sxs-lookup"><span data-stu-id="ab97f-132">4.</span></span>  <br/> |<span data-ttu-id="ab97f-133">Espaço de endereço da VNet</span><span class="sxs-lookup"><span data-stu-id="ab97f-133">VNet address space</span></span>  <br/> |<span data-ttu-id="ab97f-p103">O espaço de endereço da rede virtual. Trabalhe com seu departamento de TI para determinar esse espaço de endereço.</span><span class="sxs-lookup"><span data-stu-id="ab97f-p103">The address space for the virtual network. Work with your IT department to determine this address space.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-137">5.</span><span class="sxs-lookup"><span data-stu-id="ab97f-137">5.</span></span>  <br/> |<span data-ttu-id="ab97f-138">Chave compartilhada IPsec</span><span class="sxs-lookup"><span data-stu-id="ab97f-138">IPsec shared key</span></span>  <br/> |<span data-ttu-id="ab97f-p104">Uma cadeia alfanumérica aleatória com 32 caracteres, que será usada para autenticar ambos os lados da conexão VPN site a site. Trabalhe com seu departamento de TI ou de segurança para determinar esse valor de chave. Como alternativa, confira [Criar uma cadeia de caracteres aleatória para uma chave pré-compartilhada IPsec](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span><span class="sxs-lookup"><span data-stu-id="ab97f-p104">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection. Work with your IT or security department to determine this key value. Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span></span><br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="ab97f-143">**Tabela V: Configuração de rede virtual entre locais**</span><span class="sxs-lookup"><span data-stu-id="ab97f-143">**Table V: Cross-premises virtual network configuration**</span></span>
  
<span data-ttu-id="ab97f-p105">Em seguida, preencha a Tabela S para as sub-redes desta solução. Todos os espaços de endereço devem estar no formato de Roteamento entre Domínios sem Classificação (CIDR), também conhecido como formato de prefixo de rede. Um exemplo é 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="ab97f-p105">Next, fill in Table S for the subnets of this solution. All address spaces should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format. An example is 10.24.64.0/20.</span></span>
  
<span data-ttu-id="ab97f-p106">Para as três primeiras sub-redes, especifique um nome e um único espaço de endereços IP com base no espaço de endereço da rede virtual. Para a sub-rede de gateway, determine um espaço de endereço de 27 bits (com um comprimento de prefixo /27) para a sub-rede do gateway do Azure. Use o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ab97f-p106">For the first three subnets, specify a name and a single IP address space based on the virtual network address space. For the gateway subnet, determine the 27-bit address space (with a /27 prefix length) for the Azure gateway subnet with the following:</span></span>
  
1. <span data-ttu-id="ab97f-149">Defina os bits variáveis no espaço de endereço da VNet como 1, até os bits que estão sendo usados pela sub-rede do gateway, e depois defina os bits restantes como 0.</span><span class="sxs-lookup"><span data-stu-id="ab97f-149">Set the variable bits in the address space of the VNet to 1, up to the bits being used by the gateway subnet, then set the remaining bits to 0.</span></span>
    
2. <span data-ttu-id="ab97f-150">Converta os bits resultantes em decimais e expresse-os como um espaço de endereço com o comprimento de prefixo definido como o tamanho da sub-rede do gateway.</span><span class="sxs-lookup"><span data-stu-id="ab97f-150">Convert the resulting bits to decimal and express it as an address space with the prefix length set to the size of the gateway subnet.</span></span>
    
<span data-ttu-id="ab97f-151">Consulte a [calculadora de espaço de endereçamento para sub-redes de gateway do Azure](https://gallery.technet.microsoft.com/scriptcenter/Address-prefix-calculator-a94b6eed) para um bloco de comando do PowerShell e um aplicativo de console C# ou Python que realiza esse cálculo para você.</span><span class="sxs-lookup"><span data-stu-id="ab97f-151">See [Address space calculator for Azure gateway subnets](https://gallery.technet.microsoft.com/scriptcenter/Address-prefix-calculator-a94b6eed) for a PowerShell command block and C# or Python console application that performs this calculation for you.</span></span>
  
<span data-ttu-id="ab97f-152">Trabalhe com seu departamento de TI para determinar esses espaços de endereço a partir do espaço de endereço da rede virtual.</span><span class="sxs-lookup"><span data-stu-id="ab97f-152">Work with your IT department to determine these address spaces from the virtual network address space.</span></span>
  
|<span data-ttu-id="ab97f-153">**Item**</span><span class="sxs-lookup"><span data-stu-id="ab97f-153">**Item**</span></span>|<span data-ttu-id="ab97f-154">**Nome da sub-rede**</span><span class="sxs-lookup"><span data-stu-id="ab97f-154">**Subnet name**</span></span>|<span data-ttu-id="ab97f-155">**Espaço de endereço da sub-rede**</span><span class="sxs-lookup"><span data-stu-id="ab97f-155">**Subnet address space**</span></span>|<span data-ttu-id="ab97f-156">**Objetivo**</span><span class="sxs-lookup"><span data-stu-id="ab97f-156">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab97f-157">1.</span><span class="sxs-lookup"><span data-stu-id="ab97f-157">1.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="ab97f-160">A sub-rede usada pelo controlador de domínio dos serviços de domínio do Active Directory (AD DS) e máquinas virtuais (VMs) do servidor de sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="ab97f-160">The subnet used by the Active Directory Domain Services (AD DS) domain controller and directory synchronization server virtual machines (VMs).</span></span>  <br/> |
|<span data-ttu-id="ab97f-161">2.</span><span class="sxs-lookup"><span data-stu-id="ab97f-161">2.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="ab97f-164">A sub-rede usada pelos VMs do AD FS.</span><span class="sxs-lookup"><span data-stu-id="ab97f-164">The subnet used by the AD FS VMs.</span></span>  <br/> |
|<span data-ttu-id="ab97f-165">3.</span><span class="sxs-lookup"><span data-stu-id="ab97f-165">3.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="ab97f-168">A sub-rede usada pelas VMs de proxy do aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="ab97f-168">The subnet used by the web application proxy VMs.</span></span>  <br/> |
|<span data-ttu-id="ab97f-169">4.</span><span class="sxs-lookup"><span data-stu-id="ab97f-169">4.</span></span>  <br/> |<span data-ttu-id="ab97f-170">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="ab97f-170">GatewaySubnet</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="ab97f-172">A sub-rede usada pelas VMs do gateway do Azure.</span><span class="sxs-lookup"><span data-stu-id="ab97f-172">The subnet used by the Azure gateway VMs.</span></span>  <br/> |
   
 <span data-ttu-id="ab97f-173">**Tabela S: Sub-redes na rede virtual**</span><span class="sxs-lookup"><span data-stu-id="ab97f-173">**Table S: Subnets in the virtual network**</span></span>
  
<span data-ttu-id="ab97f-174">Em seguida, preencha a Tabela I para os endereços IP estáticos atribuídos a máquinas virtuais e instâncias de balanceador de carga.</span><span class="sxs-lookup"><span data-stu-id="ab97f-174">Next, fill in Table I for the static IP addresses assigned to virtual machines and load balancer instances.</span></span>
  
|<span data-ttu-id="ab97f-175">**Item**</span><span class="sxs-lookup"><span data-stu-id="ab97f-175">**Item**</span></span>|<span data-ttu-id="ab97f-176">**Finalidade**</span><span class="sxs-lookup"><span data-stu-id="ab97f-176">**Purpose**</span></span>|<span data-ttu-id="ab97f-177">**Endereço IP na sub-rede**</span><span class="sxs-lookup"><span data-stu-id="ab97f-177">**IP address on the subnet**</span></span>|<span data-ttu-id="ab97f-178">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ab97f-178">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab97f-179">1.</span><span class="sxs-lookup"><span data-stu-id="ab97f-179">1.</span></span>  <br/> |<span data-ttu-id="ab97f-180">Endereço IP estático do primeiro controlador de domínio</span><span class="sxs-lookup"><span data-stu-id="ab97f-180">Static IP address of the first domain controller</span></span>  <br/> |<span data-ttu-id="ab97f-181">O quarto endereço IP possível para o espaço de endereço da sub-rede definido no Item 1 da Tabela S.</span><span class="sxs-lookup"><span data-stu-id="ab97f-181">The fourth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-183">2.</span><span class="sxs-lookup"><span data-stu-id="ab97f-183">2.</span></span>  <br/> |<span data-ttu-id="ab97f-184">Endereço IP estático do segundo controlador de domínio</span><span class="sxs-lookup"><span data-stu-id="ab97f-184">Static IP address of the second domain controller</span></span>  <br/> |<span data-ttu-id="ab97f-185">O quinto endereço IP possível para o espaço de endereço da sub-rede definido no Item 1 da Tabela S.</span><span class="sxs-lookup"><span data-stu-id="ab97f-185">The fifth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-187">3.</span><span class="sxs-lookup"><span data-stu-id="ab97f-187">3.</span></span>  <br/> |<span data-ttu-id="ab97f-188">Endereço IP estático do servidor de sincronização de diretório</span><span class="sxs-lookup"><span data-stu-id="ab97f-188">Static IP address of the directory synchronization server</span></span>  <br/> |<span data-ttu-id="ab97f-189">O sexto endereço IP possível para o espaço de endereço da sub-rede definido no Item 1 da Tabela S. </span><span class="sxs-lookup"><span data-stu-id="ab97f-189">The sixth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-191">4.</span><span class="sxs-lookup"><span data-stu-id="ab97f-191">4.</span></span>  <br/> |<span data-ttu-id="ab97f-192">Endereço IP estático do balanceador de carga internos para os servidores do AD FS</span><span class="sxs-lookup"><span data-stu-id="ab97f-192">Static IP address of the internal load balancer for the AD FS servers</span></span>  <br/> |<span data-ttu-id="ab97f-193">O quarto endereço IP possível para o espaço de endereço da sub-rede definido no Item 2 da Tabela S.</span><span class="sxs-lookup"><span data-stu-id="ab97f-193">The fourth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-195">5.</span><span class="sxs-lookup"><span data-stu-id="ab97f-195">5.</span></span>  <br/> |<span data-ttu-id="ab97f-196">Endereço IP estático do primeiro servidor do AD FS</span><span class="sxs-lookup"><span data-stu-id="ab97f-196">Static IP address of the first AD FS server</span></span>  <br/> |<span data-ttu-id="ab97f-197">O quinto endereço IP possível para o espaço de endereço da sub-rede definido no Item 2 da Tabela S.</span><span class="sxs-lookup"><span data-stu-id="ab97f-197">The fifth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-199">6.</span><span class="sxs-lookup"><span data-stu-id="ab97f-199">6.</span></span>  <br/> |<span data-ttu-id="ab97f-200">Endereço IP estático do segundo servidor do AD FS</span><span class="sxs-lookup"><span data-stu-id="ab97f-200">Static IP address of the second AD FS server</span></span>  <br/> |<span data-ttu-id="ab97f-201">O sexto endereço IP possível para o espaço de endereço da sub-rede definido no Item 2 da Tabela S.</span><span class="sxs-lookup"><span data-stu-id="ab97f-201">The sixth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-203">7.</span><span class="sxs-lookup"><span data-stu-id="ab97f-203">7.</span></span>  <br/> |<span data-ttu-id="ab97f-204">Endereço IP estático do primeiro servidor proxy de aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="ab97f-204">Static IP address of the first web application proxy server</span></span>  <br/> |<span data-ttu-id="ab97f-205">O quarto endereço IP possível para o espaço de endereço da sub-rede definido no Item 3 da Tabela S.</span><span class="sxs-lookup"><span data-stu-id="ab97f-205">The fourth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-207">8.</span><span class="sxs-lookup"><span data-stu-id="ab97f-207">8.</span></span>  <br/> |<span data-ttu-id="ab97f-208">Endereço IP estático do segundo servidor proxy de aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="ab97f-208">Static IP address of the second web application proxy server</span></span>  <br/> |<span data-ttu-id="ab97f-209">O quinto endereço IP possível para o espaço de endereço da sub-rede definido no Item 3 da Tabela S.</span><span class="sxs-lookup"><span data-stu-id="ab97f-209">The fifth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="ab97f-211">**Tabela I: Endereços IP estáticos na rede virtual**</span><span class="sxs-lookup"><span data-stu-id="ab97f-211">**Table I: Static IP addresses in the virtual network**</span></span>
  
<span data-ttu-id="ab97f-212">Para dois servidores de Sistema de Nomes de Domínio (DNS) na sua rede local que você deseja usar ao configurar controladores de domínio inicialmente na sua rede virtual, preencha a Tabela D. Trabalhe com o departamento de TI para determinar essa lista.</span><span class="sxs-lookup"><span data-stu-id="ab97f-212">For two Domain Name System (DNS) servers in your on-premises network that you want to use when initially setting up the domain controllers in your virtual network, fill in Table D. Work with your IT department to determine this list.</span></span>
  
|<span data-ttu-id="ab97f-213">**Item**</span><span class="sxs-lookup"><span data-stu-id="ab97f-213">**Item**</span></span>|<span data-ttu-id="ab97f-214">**Nome amigável do servidor DNS**</span><span class="sxs-lookup"><span data-stu-id="ab97f-214">**DNS server friendly name**</span></span>|<span data-ttu-id="ab97f-215">**Endereço IP do servidor DNS**</span><span class="sxs-lookup"><span data-stu-id="ab97f-215">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ab97f-216">1.</span><span class="sxs-lookup"><span data-stu-id="ab97f-216">1.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-219">2.</span><span class="sxs-lookup"><span data-stu-id="ab97f-219">2.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="ab97f-222">**Tabela D: servidores DNS locais**</span><span class="sxs-lookup"><span data-stu-id="ab97f-222">**Table D: On-premises DNS servers**</span></span>
  
<span data-ttu-id="ab97f-223">Para rotear pacotes da rede entre locais para a sua rede de organização através da conexão VPN site a site, você deve configurar a rede virtual com uma rede local que tenha uma lista dos espaços de endereço (em notação CIDR) para todos os locais acessíveis na rede local da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ab97f-223">To route packets from the cross-premises network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network that has a list of the address spaces (in CIDR notation) for all of the reachable locations on your organization's on-premises network.</span></span> <span data-ttu-id="ab97f-224">A lista de espaços de endereço que definem a sua rede local deve ser exclusiva e não deve ser ficar sobreposta ao espaço de endereço usado para outras redes virtuais ou locais.</span><span class="sxs-lookup"><span data-stu-id="ab97f-224">The list of address spaces that define your local network must be unique and must not overlap with the address space used for other virtual networks or other local networks.</span></span>
  
<span data-ttu-id="ab97f-p108">Para o conjunto de espaços de endereço da rede local, preencha a Tabela L. Observe que há três entradas em branco listadas, mas geralmente você precisará de mais. Trabalhe com seu departamento de TI para determinar esta lista de espaços de endereço.</span><span class="sxs-lookup"><span data-stu-id="ab97f-p108">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more. Work with your IT department to determine this list of address spaces.</span></span>
  
|<span data-ttu-id="ab97f-227">**Item**</span><span class="sxs-lookup"><span data-stu-id="ab97f-227">**Item**</span></span>|<span data-ttu-id="ab97f-228">**Espaço de endereço da rede local**</span><span class="sxs-lookup"><span data-stu-id="ab97f-228">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ab97f-229">1.</span><span class="sxs-lookup"><span data-stu-id="ab97f-229">1.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-231">2.</span><span class="sxs-lookup"><span data-stu-id="ab97f-231">2.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-233">3.</span><span class="sxs-lookup"><span data-stu-id="ab97f-233">3.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="ab97f-235">**Tabela L: Prefixos de endereço para a rede local**</span><span class="sxs-lookup"><span data-stu-id="ab97f-235">**Table L: Address prefixes for the local network**</span></span>
  
<span data-ttu-id="ab97f-236">Agora, vamos começar a criar a infraestrutura do Azure para hospedar sua autenticação federada para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab97f-236">Now let's begin building the Azure infrastructure to host your federated authentication for Microsoft 365.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab97f-237">[!OBSERVAçãO] O comando a seguir define o uso da versão mais recente do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab97f-237">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="ab97f-238">Confira [introdução ao PowerShell do Azure](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="ab97f-238">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="ab97f-239">Primeiro, inicie um prompt do Azure PowerShell e faça logon na sua conta.</span><span class="sxs-lookup"><span data-stu-id="ab97f-239">First, start an Azure PowerShell prompt and login to your account.</span></span>
  
```powershell
Connect-AzAccount
```

> [!TIP]
> <span data-ttu-id="ab97f-240">Para gerar blocos de comando prontos para executar do PowerShell com base em suas configurações personalizadas, use esta [pasta de trabalho de configuração do Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="ab97f-240">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

<span data-ttu-id="ab97f-241">Para obter o nome de sua assinatura, use este comando.</span><span class="sxs-lookup"><span data-stu-id="ab97f-241">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="ab97f-242">Para versões mais antigas do Azure PowerShell, use esse comando em vez disso.</span><span class="sxs-lookup"><span data-stu-id="ab97f-242">For older versions of Azure PowerShell, use this command instead.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

<span data-ttu-id="ab97f-243">Defina sua assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="ab97f-243">Set your Azure subscription.</span></span> <span data-ttu-id="ab97f-244">Substitua tudo dentro das aspas, incluindo os \< and > caracteres, pelo nome correto.</span><span class="sxs-lookup"><span data-stu-id="ab97f-244">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="ab97f-p111">Em seguida, crie os novos grupos de recursos. Para determinar um conjunto exclusivo de nomes de grupo de recursos, use este comando para listar os grupos de recurso existentes.</span><span class="sxs-lookup"><span data-stu-id="ab97f-p111">Next, create the new resource groups. To determine a unique set of resource group names, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="ab97f-247">Preencha a tabela a seguir para o conjunto de nomes de grupos de recursos exclusivos.</span><span class="sxs-lookup"><span data-stu-id="ab97f-247">Fill in the following table for the set of unique resource group names.</span></span>
  
|<span data-ttu-id="ab97f-248">**Item**</span><span class="sxs-lookup"><span data-stu-id="ab97f-248">**Item**</span></span>|<span data-ttu-id="ab97f-249">**Nome do grupo de recursos**</span><span class="sxs-lookup"><span data-stu-id="ab97f-249">**Resource group name**</span></span>|<span data-ttu-id="ab97f-250">**Objetivo**</span><span class="sxs-lookup"><span data-stu-id="ab97f-250">**Purpose**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ab97f-251">1.</span><span class="sxs-lookup"><span data-stu-id="ab97f-251">1.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="ab97f-253">Controladores de domínio:</span><span class="sxs-lookup"><span data-stu-id="ab97f-253">Domain controllers</span></span>  <br/> |
|<span data-ttu-id="ab97f-254">2.</span><span class="sxs-lookup"><span data-stu-id="ab97f-254">2.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="ab97f-256">Servidores do AD FS</span><span class="sxs-lookup"><span data-stu-id="ab97f-256">AD FS servers</span></span>  <br/> |
|<span data-ttu-id="ab97f-257">3.</span><span class="sxs-lookup"><span data-stu-id="ab97f-257">3.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="ab97f-259">Servidores proxy de aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="ab97f-259">Web application proxy servers</span></span>  <br/> |
|<span data-ttu-id="ab97f-260">4.</span><span class="sxs-lookup"><span data-stu-id="ab97f-260">4.</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="ab97f-262">Elementos de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="ab97f-262">Infrastructure elements</span></span>  <br/> |
   
 <span data-ttu-id="ab97f-263">**Tabela R: Grupo de recursos**</span><span class="sxs-lookup"><span data-stu-id="ab97f-263">**Table R: Resource groups**</span></span>
  
<span data-ttu-id="ab97f-264">Crie os novos grupos de recursos com estes comandos.</span><span class="sxs-lookup"><span data-stu-id="ab97f-264">Create your new resource groups with these commands.</span></span>
  
```powershell
$locName="<an Azure location, such as West US>"
$rgName="<Table R - Item 1 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 2 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 3 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 4 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="ab97f-265">Em seguida, você criará a rede virtual do Azure e suas sub-redes.</span><span class="sxs-lookup"><span data-stu-id="ab97f-265">Next, you create the Azure virtual network and its subnets.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

<span data-ttu-id="ab97f-266">Em seguida, crie grupos de segurança de rede para cada sub-rede que tenha máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="ab97f-266">Next, you create network security groups for each subnet that has virtual machines.</span></span> <span data-ttu-id="ab97f-267">Para executar o isolamento de sub-rede, você pode adicionar regras para os tipos específicos de tráfego permitidos ou negados para o grupo de segurança de rede de uma sub-rede.</span><span class="sxs-lookup"><span data-stu-id="ab97f-267">To perform subnet isolation, you can add rules for the specific types of traffic allowed or denied to the network security group of a subnet.</span></span>
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="ab97f-268">Em seguida, use estes comandos para criar os gateways para a conexão VPN site a site.</span><span class="sxs-lookup"><span data-stu-id="ab97f-268">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> <span data-ttu-id="ab97f-269">A autenticação federada de usuários individuais não confia em nenhum recurso local.</span><span class="sxs-lookup"><span data-stu-id="ab97f-269">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="ab97f-270">No entanto, se esta conexão VPN de site a site ficar indisponível, os controladores de domínio no VNet não receberão atualizações para contas de usuário e grupos feitos nos serviços de domínio do Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="ab97f-270">However, if this site-to-site VPN connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services.</span></span> <span data-ttu-id="ab97f-271">Para garantir que isso não aconteça, é possível configurar a alta disponibilidade para a conexão VPN site a site.</span><span class="sxs-lookup"><span data-stu-id="ab97f-271">To ensure this does not happen, you can configure high availability for your site-to-site VPN connection.</span></span> <span data-ttu-id="ab97f-272">Veja mais informações em [Conectividade VNet para VNet e entre instalações altamente disponível](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span><span class="sxs-lookup"><span data-stu-id="ab97f-272">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="ab97f-273">Em seguida, registre o endereço IPv4 público do gateway de VPN do Azure para a sua rede virtual na exibição deste comando:</span><span class="sxs-lookup"><span data-stu-id="ab97f-273">Next, record the public IPv4 address of the Azure VPN gateway for your virtual network from the display of this command:</span></span>
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

<span data-ttu-id="ab97f-p114">Em seguida, configure seu dispositivo VPN local para se conectar ao gateway de VPN do Azure. Para saber mais, veja [Configurar seu dispositivo VPN](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span><span class="sxs-lookup"><span data-stu-id="ab97f-p114">Next, configure your on-premises VPN device to connect to the Azure VPN gateway. For more information, see [Configure your VPN device](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="ab97f-276">Para configurar seu dispositivo VPN local, você precisará do seguinte:</span><span class="sxs-lookup"><span data-stu-id="ab97f-276">To configure your on-premises VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="ab97f-277">O endereço IPv4 público do gateway de VPN do Azure.</span><span class="sxs-lookup"><span data-stu-id="ab97f-277">The public IPv4 address of the Azure VPN gateway.</span></span>
    
- <span data-ttu-id="ab97f-278">A chave IPsec pré-compartilhada para a conexão VPN de site a site (Tabela V - Item 5 - coluna Valor).</span><span class="sxs-lookup"><span data-stu-id="ab97f-278">The IPsec pre-shared key for the site-to-site VPN connection (Table V - Item 5 - Value column).</span></span>
    
<span data-ttu-id="ab97f-p115">Em seguida, certifique-se de que o espaço de endereço da rede virtual seja acessível a partir da sua rede local. Isso é feito geralmente com a inclusão de uma rota correspondente ao espaço de endereço da rede virtual para o seu dispositivo VPN e, em seguida, publicando essa rota ao restante da infraestrutura de roteamento da rede da sua organização. Trabalhe com seu departamento de TI para determinar como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="ab97f-p115">Next, ensure that the address space of the virtual network is reachable from your on-premises network. This is usually done by adding a route corresponding to the virtual network address space to your VPN device and then advertising that route to the rest of the routing infrastructure of your organization network. Work with your IT department to determine how to do this.</span></span>
  
<span data-ttu-id="ab97f-p116">Em seguida, defina os nomes de três conjuntos de disponibilidade. Preencha a Tabela A. </span><span class="sxs-lookup"><span data-stu-id="ab97f-p116">Next, define the names of three availability sets. Fill out Table A.</span></span> 
  
|<span data-ttu-id="ab97f-284">**Item**</span><span class="sxs-lookup"><span data-stu-id="ab97f-284">**Item**</span></span>|<span data-ttu-id="ab97f-285">**Finalidade**</span><span class="sxs-lookup"><span data-stu-id="ab97f-285">**Purpose**</span></span>|<span data-ttu-id="ab97f-286">**Nome do conjunto de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="ab97f-286">**Availability set name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ab97f-287">1.</span><span class="sxs-lookup"><span data-stu-id="ab97f-287">1.</span></span>  <br/> |<span data-ttu-id="ab97f-288">Controladores de domínio:</span><span class="sxs-lookup"><span data-stu-id="ab97f-288">Domain controllers</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-290">2.</span><span class="sxs-lookup"><span data-stu-id="ab97f-290">2.</span></span>  <br/> |<span data-ttu-id="ab97f-291">Servidores do AD FS</span><span class="sxs-lookup"><span data-stu-id="ab97f-291">AD FS servers</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="ab97f-293">3.</span><span class="sxs-lookup"><span data-stu-id="ab97f-293">3.</span></span>  <br/> |<span data-ttu-id="ab97f-294">Servidores proxy de aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="ab97f-294">Web application proxy servers</span></span>  <br/> |![linha](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="ab97f-296">**Tabela A: Conjuntos de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="ab97f-296">**Table A: Availability sets**</span></span>
  
<span data-ttu-id="ab97f-297">Você precisará desses nomes quando criar as máquinas virtuais nas fases 2, 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="ab97f-297">You will need these names when you create the virtual machines in phases 2, 3, and 4.</span></span>
  
<span data-ttu-id="ab97f-298">Crie os novos conjuntos de disponibilidade com estes comandos do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab97f-298">Create the new availability sets with these Azure PowerShell commands.</span></span>
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

<span data-ttu-id="ab97f-299">Esta é a configuração resultante da conclusão bem-sucedida dessa fase.</span><span class="sxs-lookup"><span data-stu-id="ab97f-299">This is the configuration resulting from the successful completion of this phase.</span></span>
  
<span data-ttu-id="ab97f-300">**Fase 1: a infraestrutura do Azure para autenticação federada de alta disponibilidade para o Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="ab97f-300">**Phase 1: The Azure infrastructure for high availability federated authentication for Microsoft 365**</span></span>

![Fase 1 da autenticação federada de alta disponibilidade da Microsoft 365 no Azure com a infraestrutura do Azure](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a><span data-ttu-id="ab97f-302">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ab97f-302">Next step</span></span>

<span data-ttu-id="ab97f-303">Use a [fase 2: configurar os controladores de domínio](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) para continuar com a configuração dessa carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ab97f-303">Use [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) to continue with the configuration of this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab97f-304">Confira também</span><span class="sxs-lookup"><span data-stu-id="ab97f-304">See Also</span></span>

[<span data-ttu-id="ab97f-305">Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure</span><span class="sxs-lookup"><span data-stu-id="ab97f-305">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="ab97f-306">Identidade federada para seu ambiente de desenvolvimento/teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab97f-306">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="ab97f-307">Centro de soluções e arquitetura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab97f-307">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="ab97f-308">Noções básicas sobre a identidade do Microsoft 365 e o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ab97f-308">Understanding Microsoft 365 identity and Azure Active Directory</span></span>](about-microsoft-365-identity.md)

