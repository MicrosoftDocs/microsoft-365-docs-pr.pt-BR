---
title: Práticas recomendadas de consulta de busca avançada no Microsoft 365 Defender
description: Saiba como construir consultas de busca de ameaças rápidas, eficientes e sem erros com a busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, esquema, kusto, evitar tempo de espera, linhas de comando, id do processo, otimizar, prática, análise, participar, resumir
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 53ec8146080e88b913de1f58d16750ffa766a1b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053231"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="4bec9-104">Práticas recomendadas de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="4bec9-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4bec9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4bec9-105">**Applies to:**</span></span>
- <span data-ttu-id="4bec9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bec9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4bec9-107">Aplique essas recomendações para obter resultados mais rápidos e evitar tempo de execução de consultas complexas.</span><span class="sxs-lookup"><span data-stu-id="4bec9-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="4bec9-108">Para obter mais informações sobre como melhorar o desempenho da consulta, leia [ práticas recomendadas de consulta no Kusto](/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="4bec9-108">For more guidance on improving query performance, read [Kusto query best practices](/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="4bec9-109">Compreender cotas de recursos da CPU</span><span class="sxs-lookup"><span data-stu-id="4bec9-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="4bec9-110">Dependendo de seu tamanho, cada locatário tem acesso a uma quantidade definida de recursos de CPU alocados para executar consultas de busca avançadas.</span><span class="sxs-lookup"><span data-stu-id="4bec9-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="4bec9-111">Para obter informações detalhadas sobre vários limites de serviço, [leia sobre cotas de busca avançadas e parâmetros de uso.](advanced-hunting-limits.md)</span><span class="sxs-lookup"><span data-stu-id="4bec9-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="4bec9-112">Os clientes que executarem várias consultas regularmente devem controlar o consumo e aplicar as diretrizes de otimização neste artigo para minimizar a interrupção resultante de cotas excedentes ou parâmetros de uso.</span><span class="sxs-lookup"><span data-stu-id="4bec9-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="4bec9-113">Dicas gerais de otimização</span><span class="sxs-lookup"><span data-stu-id="4bec9-113">General optimization tips</span></span>

