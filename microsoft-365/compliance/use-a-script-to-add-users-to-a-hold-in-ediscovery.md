---
title: Use um script para adicionar usuários a uma retenção em um caso de descoberta eletrônica principal no centro de conformidade & segurança
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Saiba como executar um script para adicionar caixas de correio & sites do OneDrive for Business a um novo bloqueio associado a uma ocorrência de descoberta eletrônica no centro de conformidade & de segurança.
ms.openlocfilehash: cfa7e176c3974d51fbcc87866c1482277d6010e1
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016304"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>Usar um script para adicionar usuários a uma retenção em um caso de descoberta eletrônica principal

O centro de conformidade do & de segurança fornece cmdlets do PowerShell que permitem automatizar tarefas demoradas relacionadas à criação e ao gerenciamento de ocorrências de descoberta eletrônica. Atualmente, usar a ferramenta de ocorrência de descoberta eletrônica no centro de conformidade do & de segurança para colocar um grande número de locais de conteúdo dos responsáveis em espera leva tempo e preparação. Por exemplo, antes de criar uma retenção, você precisa coletar a URL de cada site do OneDrive for Business que deseja colocar em espera. Em seguida, para cada usuário que você deseja colocar em espera, adicione a caixa de correio e o site do OneDrive for Business à isenção. Em versões futuras do centro de conformidade com segurança &, isso será mais fácil. Até lá, você pode usar o script neste artigo para automatizar esse processo.
  
