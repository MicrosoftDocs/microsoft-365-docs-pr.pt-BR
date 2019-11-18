---
title: Usar a pesquisa de conteúdo no seu fluxo de trabalho de descoberta eletrônica
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'Use um script do PowerShell para criar uma pesquisa de descoberta eletrônica in-loco no Exchange Online com base em uma pesquisa criada no centro de conformidade do & de segurança. '
ms.openlocfilehash: a16bf747da2d2eb8219ac4c13f4ff8c34d37b2c3
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38684997"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="68a91-103">Usar a Pesquisa de Conteúdo no seu fluxo de trabalho de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="68a91-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="68a91-104">O recurso de pesquisa de conteúdo no centro de conformidade & segurança permite pesquisar todas as caixas de correio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="68a91-104">The Content Search feature in the Security & Compliance Center allows you to search all mailboxes in your organization.</span></span> <span data-ttu-id="68a91-105">Ao contrário da descoberta eletrônica in-loco no Exchange Online (onde você pode pesquisar até 10.000 caixas de correio), não há limites para o número de caixas de correio de destino em uma única pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-105">Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search.</span></span> <span data-ttu-id="68a91-106">Para cenários que exigem a execução de pesquisas em toda a organização, você pode usar a Pesquisa de Conteúdo para pesquisar todas as caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="68a91-106">For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes.</span></span> <span data-ttu-id="68a91-107">Em seguida, você pode usar os recursos de fluxo de trabalho de descoberta eletrônica in-loco para realizar outras tarefas relacionadas à descoberta eletrônica, como colocar caixas de correio em espera e exportar resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-107">Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results.</span></span> <span data-ttu-id="68a91-108">Por exemplo, vamos supor que você precise pesquisar todas as caixas de correio para identificar os responsáveis específicos por um caso jurídico.</span><span class="sxs-lookup"><span data-stu-id="68a91-108">For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case.</span></span> <span data-ttu-id="68a91-109">Você pode usar a pesquisa de conteúdo no centro de conformidade de & de segurança para pesquisar todas as caixas de correio em sua organização para identificar as que estão respondendo ao caso.</span><span class="sxs-lookup"><span data-stu-id="68a91-109">You can use Content Search in the Security & Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case.</span></span> <span data-ttu-id="68a91-110">Em seguida, você pode usar essa lista de caixas de correio de responsáveis como caixas de correio de origem para uma pesquisa de descoberta eletrônica in-loco no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68a91-110">Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online.</span></span> <span data-ttu-id="68a91-111">O uso da descoberta eletrônica in-loco também permite que você coloque uma retenção nas caixas de correio de origem, copie os resultados da pesquisa para uma caixa de correio de descoberta e exporte os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-111">Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="68a91-112">Este tópico inclui um script que você pode executar para criar uma pesquisa de descoberta eletrônica in-loco no Exchange Online usando a lista de caixas de correio de origem e consulta de pesquisa de uma pesquisa criada no centro de conformidade de segurança &.</span><span class="sxs-lookup"><span data-stu-id="68a91-112">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security & Compliance Center.</span></span> <span data-ttu-id="68a91-113">Esta é uma visão geral do processo:</span><span class="sxs-lookup"><span data-stu-id="68a91-113">Here's an overview of the process:</span></span>
  
