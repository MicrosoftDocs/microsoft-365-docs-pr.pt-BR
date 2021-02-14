---
title: Clonar uma Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Use o script do PowerShell neste artigo para clonar rapidamente uma Pesquisa de Conteúdo existente no centro de conformidade no Office 365 ou no Microsoft 365.
ms.openlocfilehash: 9bc9329d31ae27736bdcd399c555f5d70bb9c761
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357899"
---
# <a name="clone-a-content-search"></a>Clonar uma Pesquisa de Conteúdo

Criar uma Pesquisa de Conteúdo no centro de conformidade do Office 365 ou do Microsoft 365 que pesquisa muitas caixas de correio ou sites do SharePoint e do OneDrive for Business pode demorar um pouco. Especificar os sites a serem pesquisados também pode ser suscetível a erros se você usar uma URL de forma insu mesmo. Para evitar esses problemas, você pode usar o script do Windows PowerShell neste artigo para clonar rapidamente uma Pesquisa de Conteúdo existente. Quando você clona uma pesquisa, é criada uma nova pesquisa (com um nome diferente) que contém as mesmas propriedades (como os locais de conteúdo e a consulta de pesquisa) da pesquisa original. Em seguida, você pode editar a nova pesquisa alterando a consulta de palavra-chave ou o intervalo de datas e execute-a.
  
Por que clonar Pesquisas de Conteúdo?
  
- Para comparar os resultados de diferentes consultas de pesquisa de palavra-chave, execute nos mesmos locais de conteúdo.
    
- Para salvá-lo de ter que reinserer um grande número de locais de conteúdo ao criar uma nova pesquisa.
    
- Para diminuir o tamanho dos resultados da pesquisa. Por exemplo, se você tiver uma pesquisa que retorna muitos resultados para exportar, poderá clonar a pesquisa e adicionar uma condição de pesquisa com base em um intervalo de datas para reduzir o número de resultados da pesquisa.
  
## <a name="script-information"></a>Informações de script

- Você precisa ser um membro do grupo de funções Gerente de Descobertas eDiscovery no Centro de Conformidade e Segurança & para executar o script descrito neste tópico.
    
- O script inclui tratamento mínimo de erros. O principal objetivo do script é clonar rapidamente uma pesquisa de conteúdo.
    
- O script cria uma nova Pesquisa de Conteúdo, mas não a inicia.
    
- Esse script leva em conta se a Pesquisa de Conteúdo que você está clonando está associada a um caso de Descoberta eDiscovery. Se a pesquisa estiver associada a uma ocorrência, a nova pesquisa também será associada ao mesmo caso. Se a pesquisa existente não estiver associada a uma ocorrência, a  nova pesquisa será listada na página Pesquisa de conteúdo no centro de conformidade. 
    
- O script de exemplo fornecido neste tópico não tem suporte em nenhum serviço ou programa de suporte padrão da Microsoft. O script de amostra é fornecido COMO ESTÁ, sem garantia de nenhum tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo, sem limitação, quaisquer garantias implícitas de comercialização ou adequação a uma finalidade específica. Todo o risco decorrente do uso ou desempenho do script de amostra e da documentação permanece com você. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Etapa 1: Executar o script para clonar uma pesquisa

O script nesta etapa criará uma nova Pesquisa de Conteúdo clonando uma existente. Ao executar esse script, você será solicitado a obter as seguintes informações:
  
- **Suas credenciais de usuário** – o script usará suas credenciais para se conectar ao Centro de Conformidade e Segurança da & da sua organização com o Windows PowerShell. Conforme mencionado anteriormente, você precisa ser um membro do grupo de função gerente de descoberta de ediscovery no Centro de & de segurança para executar o script. 
    
- **O nome da pesquisa existente** - Esta é a Pesquisa de Conteúdo que você deseja clonar. 
    
- O nome da nova pesquisa que será **criada-** Se você deixar esse valor em branco, o script criará um nome para a nova pesquisa com base no nome da pesquisa que você está clonando. 
    
Para clonar uma pesquisa:
  
1. Salve o texto a seguir em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo .ps1; por exemplo, `CloneSearch.ps1` .
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
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
    
3. Execute o script; por exemplo:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. Quando solicitado a inserir suas credenciais, insira seu endereço de email e senha e clique em **OK.**
    
5. Insira as informações a seguir quando solicitado pelo script. Digite cada informação e pressione **Enter.**
    
    - O nome da pesquisa existente.
    
    - O nome da nova pesquisa.
    
    O script cria a nova Pesquisa de Conteúdo, mas não a inicia. Isso dá a você a oportunidade de editar e executar a pesquisa na próxima etapa. Você pode exibir as propriedades da nova pesquisa executando o cmdlet **Get-ComplianceSearch** ou indo para a página Pesquisa de Conteúdo ou Descoberta Eletrônica no centro de conformidade, dependendo se a nova pesquisa está associada a uma ocorrência.   
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Etapa 2: Editar e executar a pesquisa clonada no centro de conformidade

Depois de executar o script para clonar uma Pesquisa de Conteúdo existente, a próxima etapa é ir para o centro de conformidade para editar e executar a nova pesquisa. Conforme mencionado anteriormente, você pode editar uma pesquisa alterando a consulta de pesquisa de palavra-chave e adicionando ou removendo condições de pesquisa. Para saber mais, confira:
  
- [Pesquisa de Conteúdo no Office 365](content-search.md)
    
- [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md)
    
- [Casos de Descoberta eDiscovery](ediscovery-cases.md)
