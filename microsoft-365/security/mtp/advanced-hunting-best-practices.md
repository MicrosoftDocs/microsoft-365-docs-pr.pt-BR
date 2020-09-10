---
title: Práticas recomendadas de consulta de busca avançada no Microsoft Threat Protection
description: Saiba como criar consultas de busca de ameaças rápidas, eficientes e com erros grátis com busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, esquema, Kusto, evitar tempo limite, linhas de comando, ID de processo, otimizar, práticas recomendadas, análise, participar, Resumo
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
ms.openlocfilehash: 3ca475ef6dbdbd66af47216c4130d748788730c2
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419127"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="f89aa-104">Práticas recomendadas de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="f89aa-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="f89aa-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f89aa-105">**Applies to:**</span></span>
- <span data-ttu-id="f89aa-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f89aa-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f89aa-107">Aplique essas recomendações para obter resultados mais rapidamente e evitar tempos limite ao executar consultas complexas.</span><span class="sxs-lookup"><span data-stu-id="f89aa-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="f89aa-108">Para obter mais informações sobre como melhorar o desempenho da consulta, leia [ práticas recomendadas de consulta no Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="f89aa-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="general-guidance"></a><span data-ttu-id="f89aa-109">Diretrizes gerais</span><span class="sxs-lookup"><span data-stu-id="f89aa-109">General guidance</span></span>

