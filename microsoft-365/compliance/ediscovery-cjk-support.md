---
title: Suporte a CJK/Byte duplo para Descoberta Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba como a Descoberta Avançada no Microsoft 365 dá suporte a idiomas em chinês, japonês e coreano (CJK), que usam um conjunto de caracteres de dois byte.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626928"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="6c146-103">Suporte à linguagem CJK para Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="6c146-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="6c146-104">A Descoberta Avançada dá suporte a idiomas de conjunto de caracteres de byte duplo (incluem chinês simplificado, chinês tradicional, japonês e coreano, que são coletivamente conhecidos como idiomas *CJK)* para os seguintes cenários avançados em um conjunto de revisão:</span><span class="sxs-lookup"><span data-stu-id="6c146-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="6c146-105">Quando você [consultar os dados em um conjunto de revisão.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="6c146-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="6c146-106">Quando você [marca documentos em um conjunto de revisão.](tagging-documents.md)</span><span class="sxs-lookup"><span data-stu-id="6c146-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="6c146-107">Ao analisar [dados de caso em um conjunto de revisão usando](analyzing-data-in-review-set.md) a detecção quase duplicada, threading de email e análise de temas.</span><span class="sxs-lookup"><span data-stu-id="6c146-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="6c146-108">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="6c146-108">Frequently asked questions</span></span>

<span data-ttu-id="6c146-109">**Como criar uma pesquisa para coletar itens que contenham caracteres CJK?**</span><span class="sxs-lookup"><span data-stu-id="6c146-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="6c146-110">Você pode usar caracteres CJK [](keyword-queries-and-search-conditions.md) para pesquisas de palavra-chave, [](building-search-queries.md#keyword-searches)consultas de palavra-chave e condições de pesquisa ao pesquisar conteúdo na Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="6c146-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="6c146-111">A pesquisa de caracteres CJK também é suportada durante a pesquisa de conteúdo na Descoberta Principal e na Pesquisa de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="6c146-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="6c146-112">Fornecemos suporte A CJK para todos os operadores de pesquisa e condições de pesquisa , incluindo os operadores boolários **AND**, **OR**, **NOT** e **NEAR**. [](keyword-queries-and-search-conditions.md#search-operators) [](keyword-queries-and-search-conditions.md#search-conditions)</span><span class="sxs-lookup"><span data-stu-id="6c146-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="6c146-113">Se você tiver certeza de que os locais ou itens de conteúdo contêm caracteres CJK, mas as pesquisas não estão retornando resultados, clique no ícone de idioma/região da consulta</span><span class="sxs-lookup"><span data-stu-id="6c146-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Ícone de idioma/país/região de consulta na pesquisa de conteúdo](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="6c146-115">e selecione o valor de código de cultura de país/idioma correspondente para a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6c146-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="6c146-116">O padrão idioma/região é neutro.</span><span class="sxs-lookup"><span data-stu-id="6c146-116">The default language/region is neutral.</span></span>

<span data-ttu-id="6c146-117">**Posso pesquisar vários idiomas ao mesmo tempo?**</span><span class="sxs-lookup"><span data-stu-id="6c146-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="6c146-118">Depende do cenário de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6c146-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="6c146-119">Ao consultar [dados em um conjunto de revisão](review-set-search.md) na Descoberta Avançada, você pode pesquisar vários idiomas.</span><span class="sxs-lookup"><span data-stu-id="6c146-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="6c146-120">Ao criar [uma pesquisa para coletar dados,](create-search-to-collect-data.md)crie uma pesquisa separada para cada idioma que você está direcionando.</span><span class="sxs-lookup"><span data-stu-id="6c146-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="6c146-121">Por exemplo, se você estiver procurando um documento que contenha chinês e coreano, selecione chinês para sua primeira consulta e selecione coreano para a segunda consulta.</span><span class="sxs-lookup"><span data-stu-id="6c146-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="6c146-122">**Não vejo o ícone de idioma/país/região de consulta para selecionar um idioma para consultas em um conjunto de revisão. Como posso especificar um idioma de consulta em uma pesquisa de conjunto de revisão?**</span><span class="sxs-lookup"><span data-stu-id="6c146-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="6c146-123">Para consultas de conjunto de revisão, você não precisa especificar um idioma de documento.</span><span class="sxs-lookup"><span data-stu-id="6c146-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="6c146-124">A Descoberta Automática Avançada detecta automaticamente idiomas de documentos quando você adiciona conteúdo a um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="6c146-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="6c146-125">Isso ajuda a otimizar os resultados da consulta em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="6c146-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="6c146-126">**Posso ver idiomas detectados nos [metadados de arquivo?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="6c146-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="6c146-127">Não, você não pode ver idiomas detectados nos metadados do arquivo.</span><span class="sxs-lookup"><span data-stu-id="6c146-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="6c146-128">**Posso filtrar por idiomas de documento em um conjunto de revisão?**</span><span class="sxs-lookup"><span data-stu-id="6c146-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="6c146-129">Não, você não pode filtrar, classificar ou pesquisar por idiomas de documento em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="6c146-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="6c146-130">**Essa versão do CJK para cenários de conjunto de revisão afetará qualquer um dos meus conjuntos de pesquisa e revisão existentes?**</span><span class="sxs-lookup"><span data-stu-id="6c146-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="6c146-131">Não, nenhum dos conjuntos de pesquisa e revisão existentes mudará.</span><span class="sxs-lookup"><span data-stu-id="6c146-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="6c146-132">Você não precisa reindexar dados existentes e os resultados da pesquisa para texto em inglês serão os mesmos.</span><span class="sxs-lookup"><span data-stu-id="6c146-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="6c146-133">**Como altero meu idioma de exibição para chinês, japonês ou coreano?**</span><span class="sxs-lookup"><span data-stu-id="6c146-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="6c146-134">Para saber mais sobre como alterar o idioma de exibição e o fuso horário, confira Como definir configurações de idioma e região para [o Office 365.](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="6c146-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="6c146-135">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="6c146-135">Known issues</span></span>

- <span data-ttu-id="6c146-136">O OCR não dá suporte a caracteres CJK de arquivos de imagem</span><span class="sxs-lookup"><span data-stu-id="6c146-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="6c146-137">Arquivos de email (como \*.eml e \*.msg) na exibição Anotação não são suportados para idiomas CJK. [](view-documents-in-review-set.md#annotate-view)</span><span class="sxs-lookup"><span data-stu-id="6c146-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="6c146-138">O realce de acertos de pesquisa [no visualização](view-documents-in-review-set.md#text-view) texto não é suportado para idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="6c146-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="6c146-139">O [módulo de Relevância](using-relevance.md) usado para analisar dados não dá suporte a linguagens CJK.</span><span class="sxs-lookup"><span data-stu-id="6c146-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="6c146-140">[Não há suporte para retém](managing-holds.md#manage-non-custodial-holds) baseados em consulta para idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="6c146-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
