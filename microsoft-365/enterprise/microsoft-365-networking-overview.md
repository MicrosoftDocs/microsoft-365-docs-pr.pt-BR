---
title: Visão Geral da Conectividade de Rede do Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Discute por que a otimização de rede é importante para serviços SaaS, a meta da rede 365 da Microsoft e como o SaaS requer redes diferentes de outras cargas de trabalho.
ms.openlocfilehash: 4fea7364dc79717583ebca8ce0dbe333ee818f1f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687098"
---
# <a name="microsoft-365-network-connectivity-overview"></a><span data-ttu-id="a753d-103">Visão geral da conectividade de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-103">Microsoft 365 network connectivity overview</span></span>

<span data-ttu-id="a753d-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a753d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a753d-105">A Microsoft 365 é uma nuvem de software (SaaS) distribuída que oferece cenários de produtividade e colaboração por meio de um conjunto variado de micro serviços e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a753d-105">Microsoft 365 is a distributed Software-as-a-Service (SaaS) cloud that provides productivity and collaboration scenarios through a diverse set of micro-services and applications.</span></span> <span data-ttu-id="a753d-106">Os componentes do cliente do Microsoft 365 como o Outlook, o Word e o PowerPoint são executados nos computadores dos usuários e se conectam a outros componentes do Microsoft 365 executados nos datacenters da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a753d-106">Client components of Microsoft 365 such as Outlook, Word and PowerPoint run on user computers and connect to other components of Microsoft 365 that run in Microsoft datacenters.</span></span> <span data-ttu-id="a753d-107">O fator mais significativo que determina a qualidade da experiência do usuário final da Microsoft 365 é a confiabilidade da rede e baixa latência entre os clientes do Microsoft 365 e as portas frontais de serviço do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a753d-107">The most significant factor that determines the quality of the Microsoft 365 end user experience is network reliability and low latency between Microsoft 365 clients and Microsoft 365 service front doors.</span></span>

<span data-ttu-id="a753d-108">Neste artigo, você aprenderá sobre as metas da rede do Microsoft 365 e por que a Microsoft 365 rede requer uma abordagem diferente da otimização do que o tráfego de Internet genérico.</span><span class="sxs-lookup"><span data-stu-id="a753d-108">In this article, you will learn about the goals of Microsoft 365 networking, and why Microsoft 365 networking requires a different approach to optimization than generic Internet traffic.</span></span>

## <a name="microsoft-365-networking-goals"></a><span data-ttu-id="a753d-109">Metas de rede da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-109">Microsoft 365 networking goals</span></span>

<span data-ttu-id="a753d-110">O objetivo final da rede 365 da Microsoft é otimizar a experiência do usuário final, habilitando o acesso menos restritivo entre os clientes e os pontos de extremidade do Microsoft 365 mais próximos.</span><span class="sxs-lookup"><span data-stu-id="a753d-110">The ultimate goal of Microsoft 365 networking is to optimize the end user experience by enabling the least restrictive access between clients and the closest Microsoft 365 endpoints.</span></span> <span data-ttu-id="a753d-111">A qualidade da experiência do usuário final está diretamente relacionada ao desempenho e à capacidade de resposta do aplicativo que o usuário está usando.</span><span class="sxs-lookup"><span data-stu-id="a753d-111">The quality of end user experience is directly related to the performance and responsiveness of the application that the user is using.</span></span> <span data-ttu-id="a753d-112">Por exemplo, o Microsoft Teams depende de baixa latência para que as chamadas telefônicas de usuário, conferências e colaborações de tela compartilhada estejam sem problemas e o Outlook dependa da grande conectividade de rede para recursos de pesquisa instantânea que aproveitam os recursos de indexação do servidor e AI.</span><span class="sxs-lookup"><span data-stu-id="a753d-112">For example, Microsoft Teams relies on low latency so that user phone calls, conferences and shared screen collaborations are glitch-free, and Outlook relies on great networking connectivity for instant search features that leverage server-side indexing and AI capabilities.</span></span>

