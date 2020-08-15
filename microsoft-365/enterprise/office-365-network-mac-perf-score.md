---
title: Avaliação de rede do Microsoft 365 (versão prévia)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Avaliação de rede do Microsoft 365 (versão prévia)
ms.openlocfilehash: aacbdf73da9552a12bde250e51544f1de533637c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695372"
---
# <a name="microsoft-365-network-assessment-preview"></a><span data-ttu-id="898e3-103">Avaliação de rede do Microsoft 365 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="898e3-103">Microsoft 365 network assessment (preview)</span></span>

<span data-ttu-id="898e3-104">Na página de conectividade do centro de administração do 365 da Microsoft para a Microsoft 365, as **avaliações de rede** expostam uma agregação de muitas métricas de desempenho de rede em um instantâneo da integridade da rede corporativa, representado por um valor de pontos de 1-100.</span><span class="sxs-lookup"><span data-stu-id="898e3-104">In the Microsoft 365 Admin Center's Connectivity to Microsoft 365 page, **network assessments** distill an aggregate of many network performance metrics into a snapshot of your enterprise network health, represented by a points value from 1 - 100.</span></span> <span data-ttu-id="898e3-105">As avaliações de rede têm o escopo para o locatário inteiro e para cada localização geográfica a partir da qual os usuários se conectam ao seu locatário, fornecendo aos administradores da Microsoft 365 uma maneira fácil de obter instantaneamente um Gestalt da integridade da rede da empresa e rapidamente se aprofundam em um relatório detalhado de qualquer local do escritório global.</span><span class="sxs-lookup"><span data-stu-id="898e3-105">Network assessments are scoped to both the entire tenant and for each geographic location from which users connect to your tenant, providing Microsoft 365 administrators with an easy way to instantly grasp a gestalt of the enterprise's network health and quickly drill down into a detailed report for any global office location.</span></span>

<span data-ttu-id="898e3-106">O valor de pontos de avaliação de rede é uma medição média da latência, largura de banda, velocidade de download e métricas de qualidade de conexão compiladas ao vivo no momento em que são exibidas.</span><span class="sxs-lookup"><span data-stu-id="898e3-106">The network assessment points value is an average measurement of latency, bandwidth, download speed and connection quality metrics compiled live at the time they are viewed.</span></span> <span data-ttu-id="898e3-107">As métricas de desempenho para redes de propriedade da Microsoft são excluídas dessas medidas para garantir que os resultados da avaliação sejam inequívocas e específicos da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="898e3-107">Performance metrics for Microsoft-owned networks are excluded from these measurements to ensure that assessment results are unambiguous and specific to the corporate network.</span></span>

