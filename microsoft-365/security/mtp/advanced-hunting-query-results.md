---
title: Trabalhar com resultados de consulta de busca avançada na proteção contra ameaças da Microsoft
description: Aproveitar ao máximo os resultados da consulta retornados por busca avançada na proteção contra ameaças da Microsoft
keywords: caça avançada, busca de ameaças, caça de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, Kusto, Microsoft 365, proteção contra ameaças da Microsoft, visualização, gráfico, filtros Drill-down
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929067"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="606da-104">Trabalhar com resultados de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="606da-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="606da-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="606da-105">**Applies to:**</span></span>
- <span data-ttu-id="606da-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="606da-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="606da-107">Embora você possa construir suas consultas de [busca avançada](advanced-hunting-overview.md) para retornar informações muito precisas, você também pode trabalhar com os resultados da consulta para obter mais percepção e investigar atividades e indicadores específicos.</span><span class="sxs-lookup"><span data-stu-id="606da-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="606da-108">Você pode executar as seguintes ações nos resultados de consulta:</span><span class="sxs-lookup"><span data-stu-id="606da-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="606da-109">Exibir resultados como uma tabela ou um gráfico</span><span class="sxs-lookup"><span data-stu-id="606da-109">View results as a table or chart</span></span>
- <span data-ttu-id="606da-110">Exportar tabelas e gráficos</span><span class="sxs-lookup"><span data-stu-id="606da-110">Export tables and charts</span></span>
- <span data-ttu-id="606da-111">Aprofundar nas informações detalhadas da entidade</span><span class="sxs-lookup"><span data-stu-id="606da-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="606da-112">Ajustar suas consultas diretamente dos resultados ou aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="606da-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="606da-113">Exibir resultados de consulta como uma tabela ou um gráfico</span><span class="sxs-lookup"><span data-stu-id="606da-113">View query results as a table or chart</span></span>
<span data-ttu-id="606da-114">Por padrão, a busca avançada exibe resultados de consulta como dados tabulares.</span><span class="sxs-lookup"><span data-stu-id="606da-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="606da-115">Você também pode exibir os mesmos dados de um gráfico.</span><span class="sxs-lookup"><span data-stu-id="606da-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="606da-116">A busca avançada é compatível com os seguintes modos de exibição:</span><span class="sxs-lookup"><span data-stu-id="606da-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="606da-117">Tipo de modo de exibição</span><span class="sxs-lookup"><span data-stu-id="606da-117">View type</span></span> | <span data-ttu-id="606da-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="606da-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="606da-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="606da-119">**Table**</span></span> | <span data-ttu-id="606da-120">Exibe os resultados da consulta no formato de tabela</span><span class="sxs-lookup"><span data-stu-id="606da-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="606da-121">**Gráfico de colunas**</span><span class="sxs-lookup"><span data-stu-id="606da-121">**Column chart**</span></span> | <span data-ttu-id="606da-122">Renderiza uma série de itens exclusivos no eixo x como barras verticais cujas alturas representam valores numéricos de outro campo</span><span class="sxs-lookup"><span data-stu-id="606da-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="606da-123">**Gráfico de colunas empilhadas**</span><span class="sxs-lookup"><span data-stu-id="606da-123">**Stacked column chart**</span></span> | <span data-ttu-id="606da-124">Renderiza uma série de itens exclusivos no eixo x como barras verticais empilhadas cujas alturas representam valores numéricos de um ou mais campos</span><span class="sxs-lookup"><span data-stu-id="606da-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="606da-125">**Gráfico de pizza**</span><span class="sxs-lookup"><span data-stu-id="606da-125">**Pie chart**</span></span> | <span data-ttu-id="606da-126">Renderiza tortas de seção que representam itens exclusivos.</span><span class="sxs-lookup"><span data-stu-id="606da-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="606da-127">O tamanho de cada pizza representa valores numéricos de outro campo.</span><span class="sxs-lookup"><span data-stu-id="606da-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="606da-128">**Gráfico de rosca**</span><span class="sxs-lookup"><span data-stu-id="606da-128">**Donut chart**</span></span> | <span data-ttu-id="606da-129">Renderiza arcos de seção que representam itens exclusivos.</span><span class="sxs-lookup"><span data-stu-id="606da-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="606da-130">O comprimento de cada arco representa valores numéricos de outro campo.</span><span class="sxs-lookup"><span data-stu-id="606da-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="606da-131">**Gráfico de linhas**</span><span class="sxs-lookup"><span data-stu-id="606da-131">**Line chart**</span></span> | <span data-ttu-id="606da-132">Plota valores numéricos para uma série de itens exclusivos e conecta os valores plotados</span><span class="sxs-lookup"><span data-stu-id="606da-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="606da-133">**Gráfico de dispersão**</span><span class="sxs-lookup"><span data-stu-id="606da-133">**Scatter chart**</span></span> | <span data-ttu-id="606da-134">Plota valores numéricos para uma série de itens exclusivos</span><span class="sxs-lookup"><span data-stu-id="606da-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="606da-135">**Gráfico de área**</span><span class="sxs-lookup"><span data-stu-id="606da-135">**Area chart**</span></span> | <span data-ttu-id="606da-136">Plota valores numéricos para uma série de itens exclusivos e preenche as seções abaixo dos valores plotados</span><span class="sxs-lookup"><span data-stu-id="606da-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="606da-137">Construir consultas para gráficos efetivos</span><span class="sxs-lookup"><span data-stu-id="606da-137">Construct queries for effective charts</span></span>
<span data-ttu-id="606da-138">Ao renderizar gráficos, a busca avançada identifica automaticamente as colunas de interesse e os valores numéricos a serem agregados.</span><span class="sxs-lookup"><span data-stu-id="606da-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="606da-139">Para obter gráficos significativos, construa suas consultas para retornar os valores específicos que você deseja ver visualizados.</span><span class="sxs-lookup"><span data-stu-id="606da-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="606da-140">Veja algumas consultas de exemplo e os gráficos resultantes.</span><span class="sxs-lookup"><span data-stu-id="606da-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="606da-141">Alertas por severidade</span><span class="sxs-lookup"><span data-stu-id="606da-141">Alerts by severity</span></span>
<span data-ttu-id="606da-142">Use o `summarize` operador para obter uma contagem numérica dos valores que você deseja para o gráfico.</span><span class="sxs-lookup"><span data-stu-id="606da-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="606da-143">A consulta abaixo usa o `summarize` operador para obter o número de alertas por severidade.</span><span class="sxs-lookup"><span data-stu-id="606da-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="606da-144">Ao renderizar os resultados, um gráfico de colunas exibe cada valor de severidade como uma coluna separada:</span><span class="sxs-lookup"><span data-stu-id="606da-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="606da-145">![Imagem dos resultados da consulta de busca avançada exibidos como um](../../media/advanced-hunting-column-chart.jpg)
gráfico de colunas*resultados de consulta para alertas por severidade exibido como gráfico de colunas*</span><span class="sxs-lookup"><span data-stu-id="606da-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="606da-146">Severidade de alerta por sistema operacional</span><span class="sxs-lookup"><span data-stu-id="606da-146">Alert severity by operating system</span></span>
<span data-ttu-id="606da-147">Você também pode usar o `summarize` operador para preparar resultados para valores de gráfico de vários campos.</span><span class="sxs-lookup"><span data-stu-id="606da-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="606da-148">Por exemplo, talvez você queira entender como as severidades de alerta são distribuídas entre OS sistemas operacionais (SO).</span><span class="sxs-lookup"><span data-stu-id="606da-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="606da-149">A consulta a seguir usa `join` um operador para extrair informações de so da `DeviceInfo` tabela e, em seguida `summarize` , usa para contar valores em `OSPlatform` ambas `Severity` as colunas:</span><span class="sxs-lookup"><span data-stu-id="606da-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="606da-150">Esses resultados são mais visualizados usando um gráfico de colunas empilhadas:</span><span class="sxs-lookup"><span data-stu-id="606da-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="606da-151">![Imagem dos resultados da consulta de busca avançada exibidos como um gráfico](../../media/advanced-hunting-stacked-chart.jpg)
empilhado*resultados de consulta para alertas por sistema operacional e severidade exibidos como um gráfico empilhado*</span><span class="sxs-lookup"><span data-stu-id="606da-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="606da-152">Emails de phishing nos dez principais domínios de remetente</span><span class="sxs-lookup"><span data-stu-id="606da-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="606da-153">Se você estiver lidando com uma lista de valores que não é finito, você pode usar `Top` o operador para apenas o gráfico os valores com a maioria das instâncias.</span><span class="sxs-lookup"><span data-stu-id="606da-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="606da-154">Por exemplo, para obter os dez principais domínios de remetente com a maioria dos emails de phishing, use a consulta abaixo:</span><span class="sxs-lookup"><span data-stu-id="606da-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="606da-155">Use o modo de exibição gráfico de pizza para mostrar efetivamente a distribuição nos principais domínios:</span><span class="sxs-lookup"><span data-stu-id="606da-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="606da-156">![Imagem dos resultados da consulta de busca avançada exibidos como gráfico](../../media/advanced-hunting-pie-chart.jpg)
de pizza de gráfico de pizza*mostrando distribuição de emails de phishing nos principais domínios de remetente*</span><span class="sxs-lookup"><span data-stu-id="606da-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="606da-157">Atividades de arquivo ao longo do tempo</span><span class="sxs-lookup"><span data-stu-id="606da-157">File activities over time</span></span>
<span data-ttu-id="606da-158">Usando o `summarize` operador com a `bin()` função, você pode verificar se há eventos que envolvem um indicador específico ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="606da-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="606da-159">A consulta abaixo conta os eventos que envolvem o arquivo `invoice.doc` em intervalos de 30 minutos para mostrar picos de atividade relacionadas a esse arquivo:</span><span class="sxs-lookup"><span data-stu-id="606da-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="606da-160">O gráfico de linhas abaixo realça claramente os períodos de tempo com `invoice.doc`mais atividade envolvendo:</span><span class="sxs-lookup"><span data-stu-id="606da-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="606da-161">![Imagem dos resultados da consulta de busca avançada exibidos como um](../../media/advanced-hunting-line-chart.jpg)
gráfico de linha de gráfico de linhas*mostrando o número de eventos que envolvem um arquivo ao longo do tempo*</span><span class="sxs-lookup"><span data-stu-id="606da-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="606da-162">Exportar tabelas e gráficos</span><span class="sxs-lookup"><span data-stu-id="606da-162">Export tables and charts</span></span>
<span data-ttu-id="606da-163">Após executar uma consulta, selecione **Exportar** para salvar os resultados no arquivo local.</span><span class="sxs-lookup"><span data-stu-id="606da-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="606da-164">O modo de exibição escolhido determina como os resultados são exportados:</span><span class="sxs-lookup"><span data-stu-id="606da-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="606da-165">**Modo de exibição de tabela** : os resultados da consulta são exportados no formato tabular como uma pasta de trabalho do Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="606da-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="606da-166">**Qualquer gráfico** — os resultados da consulta são exportados como uma imagem JPEG do gráfico renderizado</span><span class="sxs-lookup"><span data-stu-id="606da-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="606da-167">Aprofundar a partir de resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="606da-167">Drill down from query results</span></span>
<span data-ttu-id="606da-168">Para ver em seus resultados de consulta mais informações sobre entidades, como máquinas, arquivos, usuários, endereços IP e URLs, simplesmente clique no identificador de entidade.</span><span class="sxs-lookup"><span data-stu-id="606da-168">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="606da-169">Isso abre uma página de perfil detalhada para a entidade selecionada no Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="606da-169">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="606da-170">Ajustar consultas a partir dos resultados</span><span class="sxs-lookup"><span data-stu-id="606da-170">Tweak your queries from the results</span></span>
<span data-ttu-id="606da-171">Clique com o botão direito do mouse em um valor no conjunto de resultados para aprimorar rapidamente a consulta.</span><span class="sxs-lookup"><span data-stu-id="606da-171">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="606da-172">Você pode usar as opções para:</span><span class="sxs-lookup"><span data-stu-id="606da-172">You can use the options to:</span></span>

