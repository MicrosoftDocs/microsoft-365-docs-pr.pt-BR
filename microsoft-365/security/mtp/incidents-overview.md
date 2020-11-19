---
title: Visão geral de incidentes no Microsoft 365 defender
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
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357606"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="7685f-104">Visão geral de incidentes no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7685f-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7685f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7685f-105">**Applies to:**</span></span>
- <span data-ttu-id="7685f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7685f-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="7685f-107">Quer experimentar o Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="7685f-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="7685f-108">Você pode [avaliá-lo em um ambiente de laboratório](https://aka.ms/mtp-trial-lab) ou [executar o projeto piloto em produção](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="7685f-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="7685f-109">Os incidentes são baseados em alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="7685f-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="7685f-110">Os alertas são criados quando um evento ou uma atividade mal-intencionados são vistos na sua rede.</span><span class="sxs-lookup"><span data-stu-id="7685f-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="7685f-111">Alertas individuais fornecem pistas valiosas sobre um ataque contínuo.</span><span class="sxs-lookup"><span data-stu-id="7685f-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="7685f-112">No entanto, os ataques geralmente empregam vários vetores e técnicas para realizar uma violação.</span><span class="sxs-lookup"><span data-stu-id="7685f-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="7685f-113">Piecing pistas individuais juntas podem ser desafiadores e demorados.</span><span class="sxs-lookup"><span data-stu-id="7685f-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="7685f-114">Este breve vídeo fornece uma visão geral de incidentes no Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="7685f-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="7685f-115">Um incidente é uma coleção de alertas correlacionados que compõem a história de um ataque.</span><span class="sxs-lookup"><span data-stu-id="7685f-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="7685f-116">Eventos mal-intencionados e suspeitos encontrados em entidades diferentes de dispositivo, usuário e caixa de correio na rede são agregados automaticamente pelo Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="7685f-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="7685f-117">Agrupar alertas relacionados em um incidente oferece aos defensores de segurança uma visão abrangente de um ataque.</span><span class="sxs-lookup"><span data-stu-id="7685f-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="7685f-118">Por exemplo, os defensores de segurança podem ver onde o ataque começou, quais táticas foram usadas e o quanto o ataque entrou na rede.</span><span class="sxs-lookup"><span data-stu-id="7685f-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="7685f-119">Eles também podem ver o escopo do ataque, como quantos dispositivos, usuários e caixas de correio foram impactados, quão severo o impacto era e outros detalhes sobre entidades afetadas.</span><span class="sxs-lookup"><span data-stu-id="7685f-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="7685f-120">Se for habilitada, o Microsoft 365 defender poderá investigar e resolver automaticamente os alertas individuais por meio de automação e inteligência artificial.</span><span class="sxs-lookup"><span data-stu-id="7685f-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="7685f-121">Os defensores de segurança também podem realizar etapas adicionais de correção para resolver o ataque diretamente do modo de exibição incidentes.</span><span class="sxs-lookup"><span data-stu-id="7685f-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="7685f-122">Os incidentes dos últimos 30 dias são mostrados na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="7685f-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="7685f-123">A partir daqui, os defensores de segurança podem ver quais incidentes devem ser priorizados com base no nível de risco e outros fatores.</span><span class="sxs-lookup"><span data-stu-id="7685f-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="7685f-124">Os defensores de segurança também podem renomear incidentes, atribuí-los a analistas individuais, classificar e adicionar marcas a incidentes para uma experiência de gerenciamento de incidentes melhor e mais personalizada.</span><span class="sxs-lookup"><span data-stu-id="7685f-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="7685f-125">Também consulte</span><span class="sxs-lookup"><span data-stu-id="7685f-125">See also</span></span>
- [<span data-ttu-id="7685f-126">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="7685f-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="7685f-127">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="7685f-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="7685f-128">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="7685f-128">Manage incidents</span></span>](manage-incidents.md)