<span data-ttu-id="a753d-113">O objetivo principal no design de rede deve ser minimizar a latência, reduzindo o tempo de ida e volta (RTT) de máquinas clientes para a rede global da Microsoft, o backbone de rede pública da Microsoft que faz a conexão de todos os datacenters da Microsoft com a baixa latência e pontos de entrada do aplicativo de nuvem de alta disponibilidade espalhados pelo mundo.</span><span class="sxs-lookup"><span data-stu-id="a753d-113">The primary goal in the network design should be to minimize latency by reducing the round-trip time (RTT) from client machines to the Microsoft Global Network, Microsoft's public network backbone that interconnects all of Microsoft's datacenters with low latency, high availability cloud application entry points spread around the world.</span></span> <span data-ttu-id="a753d-114">Você pode saber mais sobre a Rede Global da Microsoft no [Como a Microsoft cria uma rede global rápida e confiável](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).</span><span class="sxs-lookup"><span data-stu-id="a753d-114">You can learn more about the Microsoft Global Network at [How Microsoft builds its fast and reliable global network](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).</span></span>

<span data-ttu-id="a753d-115">Otimizar o desempenho da rede Microsoft 365 não precisa ser complicado.</span><span class="sxs-lookup"><span data-stu-id="a753d-115">Optimizing Microsoft 365 network performance doesn't need to be complicated.</span></span> <span data-ttu-id="a753d-116">Você pode obter o melhor desempenho possível, seguindo alguns princípios fundamentais:</span><span class="sxs-lookup"><span data-stu-id="a753d-116">You can get the best possible performance by following a few key principles:</span></span>

- <span data-ttu-id="a753d-117">Identificar o tráfego de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-117">Identify Microsoft 365 network traffic</span></span>
- <span data-ttu-id="a753d-118">Permitir egresso de filial local do tráfego de rede 365 da Microsoft para a Internet de cada local onde os usuários se conectam ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-118">Allow local branch egress of Microsoft 365 network traffic to the internet from each location where users connect to Microsoft 365</span></span>
- <span data-ttu-id="a753d-119">Permitir que o tráfego da Microsoft 365 ignore proxies e dispositivos de inspeção de pacotes</span><span class="sxs-lookup"><span data-stu-id="a753d-119">Allow Microsoft 365 traffic to bypass proxies and packet inspection devices</span></span>

