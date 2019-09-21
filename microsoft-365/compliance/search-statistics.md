---
title: Estatísticas de pesquisa
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
ms.openlocfilehash: c4ac15bcc83fcba7415eb37bccdac2904dcf5d6c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073146"
---
# <a name="search-statistics"></a><span data-ttu-id="e954e-102">Estatísticas de pesquisa</span><span class="sxs-lookup"><span data-stu-id="e954e-102">Search statistics</span></span>

<span data-ttu-id="e954e-103">Uma maneira eficaz de validar seus resultados de pesquisa ao investigar um incidente de dados é exibir as estatísticas sobre seus resultados de pesquisa para garantir que eles se alinhem às suas expectativas.</span><span class="sxs-lookup"><span data-stu-id="e954e-103">An effective way to validate your search results when investigation a data incident is to view the statistics about your search results to make sure they align with your expectations.</span></span> <span data-ttu-id="e954e-104">Quando uma pesquisa de conclusão é executada, as seguintes estatísticas de alto nível são exibidas em **status** na página do submenu detalhes da pesquisa:</span><span class="sxs-lookup"><span data-stu-id="e954e-104">When a search as finished running, the following high-level statistics are displayed under **Status** on the search details flyout page:</span></span>

![Pesquisar statisics na página de submenu detalhes da pesquisa](media/SearchDetailsFlyout.png)

- <span data-ttu-id="e954e-106">O número estimado e o tamanho dos itens que correspondem aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-106">The estimated number and size of items that matched the search criteria.</span></span>

- <span data-ttu-id="e954e-107">O número e o tamanho de itens parcialmente indexados (também chamados de *itens não indexados*) que não são pesquisáveis, mas que foram encontrados nos locais de conteúdo que foram incluídos na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-107">The number and size of partially indexed items (also called *unindexed items*) that aren't searchable but that were found in the content locations that were included in the search.</span></span>

- <span data-ttu-id="e954e-108">O número de caixas de correio e sites que foram pesquisados.</span><span class="sxs-lookup"><span data-stu-id="e954e-108">The number of mailboxes and sites that were searched.</span></span>

<span data-ttu-id="e954e-109">Para exibir estatísticas mais detalhadas, clique em **estatísticas** na página do submenu detalhes da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-109">To view more detailed statistics, click **Statistics** on the search details flyout page.</span></span> <span data-ttu-id="e954e-110">Na página **Estatísticas de pesquisa** , você pode exibir o resumo da pesquisa, o local principal que continha itens que corresponderam aos resultados da pesquisa e estatísticas detalhadas sobre a consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-110">On the **Search statistics** page, you can view the search summary, the top location that contained items that matched the search results, and detailed statistics about the search query.</span></span>

![Lista suspensa de estatísticas de pesquisa](media/SearchStatisticsDropDownList.png)

## <a name="summary"></a><span data-ttu-id="e954e-112">Resumo</span><span class="sxs-lookup"><span data-stu-id="e954e-112">Summary</span></span>

<span data-ttu-id="e954e-113">No modo de exibição de **Resumo** , você pode ver os resultados da pesquisa divididos por tipo de local (por exemplo, locais incluem caixas de correio do Exchange e sites do SharePoint).</span><span class="sxs-lookup"><span data-stu-id="e954e-113">In the **Summary** view, you can see the search results broken down by location type (for example, locations include Exchange mailboxes and SharePoint sites).</span></span> <span data-ttu-id="e954e-114">As informações a seguir são exibidas para cada tipo de local:</span><span class="sxs-lookup"><span data-stu-id="e954e-114">The following information is displayed for each location type:</span></span>

- <span data-ttu-id="e954e-115">O número de locais que tinham itens que corresponderam aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-115">The number of locations that had items that matched the search criteria.</span></span>

- <span data-ttu-id="e954e-116">O número total de itens de cada tipo de local que corresponde aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-116">The total number of items from each location type that matched the search criteria.</span></span>

- <span data-ttu-id="e954e-117">O tamanho total dos itens de cada tipo de local que corresponde aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-117">The total size of items from each location type that matched the search criteria.</span></span>

## <a name="top-locations"></a><span data-ttu-id="e954e-118">Principais locais</span><span class="sxs-lookup"><span data-stu-id="e954e-118">Top locations</span></span>

<span data-ttu-id="e954e-119">No modo de exibição **locais principais** , você vê os locais de conteúdo individuais com a maioria dos itens que corresponderam aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-119">In the **Top locations** view, you see the individual content locations with the most items that matched the search criteria.</span></span> <span data-ttu-id="e954e-120">Para cada local de conteúdo, são exibidas as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="e954e-120">For each content location, the following information is displayed:</span></span>

- <span data-ttu-id="e954e-121">O nome do local; o endereço de email para caixas de correio e a URL para sites do SharePoint</span><span class="sxs-lookup"><span data-stu-id="e954e-121">The name of the location; the email address for mailboxes and the URL for SharePoint sites</span></span>

- <span data-ttu-id="e954e-122">O tipo de local</span><span class="sxs-lookup"><span data-stu-id="e954e-122">The location type</span></span>

- <span data-ttu-id="e954e-123">Número de itens que correspondem aos critérios de pesquisa</span><span class="sxs-lookup"><span data-stu-id="e954e-123">Number of items that matched the search criteria</span></span>

- <span data-ttu-id="e954e-124">O tamanho total de todos os itens que correspondem aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-124">The total size of all items that matched the search criteria.</span></span>

## <a name="queries"></a><span data-ttu-id="e954e-125">Consultas</span><span class="sxs-lookup"><span data-stu-id="e954e-125">Queries</span></span>

