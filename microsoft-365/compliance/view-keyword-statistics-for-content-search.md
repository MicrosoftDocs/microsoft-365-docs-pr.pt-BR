---
title: Exibir estatísticas para resultados de pesquisa de Descobertas EDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Saiba como usar o recurso de estatísticas de pesquisa para exibir estatísticas para pesquisas e pesquisas de conteúdo associadas a um caso de Descoberta Principal de Descoberta Microsoft 365 de conformidade.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311083"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="7de73-103">Exibir estatísticas para resultados de pesquisa de Descobertas EDiscovery</span><span class="sxs-lookup"><span data-stu-id="7de73-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="7de73-104">Depois de criar e executar uma pesquisa de Conteúdo ou uma pesquisa associada a um caso de Descoberta Principal de Descoberta e, você pode exibir estatísticas sobre os resultados estimados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="7de73-105">Isso inclui um resumo dos resultados da pesquisa (semelhante ao resumo dos resultados estimados da pesquisa exibidos na página de sobrevoo de pesquisa), as estatísticas de consulta, como o número de locais de conteúdo com itens que coincidem com a consulta de pesquisa, e a identidade dos locais de conteúdo que têm os itens mais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="7de73-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="7de73-106">Além disso, você pode usar a lista de palavras-chave para configurar uma pesquisa para retornar estatísticas de cada palavra-chave em uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="7de73-107">Isso permite comparar o número de resultados retornados por cada palavra-chave em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="7de73-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="7de73-108">Você também pode baixar estatísticas de pesquisa para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="7de73-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="7de73-109">Isso permite usar os recursos de filtragem e classificação no Excel para comparar resultados e preparar relatórios para os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="7de73-110">Obter estatísticas para pesquisas</span><span class="sxs-lookup"><span data-stu-id="7de73-110">Get statistics for searches</span></span>

<span data-ttu-id="7de73-111">Para exibir estatísticas de uma pesquisa de conteúdo ou uma pesquisa associada a um caso de Descoberta eDiscoveria Principal.:</span><span class="sxs-lookup"><span data-stu-id="7de73-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="7de73-112">No Microsoft 365 de conformidade, clique em **Mostrar tudo** e, em seguida, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7de73-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="7de73-113">Clique **em Pesquisa de** conteúdo e selecione uma pesquisa para exibir a página de sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="7de73-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="7de73-114">OU</span><span class="sxs-lookup"><span data-stu-id="7de73-114">OR</span></span>

   - <span data-ttu-id="7de73-115">Clique **em EDiscovery** Core, selecione uma ocorrência e selecione uma pesquisa na guia Pesquisas para exibir a página  >  de sobrevoo. </span><span class="sxs-lookup"><span data-stu-id="7de73-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="7de73-116">Na página de sobrevoo da pesquisa selecionada, clique na **guia Estatísticas de** pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![A guia Estatísticas de Pesquisa](../media/SearchStatistics1.png)

<span data-ttu-id="7de73-118">A **guia Estatísticas de Pesquisa** contém seções a seguir que contêm diferentes tipos de estatísticas sobre a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="7de73-119">Conteúdo de pesquisa</span><span class="sxs-lookup"><span data-stu-id="7de73-119">Search content</span></span>

<span data-ttu-id="7de73-120">Esta seção exibe um resumo gráfico dos itens estimados retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="7de73-121">Isso indica o número de itens que corresponderem aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="7de73-122">Essas informações dão uma ideia do número estimado de itens retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![Estimativas de pesquisa para uma pesquisa](../media/SearchContentReport.png)

- <span data-ttu-id="7de73-124">**Itens estimados por locais**: O número total de itens estimados retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="7de73-125">O número específico de itens localizados em caixas de correio e localizados em sites também é exibido.</span><span class="sxs-lookup"><span data-stu-id="7de73-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="7de73-126">**Locais estimados com visitas**: O número total de locais de conteúdo que contêm itens retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="7de73-127">O número específico de caixas de correio e locais de site também é exibido.</span><span class="sxs-lookup"><span data-stu-id="7de73-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="7de73-128">**Volume de dados por local (em MB)**: o tamanho total de todos os itens estimados retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="7de73-129">O tamanho específico de itens de caixa de correio e itens de site também é exibido.</span><span class="sxs-lookup"><span data-stu-id="7de73-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="7de73-130">Relatório de condição</span><span class="sxs-lookup"><span data-stu-id="7de73-130">Condition report</span></span>

