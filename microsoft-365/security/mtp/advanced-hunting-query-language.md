---
title: Conheça a linguagem de consulta de busca avançada no Microsoft Threat Protection
description: Crie sua primeira consulta de busca de ameaças e saiba mais sobre os operadores comuns e outros aspectos da linguagem de consulta de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, idioma, aprendizado, primeira consulta, telemetria, eventos, telemetria, detecções personalizadas, esquema, Kusto, operadores, tipos de dados, PowerShell baixar, exemplo de consulta
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
ms.openlocfilehash: 7f2cf7f62060774343354467d27b76456f6581fc
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2020
ms.locfileid: "42567021"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="2e1cb-104">Conhecer a linguagem de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="2e1cb-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="2e1cb-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2e1cb-105">**Applies to:**</span></span>
- <span data-ttu-id="2e1cb-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2e1cb-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2e1cb-107">A caça avançada baseia-se na [linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="2e1cb-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="2e1cb-108">Você pode usar a sintaxe e os operadores Kusto para construir consultas que localizem informações no [esquema](advanced-hunting-schema-tables.md) especificamente estruturadas para a pesquisa avançada.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="2e1cb-109">Para entender melhor esses conceitos, execute a primeira consulta.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="2e1cb-110">Experimente a primeira consulta</span><span class="sxs-lookup"><span data-stu-id="2e1cb-110">Try your first query</span></span>

<span data-ttu-id="2e1cb-111">No centro de segurança do Microsoft 365, vá para a **busca** para executar a primeira consulta.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="2e1cb-112">Use o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="2e1cb-112">Use the following example:</span></span>

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

<span data-ttu-id="2e1cb-113">Esta é a aparência do aspecto da pesquisa avançada.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-113">This is how it will look like in advanced hunting.</span></span>

![Imagem da consulta de busca avançada da proteção contra ameaças da Microsoft](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="2e1cb-115">Um breve comentário foi adicionado ao início da consulta para descrever o que ele é.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="2e1cb-116">Isso ajudará se você decidir salvar a consulta mais tarde e compartilhá-la com outras pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-116">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="2e1cb-117">A consulta em si geralmente começará com um nome de tabela seguido de uma série de elementos iniciados por um pipe (`|`).</span><span class="sxs-lookup"><span data-stu-id="2e1cb-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="2e1cb-118">Neste exemplo, começamos criando uma União de duas tabelas `DeviceProcessEvents` e `DeviceNetworkEvents`, e adicionar elementos canalizados, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
<span data-ttu-id="2e1cb-119">O primeiro elemento canalizado é um filtro de tempo com escopo para os sete dias anteriores.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-119">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="2e1cb-120">Manter o intervalo de tempo tão estreito quanto possível garante que as consultas sejam executadas, retornem resultados gerenciáveis e não o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="2e1cb-121">O intervalo de tempo é imediatamente seguido por uma pesquisa por nomes de arquivo de processo que representam o aplicativo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-121">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

<span data-ttu-id="2e1cb-122">Posteriormente, a consulta procura por cadeias de caracteres em linhas de comando que normalmente são usadas para baixar arquivos usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-122">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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
<span data-ttu-id="2e1cb-123">Agora que a consulta identifique claramente os dados que você deseja localizar, você pode adicionar elementos que definem a aparência dos resultados.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="2e1cb-124">`project`retorna colunas específicas e `top` limita o número de resultados, ajudando a garantir que os resultados sejam bem formatados e razoavelmente grandes e fáceis de processar.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-124">`project` returns specific columns and `top` limits the number of results, helping ensure the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="2e1cb-125">Clique **executar consulta** para ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="2e1cb-126">Selecione o ícone de expansão no canto superior direito do editor de consulta para se concentrar na consulta de busca e nos resultados.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-126">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span>

![Imagem do controle de expansão no editor de consulta de busca avançada](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="2e1cb-128">Conheça operadores de consulta comuns para a caça avançada</span><span class="sxs-lookup"><span data-stu-id="2e1cb-128">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="2e1cb-129">Agora que você executou a primeira consulta e tem uma ideia geral dos seus componentes, chegou a hora de recapitular um pouco e aprender algumas noções básicas.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-129">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="2e1cb-130">A linguagem de consulta Kusto usada por caça avançada oferece suporte a vários operadores, incluindo os seguintes.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-130">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="2e1cb-131">Operador</span><span class="sxs-lookup"><span data-stu-id="2e1cb-131">Operator</span></span> | <span data-ttu-id="2e1cb-132">Descrição e uso</span><span class="sxs-lookup"><span data-stu-id="2e1cb-132">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="2e1cb-133">Filtre uma tabela no subconjunto de linhas que atendem a um predicado.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-133">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="2e1cb-134">Produza uma tabela que agrega o conteúdo da tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-134">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="2e1cb-135">Mescle as linhas de duas tabelas para formar uma nova tabela, correspondendo valores das colunas especificadas de cada tabela.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-135">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="2e1cb-136">Retorne o número de registros no conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-136">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="2e1cb-137">Retorne os primeiros registros N classificados pelas colunas especificadas.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-137">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="2e1cb-138">Retornar para o número especificado de linhas.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-138">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="2e1cb-139">Selecione as colunas a serem incluídas, renomear ou descartar e inserir novas colunas computadas.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-139">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="2e1cb-140">Crie colunas calculadas e as acrescente ao conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-140">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="2e1cb-141">Retornar uma matriz dinâmica (JSON) do conjunto de valores distintos que Expr assume no grupo.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-141">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="2e1cb-142">Localizar linhas que correspondam a um predicado em um conjunto de tabelas.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-142">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="2e1cb-143">Para ver um exemplo instantâneo desses operadores, execute-os na seção **começar**, na caça avançada.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-143">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="2e1cb-144">Compreenda os tipos de dados e suas implicações de sintaxe de consulta</span><span class="sxs-lookup"><span data-stu-id="2e1cb-144">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="2e1cb-145">Os dados em tabelas de caça avançada geralmente são classificados nos seguintes tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-145">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="2e1cb-146">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2e1cb-146">Data type</span></span> | <span data-ttu-id="2e1cb-147">Implicações de descrição e de consulta</span><span class="sxs-lookup"><span data-stu-id="2e1cb-147">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="2e1cb-148">As informações de dados e hora geralmente representam os carimbos de data/hora</span><span class="sxs-lookup"><span data-stu-id="2e1cb-148">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="2e1cb-149">Conjunto de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e1cb-149">Character string</span></span> |
| `bool` | <span data-ttu-id="2e1cb-150">Verdadeiro ou falso</span><span class="sxs-lookup"><span data-stu-id="2e1cb-150">True or false</span></span> |
| `int` | <span data-ttu-id="2e1cb-151">valor numérico de bits de 32</span><span class="sxs-lookup"><span data-stu-id="2e1cb-151">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="2e1cb-152">valor numérico de bits de 64</span><span class="sxs-lookup"><span data-stu-id="2e1cb-152">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="2e1cb-153">Use consultas de amostra</span><span class="sxs-lookup"><span data-stu-id="2e1cb-153">Use sample queries</span></span>

<span data-ttu-id="2e1cb-154">A seção **introdução** fornece algumas consultas simples usando operadores usados com frequência.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-154">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="2e1cb-155">Tente executar essas consultas e faça pequenas modificações nelas.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-155">Try running these queries and making small modifications to them.</span></span>

![Imagem da janela de caça avançada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="2e1cb-157">Além das amostras básicas de consulta, você também pode acessar [consultas compartilhadas](advanced-hunting-shared-queries.md) para cenários específicos de busca de ameaças.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-157">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="2e1cb-158">Explore as consultas compartilhadas, no lado esquerdo da página ou no repositório de consultas do GitHub.</span><span class="sxs-lookup"><span data-stu-id="2e1cb-158">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="2e1cb-159">Documentação da linguagem de consulta do Access</span><span class="sxs-lookup"><span data-stu-id="2e1cb-159">Access query language documentation</span></span>

<span data-ttu-id="2e1cb-160">Para obter mais informações sobre a linguagem de consulta Kusto e os operadores com suporte, confira [documentação da linguagem de consulta do Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="2e1cb-160">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2e1cb-161">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2e1cb-161">Related topics</span></span>
- [<span data-ttu-id="2e1cb-162">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="2e1cb-162">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2e1cb-163">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="2e1cb-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2e1cb-164">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="2e1cb-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2e1cb-165">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="2e1cb-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2e1cb-166">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="2e1cb-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