O script solicita o nome do domínio meusite da sua organização (por exemplo, **contoso** na URL https://contoso-my.sharepoint.com) , o nome de um caso de descoberta eletrônica existente, o nome da nova retenção associada ao caso, uma lista de endereços de email dos usuários que você deseja colocar em espera e uma consulta de pesquisa a ser usada se você quiser criar uma retenção baseada em consulta. Em seguida, o script Obtém a URL do site do OneDrive for Business para cada usuário na lista, cria a nova isenção e, em seguida, adiciona a caixa de correio e o site do OneDrive for Business para cada usuário na lista à isenção. O script também gera arquivos de log que contêm informações sobre a nova isenção.
  
Estas são as etapas para fazer isso:
  
[Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online](#step-1-install-the-sharepoint-online-management-shell)
  
[Etapa 2: gerar uma lista de usuários](#step-2-generate-a-list-of-users)
  
[Etapa 3: executar o script para criar um bloqueio e adicionar usuários](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>Antes de adicionar usuários a uma isenção

- Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade & segurança e administrador do SharePoint Online para executar o script na etapa 3. Para obter mais informações, consulte [atribuir permissões de descoberta eletrônica no centro de conformidade & segurança do Office 365](assign-ediscovery-permissions.md).

- Um máximo de 1.000 caixas de correio e 100 sites pode ser adicionado a uma retenção associada a uma ocorrência de descoberta eletrônica no centro de conformidade de & de segurança. Supondo que cada usuário que você deseja colocar em espera tenha um site do OneDrive for Business, você pode adicionar no máximo 100 usuários a uma isenção usando o script neste artigo.

- Certifique-se de salvar a lista de usuários que você criou na etapa 2 e o script na etapa 3 para a mesma pasta. Isso facilitará a execução do script.

- O script adiciona a lista de usuários a uma nova retenção associada a um caso existente. Verifique se o caso para o qual você deseja associar a retenção foi criado antes de executar o script.

- O script inclui o tratamento de erros mínimo. Seu objetivo principal é colocar rápida e facilmente a caixa de correio e o site do OneDrive for Business de cada usuário em espera.

- The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online

A primeira etapa é instalar o Shell de gerenciamento do SharePoint Online se ele ainda não estiver instalado no computador local. Não é necessário usar o Shell neste procedimento, mas você precisa instalá-lo porque ele contém pré-requisitos necessários para o script executado na etapa 3. Esses pré-requisitos permitem que o script se comunique com o SharePoint Online para obter as URLs para os sites do OneDrive for Business.
  
Vá para [Configurar o ambiente do Windows PowerShell do Shell de gerenciamento do SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) e execute a etapa 1 e a etapa 2 para instalar o Shell de gerenciamento do SharePoint Online no computador local. 

## <a name="step-2-generate-a-list-of-users"></a>Etapa 2: gerar uma lista de usuários

O script na etapa 3 criará uma retenção associada a uma ocorrência de descoberta eletrônica e adicionará as caixas de correio e os sites do OneDrive for Business de uma lista de usuários à isenção. Você pode simplesmente digitar os endereços de email em um arquivo de texto ou pode executar um comando no Windows PowerShell para obter uma lista de endereços de email e salvá-los em um arquivo (localizado na mesma pasta em que você salvará o script na etapa 3).
  
Aqui está um comando do PowerShell (executado usando o PowerShell remoto conectado à sua organização do Exchange Online) para obter uma lista de endereços de email para todos os usuários em sua organização e salvá-lo em um arquivo de texto chamado HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Depois de executar esse comando, abra o arquivo de texto e remova o cabeçalho que contém o nome da propriedade `PrimarySmtpAddress` . Em seguida, remova todos os endereços de email, exceto aqueles para os usuários que você deseja adicionar à isenção que você criará na etapa 3. Certifique-se de que não haja linhas em branco antes ou depois da lista de endereços de email.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Etapa 3: executar o script para criar um bloqueio e adicionar usuários

Quando você executar o script nesta etapa, ele solicitará as seguintes informações. Certifique-se de ter essas informações prontas antes de executar o script.
  
- **Suas credenciais de usuário:** O script usará suas credenciais para se conectar ao centro de conformidade de & de segurança com o PowerShell remoto. Ele também usará essas credenciais para acessar o SharePoint Online para obter as URLs do OneDrive for Business para a lista de usuários.

- **Nome do seu domínio do meusite:** O domínio MeuSite é o domínio que contém todos os sites do OneDrive for Business em sua organização. Por exemplo, se a URL do seu domínio meusite for **https://contoso-my.sharepoint.com** , você deve inserir `contoso` quando o script solicitar o nome do seu domínio meusite.

- **Nome do caso:** O nome de um caso existente. O script criará uma nova retenção associada a esse caso.

- **Nome da retenção:** O nome da retenção que o script criará e associará ao caso especificado.

- **Consulta de pesquisa para uma retenção baseada em consulta:** Você pode criar um bloqueio baseado em consulta para que somente o conteúdo que atende aos critérios de pesquisa especificados seja colocado em espera. Para colocar todo o conteúdo em espera, basta pressionar **Enter** quando for solicitada uma consulta de pesquisa.

- **Se a retenção deve ou não ser ativada:** Você pode fazer com que o script ative o bloqueio após sua criação ou você pode fazer com que o script crie o bloqueio sem habilitá-lo. Se você não tiver o script ativado na isenção, você poderá ativá-lo mais tarde no centro de conformidade & segurança ou executando os seguintes comandos do PowerShell:

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Nome do arquivo de texto com a lista de usuários** : o nome do arquivo de texto da etapa 2 que contém a lista de usuários a serem adicionados à isenção. Se esse arquivo estiver localizado na mesma pasta que o script, basta digitar o nome do arquivo (por exemplo, HoldUsers.txt). Se o arquivo de texto estiver em outra pasta, digite o nome de caminho completo do arquivo.

Após coletar as informações que o script solicitará, a etapa final será executar o script para criar o novo bloqueio e adicionar usuários a ele.
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo de `.ps1` . Por exemplo, `AddUsersToHold.ps1`.

  ```powershell
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
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
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

2. No computador local, abra o Windows PowerShell e vá para a pasta onde você salvou o script.

3. Executar o script; por exemplo:

      ```powershell
    .\AddUsersToHold.ps1
      ```

4. Insira as informações que o script solicitará para você.

   O script se conecta ao PowerShell do centro de conformidade & segurança e, em seguida, cria o novo bloqueio no caso de descoberta eletrônica e adiciona as caixas de correio e o OneDrive for Business para os usuários na lista. Você pode ir para o caso na página **descoberta eletrônica** no centro de conformidade de & de segurança para exibir o novo bloqueio. 

Após a conclusão da execução do script, ele cria os seguintes arquivos de log e os salva na pasta em que o script está localizado.
  
- **LocationsOnHold.txt:** Contém uma lista de caixas de correio e sites do OneDrive for Business que o script colocou com êxito em espera.

- **LocationsNotOnHold.txt:** Contém uma lista de caixas de correio e sites do OneDrive for Business que o script não localizou em espera. Se um usuário tiver uma caixa de correio, mas não um site do OneDrive for Business, o usuário será incluído na lista de sites do OneDrive for Business que não foram colocados em espera.

- **GetCaseHoldPolicy.txt:** Contém a saída do cmdlet **Get-CaseHoldPolicy** para a nova isenção, que o script executou após a criação da nova isenção. As informações retornadas por este cmdlet incluem uma lista de usuários cujas caixas de correio e sites do OneDrive for Business foram colocados em espera e se a retenção está habilitada ou desabilitada. 

- **GetCaseHoldRule.txt:** Contém a saída do cmdlet **Get-CaseHoldRule** para a nova isenção, que o script executou após a criação da nova isenção. As informações retornadas por esse cmdlet incluirão a consulta de pesquisa se você tiver usado o script para criar uma retenção baseada em consulta.