<span data-ttu-id="7de73-131">Esta seção exibe estatísticas sobre a consulta de pesquisa e o número de itens estimados que corresponderam a diferentes partes da consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="7de73-132">Você pode usar essas estatísticas para analisar o número de itens que corresponderem a cada componente da consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="7de73-133">Isso pode ajudá-lo a refinar os critérios de pesquisa e, se necessário, restringir o escopo do escopo.</span><span class="sxs-lookup"><span data-stu-id="7de73-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="7de73-134">Você também pode baixar uma cópia desse relatório no formato CSV.</span><span class="sxs-lookup"><span data-stu-id="7de73-134">You can also download a copy of this report in CSV format.</span></span>

![Relatório de condição](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="7de73-136">**Tipo de** local : o tipo de local de conteúdo ao qual as estatísticas de consulta são aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="7de73-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="7de73-137">O valor de **Exchange** indica um local de caixa de correio; um valor de **SharePoint** indica um local do site.</span><span class="sxs-lookup"><span data-stu-id="7de73-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="7de73-138">**Parte**: A parte da consulta de pesquisa à que as estatísticas são aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="7de73-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="7de73-139">**O** primário indica toda a consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="7de73-140">**A** palavra-chave indica que as estatísticas na linha são para uma palavra-chave específica.</span><span class="sxs-lookup"><span data-stu-id="7de73-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="7de73-141">Se você usar uma lista de palavras-chave para consulta de pesquisa, as estatísticas de cada componente da consulta serão incluídas nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="7de73-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="7de73-142">Para obter mais informações, consulte [Obter estatísticas de palavra-chave para pesquisas](#get-keyword-statistics-for-searches).</span><span class="sxs-lookup"><span data-stu-id="7de73-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="7de73-143">**Condição**: o componente real (palavra-chave ou condição) da consulta de pesquisa que retornou as estatísticas exibidas na linha correspondente.</span><span class="sxs-lookup"><span data-stu-id="7de73-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="7de73-144">**Locais com hits**: o número dos locais  de conteúdo (especificados pela coluna Tipo de local) que contêm itens que corresponderem à consulta primária ou de palavra-chave listada na **coluna** Condição.</span><span class="sxs-lookup"><span data-stu-id="7de73-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="7de73-145">**Itens**: o número de itens (do local de conteúdo especificado) que combinam com a consulta listada na **coluna Condição.**</span><span class="sxs-lookup"><span data-stu-id="7de73-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="7de73-146">Conforme explicado anteriormente, se um item contiver várias instâncias de uma palavra-chave que está sendo pesquisada, ele só será contado uma vez nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="7de73-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="7de73-147">**Tamanho (MB)**: o tamanho total de todos os itens encontrados (no local de conteúdo especificado) que corresponderem à consulta de pesquisa na **coluna** Condição.</span><span class="sxs-lookup"><span data-stu-id="7de73-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="7de73-148">Principais locais</span><span class="sxs-lookup"><span data-stu-id="7de73-148">Top locations</span></span>

<span data-ttu-id="7de73-149">Esta seção exibe estatísticas sobre os locais de conteúdo específicos com a maioria dos itens retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="7de73-150">Os primeiros 1.000 locais são exibidos.</span><span class="sxs-lookup"><span data-stu-id="7de73-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="7de73-151">Você também pode baixar uma cópia desse relatório no formato CSV.</span><span class="sxs-lookup"><span data-stu-id="7de73-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="7de73-152">O nome do nome do local (o endereço de email das caixas de correio e a URL para sites).</span><span class="sxs-lookup"><span data-stu-id="7de73-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="7de73-153">Tipo de local (uma caixa de correio ou site).</span><span class="sxs-lookup"><span data-stu-id="7de73-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="7de73-154">Número estimado de itens no local de conteúdo retornado pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="7de73-155">O tamanho total dos itens estimados em cada local de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7de73-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="7de73-156">Obter estatísticas de palavra-chave para pesquisas</span><span class="sxs-lookup"><span data-stu-id="7de73-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="7de73-157">Como explicado anteriormente, a seção **Relatório de** condição mostra a consulta de pesquisa e o número (e tamanho) de itens que corresponderem à consulta.</span><span class="sxs-lookup"><span data-stu-id="7de73-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="7de73-158">Se você usar uma lista de palavras-chave ao criar ou editar uma consulta de pesquisa, poderá obter estatísticas avançadas que mostram quantos itens corresponderem a cada palavra-chave ou frase de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="7de73-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="7de73-159">Isso pode ajudá-lo a identificar rapidamente quais partes da consulta são mais (e menos) eficazes.</span><span class="sxs-lookup"><span data-stu-id="7de73-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="7de73-160">Por exemplo, se uma palavra-chave retornar um grande número de itens, você pode optar por refinar a consulta de palavra-chave para restringir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="7de73-161">Para criar uma lista de palavras-chave e exibir estatísticas de palavra-chave para uma pesquisa:</span><span class="sxs-lookup"><span data-stu-id="7de73-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="7de73-162">No centro Microsoft 365 de conformidade, crie uma nova pesquisa de conteúdo ou uma pesquisa associada a um caso de Descoberta Principal de Descoberta e.</span><span class="sxs-lookup"><span data-stu-id="7de73-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="7de73-163">Na página **Condições** do assistente de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="7de73-164">selecione a **caixa de seleção Mostrar lista de palavras-chave.**</span><span class="sxs-lookup"><span data-stu-id="7de73-164">select the **Show keyword list** checkbox.</span></span>

   ![Caixa de seleção Mostrar lista de palavras-chave](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="7de73-166">Digite uma palavra-chave ou uma fase de palavra-chave em uma linha na tabela de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="7de73-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="7de73-167">Por exemplo, digite **orçamento** na primeira linha, digite **segurança** na segunda linha e digite **FY2021** na terceira linha.</span><span class="sxs-lookup"><span data-stu-id="7de73-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![Digite até 20 palavras-chave ou frases de palavra-chave na lista](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="7de73-169">Para ajudar a reduzir problemas causados por listas de palavras-chave grandes, você está limitado a no máximo 20 linhas na lista de palavras-chave de uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="7de73-170">Depois de adicionar as palavras-chave à lista que você deseja pesquisar e obter estatísticas, execute a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="7de73-171">Quando a pesquisa for concluída, selecione-a para exibir a página de sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="7de73-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="7de73-172">Na guia **Estatísticas de Pesquisa,** clique no relatório **Condição** para exibir as estatísticas de palavra-chave da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![As estatísticas de cada palavra-chave são exibidas](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="7de73-174">Conforme mostrado na captura de tela anterior, as estatísticas de cada palavra-chave são exibidas; isso inclui:</span><span class="sxs-lookup"><span data-stu-id="7de73-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="7de73-175">As estatísticas de palavra-chave para cada tipo de local de conteúdo incluído na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="7de73-176">O número de itens de caixa de correio não índicedos.</span><span class="sxs-lookup"><span data-stu-id="7de73-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="7de73-177">A consulta de pesquisa real e os resultados  de cada palavra-chave (identificado como **Palavra-chave** na coluna Parte), que inclui quaisquer condições da consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7de73-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="7de73-178">A consulta de pesquisa completa (identificada como **Primária** na coluna Parte) e as estatísticas da consulta completa para cada tipo de local. </span><span class="sxs-lookup"><span data-stu-id="7de73-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="7de73-179">Observe que estas são as mesmas estatísticas exibidas na **guia Resumo.**</span><span class="sxs-lookup"><span data-stu-id="7de73-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
