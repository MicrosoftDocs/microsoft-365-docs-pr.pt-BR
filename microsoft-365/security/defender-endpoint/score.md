---
title: Métodos e propriedades de pontuação
description: Recupera a pontuação de exposição da sua organização, a pontuação segura do dispositivo e a pontuação de exposição por grupo de dispositivos
keywords: apis, api gráfica, apis com suporte, pontuação, pontuação de exposição, pontuação segura do dispositivo, pontuação de exposição por grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771424"
---
# <a name="score-resource-type"></a><span data-ttu-id="d80c8-104">Tipo de recurso score</span><span class="sxs-lookup"><span data-stu-id="d80c8-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d80c8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d80c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="d80c8-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d80c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d80c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d80c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d80c8-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d80c8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d80c8-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d80c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="d80c8-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="d80c8-110">Methods</span></span>

<span data-ttu-id="d80c8-111">Método</span><span class="sxs-lookup"><span data-stu-id="d80c8-111">Method</span></span> |<span data-ttu-id="d80c8-112">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="d80c8-112">Return Type</span></span> |<span data-ttu-id="d80c8-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="d80c8-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="d80c8-114">Obter pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="d80c8-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="d80c8-115">Pontuação</span><span class="sxs-lookup"><span data-stu-id="d80c8-115">Score</span></span>](score.md) | <span data-ttu-id="d80c8-116">Obter a pontuação de exposição organizacional.</span><span class="sxs-lookup"><span data-stu-id="d80c8-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="d80c8-117">Obter pontuação segura do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d80c8-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="d80c8-118">Pontuação</span><span class="sxs-lookup"><span data-stu-id="d80c8-118">Score</span></span>](score.md) | <span data-ttu-id="d80c8-119">Obter a pontuação segura do dispositivo organizacional.</span><span class="sxs-lookup"><span data-stu-id="d80c8-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="d80c8-120">Listar pontuação de exposição por grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d80c8-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="d80c8-121">Pontuação</span><span class="sxs-lookup"><span data-stu-id="d80c8-121">Score</span></span>](score.md) | <span data-ttu-id="d80c8-122">Listar pontuações por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d80c8-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="d80c8-123">Propriedades</span><span class="sxs-lookup"><span data-stu-id="d80c8-123">Properties</span></span>

<span data-ttu-id="d80c8-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="d80c8-124">Property</span></span> |  <span data-ttu-id="d80c8-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="d80c8-125">Type</span></span>    |   <span data-ttu-id="d80c8-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="d80c8-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="d80c8-127">Pontuação</span><span class="sxs-lookup"><span data-stu-id="d80c8-127">Score</span></span> | <span data-ttu-id="d80c8-128">Duplo</span><span class="sxs-lookup"><span data-stu-id="d80c8-128">Double</span></span> | <span data-ttu-id="d80c8-129">A pontuação atual.</span><span class="sxs-lookup"><span data-stu-id="d80c8-129">The current score.</span></span>
<span data-ttu-id="d80c8-130">Time</span><span class="sxs-lookup"><span data-stu-id="d80c8-130">Time</span></span> | <span data-ttu-id="d80c8-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="d80c8-131">DateTime</span></span> | <span data-ttu-id="d80c8-132">A data e a hora em que a chamada para essa API foi feita.</span><span class="sxs-lookup"><span data-stu-id="d80c8-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="d80c8-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="d80c8-133">RbacGroupName</span></span> | <span data-ttu-id="d80c8-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d80c8-134">String</span></span> | <span data-ttu-id="d80c8-135">O nome do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d80c8-135">The device group name.</span></span>
