---
title: Aplicar o filtro de pontuação de previsão a itens em um conjunto de revisão
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
description: Use um filtro de pontuação de previsão para exibir itens que um modelo de codificação preditivo como previsto como relevante ou não relevante.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822462"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="c4a11-103">Aplicar um filtro de pontuação de previsão a um conjunto de revisão (visualização)</span><span class="sxs-lookup"><span data-stu-id="c4a11-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="c4a11-104">Depois de criar um modelo de codificação preditiva no Advanced eDiscovery e treiná-lo até o ponto em que ele está estável, você pode aplicar o filtro de pontuação de previsão para exibir itens de conjunto de revisão que o modelo determinou são relevantes (ou não relevantes).</span><span class="sxs-lookup"><span data-stu-id="c4a11-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="c4a11-105">Quando você cria um modelo, um filtro de pontuação de previsão correspondente também é criado.</span><span class="sxs-lookup"><span data-stu-id="c4a11-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="c4a11-106">Você pode usar esse filtro para exibir itens atribuídos a uma pontuação de previsão dentro de um intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="c4a11-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="c4a11-107">Em geral, as pontuações de previsão entre 0 e **0,5** são atribuídas a itens que o modelo previu não são relevantes. </span><span class="sxs-lookup"><span data-stu-id="c4a11-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="c4a11-108">Itens atribuídos a pontuações de previsão entre **.5** e **1.0** são itens que o modelo previu são relevantes.</span><span class="sxs-lookup"><span data-stu-id="c4a11-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="c4a11-109">Aqui estão duas maneiras de usar o filtro de pontuação de previsão:</span><span class="sxs-lookup"><span data-stu-id="c4a11-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="c4a11-110">Priorizar a revisão de itens em um conjunto de revisão que o modelo previu são relevantes.</span><span class="sxs-lookup"><span data-stu-id="c4a11-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="c4a11-111">Os itens do conjunto de revisão que o modelo previu não são relevantes.</span><span class="sxs-lookup"><span data-stu-id="c4a11-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="c4a11-112">Alternativa, você pode usar o filtro de pontuação de previsão para des priorizar a revisão de itens não relevantes.</span><span class="sxs-lookup"><span data-stu-id="c4a11-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="c4a11-113">Antes de aplicar um filtro de pontuação de previsão</span><span class="sxs-lookup"><span data-stu-id="c4a11-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="c4a11-114">Crie um modelo de codificação preditiva para que um filtro de pontuação de previsão correspondente seja criado.</span><span class="sxs-lookup"><span data-stu-id="c4a11-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="c4a11-115">Você pode aplicar um filtro de pontuação de previsão após qualquer uma das rodadas de treinamento.</span><span class="sxs-lookup"><span data-stu-id="c4a11-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="c4a11-116">Mas você pode esperar depois de executar várias rodadas ou até que o modelo seja estável antes de usar o filtro de pontuação de previsão.</span><span class="sxs-lookup"><span data-stu-id="c4a11-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="c4a11-117">Aplicar um filtro de pontuação de previsão</span><span class="sxs-lookup"><span data-stu-id="c4a11-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="c4a11-118">No centro Microsoft 365 de conformidade, abra o caso Advanced eDiscovery, selecione a guia Revisar **conjuntos** e abra o conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="c4a11-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![Clique em Filtros para exibir a página de sobrevoo Filtros](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="c4a11-120">Os filtros padrão pré-carregados são exibidos na parte superior da página de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="c4a11-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="c4a11-121">Você pode deixá-los definidos como **Qualquer**.</span><span class="sxs-lookup"><span data-stu-id="c4a11-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="c4a11-122">Clique **em Filtros** para exibir a página de sobrevoo **Filtros.**</span><span class="sxs-lookup"><span data-stu-id="c4a11-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="c4a11-123">Expanda **a seção Análise & codificação preditiva** para exibir um conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="c4a11-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filtro de pontuação de previsão na seção Análise & codificação preditiva](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="c4a11-125">A convenção de nomenisagem para filtros de pontuação de previsão é **Pontuação de previsão (nome do modelo)**.</span><span class="sxs-lookup"><span data-stu-id="c4a11-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="c4a11-126">Por exemplo, o nome do filtro de pontuação de previsão para um modelo chamado **Modelo A** é **Pontuação de Previsão (Modelo A)**.</span><span class="sxs-lookup"><span data-stu-id="c4a11-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="c4a11-127">Selecione o filtro de pontuação de previsão que você deseja usar e clique em **Feito**.</span><span class="sxs-lookup"><span data-stu-id="c4a11-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="c4a11-128">Na página conjunto de revisão, clique no menu suspenso para o filtro de pontuação de previsão e digite valores mínimos e máximos para o intervalo de pontuação de previsão.</span><span class="sxs-lookup"><span data-stu-id="c4a11-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="c4a11-129">Por exemplo, a captura de tela a seguir mostra um intervalo de pontuação de previsão entre **.5** e **1,0**.</span><span class="sxs-lookup"><span data-stu-id="c4a11-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Valores mínimos e máximos para o filtro de pontuação de previsão](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="c4a11-131">Clique fora do filtro para aplicar automaticamente o filtro ao conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="c4a11-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="c4a11-132">Uma lista de documentos com uma pontuação de previsão dentro do intervalo especificado é exibida na página conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="c4a11-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="c4a11-133">Para exibir a pontuação real da previsão atribuir a um documento, você pode clicar na guia **Metadados** no painel de leitura.</span><span class="sxs-lookup"><span data-stu-id="c4a11-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="c4a11-134">As pontuações de previsão de todos os modelos no conjunto de revisão são exibidas na propriedade de metadados **RelevanceScores.**</span><span class="sxs-lookup"><span data-stu-id="c4a11-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="c4a11-135">Mais informações</span><span class="sxs-lookup"><span data-stu-id="c4a11-135">More information</span></span>

- <span data-ttu-id="c4a11-136">Para obter mais informações sobre como usar filtros, consulte [Query and filter content in a review set](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="c4a11-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