<span data-ttu-id="a753d-120">Para obter mais informações sobre os princípios de conectividade de rede da Microsoft 365, consulte [microsoft 365 princípios de conectividade de rede](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="a753d-120">For more information on Microsoft 365 network connectivity principles, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="traditional-network-architectures-and-saas"></a><span data-ttu-id="a753d-121">Arquiteturas de rede tradicionais e SaaS</span><span class="sxs-lookup"><span data-stu-id="a753d-121">Traditional network architectures and SaaS</span></span>

<span data-ttu-id="a753d-122">Os princípios de arquitetura de rede tradicionais para cargas de trabalho do cliente/servidor são projetados em torno da pressuposição de que o tráfego entre os clientes e os pontos de extremidade não é estendido fora do perímetro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="a753d-122">Traditional network architecture principles for client/server workloads are designed around the assumption that traffic between clients and endpoints does not extend outside the corporate network perimeter.</span></span> <span data-ttu-id="a753d-123">Além disso, em muitas redes corporativas, todas as conexões de saída da Internet atravessam a rede corporativa e saem de um local central.</span><span class="sxs-lookup"><span data-stu-id="a753d-123">Also, in many enterprise networks, all outbound Internet connections traverse the corporate network, and egress from a central location.</span></span>

<span data-ttu-id="a753d-124">Nas arquiteturas de rede tradicionais, a maior latência para o tráfego de Internet genérico é uma compensação necessária para manter a segurança do perímetro de rede, e a otimização de desempenho para o tráfego da Internet geralmente envolve a atualização ou o dimensionamento do equipamento em pontos de saída de rede.</span><span class="sxs-lookup"><span data-stu-id="a753d-124">In traditional network architectures, higher latency for generic Internet traffic is a necessary tradeoff in order to maintain network perimeter security, and performance optimization for Internet traffic typically involves upgrading or scaling out the equipment at network egress points.</span></span> <span data-ttu-id="a753d-125">No entanto, essa abordagem não aborda os requisitos para o desempenho ideal da rede de serviços SaaS como o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a753d-125">However, this approach does not address the requirements for optimum network performance of SaaS services such as Microsoft 365.</span></span>

## <a name="identifying-microsoft-365-network-traffic"></a><span data-ttu-id="a753d-126">Identificando o tráfego de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-126">Identifying Microsoft 365 network traffic</span></span>

<span data-ttu-id="a753d-127">Estamos facilitando a identificação do tráfego de rede do Microsoft 365 e tornando mais simples o gerenciamento da identificação de rede.</span><span class="sxs-lookup"><span data-stu-id="a753d-127">We're making it easier to identify Microsoft 365 network traffic and making it simpler to manage the network identification.</span></span>

- <span data-ttu-id="a753d-128">Novas categorias de pontos de extremidade de rede para diferenciar o tráfego de rede altamente crítico do tráfego de rede que não é afetado por latências de Internet.</span><span class="sxs-lookup"><span data-stu-id="a753d-128">New categories of network endpoints to differentiate highly critical network traffic from network traffic which is not impacted by Internet latencies.</span></span> <span data-ttu-id="a753d-129">Há apenas algumas URLs e endereços IP de suporte na categoria "otimizar" mais importante.</span><span class="sxs-lookup"><span data-stu-id="a753d-129">There are just a handful of URLs and supporting IP Addresses in the most critical “Optimize” category.</span></span>
- <span data-ttu-id="a753d-130">Serviços Web para uso de scripts ou configuração direta de dispositivos e gerenciamento de alterações da identificação de rede do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a753d-130">Web services for script usage or direct device configuration and change management of Microsoft 365 network identification.</span></span> <span data-ttu-id="a753d-131">As alterações estão disponíveis no serviço Web ou no formato RSS ou em email usando um modelo de fluxo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a753d-131">Changes are available from the web service, or in RSS format, or on email using a Microsoft Flow template.</span></span>
- <span data-ttu-id="a753d-132">[Programa de parceria de rede do Office 365](https://aka.ms/Office365NPP) com parceiros da Microsoft que oferecem dispositivos ou serviços que seguem os princípios de conectividade de rede da Microsoft 365 e que possuem uma configuração simples.</span><span class="sxs-lookup"><span data-stu-id="a753d-132">[Office 365 Network partner program](https://aka.ms/Office365NPP) with Microsoft partners who provide devices or services that follow Microsoft 365 network connectivity principles and have simple configuration.</span></span>

## <a name="securing-microsoft-365-connections"></a><span data-ttu-id="a753d-133">Protegendo conexões do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-133">Securing Microsoft 365 connections</span></span>

<span data-ttu-id="a753d-134">O objetivo da segurança de rede tradicional é otimizar o perímetro da rede corporativa contra invasões e explorações maliciosas.</span><span class="sxs-lookup"><span data-stu-id="a753d-134">The goal of traditional network security is to harden the corporate network perimeter against intrusion and malicious exploits.</span></span> <span data-ttu-id="a753d-135">A maioria das redes corporativas impõe a segurança de rede para o tráfego da Internet usando tecnologias como servidores proxy, firewalls, interrupção SSL e inspecionar, inspeção de pacote profunda e sistemas de prevenção contra perda de dados.</span><span class="sxs-lookup"><span data-stu-id="a753d-135">Most enterprise networks enforce network security for Internet traffic using technologies like proxy servers, firewalls, SSL break and inspect, deep packet inspection, and data loss prevention systems.</span></span> <span data-ttu-id="a753d-136">Essas tecnologias oferecem redução de risco importantes para solicitações de Internet genéricas, mas podem reduzir significativamente o desempenho, a capacidade de expansão e a qualidade da experiência do usuário final quando aplicada aos pontos de extremidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a753d-136">These technologies provide important risk mitigation for generic Internet requests but can dramatically reduce performance, scalability, and the quality of end user experience when applied to Microsoft 365 endpoints.</span></span>

<span data-ttu-id="a753d-137">A Microsoft 365 ajuda a atender às necessidades da sua organização quanto à segurança do conteúdo e à conformidade de uso de dados com recursos internos de segurança e governança projetados especificamente para os recursos e cargas de trabalho do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a753d-137">Microsoft 365 helps meet your organization's needs for content security and data usage compliance with built-in security and governance features designed specifically for Microsoft 365 features and workloads.</span></span> <span data-ttu-id="a753d-138">Para obter mais informações sobre segurança e conformidade do Microsoft 365, consulte o [mapa de segurança do Office 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap).</span><span class="sxs-lookup"><span data-stu-id="a753d-138">For more information about Microsoft 365 security and compliance, see the [Office 365 security roadmap](https://docs.microsoft.com/office365/securitycompliance/security-roadmap).</span></span> <span data-ttu-id="a753d-139">Para obter mais informações sobre as recomendações e a posição de suporte da Microsoft sobre soluções de rede avançadas que executam o processamento avançado no tráfego do Microsoft 365, consulte [usando dispositivos de rede de terceiros ou soluções no tráfego do Office 365](https://support.microsoft.com/help/2690045).</span><span class="sxs-lookup"><span data-stu-id="a753d-139">For more information about Microsoft’s recommendations and support position on advanced network solutions that perform advanced-level processing on Microsoft 365 traffic, see [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045).</span></span>

## <a name="why-is-microsoft-365-networking-different"></a><span data-ttu-id="a753d-140">Por que a rede Microsoft 365 é diferente?</span><span class="sxs-lookup"><span data-stu-id="a753d-140">Why is Microsoft 365 networking different?</span></span>

<span data-ttu-id="a753d-141">A Microsoft 365 foi projetada para o desempenho ideal usando a segurança de ponto de extremidade e as conexões de rede criptografadas, reduzindo a necessidade de imposição de segurança do</span><span class="sxs-lookup"><span data-stu-id="a753d-141">Microsoft 365 is designed for optimal performance using endpoint security and encrypted network connections, reducing the need for perimeter security enforcement.</span></span> <span data-ttu-id="a753d-142">Os datacenters do Microsoft 365 estão localizados em todo o mundo e o serviço é projetado para usar vários métodos de conexão de clientes aos melhores pontos de extremidade do serviço disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a753d-142">Microsoft 365 datacenters are located across the world and the service is designed to use various methods for connecting clients to best available service endpoints.</span></span> <span data-ttu-id="a753d-143">Como os dados e o processamento do usuário são distribuídos entre vários datacenters da Microsoft, não há um único ponto de extremidade de rede ao qual as máquinas clientes podem se conectar.</span><span class="sxs-lookup"><span data-stu-id="a753d-143">Since user data and processing is distributed between many Microsoft datacenters, there is no single network endpoint to which client machines can connect.</span></span> <span data-ttu-id="a753d-144">Na verdade, os dados e serviços em seu locatário do Microsoft 365 são dinamicamente otimizados pela rede global da Microsoft para se adaptar aos locais geográficos dos quais eles são acessados por usuários finais.</span><span class="sxs-lookup"><span data-stu-id="a753d-144">In fact, data and services in your Microsoft 365 tenant are dynamically optimized by the Microsoft Global Network to adapt to the geographic locations from which they are accessed by end users.</span></span>

<span data-ttu-id="a753d-145">Determinados problemas comuns de desempenho são criados quando o tráfego do Microsoft 365 está sujeito à inspeção de pacotes e à saída centralizada:</span><span class="sxs-lookup"><span data-stu-id="a753d-145">Certain common performance issues are created when Microsoft 365 traffic is subject to packet inspection and centralized egress:</span></span>

- <span data-ttu-id="a753d-146">Alta latência pode causar um desempenho extremamente ruim de fluxos de áudio e vídeo e resposta lenta de recuperação de dados, pesquisas, colaboração em tempo real, informações de disponibilidade do calendário, conteúdo do produto e outros serviços</span><span class="sxs-lookup"><span data-stu-id="a753d-146">High latency can cause extremely poor performance of video and audio streams, and slow response of data retrieval, searches, real-time collaboration, calendar free/busy information, in-product content and other services</span></span>
- <span data-ttu-id="a753d-147">As conexões de egresso de um local central derrotam os recursos de roteamento dinâmico da rede global do Microsoft 365, adicionando latência e tempo de ida e volta</span><span class="sxs-lookup"><span data-stu-id="a753d-147">Egressing connections from a central location defeats the dynamic routing capabilities of the Microsoft 365 global network, adding latency and round-trip time</span></span>
- <span data-ttu-id="a753d-148">Descriptografar o tráfego de rede do Microsoft 365 protegido por SSL e criptografá-lo novamente pode causar erros de protocolo e ter risco de segurança</span><span class="sxs-lookup"><span data-stu-id="a753d-148">Decrypting SSL secured Microsoft 365 network traffic and re-encrypting it can cause protocol errors and has security risk</span></span>

<span data-ttu-id="a753d-149">Reduzir o caminho de rede para os pontos de entrada do Microsoft 365, permitindo que o tráfego de saída do cliente seja o mais próximo possível do local geográfico pode melhorar o desempenho de conectividade e a experiência do usuário final no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a753d-149">Shortening the network path to Microsoft 365 entry points by allowing client traffic to egress as close as possible to their geographic location can improve connectivity performance and the end user experience in Microsoft 365.</span></span> <span data-ttu-id="a753d-150">Também pode ajudar a reduzir o impacto de alterações futuras na arquitetura de rede no desempenho e na confiabilidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a753d-150">It can also help to reduce the impact of future changes to the network architecture on Microsoft 365 performance and reliability.</span></span> <span data-ttu-id="a753d-151">O modelo de conectividade ideal é sempre fornecer egresso de rede no local do usuário, independentemente se isso está na rede corporativa ou locais remotos, como casa, hotéis, lanchonetes e aeroportos.</span><span class="sxs-lookup"><span data-stu-id="a753d-151">The optimum connectivity model is to always provide network egress at the user's location, regardless of whether this is on the corporate network or remote locations such as home, hotels, coffee shops and airports.</span></span> <span data-ttu-id="a753d-152">O tráfego da Internet genérico e o tráfego de rede corporativa baseado em WAN seriam roteados separadamente e não usam o modelo de egresso direta local.</span><span class="sxs-lookup"><span data-stu-id="a753d-152">Generic Internet traffic and WAN based corporate network traffic would be separately routed and not use the local direct egress model.</span></span> <span data-ttu-id="a753d-153">Esse modelo de saída direta local é representado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="a753d-153">This local direct egress model is represented in the diagram below.</span></span>

![Arquitetura de rede de saída local](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

<span data-ttu-id="a753d-155">A arquitetura de egresso local tem os seguintes benefícios para o tráfego de rede do Microsoft 365 em relação ao modelo tradicional:</span><span class="sxs-lookup"><span data-stu-id="a753d-155">The local egress architecture has the following benefits for Microsoft 365 network traffic over the traditional model:</span></span>
  
- <span data-ttu-id="a753d-156">Oferece o melhor desempenho do Microsoft 365, melhorando o comprimento da rota.</span><span class="sxs-lookup"><span data-stu-id="a753d-156">Provides optimal Microsoft 365 performance by optimizing route length.</span></span> <span data-ttu-id="a753d-157">As conexões de usuário final são direcionadas dinamicamente para o ponto de entrada mais próximo da Microsoft 365 pela infraestrutura de _porta frontal de serviço distribuído_ da rede global da Microsoft, e o tráfego é então roteado internamente para os pontos de extremidade de dados e serviço na fibra de alta disponibilidade de latência ultra baixa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a753d-157">End user connections are dynamically routed to the nearest Microsoft 365 entry point by the Microsoft Global Network's _Distributed Service Front Door_ infrastructure, and traffic is then routed internally to data and service endpoints over Microsoft's ultra-low latency high availability fiber.</span></span>
- <span data-ttu-id="a753d-158">Reduz a carga na infraestrutura de rede corporativa, permitindo o egresso local para o tráfego do Microsoft 365, ignorando proxies e dispositivos de inspeção de tráfego.</span><span class="sxs-lookup"><span data-stu-id="a753d-158">Reduces the load on corporate network infrastructure by allowing local egress for Microsoft 365 traffic, bypassing proxies and traffic inspection devices.</span></span>
- <span data-ttu-id="a753d-159">Protege as conexões em ambas as extremidades, aproveitando os recursos de segurança do ponto de extremidade do cliente e da nuvem, evitando a aplicação de tecnologias de segurança de rede redundantes.</span><span class="sxs-lookup"><span data-stu-id="a753d-159">Secures connections on both ends by leveraging client endpoint security and cloud security features, avoiding application of redundant network security technologies.</span></span>

> [!NOTE]
> <span data-ttu-id="a753d-160">A infraestrutura de _porta frontal de serviço distribuído_ é a borda de rede altamente disponível e escalonável da rede global da Microsoft com locais geograficamente distribuídos.</span><span class="sxs-lookup"><span data-stu-id="a753d-160">The _Distributed Service Front Door_ infrastructure is the Microsoft Global Network's highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="a753d-161">Ela termina as conexões de usuário final e as roteia com eficiência dentro da rede global da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a753d-161">It terminates end user connections and efficiently routes them within the Microsoft Global Network.</span></span> <span data-ttu-id="a753d-162">Você pode saber mais sobre a Rede Global da Microsoft no [Como a Microsoft cria uma rede global rápida e confiável](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).</span><span class="sxs-lookup"><span data-stu-id="a753d-162">You can learn more about the Microsoft Global Network at [How Microsoft builds its fast and reliable global network](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).</span></span>

<span data-ttu-id="a753d-163">Para obter mais informações sobre a compreensão e a aplicação dos princípios de conectividade de rede da Microsoft 365, consulte [microsoft 365 Network Connectivity principless](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="a753d-163">For more information on understanding and applying Microsoft 365 network connectivity principles, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="conclusion"></a><span data-ttu-id="a753d-164">Conclusão</span><span class="sxs-lookup"><span data-stu-id="a753d-164">Conclusion</span></span>

<span data-ttu-id="a753d-165">Otimizar o desempenho da rede Microsoft 365 é muito bem possível para remover impedimentos desnecessários.</span><span class="sxs-lookup"><span data-stu-id="a753d-165">Optimizing Microsoft 365 network performance really comes down to removing unnecessary impediments.</span></span> <span data-ttu-id="a753d-166">Ao tratar as conexões do Microsoft 365 como tráfego confiável, você pode evitar que a latência seja introduzida pela inspeção de pacote e concorrência para a largura de banda do proxy.</span><span class="sxs-lookup"><span data-stu-id="a753d-166">By treating Microsoft 365 connections as trusted traffic, you can prevent latency from being introduced by packet inspection and competition for proxy bandwidth.</span></span> <span data-ttu-id="a753d-167">Permitir conexões locais entre máquinas clientes e pontos de extremidade do Office 365 permite que o tráfego seja direcionado dinamicamente através da rede global da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a753d-167">Allowing local connections between client machines and Office 365 endpoints enables traffic to be dynamically routed through the Microsoft Global Network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a753d-168">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="a753d-168">Related Topics</span></span>

[<span data-ttu-id="a753d-169">Princípios de conectividade de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-169">Microsoft 365 Network Connectivity Principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="a753d-170">Gerenciar pontos de extremidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="a753d-170">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="a753d-171">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="a753d-171">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="a753d-172">URL do serviço Web e endereço IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="a753d-172">Office 365 IP Address and URL Web service</span></span>](microsoft-365-ip-web-service.md)

[<span data-ttu-id="a753d-173">Avaliando a conectividade de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-173">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

[<span data-ttu-id="a753d-174">Planejamento de rede e ajuste de desempenho para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-174">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="a753d-175">Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho</span><span class="sxs-lookup"><span data-stu-id="a753d-175">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)

[<span data-ttu-id="a753d-176">Plano de solução de problemas de desempenho do Office 365</span><span class="sxs-lookup"><span data-stu-id="a753d-176">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)

[<span data-ttu-id="a753d-177">Redes de Distribuição de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="a753d-177">Content Delivery Networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="a753d-178">Teste de conectividade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a753d-178">Microsoft 365 connectivity test</span></span>](https://aka.ms/netonboard)

[<span data-ttu-id="a753d-179">Como a Microsoft cria sua rede global confiável e rápida</span><span class="sxs-lookup"><span data-stu-id="a753d-179">How Microsoft builds its fast and reliable global network</span></span>](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[<span data-ttu-id="a753d-180">Blog de rede do Office 365</span><span class="sxs-lookup"><span data-stu-id="a753d-180">Office 365 Networking blog</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)