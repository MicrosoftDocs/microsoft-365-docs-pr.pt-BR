---
title: Consultar dados em um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como criar e executar uma consulta em um conjunto de revisão para organizar dados para uma revisão mais eficiente em um Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345795"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="626d5-103">Consultar dados em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="626d5-103">Query the data in a review set</span></span>

<span data-ttu-id="626d5-104">Na maioria dos casos, será útil ser capaz de aprofundar os dados em um conjunto de revisão e organizar esses dados para facilitar uma revisão mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="626d5-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="626d5-105">Usar consultas em um conjunto de revisão ajuda você a se concentrar em um subconjunto de documentos que atendem aos critérios de sua revisão.</span><span class="sxs-lookup"><span data-stu-id="626d5-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="626d5-106">Criar e executar uma consulta em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="626d5-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="626d5-107">Para criar e executar uma consulta nos documentos em um conjunto de revisão, selecione **Nova consulta** no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="626d5-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="626d5-108">Depois de nomear sua consulta e definir as condições, selecione **Salvar** para salvar e executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="626d5-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="626d5-109">Para executar uma consulta que foi salva anteriormente, selecione uma consulta salva.</span><span class="sxs-lookup"><span data-stu-id="626d5-109">To run a query that has been previously saved, select a saved query.</span></span>

![Revisar consultas de conjunto](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="626d5-111">Criando uma consulta de conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="626d5-111">Building a review set query</span></span>

<span data-ttu-id="626d5-112">Você pode criar uma consulta usando uma combinação de palavras-chave, propriedades e condições na condição Keywords.</span><span class="sxs-lookup"><span data-stu-id="626d5-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="626d5-113">Você também pode agrupar condições como um bloco (chamado de grupo de *condição*) para criar uma consulta mais complexa.</span><span class="sxs-lookup"><span data-stu-id="626d5-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="626d5-114">Para uma lista e uma descrição das propriedades de metadados que você pode pesquisar, consulte [Campos de metadados do documento no](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="626d5-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="626d5-115">Condições</span><span class="sxs-lookup"><span data-stu-id="626d5-115">Conditions</span></span>

<span data-ttu-id="626d5-116">Cada campo pesquisável em um conjunto de revisão tem uma condição correspondente que você pode usar para criar sua consulta.</span><span class="sxs-lookup"><span data-stu-id="626d5-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="626d5-117">Há vários tipos de condições:</span><span class="sxs-lookup"><span data-stu-id="626d5-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="626d5-118">Freetext: Uma condição de texto livre é usada para campos de texto, como assunto.</span><span class="sxs-lookup"><span data-stu-id="626d5-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="626d5-119">Você pode listar vários termos de pesquisa separando-os com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="626d5-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="626d5-120">Data: uma condição de data é usada para campos de data, como a última data modificada.</span><span class="sxs-lookup"><span data-stu-id="626d5-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="626d5-121">Opções de pesquisa: uma condição de opções de pesquisa fornecerá uma lista de valores possíveis para o campo específico no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="626d5-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="626d5-122">Isso é usado para campos, como remetente, onde há um número finito de valores possíveis em seu conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="626d5-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="626d5-123">Palavra-chave: uma condição de palavra-chave é uma instância específica da condição de texto livre em que você pode usar para pesquisar termos ou usar linguagem de consulta do tipo KQL.</span><span class="sxs-lookup"><span data-stu-id="626d5-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="626d5-124">Consulte abaixo para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="626d5-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="626d5-125">Linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="626d5-125">Query language</span></span>

<span data-ttu-id="626d5-126">Além das condições, você pode usar um idioma de consulta parecido com KQL na condição Palavras-chave para criar sua consulta.</span><span class="sxs-lookup"><span data-stu-id="626d5-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="626d5-127">O idioma de consulta para consultas de conjunto de revisão dá suporte a operadores booleano padrão, como **AND**, **OR**, **NOT** e **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="626d5-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="626d5-128">Ele também dá suporte a um caractere curinga de caractere único (?) e a um caractere curinga de vários caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="626d5-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="626d5-129">Filtros</span><span class="sxs-lookup"><span data-stu-id="626d5-129">Filters</span></span>

<span data-ttu-id="626d5-130">Além das consultas que você pode salvar, você pode usar filtros de conjunto de revisão para aplicar rapidamente condições adicionais a uma consulta de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="626d5-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="626d5-131">O uso de filtros ajuda você a refinar ainda mais os resultados exibidos por uma consulta de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="626d5-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Revisar filtros de conjunto](../media/AeDReviewSetFilters.png)

<span data-ttu-id="626d5-133">Os filtros diferem das consultas de duas maneiras significativas:</span><span class="sxs-lookup"><span data-stu-id="626d5-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="626d5-134">Os filtros são transitórios.</span><span class="sxs-lookup"><span data-stu-id="626d5-134">Filters are transient.</span></span> <span data-ttu-id="626d5-135">Eles não persistem além da sessão existente.</span><span class="sxs-lookup"><span data-stu-id="626d5-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="626d5-136">Em outras palavras, você não pode salvar um filtro.</span><span class="sxs-lookup"><span data-stu-id="626d5-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="626d5-137">As consultas são salvas no conjunto de revisão e acessam-nas sempre que você abre o conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="626d5-137">Queries are saved to the review set, and access them whenever you open the review set.</span></span>

- <span data-ttu-id="626d5-138">Os filtros são sempre aditivos.</span><span class="sxs-lookup"><span data-stu-id="626d5-138">Filters are always additive.</span></span> <span data-ttu-id="626d5-139">Os filtros são aplicados além da consulta de conjunto de revisão atual.</span><span class="sxs-lookup"><span data-stu-id="626d5-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="626d5-140">A aplicação de uma consulta diferente substituirá os resultados retornados pela consulta atual.</span><span class="sxs-lookup"><span data-stu-id="626d5-140">Applying a different query will replace the results returned by the current query.</span></span>
