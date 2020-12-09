---
title: Solucionando problemas comuns de descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba mais sobre as etapas básicas de solução de problemas que você pode executar para resolver problemas comuns na descoberta eletrônica do Office 365.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4f1bad23705729c15976959a3902501f05da7600
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602032"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="3941b-103">Investigar, solucionar problemas e resolver problemas comuns de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="3941b-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="3941b-104">Este tópico aborda as etapas básicas de solução de problemas que podem ser tomadas para identificar e resolver problemas que você pode encontrar durante uma pesquisa de descoberta eletrônica ou em qualquer outro lugar no processo de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="3941b-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="3941b-105">A resolução de alguns desses cenários requer ajuda do suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3941b-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="3941b-106">As informações sobre quando entrar em contato com o suporte da Microsoft estão incluídas nas etapas de resolução.</span><span class="sxs-lookup"><span data-stu-id="3941b-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="3941b-107">Erro/problema: local ambíguo</span><span class="sxs-lookup"><span data-stu-id="3941b-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="3941b-108">Se você tentar adicionar o local da caixa de correio do usuário para pesquisar e houver objetos duplicados ou conflitantes com o mesmo userID no diretório do Exchange Online Protection (EOP), você receberá esse erro: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="3941b-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="3941b-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="3941b-109">Resolution</span></span>

<span data-ttu-id="3941b-110">Verifique se há usuários duplicados ou lista de distribuição com a mesma ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="3941b-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="3941b-111">Conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="3941b-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="3941b-112">Execute o seguinte comando para recuperar todas as instâncias do nome de usuário:</span><span class="sxs-lookup"><span data-stu-id="3941b-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="3941b-113">A saída de ' useralias@contoso.com ' seria semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="3941b-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="3941b-114">Nome</span><span class="sxs-lookup"><span data-stu-id="3941b-114">Name</span></span>|<span data-ttu-id="3941b-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="3941b-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="3941b-116">Alias, usuário</span><span class="sxs-lookup"><span data-stu-id="3941b-116">Alias, User</span></span>|<span data-ttu-id="3941b-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="3941b-117">MailUser</span></span>|
   > |<span data-ttu-id="3941b-118">Alias, usuário</span><span class="sxs-lookup"><span data-stu-id="3941b-118">Alias, User</span></span>|<span data-ttu-id="3941b-119">User</span><span class="sxs-lookup"><span data-stu-id="3941b-119">User</span></span>|

3. <span data-ttu-id="3941b-120">Se vários usuários forem retornados, localize e corrija o objeto conflitante.</span><span class="sxs-lookup"><span data-stu-id="3941b-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="3941b-121">Erro/problema: a pesquisa falha em locais específicos</span><span class="sxs-lookup"><span data-stu-id="3941b-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="3941b-122">Uma pesquisa de descoberta eletrônica ou conteúdo pode resultar no seguinte erro: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="3941b-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Falha na captura de tela de erro de local específico da pesquisa](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="3941b-124">Resolução</span><span class="sxs-lookup"><span data-stu-id="3941b-124">Resolution</span></span>

<span data-ttu-id="3941b-125">Se você receber esse erro, recomendamos verificar os locais que falharam na pesquisa e, em seguida, executar a pesquisa apenas nos locais com falha.</span><span class="sxs-lookup"><span data-stu-id="3941b-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="3941b-126">Conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3941b-126">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="3941b-127">Na saída do PowerShell, exiba os locais com falha no campo erros ou nos detalhes de status no erro do resultado da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3941b-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="3941b-128">Repita a pesquisa de descoberta eletrônica somente nos locais com falha.</span><span class="sxs-lookup"><span data-stu-id="3941b-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="3941b-129">Se você continuar recebendo esses erros, confira [locais de falha na tentativa](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) de obter mais etapas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="3941b-129">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="3941b-130">Erro/problema: arquivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="3941b-130">Error/issue: File not found</span></span>

