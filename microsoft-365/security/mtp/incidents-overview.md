---
title: Visão geral de incidentes na Proteção contra Ameaças da Microsoft
description: Investigue os incidentes vistos em dispositivos, usuários e caixas de correio.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3c50bbfbfdad85283f6e366a32c126958467f4a0
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431106"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="ce5fa-104">Visão geral de incidentes na Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce5fa-104">Incidents overview in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ce5fa-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ce5fa-105">**Applies to:**</span></span>
- <span data-ttu-id="ce5fa-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce5fa-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="ce5fa-107">Os incidentes são baseados em alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="ce5fa-108">Os alertas são criados quando um evento ou uma atividade mal-intencionados são vistos na sua rede.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="ce5fa-109">Alertas individuais fornecem pistas valiosas sobre um ataque contínuo.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="ce5fa-110">No entanto, os ataques geralmente empregam vários vetores e técnicas para realizar uma violação.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="ce5fa-111">Piecing pistas individuais juntas podem ser desafiadores e demorados.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="ce5fa-112">Este breve vídeo fornece uma visão geral de incidentes na proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-112">This short video gives an overview of incidents in Microsoft Threat Protection.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="ce5fa-113">Um incidente é uma coleção de alertas correlacionados que compõem a história de um ataque.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="ce5fa-114">Eventos mal-intencionados e suspeitos encontrados em diferentes entidades de dispositivo, usuário e caixa de correio na rede são agregados automaticamente pela proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft Threat Protection.</span></span> <span data-ttu-id="ce5fa-115">Agrupar alertas relacionados em um incidente oferece aos defensores de segurança uma visão abrangente de um ataque.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="ce5fa-116">Por exemplo, os defensores de segurança podem ver onde o ataque começou, quais táticas foram usadas e o quanto o ataque entrou na rede.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="ce5fa-117">Eles também podem ver o escopo do ataque, como quantos dispositivos, usuários e caixas de correio foram impactados, quão severo o impacto era e outros detalhes sobre entidades afetadas.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="ce5fa-118">Se for habilitada, a proteção contra ameaças da Microsoft poderá investigar e resolver automaticamente os alertas individuais por meio de automação e inteligência artificial.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-118">If enabled, Microsoft Threat Protection can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="ce5fa-119">Os defensores de segurança também podem realizar etapas adicionais de correção para resolver o ataque diretamente do modo de exibição incidentes.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="ce5fa-120">Os incidentes dos últimos 30 dias são mostrados na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="ce5fa-121">A partir daqui, os defensores de segurança podem ver quais incidentes devem ser priorizados com base no nível de risco e outros fatores.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="ce5fa-122">Os defensores de segurança também podem renomear incidentes, atribuí-los a analistas individuais, classificar e adicionar marcas a incidentes para uma experiência de gerenciamento de incidentes melhor e mais personalizada.</span><span class="sxs-lookup"><span data-stu-id="ce5fa-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="ce5fa-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="ce5fa-123">See also</span></span>
- [<span data-ttu-id="ce5fa-124">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="ce5fa-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ce5fa-125">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="ce5fa-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="ce5fa-126">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="ce5fa-126">Manage incidents</span></span>](manage-incidents.md)
