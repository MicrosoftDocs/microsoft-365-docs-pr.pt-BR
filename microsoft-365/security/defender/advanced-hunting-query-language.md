---
title: Aprenda a linguagem de consulta de busca avançada no Microsoft 365 Defender
description: Crie sua primeira consulta de busca de ameaças e saiba mais sobre os operadores comuns e outros aspectos da linguagem de consulta de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, idioma, aprender, primeira consulta, telemetria, eventos, telemetria, detecções personalizadas, esquema, kusto, operadores, tipos de dados, download do powershell, exemplo de consulta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 14287fb6dea9dda8accb580246b383f0427c3b3f
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952615"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="449dd-104">Conhecer a linguagem de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="449dd-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="449dd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="449dd-105">**Applies to:**</span></span>
- <span data-ttu-id="449dd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="449dd-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="449dd-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="449dd-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="449dd-108">A caça avançada baseia-se na [linguagem de consulta Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="449dd-108">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="449dd-109">Você pode usar operadores e instruções kusto para construir consultas que localizem informações em um [esquema especializado.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="449dd-109">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="449dd-110">Para entender melhor esses conceitos, execute a primeira consulta.</span><span class="sxs-lookup"><span data-stu-id="449dd-110">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="449dd-111">Experimente a primeira consulta</span><span class="sxs-lookup"><span data-stu-id="449dd-111">Try your first query</span></span>

<span data-ttu-id="449dd-112">No Centro de segurança do Microsoft 365, vá até **Hunting** para executar sua primeira consulta.</span><span class="sxs-lookup"><span data-stu-id="449dd-112">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="449dd-113">Use o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="449dd-113">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="449dd-114">**[Executar essa consulta em busca avançada](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="449dd-114">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="449dd-115">Descrever a consulta e especificar as tabelas a ser pesquisadas</span><span class="sxs-lookup"><span data-stu-id="449dd-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="449dd-116">Um breve comentário foi adicionado ao início da consulta para descrever para que ela é.</span><span class="sxs-lookup"><span data-stu-id="449dd-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="449dd-117">Este comentário ajuda se você decidir mais tarde salvar a consulta e compartilhá-la com outras pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="449dd-117">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="449dd-118">A consulta em si normalmente iniciará com um nome de tabela seguido por vários elementos que começam com um pipe ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="449dd-118">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="449dd-119">Neste exemplo, começamos criando uma união de duas tabelas e , e adicionamos elementos  `DeviceProcessEvents` `DeviceNetworkEvents` canalados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="449dd-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="449dd-120">Definir o intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="449dd-120">Set the time range</span></span>
<span data-ttu-id="449dd-121">O primeiro elemento canalado é um filtro de tempo com escopo para os sete dias anteriores.</span><span class="sxs-lookup"><span data-stu-id="449dd-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="449dd-122">Limitar o intervalo de tempo ajuda a garantir que as consultas executem bem, retornem resultados gerenciáveis e não se limitem.</span><span class="sxs-lookup"><span data-stu-id="449dd-122">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="449dd-123">Verificar processos específicos</span><span class="sxs-lookup"><span data-stu-id="449dd-123">Check specific processes</span></span>
<span data-ttu-id="449dd-124">O intervalo de tempo é imediatamente seguido por uma pesquisa de nomes de arquivo de processo que representam o aplicativo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="449dd-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="449dd-125">Pesquisar cadeias de caracteres de comando específicas</span><span class="sxs-lookup"><span data-stu-id="449dd-125">Search for specific command strings</span></span>
<span data-ttu-id="449dd-126">Posteriormente, a consulta procura cadeias de caracteres em linhas de comando que normalmente são usadas para baixar arquivos usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="449dd-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="449dd-127">Personalizar colunas de resultados e comprimento</span><span class="sxs-lookup"><span data-stu-id="449dd-127">Customize result columns and length</span></span> 
<span data-ttu-id="449dd-128">Agora que sua consulta identifica claramente os dados que você deseja localizar, você pode definir a aparência dos resultados.</span><span class="sxs-lookup"><span data-stu-id="449dd-128">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="449dd-129">`project` retorna colunas específicas e `top` limita o número de resultados.</span><span class="sxs-lookup"><span data-stu-id="449dd-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="449dd-130">Esses operadores ajudam a garantir que os resultados sejam bem formatados e razoavelmente grandes e fáceis de processar.</span><span class="sxs-lookup"><span data-stu-id="449dd-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="449dd-131">Selecione **Executar consulta para** ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="449dd-131">Select **Run query** to see the results.</span></span> <span data-ttu-id="449dd-132">Use o ícone de expansão na parte superior direita do editor de consulta para se concentrar na consulta de busca e nos resultados.</span><span class="sxs-lookup"><span data-stu-id="449dd-132">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Imagem do controle Expandir no editor de consulta de busca avançada](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="449dd-134">Você pode exibir os resultados da consulta como gráficos e ajustar filtros rapidamente.</span><span class="sxs-lookup"><span data-stu-id="449dd-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="449dd-135">Para obter orientações, [leia sobre como trabalhar com resultados de consulta](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="449dd-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="449dd-136">Saiba mais sobre os operadores de consulta comuns</span><span class="sxs-lookup"><span data-stu-id="449dd-136">Learn common query operators</span></span>

<span data-ttu-id="449dd-137">Você acabou de executar sua primeira consulta e ter uma ideia geral de seus componentes.</span><span class="sxs-lookup"><span data-stu-id="449dd-137">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="449dd-138">É hora de voltar um pouco e aprender alguns conceitos básicos.</span><span class="sxs-lookup"><span data-stu-id="449dd-138">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="449dd-139">A linguagem de consulta Kusto usada por caça avançada oferece suporte a vários operadores, incluindo os seguintes.</span><span class="sxs-lookup"><span data-stu-id="449dd-139">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="449dd-140">Operador</span><span class="sxs-lookup"><span data-stu-id="449dd-140">Operator</span></span> | <span data-ttu-id="449dd-141">Descrição e uso</span><span class="sxs-lookup"><span data-stu-id="449dd-141">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="449dd-142">Filtre uma tabela no subconjunto de linhas que atendem a um predicado.</span><span class="sxs-lookup"><span data-stu-id="449dd-142">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="449dd-143">Produza uma tabela que agrega o conteúdo da tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="449dd-143">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="449dd-144">Mescle as linhas de duas tabelas para formar uma nova tabela, correspondendo valores das colunas especificadas de cada tabela.</span><span class="sxs-lookup"><span data-stu-id="449dd-144">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="449dd-145">Retorne o número de registros no conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="449dd-145">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="449dd-146">Retorne os primeiros registros N classificados pelas colunas especificadas.</span><span class="sxs-lookup"><span data-stu-id="449dd-146">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="449dd-147">Retornar para o número especificado de linhas.</span><span class="sxs-lookup"><span data-stu-id="449dd-147">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="449dd-148">Selecione as colunas a serem incluídas, renomear ou descartar e inserir novas colunas computadas.</span><span class="sxs-lookup"><span data-stu-id="449dd-148">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="449dd-149">Crie colunas calculadas e as acrescente ao conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="449dd-149">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="449dd-150">Retornar uma matriz dinâmica (JSON) do conjunto de valores distintos que Expr assume no grupo.</span><span class="sxs-lookup"><span data-stu-id="449dd-150">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="449dd-151">Localizar linhas que correspondam a um predicado em um conjunto de tabelas.</span><span class="sxs-lookup"><span data-stu-id="449dd-151">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="449dd-152">Para ver um exemplo instantâneo desses operadores, execute-os na seção **começar**, na caça avançada.</span><span class="sxs-lookup"><span data-stu-id="449dd-152">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="449dd-153">Compreender tipos de dados</span><span class="sxs-lookup"><span data-stu-id="449dd-153">Understand data types</span></span>

<span data-ttu-id="449dd-154">A busca avançada dá suporte a tipos de dados Kusto, incluindo os seguintes tipos comuns:</span><span class="sxs-lookup"><span data-stu-id="449dd-154">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="449dd-155">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="449dd-155">Data type</span></span> | <span data-ttu-id="449dd-156">Implicações de descrição e de consulta</span><span class="sxs-lookup"><span data-stu-id="449dd-156">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="449dd-157">As informações de dados e de hora geralmente representam os datas-hora do evento.</span><span class="sxs-lookup"><span data-stu-id="449dd-157">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="449dd-158">Consulte formatos de data/hora suportados</span><span class="sxs-lookup"><span data-stu-id="449dd-158">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="449dd-159">Cadeia de caracteres em UTF-8 entre aspas simples ( `'` ) ou aspas duplas ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="449dd-159">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="449dd-160">Leia mais sobre cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="449dd-160">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="449dd-161">Esse tipo de dados dá suporte `true` ou `false` estados.</span><span class="sxs-lookup"><span data-stu-id="449dd-161">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="449dd-162">Consulte literais e operadores com suporte</span><span class="sxs-lookup"><span data-stu-id="449dd-162">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="449dd-163">Inteiro de 32 bits</span><span class="sxs-lookup"><span data-stu-id="449dd-163">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="449dd-164">Inteiro de 64 bits</span><span class="sxs-lookup"><span data-stu-id="449dd-164">64-bit integer</span></span> |

<span data-ttu-id="449dd-165">Para saber mais sobre esses tipos de dados, leia sobre tipos de dados [escalares do Kusto.](/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="449dd-165">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="449dd-166">Obter ajuda durante a criação de consultas</span><span class="sxs-lookup"><span data-stu-id="449dd-166">Get help as you write queries</span></span>
<span data-ttu-id="449dd-167">Aproveite as funcionalidades a seguir para escrever rapidamente as consultas:</span><span class="sxs-lookup"><span data-stu-id="449dd-167">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="449dd-168">**Autosuggest**— à medida que você escreve consultas, a busca avançada fornece sugestões de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="449dd-168">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="449dd-169">**Árvore de esquema**— uma representação de esquema que inclui a lista de tabelas e suas colunas é fornecida ao lado da sua área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="449dd-169">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="449dd-170">Para saber mais, passe o mouse sobre um item.</span><span class="sxs-lookup"><span data-stu-id="449dd-170">For more information, hover over an item.</span></span> <span data-ttu-id="449dd-171">Clique duas vezes em um item para inseri-lo no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="449dd-171">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="449dd-172">**[Referência de esquema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— referência no portal com descrições de tabela e coluna, bem como tipos de eventos com suporte `ActionType` (valores) e consultas de exemplo</span><span class="sxs-lookup"><span data-stu-id="449dd-172">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="449dd-173">Trabalhar com várias consultas no editor</span><span class="sxs-lookup"><span data-stu-id="449dd-173">Work with multiple queries in the editor</span></span>
<span data-ttu-id="449dd-174">Você pode usar o editor de consulta para experimentar várias consultas.</span><span class="sxs-lookup"><span data-stu-id="449dd-174">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="449dd-175">Para usar várias consultas:</span><span class="sxs-lookup"><span data-stu-id="449dd-175">To use multiple queries:</span></span>

- <span data-ttu-id="449dd-176">Separe cada consulta com uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="449dd-176">Separate each query with an empty line.</span></span>
- <span data-ttu-id="449dd-177">Coloque o cursor em qualquer parte de uma consulta para selecionar essa consulta antes de ser executado.</span><span class="sxs-lookup"><span data-stu-id="449dd-177">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="449dd-178">Isso executará apenas a consulta selecionada.</span><span class="sxs-lookup"><span data-stu-id="449dd-178">This will run only the selected query.</span></span> <span data-ttu-id="449dd-179">Para executar outra consulta, mova o cursor de acordo e selecione **Executar consulta**.</span><span class="sxs-lookup"><span data-stu-id="449dd-179">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Imagem do editor de consulta com várias consultas](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="449dd-181">Use consultas de amostra</span><span class="sxs-lookup"><span data-stu-id="449dd-181">Use sample queries</span></span>

<span data-ttu-id="449dd-182">A seção **introdução** fornece algumas consultas simples usando operadores usados com frequência.</span><span class="sxs-lookup"><span data-stu-id="449dd-182">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="449dd-183">Tente executar essas consultas e faça pequenas modificações nelas.</span><span class="sxs-lookup"><span data-stu-id="449dd-183">Try running these queries and making small modifications to them.</span></span>

![Imagem da janela de caça avançada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="449dd-185">Além das amostras básicas de consulta, você também pode acessar [consultas compartilhadas](advanced-hunting-shared-queries.md) para cenários específicos de busca de ameaças.</span><span class="sxs-lookup"><span data-stu-id="449dd-185">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="449dd-186">Explore as consultas compartilhadas no lado esquerdo da página ou no [repositório de consulta do GitHub.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="449dd-186">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="449dd-187">Documentação da linguagem de consulta do Access</span><span class="sxs-lookup"><span data-stu-id="449dd-187">Access query language documentation</span></span>

<span data-ttu-id="449dd-188">Para obter mais informações sobre a linguagem de consulta Kusto e os operadores com suporte, confira [documentação da linguagem de consulta do Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="449dd-188">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

>[!NOTE]
><span data-ttu-id="449dd-189">Algumas tabelas neste artigo podem não estar disponíveis no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="449dd-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="449dd-190">[A turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span><span class="sxs-lookup"><span data-stu-id="449dd-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="449dd-191">Você pode mover seus fluxos de trabalho de busca avançados do Microsoft Defender para o Endpoint para o Microsoft 365 Defender seguindo as etapas em Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de [Extremidade.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="449dd-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="449dd-192">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="449dd-192">Related topics</span></span>
- [<span data-ttu-id="449dd-193">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="449dd-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="449dd-194">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="449dd-194">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="449dd-195">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="449dd-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="449dd-196">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="449dd-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="449dd-197">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="449dd-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="449dd-198">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="449dd-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)