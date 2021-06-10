---
title: Solução de problemas comuns de Descoberta e Descoberta
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
description: Saiba mais sobre as etapas básicas de solução de problemas que você pode tomar para resolver problemas comuns Office 365 Descoberta eDiscovery.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28c092cefbdd8add46d3f36aa118e230d16a918a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822233"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="e943c-103">Investigar, solucionar problemas e resolver problemas comuns de Descoberta e Descoberta</span><span class="sxs-lookup"><span data-stu-id="e943c-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="e943c-104">Este tópico aborda as etapas básicas de solução de problemas que podem ser tomadas para identificar e resolver problemas que podem ser encontrados durante uma pesquisa de Descoberta E ou em outro lugar no processo de Descoberta eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e943c-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="e943c-105">A resolução de alguns desses cenários requer ajuda do Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e943c-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="e943c-106">As informações sobre quando entrar em contato com o Suporte da Microsoft estão incluídas nas etapas de resolução.</span><span class="sxs-lookup"><span data-stu-id="e943c-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="e943c-107">Erro/problema: local ambíguo</span><span class="sxs-lookup"><span data-stu-id="e943c-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="e943c-108">Se você tentar adicionar o local da caixa de correio do usuário à pesquisa e houver objetos duplicados ou conflitantes com o mesmo userID no diretório Proteção do Exchange Online (EOP), você receberá este erro: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="e943c-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="e943c-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-109">Resolution</span></span>

<span data-ttu-id="e943c-110">Verifique se há usuários duplicados ou lista de distribuição com a mesma ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="e943c-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="e943c-111">Conexão [para o Centro de Conformidade & Segurança powerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e943c-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e943c-112">Execute o seguinte comando para recuperar todas as instâncias do nome de usuário:</span><span class="sxs-lookup"><span data-stu-id="e943c-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="e943c-113">A saída para 'useralias@contoso.com' seria semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="e943c-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="e943c-114">Nome</span><span class="sxs-lookup"><span data-stu-id="e943c-114">Name</span></span>|<span data-ttu-id="e943c-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="e943c-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="e943c-116">Alias, User</span><span class="sxs-lookup"><span data-stu-id="e943c-116">Alias, User</span></span>|<span data-ttu-id="e943c-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="e943c-117">MailUser</span></span>|
   > |<span data-ttu-id="e943c-118">Alias, User</span><span class="sxs-lookup"><span data-stu-id="e943c-118">Alias, User</span></span>|<span data-ttu-id="e943c-119">Usuário</span><span class="sxs-lookup"><span data-stu-id="e943c-119">User</span></span>|

3. <span data-ttu-id="e943c-120">Se vários usuários são retornados, localize e corrige o objeto conflitante.</span><span class="sxs-lookup"><span data-stu-id="e943c-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="e943c-121">Erro/problema: a pesquisa falha em locais específicos</span><span class="sxs-lookup"><span data-stu-id="e943c-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="e943c-122">Uma descoberta de conteúdo ou descoberta de conteúdo pode gerar o seguinte erro: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="e943c-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Local específico da pesquisa falha na captura de tela de erro](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="e943c-124">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-124">Resolution</span></span>

<span data-ttu-id="e943c-125">Se você receber esse erro, recomendamos que você verifique os locais que falharam na pesquisa e, em seguida, reprise a pesquisa somente nos locais com falha.</span><span class="sxs-lookup"><span data-stu-id="e943c-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="e943c-126">Conexão para o Centro de Conformidade & Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e943c-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="e943c-127">Na saída do PowerShell, veja os locais com falha no campo de erros ou nos detalhes de status no erro da saída de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e943c-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="e943c-128">Repetir a pesquisa de Descoberta e somente nos locais com falha.</span><span class="sxs-lookup"><span data-stu-id="e943c-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="e943c-129">Se você continuar a receber esses erros, consulte Repetir locais [com falha](/Office365/SecurityCompliance/retry-failed-content-search) para obter mais etapas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="e943c-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="e943c-130">Erro/problema: Arquivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="e943c-130">Error/issue: File not found</span></span>

