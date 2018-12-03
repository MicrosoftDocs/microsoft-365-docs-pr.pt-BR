---
title: Sistema de rede para a Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Compreenda a infraestrutura de rede da Contoso e como ela usa a tecnologia SD-WAN para ter a conectividade de rede de desempenho ideal para serviços baseados na nuvem do Microsoft 365 Enterprise.
ms.openlocfilehash: 0ef9c37755927444276c83a2c5952b5cb96f22ed
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864673"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="d4800-103">Sistema de rede para a Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="d4800-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="d4800-104">**Resumo:** compreenda a infraestrutura de rede da Contoso e como ela usa a tecnologia SD-WAN para ter a conectividade de rede de desempenho ideal para serviços baseados na nuvem do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d4800-104">**Summary:** Understand the Contoso networking infrastructure and how it uses its SD WAN technology for optimal performance network connectivity to Microsoft 365 Enterprise cloud based services.</span></span>

<span data-ttu-id="d4800-p101">Para adotar uma infraestrutura que inclua a nuvem, os engenheiros de rede da Contoso perceberam a mudança fundamental na maneira como funciona o tráfego de rede para serviços baseados na nuvem. Em vez de um modelo hub-spoke que concentra a conectividade de rede na matriz, eles trabalharam para mapear locais de usuários para saída de Internet local e conexões locais para os locais de rede da Microsoft na Internet.</span><span class="sxs-lookup"><span data-stu-id="d4800-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud-based services travels. Instead of a hub and spoke model that focusses network connectivity on the head office, they worked to map user locations to local Internet egress and local connections to Microsoft network locations on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="d4800-107">Infraestrutura de rede da Contoso</span><span class="sxs-lookup"><span data-stu-id="d4800-107">Contoso's networking infrastructure</span></span>

<span data-ttu-id="d4800-108">Os elementos de rede da Contoso que vinculam seus escritórios em todo o mundo são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="d4800-108">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="d4800-109">Rede MPLS WAN</span><span class="sxs-lookup"><span data-stu-id="d4800-109">MPLS WAN network</span></span>

  <span data-ttu-id="d4800-p102">Uma rede MPLS WAN conecta a sede de Paris aos escritórios regionais e esses a filiais em uma configuração hub-spoke. Isso é para os usuários acessarem os servidores locais que compõem os aplicativos da linha de negócios no escritório de Paris. Ele também roteará qualquer tráfego genérico da Internet para o escritório de Paris, onde os dispositivos de segurança de rede verificam as solicitações. Em cada escritório, os roteadores oferecem tráfego para hosts ou pontos de acesso sem fio em sub-redes que usam o espaço privado de endereço IP.</span><span class="sxs-lookup"><span data-stu-id="d4800-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="d4800-114">Acesso direto local à Internet para tráfego do Office 365</span><span class="sxs-lookup"><span data-stu-id="d4800-114">Local direct Internet access for Office 365 traffic</span></span>

  <span data-ttu-id="d4800-p103">Cada escritório tem um dispositivo SD-WAN com um dos circuitos de rede Internet ISP mais locais, com sua própria conectividade com a Internet por meio de um servidor proxy. Isso normalmente é implementado como um link de WAN em um ISP local que também fornece endereços IP públicos e endereços IP do servidor DNS local para o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d4800-p103">Each office has an SD WAN device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and local DNS server IP addresses for the proxy server.</span></span>

- <span data-ttu-id="d4800-117">Presença na Internet</span><span class="sxs-lookup"><span data-stu-id="d4800-117">Internet presence</span></span>

  <span data-ttu-id="d4800-p104">A Contoso possui o nome de domínio público contoso.com. O site público da Contoso para fazer o pedido de produtos é um conjunto de servidores em um datacenter conectado à Internet no campus de Paris. A Contoso usa um intervalo de endereço IP público /24 na Internet.</span><span class="sxs-lookup"><span data-stu-id="d4800-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="d4800-121">A figura 1 mostra a infraestrutura de rede da Contoso e suas conexões com a Internet.</span><span class="sxs-lookup"><span data-stu-id="d4800-121">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![](./media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="d4800-122">**Figura 1: Rede da Contoso**</span><span class="sxs-lookup"><span data-stu-id="d4800-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="d4800-123">Uso de SD-WAN para conectividade de rede ideal para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4800-123">Use of SD WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="d4800-124">A Contoso seguiu os [Princípios de conectividade de rede do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):</span><span class="sxs-lookup"><span data-stu-id="d4800-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):</span></span>

