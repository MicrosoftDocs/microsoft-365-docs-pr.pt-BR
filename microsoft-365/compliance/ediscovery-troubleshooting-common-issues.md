---
title: Solução de problemas comuns de DescobertaScoberta
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
description: Saiba mais sobre as etapas básicas de solução de problemas que você pode seguir para resolver problemas comuns na Descoberta eDiscovery do Office 365.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1fbda23b730956db42d8e7a92218fb9837868b8
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988135"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="400b3-103">Investigar, solucionar problemas e resolver problemas comuns de DescobertaScoberta</span><span class="sxs-lookup"><span data-stu-id="400b3-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="400b3-104">Este tópico aborda as etapas básicas de solução de problemas que você pode seguir para identificar e resolver problemas que você pode encontrar durante uma pesquisa de Descoberta eDiscovery ou em outro lugar no processo de Descoberta eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="400b3-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="400b3-105">Resolver alguns desses cenários requer ajuda do Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="400b3-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="400b3-106">As informações sobre quando entrar em contato com o Suporte da Microsoft estão incluídas nas etapas de resolução.</span><span class="sxs-lookup"><span data-stu-id="400b3-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="400b3-107">Erro/problema: local ambíguo</span><span class="sxs-lookup"><span data-stu-id="400b3-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="400b3-108">Se você tentar adicionar o local da caixa de correio do usuário para pesquisar e houver objetos duplicados ou conflitantes com a mesma ID de usuário no diretório do Exchange Online Protection (EOP), você receberá este erro: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="400b3-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="400b3-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="400b3-109">Resolution</span></span>

<span data-ttu-id="400b3-110">Verifique se há usuários duplicados ou lista de distribuição com a mesma ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="400b3-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="400b3-111">Conecte-se [ao PowerShell & Centro de Conformidade e Segurança.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="400b3-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="400b3-112">Execute o seguinte comando para recuperar todas as instâncias do nome de usuário:</span><span class="sxs-lookup"><span data-stu-id="400b3-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="400b3-113">A saída para "useralias@contoso.com" seria semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="400b3-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="400b3-114">Nome</span><span class="sxs-lookup"><span data-stu-id="400b3-114">Name</span></span>|<span data-ttu-id="400b3-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="400b3-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="400b3-116">Alias, Usuário</span><span class="sxs-lookup"><span data-stu-id="400b3-116">Alias, User</span></span>|<span data-ttu-id="400b3-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="400b3-117">MailUser</span></span>|
   > |<span data-ttu-id="400b3-118">Alias, Usuário</span><span class="sxs-lookup"><span data-stu-id="400b3-118">Alias, User</span></span>|<span data-ttu-id="400b3-119">Usuário</span><span class="sxs-lookup"><span data-stu-id="400b3-119">User</span></span>|

3. <span data-ttu-id="400b3-120">Se vários usuários são retornados, localize e corrige o objeto conflitante.</span><span class="sxs-lookup"><span data-stu-id="400b3-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="400b3-121">Erro/problema: a pesquisa falha em locais específicos</span><span class="sxs-lookup"><span data-stu-id="400b3-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="400b3-122">Uma pesquisa de conteúdo ou descoberta de eDiscovery pode gerar o seguinte erro: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="400b3-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Localização específica da pesquisa falha na captura de tela de erro](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="400b3-124">Resolução</span><span class="sxs-lookup"><span data-stu-id="400b3-124">Resolution</span></span>

<span data-ttu-id="400b3-125">Se você receber esse erro, recomendamos que verifique os locais que falharam na pesquisa e, em seguida, reruncar a pesquisa somente nos locais com falha.</span><span class="sxs-lookup"><span data-stu-id="400b3-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="400b3-126">[Conecte-se ao PowerShell do & Centro de Conformidade](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e Segurança e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="400b3-126">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="400b3-127">Na saída do PowerShell, veja os locais com falha no campo de erros ou nos detalhes de status no erro da saída da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="400b3-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="400b3-128">Retry the eDiscovery search on the failed locations only.</span><span class="sxs-lookup"><span data-stu-id="400b3-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="400b3-129">Se você continuar recebendo esses erros, consulte [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span><span class="sxs-lookup"><span data-stu-id="400b3-129">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="400b3-130">Erro/problema: arquivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="400b3-130">Error/issue: File not found</span></span>

<span data-ttu-id="400b3-131">Ao executar uma pesquisa de Descoberta Online que inclui locais do SharePoint Online e do OneDrive for Business, você pode receber o erro, embora o arquivo está `File Not Found` localizado no site.</span><span class="sxs-lookup"><span data-stu-id="400b3-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="400b3-132">Esse erro estará nos avisos de exportação e errors.csv ou ignorado items.csv.</span><span class="sxs-lookup"><span data-stu-id="400b3-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="400b3-133">Isso poderá ocorrer se o arquivo não puder ser encontrado no site ou se o índice estiver desa datado.</span><span class="sxs-lookup"><span data-stu-id="400b3-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="400b3-134">Aqui está o texto de um erro real (com ênfase adicionada).</span><span class="sxs-lookup"><span data-stu-id="400b3-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="400b3-135">28.06.2019 10:02:19_FailedToExportItem_Failed para baixar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="400b3-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="400b3-136">Informações de diagnóstico adicionais : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Falha ao baixar do conteúdo 6ea52149-91cd-4965-b5bb-82ca6a3ec9be do tipo Documento.</span><span class="sxs-lookup"><span data-stu-id="400b3-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="400b3-137">ID de Correlação: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="400b3-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="400b3-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***arquivo não encontrado.***</span><span class="sxs-lookup"><span data-stu-id="400b3-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="400b3-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span><span class="sxs-lookup"><span data-stu-id="400b3-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="400b3-140">Resolução</span><span class="sxs-lookup"><span data-stu-id="400b3-140">Resolution</span></span>

