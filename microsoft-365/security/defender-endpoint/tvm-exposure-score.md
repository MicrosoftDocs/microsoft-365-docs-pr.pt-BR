---
title: Pontuação de exposição no gerenciamento de ameaças e vulnerabilidades
description: A pontuação de exposição ao gerenciamento de ameaças e vulnerabilidades reflete como sua organização está vulnerável a ameaças de segurança cibernética.
keywords: pontuação de exposição, pontuação de exposição mdatp, pontuação de exposição de tvm mdatp, pontuação de exposição da organização, pontuação de exposição da organização de tvm, gerenciamento de ameaças e vulnerabilidades, Microsoft Defender para Ponto de Extremidade
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cc7abd678d6f2d317d02c4ed2b8028e7e270b055
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054457"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="73d39-104">Pontuação de exposição - gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="73d39-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73d39-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="73d39-105">**Applies to:**</span></span>

- [<span data-ttu-id="73d39-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="73d39-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="73d39-107">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="73d39-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="73d39-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73d39-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="73d39-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="73d39-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="73d39-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="73d39-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="73d39-111">Sua pontuação de exposição está visível no painel de gerenciamento de ameaças e [vulnerabilidades](tvm-dashboard-insights.md) do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="73d39-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="73d39-112">Ele reflete como sua organização está vulnerável a ameaças de segurança cibernética.</span><span class="sxs-lookup"><span data-stu-id="73d39-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="73d39-113">Baixa pontuação de exposição significa que seus dispositivos são menos vulneráveis de exploração.</span><span class="sxs-lookup"><span data-stu-id="73d39-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="73d39-114">Compreenda e identifique rapidamente as informações de alto nível sobre o estado de segurança em sua organização.</span><span class="sxs-lookup"><span data-stu-id="73d39-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="73d39-115">Detectar e responder a áreas que exigem investigação ou ação para melhorar o estado atual.</span><span class="sxs-lookup"><span data-stu-id="73d39-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="73d39-116">Comunicar-se com colegas e gerenciamento sobre o impacto dos esforços de segurança.</span><span class="sxs-lookup"><span data-stu-id="73d39-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="73d39-117">O cartão oferece uma exibição de alto nível da sua tendência de pontuação de exposição ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="73d39-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="73d39-118">Quaisquer picos no gráfico dão a você uma indicação visual de uma exposição de alta ameaça de segurança cibernética que você pode investigar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="73d39-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![Cartão de pontuação de exposição](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="73d39-120">Como funciona</span><span class="sxs-lookup"><span data-stu-id="73d39-120">How it works</span></span>

<span data-ttu-id="73d39-121">A pontuação de exposição é dividida nos seguintes níveis:</span><span class="sxs-lookup"><span data-stu-id="73d39-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="73d39-122">0 a 29: pontuação de baixa exposição</span><span class="sxs-lookup"><span data-stu-id="73d39-122">0–29: low exposure score</span></span>
- <span data-ttu-id="73d39-123">30 a 69: pontuação média de exposição</span><span class="sxs-lookup"><span data-stu-id="73d39-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="73d39-124">70 a 100: pontuação de alta exposição</span><span class="sxs-lookup"><span data-stu-id="73d39-124">70–100: high exposure score</span></span>

<span data-ttu-id="73d39-125">Você pode resolver os problemas com base em recomendações de [segurança priorizadas](tvm-security-recommendation.md) para reduzir a pontuação de exposição.</span><span class="sxs-lookup"><span data-stu-id="73d39-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="73d39-126">Cada software tem pontos fracos que são transformados em recomendações e priorizados com base no risco para a organização.</span><span class="sxs-lookup"><span data-stu-id="73d39-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="73d39-127">Reduzir sua exposição a ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="73d39-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="73d39-128">Reduza sua exposição a ameaças e vulnerabilidades ao remediar recomendações [de segurança.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="73d39-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="73d39-129">Faça o maior impacto na sua pontuação de exposição, remediando as principais recomendações de segurança, que podem ser exibidas no painel de gerenciamento de ameaças e [vulnerabilidades.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="73d39-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="73d39-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="73d39-130">Related topics</span></span>

- [<span data-ttu-id="73d39-131">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="73d39-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="73d39-132">Pontuação segura da Microsoft para dispositivos</span><span class="sxs-lookup"><span data-stu-id="73d39-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="73d39-133">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="73d39-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="73d39-134">Linha do tempo do evento</span><span class="sxs-lookup"><span data-stu-id="73d39-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)