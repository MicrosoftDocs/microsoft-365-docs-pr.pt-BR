---
title: Treine um modelo de codificação preditiva Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: ''
ms.openlocfilehash: 84ec1ad42f2cec2487debe7160a3f24e09bdd830
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288186"
---
# <a name="train-a-predictive-coding-model-preview"></a><span data-ttu-id="a31de-102">Treinar um modelo de codificação preditiva (visualização)</span><span class="sxs-lookup"><span data-stu-id="a31de-102">Train a predictive coding model (preview)</span></span>

<span data-ttu-id="a31de-103">Depois de criar um modelo de codificação preditiva no Advanced eDiscovery, a próxima etapa é executar a primeira rodada de treinamento para treinar o modelo sobre o conteúdo relevante e não relevante no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="a31de-103">After you create a predictive coding model in Advanced eDiscovery, the next step is to performing the first training round to train the model on what is relevant and non-relevant content in your review set.</span></span> <span data-ttu-id="a31de-104">Depois de concluir a primeira rodada de treinamento, você pode realizar rodadas de treinamento subsequentes para melhorar a capacidade do modelo de prever conteúdo relevante e não relevante.</span><span class="sxs-lookup"><span data-stu-id="a31de-104">After you complete the first round of training, you can perform subsequent training rounds to improve the model's ability to predict relevant and non-relevant content.</span></span>

