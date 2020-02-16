---
title: Conheça a linguagem de consulta de busca avançada no Microsoft Threat Protection
description: Crie sua primeira consulta de busca de ameaças e saiba mais sobre os operadores comuns e outros aspectos da linguagem de consulta de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, idioma, aprendizado, primeira consulta, telemetria, eventos, telemetria, detecções personalizadas, esquema, Kusto, operadores, tipos de dados
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
ms.openlocfilehash: acc515d046b1ebd2ff7c5dd9c52b363fe99f0b9e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087451"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="d8765-104">Conhecer a linguagem de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="d8765-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="d8765-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d8765-105">**Applies to:**</span></span>
- <span data-ttu-id="d8765-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8765-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d8765-107">A caça avançada baseia-se na [linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="d8765-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="d8765-108">Você pode usar a sintaxe e os operadores Kusto para construir consultas que localizem informações no [esquema](advanced-hunting-schema-tables.md) especificamente estruturadas para a pesquisa avançada.</span><span class="sxs-lookup"><span data-stu-id="d8765-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="d8765-109">Para entender melhor esses conceitos, execute a primeira consulta.</span><span class="sxs-lookup"><span data-stu-id="d8765-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="d8765-110">Experimente a primeira consulta</span><span class="sxs-lookup"><span data-stu-id="d8765-110">Try your first query</span></span>

<span data-ttu-id="d8765-111">na central de segurança do Microsoft 365, vá para **procurando** executar a primeira consulta.</span><span class="sxs-lookup"><span data-stu-id="d8765-111">in the Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="d8765-112">Use o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="d8765-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents 
| where Timestamp > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

<span data-ttu-id="d8765-113">Esta é a aparência do aspecto da pesquisa avançada.</span><span class="sxs-lookup"><span data-stu-id="d8765-113">This is how it will look like in advanced hunting.</span></span>

![Imagem da consulta caça avançada do Microsoft defender ATP](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="d8765-115">A consulta começa com um pequeno comentário descrevendo o que é para isso.</span><span class="sxs-lookup"><span data-stu-id="d8765-115">The query starts with a short comment describing what it is for.</span></span> <span data-ttu-id="d8765-116">Isso ajudará se você decidir salvar sua consulta mais tarde e compartilhá-la com outras pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8765-116">This helps if you later decide to save your query and share it with others in your organization.</span></span>

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

<span data-ttu-id="d8765-117">A consulta em si geralmente começará com um nome de tabela seguido de uma série de elementos iniciados por um pipe (`|`).</span><span class="sxs-lookup"><span data-stu-id="d8765-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="d8765-118">Neste exemplo, começamos adicionando com o nome da tabela `DeviceProcessEvents` e adicionar elementos de pipe conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="d8765-118">In this example, we start by adding  with the table name `DeviceProcessEvents` and add piped elements as needed.</span></span>

<span data-ttu-id="d8765-119">O primeiro elemento canalizado é um filtro de tempo delimitado dentro dos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="d8765-119">The first piped element is a time filter scoped within the previous seven days.</span></span> <span data-ttu-id="d8765-120">Manter o intervalo de tempo tão estreito quanto possível garante que as consultas sejam executadas, retornem resultados gerenciáveis e não o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="d8765-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="d8765-121">O intervalo de tempo é imediatamente seguido por uma pesquisa de arquivos que representam o aplicativo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8765-121">The time range is immediately followed by a search for files representing the PowerShell application.</span></span>

```kusto
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

<span data-ttu-id="d8765-122">Em seguida, a consulta procura linhas de comando que normalmente são usadas com o PowerShell para baixar arquivos.</span><span class="sxs-lookup"><span data-stu-id="d8765-122">Afterwards, the query looks for command lines that are typically used with PowerShell to download files.</span></span>

```kusto
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

<span data-ttu-id="d8765-123">Agora que a consulta identifique claramente os dados que você deseja localizar, você pode adicionar elementos que definem a aparência dos resultados.</span><span class="sxs-lookup"><span data-stu-id="d8765-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="d8765-124">`project` retorna colunas específicas e `top` limita o número de resultados, tornando os resultados bem formatados e razoavelmente grandes e fáceis de processar.</span><span class="sxs-lookup"><span data-stu-id="d8765-124">`project` returns specific columns and `top` limits the number of results, making the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

<span data-ttu-id="d8765-125">Clique **executar consulta** para ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="d8765-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="d8765-126">Você pode expandir o modo de exibição de tela para poder se concentrar em sua consulta de busca e nos resultados.</span><span class="sxs-lookup"><span data-stu-id="d8765-126">You can expand the screen view so you can focus on your hunting query and the results.</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="d8765-127">Conheça operadores de consulta comuns para a caça avançada</span><span class="sxs-lookup"><span data-stu-id="d8765-127">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="d8765-128">Agora que você executou a primeira consulta e tem uma ideia geral dos seus componentes, chegou a hora de recapitular um pouco e aprender algumas noções básicas.</span><span class="sxs-lookup"><span data-stu-id="d8765-128">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="d8765-129">A linguagem de consulta Kusto usada por caça avançada oferece suporte a vários operadores, incluindo os seguintes.</span><span class="sxs-lookup"><span data-stu-id="d8765-129">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="d8765-130">Operador</span><span class="sxs-lookup"><span data-stu-id="d8765-130">Operator</span></span> | <span data-ttu-id="d8765-131">Descrição e uso</span><span class="sxs-lookup"><span data-stu-id="d8765-131">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="d8765-132">Filtre uma tabela no subconjunto de linhas que atendem a um predicado.</span><span class="sxs-lookup"><span data-stu-id="d8765-132">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="d8765-133">Produza uma tabela que agrega o conteúdo da tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="d8765-133">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="d8765-134">Mescle as linhas de duas tabelas para formar uma nova tabela, correspondendo valores das colunas especificadas de cada tabela.</span><span class="sxs-lookup"><span data-stu-id="d8765-134">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="d8765-135">Retorne o número de registros no conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="d8765-135">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="d8765-136">Retorne os primeiros registros N classificados pelas colunas especificadas.</span><span class="sxs-lookup"><span data-stu-id="d8765-136">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="d8765-137">Retornar para o número especificado de linhas.</span><span class="sxs-lookup"><span data-stu-id="d8765-137">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="d8765-138">Selecione as colunas a serem incluídas, renomear ou descartar e inserir novas colunas computadas.</span><span class="sxs-lookup"><span data-stu-id="d8765-138">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="d8765-139">Crie colunas calculadas e as acrescente ao conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="d8765-139">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="d8765-140">Retornar uma matriz dinâmica (JSON) do conjunto de valores distintos que Expr assume no grupo.</span><span class="sxs-lookup"><span data-stu-id="d8765-140">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="d8765-141">Localizar linhas que correspondam a um predicado em um conjunto de tabelas.</span><span class="sxs-lookup"><span data-stu-id="d8765-141">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="d8765-142">Para ver um exemplo instantâneo desses operadores, execute-os na seção **começar**, na caça avançada.</span><span class="sxs-lookup"><span data-stu-id="d8765-142">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="d8765-143">Compreenda os tipos de dados e suas implicações de sintaxe de consulta</span><span class="sxs-lookup"><span data-stu-id="d8765-143">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="d8765-144">Os dados em tabelas de caça avançada geralmente são classificados nos seguintes tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="d8765-144">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="d8765-145">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d8765-145">Data type</span></span> | <span data-ttu-id="d8765-146">Implicações de descrição e de consulta</span><span class="sxs-lookup"><span data-stu-id="d8765-146">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="d8765-147">As informações de dados e hora geralmente representam os carimbos de data/hora</span><span class="sxs-lookup"><span data-stu-id="d8765-147">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="d8765-148">Conjunto de caracteres</span><span class="sxs-lookup"><span data-stu-id="d8765-148">Character string</span></span> |
| `bool` | <span data-ttu-id="d8765-149">Verdadeiro ou falso</span><span class="sxs-lookup"><span data-stu-id="d8765-149">True or false</span></span> |
| `int` | <span data-ttu-id="d8765-150">valor numérico de bits de 32</span><span class="sxs-lookup"><span data-stu-id="d8765-150">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="d8765-151">valor numérico de bits de 64</span><span class="sxs-lookup"><span data-stu-id="d8765-151">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="d8765-152">Use consultas de amostra</span><span class="sxs-lookup"><span data-stu-id="d8765-152">Use sample queries</span></span>

<span data-ttu-id="d8765-153">A seção **introdução** fornece algumas consultas simples usando operadores usados com frequência.</span><span class="sxs-lookup"><span data-stu-id="d8765-153">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="d8765-154">Tente executar essas consultas e faça pequenas modificações nelas.</span><span class="sxs-lookup"><span data-stu-id="d8765-154">Try running these queries and making small modifications to them.</span></span>

![Imagem da janela de caça avançada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="d8765-156">Além das amostras básicas de consulta, você também pode acessar [consultas compartilhadas](advanced-hunting-shared-queries.md) para cenários específicos de busca de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d8765-156">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="d8765-157">Explore as consultas compartilhadas, no lado esquerdo da página ou no repositório de consultas do GitHub.</span><span class="sxs-lookup"><span data-stu-id="d8765-157">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="d8765-158">Documentação da linguagem de consulta do Access</span><span class="sxs-lookup"><span data-stu-id="d8765-158">Access query language documentation</span></span>

<span data-ttu-id="d8765-159">Para obter mais informações sobre a linguagem de consulta Kusto e os operadores com suporte, confira [documentação da linguagem de consulta do Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="d8765-159">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8765-160">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d8765-160">Related topics</span></span>
- [<span data-ttu-id="d8765-161">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="d8765-161">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d8765-162">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="d8765-162">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d8765-163">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="d8765-163">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d8765-164">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="d8765-164">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d8765-165">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="d8765-165">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
