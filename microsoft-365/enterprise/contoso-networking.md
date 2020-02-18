---
title: Sistema de rede para a Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda a infraestrutura de rede da Contoso e como ela usa sua tecnologia SD-WAN para obter o melhor desempenho de rede dos serviços em nuvem do Microsoft 365 Enterprise.
ms.openlocfilehash: 20279ac0aed1b7ad86e1fc8e1d78a412230eba52
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068328"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="79452-103">Sistema de rede para a Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="79452-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="79452-p101">Para adotar uma infraestrutura inclusiva na nuvem, os engenheiros de rede da Contoso perceberam a mudança fundamental na maneira como o tráfego de rede nos serviços em nuvem viaja. Em vez de um modelo interno de hub e spoke que concentra a conectividade e o tráfego de rede no próximo nível da hierarquia de escritórios da Contoso, eles trabalharam para mapear os locais dos usuários para a saída local da Internet e as conexões locais para o local de rede mais próximo do Microsoft 365 na Internet.

</span><span class="sxs-lookup"><span data-stu-id="79452-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels. Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="79452-106">Infraestrutura de rede da Contoso</span><span class="sxs-lookup"><span data-stu-id="79452-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="79452-107">Os elementos de rede da Contoso que vinculam seus escritórios em todo o mundo são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="79452-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="79452-108">Rede WAN de Comutação de Rótulos Multiprotocolo (MPLS)</span><span class="sxs-lookup"><span data-stu-id="79452-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="79452-p102">Uma rede MPLS WAN conecta a sede de Paris aos escritórios regionais e esses a filiais em uma configuração hub-spoke. Isso é para os usuários acessarem os servidores locais que compõem os aplicativos da linha de negócios no escritório de Paris. Ele também roteará qualquer tráfego genérico da Internet para o escritório de Paris, onde os dispositivos de segurança de rede verificam as solicitações. Em cada escritório, os roteadores oferecem tráfego para hosts ou pontos de acesso sem fio em sub-redes que usam o espaço privado de endereço IP.</span><span class="sxs-lookup"><span data-stu-id="79452-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="79452-113">Acesso local direto à Internet para o tráfego do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="79452-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="79452-p103">Cada escritório possui um dispositivo WAN Definido por Software (SD-WAN) com mais um dos circuitos de rede ISP da Internet locais, com conectividade própria à Internet através de um servidor proxy. Isso geralmente é implementado como um link WAN para um ISP local que também fornece endereços IP públicos e um servidor DNS local.

