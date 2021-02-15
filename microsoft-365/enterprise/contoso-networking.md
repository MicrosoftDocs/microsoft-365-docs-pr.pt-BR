---
title: Sistema de rede para a Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda a infraestrutura de rede da Contoso e como a empresa usa sua tecnologia SD-WAN para obter o melhor desempenho de rede para o Microsoft 365 para serviços de nuvem corporativos.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754009"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="aaa2f-103">Sistema de rede para a Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="aaa2f-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="aaa2f-p101">Para adotar uma infraestrutura de nuvem inclusiva, a Contoso desdopou uma mudança fundamental em como o tráfego de rede para serviços de nuvem viaja. Em vez de um modelo interno de hub e spoke que concentra a conectividade de rede e o tráfego para o próximo nível da hierarquia de escritório, eles mapearam locais de usuário para saída de Internet local e conexões locais para o local de rede do Microsoft 365 mais próximo na Internet.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-p101">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels. Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="aaa2f-106">Infraestrutura de rede</span><span class="sxs-lookup"><span data-stu-id="aaa2f-106">Networking infrastructure</span></span>

<span data-ttu-id="aaa2f-107">Estes são os elementos de rede que vinculam escritórios da Contoso em todo o mundo:</span><span class="sxs-lookup"><span data-stu-id="aaa2f-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="aaa2f-108">Rede WAN de Comutação de Rótulos Multiprotocolo (MPLS)</span><span class="sxs-lookup"><span data-stu-id="aaa2f-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="aaa2f-p102">Uma rede MPLS WAN conecta a sede de Paris a escritórios regionais e escritórios regionais a filiais em uma configuração spoke-and-hub. A rede permite que os usuários acessem servidores locais que comem aplicativos de linha de negócios na sede de Paris. Ele também encaminha qualquer tráfego genérico da Internet para o escritório de Paris, onde os dispositivos de segurança de rede limparão as solicitações. Em cada escritório, os roteadores entregam tráfego para hosts com fio ou pontos de acesso sem fio em sub-redes, que usam o espaço de endereço IP privado.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration. The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters. It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="aaa2f-113">Acesso direto local à Internet para o tráfego do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aaa2f-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="aaa2f-p103">Cada escritório tem um dispositivo WAN (SD-WAN) definido por software que tem um ou mais circuitos de rede ISP de Internet locais com sua própria conectividade com a Internet por meio de um servidor proxy. Normalmente, isso é implementado como um link WAN para um ISP local que também fornece endereços IP públicos e um servidor DNS local.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-p103">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="aaa2f-116">Presença na Internet</span><span class="sxs-lookup"><span data-stu-id="aaa2f-116">Internet presence</span></span>

  <span data-ttu-id="aaa2f-p104">A Contoso possui o nome de domínio público contoso \. com. O site público da Contoso para solicitar produtos é um conjunto de servidores em um datacenter conectado à Internet no campus de Paris. A Contoso usa um intervalo de endereços IP públicos /24 na Internet.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-p104">Contoso owns the contoso\.com public domain name. The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="aaa2f-120">A Figura 1 mostra a infraestrutura de rede da Contoso e suas conexões com a Internet.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![A rede Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="aaa2f-122">**Figura 1: A rede da Contoso**</span><span class="sxs-lookup"><span data-stu-id="aaa2f-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="aaa2f-123">Uso de SD-WAN para conectividade de rede ideal para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="aaa2f-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="aaa2f-124">A Contoso seguiu os [Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md) para:</span><span class="sxs-lookup"><span data-stu-id="aaa2f-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="aaa2f-125">Identificar e diferenciar o tráfego de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aaa2f-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="aaa2f-126">Enviar conexões de rede de saída localmente</span><span class="sxs-lookup"><span data-stu-id="aaa2f-126">Egress network connections locally</span></span>
- <span data-ttu-id="aaa2f-127">Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="aaa2f-127">Avoid network hairpins</span></span>
- <span data-ttu-id="aaa2f-128">Ignorar dispositivos de segurança de rede duplicados</span><span class="sxs-lookup"><span data-stu-id="aaa2f-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="aaa2f-129">Há três categorias de tráfego de rede para o Microsoft 365: *Otimizar,* *Permitir* e *Padrão.*</span><span class="sxs-lookup"><span data-stu-id="aaa2f-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="aaa2f-130">Otimizar e Permitir tráfego é um tráfego de rede confiável que é criptografado e protegido nos pontos de extremidade e destinado à rede do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="aaa2f-131">A Contoso decidiu:</span><span class="sxs-lookup"><span data-stu-id="aaa2f-131">Contoso decided to:</span></span>

- <span data-ttu-id="aaa2f-132">Use a saída direta da Internet para otimizar e permitir o tráfego da categoria e para encaminhar todo o tráfego de categoria padrão para a conexão de Internet central com base em Paris.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="aaa2f-133">Implante dispositivos SD-WAN em cada escritório como uma maneira simples de seguir esses princípios e alcançar o melhor desempenho de rede para os serviços baseados em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="aaa2f-134">Os dispositivos SD-WAN possuem uma porta LAN para a rede do escritório local e várias portas WAN.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="aaa2f-135">Uma porta WAN se conecta à rede MPLS.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="aaa2f-136">Outro conecta-se a um circuito ISP local.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="aaa2f-137">O dispositivo SD-WAN roteia o tráfego de rede da categoria Otimizar e Permitir através do link ISP.