<span data-ttu-id="e943c-131">Ao executar uma pesquisa de Descoberta Virtual que inclui SharePoint online e locais do One Drive For Business, você pode receber o erro, embora o arquivo está `File Not Found` localizado no site.</span><span class="sxs-lookup"><span data-stu-id="e943c-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="e943c-132">Esse erro estará nos avisos de exportação e errors.csv ou ignorado items.csv.</span><span class="sxs-lookup"><span data-stu-id="e943c-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="e943c-133">Isso pode ocorrer se o arquivo não puder ser encontrado no site ou se o índice estiver desa datado.</span><span class="sxs-lookup"><span data-stu-id="e943c-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="e943c-134">Aqui está o texto de um erro real (com ênfase adicionada).</span><span class="sxs-lookup"><span data-stu-id="e943c-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="e943c-135">28.06.2019 10:02:19_FailedToExportItem_Failed baixar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e943c-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="e943c-136">Informações de diagnóstico adicionais : Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Falha ao baixar do conteúdo 6ea52149-91cd-4965-b5bb-82ca6a3ec9be do tipo Document.</span><span class="sxs-lookup"><span data-stu-id="e943c-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="e943c-137">Id de correlação: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="e943c-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="e943c-138">ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***Arquivo não encontrado***.</span><span class="sxs-lookup"><span data-stu-id="e943c-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="e943c-139">na Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) na Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- fim da pilha de exceção interna ---</span><span class="sxs-lookup"><span data-stu-id="e943c-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="e943c-140">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-140">Resolution</span></span>

1. <span data-ttu-id="e943c-141">Verifique o local identificado na pesquisa para garantir que o local do arquivo está correto e adicionado nos locais de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e943c-141">Check location identified in the search to ensure that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="e943c-142">Use os procedimentos em Solicitação manual de rastreamento e re indexação de [um site,](/sharepoint/crawl-site-content) uma biblioteca ou uma lista para reindexar o site.</span><span class="sxs-lookup"><span data-stu-id="e943c-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a><span data-ttu-id="e943c-143">Erro/problema: esse arquivo não foi exportado porque ele não existe mais.</span><span class="sxs-lookup"><span data-stu-id="e943c-143">Error/issue: This file wasn't exported because it doesn't exist anymore.</span></span> <span data-ttu-id="e943c-144">O arquivo foi incluído na contagem de resultados de pesquisa estimados porque ele ainda está listado no índice.</span><span class="sxs-lookup"><span data-stu-id="e943c-144">The file was included in the count of estimated search results because it's still listed in the index.</span></span> <span data-ttu-id="e943c-145">O arquivo eventualmente será removido do índice e não causará um erro no futuro.</span><span class="sxs-lookup"><span data-stu-id="e943c-145">The file will eventually be removed from the index, and won't cause an error in the future.</span></span>

<span data-ttu-id="e943c-146">Você pode ver esse erro ao executar uma pesquisa de Descoberta Virtual que inclui locais SharePoint Online e One Drive For Business.</span><span class="sxs-lookup"><span data-stu-id="e943c-146">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="e943c-147">A Descoberta eDiscovery depende do índice SPO para identificar os locais do arquivo.</span><span class="sxs-lookup"><span data-stu-id="e943c-147">eDiscovery relies on teh SPO index to identify the file locations.</span></span> <span data-ttu-id="e943c-148">Se o arquivo foi excluído, mas o índice SPO ainda não foi atualizado, esse erro pode ocorrer.</span><span class="sxs-lookup"><span data-stu-id="e943c-148">If the file was deleted but the SPO index was not yet updated this error may occur.</span></span>

### <a name="resolution"></a><span data-ttu-id="e943c-149">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-149">Resolution</span></span> 
<span data-ttu-id="e943c-150">Abra o local do SPO e verifique se esse arquivo realmente não está lá.</span><span class="sxs-lookup"><span data-stu-id="e943c-150">Open the SPO location and verify that this file indeed is not there.</span></span>
<span data-ttu-id="e943c-151">A solução sugerida é reindexar manualmente o site ou aguardar até que o site seja reindexado pelo processo de plano de fundo automático.</span><span class="sxs-lookup"><span data-stu-id="e943c-151">Suggested solution is to manually reindex the site, or wait till the site reindexes by the automatic background process.</span></span>


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artefact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a><span data-ttu-id="e943c-152">Erro/problema: esse resultado de pesquisa não foi baixado, pois é uma pasta ou outro artefato que não pode ser baixado por si só, qualquer item dentro da pasta ou biblioteca será baixado.</span><span class="sxs-lookup"><span data-stu-id="e943c-152">Error/issue: This search result was not downloaded as it is a folder or other artefact that can't be downloaded by itself, any items inside the folder or library will be downloaded.</span></span>

