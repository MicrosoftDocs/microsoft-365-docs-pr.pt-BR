---
title: Métodos e propriedades de pontuação
description: Recupera a pontuação de exposição da sua organização, a pontuação segura do dispositivo e a pontuação de exposição por grupo de dispositivos
keywords: apis, api gráfica, apis com suporte, pontuação, pontuação de exposição, pontuação segura do dispositivo, pontuação de exposição por grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200156"
---
# <a name="score-resource-type"></a><span data-ttu-id="95056-104">Tipo de recurso score</span><span class="sxs-lookup"><span data-stu-id="95056-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="95056-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="95056-105">**Applies to:**</span></span>
- [<span data-ttu-id="95056-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="95056-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="95056-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95056-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="95056-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="95056-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="95056-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="95056-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="95056-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="95056-110">Methods</span></span>

<span data-ttu-id="95056-111">Método</span><span class="sxs-lookup"><span data-stu-id="95056-111">Method</span></span> |<span data-ttu-id="95056-112">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="95056-112">Return Type</span></span> |<span data-ttu-id="95056-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="95056-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="95056-114">Obter pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="95056-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="95056-115">Score</span><span class="sxs-lookup"><span data-stu-id="95056-115">Score</span></span>](score.md) | <span data-ttu-id="95056-116">Obter a pontuação de exposição organizacional.</span><span class="sxs-lookup"><span data-stu-id="95056-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="95056-117">Obter pontuação segura do dispositivo</span><span class="sxs-lookup"><span data-stu-id="95056-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="95056-118">Score</span><span class="sxs-lookup"><span data-stu-id="95056-118">Score</span></span>](score.md) | <span data-ttu-id="95056-119">Obter a pontuação segura do dispositivo organizacional.</span><span class="sxs-lookup"><span data-stu-id="95056-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="95056-120">Listar pontuação de exposição por grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="95056-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="95056-121">Score</span><span class="sxs-lookup"><span data-stu-id="95056-121">Score</span></span>](score.md) | <span data-ttu-id="95056-122">Listar pontuações por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="95056-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="95056-123">Propriedades</span><span class="sxs-lookup"><span data-stu-id="95056-123">Properties</span></span>

<span data-ttu-id="95056-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="95056-124">Property</span></span> |  <span data-ttu-id="95056-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="95056-125">Type</span></span>    |   <span data-ttu-id="95056-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="95056-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="95056-127">Pontuação</span><span class="sxs-lookup"><span data-stu-id="95056-127">Score</span></span> | <span data-ttu-id="95056-128">Duplo</span><span class="sxs-lookup"><span data-stu-id="95056-128">Double</span></span> | <span data-ttu-id="95056-129">A pontuação atual.</span><span class="sxs-lookup"><span data-stu-id="95056-129">The current score.</span></span>
<span data-ttu-id="95056-130">Hora</span><span class="sxs-lookup"><span data-stu-id="95056-130">Time</span></span> | <span data-ttu-id="95056-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="95056-131">DateTime</span></span> | <span data-ttu-id="95056-132">A data e a hora em que a chamada para essa API foi feita.</span><span class="sxs-lookup"><span data-stu-id="95056-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="95056-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="95056-133">RbacGroupName</span></span> | <span data-ttu-id="95056-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="95056-134">String</span></span> | <span data-ttu-id="95056-135">O nome do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="95056-135">The device group name.</span></span>
