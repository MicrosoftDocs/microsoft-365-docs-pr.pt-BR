---
title: Módulo de ressalção de relevância no Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: O módulo De relevância no Advanced eDiscovery será retirado em 10 de março de 2021. Este artigo explica o que fazer antes que a Relevância seja retirada. Especificamente, concluindo quaisquer modelos não concluídos executando o cálculo em lotes para que você possa manter os metadados do modelo.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821992"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="cf745-105">Ressalção do módulo De relevância no Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cf745-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="cf745-106">Em 10 de março de 2021, estamos retirando o módulo De relevância no Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="cf745-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="cf745-107">Essa aposentadoria significa que as organizações não terão mais acesso ao módulo De relevância (indo para Gerenciar a relevância do conjunto de revisão em um caso Advanced eDiscovery) ou poderão acessar quaisquer modelos de  >   Relevância existentes.</span><span class="sxs-lookup"><span data-stu-id="cf745-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="cf745-108">O módulo de Relevância atual que está sendo retirado será substituído por uma nova solução de codificação preditiva no 2º trimestre de 2021.</span><span class="sxs-lookup"><span data-stu-id="cf745-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="cf745-109">Essa nova funcionalidade permitirá que as organizações criem seus próprios modelos de codificação preditivos em um fluxo de trabalho mais fácil e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="cf745-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="cf745-110">Para se preparar para essa próxima aposentadoria, recomendamos que as organizações que usam o módulo De relevância exportem a saída do modelo antes da data de aposentadoria executando um cálculo em lotes para todos os modelos existentes.</span><span class="sxs-lookup"><span data-stu-id="cf745-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="cf745-111">Todas as pontuações de Relevância do seu modelo serão armazenadas permanentemente no conjunto de revisão correspondente e acessíveis quando os documentos são exportados.</span><span class="sxs-lookup"><span data-stu-id="cf745-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="cf745-112">As pontuações de relevância também são mantidas como metadados no arquivo de carga.</span><span class="sxs-lookup"><span data-stu-id="cf745-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="cf745-113">Além disso, você ainda poderá filtrar conteúdo no conjunto de revisão com base na pontuação de relevância e ter acesso a todos os metadados produzidos por seus modelos de Relevância.</span><span class="sxs-lookup"><span data-stu-id="cf745-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="cf745-114">Concluir modelos não concluídos</span><span class="sxs-lookup"><span data-stu-id="cf745-114">Complete unfinished models</span></span>

<span data-ttu-id="cf745-115">Para quaisquer modelos de Relevância não concluídos, conclua a avaliação, o treinamento e o cálculo em lotes para que você possa aplicar o modelo aos documentos em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="cf745-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="cf745-116">Concluir o cálculo em lotes preservará as informações após a data de aposentadoria do módulo De relevância.</span><span class="sxs-lookup"><span data-stu-id="cf745-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="cf745-117">Aqui estão as etapas para concluir quaisquer modelos não concluídos:</span><span class="sxs-lookup"><span data-stu-id="cf745-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="cf745-118">Treine seu modelo até que ele esteja estabilizado e pronto para cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="cf745-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="cf745-119">Consulte [Treinamento de marcação e relevância.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="cf745-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="cf745-120">A captura de tela a seguir mostra um módulo que está pronto para um cálculo batch.</span><span class="sxs-lookup"><span data-stu-id="cf745-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="cf745-121">Observe que a Avaliação e Treinamento está concluída e a próxima etapa é executar o cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="cf745-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Captura de tela do modelo pronto para cálculo em lotes](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="cf745-123">Execute o cálculo batch.</span><span class="sxs-lookup"><span data-stu-id="cf745-123">Run the Batch calculation.</span></span> <span data-ttu-id="cf745-124">Consulte [Perform Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span><span class="sxs-lookup"><span data-stu-id="cf745-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="cf745-125">Verifique se o cálculo em lotes foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="cf745-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="cf745-126">Consulte [Resultados de cálculo em lotes](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span><span class="sxs-lookup"><span data-stu-id="cf745-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="cf745-127">Para ajudar a concluir modelos de relevância não concluídos, entre em contato com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf745-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
