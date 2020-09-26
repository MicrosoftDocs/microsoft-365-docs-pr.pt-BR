---
title: Criar consultas de pesquisa em investigações de dados
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
ms.custom: seo-marvel-mar2020
description: Use palavras-chave e condições para restringir o escopo de pesquisa ao pesquisar dados usando a investigação de dados no Microsoft 365.
ms.openlocfilehash: b2d77ef23e7427fd5f770a27166dc571f853191d
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285757"
---
# <a name="build-search-queries-in-data-investigations-preview"></a><span data-ttu-id="e5d3f-103">Criar consultas de pesquisa em investigações de dados (prévia)</span><span class="sxs-lookup"><span data-stu-id="e5d3f-103">Build search queries in Data Investigations (preview)</span></span>

<span data-ttu-id="e5d3f-104">Ao criar consultas de pesquisa, você pode usar palavras-chave para localizar conteúdo e condições específicas para restringir o escopo da pesquisa para retornar itens que sejam mais relevantes para sua investigação.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-104">When building search queries, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your investigation.</span></span>

![Usar palavras-chave e condições para restringir os resultados de uma pesquisa](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="e5d3f-106">Pesquisas de palavra-chave</span><span class="sxs-lookup"><span data-stu-id="e5d3f-106">Keyword searches</span></span>

<span data-ttu-id="e5d3f-107">Digite uma consulta de palavra-chave na caixa **palavras-** chave na consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="e5d3f-108">Você pode especificar palavras-chave, propriedades de mensagens de email, como datas enviadas e recebidas, ou propriedades do documento, como nomes de arquivo ou a data em que um documento foi alterado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="e5d3f-109">Faça consultas mais complexas que usam um operador Booleano, **E**, **OU**, **NÃO** e **PRÓXIMO**.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="e5d3f-110">Você também pode pesquisar informações confidenciais, como números de seguridade social, em documentos no SharePoint e no OneDrive (não em mensagens de email) ou pesquisar documentos que foram compartilhados externamente.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-110">You can also search for sensitive information, such as social security numbers, in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="e5d3f-111">Se você deixar a caixa **palavras-chave** vazia, todo o conteúdo localizado nos locais de conteúdo especificado será incluído nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-111">If you leave the **Keywords** box empty, all content located in the specified content locations is included in the search results.</span></span>
    
<span data-ttu-id="e5d3f-112">Como alternativa, você pode marcar a caixa de seleção **Mostrar lista de palavras-chave** e digitar uma frase de palavra-chave ou palavra-chave em cada linha.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-112">Alternatively, you can select the **Show keyword list** check box and then type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="e5d3f-113">Se você fizer isso, as palavras-chave em cada linha serão conectadas por um operador lógico (representado como *c:s*) que é semelhante em funcionalidade ao operador **or** na consulta de pesquisa criada.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-113">If you do this, the keywords in each row are connected by a logical operator (represented as *c:s*) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="e5d3f-114">Isso significa que os itens que contêm qualquer palavra-chave em qualquer linha são incluídos nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-114">This means that items that contain any keyword in any row are included in the search results.</span></span>

![Use a lista de palavras-chave para obter estatísticas sobre cada palavra-chave na consulta](../media/KeywordListSearch.png)

<span data-ttu-id="e5d3f-116">Por que usar a lista de palavras-chave?</span><span class="sxs-lookup"><span data-stu-id="e5d3f-116">Why use the keyword list?</span></span> <span data-ttu-id="e5d3f-117">Você pode obter estatísticas que mostram quantos itens correspondem a cada palavra-chave na lista de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="e5d3f-118">Isso pode ajudá-lo a identificar rapidamente as palavras-chave mais (e menos) em vigor.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="e5d3f-119">Você também pode usar uma frase de palavra-chave (entre parênteses) em uma linha na lista de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="e5d3f-120">Para obter mais informações sobre estatísticas de pesquisa, confira [Estatísticas de pesquisa](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="e5d3f-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e5d3f-121">Para ajudar a reduzir problemas causados por listas de palavras-chave grandes, você está limitado a um máximo de 20 linhas na lista de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="e5d3f-122">Condições</span><span class="sxs-lookup"><span data-stu-id="e5d3f-122">Conditions</span></span>
    
<span data-ttu-id="e5d3f-123">Você pode adicionar condições de pesquisa para restringir o escopo de uma pesquisa e retornar um conjunto de resultados mais refinado.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="e5d3f-124">Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="e5d3f-125">Uma condição é conectada logicamente à consulta de palavra-chave (especificada na caixa palavra-chave) por um operador lógico (que é representado como *c:c*) que é semelhante em funcionalidade ao operador **and** .</span><span class="sxs-lookup"><span data-stu-id="e5d3f-125">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (which is represented as *c:c*) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="e5d3f-126">Isso significa que os itens precisam satisfazer a consulta de palavra-chave e uma ou mais condições a serem incluídas nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-126">This means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="e5d3f-127">É assim que as condições ajudam a restringir os resultados.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="e5d3f-128">Para obter uma lista e uma descrição das condições que você pode usar em uma consulta de pesquisa, consulte a seção "condições de pesquisa" em [consultas de palavra-chave e condições de pesquisa](keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="e5d3f-128">For a list and description of conditions you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