- <span data-ttu-id="606da-173">Procurar explicitamente pelo valor selecionado (`==`)</span><span class="sxs-lookup"><span data-stu-id="606da-173">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="606da-174">Excluir o valor selecionado da consulta (`!=`)</span><span class="sxs-lookup"><span data-stu-id="606da-174">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="606da-175">Obter operadores mais avançados para adicionar o valor à sua consulta, como `contains`, `starts with` e `ends with`</span><span class="sxs-lookup"><span data-stu-id="606da-175">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Imagem de conjunto de resultados de busca avançada](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="606da-177">Filtrar os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="606da-177">Filter the query results</span></span>
<span data-ttu-id="606da-178">Os filtros exibidos à direita fornecem um resumo do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="606da-178">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="606da-179">Cada coluna tem sua própria seção, que lista os valores distintos encontrados para essa coluna e o número de instâncias.</span><span class="sxs-lookup"><span data-stu-id="606da-179">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="606da-180">Refine sua consulta selecionando os `+` botões `-` ou nos valores que você deseja incluir ou excluir e selecionar **Executar consulta**.</span><span class="sxs-lookup"><span data-stu-id="606da-180">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Imagem do filtro de busca avançada](../../media/advanced-hunting-filter.png)

<span data-ttu-id="606da-182">Depois de aplicar o filtro para modificar e executar a consulta, os resultados serão atualizados de acordo.</span><span class="sxs-lookup"><span data-stu-id="606da-182">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="606da-183">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="606da-183">Related topics</span></span>
- [<span data-ttu-id="606da-184">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="606da-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="606da-185">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="606da-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="606da-186">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="606da-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="606da-187">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="606da-187">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="606da-188">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="606da-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="606da-189">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="606da-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="606da-190">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="606da-190">Custom detections overview</span></span>](custom-detections-overview.md)
