---
title: Visão geral de incidentes no Microsoft 365 Defender
description: Investigue os incidentes vistos em dispositivos, usuários e caixas de correio.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6dd13c5f83d05be3c77e5f84608fb6aa5172d9a4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500932"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="a1bbd-104">Visão geral de incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1bbd-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a1bbd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a1bbd-105">**Applies to:**</span></span>
- <span data-ttu-id="a1bbd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1bbd-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="a1bbd-107">Quer experimentar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="a1bbd-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="a1bbd-108">Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="a1bbd-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="a1bbd-109">Os incidentes se baseiam em alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="a1bbd-110">Os alertas são criados quando um evento ou uma atividade mal-intencionados são vistos na sua rede.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="a1bbd-111">Alertas individuais fornecem dicas valiosas sobre um ataque em tempo útil.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="a1bbd-112">No entanto, os ataques geralmente empregam vários vetores e técnicas para executar uma violação.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="a1bbd-113">Reunir pistas individuais pode ser desafiador e demorado.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="a1bbd-114">Este vídeo curto fornece uma visão geral dos incidentes no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="a1bbd-115">Um incidente é uma coleção de alertas correlacionados que comentam a história de um ataque.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="a1bbd-116">Eventos mal-intencionados e suspeitos encontrados em diferentes entidades de dispositivo, usuário e caixa de correio na rede são agregados automaticamente pelo Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="a1bbd-117">Agrupar alertas relacionados a um incidente proporciona aos defensores de segurança uma visão abrangente de um ataque.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="a1bbd-118">Por exemplo, os defensores de segurança podem ver onde o ataque começou, quais táticas foram usadas e até onde o ataque foi para a rede.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="a1bbd-119">Eles também podem ver o escopo do ataque, como quantos dispositivos, usuários e caixas de correio foram afetados, a gravidade do impacto e outros detalhes sobre entidades afetadas.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="a1bbd-120">Se habilitado, o Microsoft 365 Defender pode investigar e resolver automaticamente os alertas individuais por meio de automação e inteligência artificial.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="a1bbd-121">Os defensores de segurança também podem executar etapas de correção adicionais para resolver o ataque diretamente do ponto de vista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="a1bbd-122">Incidentes dos últimos 30 dias são mostrados na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="a1bbd-123">A partir daqui, os defensores de segurança podem ver quais incidentes devem ser priorizados com base no nível de risco e em outros fatores.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="a1bbd-124">Os defensores de segurança também podem renomear incidentes, atribuí-los a analistas individuais, classificar e adicionar marcas a incidentes para uma experiência de gerenciamento de incidentes melhor e mais personalizada.</span><span class="sxs-lookup"><span data-stu-id="a1bbd-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="a1bbd-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="a1bbd-125">See also</span></span>
- [<span data-ttu-id="a1bbd-126">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="a1bbd-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="a1bbd-127">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="a1bbd-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a1bbd-128">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="a1bbd-128">Manage incidents</span></span>](manage-incidents.md)