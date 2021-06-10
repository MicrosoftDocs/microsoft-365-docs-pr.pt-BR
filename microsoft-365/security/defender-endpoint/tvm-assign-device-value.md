---
title: Atribuir valor de dispositivo - Gerenciamento de Ameaças e Vulnerabilidades
description: Saiba como atribuir um valor baixo, normal ou alto a um dispositivo para ajudá-lo a diferenciar entre prioridades de ativos.
keywords: Valor do dispositivo Do Microsoft Defender para Ponto de Extremidade, Gerenciamento de Ameaças e Vulnerabilidades de dispositivo, dispositivos de alto valor, pontuação de exposição do valor do dispositivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935192"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="68ad8-104">Atribuir valor de dispositivo - Gerenciamento de Ameaças e Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="68ad8-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68ad8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="68ad8-105">**Applies to:**</span></span>

- [<span data-ttu-id="68ad8-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="68ad8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="68ad8-107">Ameaça e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="68ad8-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="68ad8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68ad8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="68ad8-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="68ad8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="68ad8-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="68ad8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="68ad8-111">Definir o valor de um dispositivo ajuda você a diferenciar entre prioridades de ativos.</span><span class="sxs-lookup"><span data-stu-id="68ad8-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="68ad8-112">O valor do dispositivo é usado para incorporar o desejo de risco de um ativo individual ao cálculo Gerenciamento de Ameaças e Vulnerabilidades de pontuação de exposição.</span><span class="sxs-lookup"><span data-stu-id="68ad8-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="68ad8-113">Os dispositivos atribuídos como "alto valor" receberão mais peso.</span><span class="sxs-lookup"><span data-stu-id="68ad8-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="68ad8-114">Você também pode usar a [API de valor de dispositivo definido.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="68ad8-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="68ad8-115">Opções de valor do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="68ad8-115">Device value options:</span></span>

- <span data-ttu-id="68ad8-116">Baixo</span><span class="sxs-lookup"><span data-stu-id="68ad8-116">Low</span></span>
- <span data-ttu-id="68ad8-117">Normal (padrão)</span><span class="sxs-lookup"><span data-stu-id="68ad8-117">Normal (Default)</span></span>
- <span data-ttu-id="68ad8-118">Alto</span><span class="sxs-lookup"><span data-stu-id="68ad8-118">High</span></span>

<span data-ttu-id="68ad8-119">Exemplos de dispositivos que devem ser atribuídos a um valor alto:</span><span class="sxs-lookup"><span data-stu-id="68ad8-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="68ad8-120">Controladores de domínio, Active Directory</span><span class="sxs-lookup"><span data-stu-id="68ad8-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="68ad8-121">Dispositivos voltados para a Internet</span><span class="sxs-lookup"><span data-stu-id="68ad8-121">Internet facing devices</span></span>
- <span data-ttu-id="68ad8-122">Dispositivos VIP</span><span class="sxs-lookup"><span data-stu-id="68ad8-122">VIP devices</span></span>
- <span data-ttu-id="68ad8-123">Dispositivos que hospedam serviços de produção internos/externos</span><span class="sxs-lookup"><span data-stu-id="68ad8-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="68ad8-124">Escolher o valor do dispositivo</span><span class="sxs-lookup"><span data-stu-id="68ad8-124">Choose device value</span></span>

1. <span data-ttu-id="68ad8-125">Navegue até qualquer página de dispositivo, o local mais fácil é a partir do inventário de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="68ad8-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="68ad8-126">Selecione **Valor de dispositivo** de três pontos ao lado da barra de ações na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="68ad8-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Exemplo do menu suspenso valor do dispositivo.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="68ad8-128">Um flyout aparecerá com o valor do dispositivo atual e o que ele significa.</span><span class="sxs-lookup"><span data-stu-id="68ad8-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="68ad8-129">Revise o valor do dispositivo e escolha o que melhor se encaixa em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68ad8-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="68ad8-130">![Exemplo do flyout do valor do dispositivo.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="68ad8-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="68ad8-131">Como o valor do dispositivo afeta sua pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="68ad8-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="68ad8-132">A pontuação de exposição é uma média ponderada em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="68ad8-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="68ad8-133">Se você tiver grupos de dispositivos, também poderá filtrar a pontuação por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="68ad8-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="68ad8-134">Dispositivos normais têm um peso de 1</span><span class="sxs-lookup"><span data-stu-id="68ad8-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="68ad8-135">Dispositivos de baixo valor têm um peso de 0,75</span><span class="sxs-lookup"><span data-stu-id="68ad8-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="68ad8-136">Dispositivos de alto valor têm um peso de NumberOfAssets / 10.</span><span class="sxs-lookup"><span data-stu-id="68ad8-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="68ad8-137">Se você tiver 100 dispositivos, cada dispositivo de alto valor terá um peso de 10 (100/10)</span><span class="sxs-lookup"><span data-stu-id="68ad8-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="68ad8-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="68ad8-138">Related topics</span></span>

- [<span data-ttu-id="68ad8-139">Visão geral Gerenciamento de Vulnerabilidades ameaça</span><span class="sxs-lookup"><span data-stu-id="68ad8-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="68ad8-140">Pontuação de Exposição</span><span class="sxs-lookup"><span data-stu-id="68ad8-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="68ad8-141">APIs</span><span class="sxs-lookup"><span data-stu-id="68ad8-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)