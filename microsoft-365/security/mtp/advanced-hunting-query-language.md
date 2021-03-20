---
title: Aprenda a linguagem de consulta de busca avançada no Microsoft 365 Defender
description: Crie sua primeira consulta de busca de ameaças e saiba mais sobre os operadores comuns e outros aspectos da linguagem de consulta de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, idioma, aprender, primeira consulta, telemetria, eventos, telemetria, detecções personalizadas, esquema, kusto, operadores, tipos de dados, download do powershell, exemplo de consulta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f996cd00cc2f7a1f1de2540f1d6686d26431c4f4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904074"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="716d4-104">Conhecer a linguagem de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="716d4-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="716d4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="716d4-105">**Applies to:**</span></span>
- <span data-ttu-id="716d4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="716d4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="716d4-107">A caça avançada baseia-se na [linguagem de consulta Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="716d4-107">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="716d4-108">Você pode usar operadores e instruções kusto para construir consultas que localizem informações em um [esquema especializado.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="716d4-108">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="716d4-109">Para entender melhor esses conceitos, execute a primeira consulta.</span><span class="sxs-lookup"><span data-stu-id="716d4-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="716d4-110">Experimente a primeira consulta</span><span class="sxs-lookup"><span data-stu-id="716d4-110">Try your first query</span></span>

<span data-ttu-id="716d4-111">No Centro de segurança do Microsoft 365, vá até **Hunting** para executar sua primeira consulta.</span><span class="sxs-lookup"><span data-stu-id="716d4-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="716d4-112">Use o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="716d4-112">Use the following example:</span></span>

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

<span data-ttu-id="716d4-113">**[Executar essa consulta em busca avançada](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="716d4-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="716d4-114">Descrever a consulta e especificar as tabelas a ser pesquisadas</span><span class="sxs-lookup"><span data-stu-id="716d4-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="716d4-115">Um breve comentário foi adicionado ao início da consulta para descrever para que ela é.</span><span class="sxs-lookup"><span data-stu-id="716d4-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="716d4-116">Este comentário ajuda se você decidir mais tarde salvar a consulta e compartilhá-la com outras pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="716d4-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="716d4-117">A consulta em si normalmente iniciará com um nome de tabela seguido por vários elementos que começam com um pipe ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="716d4-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="716d4-118">Neste exemplo, começamos criando uma união de duas tabelas e , e adicionamos elementos  `DeviceProcessEvents` `DeviceNetworkEvents` canalados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="716d4-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="716d4-119">Definir o intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="716d4-119">Set the time range</span></span>
<span data-ttu-id="716d4-120">O primeiro elemento canalado é um filtro de tempo com escopo para os sete dias anteriores.</span><span class="sxs-lookup"><span data-stu-id="716d4-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="716d4-121">Limitar o intervalo de tempo ajuda a garantir que as consultas executem bem, retornem resultados gerenciáveis e não se limitem.</span><span class="sxs-lookup"><span data-stu-id="716d4-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="716d4-122">Verificar processos específicos</span><span class="sxs-lookup"><span data-stu-id="716d4-122">Check specific processes</span></span>
<span data-ttu-id="716d4-123">O intervalo de tempo é imediatamente seguido por uma pesquisa de nomes de arquivo de processo que representam o aplicativo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="716d4-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="716d4-124">Pesquisar cadeias de caracteres de comando específicas</span><span class="sxs-lookup"><span data-stu-id="716d4-124">Search for specific command strings</span></span>
<span data-ttu-id="716d4-125">Posteriormente, a consulta procura cadeias de caracteres em linhas de comando que normalmente são usadas para baixar arquivos usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="716d4-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="716d4-126">Personalizar colunas de resultados e comprimento</span><span class="sxs-lookup"><span data-stu-id="716d4-126">Customize result columns and length</span></span> 
<span data-ttu-id="716d4-127">Agora que sua consulta identifica claramente os dados que você deseja localizar, você pode definir a aparência dos resultados.</span><span class="sxs-lookup"><span data-stu-id="716d4-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="716d4-128">`project` retorna colunas específicas e `top` limita o número de resultados.</span><span class="sxs-lookup"><span data-stu-id="716d4-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="716d4-129">Esses operadores ajudam a garantir que os resultados sejam bem formatados e razoavelmente grandes e fáceis de processar.</span><span class="sxs-lookup"><span data-stu-id="716d4-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="716d4-130">Selecione **Executar consulta para** ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="716d4-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="716d4-131">Use o ícone de expansão na parte superior direita do editor de consulta para se concentrar na consulta de busca e nos resultados.</span><span class="sxs-lookup"><span data-stu-id="716d4-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Imagem do controle Expandir no editor de consulta de busca avançada](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="716d4-133">Você pode exibir os resultados da consulta como gráficos e ajustar filtros rapidamente.</span><span class="sxs-lookup"><span data-stu-id="716d4-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="716d4-134">Para obter orientações, [leia sobre como trabalhar com resultados de consulta](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="716d4-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="716d4-135">Saiba mais sobre os operadores de consulta comuns</span><span class="sxs-lookup"><span data-stu-id="716d4-135">Learn common query operators</span></span>

<span data-ttu-id="716d4-136">Você acabou de executar sua primeira consulta e ter uma ideia geral de seus componentes.</span><span class="sxs-lookup"><span data-stu-id="716d4-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="716d4-137">É hora de voltar um pouco e aprender alguns conceitos básicos.</span><span class="sxs-lookup"><span data-stu-id="716d4-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="716d4-138">A linguagem de consulta Kusto usada por caça avançada oferece suporte a vários operadores, incluindo os seguintes.</span><span class="sxs-lookup"><span data-stu-id="716d4-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="716d4-139">Operador</span><span class="sxs-lookup"><span data-stu-id="716d4-139">Operator</span></span> | <span data-ttu-id="716d4-140">Descrição e uso</span><span class="sxs-lookup"><span data-stu-id="716d4-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="716d4-141">Filtre uma tabela no subconjunto de linhas que atendem a um predicado.</span><span class="sxs-lookup"><span data-stu-id="716d4-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="716d4-142">Produza uma tabela que agrega o conteúdo da tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="716d4-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="716d4-143">Mescle as linhas de duas tabelas para formar uma nova tabela, correspondendo valores das colunas especificadas de cada tabela.</span><span class="sxs-lookup"><span data-stu-id="716d4-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="716d4-144">Retorne o número de registros no conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="716d4-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="716d4-145">Retorne os primeiros registros N classificados pelas colunas especificadas.</span><span class="sxs-lookup"><span data-stu-id="716d4-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="716d4-146">Retornar para o número especificado de linhas.</span><span class="sxs-lookup"><span data-stu-id="716d4-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="716d4-147">Selecione as colunas a serem incluídas, renomear ou descartar e inserir novas colunas computadas.</span><span class="sxs-lookup"><span data-stu-id="716d4-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="716d4-148">Crie colunas calculadas e as acrescente ao conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="716d4-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="716d4-149">Retornar uma matriz dinâmica (JSON) do conjunto de valores distintos que Expr assume no grupo.</span><span class="sxs-lookup"><span data-stu-id="716d4-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="716d4-150">Localizar linhas que correspondam a um predicado em um conjunto de tabelas.</span><span class="sxs-lookup"><span data-stu-id="716d4-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="716d4-151">Para ver um exemplo instantâneo desses operadores, execute-os na seção **começar**, na caça avançada.</span><span class="sxs-lookup"><span data-stu-id="716d4-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="716d4-152">Compreender tipos de dados</span><span class="sxs-lookup"><span data-stu-id="716d4-152">Understand data types</span></span>

<span data-ttu-id="716d4-153">A busca avançada dá suporte a tipos de dados Kusto, incluindo os seguintes tipos comuns:</span><span class="sxs-lookup"><span data-stu-id="716d4-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="716d4-154">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="716d4-154">Data type</span></span> | <span data-ttu-id="716d4-155">Implicações de descrição e de consulta</span><span class="sxs-lookup"><span data-stu-id="716d4-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="716d4-156">As informações de dados e de hora geralmente representam os datas-hora do evento.</span><span class="sxs-lookup"><span data-stu-id="716d4-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="716d4-157">Consulte formatos de data/hora suportados</span><span class="sxs-lookup"><span data-stu-id="716d4-157">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="716d4-158">Cadeia de caracteres em UTF-8 entre aspas simples ( `'` ) ou aspas duplas ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="716d4-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="716d4-159">Leia mais sobre cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="716d4-159">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="716d4-160">Esse tipo de dados dá suporte `true` ou `false` estados.</span><span class="sxs-lookup"><span data-stu-id="716d4-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="716d4-161">Consulte literais e operadores com suporte</span><span class="sxs-lookup"><span data-stu-id="716d4-161">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="716d4-162">Inteiro de 32 bits</span><span class="sxs-lookup"><span data-stu-id="716d4-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="716d4-163">Inteiro de 64 bits</span><span class="sxs-lookup"><span data-stu-id="716d4-163">64-bit integer</span></span> |

<span data-ttu-id="716d4-164">Para saber mais sobre esses tipos de dados, leia sobre tipos de dados [escalares do Kusto.](/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="716d4-164">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="716d4-165">Obter ajuda durante a criação de consultas</span><span class="sxs-lookup"><span data-stu-id="716d4-165">Get help as you write queries</span></span>
<span data-ttu-id="716d4-166">Aproveite as funcionalidades a seguir para escrever rapidamente as consultas:</span><span class="sxs-lookup"><span data-stu-id="716d4-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="716d4-167">**Autosuggest**— à medida que você escreve consultas, a busca avançada fornece sugestões de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="716d4-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="716d4-168">**Árvore de esquema**— uma representação de esquema que inclui a lista de tabelas e suas colunas é fornecida ao lado da sua área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="716d4-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="716d4-169">Para saber mais, passe o mouse sobre um item.</span><span class="sxs-lookup"><span data-stu-id="716d4-169">For more information, hover over an item.</span></span> <span data-ttu-id="716d4-170">Clique duas vezes em um item para inseri-lo no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="716d4-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="716d4-171">**[Referência de esquema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— referência no portal com descrições de tabela e coluna, bem como tipos de eventos com suporte `ActionType` (valores) e consultas de exemplo</span><span class="sxs-lookup"><span data-stu-id="716d4-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="716d4-172">Trabalhar com várias consultas no editor</span><span class="sxs-lookup"><span data-stu-id="716d4-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="716d4-173">Você pode usar o editor de consulta para experimentar várias consultas.</span><span class="sxs-lookup"><span data-stu-id="716d4-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="716d4-174">Para usar várias consultas:</span><span class="sxs-lookup"><span data-stu-id="716d4-174">To use multiple queries:</span></span>

- <span data-ttu-id="716d4-175">Separe cada consulta com uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="716d4-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="716d4-176">Coloque o cursor em qualquer parte de uma consulta para selecionar essa consulta antes de ser executado.</span><span class="sxs-lookup"><span data-stu-id="716d4-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="716d4-177">Isso executará apenas a consulta selecionada.</span><span class="sxs-lookup"><span data-stu-id="716d4-177">This will run only the selected query.</span></span> <span data-ttu-id="716d4-178">Para executar outra consulta, mova o cursor de acordo e selecione **Executar consulta**.</span><span class="sxs-lookup"><span data-stu-id="716d4-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Imagem do editor de consulta com várias consultas](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="716d4-180">Use consultas de amostra</span><span class="sxs-lookup"><span data-stu-id="716d4-180">Use sample queries</span></span>

<span data-ttu-id="716d4-181">A seção **introdução** fornece algumas consultas simples usando operadores usados com frequência.</span><span class="sxs-lookup"><span data-stu-id="716d4-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="716d4-182">Tente executar essas consultas e faça pequenas modificações nelas.</span><span class="sxs-lookup"><span data-stu-id="716d4-182">Try running these queries and making small modifications to them.</span></span>

![Imagem da janela de caça avançada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="716d4-184">Além das amostras básicas de consulta, você também pode acessar [consultas compartilhadas](advanced-hunting-shared-queries.md) para cenários específicos de busca de ameaças.</span><span class="sxs-lookup"><span data-stu-id="716d4-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="716d4-185">Explore as consultas compartilhadas no lado esquerdo da página ou no [repositório de consulta do GitHub.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="716d4-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="716d4-186">Documentação da linguagem de consulta do Access</span><span class="sxs-lookup"><span data-stu-id="716d4-186">Access query language documentation</span></span>

<span data-ttu-id="716d4-187">Para obter mais informações sobre a linguagem de consulta Kusto e os operadores com suporte, confira [documentação da linguagem de consulta do Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="716d4-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="716d4-188">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="716d4-188">Related topics</span></span>
- [<span data-ttu-id="716d4-189">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="716d4-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="716d4-190">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="716d4-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="716d4-191">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="716d4-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="716d4-192">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="716d4-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="716d4-193">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="716d4-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="716d4-194">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="716d4-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)