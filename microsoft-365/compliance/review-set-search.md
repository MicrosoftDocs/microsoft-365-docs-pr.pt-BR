---
title: Consultar dados em um conjunto de revisão
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
description: Saiba como criar e executar uma consulta em uma revisão definida para organizar dados para uma análise mais eficiente em uma ocorrência de descoberta eletrônica avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 871630af4b8b19e5fad1a062129782e36b9706f5
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527431"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="00c9e-103">Consultar dados em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="00c9e-103">Query the data in a review set</span></span>

<span data-ttu-id="00c9e-104">Na maioria dos casos, será útil ser capaz de se aprofundar nos dados de um conjunto de análise e organizar esses dados para facilitar uma análise mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="00c9e-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="00c9e-105">Usar consultas em um conjunto de revisão ajuda você a se concentrar em um subconjunto de documentos que atendem aos critérios de sua análise.</span><span class="sxs-lookup"><span data-stu-id="00c9e-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="00c9e-106">Criando e executando uma consulta em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="00c9e-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="00c9e-107">Para criar e executar uma consulta nos documentos em um conjunto de revisão, clique em **nova consulta** no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="00c9e-107">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="00c9e-108">Depois de nomear sua consulta e definir as condições, clique em **salvar** para salvar e executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="00c9e-108">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="00c9e-109">Para executar uma consulta que tenha sido salva anteriormente, clique em uma consulta salva.</span><span class="sxs-lookup"><span data-stu-id="00c9e-109">To run a query that has been previously saved, click a saved query.</span></span>

![Analisar consultas de definição](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="00c9e-111">Criar uma consulta de conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="00c9e-111">Building a review set query</span></span>

<span data-ttu-id="00c9e-112">Você pode criar uma consulta usando uma combinação de cartões de condição e linguagem de consulta no cartão de condição de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="00c9e-112">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="00c9e-113">Você também pode agrupar cartões de condição juntos como um bloco (chamado de *grupo de condição*) para criar uma consulta mais complexa.</span><span class="sxs-lookup"><span data-stu-id="00c9e-113">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="00c9e-114">Para obter uma lista e uma descrição das propriedades de metadados que você pode pesquisar, confira os [campos de metadados de documentos na descoberta eletrônica avançada](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="00c9e-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="00c9e-115">Cartões de condição</span><span class="sxs-lookup"><span data-stu-id="00c9e-115">Condition cards</span></span>

<span data-ttu-id="00c9e-116">Cada campo pesquisável em um conjunto de revisão tem um cartão de condição correspondente que você pode usar para criar sua consulta.</span><span class="sxs-lookup"><span data-stu-id="00c9e-116">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="00c9e-117">Há vários tipos de cartões de condição:</span><span class="sxs-lookup"><span data-stu-id="00c9e-117">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="00c9e-118">FREETEXT: um cartão de condição do freetext é usado para campos de texto como o assunto.</span><span class="sxs-lookup"><span data-stu-id="00c9e-118">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="00c9e-119">Você pode listar vários termos de pesquisa separando-os com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="00c9e-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="00c9e-120">Date: um cartão de condição de data é usado para campos de data, como data da última modificação.</span><span class="sxs-lookup"><span data-stu-id="00c9e-120">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="00c9e-121">Opções de pesquisa: um cartão de condição de opções de pesquisa fornecerá uma lista de valores possíveis para o campo específico em seu conjunto de análise.</span><span class="sxs-lookup"><span data-stu-id="00c9e-121">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="00c9e-122">Isso é usado para campos, como remetente, onde há um número finito de valores possíveis em seu conjunto de análise.</span><span class="sxs-lookup"><span data-stu-id="00c9e-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="00c9e-123">Palavra-chave: um cartão de condição de palavra-chave é uma instância específica do cartão de condição FREETEXT que você pode usar para pesquisar termos, ou usar o idioma de consulta do KQL como no.</span><span class="sxs-lookup"><span data-stu-id="00c9e-123">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="00c9e-124">Veja mais detalhes abaixo.</span><span class="sxs-lookup"><span data-stu-id="00c9e-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="00c9e-125">Linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="00c9e-125">Query language</span></span>

<span data-ttu-id="00c9e-126">Além de cartões de condição, você pode usar um idioma de consulta do tipo KQL no cartão de palavras-chave para criar sua consulta.</span><span class="sxs-lookup"><span data-stu-id="00c9e-126">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="00c9e-127">A linguagem de consulta para consultas de conjunto de revisão oferece suporte a operadores booleanos padrão, como **e**, **ou**, e **não**, e **Near**.</span><span class="sxs-lookup"><span data-stu-id="00c9e-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="00c9e-128">Também suporta um curinga de caractere único (?) e um curinga de vários caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="00c9e-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="00c9e-129">Usando filtros</span><span class="sxs-lookup"><span data-stu-id="00c9e-129">Using filters</span></span>

<span data-ttu-id="00c9e-130">Além das consultas que podem ser salvas, você pode usar os filtros de definição de análise para aplicar rapidamente condições adicionais a uma consulta de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="00c9e-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="00c9e-131">Isso ajuda você a refinar ainda mais os resultados exibidos por uma consulta de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="00c9e-131">This helps you further refine the results displayed by a review set query.</span></span>

![Examinar filtros de conjunto](../media/AeDReviewSetFilters.png)

<span data-ttu-id="00c9e-133">Os filtros diferem das consultas de duas maneiras significativas:</span><span class="sxs-lookup"><span data-stu-id="00c9e-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="00c9e-134">Os filtros são transitórios.</span><span class="sxs-lookup"><span data-stu-id="00c9e-134">Filters are transient.</span></span> <span data-ttu-id="00c9e-135">Eles não persistem além da sessão existente.</span><span class="sxs-lookup"><span data-stu-id="00c9e-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="00c9e-136">Em outras palavras, não é possível salvar um filtro.</span><span class="sxs-lookup"><span data-stu-id="00c9e-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="00c9e-137">As consultas são salvas no conjunto de revisão e acessadas sempre que abrir o conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="00c9e-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="00c9e-138">Os filtros são sempre aditivos.</span><span class="sxs-lookup"><span data-stu-id="00c9e-138">Filters are always additive.</span></span> <span data-ttu-id="00c9e-139">Os filtros são aplicados além da consulta do conjunto de análise atual.</span><span class="sxs-lookup"><span data-stu-id="00c9e-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="00c9e-140">A aplicação de uma consulta diferente substituirá os resultados retornados pela consulta atual.</span><span class="sxs-lookup"><span data-stu-id="00c9e-140">Applying a different query will replace the results returned by the current query.</span></span>
