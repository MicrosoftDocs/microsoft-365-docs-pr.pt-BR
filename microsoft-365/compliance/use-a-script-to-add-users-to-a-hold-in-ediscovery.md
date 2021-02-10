---
title: Usar um script para adicionar usuários a uma espera em um caso de Descoberta e Principal
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
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Saiba como executar um script para adicionar caixas de correio & sites do OneDrive for Business a uma nova espera associada a um caso de Descoberta Eletrônico no centro de conformidade do Microsoft 365.
ms.openlocfilehash: 278e8e051165eca906e9b454268068cbbe6aef05
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175570"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>Usar um script para adicionar usuários a uma espera em um caso de Descoberta e Principal

O PowerShell & segurança e conformidade fornece cmdlets que permitem automatizar tarefas demoradas relacionadas à criação e gerenciamento de casos de Descoberta Eletrônica. Atualmente, o uso do caso de Descoberta Principal no Centro de Conformidade e Segurança & para colocar um grande número de locais de conteúdo custodiante em espera leva tempo e preparação. Por exemplo, antes de criar uma espera, você precisa coletar a URL de cada site do OneDrive for Business que deseja colocar em espera. Em seguida, para cada usuário que você deseja colocar em espera, você precisa adicionar sua caixa de correio e seu site do OneDrive for Business à espera. Você pode usar o script neste artigo para automatizar esse processo.
  
