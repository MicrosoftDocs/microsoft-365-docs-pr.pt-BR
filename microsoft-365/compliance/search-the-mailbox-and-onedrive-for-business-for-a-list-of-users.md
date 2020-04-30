---
title: Use a Pesquisa de Conteúdo para procurar uma lista de usuários na caixa de correio e no site do OneDrive for Business
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Use a pesquisa de conteúdo e o script neste artigo para pesquisar as caixas de correio e os sites do OneDrive for Business para um grupo de usuários.
ms.openlocfilehash: 31dfa2057eff27ed1d2579cc541361858a11c7ce
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943270"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Use a Pesquisa de Conteúdo para procurar uma lista de usuários na caixa de correio e no site do OneDrive for Business

O centro de conformidade do & de segurança fornece vários cmdlets do Windows PowerShell que permitem automatizar tarefas relacionadas a descoberta eletrônica demoradas. Atualmente, a criação de uma pesquisa de conteúdo no centro de conformidade de & de segurança para pesquisar um grande número de locais de conteúdo dos responsáveis leva tempo e preparação. Antes de criar uma pesquisa, você precisa coletar a URL de cada site do OneDrive for Business e, em seguida, adicionar cada caixa de correio e o site do OneDrive for Business à pesquisa. Em versões futuras, isso será mais fácil de fazer no centro de conformidade de & de segurança. Até lá, você pode usar o script neste artigo para automatizar esse processo. Esse script solicita o nome do domínio meusite da sua organização (por exemplo, **contoso** na URL https://contoso-my.sharepoint.com), uma lista de endereços de email do usuário, o nome da nova pesquisa de conteúdo e a consulta de pesquisa a ser usada. O script Obtém a URL do OneDrive for Business para cada usuário na lista e, em seguida, cria e inicia uma pesquisa de conteúdo que pesquisa a caixa de correio e o site do OneDrive for Business para cada usuário na lista, usando a consulta de pesquisa que você fornece. 
  
## <a name="before-you-begin"></a>Antes de começar

- Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade & segurança e um administrador global do SharePoint Online para executar o script na etapa 3.
    
- Certifique-se de salvar a lista de usuários que você criou na etapa 2 e o script na etapa 3 para a mesma pasta. Isso facilitará a execução do script.
    
- O script inclui o tratamento de erros mínimo. O objetivo principal é Pesquisar rápida e facilmente a caixa de correio e o site do OneDrive for Business de cada usuário.
    
- Os scripts de exemplo fornecidos neste tópico não são suportados em nenhum programa ou serviço de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft se isenta de[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)todas as garantias mplied, incluindo, sem limitação, quaisquer garantias implícitas de comercialização ou ADEQÜAÇÃO para um propósito específico. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online

A primeira etapa é instalar o Shell de gerenciamento do SharePoint Online. Não é necessário usar o Shell neste procedimento, mas você precisa instalá-lo porque ele contém pré-requisitos necessários para o script executado na etapa 3. Esses pré-requisitos permitem que o script se comunique com o SharePoint Online para obter as URLs para os sites do OneDrive for Business.
  
Vá para [Configurar o ambiente do Windows PowerShell do Shell de gerenciamento do SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) e execute a etapa 1 e a etapa 2 para instalar o Shell de gerenciamento do SharePoint Online.
  
## <a name="step-2-generate-a-list-of-users"></a>Etapa 2: gerar uma lista de usuários

O script na etapa 3 criará uma pesquisa de conteúdo para pesquisar as caixas de correio e as contas do OneDrive para uma lista de usuários. Você pode simplesmente digitar os endereços de email em um arquivo de texto ou pode executar um comando no Windows PowerShell para obter uma lista de endereços de email e salvá-los em um arquivo (localizado na mesma pasta em que você salvará o script na etapa 3).
  
Este é um comando do [PowerShell do Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283) que você pode fazer com o Runt para obter uma lista de endereços de email para todos os usuários em sua organização e `Users.txt`salvá-lo em um arquivo de texto chamado. 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

Depois de executar esse comando, certifique-se de abrir o arquivo e remover o cabeçalho que contém o nome da `PrimarySmtpAddress`propriedade. O arquivo de texto deve conter apenas uma lista de endereços de email e nada mais. Certifique-se de que não haja linhas em branco antes ou depois da lista de endereços de email.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Etapa 3: executar o script para criar e iniciar a pesquisa

Quando você executar o script nesta etapa, ele solicitará as seguintes informações. Certifique-se de ter essas informações prontas antes de executar o script.
  
- **Suas credenciais de usuário** -o script usará suas credenciais para acessar o SharePoint Online para obter as URLs do onedrive for Business e se conectar ao centro de conformidade de & de segurança com o PowerShell remoto. 
    
- **Nome do seu domínio meusite** -o domínio MeuSite é o domínio que contém todos os sites do onedrive for Business em sua organização. Por exemplo, se a URL do seu domínio meusite for **https://contoso-my.sharepoint.com**, você deve inserir `contoso` quando o script solicitar o nome do seu domínio meusite. 
    
- **Nome do caminho do arquivo de texto da etapa 2** -o nome do caminho do arquivo de texto que você criou na etapa 2. Se o arquivo de texto e o script estiverem localizados na mesma pasta, insira o nome do arquivo de texto. Caso contrário, insira o nome de caminho completo para o arquivo de texto. 
    
- **Nome da pesquisa de conteúdo** -o nome da pesquisa de conteúdo que será criado pelo script. 
    
- **Consulta de pesquisa** -a consulta de pesquisa que será usada com a pesquisa de conteúdo é criada e executada. Para obter mais informações sobre consultas de pesquisa, consulte [keyword queries and Search Conditions for Content Search](keyword-queries-and-search-conditions.md).


**Para executar o script:**
    
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `SearchEXOOD4B.ps1`. Salve o arquivo na mesma pasta onde você salvou a lista de usuários na etapa 2.
    
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

2. Abra o Windows PowerShell e vá para a pasta onde você salvou o script e a lista de usuários da etapa 2.
    
3. Inicie o script; por exemplo:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. Quando solicitar suas credenciais, insira seu endereço de email e senha e clique em **OK**. 
    
5. Insira as informações a seguir quando solicitado pelo script. Digite cada informação e pressione **Enter**.
    
    - O nome do seu domínio meusite. 
    
    - O nome do caminho do arquivo de texto que contém a lista de usuários.
    
    - Um nome para a pesquisa de conteúdo.
    
    - A consulta de pesquisa (deixe em branco para retornar todos os itens nos locais de conteúdo).
    
    O script Obtém as URLs para cada site do OneDrive for Business e, em seguida, cria e inicia a pesquisa. Você pode executar o cmdlet **Get-ComplianceSearch** no PowerShell do centro de conformidade e segurança & para exibir as estatísticas de pesquisa e os resultados, ou pode ir para a página de **pesquisa de conteúdo** no centro de conformidade & de segurança para exibir informações sobre a pesquisa. 
