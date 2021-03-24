---
title: Visão geral dos recursos de detecção e resposta do ponto de extremidade
ms.reviewer: ''
description: Saiba mais sobre os recursos de detecção e resposta do ponto de extremidade no Microsoft Defender ATP
keywords: ''
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
ms.openlocfilehash: 858ea0f8d46ac2489dd6ef5c10caf2ce0879e4fb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054465"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="06852-103">Visão geral da detecção e resposta do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="06852-103">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="06852-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="06852-104">**Applies to:**</span></span>
- [<span data-ttu-id="06852-105">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="06852-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="06852-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06852-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="06852-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="06852-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06852-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="06852-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="06852-109">Os recursos de detecção e resposta de ponto de extremidade do Defender para pontos de extremidade fornecem detecções avançadas de ataque que são quase em tempo real e ativas.</span><span class="sxs-lookup"><span data-stu-id="06852-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="06852-110">Os analistas de segurança podem priorizar alertas de maneira eficaz, obter visibilidade de todo o escopo de uma violação e executar ações de resposta para remediar ameaças.</span><span class="sxs-lookup"><span data-stu-id="06852-110">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="06852-111">Quando uma ameaça é detectada, os alertas são criados no sistema para um analista investigar.</span><span class="sxs-lookup"><span data-stu-id="06852-111">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="06852-112">Alertas com as mesmas técnicas de ataque ou atribuídos ao mesmo invasor são agregados a uma entidade chamada de _incidente_.</span><span class="sxs-lookup"><span data-stu-id="06852-112">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="06852-113">Agregar alertas dessa maneira ajuda os analistas a investigar e responder a ameaças coletivamente.</span><span class="sxs-lookup"><span data-stu-id="06852-113">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="06852-114">Inspirado pela mentalidade de "assumir violação", o Defender for Endpoint coleta continuamente a telemetria cibernética comportamental.</span><span class="sxs-lookup"><span data-stu-id="06852-114">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="06852-115">Isso inclui informações sobre o processo, atividades de rede, óptica profunda no gerenciador de kernel e memória, atividades de logon do usuário, alterações no registro e no sistema de arquivos, e outras.</span><span class="sxs-lookup"><span data-stu-id="06852-115">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="06852-116">As informações são armazenadas por seis meses, permitindo que um analista volte no tempo até o início de um ataque.</span><span class="sxs-lookup"><span data-stu-id="06852-116">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="06852-117">O analista pode, então, girar em várias visualizações e pode abordar uma investigação por meio de vários vetores.</span><span class="sxs-lookup"><span data-stu-id="06852-117">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="06852-118">Os recursos de resposta permitem que você corrija imediatamente as ameaças, agindo sobre as entidades afetadas.</span><span class="sxs-lookup"><span data-stu-id="06852-118">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="06852-119">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="06852-119">Related topics</span></span>
- [<span data-ttu-id="06852-120">Painel de operações de segurança</span><span class="sxs-lookup"><span data-stu-id="06852-120">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="06852-121">Fila de incidentes</span><span class="sxs-lookup"><span data-stu-id="06852-121">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="06852-122">Fila de alertas</span><span class="sxs-lookup"><span data-stu-id="06852-122">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="06852-123">Lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="06852-123">Devices list</span></span>](machines-view-overview.md)