1. <span data-ttu-id="d4800-125">Identificar e diferenciar tráfego de rede do Office 365</span><span class="sxs-lookup"><span data-stu-id="d4800-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="d4800-126">Enviar conexões de rede de saída localmente</span><span class="sxs-lookup"><span data-stu-id="d4800-126">Egress network connections locally</span></span>
3. <span data-ttu-id="d4800-127">Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="d4800-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="d4800-128">Ignorar dispositivos de segurança de rede duplicados</span><span class="sxs-lookup"><span data-stu-id="d4800-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="d4800-p105">Há três categorias de tráfego de rede do Office 365: Otimizar, Permitir e Padrão. Otimizar e Permitir tráfego é o tráfego de rede confiável que é criptografado e protegido nos pontos de extremidade e destinado a data centers da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4800-p105">There are three categories of network traffic for Office 365: Optimize, Allow, and Default. Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for Microsoft datacenters.</span></span>

<span data-ttu-id="d4800-131">A Contoso decidiu usar saída direta de Internet para o tráfego de categoria Otimizar e Permitir e para encaminhar todo o tráfego de categoria Padrão para a conexão de Internet central com base em Paris.</span><span class="sxs-lookup"><span data-stu-id="d4800-131">Contoso decided to use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

<span data-ttu-id="d4800-132">A empresa optou por implantar os dispositivos SD-WAN em cada escritório como uma maneira simples de seguir estes princípios e atingir um desempenho ideal de rede para os serviços baseados em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4800-132">They decided to deploy SD WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="d4800-p106">Os dispositivos SD-WAN têm uma porta LAN para a rede local e várias portas WAN. Uma porta WAN conecta-se à sua rede MPLS e outras portas WAN se conectam aos circuitos ISP locais. O dispositivo SD-WAN direciona o tráfego de rede de categoria Otimizar e Permitir para os links do ISP.</span><span class="sxs-lookup"><span data-stu-id="d4800-p106">The SD WAN devices have a LAN port for the local office network and multiple WAN ports. One WAN port connects to their MPLS network and other WAN ports connect to local ISP circuits. The SD WAN device routes Optimize and Allow category network traffic to the ISP links.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="d4800-136">Infraestrutura do aplicativo de linha de negócios da Contoso</span><span class="sxs-lookup"><span data-stu-id="d4800-136">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="d4800-137">A Contoso projetou sua infraestrutura de aplicativo e servidor de linha de negócios para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d4800-137">Contoso has architected its line of business application and server infrastructure for the following:</span></span>