<span data-ttu-id="e943c-153">Você pode ver esse erro ao executar uma pesquisa de Descoberta Virtual que inclui locais SharePoint Online e One Drive For Business.</span><span class="sxs-lookup"><span data-stu-id="e943c-153">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="e943c-154">Isso significa que vamos tentar exportar o item relatado no índice, mas ele acabou sendo uma pasta para que não o exportá-lo.</span><span class="sxs-lookup"><span data-stu-id="e943c-154">It means that we were going to try and export the item reported in the index, but it turned out to be a folder so we did not export it.</span></span> <span data-ttu-id="e943c-155">Como mencionado no erro, não exportamos itens de pasta, mas exportamos seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e943c-155">As mentioned in the error, we don't export folder items but we do export their contents.</span></span>


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="e943c-156">Erro/problema: a pesquisa falha porque o destinatário não foi encontrado</span><span class="sxs-lookup"><span data-stu-id="e943c-156">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="e943c-157">Uma pesquisa de Descoberta E falha com o erro `recipient not found` de .</span><span class="sxs-lookup"><span data-stu-id="e943c-157">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="e943c-158">Esse erro pode ocorrer se o objeto do usuário não puder ser encontrado no Proteção do Exchange Online (EOP) porque o objeto não foi sincronizado.</span><span class="sxs-lookup"><span data-stu-id="e943c-158">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="e943c-159">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-159">Resolution</span></span>

