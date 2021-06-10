---
title: Pesquisar o site & OneDrive for Business caixa de correio para uma lista de usuários com Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Use a Pesquisa de Conteúdo e o script neste artigo para pesquisar as caixas de correio e OneDrive for Business sites para um grupo de usuários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922463"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="eb263-103">Use a Pesquisa de Conteúdo para procurar uma lista de usuários na caixa de correio e no site do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="eb263-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="eb263-104">O Centro de Conformidade & segurança fornece vários cmdlets Windows PowerShell que permitem automatizar tarefas relacionadas à Descoberta Eletrônica demorada.</span><span class="sxs-lookup"><span data-stu-id="eb263-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="eb263-105">Atualmente, a criação de uma Pesquisa de Conteúdo no Centro de Conformidade & Segurança para pesquisar um grande número de locais de conteúdo custodiante leva tempo e preparação.</span><span class="sxs-lookup"><span data-stu-id="eb263-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="eb263-106">Antes de criar uma pesquisa, você precisa coletar a URL para cada site OneDrive for Business e adicionar cada caixa de correio e OneDrive for Business site à pesquisa.</span><span class="sxs-lookup"><span data-stu-id="eb263-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="eb263-107">Em versões futuras, isso será mais fácil de fazer no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="eb263-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="eb263-108">Até lá, você pode usar o script neste artigo para automatizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="eb263-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="eb263-109">Este script solicita o nome do domínio MySite da sua organização (por exemplo, **contoso** na URL ), uma lista de endereços de email do usuário, o nome da nova Pesquisa de Conteúdo e a consulta de pesquisa a ser `https://contoso-my.sharepoint.com` usada.</span><span class="sxs-lookup"><span data-stu-id="eb263-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL `https://contoso-my.sharepoint.com`), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="eb263-110">O script obtém a URL de OneDrive for Business para cada usuário na lista e, em seguida, cria e inicia uma Pesquisa de Conteúdo que pesquisa a caixa de correio e o site OneDrive for Business para cada usuário na lista, usando a consulta de pesquisa que você fornece.</span><span class="sxs-lookup"><span data-stu-id="eb263-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span>
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="eb263-111">Permissões e informações de script</span><span class="sxs-lookup"><span data-stu-id="eb263-111">Permissions and script information</span></span>

- <span data-ttu-id="eb263-112">Você precisa ser membro do grupo de funções do Gerenciador de Descobertas Esdiscovery no Centro de Conformidade & Segurança e um administrador global do SharePoint Online para executar o script na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="eb263-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>

- <span data-ttu-id="eb263-113">Salve a lista de usuários que você criar na Etapa 2 e o script na Etapa 3 na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="eb263-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="eb263-114">Isso facilitará a executar o script.</span><span class="sxs-lookup"><span data-stu-id="eb263-114">That will make it easier to run the script.</span></span>

- <span data-ttu-id="eb263-115">O script inclui tratamento mínimo de erros.</span><span class="sxs-lookup"><span data-stu-id="eb263-115">The script includes minimal error handling.</span></span> <span data-ttu-id="eb263-116">Seu principal objetivo é pesquisar rapidamente e facilmente a caixa de correio e OneDrive for Business site de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="eb263-116">Its primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>