![Valor de avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

<span data-ttu-id="898e3-109">Um valor de avaliação de rede muito baixo sugere que os clientes do Microsoft 365 terão problemas significativos para se conectar ao locatário ou manter uma experiência de usuário responsiva, enquanto um valor alto indica uma rede configurada corretamente com poucos problemas de desempenho contínuos.</span><span class="sxs-lookup"><span data-stu-id="898e3-109">A very low network assessment value suggests that Microsoft 365 clients will have significant problems connecting to the tenant or maintaining a responsive user experience, while a high value indicates a properly configured network with few ongoing performance issues.</span></span> <span data-ttu-id="898e3-110">Um valor de 80% representa uma linha de base saudável onde você não deve receber queixas regulares do usuário sobre a conectividade ou a capacidade de resposta do Microsoft 365 devido ao desempenho da rede.</span><span class="sxs-lookup"><span data-stu-id="898e3-110">A value of 80% represents a healthy baseline where you should not expect to receive regular user complaints about Microsoft 365 connectivity or responsiveness due to network performance.</span></span> <span data-ttu-id="898e3-111">Conforme são feitas melhorias de conectividade de rede iterativa, esse valor aumentará junto com a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="898e3-111">As iterative network connectivity improvements are made, this value will increase along with user experience.</span></span>

>[!IMPORTANT]
><span data-ttu-id="898e3-112">Os insights de rede, as recomendações de desempenho e as avaliações no centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para os locatários do Microsoft 365 que foram registrados no programa de visualização de recurso.</span><span class="sxs-lookup"><span data-stu-id="898e3-112">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="network-assessment-panel"></a><span data-ttu-id="898e3-113">Painel de avaliação de rede</span><span class="sxs-lookup"><span data-stu-id="898e3-113">Network assessment panel</span></span>

<span data-ttu-id="898e3-114">Cada avaliação de rede, com escopo para o locatário ou para um local específico do Office, mostra um painel com detalhes sobre a avaliação.</span><span class="sxs-lookup"><span data-stu-id="898e3-114">Each network assessment, whether scoped to the tenant or to a specific office location, shows a panel with details about the assessment.</span></span> <span data-ttu-id="898e3-115">Este painel mostra um gráfico de barras da avaliação como uma porcentagem e como o total de pontos para cada carga de trabalho do componente, incluindo apenas as cargas de trabalho onde os dados de medição foram recebidos.</span><span class="sxs-lookup"><span data-stu-id="898e3-115">This panel shows a bar chart of the assessment both as a percentage and as the total points for each component workload including only workloads where measurement data was received.</span></span> <span data-ttu-id="898e3-116">Para uma avaliação de rede de local do Office, também mostramos um benchmark que é a mediana de todos os clientes da Microsoft 365 que informaram dados na mesma cidade que o local do escritório.</span><span class="sxs-lookup"><span data-stu-id="898e3-116">For an office location network assessment, we also show a benchmark which is the median of all Microsoft 365 clients that reported data in the same city as your office location.</span></span>

![Exemplo de valor de avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

<span data-ttu-id="898e3-118">A **divisão de avaliação** no painel mostra a avaliação de cada uma das cargas de trabalho do componente.</span><span class="sxs-lookup"><span data-stu-id="898e3-118">The **Assessment breakdown** in the panel shows the assessment for each of the component workloads.</span></span>

<span data-ttu-id="898e3-119">O **histórico de avaliação** mostra os últimos 30 dias da avaliação e o benchmark.</span><span class="sxs-lookup"><span data-stu-id="898e3-119">The **Assessment history** shows the past 30 days of the assessment and the benchmark.</span></span>

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a><span data-ttu-id="898e3-120">Avaliações de rede de locatários e avaliações de rede de local do escritório</span><span class="sxs-lookup"><span data-stu-id="898e3-120">Tenant network assessments and office location network assessments</span></span>

<span data-ttu-id="898e3-121">Uma avaliação de rede mede o design do perímetro de rede de um local do escritório para a rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="898e3-121">A network assessment measures the design of the network perimeter of an office location to Microsoft's network.</span></span> <span data-ttu-id="898e3-122">Aprimoramentos no perímetro da rede são mais bem executados em cada local do escritório ou onde a conectividade de rede é agregada pode haver melhorias que afetam vários locais.</span><span class="sxs-lookup"><span data-stu-id="898e3-122">Improvements to the network perimeter is best done at each office location, or where network connectivity is aggregated there may be improvements that impact multiple locations.</span></span>

<span data-ttu-id="898e3-123">Mostramos um valor de avaliação de rede para todo o Microsoft 365 locatário na página de visão geral do desempenho da rede e um valor específico para cada local do escritório detectado na página de resumo desse local.</span><span class="sxs-lookup"><span data-stu-id="898e3-123">We show a network assessment value for the whole Microsoft 365 tenant on the network performance overview page and a specific value for each detected office location on that location's summary page.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="898e3-124">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="898e3-124">Exchange Online</span></span>

<span data-ttu-id="898e3-125">Para o Exchange Online, a latência TCP da máquina cliente para o servidor front-end do Exchange é medida.</span><span class="sxs-lookup"><span data-stu-id="898e3-125">For Exchange Online the TCP latency from the client machine to the Exchange front end server is measured.</span></span> <span data-ttu-id="898e3-126">Isso pode ser afetado pela distância que a rede se movimenta na LAN e na WAN dos clientes.</span><span class="sxs-lookup"><span data-stu-id="898e3-126">This can be impacted by the distance the network travels over the customers LAN and WAN.</span></span> <span data-ttu-id="898e3-127">Também pode ser afetado por dispositivos ou serviços intermediários de rede que atrasam a conectividade ou fazem com que os pacotes sejam reenviados.</span><span class="sxs-lookup"><span data-stu-id="898e3-127">It can also be impacted by network intermediary devices or services which delay the connectivity or cause packets to be resent.</span></span>

## <a name="sharepoint-online"></a><span data-ttu-id="898e3-128">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="898e3-128">SharePoint Online</span></span>

<span data-ttu-id="898e3-129">Para o SharePoint Online, a velocidade de download disponível para o usuário acessar um documento é medida.</span><span class="sxs-lookup"><span data-stu-id="898e3-129">For SharePoint Online the download speed available for a user to access a document is measured.</span></span> <span data-ttu-id="898e3-130">Isso pode ser afetado pela largura de banda disponível em circuitos de rede entre a máquina cliente e a rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="898e3-130">This can be impacted by the bandwidth available on network circuits between the client machine and Microsoft's network.</span></span> <span data-ttu-id="898e3-131">Também é possível impactar com o congestionamento de rede que existe em gargalos em dispositivos de rede complexos ou em áreas de Wi-Fi de cobertura ruim.</span><span class="sxs-lookup"><span data-stu-id="898e3-131">It is also often impacted by network congestion that exists in bottlenecks in complex network devices or in poor coverage Wi-Fi areas.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="898e3-132">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="898e3-132">Microsoft Teams</span></span>

<span data-ttu-id="898e3-133">Para o Microsoft Teams, a qualidade da rede é medida como latência de UDP, tremulação de UDP e perda de pacotes UDP.</span><span class="sxs-lookup"><span data-stu-id="898e3-133">For Microsoft Teams the Network quality is measured as UDP latency, UDP jitter, and UDP packet loss.</span></span> <span data-ttu-id="898e3-134">O UDP é usado para a chamada e conferência de áudio e conectividade de mídia de vídeo para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="898e3-134">UDP is used for call and conferencing audio and video media connectivity for Microsoft Teams.</span></span> <span data-ttu-id="898e3-135">Isso pode ser afetado pelos mesmos fatores para a latência e velocidade de download, além de falhas de conectividade no suporte a UDP de uma rede, pois o UDP é configurado separadamente para o protocolo TCP mais comum.</span><span class="sxs-lookup"><span data-stu-id="898e3-135">This can be impacted by the same factors as for latency and download speed in addition to connectivity gaps in a network's UDP support since UDP is configured separately to the more common TCP protocol.</span></span>

## <a name="related-topics"></a><span data-ttu-id="898e3-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="898e3-136">Related topics</span></span>

[<span data-ttu-id="898e3-137">Recomendações de desempenho de rede no centro de administração do Microsoft 365 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="898e3-137">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="898e3-138">Microsoft 365 Network Performance insights (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="898e3-138">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="898e3-139">Teste de conectividade do Microsoft 365 no centro de administração do M365 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="898e3-139">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="898e3-140">Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="898e3-140">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