- <span data-ttu-id="f89aa-110">**Dimensionar novas consultas**— se você suspeita que uma consulta retornará um grande conjunto de resultados, avalie-a primeiro usando o [operador de contagem](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="f89aa-110">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="f89aa-111">Use o [limite](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) ou seu sinônimo `take` para evitar grandes conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="f89aa-111">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="f89aa-112">**Aplicar filtros antecipadamente**— Aplique filtros de tempo e outros filtros para reduzir o conjunto de dados, especialmente antes de usar funções de transformação e análise, como [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [ToUpper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)ou [parse_json (](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)).</span><span class="sxs-lookup"><span data-stu-id="f89aa-112">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="f89aa-113">No exemplo abaixo, a função de análise [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) é usada depois que os operadores de filtragem reduziram o número de registros.</span><span class="sxs-lookup"><span data-stu-id="f89aa-113">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="f89aa-114">O **tem batidas**, para evitar a pesquisa de subcadeias de caracteres em palavras desnecessariamente, use o `has` operador em vez de `contains` .</span><span class="sxs-lookup"><span data-stu-id="f89aa-114">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="f89aa-115">Saiba mais sobre operadores de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f89aa-115">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="f89aa-116">**Examinar colunas específicas**— procure em uma coluna específica em vez de executar pesquisas de texto completo em todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="f89aa-116">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="f89aa-117">Não use `*` para verificar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="f89aa-117">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="f89aa-118">Diferenciar **maiúsculas de minúsculas para velocidade**— as pesquisas que diferenciam maiúsculas de minúsculas são mais específicas e geralmente têm mais desempenho.</span><span class="sxs-lookup"><span data-stu-id="f89aa-118">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="f89aa-119">Nomes de [operadores de cadeia de caracteres](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)com distinção entre maiúsculas e minúsculas, como `has_cs` e `contains_cs` , geralmente terminam com `_cs` .</span><span class="sxs-lookup"><span data-stu-id="f89aa-119">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="f89aa-120">Você também pode usar o operador Equals que diferencia maiúsculas de minúsculas `==` em vez de `~=` .</span><span class="sxs-lookup"><span data-stu-id="f89aa-120">You can also use the case-sensitive equals operator `==` instead of `~=`.</span></span>
- <span data-ttu-id="f89aa-121">**Parse, não extrair**— sempre que possível, use o [operador Parse](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) ou uma função de análise como [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="f89aa-121">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="f89aa-122">Evite o `matches regex` operador de cadeia de caracteres ou a [função Extract ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), ambos usam a expressão regular.</span><span class="sxs-lookup"><span data-stu-id="f89aa-122">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="f89aa-123">Reserve o uso de expressão regular para cenários mais complexos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-123">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="f89aa-124">Ler mais sobre funções de análise</span><span class="sxs-lookup"><span data-stu-id="f89aa-124">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="f89aa-125">**Filter Tables Not Expressions**— não filtra uma coluna calculada se você pode filtrar em uma coluna de tabela.</span><span class="sxs-lookup"><span data-stu-id="f89aa-125">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="f89aa-126">**Sem termos de três caracteres**— Evite comparar ou filtrar usando termos com três caracteres ou menos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-126">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="f89aa-127">Esses termos não são indexados e a correspondência precisará de mais recursos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-127">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="f89aa-128">**Projeto**de forma seletiva — torne seus resultados mais fáceis de entender, projendo somente as colunas de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="f89aa-128">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="f89aa-129">Projetar colunas específicas antes de executar a [junção](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) ou operações similares também ajuda a melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="f89aa-129">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="f89aa-130">Otimizar o `join` operador</span><span class="sxs-lookup"><span data-stu-id="f89aa-130">Optimize the `join` operator</span></span>
<span data-ttu-id="f89aa-131">O [operador Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) mescla linhas de duas tabelas combinando valores em colunas especificadas.</span><span class="sxs-lookup"><span data-stu-id="f89aa-131">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="f89aa-132">Aplique estas dicas para otimizar as consultas que usam esse operador.</span><span class="sxs-lookup"><span data-stu-id="f89aa-132">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="f89aa-133">**Tabela menor à esquerda**— o `join` operador corresponde a registros na tabela do lado esquerdo da instrução Join para os registros à direita.</span><span class="sxs-lookup"><span data-stu-id="f89aa-133">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="f89aa-134">Com a menor tabela à esquerda, menos registros precisarão ser correspondidos e, portanto, acelerar a consulta.</span><span class="sxs-lookup"><span data-stu-id="f89aa-134">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="f89aa-135">Na tabela abaixo, reduzimos a tabela esquerda `DeviceLogonEvents` para abranger apenas três dispositivos específicos antes de ingressar com `IdentityLogonEvents` por SIDs de conta.</span><span class="sxs-lookup"><span data-stu-id="f89aa-135">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="f89aa-136">**Use o tipo de junção interna**— o [tipo de junção](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) padrão ou a [innerunique-Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) elimina as linhas na tabela esquerda da chave de junção antes de retornar uma linha para cada correspondência à tabela direita.</span><span class="sxs-lookup"><span data-stu-id="f89aa-136">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="f89aa-137">Se a tabela esquerda tiver várias linhas com o mesmo valor para a `join` chave, essas linhas serão desduplicadas para deixar uma única linha aleatória para cada valor exclusivo.</span><span class="sxs-lookup"><span data-stu-id="f89aa-137">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="f89aa-138">Esse comportamento padrão pode deixar informações importantes da tabela esquerda que podem fornecer informações úteis.</span><span class="sxs-lookup"><span data-stu-id="f89aa-138">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="f89aa-139">Por exemplo, a consulta abaixo só mostrará um email contendo um anexo específico, mesmo que o mesmo anexo tenha sido enviado usando várias mensagens de email:</span><span class="sxs-lookup"><span data-stu-id="f89aa-139">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="f89aa-140">Para resolver essa limitação, aplicamos o tipo de [junção interna](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) especificando `kind=inner` para mostrar todas as linhas na tabela esquerda com valores correspondentes à direita:</span><span class="sxs-lookup"><span data-stu-id="f89aa-140">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="f89aa-141">**Associar registros de uma janela de tempo**— ao investigar eventos de segurança, os analistas procuram eventos relacionados que ocorrem em torno do mesmo período de tempo.</span><span class="sxs-lookup"><span data-stu-id="f89aa-141">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="f89aa-142">Aplicar a mesma abordagem ao usar `join` também o desempenho de benefícios reduzindo o número de registros a serem verificados.</span><span class="sxs-lookup"><span data-stu-id="f89aa-142">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="f89aa-143">A consulta a seguir verifica se há eventos de logon em até 30 minutos após o recebimento de um arquivo mal-intencionado:</span><span class="sxs-lookup"><span data-stu-id="f89aa-143">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="f89aa-144">**Aplique filtros de tempo em ambos os lados**— mesmo que você não esteja investigando uma janela de tempo específica, a aplicação de filtros de tempo nas tabelas esquerda e direita pode reduzir o número de registros para verificar e melhorar o `join` desempenho.</span><span class="sxs-lookup"><span data-stu-id="f89aa-144">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="f89aa-145">A consulta a seguir aplica-se `Timestamp > ago(1h)` às duas tabelas para que ela ingresse somente nos registros da última hora:</span><span class="sxs-lookup"><span data-stu-id="f89aa-145">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="f89aa-146">**Use dicas de desempenho**— use dicas com o `join` operador para instruir o backend a distribuir o carregamento ao executar operações intensivas de recursos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-146">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="f89aa-147">Saiba mais sobre dicas de junção</span><span class="sxs-lookup"><span data-stu-id="f89aa-147">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="f89aa-148">Por exemplo, a **[dica de embaralhamento](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** ajuda a melhorar o desempenho da consulta ao unir tabelas usando uma chave com alta cardinalidade — uma chave com muitos valores exclusivos, como o `AccountObjectId` na consulta abaixo:</span><span class="sxs-lookup"><span data-stu-id="f89aa-148">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="f89aa-149">A **[dica de transmissão](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** ajuda quando a tabela esquerda é pequena (até 100.000 registros) e a tabela direita é muito grande.</span><span class="sxs-lookup"><span data-stu-id="f89aa-149">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="f89aa-150">Por exemplo, a consulta abaixo está tentando participar de alguns emails com entidades específicas com _todas_ as mensagens que contêm links na `EmailUrlInfo` tabela:</span><span class="sxs-lookup"><span data-stu-id="f89aa-150">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="f89aa-151">Otimizar o `summarize` operador</span><span class="sxs-lookup"><span data-stu-id="f89aa-151">Optimize the `summarize` operator</span></span>
<span data-ttu-id="f89aa-152">O [operador Summarizer](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) agrega o conteúdo de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="f89aa-152">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="f89aa-153">Aplique estas dicas para otimizar as consultas que usam esse operador.</span><span class="sxs-lookup"><span data-stu-id="f89aa-153">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="f89aa-154">**Localizar valores distintos**, em geral, use `summarize` para localizar valores distintos que podem ser repetitivos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-154">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="f89aa-155">Pode ser desnecessário usá-lo para agregar colunas que não tenham valores repetidos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-155">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="f89aa-156">Embora um único email possa fazer parte de vários eventos, o exemplo abaixo _não_ é um uso eficiente do `summarize` porque uma ID de mensagem de rede para um email individual sempre vem com um endereço de remetente exclusivo.</span><span class="sxs-lookup"><span data-stu-id="f89aa-156">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="f89aa-157">O `summarize` operador pode ser facilmente substituído pelo `project` , produzindo potencialmente os mesmos resultados ao consumir menos recursos:</span><span class="sxs-lookup"><span data-stu-id="f89aa-157">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="f89aa-158">O exemplo a seguir é um uso mais eficiente, `summarize` pois pode haver várias instâncias distintas de um endereço de remetente enviando emails para o mesmo endereço de destinatário.</span><span class="sxs-lookup"><span data-stu-id="f89aa-158">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="f89aa-159">Essas combinações são menos distintas e provavelmente têm duplicatas.</span><span class="sxs-lookup"><span data-stu-id="f89aa-159">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="f89aa-160">**Embaralhar a consulta**, embora `summarize` seja melhor usada em colunas com valores repetitivos, as mesmas colunas também podem ter _alta cardinalidade_ ou grandes números de valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-160">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="f89aa-161">Como o `join` operador, você também pode aplicar a [dica de embaralhamento](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) com `summarize` para distribuir a carga de processamento e potencialmente melhorar o desempenho ao operar em colunas com grande cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="f89aa-161">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="f89aa-162">A consulta a seguir usa `summarize` para contar o endereço de email de destinatário distinto, que pode ser executado em centenas de milhares em grandes organizações.</span><span class="sxs-lookup"><span data-stu-id="f89aa-162">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="f89aa-163">Para melhorar o desempenho, ele incorpora `hint.shufflekey` :</span><span class="sxs-lookup"><span data-stu-id="f89aa-163">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="f89aa-164">Cenários de consulta</span><span class="sxs-lookup"><span data-stu-id="f89aa-164">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="f89aa-165">Identificar processos exclusivos com IDs de processo</span><span class="sxs-lookup"><span data-stu-id="f89aa-165">Identify unique processes with process IDs</span></span>
<span data-ttu-id="f89aa-166">As IDs de processo (PIDs) são recicladas no Windows e reutilizadas para novos processos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-166">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="f89aa-167">Por si só, eles não servem como identificadores exclusivos para processos específicos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-167">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="f89aa-168">Para obter um identificador exclusivo para um processo em um computador específico, use a ID do processo juntamente com o tempo de criação do processo.</span><span class="sxs-lookup"><span data-stu-id="f89aa-168">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="f89aa-169">Ao juntar ou resumir dados em um processo, inclua colunas para o identificador da máquina (`DeviceId` ou `DeviceName`), a ID do processo (`ProcessId` ou `InitiatingProcessId`) e o tempo de criação do processo (`ProcessCreationTime` ou `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="f89aa-169">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="f89aa-170">O exemplo de consulta a seguir localiza processos que acessam mais de 10 endereços IP na porta 445 (SMB), possivelmente procurando por compartilhamentos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-170">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="f89aa-171">Exemplo de consulta:</span><span class="sxs-lookup"><span data-stu-id="f89aa-171">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="f89aa-172">A consulta é resumida por tanto `InitiatingProcessId` quanto`InitiatingProcessCreationTime` para que ela examine um único processo, sem misturar vários processos com a mesma ID de processo.</span><span class="sxs-lookup"><span data-stu-id="f89aa-172">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="f89aa-173">Linhas de comando de consulta</span><span class="sxs-lookup"><span data-stu-id="f89aa-173">Query command lines</span></span>
<span data-ttu-id="f89aa-174">Há várias maneiras de criar uma linha de comando para executar uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="f89aa-174">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="f89aa-175">Por exemplo, um invasor pode fazer referência a um arquivo de imagem sem um caminho, sem uma extensão de arquivo, usando variáveis de ambiente ou com aspas.</span><span class="sxs-lookup"><span data-stu-id="f89aa-175">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="f89aa-176">O invasor também pode alterar a ordem dos parâmetros ou adicionar várias aspas e espaços.</span><span class="sxs-lookup"><span data-stu-id="f89aa-176">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="f89aa-177">Para criar consultas mais duráveis em torno de linhas de comando, aplique as seguintes práticas:</span><span class="sxs-lookup"><span data-stu-id="f89aa-177">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="f89aa-178">Identifique os processos conhecidos (como *net.exe* ou *psexec.exe*) por meio de correspondência nos campos de nome de arquivo, em vez de filtrar na própria linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f89aa-178">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="f89aa-179">Analisar seções de linha de comando usando a [função parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="f89aa-179">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="f89aa-180">Ao consultar argumentos de linha de comando, não procure uma correspondência exata com vários argumentos não relacionados em uma determinada ordem.</span><span class="sxs-lookup"><span data-stu-id="f89aa-180">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="f89aa-181">Em vez disso, use expressões regulares ou use vários operadores Contém separados.</span><span class="sxs-lookup"><span data-stu-id="f89aa-181">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="f89aa-182">Correspondências que não diferenciam letras maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f89aa-182">Use case insensitive matches.</span></span> <span data-ttu-id="f89aa-183">Por exemplo, use `=~` , `in~` , e `contains` em vez de `==` , `in` e `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="f89aa-183">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="f89aa-184">Para reduzir as técnicas de ofuscação de linha de comando, considere remover aspas, substituir vírgulas por espaços e substituir vários espaços consecutivos por um único espaço.</span><span class="sxs-lookup"><span data-stu-id="f89aa-184">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="f89aa-185">Há técnicas de ofuscação mais complexas que exigem outras abordagens, mas essas alterações podem ajudar a lidar com as comuns.</span><span class="sxs-lookup"><span data-stu-id="f89aa-185">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="f89aa-186">Os exemplos a seguir mostram várias maneiras de criar uma consulta que procura o arquivo *net.exe* para interromper o serviço de firewall "MPSSVC":</span><span class="sxs-lookup"><span data-stu-id="f89aa-186">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="f89aa-187">Ingestão de dados de fontes externas</span><span class="sxs-lookup"><span data-stu-id="f89aa-187">Ingest data from external sources</span></span>
<span data-ttu-id="f89aa-188">Para incorporar listas longas ou tabelas grandes à sua consulta, use o [operador externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) para ingestão de dados de um URI especificado.</span><span class="sxs-lookup"><span data-stu-id="f89aa-188">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="f89aa-189">Você pode obter dados de arquivos em TXT, CSV, JSON ou em [outros formatos](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span><span class="sxs-lookup"><span data-stu-id="f89aa-189">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="f89aa-190">O exemplo a seguir mostra como você pode usar a lista extensa de hashes SHA-256 de malware fornecidos pelo MalwareBazaar (abuse.ch) para verificar anexos em emails:</span><span class="sxs-lookup"><span data-stu-id="f89aa-190">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a><span data-ttu-id="f89aa-191">Analisar cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="f89aa-191">Parse strings</span></span>
<span data-ttu-id="f89aa-192">Há várias funções que você pode usar para lidar com eficiência cadeias de caracteres que precisam de análise ou conversão.</span><span class="sxs-lookup"><span data-stu-id="f89aa-192">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="f89aa-193">String</span><span class="sxs-lookup"><span data-stu-id="f89aa-193">String</span></span> | <span data-ttu-id="f89aa-194">Função</span><span class="sxs-lookup"><span data-stu-id="f89aa-194">Function</span></span> | <span data-ttu-id="f89aa-195">Exemplo de uso</span><span class="sxs-lookup"><span data-stu-id="f89aa-195">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="f89aa-196">Linhas de comando</span><span class="sxs-lookup"><span data-stu-id="f89aa-196">Command-lines</span></span> | [<span data-ttu-id="f89aa-197">parse_command_line ()</span><span class="sxs-lookup"><span data-stu-id="f89aa-197">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="f89aa-198">Extraia o comando e todos os argumentos.</span><span class="sxs-lookup"><span data-stu-id="f89aa-198">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="f89aa-199">Caminhos</span><span class="sxs-lookup"><span data-stu-id="f89aa-199">Paths</span></span> | [<span data-ttu-id="f89aa-200">parse_path ()</span><span class="sxs-lookup"><span data-stu-id="f89aa-200">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="f89aa-201">Extraia as seções de um caminho de arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="f89aa-201">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="f89aa-202">Números de versão</span><span class="sxs-lookup"><span data-stu-id="f89aa-202">Version numbers</span></span> | [<span data-ttu-id="f89aa-203">parse_version ()</span><span class="sxs-lookup"><span data-stu-id="f89aa-203">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="f89aa-204">Deconstruct um número de versão com até quatro seções e até oito caracteres por seção.</span><span class="sxs-lookup"><span data-stu-id="f89aa-204">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="f89aa-205">Use os dados analisados para comparar a idade da versão.</span><span class="sxs-lookup"><span data-stu-id="f89aa-205">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="f89aa-206">Endereços IPv4</span><span class="sxs-lookup"><span data-stu-id="f89aa-206">IPv4 addresses</span></span> | [<span data-ttu-id="f89aa-207">parse_ipv4 ()</span><span class="sxs-lookup"><span data-stu-id="f89aa-207">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="f89aa-208">Converter um endereço IPv4 em um inteiro longo.</span><span class="sxs-lookup"><span data-stu-id="f89aa-208">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="f89aa-209">Para comparar endereços IPv4 sem convertê-los, use [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="f89aa-209">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="f89aa-210">Endereços IPv6</span><span class="sxs-lookup"><span data-stu-id="f89aa-210">IPv6 addresses</span></span> | [<span data-ttu-id="f89aa-211">parse_ipv6 ()</span><span class="sxs-lookup"><span data-stu-id="f89aa-211">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="f89aa-212">Converta um endereço IPv4 ou IPv6 na notação IPv6 canônica.</span><span class="sxs-lookup"><span data-stu-id="f89aa-212">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="f89aa-213">Para comparar endereços IPv6, use [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="f89aa-213">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="f89aa-214">Para saber mais sobre todas as funções de análise compatíveis, [Leia sobre as funções de cadeia de caracteres do Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="f89aa-214">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="f89aa-215">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f89aa-215">Related topics</span></span>
- [<span data-ttu-id="f89aa-216">Documentação da linguagem de consulta do Kusto</span><span class="sxs-lookup"><span data-stu-id="f89aa-216">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="f89aa-217">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="f89aa-217">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f89aa-218">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="f89aa-218">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f89aa-219">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="f89aa-219">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="f89aa-220">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="f89aa-220">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f89aa-221">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="f89aa-221">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f89aa-222">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="f89aa-222">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