<span data-ttu-id="a31de-105">Para revisar o fluxo de trabalho de codificação preditivo, [consulte Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span><span class="sxs-lookup"><span data-stu-id="a31de-105">To review the predictive coding workflow, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span></span>

## <a name="before-you-train-a-model"></a><span data-ttu-id="a31de-106">Antes de treinar um modelo</span><span class="sxs-lookup"><span data-stu-id="a31de-106">Before you train a model</span></span>

- <span data-ttu-id="a31de-107">Durante uma rodada de treinamento, rotule itens como **Relevantes** ou **Não relevantes** com base na relevância do conteúdo no documento.</span><span class="sxs-lookup"><span data-stu-id="a31de-107">During a training round, label items as **Relevant** or **Not relevant** based on the relevancy of the content in the document.</span></span> <span data-ttu-id="a31de-108">Não basee sua decisão nos valores nos campos de metadados.</span><span class="sxs-lookup"><span data-stu-id="a31de-108">Don't base your decision on the values in the metadata fields.</span></span> <span data-ttu-id="a31de-109">Por exemplo, para mensagens de email ou Teams conversas, não basee sua decisão de rotulagem nos participantes da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a31de-109">For example, for email messages or Teams conversations, don't base your labeling decision on the message participants.</span></span>

## <a name="train-a-model-for-the-first-time"></a><span data-ttu-id="a31de-110">Treinar um modelo pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="a31de-110">Train a model for the first time</span></span>

1. <span data-ttu-id="a31de-111">Na Centro de conformidade do Microsoft 365, abra uma caixa Advanced eDiscovery e selecione a guia **Revisar conjuntos.**</span><span class="sxs-lookup"><span data-stu-id="a31de-111">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="a31de-112">Abra um conjunto de revisão e clique em **Análise**  >  **Gerenciar codificação preditiva (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="a31de-112">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

3. <span data-ttu-id="a31de-113">Na página **Modelos de codificação preditiva (visualização),** selecione o modelo que você deseja treinar.</span><span class="sxs-lookup"><span data-stu-id="a31de-113">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

4. <span data-ttu-id="a31de-114">Na guia **Visão** geral, em **Round 1**, clique **em Iniciar próxima rodada de treinamento.**</span><span class="sxs-lookup"><span data-stu-id="a31de-114">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="a31de-115">A **guia** Treinamento é exibida e contém 50 itens para você rotular.</span><span class="sxs-lookup"><span data-stu-id="a31de-115">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

5. <span data-ttu-id="a31de-116">Revise cada documento e selecione o botão **Relevante** ou **Não relevante** na parte inferior do painel de leitura para rotulá-lo.</span><span class="sxs-lookup"><span data-stu-id="a31de-116">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Rotular cada documento como relevante ou não relevante](..\media\TrainModel1.png)

6. <span data-ttu-id="a31de-118">Depois de rotular todos os 50 itens, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a31de-118">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="a31de-119">O sistema levará alguns minutos para "aprender" com a rotulagem e atualizar o modelo.</span><span class="sxs-lookup"><span data-stu-id="a31de-119">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="a31de-120">Quando esse processo é concluído, um status de **Ready** é exibido para o modelo na página Modelos de codificação preditiva **(visualização).**</span><span class="sxs-lookup"><span data-stu-id="a31de-120">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

## <a name="perform-additional-training-rounds"></a><span data-ttu-id="a31de-121">Executar rodadas de treinamento adicionais</span><span class="sxs-lookup"><span data-stu-id="a31de-121">Perform additional training rounds</span></span>

<span data-ttu-id="a31de-122">Depois de executar a primeira rodada de treinamento, você pode executar rodadas de treinamento subsequentes seguindo as etapas da seção anterior.</span><span class="sxs-lookup"><span data-stu-id="a31de-122">After you perform the first round of training, you can perform subsequent training rounds by following the steps in the previous section.</span></span> <span data-ttu-id="a31de-123">A única diferença é que o número da rodada de treinamento será atualizado na guia Visão geral **do** modelo. Por exemplo, depois de executar a primeira rodada de treinamento, você pode clicar em **Iniciar** a próxima rodada de treinamento para iniciar a segunda rodada de treinamento.</span><span class="sxs-lookup"><span data-stu-id="a31de-123">The only difference is the number of the training round will be updated on the model **Overview** tab. For example, after performing the first training round, you can click **Start next training round** to start the second round of training.</span></span> <span data-ttu-id="a31de-124">E assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a31de-124">And so on.</span></span>

<span data-ttu-id="a31de-125">Cada rodada de treinamento (as que estão em andamento e as que estão concluídas) é exibida na guia **Treinamento** para o modelo.</span><span class="sxs-lookup"><span data-stu-id="a31de-125">Each round of training (both those in progress and those that are complete) is displayed on the **Training** tab for the model.</span></span> <span data-ttu-id="a31de-126">Quando você seleciona uma rodada de treinamento, uma página de sobrevoo com informações e métricas para a rodada é exibida.</span><span class="sxs-lookup"><span data-stu-id="a31de-126">When you select a training round, a flyout page with information and metrics for the round is displayed.</span></span>

## <a name="what-happens-after-you-perform-a-training-round"></a><span data-ttu-id="a31de-127">O que acontece após a realização de uma rodada de treinamento</span><span class="sxs-lookup"><span data-stu-id="a31de-127">What happens after you perform a training round</span></span>

<span data-ttu-id="a31de-128">Depois de executar a primeira rodada de treinamento, é iniciado um trabalho que faz as seguintes coisas:</span><span class="sxs-lookup"><span data-stu-id="a31de-128">After you perform the first training round, a job is started that does the following things:</span></span>

- <span data-ttu-id="a31de-129">Com base na forma como você rotulou os 40 itens no conjunto de treinamento, o modelo aprende com sua rotulagem e se atualiza para se tornar mais preciso.</span><span class="sxs-lookup"><span data-stu-id="a31de-129">Based on how you labeled the 40 items in the training set, the model learns from your labeling and updates itself to become more accurate.</span></span>

- <span data-ttu-id="a31de-130">Em seguida, o modelo processa cada item em todo o conjunto de revisão e atribui uma pontuação de previsão entre **0** (não relevante) e **1** (relevante).</span><span class="sxs-lookup"><span data-stu-id="a31de-130">The model then processes each item in the entire review set and assigns a prediction score between **0** (not relevant) and **1** (relevant).</span></span>

- <span data-ttu-id="a31de-131">O modelo atribui uma pontuação de previsão aos 10 itens no conjunto de controle que você rotulou durante a rodada de treinamento.</span><span class="sxs-lookup"><span data-stu-id="a31de-131">The model assigns a prediction score to the 10 items in the control set that you labeled during the training round.</span></span> <span data-ttu-id="a31de-132">O modelo compara a pontuação de previsão desses 10 itens com o rótulo real atribuído ao item durante a rodada de treinamento.</span><span class="sxs-lookup"><span data-stu-id="a31de-132">The model compares the prediction score of these 10 items with the actual label that you assigned to the item during the training round.</span></span> <span data-ttu-id="a31de-133">Com base nessa comparação, o modelo identifica a seguinte classificação (chamada de matriz de confusão do conjunto de controle *)* para avaliar o desempenho de previsão do modelo:</span><span class="sxs-lookup"><span data-stu-id="a31de-133">Based on this comparison, the model identifies the following classification (called the *Control set confusion matrix*) to assess the model's prediction performance:</span></span>

  <br>

  ****

  |<span data-ttu-id="a31de-134">Rótulo</span><span class="sxs-lookup"><span data-stu-id="a31de-134">Label</span></span>|<span data-ttu-id="a31de-135">Modelo prevê que item é relevante</span><span class="sxs-lookup"><span data-stu-id="a31de-135">Model predicts item is relevant</span></span>|<span data-ttu-id="a31de-136">Modelo prevê item não é relevante</span><span class="sxs-lookup"><span data-stu-id="a31de-136">Model predicts item is not relevant</span></span>|
  |---|---|---|
  |<span data-ttu-id="a31de-137">**Item de rótulos do revistor como relevante**</span><span class="sxs-lookup"><span data-stu-id="a31de-137">**Reviewer labels item as relevant**</span></span>|<span data-ttu-id="a31de-138">Verdadeiro positivo</span><span class="sxs-lookup"><span data-stu-id="a31de-138">True positive</span></span>|<span data-ttu-id="a31de-139">Falso positivo</span><span class="sxs-lookup"><span data-stu-id="a31de-139">False positive</span></span>|
  |<span data-ttu-id="a31de-140">**Item rótulos do revistor como não relevante**</span><span class="sxs-lookup"><span data-stu-id="a31de-140">**Reviewer labels item as not relevant**</span></span>|<span data-ttu-id="a31de-141">Falso negativo</span><span class="sxs-lookup"><span data-stu-id="a31de-141">False negative</span></span>|<span data-ttu-id="a31de-142">Verdadeiro negativo</span><span class="sxs-lookup"><span data-stu-id="a31de-142">True negative</span></span>|
  |

  <span data-ttu-id="a31de-143">Com base nessas comparações, o modelo deriva valores para as métricas de pontuação F, precisão e recall e a margem de erro para cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="a31de-143">Based on these comparisons, the model derives values for the F-score, precision, and recall metrics and the margin of error for each one.</span></span> <span data-ttu-id="a31de-144">As pontuações dessas métricas de desempenho do modelo são exibidas em uma página de sobrevoo para a rodada de treinamento.</span><span class="sxs-lookup"><span data-stu-id="a31de-144">Scores for these model performance metrics are displayed on a flyout page for the training round.</span></span> <span data-ttu-id="a31de-145">Para uma descrição dessas métricas, consulte [Referência de codificação preditiva](predictive-coding-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a31de-145">For a description of these metrics, see [Predictive coding reference](predictive-coding-reference.md).</span></span>

- <span data-ttu-id="a31de-146">Por fim, o modelo determina os próximos 50 itens que serão usados para a próxima rodada de treinamento.</span><span class="sxs-lookup"><span data-stu-id="a31de-146">Finally, the model determines the next 50 items that will be used for the next training round.</span></span> <span data-ttu-id="a31de-147">Dessa vez, o modelo pode selecionar 20 itens do conjunto de controle e 30 novos itens do conjunto de revisão e designá-los como o conjunto de treinamento para a próxima rodada.</span><span class="sxs-lookup"><span data-stu-id="a31de-147">This time, the model might select 20 items from the control set and 30 new items from the review set and designate them as the training set for the next round.</span></span> <span data-ttu-id="a31de-148">A amostragem da próxima rodada de treinamento não é amostrada uniformemente.</span><span class="sxs-lookup"><span data-stu-id="a31de-148">The sampling for the next training round is not uniformly sampled.</span></span> <span data-ttu-id="a31de-149">O modelo otimizará a seleção de amostragem de itens do conjunto de revisão para selecionar itens onde a previsão é ambígua, o que significa que a pontuação de previsão está no intervalo de 0,5.</span><span class="sxs-lookup"><span data-stu-id="a31de-149">The model will optimize the sampling selection of items from the review set to select items where the prediction is ambiguous, which means the prediction score is in the 0.5 range.</span></span> <span data-ttu-id="a31de-150">Esse processo é conhecido como *seleção parcial.*</span><span class="sxs-lookup"><span data-stu-id="a31de-150">This process is known as *biased selection*.</span></span>

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a><span data-ttu-id="a31de-151">O que acontece após a realização de rodadas de treinamento subsequentes</span><span class="sxs-lookup"><span data-stu-id="a31de-151">What happens after you perform subsequent training rounds</span></span>

<span data-ttu-id="a31de-152">Depois de executar as rodadas de treinamento subsequentes (após a primeira rodada de treinamento), o modelo faz as seguintes coisas:</span><span class="sxs-lookup"><span data-stu-id="a31de-152">After you perform subsequent training rounds (after the first training round), the model does the following things:</span></span>

- <span data-ttu-id="a31de-153">O modelo é atualizado com base nos rótulos que você aplicou ao conjunto de treinamento nessa rodada de treinamento.</span><span class="sxs-lookup"><span data-stu-id="a31de-153">The model is updated based on the labels that you applied to the training set in that round of training.</span></span>

- <span data-ttu-id="a31de-154">O sistema avalia a pontuação de previsão do modelo nos itens no conjunto de controle e verifica se a pontuação se alinha com a forma como você rotulou itens no conjunto de controles.</span><span class="sxs-lookup"><span data-stu-id="a31de-154">The system evaluates the model's prediction score on the items in the control set and check whether the score aligns with how you labeled items in the control set.</span></span> <span data-ttu-id="a31de-155">A avaliação é realizada em todos os itens rotulados do conjunto de controle para todas as rodadas de treinamento.</span><span class="sxs-lookup"><span data-stu-id="a31de-155">The evaluation is performed on all labeled items from control set for all training rounds.</span></span> <span data-ttu-id="a31de-156">Os resultados dessa avaliação são incorporados no painel na guia **Visão** geral do modelo.</span><span class="sxs-lookup"><span data-stu-id="a31de-156">The results of this evaluation are incorporated in the dashboard on the **Overview** tab for the model.</span></span>

- <span data-ttu-id="a31de-157">O modelo atualizado reprocessa cada item no conjunto de revisão e atribui a cada item uma pontuação de previsão atualizada.</span><span class="sxs-lookup"><span data-stu-id="a31de-157">The updated model reprocesses every item in the review set and assign each item an updated prediction score.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a31de-158">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a31de-158">Next steps</span></span>

<span data-ttu-id="a31de-159">Depois de executar a primeira rodada de treinamento, você pode executar mais rodadas de treinamento ou aplicar o filtro de pontuação de previsão do modelo ao conjunto de revisão para exibir os itens que o modelo previu como relevantes ou não relevantes.</span><span class="sxs-lookup"><span data-stu-id="a31de-159">After you perform the first training round, you can perform more training rounds or apply the model's prediction score filter to the review set to view the items the model has predicted as relevant or not relevant.</span></span> <span data-ttu-id="a31de-160">Para obter mais informações, [consulte Aplicar um filtro de pontuação de previsão a um conjunto de revisão](predictive-coding-apply-prediction-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a31de-160">For more information, see [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>
