---
title: Codificação preditiva em Advanced eDiscovery - Início rápido
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
description: Saiba como começar a usar o módulo de codificação preditiva Advanced eDiscovery. Este artigo orienta você sobre o processo de ponta a ponta do uso da codificação preditiva para identificar conteúdo em um conjunto de revisão mais relevante para sua investigação.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822470"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="671a9-104">Início rápido: codificação preditiva no Advanced eDiscovery (visualização)</span><span class="sxs-lookup"><span data-stu-id="671a9-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="671a9-105">Este artigo apresenta um início rápido para o uso da codificação preditiva Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="671a9-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="671a9-106">O módulo de codificação preditiva no Advanced eDiscovery usa os recursos inteligentes de aprendizado de máquina no Advanced eDiscovery para ajudá-lo a reduzir a quantidade de conteúdo a ser revisado.</span><span class="sxs-lookup"><span data-stu-id="671a9-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="671a9-107">A codificação preditiva ajuda você a reduzir e a reduzir grandes volumes de conteúdo de caso para um conjunto relevante de itens que você pode priorizar para revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="671a9-108">Isso é feito criando e treinando seus próprios modelos de codificação preditivos que ajudam você a priorizar a revisão dos itens mais relevantes em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="671a9-109">Aqui está uma visão geral rápida do processo de codificação preditiva:</span><span class="sxs-lookup"><span data-stu-id="671a9-109">Here's an a quick overview of the predictive coding process:</span></span>

