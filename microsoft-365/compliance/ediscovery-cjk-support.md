---
title: Suporte A CJK/Byte Duplo para Advanced eDiscovery
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
description: Saiba como Advanced eDiscovery no Microsoft 365 suporta idiomas chineses, japoneses e coreanos (CJK), que usam um conjunto de caracteres de byte duplo.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926597"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="6ff46-103">Suporte a idiomas CJK para Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6ff46-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="6ff46-104">Advanced eDiscovery suporta idiomas de conjunto de caracteres de byte duplo (eles incluem chinês simplificado, chinês tradicional, japonês e coreano, que são coletivamente conhecidos como idiomas *CJK)* para os seguintes cenários avançados em um conjunto de revisão:</span><span class="sxs-lookup"><span data-stu-id="6ff46-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="6ff46-105">Quando você [consulta os dados em um conjunto de revisão.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="6ff46-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="6ff46-106">Quando você [marca documentos em um conjunto de revisão](tagging-documents.md).</span><span class="sxs-lookup"><span data-stu-id="6ff46-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="6ff46-107">Quando você [analisa dados de caso em um conjunto de](analyzing-data-in-review-set.md) revisão usando a detecção quase duplicada, threading de email e análise de temas.</span><span class="sxs-lookup"><span data-stu-id="6ff46-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="6ff46-108">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="6ff46-108">Frequently asked questions</span></span>

<span data-ttu-id="6ff46-109">**Como criar uma pesquisa para coletar itens que contenham caracteres CJK?**</span><span class="sxs-lookup"><span data-stu-id="6ff46-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="6ff46-110">Você pode usar caracteres CJK para [pesquisas](building-search-queries.md#keyword-searches)de palavra-chave, consultas de [palavra-chave](keyword-queries-and-search-conditions.md) e condições de pesquisa ao pesquisar conteúdo em Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6ff46-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="6ff46-111">A pesquisa de caracteres CJK também é suportada ao pesquisar conteúdo no Core eDiscovery and Content Search.</span><span class="sxs-lookup"><span data-stu-id="6ff46-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="6ff46-112">Fornecemos suporte a CJK para todos os operadores de pesquisa e condições de pesquisa [,](keyword-queries-and-search-conditions.md#search-conditions)incluindo os operadores booleanos **AND**, **OR**, **NOT** e **NEAR**. [](keyword-queries-and-search-conditions.md#search-operators)</span><span class="sxs-lookup"><span data-stu-id="6ff46-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="6ff46-113">Se você tiver certeza de que os locais ou itens de conteúdo contêm caracteres CJK, mas as pesquisas não estão retornando resultados, clique no ícone idioma de consulta-país/região</span><span class="sxs-lookup"><span data-stu-id="6ff46-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Ícone de país/região de idioma de consulta na pesquisa de conteúdo](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="6ff46-115">e selecione o valor de código de cultura de idioma-país correspondente para a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6ff46-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="6ff46-116">O padrão idioma/região é neutro.</span><span class="sxs-lookup"><span data-stu-id="6ff46-116">The default language/region is neutral.</span></span>

<span data-ttu-id="6ff46-117">**Posso pesquisar vários idiomas ao mesmo tempo?**</span><span class="sxs-lookup"><span data-stu-id="6ff46-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="6ff46-118">Depende do cenário de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6ff46-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="6ff46-119">Quando você [consulta dados em um conjunto de](review-set-search.md) revisão no Advanced eDiscovery, você pode pesquisar vários idiomas.</span><span class="sxs-lookup"><span data-stu-id="6ff46-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="6ff46-120">Ao criar [uma pesquisa para coletar dados,](create-search-to-collect-data.md)crie uma pesquisa separada para cada idioma que você está direcionando.</span><span class="sxs-lookup"><span data-stu-id="6ff46-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="6ff46-121">Por exemplo, se você estiver procurando por um documento que contenha chinês e coreano, selecione Chinês para sua primeira consulta e selecione Coreano para sua segunda consulta.</span><span class="sxs-lookup"><span data-stu-id="6ff46-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="6ff46-122">**Não vejo o ícone de idioma de consulta país/região para selecionar um idioma para consultas em um conjunto de revisão. Como posso especificar um idioma de consulta em uma pesquisa de conjunto de revisão?**</span><span class="sxs-lookup"><span data-stu-id="6ff46-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="6ff46-123">Para consultar o conjunto de revisão, você não precisa especificar um idioma de documento.</span><span class="sxs-lookup"><span data-stu-id="6ff46-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="6ff46-124">Advanced eDiscovery detecta automaticamente idiomas de documento quando você adiciona conteúdo a um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="6ff46-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="6ff46-125">Isso ajuda você a otimizar os resultados da consulta em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="6ff46-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="6ff46-126">**Posso ver idiomas detectados em [metadados de arquivo?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="6ff46-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="6ff46-127">Não, você não pode ver idiomas detectados em metadados de arquivo.</span><span class="sxs-lookup"><span data-stu-id="6ff46-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="6ff46-128">**Posso filtrar por idiomas de documento em um conjunto de revisão?**</span><span class="sxs-lookup"><span data-stu-id="6ff46-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="6ff46-129">Não, você não pode filtrar, classificar ou pesquisar por idiomas de documento em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="6ff46-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="6ff46-130">**Essa versão CJK para cenários de conjunto de revisão afetará qualquer um dos meus conjuntos de pesquisa e revisão existentes?**</span><span class="sxs-lookup"><span data-stu-id="6ff46-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="6ff46-131">Não, nenhuma das suas pesquisas e conjuntos de revisão existentes será mudada.</span><span class="sxs-lookup"><span data-stu-id="6ff46-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="6ff46-132">Você não precisa reindexar dados existentes, e os resultados da pesquisa para texto em inglês serão os mesmos.</span><span class="sxs-lookup"><span data-stu-id="6ff46-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="6ff46-133">**Como altero meu idioma de exibição para chinês, japonês ou coreano?**</span><span class="sxs-lookup"><span data-stu-id="6ff46-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="6ff46-134">Para obter informações sobre como alterar o idioma de exibição e o fuso horário, consulte Como definir configurações de idioma e região para [Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span><span class="sxs-lookup"><span data-stu-id="6ff46-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="6ff46-135">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="6ff46-135">Known issues</span></span>

- <span data-ttu-id="6ff46-136">O OCR não dá suporte a caracteres CJK de arquivos de imagem</span><span class="sxs-lookup"><span data-stu-id="6ff46-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="6ff46-137">Arquivos de email (como \*.eml e \*.msg) no exibição [Anotações](view-documents-in-review-set.md#annotate-view) não são suportados para idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="6ff46-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="6ff46-138">O realce de acerto de pesquisa no [exibição Texto](view-documents-in-review-set.md#text-view) não é suportado para idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="6ff46-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="6ff46-139">O [módulo De](using-relevance.md) relevância usado para analisar dados não dá suporte a idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="6ff46-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="6ff46-140">[Os respaldos baseados](managing-holds.md#manage-non-custodial-holds) em consultas não são suportados para idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="6ff46-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>