O script solicita o nome do domínio de Meu Site da sua organização (por exemplo, na URL, o nome de um caso de Descoberta Eletrônico existente, o nome da nova responsabilidade associada à ocorrência, uma lista de endereços de email dos usuários que você deseja colocar em espera e uma consulta de pesquisa a ser usada se quiser criar uma espera baseada em `contoso` https://contoso-my.sharepoint.com) consulta. Em seguida, o script obtém a URL do site do OneDrive for Business para cada usuário na lista, cria a nova espera e, em seguida, adiciona a caixa de correio e o site do OneDrive for Business para cada usuário na lista à espera. O script também gera arquivos de log que contêm informações sobre a nova espera.
  
Aqui estão as etapas para fazer isso acontecer:
  
[Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online](#step-1-install-the-sharepoint-online-management-shell)
  
[Etapa 2: Gerar uma lista de usuários](#step-2-generate-a-list-of-users)
  
[Etapa 3: Executar o script para criar uma espera e adicionar usuários](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>Antes de adicionar usuários a uma espera

- Você precisa ser membro do grupo de funções Gerente de Descobertas EDiscovery no Centro de Conformidade & Segurança e um administrador do SharePoint Online para executar o script na Etapa 3. Para saber mais, confira Atribuir permissões de Descoberta e no Centro de Conformidade e Segurança [& do Office 365.](assign-ediscovery-permissions.md)

- No máximo 1.000 caixas de correio e 100 sites podem ser adicionados a uma espera associada a um caso de & Descoberta Eletrônico no Centro de Conformidade e Segurança. Supondo que cada usuário que você deseja colocar em espera tenha um site do OneDrive for Business, você pode adicionar no máximo 100 usuários a uma espera usando o script neste artigo.

- Salve a lista de usuários que você criou na Etapa 2 e o script na Etapa 3 na mesma pasta. Isso facilitará a executar o script.

- O script adiciona a lista de usuários a uma nova isenta que está associada a um caso existente. Certifique-se de que o caso ao que você deseja associar a iseção foi criado antes de executar o script.

- O script neste artigo oferece suporte à autenticação moderna & ao se conectar ao PowerShell do Centro de Conformidade e Segurança e Ao Shell de Gerenciamento do SharePoint Online. Você pode usar o script como está se você for uma organização do Microsoft 365 ou microsoft 365 GCC. Se você for uma organização do Office 365 Germany, uma organização do Microsoft 365 GCC High ou uma organização do Microsoft 365 DoD, terá que editar o script para executar com êxito. Especificamente, você precisa editar a linha e usar os `Connect-IPPSSession` parâmetros *ConnectionUri* e *AzureADAuthorizationEndpointUri* (e os valores apropriados para seu tipo de organização &) para se conectar ao PowerShell do Centro de Conformidade e Segurança. Para obter mais informações, consulte os exemplos no PowerShell do Centro de Conformidade e Segurança [& Segurança.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- O script se desconecta automaticamente do PowerShell do Centro de Conformidade & Segurança e do Shell de Gerenciamento do SharePoint Online.

- O script inclui tratamento mínimo de erros. Seu objetivo principal é colocar rapidamente e facilmente a caixa de correio e o site do OneDrive for Business de cada usuário em espera.

- Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online

A primeira etapa é instalar o Shell de Gerenciamento do SharePoint Online se ele ainda não estiver instalado no computador local. Você não precisa usar o shell neste procedimento, mas precisa instalá-lo porque ele contém os pré-requisitos exigidos pelo script executado na Etapa 3. Esses pré-requisitos permitem que o script se comunique com o SharePoint Online para obter as URLs dos sites do OneDrive for Business.
  
Vá para Configurar o ambiente Do Windows PowerShell do Shell de Gerenciamento do [SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) e execute as Etapas 1 e 2 para instalar o Shell de Gerenciamento do SharePoint Online no computador local.

## <a name="step-2-generate-a-list-of-users"></a>Etapa 2: Gerar uma lista de usuários

O script na Etapa 3 criará uma responsabilidade associada a um caso de Descoberta Eletrônico e adicionará as caixas de correio e os sites do OneDrive for Business de uma lista de usuários à espera. Você pode apenas digitar os endereços de email em um arquivo de texto ou pode executar um comando no Windows PowerShell para obter uma lista de endereços de email e salvá-los em um arquivo (localizado na mesma pasta em que você salvará o script na Etapa 3).
  
Aqui está um comando do PowerShell (executado usando o PowerShell remoto conectado à sua organização do Exchange Online) para obter uma lista de endereços de email para todos os usuários em sua organização e salvá-lo em um arquivo de texto chamado HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Depois de executar esse comando, abra o arquivo de texto e remova o header que contém o nome da  `PrimarySmtpAddress` propriedade. Em seguida, remova todos os endereços de email, exceto os dos usuários que você deseja adicionar à espera que você criará na Etapa 3. Certifique-se de que não haja linhas em branco antes ou depois da lista de endereços de email.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Etapa 3: Executar o script para criar uma espera e adicionar usuários

Quando você executar o script nesta etapa, ele solicitará as informações a seguir. Certifique-se de ter essas informações prontas antes de executar o script.
  
- **Suas credenciais de usuário:** O script usará suas credenciais para se conectar ao Centro de Conformidade & segurança com o PowerShell. Ele também usará essas credenciais para acessar o SharePoint Online e obter as URLs do OneDrive for Business para a lista de usuários.

- **Nome do seu domínio do SharePoint:** O script solicita que você insira esse nome para que ele possa se conectar ao Centro de administração do SharePoint. Ele também usa o nome de domínio para as URLs do OneDrive em sua organização. Por exemplo, se a URL do seu centro de administração for e a URL do OneDrive for, você digitará quando o script solicitar seu `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` nome de `contoso` domínio.

- **Nome da ocorrência:** O nome de uma ocorrência existente. O script criará uma nova iseção associada a esse caso.

- **Nome da espera:** O nome da espera que o script criará e associará ao caso especificado.

- **Consulta de pesquisa para uma espera baseada em consulta:** Você pode criar uma isenção baseada em consulta para que somente o conteúdo que atenda aos critérios de pesquisa especificados seja colocado em espera. Para colocar todo o conteúdo em espera, pressione **Enter** quando for solicitado a fazer uma consulta de pesquisa.

- **A ligar a espera ou não:** Você pode fazer o script ativar a espera depois que ele é criado ou pode fazer com que o script crie a espera sem habilita-lo. Se você não tiver o script para ativar a espera &, poderá a turn-lo posteriormente no Centro de Conformidade e Segurança ou executando os seguintes comandos do PowerShell:

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Nome do arquivo de texto** com a lista de usuários - O nome do arquivo de texto da Etapa 2 que contém a lista de usuários a adicionar à espera. Se esse arquivo estiver localizado na mesma pasta do script, basta digitar o nome do arquivo (por exemplo, HoldUsers.txt). Se o arquivo de texto estiver em outra pasta, digite o nome de caminho completo do arquivo.

Depois de coletar as informações que o script solicitará, a etapa final é executar o script para criar o novo hold e adicionar usuários a ele.
  
1. Salve o texto a seguir em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo de `.ps1` . Por exemplo, `AddUsersToHold.ps1`.

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. No computador local, abra o Windows PowerShell e vá para a pasta onde você salvou o script.

3. Execute o script; por exemplo:

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. Insira as informações que o script solicita.

   O & script se conecta ao PowerShell do Centro de Conformidade e Segurança e, em seguida, cria a nova espera no caso de Descoberta Eletrônico e adiciona as caixas de correio e o OneDrive for Business para os usuários na lista. Você pode ir para o caso na página descoberta de **eDiscovery** no Centro de conformidade & segurança para exibir a nova espera.

Após a execução do script, ele cria os arquivos de log a seguir e os salva na pasta onde o script está localizado.
  
- **LocationsOnHold.txt:** Contém uma lista de caixas de correio e sites do OneDrive for Business que o script colocou com êxito em espera.

- **LocationsNotOnHold.txt:** Contém uma lista de caixas de correio e sites do OneDrive for Business que o script não colocar em espera. Se um usuário tiver uma caixa de correio, mas não um site do OneDrive for Business, ele será incluído na lista de sites do OneDrive for Business que não foram colocados em espera.

- **GetCaseHoldPolicy.txt:** Contém a saída do cmdlet **Get-CaseHoldPolicy** para a nova espera, que o script criou após criar a nova espera. As informações retornadas por esse cmdlet incluem uma lista de usuários cujas caixas de correio e sites do OneDrive for Business foram colocados em espera e se a espera está habilitada ou desabilitada. 

- **GetCaseHoldRule.txt:** Contém a saída do cmdlet **Get-CaseHoldRule** para a nova espera, que o script foi aplicável após a criação da nova espera. As informações retornadas por esse cmdlet incluirão a consulta de pesquisa se você tiver usado o script para criar uma espera baseada em consulta.
