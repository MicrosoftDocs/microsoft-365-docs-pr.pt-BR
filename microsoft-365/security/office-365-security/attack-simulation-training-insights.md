---
title: Obter insights por meio do treinamento de simulação de Ataque
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Os administradores podem aprender como o treinamento de simulação de ataque no centro de segurança do Microsoft 365 afeta os funcionários e pode obter informações sobre os resultados de simulação e treinamento.
ms.openlocfilehash: 6fc109469f8a9a3cf6aa87e9b8f9e3a024fed6e3
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667584"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="345a9-103">Obter insights por meio do treinamento de simulação de Ataque</span><span class="sxs-lookup"><span data-stu-id="345a9-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="345a9-104">Dentro do treinamento de simulação de ataques, a Microsoft fornece ideias com base em resultados de simulações e treinamentos que os funcionários passaram.</span><span class="sxs-lookup"><span data-stu-id="345a9-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="345a9-105">Esses insights ajudarão você a se informar sobre o andamento da prontidão da ameaça de seus funcionários, além de recomendar as próximas etapas para preparar melhor seus funcionários e seu ambiente para ataques.</span><span class="sxs-lookup"><span data-stu-id="345a9-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="345a9-106">Estamos trabalhando continuamente para expandir os insights que estão disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="345a9-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="345a9-107">O impacto do comportamento e as ações recomendadas estão disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="345a9-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="345a9-108">Para começar, vá para [o treinamento de simulação de ataque no centro de segurança do Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="345a9-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="345a9-109">Impacto do comportamento na taxa de comprometimento</span><span class="sxs-lookup"><span data-stu-id="345a9-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="345a9-110">Na guia **visão geral** do treinamento de simulação de ataque, você encontrará o **impacto do comportamento no cartão de Tarifa de comprometimento** .</span><span class="sxs-lookup"><span data-stu-id="345a9-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="345a9-111">Este cartão mostra como os funcionários lidar com as simulações que você executou em comparação com a **taxa de comprometimento prevista**.</span><span class="sxs-lookup"><span data-stu-id="345a9-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="345a9-112">Você pode usar esses percepções para acompanhar o progresso da prontidão de ameaças dos funcionários, executando várias simulações em relação aos mesmos grupos de funcionários.</span><span class="sxs-lookup"><span data-stu-id="345a9-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="345a9-113">No gráfico, você pode ver:</span><span class="sxs-lookup"><span data-stu-id="345a9-113">In the graph you can see:</span></span>

- <span data-ttu-id="345a9-114">**Taxa de comprometimento prevista** que reflete a taxa de comprometimento média de simulações usando o mesmo tipo de carga em outros locatários do Microsoft 365 que usam o treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="345a9-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="345a9-115">**Taxa de comprometimento real** reflete a porcentagem de funcionários que foram desefetivados para a simulação.</span><span class="sxs-lookup"><span data-stu-id="345a9-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="345a9-116">Além disso, `<number> less susceptible to phishing` reflete a diferença entre o número real de funcionários comprometidos pelo ataque e a taxa de comprometimento prevista.</span><span class="sxs-lookup"><span data-stu-id="345a9-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="345a9-117">Esse número de funcionários é menos provável de ser comprometido por ataques similares no futuro, enquanto `<percent%> better than predicted rate` indica como os funcionários faziam o total em comparação com a taxa de comprometimento prevista.</span><span class="sxs-lookup"><span data-stu-id="345a9-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="345a9-118">![Cartão de impacto de comportamento na simulação de ataque visão geral do treinamento](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="345a9-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="345a9-119">Para ver um relatório mais detalhado, clique em **Exibir relatório de eficácia de simulações e treinamento**.</span><span class="sxs-lookup"><span data-stu-id="345a9-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="345a9-120">Este relatório fornece as mesmas informações com contexto adicional da simulação (por exemplo, técnica de simulação e total de usuários direcionados).</span><span class="sxs-lookup"><span data-stu-id="345a9-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="345a9-121">Ações recomendadas</span><span class="sxs-lookup"><span data-stu-id="345a9-121">Recommended actions</span></span>

<span data-ttu-id="345a9-122">Na guia [ **Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations), selecionando uma simulação o levará para os detalhes de simulação, onde você encontrará a seção **ações recomendadas** .</span><span class="sxs-lookup"><span data-stu-id="345a9-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="345a9-123">A seção de ações recomendadas detalha as recomendações, conforme disponível na [Pontuação segura da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="345a9-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="345a9-124">Essas recomendações são baseadas na carga usada na simulação e ajudarão você a proteger seus funcionários e seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="345a9-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="345a9-125">Ao clicar em cada ação de melhoria, você terá seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="345a9-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="345a9-126">![Seção ações de recomendação no treinamento de simulação de ataque](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="345a9-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="345a9-127">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="345a9-127">Related Links</span></span>

<span data-ttu-id="345a9-128">**Simulador de ataque** [crie uma simulação de ataque de phishing](attack-simulation-training.md) e [crie uma carga para treinar suas pessoas](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="345a9-128">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
