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
- m365initiative-defender-office365
description: Os administradores podem saber como o treinamento de simulação de ataque no centro de segurança do Microsoft 365 afeta os funcionários e pode obter informações sobre os resultados de simulação e treinamento.
ms.openlocfilehash: c283819550872691d8dd23d3921c22cb23637633
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870950"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="c3065-103">Obter insights por meio do treinamento de simulação de Ataque</span><span class="sxs-lookup"><span data-stu-id="c3065-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="c3065-104">No treinamento de simulação de ataques, a Microsoft fornece informações com base nos resultados de simulações e treinamentos que os funcionários passaram.</span><span class="sxs-lookup"><span data-stu-id="c3065-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="c3065-105">Essas informações ajudarão a mantê-lo informado sobre o progresso da prontidão contra ameaças de seus funcionários, bem como recomendará as próximas etapas para preparar melhor seus funcionários e seu ambiente para ataques.</span><span class="sxs-lookup"><span data-stu-id="c3065-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c3065-106">Estamos trabalhando continuamente para expandir as informações disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="c3065-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="c3065-107">O impacto no comportamento e as ações recomendadas estão disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="c3065-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="c3065-108">Para começar, vá para o treinamento [de simulação de ataque no centro de segurança do Microsoft 365.](https://security.microsoft.com/attacksimulator?viewid=overview)</span><span class="sxs-lookup"><span data-stu-id="c3065-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="c3065-109">Impacto do comportamento na taxa de comprometimento</span><span class="sxs-lookup"><span data-stu-id="c3065-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="c3065-110">Na guia **Visão geral do** treinamento de simulação de ataque, você encontrará o impacto do comportamento no cartão de taxa **de** comprometimento.</span><span class="sxs-lookup"><span data-stu-id="c3065-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="c3065-111">Este cartão mostra como os funcionários lidaram com as simulações que você fez em contraste com a taxa **de comprometimento prevista.**</span><span class="sxs-lookup"><span data-stu-id="c3065-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="c3065-112">Você pode usar essas informações para controlar o progresso da prontidão contra ameaças dos funcionários executando várias simulações nos mesmos grupos de funcionários.</span><span class="sxs-lookup"><span data-stu-id="c3065-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="c3065-113">No gráfico, você pode ver:</span><span class="sxs-lookup"><span data-stu-id="c3065-113">In the graph you can see:</span></span>

- <span data-ttu-id="c3065-114">**Taxa de** comprometimento prevista que reflete a taxa média de comprometimento para simulações usando o mesmo tipo de carga em outros locatários do Microsoft 365 que usam treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="c3065-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="c3065-115">**A taxa de comprometimento** real reflete a porcentagem de funcionários que ficaram inocentados para a simulação.</span><span class="sxs-lookup"><span data-stu-id="c3065-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="c3065-116">Além disso, reflete a diferença entre o número real de funcionários comprometidos pelo ataque e a `<number> less susceptible to phishing` taxa de comprometimento prevista.</span><span class="sxs-lookup"><span data-stu-id="c3065-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="c3065-117">É menos provável que esse número de funcionários seja comprometido por ataques semelhantes no futuro, enquanto indica como os funcionários fizeram em geral em contraste com a taxa de `<percent%> better than predicted rate` comprometimento prevista.</span><span class="sxs-lookup"><span data-stu-id="c3065-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c3065-118">![Visão geral do cartão de impacto do comportamento no treinamento de simulação de ataques](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="c3065-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="c3065-119">Para ver um relatório mais detalhado, clique em Exibir simulações **e relatório de treinamento.**</span><span class="sxs-lookup"><span data-stu-id="c3065-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="c3065-120">Esse relatório fornece as mesmas informações com contexto adicional da própria simulação (por exemplo, técnica de simulação e total de usuários direcionados).</span><span class="sxs-lookup"><span data-stu-id="c3065-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="c3065-121">Ações recomendadas</span><span class="sxs-lookup"><span data-stu-id="c3065-121">Recommended actions</span></span>

<span data-ttu-id="c3065-122">Na guia [ **Simulações,**](https://security.microsoft.com/attacksimulator?viewid=simulations)selecionar uma simulação levará você aos detalhes da simulação, onde você encontrará a **seção Ações recomendadas.**</span><span class="sxs-lookup"><span data-stu-id="c3065-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="c3065-123">A seção de ações recomendadas detalha as recomendações conforme disponíveis no [Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)</span><span class="sxs-lookup"><span data-stu-id="c3065-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="c3065-124">Essas recomendações são baseadas na carga usada na simulação e ajudarão você a proteger seus funcionários e seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c3065-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="c3065-125">Clicar em cada ação de melhoria levará você aos detalhes.</span><span class="sxs-lookup"><span data-stu-id="c3065-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c3065-126">![Seção de ações de recomendação sobre treinamento de simulação de ataque](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="c3065-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="c3065-127">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="c3065-127">Related Links</span></span>

[<span data-ttu-id="c3065-128">Começar a usar o treinamento de simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="c3065-128">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="c3065-129">Criar uma simulação de ataque de phishing</span><span class="sxs-lookup"><span data-stu-id="c3065-129">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="c3065-130">criar uma carga para treinar suas pessoas</span><span class="sxs-lookup"><span data-stu-id="c3065-130">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
