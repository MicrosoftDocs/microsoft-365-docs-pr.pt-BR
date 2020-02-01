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
description: ''
ms.openlocfilehash: 1c0f174b29d49ec1d07c128f709ee3279c1b53ef
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594044"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="a6e20-102">Adicionar dados a um conjunto de revisão de outro conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="a6e20-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="a6e20-103">Em alguns casos, pode ser necessário selecionar documentos de um conjunto de análise e trabalhar com eles individualmente em outro conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="a6e20-103">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="a6e20-104">Isso é especialmente útil se você tiver escolhido conteúdo em um conjunto de revisão e quiser executar a análise no subconjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="a6e20-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="a6e20-105">Siga o fluxo de trabalho neste artigo para adicionar conteúdo de um conjunto de análise para outro.</span><span class="sxs-lookup"><span data-stu-id="a6e20-105">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a6e20-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a6e20-106">Before you begin</span></span>

<span data-ttu-id="a6e20-107">Antes de começar, você precisará criar uma nova revisão configurada para adicionar os dados a.</span><span class="sxs-lookup"><span data-stu-id="a6e20-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="a6e20-108">Um novo conjunto de revisão pode ser adicionado à guia **conjuntos de revisão** da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="a6e20-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="a6e20-109">Para obter mais informações, consulte [criar um conjunto de revisão](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="a6e20-109">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="a6e20-110">Etapa 1: identificar o conteúdo a ser adicionado a outro conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="a6e20-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="a6e20-111">Você pode adicionar conteúdo de uma análise definida para outra selecionando documentos específicos no conjunto de revisão de origem ou selecionando todos os itens retornados por consulta de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="a6e20-111">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="a6e20-112">Se você estiver adicionando itens selecionados, selecione os itens, selecione **ação**e, em seguida, selecione **Adicionar a outro conjunto de revisão**.</span><span class="sxs-lookup"><span data-stu-id="a6e20-112">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Adicionar a outro conjunto de revisão](media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="a6e20-114">Etapa 2: especificar as opções para adicionar a outro conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="a6e20-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="a6e20-115">Na página **Adicionar a outro conjunto de revisão de opções** , escolha o conjunto de revisão ao qual você deseja adicionar os itens.</span><span class="sxs-lookup"><span data-stu-id="a6e20-115">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="a6e20-116">Escolha se deseja adicionar **todos os resultados de pesquisa** ou os **itens selecionados**.</span><span class="sxs-lookup"><span data-stu-id="a6e20-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="a6e20-117">**Informações adicionais** fornecem opções para incluir todos os metadados dos itens e se devem ser incluídas as marcas (marcando a caixa de seleção **Rótulos** ) do conjunto de revisão de origem quando os documentos são adicionados ao novo conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="a6e20-117">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Adicionar a outro conjunto de revisão](media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="a6e20-119">Após clicar em **OK**, um novo trabalho (chamado **adição de dados a outro conjunto de revisão**) é criado para adicionar o conteúdo a outro conjunto de análise.</span><span class="sxs-lookup"><span data-stu-id="a6e20-119">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="a6e20-120">Você pode ir para a guia **trabalhos** e monitorar o progresso desse trabalho.</span><span class="sxs-lookup"><span data-stu-id="a6e20-120">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="a6e20-121">Para obter mais informações, consulte [Manage Jobs](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="a6e20-121">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