1. <span data-ttu-id="400b3-141">Verifique o local identificado na pesquisa para garantir que o local do arquivo está correto e adicionado nos locais de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="400b3-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="400b3-142">Use os procedimentos na solicitação manual de rastreamento e [reindexação](https://docs.microsoft.com/sharepoint/crawl-site-content) de um site, biblioteca ou lista para reindexar o site.</span><span class="sxs-lookup"><span data-stu-id="400b3-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="400b3-143">Erro/problema: a pesquisa falha porque o destinatário não foi encontrado</span><span class="sxs-lookup"><span data-stu-id="400b3-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="400b3-144">Uma pesquisa de Descoberta Descoberta falha com o erro `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="400b3-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="400b3-145">Esse erro poderá ocorrer se o objeto do usuário não puder ser encontrado no Exchange Online Protection (EOP) porque o objeto não foi sincronizado.</span><span class="sxs-lookup"><span data-stu-id="400b3-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="400b3-146">Resolução</span><span class="sxs-lookup"><span data-stu-id="400b3-146">Resolution</span></span>

1. <span data-ttu-id="400b3-147">Conecte-se [ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="400b3-147">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="400b3-148">Execute o seguinte comando para verificar se o usuário está sincronizado com o Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="400b3-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="400b3-149">Deve haver um objeto de usuário de email para a pergunta do usuário.</span><span class="sxs-lookup"><span data-stu-id="400b3-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="400b3-150">Se nada for retornado, investigue o objeto do usuário.</span><span class="sxs-lookup"><span data-stu-id="400b3-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="400b3-151">Entre em contato com o Suporte da Microsoft se o objeto não puder ser sincronizado.</span><span class="sxs-lookup"><span data-stu-id="400b3-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="400b3-152">Erro/problema: a exportação dos resultados da pesquisa está lenta</span><span class="sxs-lookup"><span data-stu-id="400b3-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="400b3-153">Ao exportar os resultados da pesquisa da Descoberta e ou da Pesquisa de Conteúdo no Centro de Conformidade e Segurança, o download leva mais tempo do que o esperado.</span><span class="sxs-lookup"><span data-stu-id="400b3-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="400b3-154">Você pode verificar a quantidade de dados a serem baixados e possivelmente aumentar a velocidade de exportação.</span><span class="sxs-lookup"><span data-stu-id="400b3-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="400b3-155">Resolução</span><span class="sxs-lookup"><span data-stu-id="400b3-155">Resolution</span></span>

1. <span data-ttu-id="400b3-156">[Conecte-se ao PowerShell do & Centro de Conformidade](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e Segurança e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="400b3-156">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="400b3-157">Encontre a quantidade de dados a serem baixados nos parâmetros SearchResults e SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="400b3-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="400b3-158">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="400b3-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="400b3-159">No campo de resultados, encontre os dados que foram exportados e veja quaisquer erros encontrados.</span><span class="sxs-lookup"><span data-stu-id="400b3-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="400b3-160">Verifique se há erros no arquivo trace.log localizado no diretório para o qual você exportou o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="400b3-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="400b3-161">Se você ainda tiver problemas, considere dividir as pesquisas que retornam um grande conjunto de resultados em pesquisas menores.</span><span class="sxs-lookup"><span data-stu-id="400b3-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="400b3-162">Por exemplo, você pode usar intervalos de datas em consultas de pesquisa para retornar um conjunto menor de resultados que podem ser baixados mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="400b3-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="400b3-163">Erro/problema: "Erro interno do servidor (500) ocorreu"</span><span class="sxs-lookup"><span data-stu-id="400b3-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="400b3-164">Ao executar uma pesquisa de Descoberta Eletrônico, se a pesquisa falhar continuamente com um erro semelhante a "Erro interno do servidor (500) ocorreu", talvez seja necessário executar a pesquisa apenas em locais de caixa de correio específicos.</span><span class="sxs-lookup"><span data-stu-id="400b3-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Captura de tela de erro 500 do servidor interno](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="400b3-166">Resolução</span><span class="sxs-lookup"><span data-stu-id="400b3-166">Resolution</span></span>

1. <span data-ttu-id="400b3-167">Quebrar a pesquisa em pesquisas menores e executar a pesquisa novamente.</span><span class="sxs-lookup"><span data-stu-id="400b3-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="400b3-168">Tente usar um intervalo de datas menor ou limite o número de locais que estão sendo pesquisados.</span><span class="sxs-lookup"><span data-stu-id="400b3-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="400b3-169">[Conecte-se ao PowerShell do & Centro de Conformidade](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e Segurança e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="400b3-169">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="400b3-170">Examine a saída em busca de resultados e erros.</span><span class="sxs-lookup"><span data-stu-id="400b3-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="400b3-171">Examine o arquivo trace.log.</span><span class="sxs-lookup"><span data-stu-id="400b3-171">Examine the trace.log file.</span></span> <span data-ttu-id="400b3-172">Ele está localizado na mesma pasta para a onde você exportou os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="400b3-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="400b3-173">Entrar em contato com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="400b3-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="400b3-174">Erro/problema: as respeções não são sincronizadas</span><span class="sxs-lookup"><span data-stu-id="400b3-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="400b3-175">Erro de distribuição de sincronização de política de espera de descoberta do eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="400b3-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="400b3-176">O erro lê:</span><span class="sxs-lookup"><span data-stu-id="400b3-176">The error reads:</span></span>

> <span data-ttu-id="400b3-177">"Recursos: Está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="400b3-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="400b3-178">Pode levar mais 2 horas para atualizar o status final da implantação, portanto, verifique novamente em algumas horas."</span><span class="sxs-lookup"><span data-stu-id="400b3-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="400b3-179">Resolução</span><span class="sxs-lookup"><span data-stu-id="400b3-179">Resolution</span></span>

1. <span data-ttu-id="400b3-180">[Conecte-se ao PowerShell & Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) de Conformidade e Segurança e execute o seguinte comando para um caso de descoberta de eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="400b3-180">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="400b3-181">Para uma política de retenção, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="400b3-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="400b3-182">Examine o valor no parâmetro DistributionDetail em busca de erros como os seguintes:</span><span class="sxs-lookup"><span data-stu-id="400b3-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="400b3-183">Erro: Recursos: a implantação da política está demorando mais do que o esperado.</span><span class="sxs-lookup"><span data-stu-id="400b3-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="400b3-184">Pode levar mais 2 horas para atualizar o status final da implantação, portanto, verifique novamente em algumas horas."</span><span class="sxs-lookup"><span data-stu-id="400b3-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="400b3-185">Tente executar o parâmetro RetryDistribution na política em questão:</span><span class="sxs-lookup"><span data-stu-id="400b3-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="400b3-186">Para o caso de Descoberta eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="400b3-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="400b3-187">Para políticas de retenção:</span><span class="sxs-lookup"><span data-stu-id="400b3-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="400b3-188">Entrar em contato com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="400b3-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="400b3-189">Erro: "A condição especificada usando cabeçalhos condicionais HTTP não é atendida"</span><span class="sxs-lookup"><span data-stu-id="400b3-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="400b3-190">Ao baixar os resultados da pesquisa usando a Ferramenta de Exportação de Descobertas, é possível que você receba o seguinte erro: este é um erro transitório, que normalmente ocorre no local de armazenamento do `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure.</span><span class="sxs-lookup"><span data-stu-id="400b3-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="400b3-191">Resolução</span><span class="sxs-lookup"><span data-stu-id="400b3-191">Resolution</span></span>

<span data-ttu-id="400b3-192">Para resolver esse problema, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span><span class="sxs-lookup"><span data-stu-id="400b3-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="400b3-193">Erro/problema: a exportação baixada não mostra resultados</span><span class="sxs-lookup"><span data-stu-id="400b3-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="400b3-194">Após uma exportação bem-sucedida, o download concluído por meio da ferramenta de exportação mostra zero arquivos nos resultados.</span><span class="sxs-lookup"><span data-stu-id="400b3-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="400b3-195">Resolução</span><span class="sxs-lookup"><span data-stu-id="400b3-195">Resolution</span></span>

<span data-ttu-id="400b3-196">Esse é um problema do lado do cliente e, para remediar, tente as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="400b3-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="400b3-197">Tente usar outro cliente/computador para baixar.</span><span class="sxs-lookup"><span data-stu-id="400b3-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="400b3-198">Certifique-se de baixar para uma unidade local.</span><span class="sxs-lookup"><span data-stu-id="400b3-198">Make sure to download to a local drive.</span></span>

3. <span data-ttu-id="400b3-199">Certifique-se de que o scanner de vírus não está em execução.</span><span class="sxs-lookup"><span data-stu-id="400b3-199">Make sure the virus scanner is not running.</span></span>

4. <span data-ttu-id="400b3-200">Certifique-se de que nenhuma outra exportação está baixando para a mesma pasta ou qualquer pasta pai.</span><span class="sxs-lookup"><span data-stu-id="400b3-200">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

5. <span data-ttu-id="400b3-201">Se as etapas anteriores não funcionarem, desabilite a replicação e a duplicação.</span><span class="sxs-lookup"><span data-stu-id="400b3-201">If the previous steps did not work, disable zipping and de-duplication.</span></span>

6. <span data-ttu-id="400b3-202">Se isso funcionar, o problema é devido a um scanner de vírus local ou um problema de disco.</span><span class="sxs-lookup"><span data-stu-id="400b3-202">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