- <span data-ttu-id="4bec9-114">**Tamanho de novas consultas**— Se você suspeitar que uma consulta retornará um conjunto de resultados grandes, avalie-a primeiro usando o operador [de contagem](/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="4bec9-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="4bec9-115">Use [limite](/azure/data-explorer/kusto/query/limitoperator) ou seu sinônimo `take` para evitar grandes conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="4bec9-115">Use [limit](/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="4bec9-116">**Aplicar filtros** mais cedo — aplique filtros de tempo e outros filtros para reduzir o conjunto de dados, especialmente antes de usar funções de transformação e análise, como [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)ou [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="4bec9-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="4bec9-117">No exemplo abaixo, a função de análise [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) é usada após os operadores de filtragem reduzirem o número de registros.</span><span class="sxs-lookup"><span data-stu-id="4bec9-117">In the example below, the parsing function [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="4bec9-118">**Tem batidas que contêm**— Para evitar pesquisar subdstrings em palavras desnecessariamente, use o `has` operador em vez de `contains` .</span><span class="sxs-lookup"><span data-stu-id="4bec9-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="4bec9-119">Saiba mais sobre operadores de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4bec9-119">Learn about string operators</span></span>](/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="4bec9-120">**Procure em colunas específicas**— procure em uma coluna específica em vez de executar pesquisas de texto completo em todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="4bec9-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="4bec9-121">Não use para `*` verificar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="4bec9-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="4bec9-122">**Case-sensitive para velocidade —** pesquisas sensíveis a caso são mais específicas e geralmente mais performant.</span><span class="sxs-lookup"><span data-stu-id="4bec9-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="4bec9-123">Nomes de operadores de cadeia de caracteres sensíveis a [caso,](/azure/data-explorer/kusto/query/datatypes-string-operators) `has_cs` como e , geralmente `contains_cs` terminam com `_cs` .</span><span class="sxs-lookup"><span data-stu-id="4bec9-123">Names of case-sensitive [string operators](/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="4bec9-124">Você também pode usar o operador igual a minúsculas em `==` vez de `=~` .</span><span class="sxs-lookup"><span data-stu-id="4bec9-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="4bec9-125">**Analisar, não extraia**— sempre que [](/azure/data-explorer/kusto/query/parseoperator) possível, use o operador de análise ou uma função de [análise como parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="4bec9-125">**Parse, don't extract**—Whenever possible, use the [parse operator](/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="4bec9-126">Evite o `matches regex` operador de cadeia de caracteres ou a função [extract(),](/azure/data-explorer/kusto/query/extractfunction)ambos usam expressão regular.</span><span class="sxs-lookup"><span data-stu-id="4bec9-126">Avoid the `matches regex` string operator or the [extract() function](/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="4bec9-127">Reserve o uso da expressão regular para cenários mais complexos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="4bec9-128">Leia mais sobre funções de análise</span><span class="sxs-lookup"><span data-stu-id="4bec9-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="4bec9-129">**Filtrar tabelas não expressões**— Não filtre em uma coluna calculada se você puder filtrar em uma coluna de tabela.</span><span class="sxs-lookup"><span data-stu-id="4bec9-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="4bec9-130">**Sem termos de três caracteres**— Evite comparar ou filtrar usando termos com três caracteres ou menos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="4bec9-131">Esses termos não são indexados e a correspondência deles exigirá mais recursos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="4bec9-132">**Project seletivamente**— facilmente entenda seus resultados projetando apenas as colunas de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="4bec9-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="4bec9-133">Projetar colunas específicas antes de executar a [junção](/azure/data-explorer/kusto/query/joinoperator) ou operações semelhantes também ajuda a melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="4bec9-133">Projecting specific columns prior to running [join](/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="4bec9-134">Otimizar o `join` operador</span><span class="sxs-lookup"><span data-stu-id="4bec9-134">Optimize the `join` operator</span></span>
<span data-ttu-id="4bec9-135">O [operador de junção](/azure/data-explorer/kusto/query/joinoperator) mescla linhas de duas tabelas combinando valores em colunas especificadas.</span><span class="sxs-lookup"><span data-stu-id="4bec9-135">The [join operator](/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="4bec9-136">Aplique essas dicas para otimizar consultas que usam esse operador.</span><span class="sxs-lookup"><span data-stu-id="4bec9-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="4bec9-137">**Tabela menor à esquerda**— o operador corresponde a registros na tabela no lado esquerdo da instrução join aos `join` registros à direita.</span><span class="sxs-lookup"><span data-stu-id="4bec9-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="4bec9-138">Ao ter a tabela menor à esquerda, menos registros precisarão ser corresponder, acelerando a consulta.</span><span class="sxs-lookup"><span data-stu-id="4bec9-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="4bec9-139">Na tabela abaixo, reduzimos a tabela esquerda para abranger apenas três dispositivos específicos antes de junção a ela por `DeviceLogonEvents` `IdentityLogonEvents` SIDs de conta.</span><span class="sxs-lookup"><span data-stu-id="4bec9-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- <span data-ttu-id="4bec9-140">**Use** o sabor de junção interna — O sabor de junção padrão ou as linhas deduplicações de junção interna na tabela esquerda pela tecla de junção antes de retornar uma linha para cada partida à tabela direita. [](/azure/data-explorer/kusto/query/joinoperator#join-flavors) [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor)</span><span class="sxs-lookup"><span data-stu-id="4bec9-140">**Use the inner-join flavor**—The default [join flavor](/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="4bec9-141">Se a tabela esquerda tiver várias linhas com o mesmo valor da chave, essas linhas serão deduplicadas para deixar uma única linha aleatória para `join` cada valor exclusivo.</span><span class="sxs-lookup"><span data-stu-id="4bec9-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="4bec9-142">Esse comportamento padrão pode deixar de fora informações importantes da tabela esquerda que podem fornecer informações úteis.</span><span class="sxs-lookup"><span data-stu-id="4bec9-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="4bec9-143">Por exemplo, a consulta abaixo mostrará apenas um email contendo um anexo específico, mesmo que esse mesmo anexo foi enviado usando várias mensagens de email:</span><span class="sxs-lookup"><span data-stu-id="4bec9-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="4bec9-144">Para resolver essa limitação, aplicamos o sabor de junção interna especificando para mostrar todas as linhas na tabela esquerda com valores [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) `kind=inner` correspondentes à direita:</span><span class="sxs-lookup"><span data-stu-id="4bec9-144">To address this limitation, we apply the [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="4bec9-145">**Ingressar registros de uma janela de** tempo — ao investigar eventos de segurança, os analistas pesquisam eventos relacionados que ocorrem ao redor do mesmo período de tempo.</span><span class="sxs-lookup"><span data-stu-id="4bec9-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="4bec9-146">Aplicar a mesma abordagem ao usar também `join` beneficia o desempenho, reduzindo o número de registros a verificar.</span><span class="sxs-lookup"><span data-stu-id="4bec9-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="4bec9-147">A consulta abaixo verifica se há eventos de logon dentro de 30 minutos após receber um arquivo mal-intencionado:</span><span class="sxs-lookup"><span data-stu-id="4bec9-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="4bec9-148">**Aplique filtros** de tempo em ambos os lados — Mesmo que você não esteja investigando uma janela de tempo específica, a aplicação de filtros de tempo nas tabelas esquerda e direita pode reduzir o número de registros para verificar e melhorar o `join` desempenho.</span><span class="sxs-lookup"><span data-stu-id="4bec9-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="4bec9-149">A consulta a seguir se aplica a ambas as tabelas para que ela `Timestamp > ago(1h)` insisse apenas registros da última hora:</span><span class="sxs-lookup"><span data-stu-id="4bec9-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="4bec9-150">**Use dicas para desempenho**— Use dicas com o operador para instruir o back-end a distribuir carga ao executar operações de uso `join` intensivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="4bec9-151">Saiba mais sobre dicas de junção</span><span class="sxs-lookup"><span data-stu-id="4bec9-151">Learn more about join hints</span></span>](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="4bec9-152">Por exemplo, **[](/azure/data-explorer/kusto/query/shufflequery)** a dica de embaralhar ajuda a melhorar o desempenho da consulta ao ingressar em tabelas usando uma chave com alta cardinalidade , uma chave com muitos valores exclusivos, como a consulta `AccountObjectId` abaixo:</span><span class="sxs-lookup"><span data-stu-id="4bec9-152">For example, the **[shuffle hint](/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="4bec9-153">A **[dica de](/azure/data-explorer/kusto/query/broadcastjoin)** transmissão ajuda quando a tabela esquerda é pequena (até 100.000 registros) e a tabela direita é extremamente grande.</span><span class="sxs-lookup"><span data-stu-id="4bec9-153">The **[broadcast hint](/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="4bec9-154">Por exemplo, a consulta a seguir está tentando ingressar  alguns emails que têm assuntos específicos com todas as mensagens que contêm links na `EmailUrlInfo` tabela:</span><span class="sxs-lookup"><span data-stu-id="4bec9-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="4bec9-155">Otimizar o `summarize` operador</span><span class="sxs-lookup"><span data-stu-id="4bec9-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="4bec9-156">O [operador resumir](/azure/data-explorer/kusto/query/summarizeoperator) agrega o conteúdo de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="4bec9-156">The [summarize operator](/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="4bec9-157">Aplique essas dicas para otimizar consultas que usam esse operador.</span><span class="sxs-lookup"><span data-stu-id="4bec9-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="4bec9-158">**Encontre valores distintos**— em geral, use `summarize` para encontrar valores distintos que podem ser repetitivos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="4bec9-159">Pode ser desnecessário usá-lo para agregar colunas que não têm valores repetitivos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="4bec9-160">Embora um único email possa fazer parte de  vários eventos, o exemplo a seguir não é um uso eficiente porque uma ID de mensagem de rede para um email individual sempre vem com um endereço de `summarize` remetente exclusivo.</span><span class="sxs-lookup"><span data-stu-id="4bec9-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="4bec9-161">O `summarize` operador pode ser facilmente substituído por , produtividade potencialmente os mesmos resultados enquanto consome menos `project` recursos:</span><span class="sxs-lookup"><span data-stu-id="4bec9-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="4bec9-162">O exemplo a seguir é um uso mais eficiente porque pode haver várias instâncias distintas de um endereço de remetente enviando `summarize` emails para o mesmo endereço de destinatário.</span><span class="sxs-lookup"><span data-stu-id="4bec9-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="4bec9-163">Essas combinações são menos distintas e provavelmente terão duplicatas.</span><span class="sxs-lookup"><span data-stu-id="4bec9-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="4bec9-164">**Embaralhar** a consulta — embora seja melhor usado em colunas com valores repetitivos, as mesmas colunas também podem ter alta cardinalidade ou um grande número `summarize` de valores  exclusivos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="4bec9-165">Assim como o operador, você também pode aplicar a dica de embaralhar para distribuir a carga de processamento e potencialmente melhorar o desempenho ao operar em colunas com `join` alta [](/azure/data-explorer/kusto/query/shufflequery) `summarize` cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="4bec9-165">Like the `join` operator, you can also apply the [shuffle hint](/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="4bec9-166">A consulta a seguir usa para contar endereço de email de destinatário distinto, que pode ser executado em centenas `summarize` de milhares em grandes organizações.</span><span class="sxs-lookup"><span data-stu-id="4bec9-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="4bec9-167">Para melhorar o desempenho, ele incorpora `hint.shufflekey` :</span><span class="sxs-lookup"><span data-stu-id="4bec9-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="4bec9-168">Cenários de consulta</span><span class="sxs-lookup"><span data-stu-id="4bec9-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="4bec9-169">Identificar processos exclusivos com IDs de processo</span><span class="sxs-lookup"><span data-stu-id="4bec9-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="4bec9-170">As IDs de processo (PIDs) são recicladas no Windows e reutilizadas para novos processos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="4bec9-171">Por si só, eles não servem como identificadores exclusivos para processos específicos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="4bec9-172">Para obter um identificador exclusivo para um processo em um computador específico, use a ID do processo juntamente com o tempo de criação do processo.</span><span class="sxs-lookup"><span data-stu-id="4bec9-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="4bec9-173">Ao juntar ou resumir dados em um processo, inclua colunas para o identificador da máquina (`DeviceId` ou `DeviceName`), a ID do processo (`ProcessId` ou `InitiatingProcessId`) e o tempo de criação do processo (`ProcessCreationTime` ou `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="4bec9-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="4bec9-174">O exemplo de consulta a seguir localiza processos que acessam mais de 10 endereços IP na porta 445 (SMB), possivelmente procurando por compartilhamentos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="4bec9-175">Exemplo de consulta:</span><span class="sxs-lookup"><span data-stu-id="4bec9-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="4bec9-176">A consulta é resumida por tanto `InitiatingProcessId` quanto`InitiatingProcessCreationTime` para que ela examine um único processo, sem misturar vários processos com a mesma ID de processo.</span><span class="sxs-lookup"><span data-stu-id="4bec9-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="4bec9-177">Linhas de comando de consulta</span><span class="sxs-lookup"><span data-stu-id="4bec9-177">Query command lines</span></span>
<span data-ttu-id="4bec9-178">Há várias maneiras de criar uma linha de comando para executar uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="4bec9-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="4bec9-179">Por exemplo, um invasor pode fazer referência a um arquivo de imagem sem um caminho, sem uma extensão de arquivo, usando variáveis de ambiente ou com aspas.</span><span class="sxs-lookup"><span data-stu-id="4bec9-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="4bec9-180">O invasor também pode alterar a ordem dos parâmetros ou adicionar várias aspas e espaços.</span><span class="sxs-lookup"><span data-stu-id="4bec9-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="4bec9-181">Para criar consultas mais duráveis ao redor das linhas de comando, aplique as seguintes práticas:</span><span class="sxs-lookup"><span data-stu-id="4bec9-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="4bec9-182">Identifique os processos conhecidos (comonet.exe *ou* *psexec.exe*) correspondendo aos campos de nome do arquivo, em vez de filtrar na própria linha de comando.</span><span class="sxs-lookup"><span data-stu-id="4bec9-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="4bec9-183">Analisar seções de linha de comando usando a [função parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="4bec9-183">Parse command-line sections using the [parse_command_line() function](/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="4bec9-184">Ao consultar argumentos de linha de comando, não procure uma correspondência exata com vários argumentos não relacionados em uma determinada ordem.</span><span class="sxs-lookup"><span data-stu-id="4bec9-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="4bec9-185">Em vez disso, use expressões regulares ou use vários operadores Contém separados.</span><span class="sxs-lookup"><span data-stu-id="4bec9-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="4bec9-186">Correspondências que não diferenciam letras maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4bec9-186">Use case insensitive matches.</span></span> <span data-ttu-id="4bec9-187">Por exemplo, use `=~` `in~` , e, em vez de `contains` , e `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="4bec9-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="4bec9-188">Para atenuar técnicas de ofuscação de linha de comando, considere remover aspas, substituir vírgulas por espaços e substituir vários espaços consecutivos por um único espaço.</span><span class="sxs-lookup"><span data-stu-id="4bec9-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="4bec9-189">Há técnicas de ofuscação mais complexas que exigem outras abordagens, mas esses ajustes podem ajudar a resolver as comuns.</span><span class="sxs-lookup"><span data-stu-id="4bec9-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="4bec9-190">Os exemplos a seguir mostram várias maneiras de construir uma consulta que procura o arquivonet.exe *parar* o serviço de firewall "MpsSvc":</span><span class="sxs-lookup"><span data-stu-id="4bec9-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="4bec9-191">Ingerir dados de fontes externas</span><span class="sxs-lookup"><span data-stu-id="4bec9-191">Ingest data from external sources</span></span>
<span data-ttu-id="4bec9-192">Para incorporar listas longas ou tabelas grandes à sua consulta, use o operador [externaldata](/azure/data-explorer/kusto/query/externaldata-operator) para ingerir dados de um URI especificado.</span><span class="sxs-lookup"><span data-stu-id="4bec9-192">To incorporate long lists or large tables into your query, use the [externaldata operator](/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="4bec9-193">Você pode obter dados de arquivos em TXT, CSV, JSON ou [outros formatos.](/azure/data-explorer/ingestion-supported-formats)</span><span class="sxs-lookup"><span data-stu-id="4bec9-193">You can get data from files in TXT, CSV, JSON, or [other formats](/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="4bec9-194">O exemplo a seguir mostra como você pode utilizar a extensa lista de hashes sha-256 de malware fornecidos pelo MalwareBazaar (abuse.ch) para verificar anexos em emails:</span><span class="sxs-lookup"><span data-stu-id="4bec9-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a><span data-ttu-id="4bec9-195">Cadeias de caracteres de análise</span><span class="sxs-lookup"><span data-stu-id="4bec9-195">Parse strings</span></span>
<span data-ttu-id="4bec9-196">Há várias funções que você pode usar para lidar com cadeias de caracteres com eficiência que precisam de análise ou conversão.</span><span class="sxs-lookup"><span data-stu-id="4bec9-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="4bec9-197">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4bec9-197">String</span></span> | <span data-ttu-id="4bec9-198">Função</span><span class="sxs-lookup"><span data-stu-id="4bec9-198">Function</span></span> | <span data-ttu-id="4bec9-199">Exemplo de uso</span><span class="sxs-lookup"><span data-stu-id="4bec9-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="4bec9-200">Linhas de comando</span><span class="sxs-lookup"><span data-stu-id="4bec9-200">Command-lines</span></span> | [<span data-ttu-id="4bec9-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="4bec9-201">parse_command_line()</span></span>](/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="4bec9-202">Extraia o comando e todos os argumentos.</span><span class="sxs-lookup"><span data-stu-id="4bec9-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="4bec9-203">Caminhos</span><span class="sxs-lookup"><span data-stu-id="4bec9-203">Paths</span></span> | [<span data-ttu-id="4bec9-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="4bec9-204">parse_path()</span></span>](/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="4bec9-205">Extraia as seções de um arquivo ou caminho de pasta.</span><span class="sxs-lookup"><span data-stu-id="4bec9-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="4bec9-206">Números de versão</span><span class="sxs-lookup"><span data-stu-id="4bec9-206">Version numbers</span></span> | [<span data-ttu-id="4bec9-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="4bec9-207">parse_version()</span></span>](/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="4bec9-208">Desconstrua um número de versão com até quatro seções e até oito caracteres por seção.</span><span class="sxs-lookup"><span data-stu-id="4bec9-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="4bec9-209">Use os dados analisados para comparar a idade da versão.</span><span class="sxs-lookup"><span data-stu-id="4bec9-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="4bec9-210">Endereços IPv4</span><span class="sxs-lookup"><span data-stu-id="4bec9-210">IPv4 addresses</span></span> | [<span data-ttu-id="4bec9-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="4bec9-211">parse_ipv4()</span></span>](/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="4bec9-212">Converta um endereço IPv4 em um inteiro longo.</span><span class="sxs-lookup"><span data-stu-id="4bec9-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="4bec9-213">Para comparar endereços IPv4 sem convertê-los, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="4bec9-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="4bec9-214">Endereços IPv6</span><span class="sxs-lookup"><span data-stu-id="4bec9-214">IPv6 addresses</span></span> | [<span data-ttu-id="4bec9-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="4bec9-215">parse_ipv6()</span></span>](/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="4bec9-216">Converta um endereço IPv4 ou IPv6 para a notação IPv6 canônica.</span><span class="sxs-lookup"><span data-stu-id="4bec9-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="4bec9-217">Para comparar endereços IPv6, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="4bec9-217">To compare IPv6 addresses, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="4bec9-218">Para saber mais sobre todas as funções de análise com suporte, [leia sobre as funções de cadeia de caracteres kusto](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="4bec9-218">To learn about all supported parsing functions, [read about Kusto string functions](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="4bec9-219">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4bec9-219">Related topics</span></span>
- [<span data-ttu-id="4bec9-220">Documentação de idioma de consulta kusto</span><span class="sxs-lookup"><span data-stu-id="4bec9-220">Kusto query language documentation</span></span>](/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="4bec9-221">Cotas e parâmetros de uso</span><span class="sxs-lookup"><span data-stu-id="4bec9-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="4bec9-222">Manipular erros avançados de busca</span><span class="sxs-lookup"><span data-stu-id="4bec9-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="4bec9-223">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="4bec9-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4bec9-224">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="4bec9-224">Learn the query language</span></span>](advanced-hunting-query-language.md)