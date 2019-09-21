---
title: Use um script para adicionar usuários a uma retenção em caso de descoberta eletrônica no centro de conformidade & segurança
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: Execute um script para adicionar rapidamente as caixas de correio e os sites do OneDrive for Business a uma nova retenção associada a um caso de descoberta eletrônica no centro de conformidade do & de segurança.
ms.openlocfilehash: c680e584a6f729b3d6d0d74b84ddd0e03da6dc9a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073055"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-security--compliance-center"></a><span data-ttu-id="363df-103">Use um script para adicionar usuários a uma retenção em caso de descoberta eletrônica no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="363df-103">Use a script to add users to a hold in an eDiscovery case in the Security & Compliance Center</span></span>

<span data-ttu-id="363df-104">O centro de conformidade do & de segurança fornece muitos cmdlets do Windows PowerShell que permitem automatizar tarefas demoradas relacionadas à criação e ao gerenciamento de ocorrências de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="363df-104">The Security & Compliance Center provides lots of Windows PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="363df-105">Atualmente, usar a ferramenta de ocorrência de descoberta eletrônica no centro de conformidade do & de segurança para colocar um grande número de locais de conteúdo dos responsáveis em espera leva tempo e preparação.</span><span class="sxs-lookup"><span data-stu-id="363df-105">Currently, using the eDiscovery case tool in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="363df-106">Por exemplo, antes de criar uma retenção, você precisa coletar a URL de cada site do OneDrive for Business que deseja colocar em espera.</span><span class="sxs-lookup"><span data-stu-id="363df-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="363df-107">Em seguida, para cada usuário que você deseja colocar em espera, adicione a caixa de correio e o site do OneDrive for Business à isenção.</span><span class="sxs-lookup"><span data-stu-id="363df-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="363df-108">Em versões futuras do centro de conformidade com segurança &, isso será mais fácil.</span><span class="sxs-lookup"><span data-stu-id="363df-108">In future releases of the Security & Compliance Center, this will get easier to do.</span></span> <span data-ttu-id="363df-109">Até lá, você pode usar o script neste artigo para automatizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="363df-109">Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="363df-110">O script solicita o nome do domínio meusite da sua organização (por exemplo, **contoso** na URL https://contoso-my.sharepoint.com), o nome de um caso de descoberta eletrônica existente, o nome da nova retenção associada ao caso, uma lista de endereços de email dos usuários que você deseja para colocar em espera e uma consulta de pesquisa a ser usada se você quiser criar uma retenção baseada em consulta.</span><span class="sxs-lookup"><span data-stu-id="363df-110">The script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="363df-111">Em seguida, o script Obtém a URL do site do OneDrive for Business para cada usuário na lista, cria a nova isenção e, em seguida, adiciona a caixa de correio e o site do OneDrive for Business para cada usuário na lista à isenção.</span><span class="sxs-lookup"><span data-stu-id="363df-111">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="363df-112">O script também gera arquivos de log que contêm informações sobre a nova isenção.</span><span class="sxs-lookup"><span data-stu-id="363df-112">The script also generates log files that contain information about the new hold.</span></span> 
  
<span data-ttu-id="363df-113">Estas são as etapas para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="363df-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="363df-114">Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="363df-114">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="363df-115">Etapa 2: gerar uma lista de usuários</span><span class="sxs-lookup"><span data-stu-id="363df-115">Step 2: Generate a list of users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[<span data-ttu-id="363df-116">Etapa 3: executar o script para criar um bloqueio e adicionar usuários</span><span class="sxs-lookup"><span data-stu-id="363df-116">Step 3: Run the script to create a hold and add users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a><span data-ttu-id="363df-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="363df-117">Before you begin</span></span>

- <span data-ttu-id="363df-118">Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade & segurança e um administrador global do SharePoint Online para executar o script na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="363df-118">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span> <span data-ttu-id="363df-119">Para obter mais informações, consulte [atribuir permissões de descoberta eletrônica no centro de conformidade & segurança do Office 365](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="363df-119">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="363df-120">Um máximo de 1.000 caixas de correio e 100 sites pode ser adicionado a uma retenção associada a uma ocorrência de descoberta eletrônica no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="363df-120">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="363df-121">Supondo que cada usuário que você deseja colocar em espera tenha um site do OneDrive for Business, você pode adicionar no máximo 100 usuários a uma isenção usando o script neste artigo.</span><span class="sxs-lookup"><span data-stu-id="363df-121">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span> 
    
- <span data-ttu-id="363df-122">Certifique-se de salvar a lista de usuários que você criou na etapa 2 e o script na etapa 3 para a mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="363df-122">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="363df-123">Isso facilitará a execução do script.</span><span class="sxs-lookup"><span data-stu-id="363df-123">That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="363df-124">O script adiciona a lista de usuários a uma nova retenção associada a um caso existente.</span><span class="sxs-lookup"><span data-stu-id="363df-124">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="363df-125">Verifique se o caso para o qual você deseja associar a retenção foi criado antes de executar o script.</span><span class="sxs-lookup"><span data-stu-id="363df-125">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>
    
- <span data-ttu-id="363df-126">O script inclui o tratamento de erros mínimo.</span><span class="sxs-lookup"><span data-stu-id="363df-126">The script includes minimal error handling.</span></span> <span data-ttu-id="363df-127">Seu objetivo principal é colocar rápida e facilmente a caixa de correio e o site do OneDrive for Business de cada usuário em espera.</span><span class="sxs-lookup"><span data-stu-id="363df-127">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>
    
- <span data-ttu-id="363df-p108">Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="363df-p108">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="363df-133">Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="363df-133">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="363df-134">A primeira etapa é instalar o Shell de gerenciamento do SharePoint Online se ele ainda não estiver instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="363df-134">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="363df-135">Não é necessário usar o Shell neste procedimento, mas você precisa instalá-lo porque ele contém pré-requisitos necessários para o script executado na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="363df-135">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="363df-136">Esses pré-requisitos permitem que o script se comunique com o SharePoint Online para obter as URLs para os sites do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="363df-136">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="363df-137">Vá para [Configurar o ambiente do Windows PowerShell do Shell de gerenciamento do SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) e execute a etapa 1 e a etapa 2 para instalar o Shell de gerenciamento do SharePoint Online no computador local.</span><span class="sxs-lookup"><span data-stu-id="363df-137">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="363df-138">Etapa 2: gerar uma lista de usuários</span><span class="sxs-lookup"><span data-stu-id="363df-138">Step 2: Generate a list of users</span></span>
<span data-ttu-id="363df-139"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="363df-139"></span></span>

<span data-ttu-id="363df-140">O script na etapa 3 criará uma retenção associada a uma ocorrência de descoberta eletrônica e adicionará as caixas de correio e os sites do OneDrive for Business de uma lista de usuários à isenção.</span><span class="sxs-lookup"><span data-stu-id="363df-140">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="363df-141">Você pode simplesmente digitar os endereços de email em um arquivo de texto ou pode executar um comando no Windows PowerShell para obter uma lista de endereços de email e salvá-los em um arquivo (localizado na mesma pasta em que você salvará o script na etapa 3).</span><span class="sxs-lookup"><span data-stu-id="363df-141">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="363df-142">Aqui está um comando do PowerShell (executado usando o PowerShell remoto conectado à sua organização do Exchange Online) para obter uma lista de endereços de email para todos os usuários em sua organização e salvá-lo em um arquivo de texto chamado HoldUsers. txt.</span><span class="sxs-lookup"><span data-stu-id="363df-142">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="363df-143">Depois de executar esse comando, abra o arquivo de texto e remova o cabeçalho que contém o nome da `PrimarySmtpAddress`propriedade.</span><span class="sxs-lookup"><span data-stu-id="363df-143">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="363df-144">Em seguida, remova todos os endereços de email, exceto aqueles para os usuários que você deseja adicionar à isenção que você criará na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="363df-144">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="363df-145">Certifique-se de que não haja linhas em branco antes ou depois da lista de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="363df-145">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="363df-146">Etapa 3: executar o script para criar um bloqueio e adicionar usuários</span><span class="sxs-lookup"><span data-stu-id="363df-146">Step 3: Run the script to create a hold and add users</span></span>
<span data-ttu-id="363df-147"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="363df-147"></span></span>

<span data-ttu-id="363df-148">Quando você executar o script nesta etapa, ele solicitará as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="363df-148">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="363df-149">Certifique-se de ter essas informações prontas antes de executar o script.</span><span class="sxs-lookup"><span data-stu-id="363df-149">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="363df-150">**Suas credenciais de usuário** -o script usará suas credenciais para se conectar ao centro de conformidade do & de segurança com o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="363df-150">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="363df-151">Ele também usará essas credenciais para acessar o SharePoint Online para obter as URLs do OneDrive for Business para a lista de usuários.</span><span class="sxs-lookup"><span data-stu-id="363df-151">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>
    
- <span data-ttu-id="363df-152">**Nome do seu domínio meusite** -o domínio MeuSite é o domínio que contém todos os sites do onedrive for Business em sua organização.</span><span class="sxs-lookup"><span data-stu-id="363df-152">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="363df-153">Por exemplo, se a URL do seu domínio meusite for **https://contoso-my.sharepoint.com**, você deve inserir `contoso` quando o script solicitar o nome do seu domínio meusite.</span><span class="sxs-lookup"><span data-stu-id="363df-153">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="363df-154">**Nome do caso** -o nome de um caso existente.</span><span class="sxs-lookup"><span data-stu-id="363df-154">**Name of the case** - The name of an existing case.</span></span> <span data-ttu-id="363df-155">O script criará uma nova retenção associada a esse caso.</span><span class="sxs-lookup"><span data-stu-id="363df-155">The script will create a new hold that is associated with this case.</span></span>
    
- <span data-ttu-id="363df-156">**Nome do bloqueio** -o nome da retenção que o script criará e associará ao caso especificado.</span><span class="sxs-lookup"><span data-stu-id="363df-156">**Name of the hold** - The name of the hold the script will create and associate with the specified case.</span></span>
    
- <span data-ttu-id="363df-157">**Consulta de pesquisa para retenção baseada em consulta** -você pode criar um bloqueio baseado em consulta para que apenas o conteúdo que atende aos critérios de pesquisa especificados seja colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="363df-157">**Search query for a query-based hold** - You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="363df-158">Para colocar todo o conteúdo em espera, basta pressionar **Enter** quando for solicitada uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="363df-158">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span> 
    
- <span data-ttu-id="363df-159">**Se o script deve ou não ser ativado** , você pode fazer com que o script ative a retenção depois que ele é criado ou você pode fazer com que o script crie o bloqueio sem habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="363df-159">**Whether or not to turn the hold on** - You can have the script turn the hold on after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="363df-160">Se você não tiver o script ativado na isenção, você poderá ativá-lo mais tarde no centro de conformidade & segurança ou executando os seguintes comandos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="363df-160">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span> 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="363df-161">**Nome do arquivo de texto com a lista de usuários** : o nome do arquivo de texto da etapa 2 que contém a lista de usuários a serem adicionados à isenção.</span><span class="sxs-lookup"><span data-stu-id="363df-161">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="363df-162">Se esse arquivo estiver localizado na mesma pasta que o script, basta digitar o nome do arquivo (por exemplo, HoldUsers. txt).</span><span class="sxs-lookup"><span data-stu-id="363df-162">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="363df-163">Se o arquivo de texto estiver em outra pasta, digite o nome de caminho completo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="363df-163">If the text file is in another folder, type the full pathname of the file.</span></span>
    
<span data-ttu-id="363df-164">Após coletar as informações que o script solicitará, a etapa final será executar o script para criar o novo bloqueio e adicionar usuários a ele.</span><span class="sxs-lookup"><span data-stu-id="363df-164">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="363df-165">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="363df-165">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `AddUsersToHold.ps1`.</span></span>
    
  ```
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
      }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to http://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
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
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. <span data-ttu-id="363df-166">No computador local, abra o Windows PowerShell e vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="363df-166">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="363df-167">Executar o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="363df-167">Run the script; for example:</span></span>
    
      ```
    .\AddUsersToHold.ps1
      ```

4. <span data-ttu-id="363df-168">Insira as informações que o script solicitará para você.</span><span class="sxs-lookup"><span data-stu-id="363df-168">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="363df-169">O script se conecta ao PowerShell do centro de conformidade & segurança e, em seguida, cria o novo bloqueio no caso de descoberta eletrônica e adiciona as caixas de correio e o OneDrive for Business para os usuários na lista.</span><span class="sxs-lookup"><span data-stu-id="363df-169">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="363df-170">Você pode ir para o caso na página **descoberta eletrônica** no centro de conformidade de & de segurança para exibir o novo bloqueio.</span><span class="sxs-lookup"><span data-stu-id="363df-170">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span> 
    
<span data-ttu-id="363df-171">Após a conclusão da execução do script, ele cria os seguintes arquivos de log e os salva na pasta em que o script está localizado.</span><span class="sxs-lookup"><span data-stu-id="363df-171">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="363df-172">**LocationsOnHold. txt** – contém uma lista de caixas de correio e sites do onedrive for Business que o script colocou com êxito em espera.</span><span class="sxs-lookup"><span data-stu-id="363df-172">**LocationsOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>
    
- <span data-ttu-id="363df-173">**LocationsNotOnHold. txt** -contém uma lista de caixas de correio e sites do onedrive for Business que o script não localizou em espera.</span><span class="sxs-lookup"><span data-stu-id="363df-173">**LocationsNotOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="363df-174">Se um usuário tiver uma caixa de correio, mas não um site do OneDrive for Business, o usuário será incluído na lista de sites do OneDrive for Business que não foram colocados em espera.</span><span class="sxs-lookup"><span data-stu-id="363df-174">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>
    
- <span data-ttu-id="363df-175">**GetCaseHoldPolicy. txt** -contém a saída do cmdlet **Get-CaseHoldPolicy** para a nova isenção, que o script executou após a criação da nova isenção.</span><span class="sxs-lookup"><span data-stu-id="363df-175">**GetCaseHoldPolicy.txt** - Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="363df-176">As informações retornadas por este cmdlet incluem uma lista de usuários cujas caixas de correio e sites do OneDrive for Business foram colocados em espera e se a retenção está habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="363df-176">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 
    
- <span data-ttu-id="363df-177">**GetCaseHoldRule. txt** -contém a saída do cmdlet **Get-CaseHoldRule** para a nova isenção, que o script executou após a criação da nova isenção.</span><span class="sxs-lookup"><span data-stu-id="363df-177">**GetCaseHoldRule.txt** - Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="363df-178">As informações retornadas por esse cmdlet incluirão a consulta de pesquisa se você tiver usado o script para criar uma retenção baseada em consulta.</span><span class="sxs-lookup"><span data-stu-id="363df-178">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span> 
