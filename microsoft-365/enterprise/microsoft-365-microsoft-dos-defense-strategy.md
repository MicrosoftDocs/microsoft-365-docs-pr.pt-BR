---
title: Estratégia de defesa de negação de serviço da Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Neste artigo, você pode encontrar uma visão geral da estratégia de defesa da Microsoft para ataques de negação de serviço (DoS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f28f7bcb9c6241404c8101bffe7268c5a1917ffa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687394"
---
# <a name="microsoft-365-denial-of-service-defense-strategy"></a><span data-ttu-id="50d67-103">Estratégia de defesa de negação de serviço da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="50d67-103">Microsoft 365 denial-of-service defense strategy</span></span>

<span data-ttu-id="50d67-104">A estratégia da Microsoft para se defender contra ataques de negação de serviço (DoS) baseado em rede é exclusiva devido à nossa escala e ao espaço global.</span><span class="sxs-lookup"><span data-stu-id="50d67-104">Microsoft's strategy to defend against network-based denial-of-service (DoS) attacks is unique due to our scale and global footprint.</span></span> <span data-ttu-id="50d67-105">Essa escala permite que a Microsoft use estratégias e técnicas de que poucas organizações, provedores ou organizações de clientes podem ser compatíveis.</span><span class="sxs-lookup"><span data-stu-id="50d67-105">This scale allows Microsoft to utilize strategies and techniques few organizations, providers, or customer organizations can match.</span></span> <span data-ttu-id="50d67-106">A base da estratégia de DoS é nossa presença global.</span><span class="sxs-lookup"><span data-stu-id="50d67-106">The cornerstone of the DoS strategy is our global presence.</span></span> <span data-ttu-id="50d67-107">A Microsoft se comunica com provedores de Internet, provedores de emparelhamento (públicos e privados) e corporações privadas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="50d67-107">Microsoft engages with Internet providers, peering providers (public and private), and private corporations all over the world.</span></span> <span data-ttu-id="50d67-108">Isso dá à Microsoft uma presença significativa na Internet e permite que a Microsoft absorver ataques em uma grande área de superfície.</span><span class="sxs-lookup"><span data-stu-id="50d67-108">This gives Microsoft a significant Internet presence and enables Microsoft to absorb attacks across a large surface area.</span></span>

<span data-ttu-id="50d67-109">Considerando essa natureza exclusiva, a Microsoft usa processos de detecção e mitigação que diferem dos usados por grandes empresas.</span><span class="sxs-lookup"><span data-stu-id="50d67-109">Given this unique nature, Microsoft uses detection and mitigation processes that differ from ones used by large enterprises.</span></span> <span data-ttu-id="50d67-110">A estratégia é baseada em uma separação de detecção e redução global distribuída por várias bordas de rede.</span><span class="sxs-lookup"><span data-stu-id="50d67-110">The strategy is based on a separation of detection and global distributed mitigation through many network edges.</span></span> <span data-ttu-id="50d67-111">Muitas empresas usam soluções de terceiros para detectar e reduzir ataques na borda.</span><span class="sxs-lookup"><span data-stu-id="50d67-111">Many enterprises use third-party solutions to detect and mitigate attacks at the edge.</span></span> <span data-ttu-id="50d67-112">À medida que a capacidade de borda da Microsoft aumentou, ficou claro o significado de qualquer ataque em relação a bordas individuais ou específicas era baixo.</span><span class="sxs-lookup"><span data-stu-id="50d67-112">As the edge capacity for Microsoft grew, it became clear the significance of any attack against individual or particular edges was low.</span></span> <span data-ttu-id="50d67-113">Por causa dessa configuração exclusiva, a Microsoft separou os componentes de detecção e mitigação.</span><span class="sxs-lookup"><span data-stu-id="50d67-113">Because of this unique configuration, Microsoft separated the detection and mitigation components.</span></span> <span data-ttu-id="50d67-114">A Microsoft implanta sistemas de detecção de várias camadas para detectar ataques mais próximos de seus pontos de saturação, mantendo a redução global na borda.</span><span class="sxs-lookup"><span data-stu-id="50d67-114">Microsoft deploys multi-tiered detection systems to detect attacks closer to their saturation points while maintaining global mitigation at the edge.</span></span> <span data-ttu-id="50d67-115">Essa estratégia garante que possamos lidar com vários ataques simultâneos.</span><span class="sxs-lookup"><span data-stu-id="50d67-115">This strategy ensures we can handle multiple simultaneous attacks.</span></span>

<span data-ttu-id="50d67-116">Uma das defesas mais eficazes e de baixo custo empregadas pela Microsoft contra ataques de negação de serviço é reduzir as superfícies de ataque.</span><span class="sxs-lookup"><span data-stu-id="50d67-116">One of the most effective and low-cost defenses employed by Microsoft against DoS attacks is reducing service attack surfaces.</span></span> <span data-ttu-id="50d67-117">O tráfego indesejado é Descartado na borda da rede em vez de analisar, processar e depurar os dados embutidos.</span><span class="sxs-lookup"><span data-stu-id="50d67-117">Unwanted traffic is dropped at the network edge instead of analyzing, processing, and scrubbing the data inline.</span></span>

<span data-ttu-id="50d67-118">Na interface com a rede pública, a Microsoft usa dispositivos de segurança de uso especial para firewall, conversão de endereços de rede e funções de filtragem de IP.</span><span class="sxs-lookup"><span data-stu-id="50d67-118">At the interface with the public network, Microsoft uses special-purpose security devices for firewall, network address translation, and IP filtering functions.</span></span> <span data-ttu-id="50d67-119">A Microsoft também usa roteamento global de vários caminhos de custo igual (ECMP).</span><span class="sxs-lookup"><span data-stu-id="50d67-119">Microsoft also uses global equal-cost multi-path (ECMP) routing.</span></span> <span data-ttu-id="50d67-120">Global ECMP Routing é uma estrutura de rede para garantir que haja vários caminhos globais para chegar a um serviço.</span><span class="sxs-lookup"><span data-stu-id="50d67-120">Global ECMP routing is a network framework to ensure that there are multiple global paths to reach a service.</span></span> <span data-ttu-id="50d67-121">Com esses vários caminhos, os ataques contra serviços são limitados à região da qual o ataque se originou.</span><span class="sxs-lookup"><span data-stu-id="50d67-121">With these multiple paths, attacks against services are limited to the region from which the attack originates.</span></span> <span data-ttu-id="50d67-122">Outras regiões devem ser não afetadas por esse ataque, já que os usuários finais usariam outros caminhos para acessar o serviço nessas regiões.</span><span class="sxs-lookup"><span data-stu-id="50d67-122">Other regions should be unaffected by this attack, as end users would use other paths to reach the service in those regions.</span></span> <span data-ttu-id="50d67-123">A Microsoft também desenvolveu sistemas de detecção e correlação de DoS internos que usam dados de fluxo, métricas de desempenho e outras informações.</span><span class="sxs-lookup"><span data-stu-id="50d67-123">Microsoft has also developed internal DoS correlation and detection systems that use flow data, performance metrics, and other information.</span></span> <span data-ttu-id="50d67-124">Este é um serviço de nuvem de hiperescalas no Microsoft Azure, que analisa dados coletados de vários pontos em redes e serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="50d67-124">This is a hyperscale cloud service in Microsoft Azure, which analyzes data collected from various points on Microsoft networks and services.</span></span> <span data-ttu-id="50d67-125">Uma equipe de resposta a incidentes de um entre cargas de trabalho identifica as funções e responsabilidades entre as equipes, os critérios de escalonamento e os protocolos para envolver várias equipes e tratamento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="50d67-125">A cross-workload DoS incident response team identifies the roles and responsibilities across teams, the criteria for escalations, and the protocols for engaging various teams and for incident handling.</span></span> <span data-ttu-id="50d67-126">Essas soluções fornecem proteção baseada em rede contra ataques de DoS.</span><span class="sxs-lookup"><span data-stu-id="50d67-126">These solutions provide network-based protection against DoS attacks.</span></span>

<span data-ttu-id="50d67-127">Por fim, as cargas de trabalho baseadas em nuvem são configuradas com limites otimizados com base em seu protocolo e uso de largura de banda precisa proteger exclusivamente essa carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="50d67-127">Finally, cloud-based workloads are configured with optimized thresholds based on their protocol and bandwidth usage needs to uniquely protect that workload.</span></span>