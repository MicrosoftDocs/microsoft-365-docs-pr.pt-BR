---
title: Adicionar dados de um conjunto de revisão a outro conjunto de revisão
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
description: Saiba como selecionar documentos de um conjunto de revisão e trabalhar com eles individualmente em outro conjunto em Advanced eDiscovery caso.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285175"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="8173e-103">Adicionar dados a um conjunto de revisão de outro conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="8173e-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="8173e-104">Em alguns casos, pode ser necessário selecionar documentos de um conjunto de revisão e trabalhar com eles individualmente em outro conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="8173e-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="8173e-105">Isso é particularmente útil se você selecionou conteúdo em um conjunto de revisão e desejar executar a análise no subconjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="8173e-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="8173e-106">Siga o fluxo de trabalho neste artigo para adicionar conteúdo de um conjunto de revisão para outro.</span><span class="sxs-lookup"><span data-stu-id="8173e-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="8173e-107">Criar um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="8173e-107">Create a review set</span></span>

<span data-ttu-id="8173e-108">Antes de começar, você precisará criar um conjunto de revisão para adicionar os dados.</span><span class="sxs-lookup"><span data-stu-id="8173e-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="8173e-109">Um novo conjunto de revisão pode ser adicionado na guia **Conjuntos de revisão** do caso.</span><span class="sxs-lookup"><span data-stu-id="8173e-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="8173e-110">Para obter mais informações, consulte [Create a review set](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="8173e-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="8173e-111">Etapa 1: identificar conteúdo a ser acrescentado a outro conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="8173e-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="8173e-112">Você pode adicionar conteúdo de um conjunto de revisão para outro selecionando documentos específicos no conjunto de revisão de origem ou selecionando todos os itens retornados pela consulta do conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="8173e-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="8173e-113">Se você estiver adicionando itens selecionados, selecione os itens, selecione **Ação** e, em seguida, **selecione Adicionar a outro conjunto de revisão**.</span><span class="sxs-lookup"><span data-stu-id="8173e-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Adicionar a outro conjunto de revisão no menu Ação](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="8173e-115">Etapa 2: Especificar opções para adicionar a outro conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="8173e-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="8173e-116">Na página **Adicionar a outra opção de conjunto** de revisão, escolha o conjunto de revisão ao qual você deseja adicionar os itens.</span><span class="sxs-lookup"><span data-stu-id="8173e-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="8173e-117">Escolha se deve adicionar **Todos os resultados da pesquisa ou** itens **Selecionados.**</span><span class="sxs-lookup"><span data-stu-id="8173e-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="8173e-118">**Informações adicionais** fornece opções para incluir todos os metadados dos  itens e se devem incluir as marcas (selecionando a caixa de seleção Rótulos) no conjunto de revisão de origem quando os documentos são adicionados ao novo conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="8173e-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Opções para adicionar dados a outro conjunto de revisão](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="8173e-120">Depois de clicar em **Ok,** um novo trabalho (chamado **Adicionando dados** a outro conjunto de revisão ) é criado para adicionar o conteúdo a outro conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="8173e-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="8173e-121">Você pode ir até a guia **Trabalhos** e monitorar o andamento deste trabalho.</span><span class="sxs-lookup"><span data-stu-id="8173e-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="8173e-122">Para obter mais informações, consulte [Gerenciar trabalhos](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="8173e-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
