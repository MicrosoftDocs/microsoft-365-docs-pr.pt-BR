---
title: Problemas comuns de descoberta eletrônica do Troublshooting
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Investigue, solucione problemas e resolva problemas comuns na descoberta eletrônica do Office 365.
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207284"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="9ecd4-103">Investigar, solucionar problemas e resolver problemas comuns de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="9ecd4-103">Investigate, troubleshoot and resolve common eDiscovery issues</span></span>

<span data-ttu-id="9ecd4-104">Este tópico aborda as etapas básicas de solução de problemas que podem ser tomadas para identificar e resolver problemas que você pode encontrar durante uma pesquisa de descoberta eletrônica ou em qualquer outro lugar no processo de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="9ecd4-105">A resolução de alguns desses cenários requer ajuda dos serviços de suporte ao cliente (CSS).</span><span class="sxs-lookup"><span data-stu-id="9ecd4-105">Resolving some of these scenarios requires help from Customer Support Services (CSS).</span></span> <span data-ttu-id="9ecd4-106">As informações sobre quando entrar em contato com CSS estão incluídas nas etapas de resolução.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-106">Information on when to contact CSS is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="9ecd4-107">Localização ambígua de erro/problema</span><span class="sxs-lookup"><span data-stu-id="9ecd4-107">Error/issue ambiguous location</span></span>

<span data-ttu-id="9ecd4-108">Você receberá este erro "a pesquisa de conformidade contém o seguinte local `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` inválido se você tentou adicionar o local da caixa de correio do usuário para pesquisar e há objetos duplicados ou conflitantes com a mesma ID de usuário na proteção do Exchange Online (EOP) Directory.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-108">You'll receive this error "The compliance search contains the following invalid location `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` if you tried to add user’s mailbox location to search and there are duplicate or conflicting objects with the same user id in the Exchange Online Protection (EOP) directory.</span></span>

### <a name="resolution"></a><span data-ttu-id="9ecd4-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="9ecd4-109">Resolution</span></span>

