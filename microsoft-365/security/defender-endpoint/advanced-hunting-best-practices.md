---
title: Práticas recomendadas de consulta para busca avançada
description: Aprenda a criar consultas de busca de ameaças rápidas, eficientes e sem erros ao usar a busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, detecções personalizadas, esquema, kusto, evitar tempo de espera, linhas de comando, id de processo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499254"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="2cf6e-104">Práticas recomendadas de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="2cf6e-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2cf6e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2cf6e-105">**Applies to:**</span></span>
- [<span data-ttu-id="2cf6e-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2cf6e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="2cf6e-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2cf6e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2cf6e-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="2cf6e-109">Obter o melhor resultado possível numa consulta</span><span class="sxs-lookup"><span data-stu-id="2cf6e-109">Optimize query performance</span></span>

<span data-ttu-id="2cf6e-110">Aplique essas recomendações para obter resultados mais rápidos e evitar tempo de execução de consultas complexas.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="2cf6e-111">Ao experimentar novas consultas, use sempre `limit` para evitar conjuntos de resultados grandes demais.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="2cf6e-112">Você também pode avaliar inicialmente o tamanho do conjunto de resultados usando `count`.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="2cf6e-113">Use primeiro os filtros de tempo.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-113">Use time filters first.</span></span> <span data-ttu-id="2cf6e-114">O ideal é limitar suas consultas a sete dias.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="2cf6e-115">Coloque os filtros passíveis de remover a maior parte dos dados no início da consulta, imediatamente após o filtro de tempo.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="2cf6e-116">Use o operador `has` sobre `contains` ao procurar tokens completos.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="2cf6e-117">Examine uma coluna específica, em vez de executar pesquisas de texto completo em todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="2cf6e-118">Ao adicionar tabelas, especifique primeiro a tabela com menos linhas.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="2cf6e-119">`project` somente as colunas necessárias das tabelas que adicionou.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="2cf6e-120">Para obter mais informações sobre como melhorar o desempenho da consulta, leia [ práticas recomendadas de consulta no Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="2cf6e-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="2cf6e-121">Dicas de consulta e armadilhas</span><span class="sxs-lookup"><span data-stu-id="2cf6e-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="2cf6e-122">Consultas com IDs de processo</span><span class="sxs-lookup"><span data-stu-id="2cf6e-122">Queries with process IDs</span></span>

<span data-ttu-id="2cf6e-123">As IDs de processo (PIDs) são recicladas no Windows e reutilizadas para novos processos.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="2cf6e-124">Por si só, eles não servem como identificadores exclusivos para processos específicos.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="2cf6e-125">Para obter um identificador exclusivo para um processo em um dispositivo específico, use a ID do processo juntamente com o tempo de criação do processo.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="2cf6e-126">Ao ingressar ou resumir dados em torno de processos, inclua colunas para o identificador de dispositivo (ou ), a ID do processo ( ou ) e o tempo de criação do processo `DeviceId` `DeviceName` ( ou `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` ).</span><span class="sxs-lookup"><span data-stu-id="2cf6e-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="2cf6e-127">O exemplo de consulta a seguir localiza processos que acessam mais de 10 endereços IP na porta 445 (SMB), possivelmente procurando por compartilhamentos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="2cf6e-128">A consulta é resumida por tanto `InitiatingProcessId` quanto`InitiatingProcessCreationTime` para que ela examine um único processo, sem misturar vários processos com a mesma ID de processo.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="2cf6e-129">Consultas com linhas de comando</span><span class="sxs-lookup"><span data-stu-id="2cf6e-129">Queries with command lines</span></span>

<span data-ttu-id="2cf6e-130">As linhas de comando podem variar.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-130">Command lines can vary.</span></span> <span data-ttu-id="2cf6e-131">Quando aplicável, filtre os nomes dos arquivos e realize correspondência difusa.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="2cf6e-132">Há várias maneiras de criar uma linha de comando para executar uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="2cf6e-133">Por exemplo, um invasor pode fazer referência a um arquivo de imagem com ou sem um caminho, sem uma extensão de arquivo, usando variáveis de ambiente ou com aspas.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="2cf6e-134">Além disso, o invasor também pode alterar a ordem dos parâmetros ou adicionar várias aspas e espaços.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="2cf6e-135">Para criar consultas mais duráveis usando linhas de comando, aplique as seguintes práticas:</span><span class="sxs-lookup"><span data-stu-id="2cf6e-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="2cf6e-136">Identifique os processos conhecidos ( tais como *net. exe* ou *PsExec. exe*) pela correspondência com os campos nome de arquivo, em vez de usar um filtro no campo de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="2cf6e-137">Ao consultar argumentos de linha de comando, não procure uma correspondência exata com vários argumentos não relacionados em uma determinada ordem.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="2cf6e-138">Em vez disso, use expressões regulares ou use vários operadores Contém separados.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="2cf6e-139">Correspondências que não diferenciam letras maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-139">Use case insensitive matches.</span></span> <span data-ttu-id="2cf6e-140">Por exemplo, use `=~` , `in~` e, `contains` em vez de `==` , `in` e `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="2cf6e-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="2cf6e-141">Para atenuar os efeitos das técnicas de ofuscação de linha de comando do DOS, considere remover aspas, substituir vírgulas por espaços e substituir vários espaços consecutivos por um único espaço.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="2cf6e-142">Observe que há técnicas de ofuscação de DOS mais complexas que exigem outras abordagens, mas estas técnicas acima citadas podem ajudar a resolver os problemas mais comuns.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="2cf6e-143">Os exemplos a seguir mostram várias maneiras de criar uma consulta que procura o arquivo *net. exe* para deter o serviço do Windows Defender firewall:</span><span class="sxs-lookup"><span data-stu-id="2cf6e-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
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

> <span data-ttu-id="2cf6e-144">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2cf6e-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2cf6e-145">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2cf6e-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="2cf6e-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2cf6e-146">Related topics</span></span>

- [<span data-ttu-id="2cf6e-147">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="2cf6e-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2cf6e-148">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="2cf6e-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2cf6e-149">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="2cf6e-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="2cf6e-150">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="2cf6e-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="2cf6e-151">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="2cf6e-151">Custom detections overview</span></span>](overview-custom-detections.md)