<span data-ttu-id="3941b-131">Ao executar uma pesquisa de descoberta eletrônica que inclui o SharePoint Online e uma unidade para locais comerciais, você pode receber o erro, `File Not Found` embora o arquivo esteja localizado no site.</span><span class="sxs-lookup"><span data-stu-id="3941b-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="3941b-132">Este erro estará nos avisos de exportação e errors.csv ou ignorados items.csv.</span><span class="sxs-lookup"><span data-stu-id="3941b-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="3941b-133">Isso pode ocorrer se o arquivo não puder ser encontrado no site ou se o índice estiver desatualizado.</span><span class="sxs-lookup"><span data-stu-id="3941b-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="3941b-134">Este é o texto de um erro real (com ênfase adicionada).</span><span class="sxs-lookup"><span data-stu-id="3941b-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="3941b-135">28.06.2019 10:02:19_FailedToExportItem_Failed para baixar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3941b-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="3941b-136">Informações adicionais de diagnóstico: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: falha ao baixar do conteúdo 6ea52149-91cd-4965-b5bb-82ca6a3ec9be do tipo documento.</span><span class="sxs-lookup"><span data-stu-id="3941b-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="3941b-137">ID de correlação: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="3941b-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="3941b-138">ServerErrorCode:-2147024894---> Microsoft. SharePoint. Client. ServerException: ***arquivo não encontrado***.</span><span class="sxs-lookup"><span data-stu-id="3941b-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="3941b-139">em Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) em Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---fim de rastreamento de pilha de exceção interna---</span><span class="sxs-lookup"><span data-stu-id="3941b-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="3941b-140">Resolução</span><span class="sxs-lookup"><span data-stu-id="3941b-140">Resolution</span></span>

