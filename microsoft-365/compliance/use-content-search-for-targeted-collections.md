---
title: Usar a Pesquisa de Conteúdo para determinadas coleções
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Use a pesquisa de conteúdo no centro de conformidade da Microsoft 365 para realizar coleções direcionadas, que garantem que os itens estejam localizados em uma caixa de correio ou pasta de site específica.
ms.openlocfilehash: 0908b8262942e7a1c4d80bc511d4b8cbcc6dc646
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376584"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="a6793-103">Usar a Pesquisa de Conteúdo para determinadas coleções</span><span class="sxs-lookup"><span data-stu-id="a6793-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="a6793-104">O recurso de pesquisa de conteúdo no centro de conformidade da Microsoft 365 não fornece uma forma direta na interface do usuário para pesquisar pastas específicas em caixas de correio do Exchange ou sites do SharePoint e do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="a6793-104">The Content Search feature in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="a6793-105">No entanto, é possível pesquisar pastas específicas (chamadas de *coleção direcionadas*) especificando a propriedade ID da pasta para a propriedade email ou caminho (DocumentLink) para sites na sintaxe de consulta de pesquisa real.</span><span class="sxs-lookup"><span data-stu-id="a6793-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="a6793-106">O uso da pesquisa de conteúdo para executar uma coleção direcionada é útil quando você tem certeza de que os itens que respondem a um caso ou itens privilegiados estão localizados em uma caixa de correio ou pasta de site específica.</span><span class="sxs-lookup"><span data-stu-id="a6793-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="a6793-107">Você pode usar o script neste artigo para obter a ID de pasta para pastas de caixa de correio ou o caminho (DocumentLink) para pastas em um site do SharePoint e do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="a6793-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="a6793-108">Em seguida, você pode usar a ID de pasta ou o caminho em uma consulta de pesquisa para retornar itens localizados na pasta.</span><span class="sxs-lookup"><span data-stu-id="a6793-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="a6793-109">Para retornar conteúdo localizado em uma pasta em um site do SharePoint ou do OneDrive for Business, o script neste tópico usa a propriedade gerenciada DocumentLink em vez da propriedade Path.</span><span class="sxs-lookup"><span data-stu-id="a6793-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="a6793-110">A propriedade DocumentLink é mais robusta que a propriedade Path porque ela retornará todo o conteúdo de uma pasta, enquanto a propriedade Path não retornará alguns arquivos de mídia.</span><span class="sxs-lookup"><span data-stu-id="a6793-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="a6793-111">Antes de executar uma coleção direcionada</span><span class="sxs-lookup"><span data-stu-id="a6793-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="a6793-112">Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade do & de segurança para executar o script na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a6793-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="a6793-113">Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a6793-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

    <span data-ttu-id="a6793-114">Além disso, você precisa receber a função de destinatários de email em sua organização do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a6793-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="a6793-115">Isso é necessário para executar o cmdlet **Get-MailboxFolderStatistics** , que está incluído no script.</span><span class="sxs-lookup"><span data-stu-id="a6793-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="a6793-116">Por padrão, a função de destinatários de email é atribuída aos grupos de função de gerenciamento de organização e de gerenciamento de destinatários no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a6793-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="a6793-117">Para obter mais informações sobre como atribuir permissões no Exchange Online, consulte [Manage role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span><span class="sxs-lookup"><span data-stu-id="a6793-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="a6793-118">Você também pode criar um grupo de função personalizado, atribuir a ele a função de destinatários de email e, em seguida, adicionar os membros que precisam executar o script na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a6793-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="a6793-119">Para obter mais informações, consulte [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="a6793-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>

- <span data-ttu-id="a6793-120">O script deste artigo oferece suporte à autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="a6793-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="a6793-121">Você pode usar o script como está se for um Microsoft 365 ou uma organização do Microsoft 365 GCC.</span><span class="sxs-lookup"><span data-stu-id="a6793-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="a6793-122">Se você for uma organização da Alemanha do Office 365, uma organização alta do Microsoft 365 GCC ou uma organização do Microsoft 365 DoD, será necessário editar o script para executá-lo com êxito.</span><span class="sxs-lookup"><span data-stu-id="a6793-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="a6793-123">Especificamente, você precisa editar a linha `Connect-ExchangeOnline` e usar o parâmetro *ExchangeEnvironmentName* (e o valor apropriado para seu tipo de organização) para se conectar ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a6793-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="a6793-124">Além disso, você precisa editar a linha `Connect-IPPSSession` e usar os parâmetros *ConnectionURI* e *AzureADAuthorizationEndpointUri* (e os valores apropriados para seu tipo de organização) para se conectar ao PowerShell do centro de conformidade do & Security.</span><span class="sxs-lookup"><span data-stu-id="a6793-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="a6793-125">Para obter mais informações, consulte os exemplos em [conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) e [conectar-se ao PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span><span class="sxs-lookup"><span data-stu-id="a6793-125">For more information, see the examples in [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="a6793-126">Toda vez que você executa o script, uma nova sessão remota do PowerShell é criada.</span><span class="sxs-lookup"><span data-stu-id="a6793-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="a6793-127">Isso significa que você pode usar todas as sessões do PowerShell remotos disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="a6793-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="a6793-128">Para evitar que isso aconteça, execute o seguinte comando para desconectar suas sessões do PowerShell remotos ativas.</span><span class="sxs-lookup"><span data-stu-id="a6793-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="a6793-129">Para saber mais, confira [Conectar-se ao Exchange Online usando o PowerShell Remoto](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="a6793-129">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="a6793-130">O script inclui o tratamento de erros mínimo.</span><span class="sxs-lookup"><span data-stu-id="a6793-130">The script includes minimal error handling.</span></span> <span data-ttu-id="a6793-131">O objetivo principal do script é exibir rapidamente uma lista de IDs de pasta de caixa de correio ou caminhos de site que podem ser usados na sintaxe de consulta de pesquisa de uma pesquisa de conteúdo para executar uma coleção direcionada.</span><span class="sxs-lookup"><span data-stu-id="a6793-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="a6793-132">Não há suporte para o script de exemplo fornecido neste tópico em qualquer serviço ou programa de suporte padrão da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6793-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="a6793-133">O script de exemplo é fornecido como está sem garantia de qualquer tipo.</span><span class="sxs-lookup"><span data-stu-id="a6793-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="a6793-134">A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica.</span><span class="sxs-lookup"><span data-stu-id="a6793-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="a6793-135">Todo o risco resultante do uso ou do desempenho do script de exemplo e da documentação permanece com você.</span><span class="sxs-lookup"><span data-stu-id="a6793-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="a6793-136">De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="a6793-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="a6793-137">Etapa 1: executar o script para obter uma lista de pastas para uma caixa de correio ou site</span><span class="sxs-lookup"><span data-stu-id="a6793-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="a6793-138">O script executado nesta primeira etapa retornará uma lista de pastas de caixa de correio ou pastas do SharePoint e do OneDrive for Business e a ID de pasta ou o caminho correspondente de cada pasta.</span><span class="sxs-lookup"><span data-stu-id="a6793-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="a6793-139">Quando você executar esse script, ele solicitará as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="a6793-139">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="a6793-140">**Endereço de email ou URL do site**: digite um endereço de email do responsáveis para retornar uma lista de pastas e IDs de pastas da caixa de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6793-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="a6793-141">Ou digite a URL de um site do SharePoint ou do OneDrive for Business para retornar uma lista de caminhos para o site especificado.</span><span class="sxs-lookup"><span data-stu-id="a6793-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="a6793-142">Aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="a6793-142">Here are some examples:</span></span>

  - <span data-ttu-id="a6793-143">**Exchange**: stacig@contoso. onmicrosoft <spam> <spam> . com</span><span class="sxs-lookup"><span data-stu-id="a6793-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="a6793-144">**SharePoint**: https <span>://</span>contoso.SharePoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="a6793-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span> 

  - <span data-ttu-id="a6793-145">**Onedrive for Business**: https <span>://</span>contoso-My.SharePoint.com/Personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="a6793-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 

- <span data-ttu-id="a6793-146">**Suas credenciais de usuário**: o script usará suas credenciais para se conectar ao PowerShell do Exchange Online PowerShell ou segurança & o PowerShell usando a autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="a6793-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="a6793-147">Conforme explicado anteriormente, você precisa ter recebido as permissões apropriadas para executar esse script com êxito.</span><span class="sxs-lookup"><span data-stu-id="a6793-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="a6793-148">Para exibir uma lista de pastas de caixa de correio ou nomes de site documentlink (caminho):</span><span class="sxs-lookup"><span data-stu-id="a6793-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="a6793-149">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="a6793-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
   # The script will then:                                            #
   #    * If an email address is supplied: list the folders for the target mailbox.            #
   #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
   #    * for the site.                                                                                    #
   #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
   #      appended to the folder ID or documentlink to use in a Content Search.                #
   # Notes:                                                #
   #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
   #      the current folder and all sub-folders are searched.                        #
   #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
   #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
   #      each sub-folder that you want to search.                                #
   #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
   #########################################################################################################
   # Collect the target email address or SharePoint Url
   $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
   # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
   }
   elseif ($addressOrSite.IndexOf("http") -ige 0)
   {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
   }
   else
   {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
   }
   ```

2. <span data-ttu-id="a6793-150">No computador local, abra o Windows PowerShell e vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="a6793-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="a6793-151">Executar o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a6793-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="a6793-152">Insira as informações que o script solicitará para você.</span><span class="sxs-lookup"><span data-stu-id="a6793-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="a6793-153">O script exibe uma lista de pastas de caixa de correio ou pastas de site para o usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="a6793-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="a6793-154">Deixe essa janela aberta para que você possa copiar uma ID de pasta ou um nome de documentlink e colá-lo em uma consulta de pesquisa na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="a6793-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="a6793-155">Em vez de exibir uma lista de pastas na tela do computador, você pode redirecionar a saída do script para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a6793-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="a6793-156">Esse arquivo será salvo na pasta em que o script está localizado.</span><span class="sxs-lookup"><span data-stu-id="a6793-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="a6793-157">Por exemplo, para redirecionar a saída do script para um arquivo de texto, execute o seguinte comando na etapa 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` depois você pode copiar uma ID de pasta ou documentlink do arquivo para usar em uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6793-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="a6793-158">Saída de script para pastas de caixa de correio</span><span class="sxs-lookup"><span data-stu-id="a6793-158">Script output for mailbox folders</span></span>

<span data-ttu-id="a6793-159">Se você estiver obtendo IDs de pasta de caixa de correio, o script se conectará ao PowerShell do Exchange Online, executará o cmdlet **Get-MailboxFolderStatisics** e, em seguida, exibirá a lista de pastas da caixa de correio especificada.</span><span class="sxs-lookup"><span data-stu-id="a6793-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="a6793-160">Para cada pasta na caixa de correio, o script exibe o nome da pasta na coluna **FolderPath** e a ID da pasta na coluna **FolderQuery** .</span><span class="sxs-lookup"><span data-stu-id="a6793-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="a6793-161">Além disso, o script adiciona o prefixo de **FolderId** (que é o nome da propriedade da caixa de correio) à ID da pasta.</span><span class="sxs-lookup"><span data-stu-id="a6793-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="a6793-162">Como a propriedade **FolderId** é uma propriedade pesquisável, você usará  `folderid:<folderid>` uma consulta de pesquisa na etapa 2 para pesquisar essa pasta.</span><span class="sxs-lookup"><span data-stu-id="a6793-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="a6793-163">O script exibe um máximo de 100 pastas de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="a6793-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6793-164">O script neste artigo inclui lógica de codificação que converte os valores de ID de pasta de 64 caracteres retornados pelo **Get-MailboxFolderStatistics** para o mesmo formato de caractere 48 que é indexado para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6793-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="a6793-165">Se você apenas executar o cmdlet **Get-MailboxFolderStatistics** no PowerShell para obter uma ID de pasta (em vez de executar o script neste artigo), uma consulta de pesquisa que usa esse valor de ID de pasta falhará.</span><span class="sxs-lookup"><span data-stu-id="a6793-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="a6793-166">Você precisa executar o script para obter as IDs de pasta formatadas corretamente que podem ser usadas em uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a6793-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="a6793-167">Veja um exemplo de saída retornada pelo script para pastas de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="a6793-167">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Exemplo da lista de pastas de caixa de correio e IDs de pasta retornada pelo script](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="a6793-169">O exemplo na etapa 2 mostra a consulta usada para pesquisar a subpasta de limpezas na pasta itens recuperáveis do usuário.</span><span class="sxs-lookup"><span data-stu-id="a6793-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="a6793-170">Saída de script para pastas de site</span><span class="sxs-lookup"><span data-stu-id="a6793-170">Script output for site folders</span></span>

<span data-ttu-id="a6793-171">Se você estiver obtendo o caminho da propriedade **documentlink** do SharePoint ou do onedrive for Business sites, o script se conecta ao PowerShell de segurança & de conformidade, cria uma nova pesquisa de conteúdo que pesquisa o site para pastas e, em seguida, exibe uma lista das pastas localizadas no site especificado.</span><span class="sxs-lookup"><span data-stu-id="a6793-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="a6793-172">O script exibe o nome de cada pasta e adiciona o prefixo de **documentlink** à URL da pasta.</span><span class="sxs-lookup"><span data-stu-id="a6793-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="a6793-173">Como a propriedade **documentlink** é uma propriedade pesquisável, você usará o `documentlink:<path>` par propriedade: valor em uma consulta de pesquisa na etapa 2 para pesquisar essa pasta.</span><span class="sxs-lookup"><span data-stu-id="a6793-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="a6793-174">O script exibe um máximo de 200 pastas de site.</span><span class="sxs-lookup"><span data-stu-id="a6793-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="a6793-175">Se houver mais de 200 pastas de site, as mais recentes serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="a6793-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="a6793-176">Veja um exemplo de saída retornada pelo script para pastas de site.</span><span class="sxs-lookup"><span data-stu-id="a6793-176">Here's an example of the output returned by the script for site folders.</span></span>
  
![Exemplo da lista de nomes de documentlink para pastas de site retornadas pelo script](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="a6793-178">Etapa 2: usar uma ID de pasta ou documentlink para executar uma coleção direcionada</span><span class="sxs-lookup"><span data-stu-id="a6793-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="a6793-179">Após executar o script para coletar uma lista de IDs de pasta ou links de documentos para um usuário específico, a próxima etapa para ir para o centro de conformidade da Microsoft 365 e criar uma nova pesquisa de conteúdo para pesquisar uma pasta específica.</span><span class="sxs-lookup"><span data-stu-id="a6793-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="a6793-180">Você usará o  `folderid:<folderid>`  `documentlink:<path>` par propriedade ou: valor na consulta de pesquisa que você configurou na caixa palavra-chave de pesquisa de conteúdo (ou como o valor para o parâmetro  *ContentMatchQuery*  se você usar o cmdlet **New-ComplianceSearch** ).</span><span class="sxs-lookup"><span data-stu-id="a6793-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="a6793-181">Você pode combinar a  `folderid`  `documentlink` propriedade ou com outros parâmetros de pesquisa ou condições de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6793-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="a6793-182">Se você incluir apenas a  `folderid`  `documentlink` propriedade ou na consulta, a pesquisa retornará todos os itens localizados na pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="a6793-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>
  
1. <span data-ttu-id="a6793-183">Acesse [https://compliance.microsoft.com](https://compliance.microsoft.com) e entre usando a conta e as credenciais que você usou para executar o script na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a6793-183">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="a6793-184">No painel esquerdo do centro de conformidade, clique em **mostrar toda** a  >  **pesquisa de conteúdo** e, em seguida, clique em **nova pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="a6793-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="a6793-185">Na caixa **palavras-chave** , Cole o `folderid:<folderid>` ou o  `documentlink:<path>` valor retornado pelo script na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a6793-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="a6793-186">Por exemplo, a consulta na captura de tela a seguir pesquisará qualquer item na subpasta de limpezas na pasta itens recuperáveis do usuário (o valor da `folderid` propriedade da subpasta de limpezas é mostrado na captura de tela na etapa 1):</span><span class="sxs-lookup"><span data-stu-id="a6793-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![Cole o FolderId ou documentlink na caixa palavra-chave da consulta de pesquisa](../media/FolderIDSearchQuery.png)

4. <span data-ttu-id="a6793-188">Em **locais**, selecione **locais específicos** e clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="a6793-188">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="a6793-189">Execute um dos procedimentos a seguir, dependendo de como você está pesquisando uma pasta de caixa de correio ou uma pasta de site:</span><span class="sxs-lookup"><span data-stu-id="a6793-189">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="a6793-190">Ao lado de **email do Exchange**, clique em **escolher usuários, grupos ou equipes** e, em seguida, adicione a mesma caixa de correio que você especificou ao executar o script na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a6793-190">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="a6793-191">Ou</span><span class="sxs-lookup"><span data-stu-id="a6793-191">Or</span></span>

    - <span data-ttu-id="a6793-192">Ao lado de **sites do SharePoint**, clique em **escolher sites** e adicione a URL do mesmo site que você especificou ao executar o script na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a6793-192">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="a6793-193">Depois de salvar o local de conteúdo para pesquisa, clique em **salvar & executar**, digite um nome para a pesquisa de conteúdo e clique em **salvar** para iniciar a pesquisa de coleta direcionada.</span><span class="sxs-lookup"><span data-stu-id="a6793-193">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="a6793-194">Exemplos de consultas de pesquisa para coleções direcionadas</span><span class="sxs-lookup"><span data-stu-id="a6793-194">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="a6793-195">Aqui estão alguns exemplos de como usar  `folderid` as  `documentlink` Propriedades e em uma consulta de pesquisa para executar uma coleção direcionada.</span><span class="sxs-lookup"><span data-stu-id="a6793-195">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="a6793-196">Os espaços reservados são usados para  `folderid:<folderid>` e  `documentlink:<path>` para economizar espaço.</span><span class="sxs-lookup"><span data-stu-id="a6793-196">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="a6793-197">Este exemplo pesquisa três pastas de caixa de correio diferentes.</span><span class="sxs-lookup"><span data-stu-id="a6793-197">This example searches three different mailbox folders.</span></span> <span data-ttu-id="a6793-198">Você pode usar sintaxe de consulta semelhante para pesquisar as pastas ocultas em uma pasta de itens recuperáveis de um usuário.</span><span class="sxs-lookup"><span data-stu-id="a6793-198">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="a6793-199">Este exemplo procura em uma pasta de caixa de correio itens que contenham uma frase exata.</span><span class="sxs-lookup"><span data-stu-id="a6793-199">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="a6793-200">Este exemplo pesquisa uma pasta de site (e todas as subpastas) para documentos que contenham as letras "NDA" no título.</span><span class="sxs-lookup"><span data-stu-id="a6793-200">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="a6793-201">Este exemplo pesquisa uma pasta de site (e qualquer subpasta) para documentos que foram alterados em um intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="a6793-201">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="a6793-202">Mais informações</span><span class="sxs-lookup"><span data-stu-id="a6793-202">More information</span></span>

<span data-ttu-id="a6793-203">Tenha em mente os seguintes pontos ao usar o script neste artigo para executar coleções direcionadas.</span><span class="sxs-lookup"><span data-stu-id="a6793-203">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="a6793-204">O script não remove nenhuma pasta dos resultados.</span><span class="sxs-lookup"><span data-stu-id="a6793-204">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="a6793-205">Portanto, algumas pastas listadas nos resultados podem não ser pesquisadas (ou retornar itens zero) porque elas contêm conteúdo gerado pelo sistema ou porque contêm apenas subpastas e não itens de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="a6793-205">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="a6793-206">Este script retorna apenas as informações da pasta da caixa de correio principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="a6793-206">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="a6793-207">Ele não retorna informações sobre pastas na caixa de correio de arquivo morto do usuário.</span><span class="sxs-lookup"><span data-stu-id="a6793-207">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="a6793-208">Para retornar informações sobre pastas na caixa de correio de arquivo morto do usuário, você pode editar o script.</span><span class="sxs-lookup"><span data-stu-id="a6793-208">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="a6793-209">Para fazer isso, altere a linha `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` para `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` e, em seguida, salve e execute o script editado.</span><span class="sxs-lookup"><span data-stu-id="a6793-209">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="a6793-210">Essa alteração retornará as IDs de pasta para pastas e subpastas na caixa de correio de arquivo morto do usuário.</span><span class="sxs-lookup"><span data-stu-id="a6793-210">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="a6793-211">Para Pesquisar toda a caixa de correio de arquivo morto, você pode conectar todas as propriedades de ID de pasta: pares de valores com um `OR` operador em uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6793-211">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="a6793-212">Ao pesquisar pastas de caixa de correio, somente a pasta especificada (identificada por sua `folderid` Propriedade) será pesquisada; as subpastas não serão pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="a6793-212">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="a6793-213">Para pesquisar subpastas, você precisa usar a ID de pasta para a subpasta que você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="a6793-213">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="a6793-214">Ao pesquisar pastas de site, a pasta (identificado por sua `documentlink` Propriedade) e todas as subpastas serão pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="a6793-214">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span> 

- <span data-ttu-id="a6793-215">Ao exportar os resultados de uma pesquisa na qual você só especificou a `folderid` Propriedade na consulta de pesquisa, você pode escolher a primeira opção de exportação, "todos os itens, exceto aqueles que têm um formato não reconhecido, são criptografados ou não foram indexados por outros motivos".</span><span class="sxs-lookup"><span data-stu-id="a6793-215">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="a6793-216">Todos os itens na pasta sempre serão exportados, independentemente do status de indexação, porque a ID da pasta é sempre indexada.</span><span class="sxs-lookup"><span data-stu-id="a6793-216">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
