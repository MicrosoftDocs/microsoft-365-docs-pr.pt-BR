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
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Use a Pesquisa de Conteúdo para procurar uma lista de usuários na caixa de correio e no site do OneDrive for Business

O Centro de Conformidade & segurança fornece vários cmdlets Windows PowerShell que permitem automatizar tarefas relacionadas à Descoberta Eletrônica demorada. Atualmente, a criação de uma Pesquisa de Conteúdo no Centro de Conformidade & Segurança para pesquisar um grande número de locais de conteúdo custodiante leva tempo e preparação. Antes de criar uma pesquisa, você precisa coletar a URL para cada site OneDrive for Business e adicionar cada caixa de correio e OneDrive for Business site à pesquisa. Em versões futuras, isso será mais fácil de fazer no Centro de Conformidade & Segurança. Até lá, você pode usar o script neste artigo para automatizar esse processo. Este script solicita o nome do domínio MySite da sua organização (por exemplo, **contoso** na URL ), uma lista de endereços de email do usuário, o nome da nova Pesquisa de Conteúdo e a consulta de pesquisa a ser `https://contoso-my.sharepoint.com` usada. O script obtém a URL de OneDrive for Business para cada usuário na lista e, em seguida, cria e inicia uma Pesquisa de Conteúdo que pesquisa a caixa de correio e o site OneDrive for Business para cada usuário na lista, usando a consulta de pesquisa que você fornece.
  
## <a name="permissions-and-script-information"></a>Permissões e informações de script

- Você precisa ser membro do grupo de funções do Gerenciador de Descobertas Esdiscovery no Centro de Conformidade & Segurança e um administrador global do SharePoint Online para executar o script na Etapa 3.

- Salve a lista de usuários que você criar na Etapa 2 e o script na Etapa 3 na mesma pasta. Isso facilitará a executar o script.

- O script inclui tratamento mínimo de erros. Seu principal objetivo é pesquisar rapidamente e facilmente a caixa de correio e OneDrive for Business site de cada usuário.

- Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online

A primeira etapa é instalar o Shell de Gerenciamento SharePoint Online. Você não precisa usar o shell neste procedimento, mas precisa instalá-lo porque ele contém os pré-requisitos exigidos pelo script executado na Etapa 3. Esses pré-requisitos permitem que o script se comunique com o SharePoint Online para obter as URLs para os OneDrive for Business sites.
  
Vá para Configurar o ambiente SharePoint Shell de Gerenciamento [Online Windows PowerShell e](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) execute a Etapa 1 e a Etapa 2 para instalar o Shell de Gerenciamento SharePoint Online.
  
## <a name="step-2-generate-a-list-of-users"></a>Etapa 2: Gerar uma lista de usuários

O script na Etapa 3 criará uma Pesquisa de Conteúdo para pesquisar as caixas de correio e OneDrive contas de uma lista de usuários. Você pode digitar os endereços de email em um arquivo de texto ou executar um comando no Windows PowerShell para obter uma lista de endereços de email e salvá-los em um arquivo (localizado na mesma pasta para a qual você salvará o script na Etapa 3).
  
Aqui está um comando [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) que você pode executar para obter uma lista de endereços de email para todos os usuários em sua organização e salvá-lo em um arquivo de texto chamado `Users.txt` . 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

Depois de executar esse comando, certifique-se de abrir o arquivo e remover o header que contém o nome da propriedade,  `PrimarySmtpAddress` . O arquivo de texto deve conter apenas uma lista de endereços de email e nada mais. Certifique-se de que não haja linhas em branco antes ou após a lista de endereços de email.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Etapa 3: Executar o script para criar e iniciar a pesquisa

Quando você executar o script nesta etapa, ele solicitará as seguintes informações. Certifique-se de ter essas informações prontas antes de executar o script.
  
- **Suas** credenciais de usuário - O script usará suas credenciais para acessar o SharePoint Online para obter as URLs OneDrive for Business de OneDrive for Business e se conectar ao Centro de Conformidade & Segurança com o PowerShell remoto. 
    
- **Nome do seu domínio MySite** - O domínio MySite é o domínio que contém todos os OneDrive for Business de sua organização. Por exemplo, se a URL do seu domínio MySite for , você digitará quando o script solicitar o nome do **https://contoso-my.sharepoint.com**  `contoso` seu domínio MySite. 
    
- **Pathname do arquivo de texto** da Etapa 2 - O nome do caminho do arquivo de texto que você criou na Etapa 2. Se o arquivo de texto e o script estão localizados na mesma pasta, digite o nome do arquivo de texto. Caso contrário, insira o nome do caminho completo para o arquivo de texto. 
    
- **Nome da Pesquisa de Conteúdo** - O nome da Pesquisa de Conteúdo que será criada pelo script. 
    
- **Consulta de pesquisa** - A consulta de pesquisa que será usada com a Pesquisa de Conteúdo é criada e executado. Para obter mais informações sobre consultas de pesquisa, consulte [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).


**Para executar o script:**
    
1. Salve o texto a seguir em um arquivo Windows PowerShell script usando um sufixo de nome de arquivo de .ps1; por exemplo, `SearchEXOOD4B.ps1` . Salve o arquivo na mesma pasta em que você salvou a lista de usuários na Etapa 2.
    
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

2. Abra Windows PowerShell e vá para a pasta onde você salvou o script e a lista de usuários da Etapa 2.
    
3. Inicie o script; por exemplo:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. Quando solicitado para suas credenciais, insira seu endereço de email e senha e clique em **OK**. 
    
5. Insira as informações a seguir quando solicitado pelo script. Digite cada informação e pressione **Enter**.
    
    - O nome do seu domínio MySite. 
    
    - O nome do caminho do arquivo de texto que contém a lista de usuários.
    
    - Um nome para a Pesquisa de Conteúdo.
    
    - A consulta de pesquisa (deixe isso em branco para retornar todos os itens nos locais de conteúdo).
    
    O script obtém as URLs de cada site OneDrive for Business e cria e inicia a pesquisa. Você pode executar o cmd & let **Get-ComplianceSearch** no Centro de Conformidade e Segurança do PowerShell  para exibir as estatísticas e resultados da pesquisa ou pode ir para a página de pesquisa de conteúdo no Centro de Conformidade e Segurança & para exibir informações sobre a pesquisa.