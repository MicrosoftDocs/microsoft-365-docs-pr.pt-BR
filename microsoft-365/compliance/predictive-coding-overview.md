---
title: Módulo de codificação preditiva para Descoberta Avançada (visualização)
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
description: O novo módulo de codificação preditiva na Descoberta Eletrônica Avançada usa aprendizado de máquina para analisar documentos em um conjunto de revisão para prever quais documentos são relevantes para seu caso ou investigação.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382944"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="9ca28-103">Módulo de codificação preditiva para Descoberta Avançada (visualização)</span><span class="sxs-lookup"><span data-stu-id="9ca28-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="9ca28-104">Usando o novo módulo de codificação preditiva na Descoberta Avançada, você pode criar e criar um modelo para priorizar a revisão de documentos começando com os documentos mais relevantes.</span><span class="sxs-lookup"><span data-stu-id="9ca28-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="9ca28-105">Para começar, você pode criar um modelo, rotular até 50 documentos e filtrar documentos por pontuações de previsão de modelo para revisar documentos relevantes não relevantes.</span><span class="sxs-lookup"><span data-stu-id="9ca28-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="9ca28-106">Aqui está uma visão geral rápida do fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="9ca28-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="9ca28-107">Abra o módulo de codificação preditiva em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="9ca28-107">Open the predictive coding module in a review set.</span></span>

   ![Clique na lista suspenso Analisar em uma revisão para ir para o módulo de codificação preditiva](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="9ca28-109">Na página **Modelos de codificação preditiva,** clique em **Novo modelo** para criar um novo modelo de codificação preditiva.</span><span class="sxs-lookup"><span data-stu-id="9ca28-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![Criar um novo modelo](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="9ca28-111">Rotule pelo menos 50 documentos **como Relevantes** **ou Não Relevantes.**</span><span class="sxs-lookup"><span data-stu-id="9ca28-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="9ca28-112">Essa rotulagem é usada para treinar o sistema.</span><span class="sxs-lookup"><span data-stu-id="9ca28-112">This labeling is used to train the system.</span></span>

   ![Rotular documentos como relevantes ou não relevantes para treinar o sistema](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="9ca28-114">Aplique o **filtro de pontuação** previsão para seu modelo ao conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="9ca28-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="9ca28-115">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="9ca28-115">To do this:</span></span>

   1. <span data-ttu-id="9ca28-116">No conjunto de revisão, clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="9ca28-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="9ca28-117">Na página **Sobrevoo Filtros,** expanda a  seção **Análise/ML** e selecione Caixa de seleção Pontuação de previsão para o modelo que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="9ca28-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="9ca28-118">No filtro **de pontuação previsão,** especifique uma pontuação de previsão.</span><span class="sxs-lookup"><span data-stu-id="9ca28-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="9ca28-119">O filtro exibirá os documentos no conjunto de revisão que corresponderem à pontuação de previsão.</span><span class="sxs-lookup"><span data-stu-id="9ca28-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![Especificar uma pontuação de previsão para filtrar documentos](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="9ca28-121">Monitore o desempenho, o status e a estabilidade do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="9ca28-121">Monitor the performance, status, and stability of your model.</span></span>

   ![Monitorar o desempenho, o status e a estabilidade do seu modelo](..\media\PredictiveCoding5.png)
