---
title: Suporte de CJK/dobrar bytes para descoberta eletrônica avançada
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
description: Saiba como a descoberta eletrônica avançada no Microsoft 365 suporta idiomas em chinês, japonês e coreano (CJK), que usam um conjunto de caracteres de byte duplo.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626928"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="3cd55-103">Suporte a idiomas CJK para descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="3cd55-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="3cd55-104">A descoberta eletrônica avançada oferece suporte a idiomas de conjunto de caracteres de byte duplo (eles incluem chinês simplificado, chinês tradicional, japonês e coreano, coletivamente conhecidos como idiomas *CJK* ) para os seguintes cenários avançados em um conjunto de análise:</span><span class="sxs-lookup"><span data-stu-id="3cd55-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="3cd55-105">Quando você [consulta os dados em um conjunto de revisão](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="3cd55-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="3cd55-106">Quando você [marca documentos em um conjunto de revisão](tagging-documents.md).</span><span class="sxs-lookup"><span data-stu-id="3cd55-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="3cd55-107">Quando você [analisa dados de caso em um conjunto de revisão usando a](analyzing-data-in-review-set.md) detecção próxima duplicação, encadeamento de email e análise de temas.</span><span class="sxs-lookup"><span data-stu-id="3cd55-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="3cd55-108">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="3cd55-108">Frequently asked questions</span></span>

<span data-ttu-id="3cd55-109">**Como faço para criar uma pesquisa para coletar itens que contenham caracteres CJK?**</span><span class="sxs-lookup"><span data-stu-id="3cd55-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="3cd55-110">Você pode usar caracteres CJK para [pesquisas de palavra-](building-search-queries.md#keyword-searches)chave, [consultas de palavra-chave e condições de pesquisa](keyword-queries-and-search-conditions.md) ao pesquisar conteúdo na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="3cd55-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="3cd55-111">A pesquisa por caracteres CJK também é suportada durante a pesquisa de conteúdo na descoberta eletrônica principal e pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3cd55-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="3cd55-112">Oferecemos suporte a CJK para todos [os operadores de pesquisa](keyword-queries-and-search-conditions.md#search-operators) e condições de [pesquisa](keyword-queries-and-search-conditions.md#search-conditions), incluindo os operadores booleanos **e**, **ou**, **não**e **próximos**.</span><span class="sxs-lookup"><span data-stu-id="3cd55-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="3cd55-113">Se você tiver certeza de que os itens ou os locais de conteúdo contêm caracteres CJK, mas as pesquisas não estão retornando nenhum resultado, clique no ícone idioma da consulta-país/região</span><span class="sxs-lookup"><span data-stu-id="3cd55-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Idioma da consulta-ícone de país/região na pesquisa de conteúdo](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="3cd55-115">e selecione o valor de código de cultura do idioma-país correspondente para a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3cd55-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="3cd55-116">O padrão idioma/região é neutro.</span><span class="sxs-lookup"><span data-stu-id="3cd55-116">The default language/region is neutral.</span></span>

<span data-ttu-id="3cd55-117">**Posso pesquisar vários idiomas de uma só vez?**</span><span class="sxs-lookup"><span data-stu-id="3cd55-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="3cd55-118">Depende do seu cenário de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3cd55-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="3cd55-119">Ao [consultar dados em um conjunto de análise](review-set-search.md) na descoberta eletrônica avançada, você pode pesquisar vários idiomas.</span><span class="sxs-lookup"><span data-stu-id="3cd55-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="3cd55-120">Ao [criar uma pesquisa para coletar dados](create-search-to-collect-data.md), crie uma pesquisa separada para cada idioma para o qual você está direcionado.</span><span class="sxs-lookup"><span data-stu-id="3cd55-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="3cd55-121">Por exemplo, se você estiver procurando um documento que contenha chinês e coreano, selecione chinês para a primeira consulta e selecione coreano para a segunda consulta.</span><span class="sxs-lookup"><span data-stu-id="3cd55-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="3cd55-122">**Não vejo o ícone de idioma de consulta-país/região para selecionar um idioma para consultas em um conjunto de revisão. Como posso especificar um idioma de consulta em uma análise definir pesquisa?**</span><span class="sxs-lookup"><span data-stu-id="3cd55-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="3cd55-123">Para consultas de conjunto de revisão, não é necessário especificar um idioma de documento.</span><span class="sxs-lookup"><span data-stu-id="3cd55-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="3cd55-124">A descoberta eletrônica avançada detecta idiomas de documento automaticamente quando você adiciona conteúdo a um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="3cd55-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="3cd55-125">Isso ajuda a otimizar os resultados da consulta em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="3cd55-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="3cd55-126">**Posso ver os idiomas detectados nos [metadados do arquivo](view-documents-in-review-set.md#file-metadata)?**</span><span class="sxs-lookup"><span data-stu-id="3cd55-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="3cd55-127">Não, não é possível ver idiomas detectados nos metadados do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3cd55-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="3cd55-128">**Posso filtrar por idiomas de documento em um conjunto de revisão**?</span><span class="sxs-lookup"><span data-stu-id="3cd55-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="3cd55-129">Não, não é possível filtrar, classificar ou pesquisar por idiomas de documento em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="3cd55-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="3cd55-130">**Este lançamento CJK para cenários de análise definida afetará qualquer uma das minhas pesquisas existentes e conjuntos de revisão?**</span><span class="sxs-lookup"><span data-stu-id="3cd55-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="3cd55-131">Não, nenhum dos conjuntos de pesquisas e de revisão existentes será alterado.</span><span class="sxs-lookup"><span data-stu-id="3cd55-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="3cd55-132">Você não precisa reindexar os dados existentes e os resultados de pesquisa do texto em inglês serão os mesmos.</span><span class="sxs-lookup"><span data-stu-id="3cd55-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="3cd55-133">**Como altero meu idioma de exibição para chinês, japonês ou coreano?**</span><span class="sxs-lookup"><span data-stu-id="3cd55-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="3cd55-134">Para obter informações sobre como alterar o idioma de exibição e o fuso horário, consulte [como definir configurações de idioma e região para o Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span><span class="sxs-lookup"><span data-stu-id="3cd55-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="3cd55-135">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="3cd55-135">Known issues</span></span>

- <span data-ttu-id="3cd55-136">O OCR não dá suporte a caracteres CJK de arquivos de imagem</span><span class="sxs-lookup"><span data-stu-id="3cd55-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="3cd55-137">Arquivos de email (como \*. eml e \*. msg) no [modo de anotações](view-documents-in-review-set.md#annotate-view) não têm suporte para idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="3cd55-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="3cd55-138">O realce de ocorrências de pesquisa no [modo de texto](view-documents-in-review-set.md#text-view) não tem suporte em idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="3cd55-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="3cd55-139">O [módulo de relevância](using-relevance.md) usado para analisar dados não é compatível com idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="3cd55-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="3cd55-140">Não há suporte para o [bloqueio baseado em consulta](managing-holds.md#manage-non-custodial-holds) em idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="3cd55-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
