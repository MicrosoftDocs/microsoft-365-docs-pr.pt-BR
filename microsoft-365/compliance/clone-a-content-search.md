---
title: Clonar uma Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: Use o script do Windows PowerShell neste artigo para clonar rapidamente uma pesquisa de conteúdo existente no centro de conformidade no Office 365 ou no Microsoft 365. Quando você clona uma pesquisa, uma nova pesquisa (com um novo nome) é criada e contém as mesmas propriedades da pesquisa original. Em seguida, você pode editar a nova pesquisa alterando a palavra-chave de consulta ou o intervalo de datas e, em seguida, execute-a.
ms.openlocfilehash: 59fdaab7cf12bc0f5c4b08cbac1834803e5a8d98
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595878"
---
# <a name="clone-a-content-search"></a>Clonar uma Pesquisa de Conteúdo

Criar uma pesquisa de conteúdo no centro de conformidade no Office 365 ou Microsoft 365 que pesquisa muitas caixas de correio ou sites do OneDrive for Business pode levar algum tempo. A especificação dos sites a serem pesquisados também pode ser propensa a erros se você digitar indigitou uma URL. Para evitar esses problemas, você pode usar o script do Windows PowerShell neste artigo para clonar rapidamente uma pesquisa de conteúdo existente. Quando você clona uma pesquisa, uma nova pesquisa (com um nome diferente) é criada, contendo as mesmas propriedades (como os locais de conteúdo e a consulta de pesquisa) como a pesquisa original. Em seguida, você pode editar a nova pesquisa alterando a palavra-chave de consulta ou o intervalo de datas e executá-la.
  
Por que clonar pesquisas de conteúdo?
  
- Para comparar os resultados das diferentes consultas de pesquisa de palavras-chave executadas nos mesmos locais de conteúdo.
    
- Para evitar que você reinsira um grande número de locais de conteúdo ao criar uma nova pesquisa.
    
- Para diminuir o tamanho dos resultados da pesquisa. Por exemplo, se você tiver uma pesquisa que retorne muitos resultados para exportação, você pode clonar a pesquisa e, em seguida, adicionar um critério de pesquisa com base em um intervalo de datas para reduzir o número de resultados da pesquisa.
  
## <a name="before-you-begin"></a>Antes de começar

- Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade do & de segurança para executar o script descrito neste tópico.
    
- O script inclui o tratamento de erros mínimo. O objetivo principal do script é clonar rapidamente uma pesquisa de conteúdo.
    
- O script cria uma nova pesquisa de conteúdo, mas não a inicia.
    
- Esse script leva em consideração se a pesquisa de conteúdo que você está clonando está associada a um caso de descoberta eletrônica. Se a pesquisa estiver associada a uma ocorrência, a nova pesquisa também será associada ao mesmo caso. Se a pesquisa existente não estiver associada a uma ocorrência, a nova pesquisa será listada na página de **pesquisa de conteúdo** no centro de conformidade. 
    
- Não há suporte para o script de exemplo fornecido neste tópico em qualquer serviço ou programa de suporte padrão da Microsoft. O script de exemplo é fornecido como está sem garantia de qualquer tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todo o risco resultante do uso ou do desempenho do script de exemplo e da documentação permanece com você. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Etapa 1: executar o script para clonar uma pesquisa

O script nesta etapa criará uma nova pesquisa de conteúdo clonando uma existente. Ao executar esse script, você será solicitado a fornecer as seguintes informações:
  
- **Suas credenciais de usuário** -o script usará suas credenciais para se conectar ao centro de conformidade de & de segurança para sua organização do Office 365 com o Windows PowerShell. Conforme mencionado anteriormente, você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de segurança & compCompliance para executar o script. 
    
- **O nome da pesquisa existente** -esta é a pesquisa de conteúdo que você deseja clonar. 
    
- **O nome da nova pesquisa que será criada** -se você deixar esse valor em branco, o script criará um nome para a nova pesquisa, com base no nome da pesquisa que você está clonando. 
    
Para clonar uma pesquisa:
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `CloneSearch.ps1`.
    
  ```powershell
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. Abra o Windows PowerShell e vá para a pasta onde você salvou o script.
    
3. Executar o script; por exemplo:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. Quando solicitar suas credenciais, insira seu endereço de email e senha e clique em **OK**.
    
5. Insira as informações a seguir quando solicitado pelo script. Digite cada informação e pressione **Enter**.
    
    - O nome da pesquisa existente.
    
    - O nome da nova pesquisa.
    
    O script cria a nova pesquisa de conteúdo, mas não a inicia. Isso lhe dá a oportunidade de editar e executar a pesquisa na próxima etapa. Você pode exibir as propriedades da nova pesquisa executando o cmdlet **Get-ComplianceSearch** ou indo para a página de **pesquisa de conteúdo** ou **descoberta eletrônica** no centro de conformidade, dependendo se a nova pesquisa está associada a um caso. 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Etapa 2: editar e executar a pesquisa clonada no centro de conformidade

Depois de executar o script para clonar uma pesquisa de conteúdo existente, a próxima etapa é acessar o centro de conformidade para editar e executar a nova pesquisa. Conforme mencionado anteriormente, você pode editar uma pesquisa, alterando a consulta de pesquisa de palavra-chave e adicionando ou removendo condições de pesquisa. Para saber mais, confira:
  
- [Pesquisa de Conteúdo no Office 365](content-search.md)
    
- [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md)
    
- [ocorrências de descoberta eletrônica](ediscovery-cases.md)
