---
title: Práticas recomendadas para busca avançada na Proteção contra Ameaças da Microsoft
description: Aprenda a criar consultas de busca de ameaças rápidas, eficientes e sem erros ao usar a busca avançada
keywords: busca avançada, busca de ameaças, busca por ameaças cibernéticas, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, evite o tempo limite, linhas de comando, id do processo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 871f659074c4f8386746e341db4d3500c5e80a31
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807000"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="43d6b-104">Práticas recomendadas de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="43d6b-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="43d6b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="43d6b-105">**Applies to:**</span></span>
- <span data-ttu-id="43d6b-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="43d6b-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="optimize-query-performance"></a><span data-ttu-id="43d6b-107">Obter o melhor resultado possível numa consulta</span><span class="sxs-lookup"><span data-stu-id="43d6b-107">Optimize query performance</span></span>
<span data-ttu-id="43d6b-108">Aplique essas recomendações para obter resultados mais rapidamente e evitar tempos limite enquanto executa consultas complexas:</span><span class="sxs-lookup"><span data-stu-id="43d6b-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="43d6b-109">Ao experimentar novas consultas, use sempre `limit` para evitar conjuntos de resultados grandes demais.</span><span class="sxs-lookup"><span data-stu-id="43d6b-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="43d6b-110">Você também pode avaliar inicialmente o tamanho do conjunto de resultados usando `count`.</span><span class="sxs-lookup"><span data-stu-id="43d6b-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="43d6b-111">Use primeiro os filtros de tempo.</span><span class="sxs-lookup"><span data-stu-id="43d6b-111">Use time filters first.</span></span> <span data-ttu-id="43d6b-112">O ideal é limitar as suas consultas aos dias pares ou alternados.</span><span class="sxs-lookup"><span data-stu-id="43d6b-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="43d6b-113">Coloque os filtros passíveis de remover a maior parte dos dados no início da consulta, imediatamente após o filtro de tempo.</span><span class="sxs-lookup"><span data-stu-id="43d6b-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="43d6b-114">Use o operador `has` sobre `contains` ao procurar tokens completos.</span><span class="sxs-lookup"><span data-stu-id="43d6b-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="43d6b-115">Examine uma coluna específica, em vez de executar pesquisas de texto completo em todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="43d6b-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="43d6b-116">Ao adicionar tabelas, especifique primeiro a tabela com menos linhas.</span><span class="sxs-lookup"><span data-stu-id="43d6b-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="43d6b-117">`project` somente as colunas necessárias das tabelas que adicionou.</span><span class="sxs-lookup"><span data-stu-id="43d6b-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="43d6b-118">Para obter mais informações sobre como melhorar o desempenho da consulta, leia [ práticas recomendadas de consulta no Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="43d6b-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="43d6b-119">Dicas de consulta e armadilhas</span><span class="sxs-lookup"><span data-stu-id="43d6b-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="43d6b-120">Consultas com IDs de processo</span><span class="sxs-lookup"><span data-stu-id="43d6b-120">Queries with process IDs</span></span>
<span data-ttu-id="43d6b-121">As IDs de processo (PIDs) são recicladas no Windows e reutilizadas para novos processos.</span><span class="sxs-lookup"><span data-stu-id="43d6b-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="43d6b-122">Por si só, eles não servem como identificadores exclusivos para processos específicos.</span><span class="sxs-lookup"><span data-stu-id="43d6b-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="43d6b-123">Para obter um identificador exclusivo para um processo em um computador específico, use a ID do processo juntamente com o tempo de criação do processo.</span><span class="sxs-lookup"><span data-stu-id="43d6b-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="43d6b-124">Ao juntar ou resumir dados em um processo, inclua colunas para o identificador da máquina (`DeviceId` ou `DeviceName`), a ID do processo (`ProcessId` ou `InitiatingProcessId`) e o tempo de criação do processo (`ProcessCreationTime` ou `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="43d6b-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="43d6b-125">O exemplo de consulta a seguir localiza processos que acessam mais de 10 endereços IP na porta 445 (SMB), possivelmente procurando por compartilhamentos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="43d6b-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="43d6b-126">Exemplo de consulta:</span><span class="sxs-lookup"><span data-stu-id="43d6b-126">Example query:</span></span>
```
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="43d6b-127">A consulta é resumida por tanto `InitiatingProcessId` quanto`InitiatingProcessCreationTime` para que ela examine um único processo, sem misturar vários processos com a mesma ID de processo.</span><span class="sxs-lookup"><span data-stu-id="43d6b-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="43d6b-128">Consultas com linhas de comando</span><span class="sxs-lookup"><span data-stu-id="43d6b-128">Queries with command lines</span></span>

<span data-ttu-id="43d6b-129">As linhas de comando podem variar.</span><span class="sxs-lookup"><span data-stu-id="43d6b-129">Command lines can vary.</span></span> <span data-ttu-id="43d6b-130">Quando aplicável, filtre os nomes dos arquivos e realize correspondência difusa.</span><span class="sxs-lookup"><span data-stu-id="43d6b-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="43d6b-131">Há várias maneiras de criar uma linha de comando para executar uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="43d6b-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="43d6b-132">Por exemplo, um invasor pode fazer referência a um arquivo de imagem com ou sem um caminho, sem uma extensão de arquivo, usando variáveis de ambiente ou com aspas.</span><span class="sxs-lookup"><span data-stu-id="43d6b-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="43d6b-133">Além disso, o invasor também pode alterar a ordem dos parâmetros ou adicionar várias aspas e espaços.</span><span class="sxs-lookup"><span data-stu-id="43d6b-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="43d6b-134">Para criar consultas mais duráveis usando linhas de comando, aplique as seguintes práticas:</span><span class="sxs-lookup"><span data-stu-id="43d6b-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="43d6b-135">Identifique os processos conhecidos ( tais como*net. exe* ou *PsExec. exe*) pela correspondência com os campos nome de arquivo, em vez de usar um filtro no campo de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="43d6b-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="43d6b-136">Ao consultar argumentos de linha de comando, não procure uma correspondência exata com vários argumentos não relacionados em uma determinada ordem.</span><span class="sxs-lookup"><span data-stu-id="43d6b-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="43d6b-137">Em vez disso, use expressões regulares ou use vários operadores Contém separados.</span><span class="sxs-lookup"><span data-stu-id="43d6b-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="43d6b-138">Correspondências que não diferenciam letras maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="43d6b-138">Use case insensitive matches.</span></span> <span data-ttu-id="43d6b-139">Por exemplo, use `=~`, `in~`e `contains`, em vez de `==`, `in`e `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="43d6b-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="43d6b-140">Para atenuar os efeitos das técnicas de ofuscação de linha de comando do DOS, considere remover aspas, substituir vírgulas por espaços e substituir vários espaços consecutivos por um único espaço.</span><span class="sxs-lookup"><span data-stu-id="43d6b-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="43d6b-141">Observe que há técnicas de ofuscação de DOS mais complexas que exigem outras abordagens, mas estas técnicas acima citadas podem ajudar a resolver os problemas mais comuns.</span><span class="sxs-lookup"><span data-stu-id="43d6b-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="43d6b-142">Os exemplos a seguir mostram várias maneiras de criar uma consulta que procura o arquivo *net. exe* para deter o serviço do Windows Defender firewall:</span><span class="sxs-lookup"><span data-stu-id="43d6b-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="43d6b-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="43d6b-143">Related topics</span></span>
- [<span data-ttu-id="43d6b-144">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="43d6b-144">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="43d6b-145">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="43d6b-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="43d6b-146">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="43d6b-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="43d6b-147">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="43d6b-147">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="43d6b-148">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="43d6b-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
