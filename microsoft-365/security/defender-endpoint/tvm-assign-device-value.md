---
title: Atribuir valor de dispositivo - gerenciamento de ameaças e vulnerabilidades
description: Saiba como atribuir um valor baixo, normal ou alto a um dispositivo para ajudá-lo a diferenciar entre prioridades de ativos.
keywords: Valor do dispositivo microsoft defender atp, valor do dispositivo de gerenciamento de ameaças e vulnerabilidades, dispositivos de alto valor, pontuação de exposição do valor do dispositivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: be578158e18d55bb25d450749c3fb4373854456b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053844"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="5d6d9-104">Atribuir valor de dispositivo - gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="5d6d9-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d6d9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5d6d9-105">**Applies to:**</span></span>

- [<span data-ttu-id="5d6d9-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5d6d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5d6d9-107">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="5d6d9-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5d6d9-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d6d9-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5d6d9-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5d6d9-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5d6d9-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5d6d9-111">Definir o valor de um dispositivo ajuda você a diferenciar entre prioridades de ativos.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="5d6d9-112">O valor do dispositivo é usado para incorporar o desejo de risco de um ativo individual ao cálculo de pontuação de exposição de gerenciamento de ameaças e vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="5d6d9-113">Os dispositivos atribuídos como "alto valor" receberão mais peso.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="5d6d9-114">Você também pode usar a [API de valor de dispositivo definido.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="5d6d9-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="5d6d9-115">Opções de valor do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="5d6d9-115">Device value options:</span></span>

- <span data-ttu-id="5d6d9-116">Baixo</span><span class="sxs-lookup"><span data-stu-id="5d6d9-116">Low</span></span>
- <span data-ttu-id="5d6d9-117">Normal (padrão)</span><span class="sxs-lookup"><span data-stu-id="5d6d9-117">Normal (Default)</span></span>
- <span data-ttu-id="5d6d9-118">Alto</span><span class="sxs-lookup"><span data-stu-id="5d6d9-118">High</span></span>

<span data-ttu-id="5d6d9-119">Exemplos de dispositivos que devem ser atribuídos a um valor alto:</span><span class="sxs-lookup"><span data-stu-id="5d6d9-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="5d6d9-120">Controladores de domínio, Active Directory</span><span class="sxs-lookup"><span data-stu-id="5d6d9-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="5d6d9-121">Dispositivos voltados para a Internet</span><span class="sxs-lookup"><span data-stu-id="5d6d9-121">Internet facing devices</span></span>
- <span data-ttu-id="5d6d9-122">Dispositivos VIP</span><span class="sxs-lookup"><span data-stu-id="5d6d9-122">VIP devices</span></span>
- <span data-ttu-id="5d6d9-123">Dispositivos que hospedam serviços de produção internos/externos</span><span class="sxs-lookup"><span data-stu-id="5d6d9-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="5d6d9-124">Escolher o valor do dispositivo</span><span class="sxs-lookup"><span data-stu-id="5d6d9-124">Choose device value</span></span>

1. <span data-ttu-id="5d6d9-125">Navegue até qualquer página de dispositivo, o local mais fácil é a partir do inventário de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="5d6d9-126">Selecione **Valor de dispositivo** de três pontos ao lado da barra de ações na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Exemplo do menu suspenso valor do dispositivo.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="5d6d9-128">Um flyout aparecerá com o valor do dispositivo atual e o que ele significa.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="5d6d9-129">Revise o valor do dispositivo e escolha o que melhor se encaixa em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="5d6d9-130">![Exemplo do flyout do valor do dispositivo.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="5d6d9-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="5d6d9-131">Como o valor do dispositivo afeta sua pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="5d6d9-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="5d6d9-132">A pontuação de exposição é uma média ponderada em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="5d6d9-133">Se você tiver grupos de dispositivos, também poderá filtrar a pontuação por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="5d6d9-134">Dispositivos normais têm um peso de 1</span><span class="sxs-lookup"><span data-stu-id="5d6d9-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="5d6d9-135">Dispositivos de baixo valor têm um peso de 0,75</span><span class="sxs-lookup"><span data-stu-id="5d6d9-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="5d6d9-136">Dispositivos de alto valor têm um peso de NumberOfAssets / 10.</span><span class="sxs-lookup"><span data-stu-id="5d6d9-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="5d6d9-137">Se você tiver 100 dispositivos, cada dispositivo de alto valor terá um peso de 10 (100/10)</span><span class="sxs-lookup"><span data-stu-id="5d6d9-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d6d9-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5d6d9-138">Related topics</span></span>

- [<span data-ttu-id="5d6d9-139">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="5d6d9-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5d6d9-140">Pontuação de Exposição</span><span class="sxs-lookup"><span data-stu-id="5d6d9-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="5d6d9-141">APIs</span><span class="sxs-lookup"><span data-stu-id="5d6d9-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)