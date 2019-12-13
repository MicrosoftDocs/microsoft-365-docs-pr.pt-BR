---
title: Investigar incidentes na Proteção contra Ameaças da Microsoft
description: Investigue os incidentes vistos em dispositivos, usuários e caixas de correio.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 989184c5dd8af6aafc525100e34e0172d96adcfe
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910708"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="36b0a-104">Visão geral de incidentes na Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="36b0a-104">Incidents overview in Microsoft Threat Protection</span></span>

<span data-ttu-id="36b0a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="36b0a-105">**Applies to:**</span></span>
- <span data-ttu-id="36b0a-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="36b0a-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="36b0a-107">A base de todos os incidentes são os alertas.</span><span class="sxs-lookup"><span data-stu-id="36b0a-107">The basis of all incidents are alerts.</span></span> <span data-ttu-id="36b0a-108">Os alertas são criados quando um evento ou uma atividade mal-intencionados são vistos na sua rede.</span><span class="sxs-lookup"><span data-stu-id="36b0a-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="36b0a-109">Os alertas individuais fornecem pistas valiosas sobre o que está acontecendo em eventos individuais ou entidades.</span><span class="sxs-lookup"><span data-stu-id="36b0a-109">Individual alerts provide valuable clues in what's happening on individual events or entities.</span></span> <span data-ttu-id="36b0a-110">No entanto, em ataques geralmente são usados vários vetores de ataque para executar uma violação.</span><span class="sxs-lookup"><span data-stu-id="36b0a-110">However, attacks typically employ various attack vectors to carry out a breach.</span></span> <span data-ttu-id="36b0a-111">Juntar pistas individuais para chegar a um todo pode ser um desafio.</span><span class="sxs-lookup"><span data-stu-id="36b0a-111">Piecing individual clues together can be a challenging and time-consuming task.</span></span> 

<span data-ttu-id="36b0a-112">A Proteção contra Ameaças da Microsoft conecta os pontos em alertas individuais.</span><span class="sxs-lookup"><span data-stu-id="36b0a-112">Microsoft Threat Protection connects the dots on individual alerts.</span></span> <span data-ttu-id="36b0a-113">Os eventos mal-intencionados nas seguintes entidades são exibidos no centro de segurança do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="36b0a-113">Malicious events on the following entities are surfaced in the Microsoft 365 security center:</span></span>
- <span data-ttu-id="36b0a-114">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="36b0a-114">Devices</span></span>
- <span data-ttu-id="36b0a-115">Usuários</span><span class="sxs-lookup"><span data-stu-id="36b0a-115">Users</span></span>
- <span data-ttu-id="36b0a-116">Caixas de correio</span><span class="sxs-lookup"><span data-stu-id="36b0a-116">Mailboxes</span></span>

<span data-ttu-id="36b0a-117">Os eventos suspeitos que mostram as características de ser parte de um ataque maior são agregados em um só incidente.</span><span class="sxs-lookup"><span data-stu-id="36b0a-117">Suspicious events that show characteristics of being part of a larger attack are aggregated into an incident.</span></span> 

<span data-ttu-id="36b0a-118">Você saberá exatamente onde um ataque começou e outros detalhes para ajudá-lo a ver a extensão desse ataque.</span><span class="sxs-lookup"><span data-stu-id="36b0a-118">You'll know exactly where an attack started and other details to help you see the extent of the attack.</span></span>

<span data-ttu-id="36b0a-119">A plataforma fornece agentes defensores da segurança com visuais e representações de dados corretos para entender e resolver ameaças complexas que podem afetar diferentes entidades ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="36b0a-119">The platform provides security defenders with the right visuals and data representations to understand and address complex cross-entity threats.</span></span> 

<span data-ttu-id="36b0a-120">Você terá não somente visibilidade sobre o escopo de um ataque, mas também terá acesso aos serviços que permitirão que você execute etapas táticas para conter um incidente.</span><span class="sxs-lookup"><span data-stu-id="36b0a-120">Not only will you have visibility on the scope of an attack, but you'll also have access to services that will allow you to take tactical steps to contain an incident.</span></span>


## <a name="related-topics"></a><span data-ttu-id="36b0a-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="36b0a-121">Related topics</span></span>
- [<span data-ttu-id="36b0a-122">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="36b0a-122">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="36b0a-123">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="36b0a-123">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="36b0a-124">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="36b0a-124">Manage incidents</span></span>](manage-incidents.md)