<span data-ttu-id="e954e-126">No modo de exibição **consultas** , você pode ver estatísticas detalhadas para cada componente da consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-126">In the **Queries** view, you can see detailed statistics for each component of the search query.</span></span> <span data-ttu-id="e954e-127">Se você usou a lista de palavras-chave na consulta de pesquisa, poderá exibir as estatísticas aprimoradas no modo de exibição **consultas** que mostram quantos itens correspondem a cada palavra-chave ou frase de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="e954e-127">If you used the keyword list in the search query, you can view enhanced statistics in the **Queries** view  that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="e954e-128">Isso pode ajudá-lo a identificar rapidamente quais partes da consulta são as mais (e menos) eficientes.</span><span class="sxs-lookup"><span data-stu-id="e954e-128">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> 

<span data-ttu-id="e954e-129">As informações a seguir são exibidas no modo de exibição de **consultas** :</span><span class="sxs-lookup"><span data-stu-id="e954e-129">The following information is displayed in the **Queries** view:</span></span>

 - <span data-ttu-id="e954e-130">**Tipo de local** -o tipo de local de conteúdo para as estatísticas exibidas na linha.</span><span class="sxs-lookup"><span data-stu-id="e954e-130">**Location type** - The type of content location for the statistics displayed in the row.</span></span>

- <span data-ttu-id="e954e-131">**Parte** -esta coluna exibirá um dos seguintes valores: **Primary** ou **keyword**.</span><span class="sxs-lookup"><span data-stu-id="e954e-131">**Part** - This column will display one of the following values: **Primary** or **Keyword**.</span></span> <span data-ttu-id="e954e-132">**Principal** significa que a linha apresenta estatísticas em toda a consulta; **Palavra-chave** significa que as estatísticas na linha são para um dos componentes de consulta.</span><span class="sxs-lookup"><span data-stu-id="e954e-132">**Primary** means the row presents statistics on the entire query; **Keyword** means the statistics in the row are for one of the query components.</span></span>

- <span data-ttu-id="e954e-133">**Condition** -o componente de consulta real da consulta de pesquisa à qual a linha se refere.</span><span class="sxs-lookup"><span data-stu-id="e954e-133">**Condition** - The actual query component of the search query the row refers to.</span></span> <span data-ttu-id="e954e-134">Se o valor na coluna **parte** for **principal**, as estatísticas para a consulta de pesquisa inteira serão exibidas; Se o valor for **keyword**, as estatísticas do componente da consulta mostrada na coluna de **consulta** serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="e954e-134">If the value in the **Part** column is **Primary**, then the statistics for the entire search query are displayed; if the value is **Keyword**, then the statistics for the component of the query shown in the **Query** column are displayed.</span></span> <span data-ttu-id="e954e-135">Por exemplo, se a lista de palavras-chave foi usada, as estatísticas uma das palavras-chave são exibidas.</span><span class="sxs-lookup"><span data-stu-id="e954e-135">For example, if the keyword list was used, then the statistics one of the keywords are displayed.</span></span>

  <span data-ttu-id="e954e-136">Veja algumas outras coisas que você precisa saber sobre as estatísticas exibidas na coluna **consultas** :</span><span class="sxs-lookup"><span data-stu-id="e954e-136">Here are some other things to know about the statistics displayed in the **Queries** column:</span></span>
  
  - <span data-ttu-id="e954e-137">Quando você procura todo o conteúdo nas caixas de correio (não especificando nenhuma palavra-chave), a consulta real é **(tamanho >= 0)** para que todos os itens sejam retornados</span><span class="sxs-lookup"><span data-stu-id="e954e-137">When you search for all content in mailboxes (by not specifying any keywords), the actual query is **(size >= 0)** so that all items are returned</span></span>
  
  - <span data-ttu-id="e954e-138">Quando você pesquisa sites do SharePoint e do OneDrive, os dois componentes a seguir são adicionados à consulta de pesquisa:</span><span class="sxs-lookup"><span data-stu-id="e954e-138">When you search SharePoint and OneDrive sites, the two following components are added to the search query:</span></span>
    
    <span data-ttu-id="e954e-139">**Não IsExternalContent: 1** -isso exclui qualquer conteúdo de uma organização local do SharePoint</span><span class="sxs-lookup"><span data-stu-id="e954e-139">**NOT IsExternalContent:1** - This excludes any content from an on-premises SharePoint organization</span></span>
    
    <span data-ttu-id="e954e-140">**Não isOneNotePage: 1** -isso exclui todos os arquivos do OneNote porque eles seriam duplicatas de qualquer documento que corresponda à consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-140">**NOT isOneNotePage:1** - This excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="e954e-141">**Locais na pesquisa** O número de locais de conteúdo que tinham itens que corresponderam à consulta de pesquisa da parte/condição exibida na linha.</span><span class="sxs-lookup"><span data-stu-id="e954e-141">**Locations in search** The number of content locations that had items that matched the search query for the part/condition displayed in the row.</span></span> <span data-ttu-id="e954e-142">Observe que as caixas de correio de arquivo morto são contadas como um local separado, caso contenham itens que correspondam aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e954e-142">Note that archive mailboxes are counted as a separate location if they contain items that match the search criteria.</span></span>

- <span data-ttu-id="e954e-143">**Items** -o número total de itens que correspondem aos critérios de pesquisa para a parte/condição exibida na linha.</span><span class="sxs-lookup"><span data-stu-id="e954e-143">**Items** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

- <span data-ttu-id="e954e-144">**Size** -o número total de itens que correspondem aos critérios de pesquisa para a parte/condição exibida na linha.</span><span class="sxs-lookup"><span data-stu-id="e954e-144">**Size** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