1. <span data-ttu-id="3941b-141">Verifique o local identificado na pesquisa para garantir que o local do arquivo está correto e adicionado nos locais de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3941b-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="3941b-142">Use os procedimentos a fim de [solicitar manualmente o rastreamento e a reindexação de um site, uma biblioteca ou uma lista](https://docs.microsoft.com/sharepoint/crawl-site-content) para reindexar o site.</span><span class="sxs-lookup"><span data-stu-id="3941b-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="3941b-143">Erro/problema: a pesquisa falha porque o destinatário não foi encontrado</span><span class="sxs-lookup"><span data-stu-id="3941b-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="3941b-144">Uma pesquisa de descoberta eletrônica falha com o erro `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="3941b-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="3941b-145">Esse erro pode ocorrer se o objeto de usuário não puder ser encontrado na proteção do Exchange Online (EOP) porque o objeto não foi sincronizado.</span><span class="sxs-lookup"><span data-stu-id="3941b-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="3941b-146">Resolução</span><span class="sxs-lookup"><span data-stu-id="3941b-146">Resolution</span></span>

1. <span data-ttu-id="3941b-147">Conecte-se ao [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3941b-147">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3941b-148">Execute o seguinte comando para verificar se o usuário foi sincronizado com a proteção do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="3941b-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="3941b-149">Deve haver um objeto de usuário de email para a pergunta do usuário.</span><span class="sxs-lookup"><span data-stu-id="3941b-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="3941b-150">Se nada for retornado, investigue o objeto user.</span><span class="sxs-lookup"><span data-stu-id="3941b-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="3941b-151">Entre em contato com o suporte da Microsoft se o objeto não puder ser sincronizado.</span><span class="sxs-lookup"><span data-stu-id="3941b-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="3941b-152">Erro/problema: a exportação dos resultados da pesquisa é lenta</span><span class="sxs-lookup"><span data-stu-id="3941b-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="3941b-153">Ao exportar os resultados da pesquisa de descoberta eletrônica ou de pesquisa de conteúdo no centro de segurança e conformidade, o download demora mais do que o esperado.</span><span class="sxs-lookup"><span data-stu-id="3941b-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="3941b-154">Você pode verificar para ver a quantidade de dados a serem baixados e, possivelmente, aumentar a velocidade de exportação.</span><span class="sxs-lookup"><span data-stu-id="3941b-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="3941b-155">Resolução</span><span class="sxs-lookup"><span data-stu-id="3941b-155">Resolution</span></span>

1. <span data-ttu-id="3941b-156">Conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3941b-156">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="3941b-157">Encontre a quantidade de dados a serem baixados nos parâmetros SearchResults e SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="3941b-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="3941b-158">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3941b-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="3941b-159">No campo resultados, localize os dados que foram exportados e exiba os erros encontrados.</span><span class="sxs-lookup"><span data-stu-id="3941b-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="3941b-160">Verifique o arquivo Trace. log localizado no diretório em que você exportou o conteúdo para qualquer erro.</span><span class="sxs-lookup"><span data-stu-id="3941b-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="3941b-161">Se você ainda tiver problemas, considere dividir as pesquisas que retornam um grande conjunto de resultados em pesquisas menores.</span><span class="sxs-lookup"><span data-stu-id="3941b-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="3941b-162">Por exemplo, você pode usar intervalos de datas em consultas de pesquisa para retornar um conjunto menor de resultados que podem ser baixados mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="3941b-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="3941b-163">Erro/problema: ocorreu o erro interno do servidor (500)</span><span class="sxs-lookup"><span data-stu-id="3941b-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="3941b-164">Ao executar uma pesquisa de descoberta eletrônica, se a pesquisa falhar continuamente com um erro semelhante a "erro interno do servidor (500)", você pode precisar executar novamente a pesquisa em locais de caixa de correio específicos.</span><span class="sxs-lookup"><span data-stu-id="3941b-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Captura de tela do erro do servidor interno 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="3941b-166">Resolução</span><span class="sxs-lookup"><span data-stu-id="3941b-166">Resolution</span></span>

1. <span data-ttu-id="3941b-167">Divida a pesquisa em pesquisas menores e execute a pesquisa novamente.</span><span class="sxs-lookup"><span data-stu-id="3941b-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="3941b-168">Tente usar um intervalo de datas menor ou limitar o número de locais que estão sendo pesquisados.</span><span class="sxs-lookup"><span data-stu-id="3941b-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="3941b-169">Conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3941b-169">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="3941b-170">Examine a saída para obter resultados e erros.</span><span class="sxs-lookup"><span data-stu-id="3941b-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="3941b-171">Examine o arquivo Trace. log.</span><span class="sxs-lookup"><span data-stu-id="3941b-171">Examine the trace.log file.</span></span> <span data-ttu-id="3941b-172">Ele está localizado na mesma pasta para a qual você exportou os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3941b-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="3941b-173">Entrar em contato com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3941b-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="3941b-174">Erro/problema: isenções não sincronizar</span><span class="sxs-lookup"><span data-stu-id="3941b-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="3941b-175">erro de distribuição de política de retenção de caso de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="3941b-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="3941b-176">O erro diz:</span><span class="sxs-lookup"><span data-stu-id="3941b-176">The error reads:</span></span>

> <span data-ttu-id="3941b-177">"Recursos: está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="3941b-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="3941b-178">Pode levar mais duas horas para atualizar o status de implantação final, portanto, verifique novamente em algumas horas. "</span><span class="sxs-lookup"><span data-stu-id="3941b-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="3941b-179">Resolução</span><span class="sxs-lookup"><span data-stu-id="3941b-179">Resolution</span></span>

1. <span data-ttu-id="3941b-180">Conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e, em seguida, execute o seguinte comando para uma retenção de caso de descoberta eletrônica:</span><span class="sxs-lookup"><span data-stu-id="3941b-180">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="3941b-181">Para uma política de retenção, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3941b-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="3941b-182">Examine o valor no parâmetro DistributionDetail para obter erros como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3941b-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="3941b-183">Erro: recursos: está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="3941b-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="3941b-184">Pode levar mais duas horas para atualizar o status de implantação final, portanto, verifique novamente em algumas horas. "</span><span class="sxs-lookup"><span data-stu-id="3941b-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="3941b-185">Tente executar o parâmetro RetryDistribution na política em questão:</span><span class="sxs-lookup"><span data-stu-id="3941b-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="3941b-186">Para isenções de caso de descoberta eletrônica:</span><span class="sxs-lookup"><span data-stu-id="3941b-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="3941b-187">Para políticas de retenção:</span><span class="sxs-lookup"><span data-stu-id="3941b-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="3941b-188">Entrar em contato com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3941b-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="3941b-189">Erro: "a condição especificada usando cabeçalho (s) condicional HTTP não é atendida"</span><span class="sxs-lookup"><span data-stu-id="3941b-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="3941b-190">Ao baixar os resultados da pesquisa usando a ferramenta de exportação de descoberta eletrônica, é possível que você possa receber o seguinte erro: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` este é um erro transitório, que geralmente ocorre no local de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="3941b-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="3941b-191">Resolução</span><span class="sxs-lookup"><span data-stu-id="3941b-191">Resolution</span></span>

<span data-ttu-id="3941b-192">Para resolver esse problema, tente [baixar novamente os resultados da pesquisa](export-search-results.md#step-2-download-the-search-results), o que irá reiniciar a ferramenta de exportação de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="3941b-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="3941b-193">Confira também</span><span class="sxs-lookup"><span data-stu-id="3941b-193">See Also</span></span>

- [<span data-ttu-id="3941b-194">Dicas para evitar erros de localização de conteúdo</span><span class="sxs-lookup"><span data-stu-id="3941b-194">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