- <span data-ttu-id="eb263-p104">Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="eb263-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="eb263-122">Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="eb263-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="eb263-123">A primeira etapa é instalar o Shell de Gerenciamento SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="eb263-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="eb263-124">Você não precisa usar o shell neste procedimento, mas precisa instalá-lo porque ele contém os pré-requisitos exigidos pelo script executado na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="eb263-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="eb263-125">Esses pré-requisitos permitem que o script se comunique com o SharePoint Online para obter as URLs para os OneDrive for Business sites.</span><span class="sxs-lookup"><span data-stu-id="eb263-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="eb263-126">Vá para Configurar o ambiente SharePoint Shell de Gerenciamento [Online Windows PowerShell e](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) execute a Etapa 1 e a Etapa 2 para instalar o Shell de Gerenciamento SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="eb263-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="eb263-127">Etapa 2: Gerar uma lista de usuários</span><span class="sxs-lookup"><span data-stu-id="eb263-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="eb263-128">O script na Etapa 3 criará uma Pesquisa de Conteúdo para pesquisar as caixas de correio e OneDrive contas de uma lista de usuários.</span><span class="sxs-lookup"><span data-stu-id="eb263-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="eb263-129">Você pode digitar os endereços de email em um arquivo de texto ou executar um comando no Windows PowerShell para obter uma lista de endereços de email e salvá-los em um arquivo (localizado na mesma pasta para a qual você salvará o script na Etapa 3).</span><span class="sxs-lookup"><span data-stu-id="eb263-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="eb263-130">Aqui está um comando [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) que você pode executar para obter uma lista de endereços de email para todos os usuários em sua organização e salvá-lo em um arquivo de texto chamado `Users.txt` .</span><span class="sxs-lookup"><span data-stu-id="eb263-130">Here's an [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="eb263-131">Depois de executar esse comando, certifique-se de abrir o arquivo e remover o header que contém o nome da propriedade,  `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="eb263-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="eb263-132">O arquivo de texto deve conter apenas uma lista de endereços de email e nada mais.</span><span class="sxs-lookup"><span data-stu-id="eb263-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="eb263-133">Certifique-se de que não haja linhas em branco antes ou após a lista de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="eb263-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="eb263-134">Etapa 3: Executar o script para criar e iniciar a pesquisa</span><span class="sxs-lookup"><span data-stu-id="eb263-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="eb263-135">Quando você executar o script nesta etapa, ele solicitará as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="eb263-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="eb263-136">Certifique-se de ter essas informações prontas antes de executar o script.</span><span class="sxs-lookup"><span data-stu-id="eb263-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="eb263-137">**Suas** credenciais de usuário - O script usará suas credenciais para acessar o SharePoint Online para obter as URLs OneDrive for Business de OneDrive for Business e se conectar ao Centro de Conformidade & Segurança com o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="eb263-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="eb263-138">**Nome do seu domínio MySite** - O domínio MySite é o domínio que contém todos os OneDrive for Business de sua organização.</span><span class="sxs-lookup"><span data-stu-id="eb263-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="eb263-139">Por exemplo, se a URL do seu domínio MySite for , você digitará quando o script solicitar o nome do **https://contoso-my.sharepoint.com**  `contoso` seu domínio MySite.</span><span class="sxs-lookup"><span data-stu-id="eb263-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="eb263-140">**Pathname do arquivo de texto** da Etapa 2 - O nome do caminho do arquivo de texto que você criou na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="eb263-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="eb263-141">Se o arquivo de texto e o script estão localizados na mesma pasta, digite o nome do arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="eb263-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="eb263-142">Caso contrário, insira o nome do caminho completo para o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="eb263-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="eb263-143">**Nome da Pesquisa de Conteúdo** - O nome da Pesquisa de Conteúdo que será criada pelo script.</span><span class="sxs-lookup"><span data-stu-id="eb263-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="eb263-144">**Consulta de pesquisa** - A consulta de pesquisa que será usada com a Pesquisa de Conteúdo é criada e executado.</span><span class="sxs-lookup"><span data-stu-id="eb263-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="eb263-145">Para obter mais informações sobre consultas de pesquisa, consulte [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="eb263-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="eb263-146">**Para executar o script:**</span><span class="sxs-lookup"><span data-stu-id="eb263-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="eb263-147">Salve o texto a seguir em um arquivo Windows PowerShell script usando um sufixo de nome de arquivo de .ps1; por exemplo, `SearchEXOOD4B.ps1` .</span><span class="sxs-lookup"><span data-stu-id="eb263-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="eb263-148">Salve o arquivo na mesma pasta em que você salvou a lista de usuários na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="eb263-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="eb263-149">Abra Windows PowerShell e vá para a pasta onde você salvou o script e a lista de usuários da Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="eb263-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="eb263-150">Inicie o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eb263-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="eb263-151">Quando solicitado para suas credenciais, insira seu endereço de email e senha e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb263-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="eb263-152">Insira as informações a seguir quando solicitado pelo script.</span><span class="sxs-lookup"><span data-stu-id="eb263-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="eb263-153">Digite cada informação e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="eb263-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="eb263-154">O nome do seu domínio MySite.</span><span class="sxs-lookup"><span data-stu-id="eb263-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="eb263-155">O nome do caminho do arquivo de texto que contém a lista de usuários.</span><span class="sxs-lookup"><span data-stu-id="eb263-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="eb263-156">Um nome para a Pesquisa de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="eb263-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="eb263-157">A consulta de pesquisa (deixe isso em branco para retornar todos os itens nos locais de conteúdo).</span><span class="sxs-lookup"><span data-stu-id="eb263-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="eb263-158">O script obtém as URLs de cada site OneDrive for Business e cria e inicia a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="eb263-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="eb263-159">Você pode executar o cmd & let **Get-ComplianceSearch** no Centro de Conformidade e Segurança do PowerShell  para exibir as estatísticas e resultados da pesquisa ou pode ir para a página de pesquisa de conteúdo no Centro de Conformidade e Segurança & para exibir informações sobre a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="eb263-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span>