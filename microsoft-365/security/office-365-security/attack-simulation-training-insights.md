---
title: Obter insights por meio do treinamento de simulação de Ataque
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem aprender como o treinamento de simulação de ataque no portal do Microsoft 365 Defender afeta os funcionários e podem obter informações sobre resultados de simulação e treinamento.
ms.technology: mdo
ms.openlocfilehash: e189864a42d025bb5ce720a6edb6c1c2c8c84623
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878371"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="55d9c-103">Obter insights por meio do treinamento de simulação de Ataque</span><span class="sxs-lookup"><span data-stu-id="55d9c-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="55d9c-104">**Aplica-se ao** [Microsoft Defender para Office 365 plano 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="55d9c-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="55d9c-105">No treinamento de simulação de ataque, a Microsoft fornece informações com base nos resultados de simulações e treinamentos pelos funcionários.</span><span class="sxs-lookup"><span data-stu-id="55d9c-105">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="55d9c-106">Essas informações ajudarão a mantê-lo informado sobre o progresso da preparação de ameaças de seus funcionários, bem como recomendar as próximas etapas para preparar melhor seus funcionários e seu ambiente para ataques.</span><span class="sxs-lookup"><span data-stu-id="55d9c-106">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

<span data-ttu-id="55d9c-107">Estamos trabalhando continuamente para expandir as percepções que estão disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="55d9c-107">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="55d9c-108">O impacto no comportamento e as ações recomendadas estão disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="55d9c-108">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="55d9c-109">Para começar, vá para Treinamento [de simulação de ataque no portal Microsoft 365 Defender.](https://security.microsoft.com/attacksimulator?viewid=overview)</span><span class="sxs-lookup"><span data-stu-id="55d9c-109">To start, head over to [Attack simulation training in the Microsoft 365 Defender portal](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="55d9c-110">Impacto de comportamento na taxa de comprometimento</span><span class="sxs-lookup"><span data-stu-id="55d9c-110">Behavior impact on compromise rate</span></span>

<span data-ttu-id="55d9c-111">Na guia **Visão geral** do treinamento de simulação de ataque, você encontrará o impacto do comportamento no cartão de **taxa de** comprometimento.</span><span class="sxs-lookup"><span data-stu-id="55d9c-111">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="55d9c-112">Este cartão mostra como os funcionários lidavam com as simulações que você fez em contraste com a taxa **de comprometimento prevista.**</span><span class="sxs-lookup"><span data-stu-id="55d9c-112">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="55d9c-113">Você pode usar essas informações para acompanhar o progresso na preparação de ameaças de funcionários executando várias simulações nos mesmos grupos de funcionários.</span><span class="sxs-lookup"><span data-stu-id="55d9c-113">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="55d9c-114">No gráfico, você pode ver:</span><span class="sxs-lookup"><span data-stu-id="55d9c-114">In the graph you can see:</span></span>

- <span data-ttu-id="55d9c-115">**Taxa de comprometimento prevista** que reflete a taxa média de comprometimento para simulações usando o mesmo tipo de carga em outros locatários Microsoft 365 que usam treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="55d9c-115">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="55d9c-116">**A taxa de comprometimento real** reflete a porcentagem de funcionários que caiu na simulação.</span><span class="sxs-lookup"><span data-stu-id="55d9c-116">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="55d9c-117">Além disso, reflete a diferença entre o número real de funcionários comprometidos pelo ataque e a taxa `<number> less susceptible to phishing` de comprometimento prevista.</span><span class="sxs-lookup"><span data-stu-id="55d9c-117">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="55d9c-118">Esse número de funcionários é menos provável de ser comprometido por ataques semelhantes no futuro, enquanto indica como os funcionários fizeram em geral, em contraste com a taxa de comprometimento `<percent%> better than predicted rate` prevista.</span><span class="sxs-lookup"><span data-stu-id="55d9c-118">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="55d9c-119">![Cartão de impacto de comportamento na visão geral do treinamento de simulação de ataque](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="55d9c-119">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="55d9c-120">Para ver um relatório mais detalhado, clique em **Exibir simulações e relatório** de eficácia de treinamento.</span><span class="sxs-lookup"><span data-stu-id="55d9c-120">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="55d9c-121">Este relatório fornece as mesmas informações com contexto adicional da própria simulação (por exemplo, a técnica de simulação e o total de usuários direcionados).</span><span class="sxs-lookup"><span data-stu-id="55d9c-121">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="55d9c-122">Ações recomendadas</span><span class="sxs-lookup"><span data-stu-id="55d9c-122">Recommended actions</span></span>

<span data-ttu-id="55d9c-123">Na guia [ **Simulações,**](https://security.microsoft.com/attacksimulator?viewid=simulations)selecionar uma simulação levará você aos detalhes da simulação, onde você encontrará a **seção Ações recomendadas.**</span><span class="sxs-lookup"><span data-stu-id="55d9c-123">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="55d9c-124">A seção ações recomendadas detalha as recomendações conforme disponível na [Pontuação Segura da Microsoft.](../defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="55d9c-124">The recommended actions section details recommendations as available in [Microsoft Secure Score](../defender/microsoft-secure-score.md).</span></span> <span data-ttu-id="55d9c-125">Essas recomendações se baseiam na carga usada na simulação e ajudarão você a proteger seus funcionários e seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="55d9c-125">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="55d9c-126">Clicar em cada ação de melhoria levará você aos detalhes.</span><span class="sxs-lookup"><span data-stu-id="55d9c-126">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="55d9c-127">![Seção Ações de recomendação no treinamento de simulação de ataque](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="55d9c-127">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="55d9c-128">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="55d9c-128">Related Links</span></span>

[<span data-ttu-id="55d9c-129">Começar a usar o Treinamento de simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="55d9c-129">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="55d9c-130">Criar uma simulação de ataque de phishing</span><span class="sxs-lookup"><span data-stu-id="55d9c-130">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="55d9c-131">criar uma carga para treinar suas pessoas</span><span class="sxs-lookup"><span data-stu-id="55d9c-131">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