[<span data-ttu-id="68a91-114">Etapa 1: Criar uma Pesquisa de Conteúdo para pesquisar todas as caixas de correio em sua organização</span><span class="sxs-lookup"><span data-stu-id="68a91-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="68a91-115">Etapa 2: conectar-se ao \& centro de conformidade de segurança e ao Exchange Online em uma única sessão remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="68a91-115">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="68a91-116">Etapa 3: Execute o script para criar uma pesquisa de Descoberta Eletrônica In-loco na Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="68a91-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="68a91-117">Step 4: Start the In-Place eDiscovery search</span><span class="sxs-lookup"><span data-stu-id="68a91-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="68a91-118">Etapa 1: Criar uma Pesquisa de Conteúdo para pesquisar todas as caixas de correio em sua organização</span><span class="sxs-lookup"><span data-stu-id="68a91-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="68a91-119">A primeira etapa é usar o centro de conformidade de & de segurança (ou o PowerShell de segurança & do centro de conformidade) para criar uma pesquisa de conteúdo que pesquise todas as caixas de correio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="68a91-119">The first step is to use the Security & Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization.</span></span> <span data-ttu-id="68a91-120">Não há qualquer limite para o número de caixas de correio em uma única pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="68a91-120">There's no limit for the number of mailboxes for a single Content Search.</span></span> <span data-ttu-id="68a91-121">Especifica uma consulta de palavra-chave apropriada (ou uma consulta de tipos de informações confidenciais) para que a pesquisa retorne apenas as caixas de correio de origem relevantes para a investigação.</span><span class="sxs-lookup"><span data-stu-id="68a91-121">Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation.</span></span> <span data-ttu-id="68a91-122">Se for necessário, refine a consulta de pesquisa para restringir o escopo dos resultados da pesquisa e as caixas de correio de origem retornadas.</span><span class="sxs-lookup"><span data-stu-id="68a91-122">If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68a91-p104">Se a pesquisa de conteúdo de origem não retornar qualquer resultado, a Descoberta Eletrônica In-loco não será criada quando você executar o script na Etapa 3. Talvez seja necessário revisar a consulta de pesquisa e executar novamente a pesquisa de conteúdo para retornar os resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-p104">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3. You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="68a91-125">Usar o Centro de Conformidade e Segurança para pesquisar todas as caixas de correio</span><span class="sxs-lookup"><span data-stu-id="68a91-125">Use the Security & Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="68a91-126">[Vá para o centro de conformidade & segurança](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="68a91-126">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="68a91-127">Clique em**pesquisa de conteúdo**de **pesquisa** > e clique em novo ícone](media/O365-MDM-CreatePolicy-AddIcon.gif)de adição de **pesquisa** ![.</span><span class="sxs-lookup"><span data-stu-id="68a91-127">Click **Search** > **Content search**, and then click **New search** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="68a91-128">Na página **Nova pesquisa**, digite um nome para a pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="68a91-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="68a91-129">Em **Onde você deseja que procuremos?**, clique em **Pesquisar todas as caixas de correio** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="68a91-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="68a91-130">Na caixa sob o **que você deseja que procuremos?**, digite uma consulta de pesquisa na caixa.</span><span class="sxs-lookup"><span data-stu-id="68a91-130">In the box under **What do you want us to look for?**, type a search query in the box.</span></span> <span data-ttu-id="68a91-131">Você pode especificar palavras-chave, propriedades de mensagem como datas enviadas e recebidas, ou ainda, propriedades do documento como nomes de arquivos ou a data em que um documento foi alterado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="68a91-131">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="68a91-132">Você pode usar consultas mais complexas que usam um operador Boolean, como e, ou, não ou NEAR, ou também pode pesquisar informações confidenciais (como números de seguridade social) em mensagens.</span><span class="sxs-lookup"><span data-stu-id="68a91-132">You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages.</span></span> <span data-ttu-id="68a91-133">Para obter mais informações sobre a criação de consultas de pesquisa, consulte [keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="68a91-133">For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="68a91-134">Clique em **Pesquisar** para salvar as configurações da pesquisa e iniciá-la.</span><span class="sxs-lookup"><span data-stu-id="68a91-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="68a91-135">Após um tempo, uma estimativa dos resultados da pesquisa são exibidos no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="68a91-135">After a while, an estimate of the search results displayed in the details pane.</span></span> <span data-ttu-id="68a91-136">A estimativa inclui o tamanho total e o número de itens dos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-136">The estimate includes the total size and number of items for the search results.</span></span> <span data-ttu-id="68a91-137">Após a conclusão da pesquisa, você poderá visualizar os resultados.</span><span class="sxs-lookup"><span data-stu-id="68a91-137">After the search is completed, you can preview the search results.</span></span> <span data-ttu-id="68a91-138">Se necessário, clique em **Atualizar**![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar as informações no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="68a91-138">If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="68a91-139">Se for necessário, refine a consulta de pesquisa para restringir o escopo dos resultados da pesquisa e reinicie a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="68a91-140">Usar o centro de conformidade & o PowerShell para pesquisar todas as caixas de correio</span><span class="sxs-lookup"><span data-stu-id="68a91-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="68a91-141">Você também pode usar o cmdlet **New-ComplianceSearch** para pesquisar em todas as caixas de correio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="68a91-141">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization.</span></span> <span data-ttu-id="68a91-142">A primeira etapa é [conectar-se ao PowerShell do centro de conformidade & segurança](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span><span class="sxs-lookup"><span data-stu-id="68a91-142">The first step is to [Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="68a91-143">Veja um exemplo de como usar o PowerShell para pesquisar todas as caixas de correio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="68a91-143">Here's an example of using PowerShell to search all mailboxes in your organization.</span></span> <span data-ttu-id="68a91-144">A consulta de pesquisa retorna todas as mensagens enviadas entre 1º de janeiro de 2015 e 30 de junho de 2015 e que contenham a frase "relatório financeiro" na linha de assunto.</span><span class="sxs-lookup"><span data-stu-id="68a91-144">The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line.</span></span> <span data-ttu-id="68a91-145">O primeiro comando cria a pesquisa e o segundo comando executa a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-145">The first command creates the search, and the second command runs the search.</span></span> 
  
```powershell
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```powershell
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="68a91-146">Para obter mais informações, consulte [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span><span class="sxs-lookup"><span data-stu-id="68a91-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="68a91-147">Verifique o número de caixas de correio de origem na pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="68a91-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="68a91-148">Uma pesquisa de conteúdo retorna um máximo de 1.000 caixas de correio de origem que contêm resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-148">A Content Search returns a maximum of 1,000 source mailboxes that contain search results.</span></span> <span data-ttu-id="68a91-149">Se houver mais de 1.000 caixas de correio que contenham conteúdo que corresponda à consulta de pesquisa, somente as primeiras caixas de correio de 1.000 com a maioria dos resultados de pesquisa serão incluídas na pesquisa de conteúdo que você criou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="68a91-149">If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step.</span></span> <span data-ttu-id="68a91-150">Portanto, se mais de 1.000 caixas de correio contiverem resultados de pesquisa, algumas dessas caixas de correio não serão incluídas na lista de caixas de correio de origem copiadas para a nova pesquisa de descoberta eletrônica in-loco criada na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="68a91-150">So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="68a91-151">Para ajudá-lo a criar uma pesquisa de conteúdo com mais de 1.000 caixas de correio de origem, siga estas etapas para executar um script que exibe o número de caixas de correio de origem (que contêm resultados de pesquisa) retornado pela pesquisa de conteúdo que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="68a91-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="68a91-152">Salve o seguinte texto em um arquivo de script do PowerShell usando um sufixo de nome de arquivo. ps1.</span><span class="sxs-lookup"><span data-stu-id="68a91-152">Save the following text to a PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="68a91-153">Por exemplo, você pode salvá-lo em um arquivo `SourceMailboxes.ps1`chamado.</span><span class="sxs-lookup"><span data-stu-id="68a91-153">For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
  ```powershell
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. <span data-ttu-id="68a91-154">Em segurança & centro de conformidade do PowerShell, vá para a pasta onde o script criado na etapa anterior está localizado e, em seguida, execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68a91-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```powershell
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="68a91-155">Quando receber a solicitação pelo script, digite o nome da pesquisa de conteúdo criada na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="68a91-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="68a91-156">O script exibe o número de caixas de correio de origem que contêm os resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="68a91-157">Se houver mais de 1.000 caixas de correio de origem, tente criar duas (ou mais) pesquisas de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="68a91-157">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches.</span></span> <span data-ttu-id="68a91-158">Por exemplo, pesquise metade das caixas de correio da organização em uma pesquisa de conteúdo, e a outra metade em outra pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="68a91-158">For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search.</span></span> <span data-ttu-id="68a91-159">Você também pode alterar os critérios de pesquisa para reduzir o número de caixas de correio que contêm os resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-159">You could also change the search criteria to reduce the number of mailboxes that contain search results.</span></span> <span data-ttu-id="68a91-160">Por exemplo, você pode incluir um intervalo de datas ou refinar a consulta de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="68a91-160">For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="68a91-161">Etapa 2: conectar-se ao \& centro de conformidade de segurança e ao Exchange Online em uma única sessão remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="68a91-161">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="68a91-162">A próxima etapa é conectar o Windows PowerShell ao centro de conformidade de & de segurança e à sua organização do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68a91-162">The next step is to connect Windows PowerShell to both the Security & Compliance Center and to your Exchange Online organization.</span></span> <span data-ttu-id="68a91-163">Isso é necessário porque o script executado na etapa 3 requer acesso aos cmdlets de pesquisa de conteúdo no centro de conformidade e segurança & e nos cmdlets de descoberta eletrônica in-loco no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68a91-163">This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security & Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="68a91-164">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1.</span><span class="sxs-lookup"><span data-stu-id="68a91-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="68a91-165">Por exemplo, você pode salvá-lo em um arquivo `ConnectEXO-CC.ps1`chamado.</span><span class="sxs-lookup"><span data-stu-id="68a91-165">For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="68a91-166">No computador local, abra o Windows PowerShell, vá para a pasta onde o script criado na etapa anterior está localizado e, em seguida, execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68a91-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```powershell
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="68a91-167">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="68a91-167">How do you know if this worked?</span></span> <span data-ttu-id="68a91-168">Depois de executar o script, os cmdlets do centro de conformidade & segurança e do Exchange Online são importados para sua sessão local do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68a91-168">After you run the script, cmdlets from the Security & Compliance Center and Exchange Online are imported into your local PowerShell session.</span></span> <span data-ttu-id="68a91-169">Se nenhum erro aparecer, a conexão terá sido estabelecida.</span><span class="sxs-lookup"><span data-stu-id="68a91-169">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="68a91-170">Um teste rápido é executar um cmdlet de segurança & o centro de conformidade — por exemplo, **install-UnifiedCompliancePrerequisite** — e um cmdlet do Exchange Online, como o **Get-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="68a91-170">A quick test is to run a Security & Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="68a91-171">Etapa 3: Execute o script para criar uma pesquisa de Descoberta Eletrônica In-loco na Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="68a91-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="68a91-172">Depois de criar a sessão de dois PowerShell na etapa 2, a próxima etapa é executar um script que converta uma pesquisa de conteúdo existente em uma pesquisa de descoberta eletrônica in-loco.</span><span class="sxs-lookup"><span data-stu-id="68a91-172">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search.</span></span> <span data-ttu-id="68a91-173">Veja a seguir o que o script faz:</span><span class="sxs-lookup"><span data-stu-id="68a91-173">Here's what the script does:</span></span>
  
- <span data-ttu-id="68a91-174">Solicita o nome da pesquisa de conteúdo para a conversão.</span><span class="sxs-lookup"><span data-stu-id="68a91-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="68a91-p116">Verifica se a pesquisa de conteúdo foi concluída. Se a pesquisa de conteúdo não retornar resultados, e a Descoberta Eletrônica In-loco não for criada.</span><span class="sxs-lookup"><span data-stu-id="68a91-p116">Verifies that the Content Search has completed running. If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="68a91-177">Salva uma lista das caixas de correio de origem da pesquisa de conteúdo que contêm os resultados de pesquisa para uma variável.</span><span class="sxs-lookup"><span data-stu-id="68a91-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="68a91-p117">Cria uma nova pesquisa de Descoberta Eletrônica In-loco, com as seguintes propriedades. Observe que a nova pesquisa não foi iniciada. Você poderá iniciá-la na Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="68a91-p117">Creates a new In-Place eDiscovery search, with the following properties. Note that the new search isn't started. You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="68a91-181">**Name** -o nome da nova pesquisa usa este formato: \<nome da pesquisa\>de conteúdo _MBSearch1.</span><span class="sxs-lookup"><span data-stu-id="68a91-181">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1.</span></span> <span data-ttu-id="68a91-182">Se você executar o script novamente e usar a mesma pesquisa de conteúdo de origem, a pesquisa será \<nomeada como nome de\>pesquisa de conteúdo _MBSearch2.</span><span class="sxs-lookup"><span data-stu-id="68a91-182">If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="68a91-183">**Caixas de correio de origem** -todas as caixas de correio da pesquisa de conteúdo que contêm resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="68a91-184">**Consulta de pesquisa** – a nova pesquisa usa a consulta de pesquisa da pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="68a91-184">**Search query** - The new search uses the search query from the Content Search.</span></span> <span data-ttu-id="68a91-185">Se a pesquisa de conteúdo incluir todo o conteúdo (quando a consulta de pesquisa estiver em branco), a nova pesquisa também terá uma consulta de pesquisa em branco e incluirá todo o conteúdo encontrado nas caixas de correio de origem.</span><span class="sxs-lookup"><span data-stu-id="68a91-185">If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="68a91-186">**Estimar somente pesquisa** – a nova pesquisa está marcada como uma pesquisa somente estimada.</span><span class="sxs-lookup"><span data-stu-id="68a91-186">**Estimate only search** - The new search is marked as an estimate-only search.</span></span> <span data-ttu-id="68a91-187">Ela não copiará resultados da pesquisa para uma caixa de correio de descoberta depois de iniciá-la.</span><span class="sxs-lookup"><span data-stu-id="68a91-187">It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="68a91-188">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo ps1.</span><span class="sxs-lookup"><span data-stu-id="68a91-188">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1.</span></span> <span data-ttu-id="68a91-189">Por exemplo, você pode salvá-lo em um arquivo `CreateMBSearchFromComplianceSearch.ps1`chamado.</span><span class="sxs-lookup"><span data-stu-id="68a91-189">For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
  ```powershell
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  ```

2. <span data-ttu-id="68a91-190">Na sessão do Windows PowerShell que você criou na etapa 2, vá para a pasta onde o script criado na etapa anterior está localizado e, em seguida, execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68a91-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```powershell
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="68a91-191">Quando solicitado pelo script, digite o nome da pesquisa de conteúdo que você deseja converter em uma pesquisa de descoberta eletrônica in-loco (por exemplo, a pesquisa que você criou na etapa 1) e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="68a91-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="68a91-192">Se o script for bem-sucedido, uma nova pesquisa de Descoberta Eletrônica In-loco será criada com um status de **NotStarted**.</span><span class="sxs-lookup"><span data-stu-id="68a91-192">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**.</span></span> <span data-ttu-id="68a91-193">Execute o comando `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` para exibir as propriedades da nova pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-193">Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="68a91-194">Etapa 4: Iniciar a pesquisa de Descoberta Eletrônica In-loco</span><span class="sxs-lookup"><span data-stu-id="68a91-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="68a91-p123">O script executado na Etapa 3 cria uma nova pesquisa de Descoberta Eletrônica In-loco, mas não a inicia. A próxima etapa é iniciar a pesquisa para que você possa obter uma estimativa dos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="68a91-197">No centro de administração do Exchange (Eat), vá para **Gerenciamento** \> **de conformidade e descoberta &amp; eletrônica in-loco**.</span><span class="sxs-lookup"><span data-stu-id="68a91-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="68a91-198">No modo de exibição de lista, selecione a pesquisa de Descoberta Eletrônica In-loco que você criou na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="68a91-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="68a91-199">![](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> Clique **em Pesquisar ícone** de pesquisa **estimar os resultados da pesquisa** para iniciar a pesquisa e retornar uma estimativa do tamanho total e do número de itens retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="68a91-200">As estimativas são exibidas no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="68a91-200">The estimates are displayed in the details pane.</span></span> <span data-ttu-id="68a91-201">Clique em **Atualizar** ![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar as informações exibidas no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="68a91-201">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="68a91-202">Para visualizar os resultados após a conclusão da pesquisa, clique em **Visualizar resultados da pesquisa** no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="68a91-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="68a91-203">Próximas etapas após a criação e execução da pesquisa de Descoberta Eletrônica In-loco</span><span class="sxs-lookup"><span data-stu-id="68a91-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="68a91-204">Depois de criar e iniciar a pesquisa de Descoberta Eletrônica In-loco criada pelo script na Etapa 3, você pode usar o fluxo de trabalho normal de Descoberta Eletrônica In-loco para executar ações de Descoberta Eletrônica diferentes nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="68a91-205">Criar um Bloqueio In-loco</span><span class="sxs-lookup"><span data-stu-id="68a91-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="68a91-206">No Eat, vá para **Gerenciamento** \> **de conformidade e descoberta eletrônica &amp; in-loco**.</span><span class="sxs-lookup"><span data-stu-id="68a91-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="68a91-207">No modo de exibição de lista, selecione a pesquisa de descoberta eletrônica in-loco que você criou na etapa 3 \*\*\*\* ![e clique em](media/O365-MDM-CreatePolicy-EditIcon.gif)editar ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="68a91-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="68a91-208">Na página **Bloqueio In-loco**, marque a caixa de seleção **Colocar conteúdo correspondente à consulta de pesquisa nas caixas de correio selecionadas em bloqueio** e selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="68a91-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="68a91-209">**Reter indefinidamente** -escolha essa opção para colocar os itens retornados pela pesquisa em um bloqueio indefinido.</span><span class="sxs-lookup"><span data-stu-id="68a91-209">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold.</span></span> <span data-ttu-id="68a91-210">Itens retidos serão preservados até que você remova a caixa de correio da pesquisa ou remova a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-210">Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="68a91-211">**Especificar o número de dias para reter itens em relação à sua data de recebimento** -escolha esta opção para reter itens por um período específico.</span><span class="sxs-lookup"><span data-stu-id="68a91-211">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period.</span></span> <span data-ttu-id="68a91-212">A duração é calculada a partir da data em que um item de caixa de correio é recebido ou criado.</span><span class="sxs-lookup"><span data-stu-id="68a91-212">The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="68a91-213">Clique em **Salvar** para criar o Bloqueio In-loco e reiniciar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="68a91-214">Return to top</span><span class="sxs-lookup"><span data-stu-id="68a91-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="68a91-215">Copiar os resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="68a91-215">Copy the search results</span></span>

1. <span data-ttu-id="68a91-216">No Eat, vá para **Gerenciamento** \> **de conformidade e descoberta eletrônica &amp; in-loco**.</span><span class="sxs-lookup"><span data-stu-id="68a91-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="68a91-217">No modo de exibição de lista, selecione a pesquisa de Descoberta Eletrônica In-loco que você criou na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="68a91-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="68a91-218">![](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)Clique **em ícone pesquisa de** pesquisa e, em seguida, clique em **copiar resultados da pesquisa** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="68a91-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="68a91-219">Em **Copiar Resultados da Pesquisa**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="68a91-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="68a91-220">**Incluir itens não pesquisáveis** -Marque essa caixa de seleção para incluir itens de caixa de correio que não puderam ser pesquisados (por exemplo, mensagens com anexos de tipos de arquivo que não puderam ser indexados pela pesquisa do Exchange).</span><span class="sxs-lookup"><span data-stu-id="68a91-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="68a91-221">**Habilitar eliminação de duplicação** : Marque essa caixa de seleção para excluir mensagens duplicadas.</span><span class="sxs-lookup"><span data-stu-id="68a91-221">**Enable de-duplication** - Select this check box to exclude duplicate messages.</span></span> <span data-ttu-id="68a91-222">Somente uma única instância de uma mensagem será copiada para a caixa de correio de descoberta.</span><span class="sxs-lookup"><span data-stu-id="68a91-222">Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="68a91-223">**Habilitar registro em log completo** -Marque essa caixa de seleção para incluir um log completo dos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="68a91-224">**Enviar-me email quando a cópia estiver concluída** -Marque essa caixa de seleção para obter uma notificação por email quando a pesquisa estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="68a91-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="68a91-225">**Copie os resultados para esta caixa de correio de descoberta** , clique em **procurar** para selecionar a caixa de correio de descoberta onde você deseja copiar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="68a91-226">Clique em **Copiar** para iniciar o processo de cópia dos resultados da pesquisa para a caixa de correio de descoberta especificada.</span><span class="sxs-lookup"><span data-stu-id="68a91-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="68a91-227">Clique em **Atualizar** ![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar as informações sobre o status de cópia exibido no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="68a91-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="68a91-228">Após a conclusão da cópia, clique em **Abrir** para abrir a caixa de correio de descoberta e exibir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68a91-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="68a91-229">Exportar os resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="68a91-229">Export the search results</span></span>

1. <span data-ttu-id="68a91-230">No Eat, vá para **Gerenciamento** \> **de conformidade e descoberta eletrônica &amp; in-loco**.</span><span class="sxs-lookup"><span data-stu-id="68a91-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="68a91-231">No modo de exibição de lista, selecione a pesquisa de Descoberta Eletrônica In-loco criada na Etapa 3 e clique em **Exportar para um arquivo PST**.</span><span class="sxs-lookup"><span data-stu-id="68a91-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="68a91-232">Na janela **Ferramenta de Exportação de PST de Descoberta Eletrônica**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="68a91-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="68a91-233">Clique em **Procurar** para especificar o local para o qual você deseja baixar o arquivo PST.</span><span class="sxs-lookup"><span data-stu-id="68a91-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="68a91-p128">Clique na caixa de seleção **Habilitar deduplicação** para excluir as mensagens duplicadas. Somente uma única instância de uma mensagem será incluída no arquivo PST.</span><span class="sxs-lookup"><span data-stu-id="68a91-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="68a91-p129">Clique na caixa de seleção **Incluir itens não pesquisáveis** para incluir itens da caixa de correio que não puderam ser pesquisados (por exemplo, mensagens com anexos dos tipos de arquivo que não puderam ser indexadas pela Pesquisa do Exchange). Os itens não pesquisáveis são exportados para um arquivo PST separado.</span><span class="sxs-lookup"><span data-stu-id="68a91-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="68a91-238">Clique em **Iniciar** para exportar os resultados da pesquisa para um arquivo PST.</span><span class="sxs-lookup"><span data-stu-id="68a91-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="68a91-239">Uma janela é exibida contendo as informações do status sobre o processo de exportação.</span><span class="sxs-lookup"><span data-stu-id="68a91-239">A window is displayed that contains status information about the export process.</span></span>