- <span data-ttu-id="d4800-138">As filiais usam servidores de cache locais para armazenar documentos acessados com frequência e sites internos.</span><span class="sxs-lookup"><span data-stu-id="d4800-138">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="d4800-p107">Os hubs regionais usam servidores de aplicativo regionais para os escritórios regionais e as filiais. Esses servidores sincronizam-se com os servidores da matriz de Paris.</span><span class="sxs-lookup"><span data-stu-id="d4800-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="d4800-141">O campus de Paris tem os datacenters que contêm os servidores de aplicativo centralizados que atendem toda a organização.</span><span class="sxs-lookup"><span data-stu-id="d4800-141">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="d4800-142">A Figura 2 mostra a porcentagem do tráfego de rede ao acessar os servidores na intranet da Contoso.</span><span class="sxs-lookup"><span data-stu-id="d4800-142">Figure 1 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![](./media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="d4800-143">**Figura 2: Infraestrutura da Contoso para aplicativos internos**</span><span class="sxs-lookup"><span data-stu-id="d4800-143">**Figure 1: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="d4800-p108">Para usuários nas filiais ou hubs regionais, 60% dos recursos de que os funcionários precisam podem ser atendidos por servidores de filiais e hubs regionais. Os outros 40% das solicitações de recursos devem ir pelo link de WAN para o campus de Paris.</span><span class="sxs-lookup"><span data-stu-id="d4800-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="d4800-146">A preparação e a análise de rede da Contoso para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4800-146">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d4800-p109">A adoção bem-sucedida dos serviços do Microsoft 365 Enterprise por usuários da Contoso dependem da conectividade de alta disponibilidade e eficaz com a Internet ou diretamente com os serviços em nuvem da Microsoft. A Contoso realizou estas etapas para planejar e implementar a conectividade otimizada com serviços de nuvem do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="d4800-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="d4800-149">Criou um diagrama de rede WAN da empresa para ajudar a planejar</span><span class="sxs-lookup"><span data-stu-id="d4800-149">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="d4800-p110">A Contoso iniciou seu planejamento de rede criando um diagrama que mostra seus locais, a conectividade de rede existente, os dispositivos de perímetro de rede existentes e as classes de serviço que são gerenciadas na rede. Eles usaram este diagrama para cada etapa subsequente no planejamento e na implementação da conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="d4800-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="d4800-152">Criou um plano para conectividade de rede do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4800-152">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="d4800-153">A Contoso usou os [princípios de conectividade de rede do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) e forneceu arquiteturas de rede de referência para determinar o SD-WAN como a topologia preferencial para a conectividade do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4800-153">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="d4800-154">Analisou a utilização da conexão de Internet e a largura de banda MPLS WAN em cada escritório e aumentou a largura de banda conforme o necessário</span><span class="sxs-lookup"><span data-stu-id="d4800-154">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="d4800-155">Cada escritório foi analisado em relação ao uso atual e os circuitos foram aumentados para que o tráfego com base em nuvem previsto do Microsoft 365 funcionasse com uma média de 20% da capacidade não utilizada.</span><span class="sxs-lookup"><span data-stu-id="d4800-155">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="d4800-156">Otimizou o desempenho para os serviços de rede da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4800-156">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="d4800-p111">A Contoso determinou o conjunto de pontos de extremidade do Office 365, do Intune e do Azure e firewalls configurados, dispositivos de segurança e outros sistemas no caminho da Internet para obter um desempenho ideal. Os pontos de extremidade para o tráfego de categoria Otimizar e Permitir do Office 365 foram configurados para os dispositivos SD-WAN que receberam acesso direto à Internet.</span><span class="sxs-lookup"><span data-stu-id="d4800-p111">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance. Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD WAN devices that provided direct Internet access.</span></span>

5. <span data-ttu-id="d4800-159">Configurou DNS interno</span><span class="sxs-lookup"><span data-stu-id="d4800-159">Configured internal DNS</span></span>

   <span data-ttu-id="d4800-160">O DNS precisa ser funcional e ser pesquisado localmente para o tráfego do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4800-160">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="d4800-161">Validou o ponto de extremidade de rede e a conectividade da porta</span><span class="sxs-lookup"><span data-stu-id="d4800-161">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="d4800-162">A Contoso executou ferramentas de teste de conectividade de rede fornecidas pela Microsoft para validar a conectividade de serviços de nuvem do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d4800-162">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="d4800-163">Otimizou computadores de funcionários para a conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="d4800-163">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="d4800-164">Os computadores individuais foram verificados para garantir que as atualizações mais recentes do sistema operacional foram instaladas e o monitoramento de segurança do ponto de extremidade estava ativo em todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="d4800-164">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="d4800-165">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="d4800-165">Next step</span></span>

<span data-ttu-id="d4800-166">[Saiba](contoso-identity.md) como a Contoso está aproveitando o seu provedor de identidade local na nuvem para os funcionários e realizando a federação de autenticação para clientes e parceiros de negócios.</span><span class="sxs-lookup"><span data-stu-id="d4800-166">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises identity provider in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4800-167">Confira também</span><span class="sxs-lookup"><span data-stu-id="d4800-167">See also</span></span>

[<span data-ttu-id="d4800-168">Sistema de rede para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4800-168">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="d4800-169">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="d4800-169">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d4800-170">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="d4800-170">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