1. <span data-ttu-id="e943c-160">Conexão para [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e943c-160">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e943c-161">Execute o seguinte comando para verificar se o usuário está sincronizado com Proteção do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="e943c-161">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="e943c-162">Deve haver um objeto de usuário de email para a pergunta do usuário.</span><span class="sxs-lookup"><span data-stu-id="e943c-162">There should be a mail user object for the user question.</span></span> <span data-ttu-id="e943c-163">Se nada for retornado, investigue o objeto user.</span><span class="sxs-lookup"><span data-stu-id="e943c-163">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="e943c-164">Entre em contato com o Suporte da Microsoft se o objeto não puder ser sincronizado.</span><span class="sxs-lookup"><span data-stu-id="e943c-164">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="e943c-165">Erro/problema: a exportação de resultados da pesquisa é lenta</span><span class="sxs-lookup"><span data-stu-id="e943c-165">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="e943c-166">Ao exportar resultados da pesquisa da Descoberta Digital ou da Pesquisa de Conteúdo no Centro de Segurança e Conformidade, o download leva mais tempo do que o esperado.</span><span class="sxs-lookup"><span data-stu-id="e943c-166">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="e943c-167">Você pode verificar a quantidade de dados a serem baixados e possivelmente aumentar a velocidade de exportação.</span><span class="sxs-lookup"><span data-stu-id="e943c-167">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="e943c-168">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-168">Resolution</span></span>

1. <span data-ttu-id="e943c-169">Conexão para o Centro de Conformidade & Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e943c-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="e943c-170">Encontre a quantidade de dados a serem baixados nos parâmetros SearchResults e SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="e943c-170">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="e943c-171">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e943c-171">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="e943c-172">No campo resultados, encontre os dados que foram exportados e exibir quaisquer erros encontrados.</span><span class="sxs-lookup"><span data-stu-id="e943c-172">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="e943c-173">Verifique o arquivo trace.log localizado no diretório para o qual você exportou o conteúdo para quaisquer erros.</span><span class="sxs-lookup"><span data-stu-id="e943c-173">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="e943c-174">Se você ainda tiver problemas, considere dividir pesquisas que retornam um grande conjunto de resultados em pesquisas menores.</span><span class="sxs-lookup"><span data-stu-id="e943c-174">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="e943c-175">Por exemplo, você pode usar intervalos de datas em consultas de pesquisa para retornar um conjunto menor de resultados que podem ser baixados mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="e943c-175">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="e943c-176">Erro/problema: "Erro interno do servidor (500) ocorrido"</span><span class="sxs-lookup"><span data-stu-id="e943c-176">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="e943c-177">Ao executar uma pesquisa de Descoberta Eletrônico, se a pesquisa falhar continuamente com um erro semelhante a "Erro de servidor interno (500) ocorreu", talvez seja necessário executar a pesquisa apenas em locais de caixa de correio específicos.</span><span class="sxs-lookup"><span data-stu-id="e943c-177">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Captura de tela de erro de servidor interno 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="e943c-179">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-179">Resolution</span></span>

1. <span data-ttu-id="e943c-180">Quebre a pesquisa em pesquisas menores e execute a pesquisa novamente.</span><span class="sxs-lookup"><span data-stu-id="e943c-180">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="e943c-181">Tente usar um intervalo de datas menor ou limite o número de locais que estão sendo pesquisados.</span><span class="sxs-lookup"><span data-stu-id="e943c-181">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="e943c-182">Conexão para o Centro de Conformidade & Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e943c-182">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="e943c-183">Examine a saída em busca de resultados e erros.</span><span class="sxs-lookup"><span data-stu-id="e943c-183">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="e943c-184">Examine o arquivo trace.log.</span><span class="sxs-lookup"><span data-stu-id="e943c-184">Examine the trace.log file.</span></span> <span data-ttu-id="e943c-185">Ele está localizado na mesma pasta para a onde você exportou os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e943c-185">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="e943c-186">Entrar em contato com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e943c-186">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="e943c-187">Erro/problema: retém não sincronizar</span><span class="sxs-lookup"><span data-stu-id="e943c-187">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="e943c-188">Erro de Distribuição de Sincronização de Sincronização de Política de Descoberta EDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e943c-188">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="e943c-189">O erro diz:</span><span class="sxs-lookup"><span data-stu-id="e943c-189">The error reads:</span></span>

> <span data-ttu-id="e943c-190">"Recursos: está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="e943c-190">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="e943c-191">Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas."</span><span class="sxs-lookup"><span data-stu-id="e943c-191">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="e943c-192">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-192">Resolution</span></span>

1. <span data-ttu-id="e943c-193">Conexão & para o Centro de Conformidade e Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando para uma ressarção de caso de Descoberta eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="e943c-193">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="e943c-194">Para uma política de retenção, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e943c-194">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="e943c-195">Examine o valor no parâmetro DistributionDetail para ver se há erros como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e943c-195">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="e943c-196">Erro: Recursos: está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="e943c-196">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="e943c-197">Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas."</span><span class="sxs-lookup"><span data-stu-id="e943c-197">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="e943c-198">Tente executar o parâmetro RetryDistribution na política em questão:</span><span class="sxs-lookup"><span data-stu-id="e943c-198">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="e943c-199">Para os casos de Descoberta eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="e943c-199">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="e943c-200">Para políticas de retenção:</span><span class="sxs-lookup"><span data-stu-id="e943c-200">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="e943c-201">Entrar em contato com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e943c-201">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="e943c-202">Erro: "A condição especificada usando cabeçalhos condicionais HTTP não é atendida"</span><span class="sxs-lookup"><span data-stu-id="e943c-202">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="e943c-203">Ao baixar os resultados da pesquisa usando a Ferramenta de Exportação de Descoberta Armazenamento, é possível que você receba o seguinte erro: Este é um erro transitório, que normalmente ocorre no local de Armazenamento `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` do Azure.</span><span class="sxs-lookup"><span data-stu-id="e943c-203">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="e943c-204">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-204">Resolution</span></span>

<span data-ttu-id="e943c-205">Para resolver esse problema, baixe novamente [os](export-search-results.md#step-2-download-the-search-results)resultados da pesquisa , que reiniciarão a Ferramenta de Exportação de Descoberta e.</span><span class="sxs-lookup"><span data-stu-id="e943c-205">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="e943c-206">Erro/problema: a exportação baixada não mostra resultados</span><span class="sxs-lookup"><span data-stu-id="e943c-206">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="e943c-207">Após uma exportação bem-sucedida, o download concluído por meio da ferramenta de exportação mostra zero arquivos nos resultados.</span><span class="sxs-lookup"><span data-stu-id="e943c-207">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="e943c-208">Resolução</span><span class="sxs-lookup"><span data-stu-id="e943c-208">Resolution</span></span>

<span data-ttu-id="e943c-209">Este é um problema do lado do cliente e, para remediar, tente as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e943c-209">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="e943c-210">Tente usar outro cliente/máquina para baixar.</span><span class="sxs-lookup"><span data-stu-id="e943c-210">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="e943c-211">Remova pesquisas antigas que não são mais necessárias usando o cmdlet [Remove-ComplianceSearch.](/powershell/module/exchange/remove-compliancesearch)</span><span class="sxs-lookup"><span data-stu-id="e943c-211">Remove old searches that are no longer needed using [Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) cmdlet.</span></span>

3. <span data-ttu-id="e943c-212">Certifique-se de baixar para uma unidade local.</span><span class="sxs-lookup"><span data-stu-id="e943c-212">Make sure to download to a local drive.</span></span>

4. <span data-ttu-id="e943c-213">Certifique-se de que o scanner de vírus não está em execução.</span><span class="sxs-lookup"><span data-stu-id="e943c-213">Make sure the virus scanner is not running.</span></span>

5. <span data-ttu-id="e943c-214">Certifique-se de que nenhuma outra exportação está baixando para a mesma pasta ou qualquer pasta pai.</span><span class="sxs-lookup"><span data-stu-id="e943c-214">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

6. <span data-ttu-id="e943c-215">Se as etapas anteriores não funcionarem, desabilite o zipping e a de duplicação.</span><span class="sxs-lookup"><span data-stu-id="e943c-215">If the previous steps did not work, disable zipping and de-duplication.</span></span>

7. <span data-ttu-id="e943c-216">Se isso funcionar, o problema será devido a um scanner de vírus local ou a um problema de disco.</span><span class="sxs-lookup"><span data-stu-id="e943c-216">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