</span><span class="sxs-lookup"><span data-stu-id="aaa2f-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="aaa2f-138">A infraestrutura do aplicativo de linha de negócios da Contoso</span><span class="sxs-lookup"><span data-stu-id="aaa2f-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="aaa2f-139">A Contoso arquitetou sua infraestrutura de intranet de servidor e aplicativo de linha de negócios para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aaa2f-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="aaa2f-140">As filiais usam servidores de cache locais para armazenar documentos acessados com frequência e sites internos.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="aaa2f-p107">Os hubs regionais usam servidores de aplicativo regionais para os escritórios regionais e as filiais. Esses servidores sincronizam-se com os servidores da matriz de Paris.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="aaa2f-143">Os datacenters do campus de Paris contêm servidores de aplicativos centralizados que atendem toda a organização.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="aaa2f-144">A Figura 2 mostra a porcentagem de capacidade de tráfego de rede usada ao acessar servidores na intranet da Contoso.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![A infraestrutura da Contoso para aplicativos internos](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="aaa2f-146">**Figura 2: A infraestrutura da Contoso para aplicativos internos**</span><span class="sxs-lookup"><span data-stu-id="aaa2f-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="aaa2f-147">Para os escritórios de hub satélite ou regionais, 60% dos recursos necessários para os funcionários podem ser atendidos por servidores de filiais e hubs regionais.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="aaa2f-148">Os 40% adicionais de solicitações de recursos devem passar pelo link WAN para o campus de Paris.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="aaa2f-149">Análise de rede e preparação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="aaa2f-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="aaa2f-150">A adoção bem-sucedida do Microsoft 365 para serviços corporativos por usuários da Contoso depende de conectividade altamente disponível e de alto desempenho com a Internet ou diretamente com os serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="aaa2f-151">A Contoso tomou estas etapas para planejar e implementar a conectividade otimizada com o Microsoft 365 para serviços de nuvem corporativos:</span><span class="sxs-lookup"><span data-stu-id="aaa2f-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="aaa2f-152">Criar um diagrama de rede WAN da empresa para auxiliar no planejamento</span><span class="sxs-lookup"><span data-stu-id="aaa2f-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="aaa2f-153">Para iniciar o planejamento de rede, a Contoso criou um diagrama mostrando seus locais de escritório, conectividade de rede existente, dispositivos de perímetro de rede existentes e classes de serviço gerenciadas na rede.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="aaa2f-154">Ela usou este diagrama para cada etapa subsequente no planejamento e na implementação da conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="aaa2f-155">Criar um plano para o Microsoft 365 para conectividade de rede corporativa</span><span class="sxs-lookup"><span data-stu-id="aaa2f-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="aaa2f-156">A Contoso usou os princípios de conectividade de rede do [Microsoft 365](microsoft-365-network-connectivity-principles.md) e exemplos de arquiteturas de rede de referência para identificar o SD-WAN como sua topologia preferida para a conectividade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="aaa2f-157">Analisar a utilização da conexão com a Internet e a largura de banda MPLS-WAN em cada escritório e aumentar a largura de banda conforme necessário</span><span class="sxs-lookup"><span data-stu-id="aaa2f-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="aaa2f-158">O uso atual de cada escritório foi analisado e os circuitos foram aumentados para que o tráfego previsto na nuvem do Microsoft 365 funcionasse com uma média de 20% de capacidade não utilizado.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="aaa2f-159">Otimizar o desempenho dos serviços de rede da Microsoft</span><span class="sxs-lookup"><span data-stu-id="aaa2f-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="aaa2f-160">A Contoso determinou o conjunto de pontos de extremidade do Office 365, Do Intune e do Azure e configurou firewalls, dispositivos de segurança e outros sistemas no caminho da Internet para obter o melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="aaa2f-161">Os pontos de extremidade do tráfego da categoria Otimizar e Permitir do Office 365 foram configurados nos dispositivos SD-WAN para roteamento pelo circuito ISP.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="aaa2f-162">Configurar o DNS interno</span><span class="sxs-lookup"><span data-stu-id="aaa2f-162">Configure internal DNS</span></span>

   <span data-ttu-id="aaa2f-163">O DNS precisa ser funcional e ser pesquisado localmente para o tráfego do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="aaa2f-164">Validar o ponto de extremidade de rede e a conectividade de porta</span><span class="sxs-lookup"><span data-stu-id="aaa2f-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="aaa2f-165">A Contoso fez o teste de conectividade de rede da Microsoft para validar a conectividade do Microsoft 365 para serviços de nuvem corporativos.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="aaa2f-166">Otimizar computadores dos funcionários para conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="aaa2f-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="aaa2f-167">Computadores individuais foram verificados para garantir que as atualizações mais recentes do sistema operacional foram instaladas e que o monitoramento de segurança do ponto de extremidade estava ativo em todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="aaa2f-168">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="aaa2f-168">Next step</span></span>

<span data-ttu-id="aaa2f-169">Saiba como a Contoso está aproveitando seus Serviços de Domínio Active Directory locais na nuvem para [funcionários](contoso-identity.md) e autenticação federante para clientes e parceiros de negócios.</span><span class="sxs-lookup"><span data-stu-id="aaa2f-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaa2f-170">Confira também</span><span class="sxs-lookup"><span data-stu-id="aaa2f-170">See also</span></span>

[<span data-ttu-id="aaa2f-171">Roteiro de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aaa2f-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="aaa2f-172">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="aaa2f-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="aaa2f-173">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="aaa2f-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