<span data-ttu-id="9ecd4-110">Verifique se há usuários duplicados ou lista de distribuição com a mesma ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="9ecd4-111">Conecte-se ao [PowerShell do Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="9ecd4-111">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="9ecd4-112">Recuperar todas as instâncias do nome de usuário, digite:</span><span class="sxs-lookup"><span data-stu-id="9ecd4-112">Retrieve all instances of the username, type:</span></span>

```powershell
Get-Recipient <username>
```

<span data-ttu-id="9ecd4-113">A saída de ' useralias@contoso.com ' pode ser</span><span class="sxs-lookup"><span data-stu-id="9ecd4-113">The output for 'useralias@contoso.com' might be</span></span>

> 
> |<span data-ttu-id="9ecd4-114">Nome</span><span class="sxs-lookup"><span data-stu-id="9ecd4-114">Name</span></span>  |<span data-ttu-id="9ecd4-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="9ecd4-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="9ecd4-116">Alias, usuário</span><span class="sxs-lookup"><span data-stu-id="9ecd4-116">Alias, User</span></span>     |<span data-ttu-id="9ecd4-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="9ecd4-117">MailUser</span></span>         |
> |<span data-ttu-id="9ecd4-118">Alias, usuário</span><span class="sxs-lookup"><span data-stu-id="9ecd4-118">Alias, User</span></span>     |<span data-ttu-id="9ecd4-119">Usuário</span><span class="sxs-lookup"><span data-stu-id="9ecd4-119">User</span></span>         |

3. <span data-ttu-id="9ecd4-120">Se vários usuários forem retornados, localize e corrija o objeto conflitante.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="9ecd4-121">Falha de pesquisa de erro/problema em locais específicos</span><span class="sxs-lookup"><span data-stu-id="9ecd4-121">Error/issue search fails on specific locations</span></span>

<span data-ttu-id="9ecd4-122">Uma pesquisa de descoberta eletrônica ou conteúdo pode resultar no seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="9ecd4-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="9ecd4-123">Esta pesquisa foi concluída com erros (#).</span><span class="sxs-lookup"><span data-stu-id="9ecd4-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="9ecd4-124">Você gostaria de repetir a pesquisa nos locais com falha?</span><span class="sxs-lookup"><span data-stu-id="9ecd4-124">Would you like to retry the search on the failed locations?</span></span>

![falha na captura de tela de erro de local específico de pesquisa]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="9ecd4-126">Resolução</span><span class="sxs-lookup"><span data-stu-id="9ecd4-126">Resolution</span></span>

<span data-ttu-id="9ecd4-127">Se você receber esse erro, recomendamos verificar os locais que falharam na pesquisa e, em seguida, executar novamente a pesquisa nos locais com falha.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-127">If you receive this error, we recommend that you verify the locations that failed in the search  then re-run the search only on the failed locations.</span></span>

1. <span data-ttu-id="9ecd4-128">Conecte-se ao [PowerShell do Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="9ecd4-128">Connect to [Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="9ecd4-129">Tipo:</span><span class="sxs-lookup"><span data-stu-id="9ecd4-129">Type:</span></span>

```powershell
Get-Compliancesearch searchname|fl 
```

3. <span data-ttu-id="9ecd4-130">Na saída do PowerShell, exiba os locais com falha no campo erros ou nos detalhes de status no erro do resultado da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-130">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>
1. <span data-ttu-id="9ecd4-131">Repita a pesquisa de descoberta eletrônica somente nos locais com falha.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-131">Retry the eDiscovery search on the failed locations only.</span></span>
1. <span data-ttu-id="9ecd4-132">Se você continuar recebendo esse erro, veja [locais de falha na tentativa](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) de etapas adicionais de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-132">If you continue to receive these error, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for additional troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="9ecd4-133">Erro/arquivo de problema não encontrado</span><span class="sxs-lookup"><span data-stu-id="9ecd4-133">Error/issue file not found</span></span>

<span data-ttu-id="9ecd4-134">Ao executar uma pesquisa de descoberta eletrônica que inclui o SharePoint Online e uma unidade para locais comerciais, você pode `File Not Found` receber o erro, embora o arquivo esteja localizado no site.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-134">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="9ecd4-135">Este erro estará nos avisos de exportação e erros. csv ou itens ignorados. csv isso pode ocorrer se o arquivo não puder ser localizado no site ou se o índice estiver desatualizado.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-135">This error will be in the export warnings and errors.csv or skipped items.csv  This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="9ecd4-136">Este é o texto de um erro real, com ênfase adicionada.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="9ecd4-137">28.06.2019 10:02:19_FailedToExportItem_Failed para baixar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="9ecd4-138">Informações adicionais de diagnóstico: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: falha ao baixar do conteúdo 6ea52149-91cd-4965-b5bb-82ca6a3ec9be do tipo documento.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="9ecd4-139">ID de correlação: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="9ecd4-140">ServerErrorCode:-2147024894---> Microsoft. SharePoint. Client. ServerException: ***arquivo não encontrado***.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="9ecd4-141">em Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) em Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---fim de rastreamento de pilha de exceção interna---</span><span class="sxs-lookup"><span data-stu-id="9ecd4-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="9ecd4-142">Resolução</span><span class="sxs-lookup"><span data-stu-id="9ecd4-142">Resolution</span></span>

1. <span data-ttu-id="9ecd4-143">Verifique o local identificado na pesquisa para garantir que o local do arquivo está correto e adicionado nos locais de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>
2. <span data-ttu-id="9ecd4-144">Use os procedimentos a fim de [solicitar manualmente o rastreamento e a reindexação de um site, uma biblioteca ou uma lista](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) para reindexar o site.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-recipient-not-found"></a><span data-ttu-id="9ecd4-145">Erro/pesquisa de problema falha de destinatário não encontrada</span><span class="sxs-lookup"><span data-stu-id="9ecd4-145">Error/issue search fails recipient not found</span></span>

<span data-ttu-id="9ecd4-146">a pesquisa de descoberta eletrônica `recipient not found`falha com erro.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-146">eDiscovery search fails with error `recipient not found`.</span></span> <span data-ttu-id="9ecd4-147">Esse erro pode ocorrer se o objeto de usuário não puder ser encontrado na proteção do Exchange Online (EOP) porque o objeto não foi sincronizado.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="9ecd4-148">Resolução</span><span class="sxs-lookup"><span data-stu-id="9ecd4-148">Resolution</span></span>

1. <span data-ttu-id="9ecd4-149">Conecte-se ao [PowerShell do Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="9ecd4-149">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="9ecd4-150">Verifique se o objeto do usuário está sincronizado com o tipo de proteção do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="9ecd4-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

```powershell
Get-Recipient userId|fl
```

3. <span data-ttu-id="9ecd4-151">Deve haver um objeto MailUser para a pergunta do usuário.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-151">There should be a mailuser object for the user question.</span></span> <span data-ttu-id="9ecd4-152">Se nada for retornado, investigue o objeto user.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="9ecd4-153">Contato CSS se o objeto não pode ser sincronizado.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-153">Contact CSS if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="9ecd4-154">Erro/problema a exportação dos resultados da pesquisa é lenta</span><span class="sxs-lookup"><span data-stu-id="9ecd4-154">Error/issue exporting search results is slow</span></span>

<span data-ttu-id="9ecd4-155">Ao exportar os resultados da pesquisa de descoberta eletrônica ou de pesquisa de conteúdo no centro de segurança e conformidade, o download demora mais do que o esperado.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="9ecd4-156">Você pode verificar para ver a quantidade de dados a serem baixados e, possivelmente, aumentar a velocidade de exportação.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="9ecd4-157">Resolução</span><span class="sxs-lookup"><span data-stu-id="9ecd4-157">Resolution</span></span>

1.  <span data-ttu-id="9ecd4-158">Tente usar as etapas identificadas no artigo [aumentar as velocidades de download](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="9ecd4-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>
2.  <span data-ttu-id="9ecd4-159">Se você ainda tiver problemas, conecte-se à [proteção do Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) e digite:</span><span class="sxs-lookup"><span data-stu-id="9ecd4-159">If you still have issues, connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname\fl
```

4. <span data-ttu-id="9ecd4-160">Encontre a quantidade de dados a serem baixados nos parâmetros SearchResults e SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>
5. <span data-ttu-id="9ecd4-161">Tipo:</span><span class="sxs-lookup"><span data-stu-id="9ecd4-161">Type:</span></span>

```powershell
Get-ComplianceSearchAction |fl
```

6. <span data-ttu-id="9ecd4-162">No campo resultados, localize os dados que foram exportados e exiba os erros encontrados.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-162">In the results field find the data that has been exported and view any errors encountered.</span></span>
7. <span data-ttu-id="9ecd4-163">Verifique o arquivo Trace. log localizado no diretório em que você exportou o conteúdo para qualquer erro.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="9ecd4-164">Erro/problema ocorreu o erro interno do servidor (500)</span><span class="sxs-lookup"><span data-stu-id="9ecd4-164">Error/issue "Internal server error (500) occurred"</span></span>

<span data-ttu-id="9ecd4-165">Ao executar uma pesquisa de descoberta eletrônica, se a pesquisa falhar continuamente com um erro semelhante a "erro interno do servidor (500)", você pode precisar executar novamente a pesquisa em locais de caixa de correio específicos.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need re-run the search only on specific mailbox locations.</span></span>

![captura de tela do erro do servidor interno 500](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="9ecd4-167">Resolução</span><span class="sxs-lookup"><span data-stu-id="9ecd4-167">Resolution</span></span>

1. <span data-ttu-id="9ecd4-168">Divida a pesquisa em pesquisas menores e execute a pesquisa novamente.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="9ecd4-169">Tente usar um intervalo de datas menor ou limitar o número de locais que estão sendo pesquisados.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-169">Try using a smaller date range or limit the number of locations being searched.</span></span>
2. <span data-ttu-id="9ecd4-170">Conectar-se ao PowerShell e ao tipo de [proteção do Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) :</span><span class="sxs-lookup"><span data-stu-id="9ecd4-170">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname |fl
```

3. <span data-ttu-id="9ecd4-171">Examine a saída para obter resultados e erros.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-171">Examine the output for results and errors.</span></span>
3. <span data-ttu-id="9ecd4-172">Examine o arquivo Trace. log.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-172">Examine the trace.log file.</span></span> <span data-ttu-id="9ecd4-173">Ele será na mesma pasta para a qual você enviou a exportação.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-173">It will be in the same folder that you sent the export to.</span></span>
4. <span data-ttu-id="9ecd4-174">Contatar o CSS de suporte.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-174">Contact Support CSS.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="9ecd4-175">Erro/problema contém não sincronizar</span><span class="sxs-lookup"><span data-stu-id="9ecd4-175">Error/issue holds don't sync</span></span>

<span data-ttu-id="9ecd4-176">erro de distribuição de política de retenção de caso de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="9ecd4-177">O erro diz:</span><span class="sxs-lookup"><span data-stu-id="9ecd4-177">The error reads:</span></span>

> <span data-ttu-id="9ecd4-178">"Recursos: está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="9ecd4-179">Pode levar mais duas horas para atualizar o status de implantação final, portanto, verifique novamente em algumas horas. "</span><span class="sxs-lookup"><span data-stu-id="9ecd4-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="9ecd4-180">Resolução</span><span class="sxs-lookup"><span data-stu-id="9ecd4-180">Resolution</span></span>

1.  <span data-ttu-id="9ecd4-181">Conectar-se ao PowerShell e ao tipo de [proteção do Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) :</span><span class="sxs-lookup"><span data-stu-id="9ecd4-181">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. <span data-ttu-id="9ecd4-182">Examine o valor no parâmetro Distributiondetail para obter erros como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ecd4-182">Examine the value in the Distributiondetail parameter for errors like the following:</span></span>

> <span data-ttu-id="9ecd4-183">Se houver erro, crie escalonamento para PG para forçar uma nova sincronização manual na política.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="9ecd4-184">CSS do contato.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-184">Contact CSS.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ecd4-185">Confira também</span><span class="sxs-lookup"><span data-stu-id="9ecd4-185">See Also</span></span>
- [<span data-ttu-id="9ecd4-186">Dicas para evitar erros de localização de conteúdo</span><span class="sxs-lookup"><span data-stu-id="9ecd4-186">Tips to avoid content location errors</span></span>](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)