![Processo de início rápido para codificação de previsão](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="671a9-111">Para começar, crie um modelo, rotule até 50 itens como relevantes ou não relevantes.</span><span class="sxs-lookup"><span data-stu-id="671a9-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="671a9-112">Em seguida, o sistema usa esse treinamento para aplicar pontuações de previsão a cada item no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="671a9-113">Isso permite filtrar itens com base na pontuação de previsão, o que permite que você revise primeiro os itens mais relevantes (ou não relevantes).</span><span class="sxs-lookup"><span data-stu-id="671a9-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="671a9-114">Se você quiser treinar modelos com maiores precisões e taxas de recall, poderá continuar rotulando itens em rodadas de treinamento subsequentes até que o modelo se estabiliza.</span><span class="sxs-lookup"><span data-stu-id="671a9-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="671a9-115">Depois que o modelo for estabilizado, você poderá aplicar o filtro de previsão final para priorizar itens para revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="671a9-116">Para uma visão geral detalhada da codificação preditiva, consulte [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="671a9-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="671a9-117">Etapa 1: Criar um novo modelo de codificação preditiva</span><span class="sxs-lookup"><span data-stu-id="671a9-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="671a9-118">A primeira etapa é criar um novo modelo de codificação preditiva no conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="671a9-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="671a9-119">No centro Microsoft 365 de conformidade, abra uma caixa Advanced eDiscovery e selecione a guia **Revisar conjuntos.**</span><span class="sxs-lookup"><span data-stu-id="671a9-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="671a9-120">Abra um conjunto de revisão e clique em **Análise**  >  **Gerenciar codificação preditiva (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="671a9-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![Clique no menu suspenso Analisar no conjunto de revisão para ir para a página codificação preditiva](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="671a9-122">Na página **Modelos de codificação preditiva (visualização),** clique **em Novo modelo**.</span><span class="sxs-lookup"><span data-stu-id="671a9-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="671a9-123">Na página de sobrevoo, digite um nome para o modelo e uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="671a9-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="671a9-124">Clique **em Salvar** para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="671a9-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="671a9-125">O sistema levará alguns minutos para preparar seu modelo.</span><span class="sxs-lookup"><span data-stu-id="671a9-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="671a9-126">Depois que estiver pronto, você poderá executar a primeira rodada de treinamento.</span><span class="sxs-lookup"><span data-stu-id="671a9-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="671a9-127">Para obter instruções mais detalhadas, consulte [Create a predictive coding model](predictive-coding-create-model.md).</span><span class="sxs-lookup"><span data-stu-id="671a9-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="671a9-128">Etapa 2: Executar a primeira rodada de treinamento</span><span class="sxs-lookup"><span data-stu-id="671a9-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="671a9-129">Depois de criar o modelo, a próxima etapa é concluir a primeira rodada de treinamento rotulando itens como relevantes ou não relevantes.</span><span class="sxs-lookup"><span data-stu-id="671a9-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="671a9-130">Abra o conjunto de revisão e clique em **Análise**  >  **Gerenciar codificação preditiva (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="671a9-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="671a9-131">Na página **Modelos de codificação preditiva (visualização),** selecione o modelo que você deseja treinar.</span><span class="sxs-lookup"><span data-stu-id="671a9-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="671a9-132">Na guia **Visão** geral, em **Round 1**, clique **em Iniciar próxima rodada de treinamento.**</span><span class="sxs-lookup"><span data-stu-id="671a9-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="671a9-133">A **guia** Treinamento é exibida e contém 50 itens para você rotular.</span><span class="sxs-lookup"><span data-stu-id="671a9-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="671a9-134">Revise cada documento e selecione o botão **Relevante** ou **Não relevante** na parte inferior do painel de leitura para rotulá-lo.</span><span class="sxs-lookup"><span data-stu-id="671a9-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Rotular cada documento como relevante ou não relevante](..\media\TrainModel1.png)

5. <span data-ttu-id="671a9-136">Depois de rotular todos os 50 itens, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="671a9-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="671a9-137">O sistema levará alguns minutos para "aprender" com a rotulagem e atualizar o modelo.</span><span class="sxs-lookup"><span data-stu-id="671a9-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="671a9-138">Quando esse processo é concluído, um status de **Ready** é exibido para o modelo na página Modelos de codificação preditiva **(visualização).**</span><span class="sxs-lookup"><span data-stu-id="671a9-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="671a9-139">Para obter instruções mais detalhadas, consulte [Train a predictive coding model](predictive-coding-train-model.md).</span><span class="sxs-lookup"><span data-stu-id="671a9-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="671a9-140">Etapa 3: Aplicar o filtro de pontuação de previsão a itens no conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="671a9-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="671a9-141">Depois de executar na locação de uma rodada de treinamento, você pode aplicar o filtro de pontuação de previsão aos itens no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="671a9-142">Isso permite que você revise os itens que o modelo previu como relevantes ou não relevantes.</span><span class="sxs-lookup"><span data-stu-id="671a9-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="671a9-143">Abra o conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-143">Open the review set.</span></span>

   ![Clique em Filtros para exibir a página de sobrevoo Filtros](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="671a9-145">Os filtros padrão pré-carregados são exibidos na parte superior da página de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="671a9-146">Você pode deixá-los definidos como **Qualquer**.</span><span class="sxs-lookup"><span data-stu-id="671a9-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="671a9-147">Clique **em Filtros** para exibir a página de sobrevoo **Filtros.**</span><span class="sxs-lookup"><span data-stu-id="671a9-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="671a9-148">Expanda **a seção Análise & codificação preditiva** para exibir um conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="671a9-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filtro de pontuação de previsão na seção Análise & codificação preditiva](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="671a9-150">A convenção de nomenisagem para filtros de pontuação de previsão é **Pontuação de previsão (nome do modelo)**.</span><span class="sxs-lookup"><span data-stu-id="671a9-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="671a9-151">Por exemplo, o nome do filtro de pontuação de previsão para um modelo chamado **Modelo A** é **Pontuação de Previsão (Modelo A)**.</span><span class="sxs-lookup"><span data-stu-id="671a9-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="671a9-152">Selecione o filtro de pontuação de previsão que você deseja usar e clique em **Feito**.</span><span class="sxs-lookup"><span data-stu-id="671a9-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="671a9-153">Na página conjunto de revisão, clique no menu suspenso para o filtro de pontuação de previsão e digite valores mínimos e máximos para o intervalo de pontuação de previsão.</span><span class="sxs-lookup"><span data-stu-id="671a9-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="671a9-154">Por exemplo, a captura de tela a seguir mostra um intervalo de pontuação de previsão entre **.5** e **1,0**.</span><span class="sxs-lookup"><span data-stu-id="671a9-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Valores mínimos e máximos para o filtro de pontuação de previsão](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="671a9-156">Clique fora do filtro para aplicar automaticamente o filtro ao conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="671a9-157">Uma lista de documentos com uma pontuação de previsão dentro do intervalo especificado é exibida na página conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="671a9-158">Para obter instruções mais detalhadas, consulte Aplicar um filtro [de previsão a um conjunto de revisão](predictive-coding-apply-prediction-filter.md).</span><span class="sxs-lookup"><span data-stu-id="671a9-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="671a9-159">Etapa 4: Executar mais rodadas de treinamento</span><span class="sxs-lookup"><span data-stu-id="671a9-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="671a9-160">Mais do que provável, você terá que executar mais rodadas de treinamento para treinar o módulo para prever melhor os itens relevantes e não relevantes no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="671a9-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="671a9-161">Em geral, você treinará o modelo vezes suficientes até que ele se estabiliza o suficiente para atender aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="671a9-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="671a9-162">Para obter mais informações, consulte [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="671a9-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="671a9-163">Etapa 5: aplicar o filtro de pontuação de previsão final para priorizar a revisão</span><span class="sxs-lookup"><span data-stu-id="671a9-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="671a9-164">Repita as instruções na Etapa 3 para aplicar a pontuação final de previsão ao conjunto de revisão para priorizar a revisão de itens relevantes e não relevantes depois de concluir todas as rodadas de treinamento e estabilizar o modelo.</span><span class="sxs-lookup"><span data-stu-id="671a9-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
