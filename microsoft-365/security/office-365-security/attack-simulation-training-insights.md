---
title: Obter insights por meio do treinamento de simulação de Ataque
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Saiba como o treinamento de simulação de ataque no Microsoft 365 Security Center afeta os funcionários e obter informações sobre os resultados de simulação e treinamento.
ms.openlocfilehash: 772815add47d2e0a61187f2d687ff047a4de9c31
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615175"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="d9a51-103">Obter insights por meio do treinamento de simulação de Ataque</span><span class="sxs-lookup"><span data-stu-id="d9a51-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="d9a51-104">Dentro do treinamento de simulação de ataques, a Microsoft fornece ideias com base em resultados de simulações e funcionários de treinamento.</span><span class="sxs-lookup"><span data-stu-id="d9a51-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and training employees went through.</span></span> <span data-ttu-id="d9a51-105">Esses insights ajudarão você a informá-lo sobre o andamento que seus funcionários estão fazendo a prontidão da ameaça, bem como recomendam as próximas etapas para preparar melhor seus funcionários e seu ambiente para ataques.</span><span class="sxs-lookup"><span data-stu-id="d9a51-105">These insights will help inform you on progress your employees are doing on threat readiness, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d9a51-106">Estamos trabalhando continuamente na expansão de ideias disponíveis para você, com impacto de comportamento e ações recomendadas disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="d9a51-106">We are continuously working on expanding insights available to you, with behavior impact and recommended actions currently available.</span></span>
<span data-ttu-id="d9a51-107">Para começar, vá para [o treinamento de simulação de ataque na central de segurança do Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="d9a51-107">To start, head over to [Attack simulation training on the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="d9a51-108">Impacto do comportamento na taxa de comprometimento</span><span class="sxs-lookup"><span data-stu-id="d9a51-108">Behavior impact on compromise rate</span></span>

<span data-ttu-id="d9a51-109">Na guia **visão geral** do treinamento de simulação de ataque, você encontrará o **impacto do comportamento no cartão de Tarifa de comprometimento** .</span><span class="sxs-lookup"><span data-stu-id="d9a51-109">On the Attack simulation training **Overview** tab, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="d9a51-110">Este cartão mostra como os funcionários lidaram com a simulação que você executou em contraste com a **taxa de comprometimento prevista**.</span><span class="sxs-lookup"><span data-stu-id="d9a51-110">This card shows how employees dealt with simulation you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="d9a51-111">Você pode usar esses percepções para acompanhar o progresso da prontidão de ameaças dos funcionários, executando várias simulações em relação aos mesmos grupos de funcionários.</span><span class="sxs-lookup"><span data-stu-id="d9a51-111">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="d9a51-112">No gráfico, você pode ver:</span><span class="sxs-lookup"><span data-stu-id="d9a51-112">In the graph you can see:</span></span>

- <span data-ttu-id="d9a51-113">**Taxa de comprometimento prevista** que reflete a taxa de comprometimento média de simulações usando o mesmo tipo de carga entre locatários usando o treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="d9a51-113">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across tenants using Attack simulation training.</span></span>
- <span data-ttu-id="d9a51-114">**Taxa de comprometimento real** reflete a porcentagem de funcionários que foram desefetivados para a simulação.</span><span class="sxs-lookup"><span data-stu-id="d9a51-114">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="d9a51-115">Além disso, `<number> less susceptible to phishing` reflete a diferença entre o número real de funcionários comprometidos pelo ataque e a taxa de comprometimento prevista.</span><span class="sxs-lookup"><span data-stu-id="d9a51-115">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="d9a51-116">Esse número de funcionários é menos provável de ser comprometido por ataques similares no futuro, enquanto `<percent%> better than predicted rate` indica como os funcionários faziam o total em comparação com a taxa de comprometimento prevista.</span><span class="sxs-lookup"><span data-stu-id="d9a51-116">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d9a51-117">![Cartão de impacto de comportamento na simulação de ataque visão geral do treinamento](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="d9a51-117">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="d9a51-118">Para ver um relatório mais detalhado, clique em **Exibir simulações e o relatório de eficácia do treinamento** , que fornece as mesmas informações com contexto adicional da simulação, como técnica de simulação e total de usuários direcionados.</span><span class="sxs-lookup"><span data-stu-id="d9a51-118">To see a more detailed report, click on **View simulations and training efficacy report** which provides the same information with additional context from the simulation itself, like simulation technique and total users targeted.</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="d9a51-119">Ações recomendadas</span><span class="sxs-lookup"><span data-stu-id="d9a51-119">Recommended actions</span></span>

<span data-ttu-id="d9a51-120">Na guia [ **Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations), selecionando qualquer uma das simulações levará você para a simulação de detalhes.</span><span class="sxs-lookup"><span data-stu-id="d9a51-120">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting any of the simulations will take you to simulation details.</span></span> <span data-ttu-id="d9a51-121">Aqui, você encontrará a seção **ações recomendadas** .</span><span class="sxs-lookup"><span data-stu-id="d9a51-121">Here you will find the **Recommended actions** section.</span></span>

<span data-ttu-id="d9a51-122">A seção de ações recomendadas detalha as recomendações, conforme disponível na [Pontuação segura da Microsoft](../mtp/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="d9a51-122">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="d9a51-123">Essas recomendações são baseadas na carga usada na simulação e ajudarão você a proteger seus funcionários e seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9a51-123">These recommendations are based on the payload used in the simulation and will help you protect your employees and your environment.</span></span> <span data-ttu-id="d9a51-124">Ao clicar em cada ação de melhoria, você terá seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="d9a51-124">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d9a51-125">![Seção ações de recomendação no treinamento de simulação de ataque](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="d9a51-125">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="d9a51-126">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="d9a51-126">Related Links</span></span>

<span data-ttu-id="d9a51-127">**Simulador de ataque** [crie uma simulação de ataque de phishing](attack-simulation-training.md) e [crie uma carga para treinar suas pessoas](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="d9a51-127">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