</span><span class="sxs-lookup"><span data-stu-id="79452-p103">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="79452-116">Presença na Internet</span><span class="sxs-lookup"><span data-stu-id="79452-116">Internet presence</span></span>

  <span data-ttu-id="79452-p104">A Contoso possui o nome de domínio público contoso.com. O site público da Contoso para fazer o pedido de produtos é um conjunto de servidores em um datacenter conectado à Internet no campus de Paris. A Contoso usa um intervalo de endereço IP público /24 na Internet.</span><span class="sxs-lookup"><span data-stu-id="79452-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="79452-120">A figura 1 mostra a infraestrutura de rede da Contoso e suas conexões com a Internet.</span><span class="sxs-lookup"><span data-stu-id="79452-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![Rede da Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="79452-122">**Figura 1: Rede da Contoso**</span><span class="sxs-lookup"><span data-stu-id="79452-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="79452-123">Uso de SD-WAN para conectividade de rede ideal para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="79452-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="79452-124">A Contoso seguiu os [princípios de conectividade de rede do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) para:</span><span class="sxs-lookup"><span data-stu-id="79452-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) to:</span></span>

1. <span data-ttu-id="79452-125">Identificar e diferenciar tráfego de rede do Office 365</span><span class="sxs-lookup"><span data-stu-id="79452-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="79452-126">Enviar conexões de rede de saída localmente</span><span class="sxs-lookup"><span data-stu-id="79452-126">Egress network connections locally</span></span>
3. <span data-ttu-id="79452-127">Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="79452-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="79452-128">Ignorar dispositivos de segurança de rede duplicados</span><span class="sxs-lookup"><span data-stu-id="79452-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="79452-129">Há três categorias de tráfego de rede para o Office 365: Otimizar, Permitir e Padrão.</span><span class="sxs-lookup"><span data-stu-id="79452-129">There are three categories of network traffic for Office 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="79452-130">Otimize e permita que tráfego seja um tráfego de rede confiável, criptografado e protegido nos pontos de extremidade e destinado à rede do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79452-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="79452-131">A Contoso decidiu:</span><span class="sxs-lookup"><span data-stu-id="79452-131">Contoso decided to:</span></span>

- <span data-ttu-id="79452-132">Usar saída direta de Internet para o tráfego de categoria Otimizar e Permitir e para encaminhar todo o tráfego de categoria Padrão para a conexão de Internet central com base em Paris.</span><span class="sxs-lookup"><span data-stu-id="79452-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="79452-133">Implantar os dispositivos SD-WAN em cada escritório como uma maneira simples de seguir estes princípios e atingir um desempenho ideal de rede para os serviços baseados em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79452-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="79452-134">Os dispositivos SD-WAN possuem uma porta LAN para a rede do escritório local e várias portas WAN.</span><span class="sxs-lookup"><span data-stu-id="79452-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="79452-135">Uma porta WAN se conecta à sua rede MPLS e outra porta WAN se conecta a um circuito ISP local.</span><span class="sxs-lookup"><span data-stu-id="79452-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="79452-136">O dispositivo SD-WAN roteia o tráfego de rede da categoria Otimizar e Permitir através do link ISP.

</span><span class="sxs-lookup"><span data-stu-id="79452-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="79452-137">Infraestrutura do aplicativo de linha de negócios da Contoso</span><span class="sxs-lookup"><span data-stu-id="79452-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="79452-138">A Contoso projetou sua infraestrutura de aplicativos de negócios e intranet de servidores para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79452-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="79452-139">As filiais usam servidores de cache locais para armazenar documentos acessados com frequência e sites internos.</span><span class="sxs-lookup"><span data-stu-id="79452-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="79452-p107">Os hubs regionais usam servidores de aplicativo regionais para os escritórios regionais e as filiais. Esses servidores sincronizam-se com os servidores da matriz de Paris.</span><span class="sxs-lookup"><span data-stu-id="79452-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="79452-142">O campus de Paris tem os datacenters que contêm os servidores de aplicativo centralizados que atendem toda a organização.</span><span class="sxs-lookup"><span data-stu-id="79452-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="79452-143">A Figura 2 mostra a porcentagem do tráfego de rede ao acessar os servidores na intranet da Contoso.</span><span class="sxs-lookup"><span data-stu-id="79452-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![Infraestrutura da Contoso para aplicativos internos](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="79452-145">**Figura 2: Infraestrutura da Contoso para aplicativos internos**</span><span class="sxs-lookup"><span data-stu-id="79452-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="79452-p108">Para usuários nas filiais ou hubs regionais, 60% dos recursos de que os funcionários precisam podem ser atendidos por servidores de filiais e hubs regionais. Os outros 40% das solicitações de recursos devem ir pelo link de WAN para o campus de Paris.</span><span class="sxs-lookup"><span data-stu-id="79452-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="79452-148">A preparação e a análise de rede da Contoso para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="79452-148">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="79452-p109">A adoção bem-sucedida dos serviços do Microsoft 365 Enterprise por usuários da Contoso dependem da conectividade de alta disponibilidade e eficaz com a Internet ou diretamente com os serviços em nuvem da Microsoft. A Contoso realizou estas etapas para planejar e implementar a conectividade otimizada com serviços de nuvem do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="79452-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="79452-151">Criou um diagrama de rede WAN da empresa para ajudar a planejar</span><span class="sxs-lookup"><span data-stu-id="79452-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="79452-152">A Contoso iniciou seu planejamento de rede criando um diagrama que mostra seus locais, a conectividade de rede existente, os dispositivos de perímetro de rede existentes e as classes de serviço que são gerenciadas na rede. </span><span class="sxs-lookup"><span data-stu-id="79452-152">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network.</span></span> <span data-ttu-id="79452-153">Ela usou este diagrama para cada etapa subsequente no planejamento e na implementação da conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="79452-153">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="79452-154">Criou um plano para conectividade de rede do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="79452-154">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="79452-155">A Contoso usou os [princípios de conectividade de rede do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) e forneceu arquiteturas de rede de referência para determinar o SD-WAN como a topologia preferencial para a conectividade do Office 365.</span><span class="sxs-lookup"><span data-stu-id="79452-155">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD-WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="79452-156">Analisou a utilização da conexão de Internet e a largura de banda MPLS WAN em cada escritório e aumentou a largura de banda conforme o necessário</span><span class="sxs-lookup"><span data-stu-id="79452-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="79452-157">Cada escritório foi analisado em relação ao uso atual e os circuitos foram aumentados para que o tráfego com base em nuvem previsto do Microsoft 365 funcionasse com uma média de 20% da capacidade não utilizada.</span><span class="sxs-lookup"><span data-stu-id="79452-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="79452-158">Otimizou o desempenho para os serviços de rede da Microsoft</span><span class="sxs-lookup"><span data-stu-id="79452-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="79452-159">A Contoso determinou o conjunto de pontos de extremidade do Office 365, Intune e Azure e configurou firewalls, dispositivos de segurança e outros sistemas no caminho da Internet para desempenho otimizado.</span><span class="sxs-lookup"><span data-stu-id="79452-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="79452-160">Os pontos de extremidade do tráfego de categoria Otimizar e Permitir do Office 365 foram configurados nos dispositivos SD-WAN para roteamento pelo circuito ISP.</span><span class="sxs-lookup"><span data-stu-id="79452-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="79452-161">DNS interno configurado</span><span class="sxs-lookup"><span data-stu-id="79452-161">Configured internal DNS</span></span>

   <span data-ttu-id="79452-162">O DNS precisa ser funcional e ser pesquisado localmente para o tráfego do Office 365.</span><span class="sxs-lookup"><span data-stu-id="79452-162">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="79452-163">Validou o ponto de extremidade de rede e a conectividade da porta</span><span class="sxs-lookup"><span data-stu-id="79452-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="79452-164">A Contoso executou ferramentas de teste de conectividade de rede fornecidas pela Microsoft para validar a conectividade de serviços de nuvem do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="79452-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="79452-165">Otimizou computadores de funcionários para a conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="79452-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="79452-166">Os computadores individuais foram verificados para garantir que as atualizações mais recentes do sistema operacional foram instaladas e o monitoramento de segurança do ponto de extremidade estava ativo em todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="79452-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="79452-167">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="79452-167">Next step</span></span>

<span data-ttu-id="79452-168">[Saiba](contoso-identity.md) como a Contoso está aproveitando seus Serviços de Domínio Active Directory (AD DS) na nuvem para funcionários e autenticação de federação para clientes e parceiros de negócios.</span><span class="sxs-lookup"><span data-stu-id="79452-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="79452-169">Confira também</span><span class="sxs-lookup"><span data-stu-id="79452-169">See also</span></span>

[<span data-ttu-id="79452-170">Sistema de rede para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="79452-170">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="79452-171">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="79452-171">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="79452-172">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="79452-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
