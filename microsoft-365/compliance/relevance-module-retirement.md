---
title: Módulo Desaconsuência da Relevância na Descoberta Avançada
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
ms.collection: M365-security-compliance
description: O módulo Relevância na Descoberta Avançada será retirado em 10 de março de 2021. Este artigo explica o que fazer antes que a Relevância seja retirada. Especificamente, concluindo todos os modelos não concluídos executando o cálculo em lotes para que você possa manter os metadados do modelo.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122521"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="675a1-105">Baixa do módulo Relevância na Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="675a1-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="675a1-106">Em 10 de março de 2021, estamos retirando o módulo Relevância na Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="675a1-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="675a1-107">Essa baixa significa que as organizações não terão mais acesso ao módulo Relevância (gerenciando a relevância do conjunto de revisão em um caso de Descoberta Eletrônico Avançada) ou poderão acessar quaisquer modelos de Relevância  >   existentes.</span><span class="sxs-lookup"><span data-stu-id="675a1-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="675a1-108">O módulo de Relevância atual que está sendo retirado será substituído por uma nova solução de codificação preditiva no 2º trimestre de 2021.</span><span class="sxs-lookup"><span data-stu-id="675a1-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="675a1-109">Essa nova funcionalidade permitirá que as organizações criem seus próprios modelos de codificação preditiva em um fluxo de trabalho mais fácil e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="675a1-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="675a1-110">Para se preparar para essa futura desaportação, recomendamos que as organizações que usam o módulo de Relevância exportem a saída do modelo antes da data de reforma, executando um cálculo em lotes para todos os modelos existentes.</span><span class="sxs-lookup"><span data-stu-id="675a1-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="675a1-111">Todas as pontuações de Relevância do seu modelo serão armazenadas permanentemente no conjunto de revisão correspondente e acessíveis quando os documentos são exportados.</span><span class="sxs-lookup"><span data-stu-id="675a1-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="675a1-112">As pontuações de relevância também são mantidas como metadados no arquivo de carregamento.</span><span class="sxs-lookup"><span data-stu-id="675a1-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="675a1-113">Além disso, você ainda poderá filtrar o conteúdo no conjunto de revisão com base na pontuação de relevância e ter acesso a todos os metadados produzidos por seus modelos de Relevância.</span><span class="sxs-lookup"><span data-stu-id="675a1-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="675a1-114">Concluir modelos não concluídos</span><span class="sxs-lookup"><span data-stu-id="675a1-114">Complete unfinished models</span></span>

<span data-ttu-id="675a1-115">Para qualquer modelo de Relevância não concluído, conclua a avaliação, o treinamento e o cálculo em lotes para que você possa aplicar o modelo aos documentos em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="675a1-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="675a1-116">A conclusão do cálculo em lotes preservará as informações após a data de conclusão do módulo relevância.</span><span class="sxs-lookup"><span data-stu-id="675a1-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="675a1-117">Aqui estão as etapas para concluir todos os modelos não concluídos:</span><span class="sxs-lookup"><span data-stu-id="675a1-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="675a1-118">Treine seu modelo até que ele esteja estabilizado e pronto para o cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="675a1-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="675a1-119">Consulte [Marcação e treinamento de relevância.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="675a1-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="675a1-120">A captura de tela a seguir mostra um módulo que está pronto para um cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="675a1-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="675a1-121">Observe que a Avaliação e Treinamento está concluída, e a próxima etapa é executar o cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="675a1-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Captura de tela do modelo pronto para cálculo em lotes](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="675a1-123">Execute o cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="675a1-123">Run the Batch calculation.</span></span> <span data-ttu-id="675a1-124">Consulte [Executando o cálculo em lotes.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="675a1-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="675a1-125">Verifique se o cálculo do lote foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="675a1-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="675a1-126">Consulte [Resultados de cálculo em lotes.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)</span><span class="sxs-lookup"><span data-stu-id="675a1-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="675a1-127">Para ajuda com a conclusão de modelos de relevância não concluídos, entre em contato com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="675a1-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
