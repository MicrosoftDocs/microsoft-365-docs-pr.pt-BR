---
title: Adicionar dados de um conjunto de revisão para outro conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como selecionar documentos de um conjunto de análise e trabalhar com eles individualmente em outro conjunto em um caso de descoberta eletrônica avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 636e76b1740cfa07254e4c56165cfafa8f1fad5a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034675"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="85fe8-103">Adicionar dados a um conjunto de revisão de outro conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="85fe8-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="85fe8-104">Em alguns casos, pode ser necessário selecionar documentos de um conjunto de análise e trabalhar com eles individualmente em outro conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="85fe8-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="85fe8-105">Isso é especialmente útil se você tiver escolhido conteúdo em um conjunto de revisão e quiser executar a análise no subconjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="85fe8-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="85fe8-106">Siga o fluxo de trabalho neste artigo para adicionar conteúdo de um conjunto de análise para outro.</span><span class="sxs-lookup"><span data-stu-id="85fe8-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="85fe8-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="85fe8-107">Before you begin</span></span>

<span data-ttu-id="85fe8-108">Antes de começar, você precisará criar uma nova revisão configurada para adicionar os dados a.</span><span class="sxs-lookup"><span data-stu-id="85fe8-108">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="85fe8-109">Um novo conjunto de revisão pode ser adicionado à guia **conjuntos de revisão** da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="85fe8-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="85fe8-110">Para obter mais informações, consulte [criar um conjunto de revisão](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="85fe8-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="85fe8-111">Etapa 1: identificar o conteúdo a ser adicionado a outro conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="85fe8-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="85fe8-112">Você pode adicionar conteúdo de uma análise definida para outra selecionando documentos específicos no conjunto de revisão de origem ou selecionando todos os itens retornados por consulta de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="85fe8-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="85fe8-113">Se você estiver adicionando itens selecionados, selecione os itens, selecione **ação**e, em seguida, selecione **Adicionar a outro conjunto de revisão**.</span><span class="sxs-lookup"><span data-stu-id="85fe8-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Adicionar a outro conjunto de revisão](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="85fe8-115">Etapa 2: especificar as opções para adicionar a outro conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="85fe8-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="85fe8-116">Na página **Adicionar a outro conjunto de revisão de opções** , escolha o conjunto de revisão ao qual você deseja adicionar os itens.</span><span class="sxs-lookup"><span data-stu-id="85fe8-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="85fe8-117">Escolha se deseja adicionar **todos os resultados de pesquisa** ou os **itens selecionados**.</span><span class="sxs-lookup"><span data-stu-id="85fe8-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="85fe8-118">**Informações adicionais** fornecem opções para incluir todos os metadados dos itens e se devem ser incluídas as marcas (marcando a caixa de seleção **Rótulos** ) do conjunto de revisão de origem quando os documentos são adicionados ao novo conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="85fe8-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Adicionar a outro conjunto de revisão](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="85fe8-120">Após clicar em **OK**, um novo trabalho (chamado **adição de dados a outro conjunto de revisão**) é criado para adicionar o conteúdo a outro conjunto de análise.</span><span class="sxs-lookup"><span data-stu-id="85fe8-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="85fe8-121">Você pode ir para a guia **trabalhos** e monitorar o progresso desse trabalho.</span><span class="sxs-lookup"><span data-stu-id="85fe8-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="85fe8-122">Para obter mais informações, consulte [Manage Jobs](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="85fe8-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
