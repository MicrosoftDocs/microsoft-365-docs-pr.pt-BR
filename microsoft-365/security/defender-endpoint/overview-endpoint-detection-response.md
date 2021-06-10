---
title: Visão geral dos detecção e resposta de ponto de extremidade recursos
ms.reviewer: ''
description: Saiba mais sobre os detecção e resposta de ponto de extremidade no Microsoft Defender para Ponto de Extremidade
keywords: Microsoft Defender para Ponto de Extremidade, detecção e resposta de ponto de extremidade, resposta, detecção, segurança cibernética, proteção
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b00bef611a3e4b33bf15a5366b09a96f68d4c1a2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933512"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="5df9a-104">Visão geral do detecção e resposta de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="5df9a-104">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5df9a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5df9a-105">**Applies to:**</span></span>
- [<span data-ttu-id="5df9a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5df9a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5df9a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5df9a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5df9a-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5df9a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5df9a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5df9a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5df9a-110">Os recursos do Defender for Endpoint detecção e resposta de ponto de extremidade fornecem detecções avançadas de ataque que são quase em tempo real e ativas.</span><span class="sxs-lookup"><span data-stu-id="5df9a-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="5df9a-111">Os analistas de segurança podem priorizar alertas de maneira eficaz, obter visibilidade de todo o escopo de uma violação e executar ações de resposta para remediar ameaças.</span><span class="sxs-lookup"><span data-stu-id="5df9a-111">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="5df9a-112">Quando uma ameaça é detectada, os alertas são criados no sistema para um analista investigar.</span><span class="sxs-lookup"><span data-stu-id="5df9a-112">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="5df9a-113">Alertas com as mesmas técnicas de ataque ou atribuídos ao mesmo invasor são agregados a uma entidade chamada de _incidente_.</span><span class="sxs-lookup"><span data-stu-id="5df9a-113">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="5df9a-114">Agregar alertas dessa maneira ajuda os analistas a investigar e responder a ameaças coletivamente.</span><span class="sxs-lookup"><span data-stu-id="5df9a-114">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="5df9a-115">Inspirado pela mentalidade de "assumir violação", o Defender for Endpoint coleta continuamente a telemetria cibernética comportamental.</span><span class="sxs-lookup"><span data-stu-id="5df9a-115">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="5df9a-116">Isso inclui informações sobre o processo, atividades de rede, óptica profunda no gerenciador de kernel e memória, atividades de logon do usuário, alterações no registro e no sistema de arquivos, e outras.</span><span class="sxs-lookup"><span data-stu-id="5df9a-116">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="5df9a-117">As informações são armazenadas por seis meses, permitindo que um analista volte no tempo até o início de um ataque.</span><span class="sxs-lookup"><span data-stu-id="5df9a-117">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="5df9a-118">O analista pode, então, girar em várias visualizações e pode abordar uma investigação por meio de vários vetores.</span><span class="sxs-lookup"><span data-stu-id="5df9a-118">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="5df9a-119">Os recursos de resposta permitem que você corrija imediatamente as ameaças, agindo sobre as entidades afetadas.</span><span class="sxs-lookup"><span data-stu-id="5df9a-119">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5df9a-120">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5df9a-120">Related topics</span></span>
- [<span data-ttu-id="5df9a-121">Painel de operações de segurança</span><span class="sxs-lookup"><span data-stu-id="5df9a-121">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="5df9a-122">Fila de incidentes</span><span class="sxs-lookup"><span data-stu-id="5df9a-122">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="5df9a-123">Fila de alertas</span><span class="sxs-lookup"><span data-stu-id="5df9a-123">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="5df9a-124">Lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="5df9a-124">Devices list</span></span>](machines-view-overview.md)

