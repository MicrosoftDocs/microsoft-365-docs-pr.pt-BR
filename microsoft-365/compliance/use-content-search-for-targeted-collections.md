---
title: Usar a Pesquisa de Conteúdo para determinadas coleções
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
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Use a pesquisa de conteúdo no centro de conformidade de & de segurança para realizar coleções direcionadas, que garantem que os itens estejam localizados em uma caixa de correio ou pasta de site específica.
ms.openlocfilehash: fb7f900e8deaef6946d1ed8ea109d42207a882b3
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819101"
---
# <a name="use-content-search-for-targeted-collections"></a>Usar a Pesquisa de Conteúdo para determinadas coleções

O recurso de pesquisa de conteúdo no &amp; centro de conformidade de segurança não fornece uma maneira direta na interface de usuário pesquisar pastas específicas em caixas de correio do Exchange ou sites do SharePoint e do onedrive for Business. No entanto, é possível pesquisar pastas específicas (chamadas de *coleção direcionadas*) especificando a propriedade ID da pasta para a propriedade email ou caminho (DocumentLink) para sites na sintaxe de consulta de pesquisa real. O uso da pesquisa de conteúdo para executar uma coleção direcionada é útil quando você tem certeza de que os itens que respondem a um caso ou itens privilegiados estão localizados em uma caixa de correio ou pasta de site específica. Você pode usar o script neste artigo para obter a ID de pasta para pastas de caixa de correio ou o caminho (DocumentLink) para pastas em um site do SharePoint e do OneDrive for Business. Em seguida, você pode usar a ID de pasta ou o caminho em uma consulta de pesquisa para retornar itens localizados na pasta.

> [!NOTE]
> Para retornar conteúdo localizado em uma pasta em um site do SharePoint ou do OneDrive for Business, o script neste tópico usa a propriedade gerenciada DocumentLink em vez da propriedade Path. A propriedade DocumentLink é mais robusta que a propriedade Path porque ela retornará todo o conteúdo de uma pasta, enquanto a propriedade Path não retornará alguns arquivos de mídia.

## <a name="before-you-use-content-search"></a>Antes de usar a pesquisa de conteúdo

- Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de &amp; conformidade de segurança para executar o script na etapa 1. Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).
    
    Além disso, você precisa receber a função de destinatários de email em sua organização do Exchange Online. Isso é necessário para executar o cmdlet **Get-MailboxFolderStatistics** , que está incluído no script na etapa 1. Por padrão, a função de destinatários de email é atribuída aos grupos de função de gerenciamento de organização e de gerenciamento de destinatários no Exchange Online. Para obter mais informações sobre como atribuir permissões no Exchange Online, consulte [Manage role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102). Você também pode criar um grupo de função personalizado, atribuir a ele a função de destinatários de email e, em seguida, adicionar os membros que precisam executar o script na etapa 1. Para obter mais informações, consulte [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).
    
- Cada vez que você executa o script na etapa 1, uma nova sessão remota do PowerShell é criada. Portanto, você pode usar todas as sessões remotas do PowerShell disponíveis para você. Para evitar que isso aconteça, você pode executar o seguinte comando para desconectar suas sessões do PowerShell remotos ativas.
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Para saber mais, confira [Conectar-se ao Exchange Online usando o PowerShell Remoto](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- O script inclui o tratamento de erros mínimo. O objetivo principal do script é exibir rapidamente uma lista de IDs de pasta de caixa de correio ou caminhos de site que podem ser usados na sintaxe de consulta de pesquisa de uma pesquisa de conteúdo para executar uma coleção direcionada.
    
- Não há suporte para o script de exemplo fornecido neste tópico em qualquer serviço ou programa de suporte padrão da Microsoft. O script de exemplo é fornecido como está sem garantia de qualquer tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todo o risco resultante do uso ou do desempenho do script de exemplo e da documentação permanece com você. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Etapa 1: executar o script para obter uma lista de pastas para uma caixa de correio ou site

O script executado nesta primeira etapa retornará uma lista de pastas de caixa de correio ou pastas do SharePoint e do OneDrive for Business e a ID de pasta ou o caminho correspondente de cada pasta. Quando você executar esse script, ele solicitará as seguintes informações.
  
- **Endereço de email ou URL do site** Digite um endereço de email do responsáveis para retornar uma lista de pastas de caixa de correio do Exchange e IDs de pasta. Ou digite a URL de um site do SharePoint ou do OneDrive for Business para retornar uma lista de caminhos para o site especificado. Aqui estão alguns exemplos: 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **Do** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **Suas credenciais de usuário** -o script usará suas credenciais para se conectar ao Exchange Online e ao centro de conformidade & segurança com o PowerShell remoto. Conforme explicado anteriormente, você precisa atribuir as permissões apropriadas para executar esse script com êxito.
    
Para exibir uma lista de pastas de caixa de correio ou nomes de site documentlink (caminho):
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `GetFolderSearchParameters.ps1` .
    
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
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  if ($addressOrSite.IndexOf("@") -ige 0)
  {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
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
      # Authenticate with the Security & Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
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

2. No computador local, abra o Windows PowerShell e vá para a pasta onde você salvou o script.
    
3. Executar o script; por exemplo:
    
      ```powershell
      .\GetFolderSearchParameters.ps1
      ```

4. Insira as informações que o script solicitará para você.
    
    O script exibe uma lista de pastas de caixa de correio ou pastas de site para o usuário especificado. Deixe essa janela aberta para que você possa copiar uma ID de pasta ou um nome de documentlink e colá-lo em uma consulta de pesquisa na etapa 2.
    
    > [!TIP]
    > Em vez de exibir uma lista de pastas na tela do computador, você pode redirecionar a saída do script para um arquivo de texto. Esse arquivo será salvo na pasta em que o script está localizado. Por exemplo, para redirecionar a saída do script para um arquivo de texto, execute o seguinte comando na etapa 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` depois você pode copiar uma ID de pasta ou documentlink do arquivo para usar em uma consulta de pesquisa.
  
### <a name="script-output-for-mailbox-folders"></a>Saída de script para pastas de caixa de correio

Se você estiver obtendo IDs de pasta de caixa de correio, o script se conecta ao Exchange Online usando o PowerShell remoto, executa o cmdlet **Get-MailboxFolderStatisics** e exibe a lista de pastas da caixa de correio especificada. Para cada pasta na caixa de correio, o script exibe o nome da pasta na coluna **FolderPath** e a ID da pasta na coluna **FolderQuery** . Além disso, o script adiciona o prefixo de **FolderId** (que é o nome da propriedade da caixa de correio) à ID da pasta. Como a propriedade **FolderId** é uma propriedade pesquisável, você usará `folderid:<folderid>` uma consulta de pesquisa na etapa 2 para pesquisar essa pasta. O script exibe um máximo de 100 pastas de caixa de correio.

> [!IMPORTANT]
> O script neste artigo inclui lógica de codificação que converte os valores de ID de pasta de 64 caracteres retornados pelo **Get-MailboxFolderStatistics** para o mesmo formato de caractere 48 que é indexado para pesquisa. Se você apenas executar o cmdlet **Get-MailboxFolderStatistics** no PowerShell para obter uma ID de pasta (em vez de executar o script neste artigo), uma consulta de pesquisa que usa esse valor de ID de pasta falhará. Você precisa executar o script para obter as IDs de pasta formatadas corretamente que podem ser usadas em uma pesquisa de conteúdo.
  
Veja um exemplo de saída retornada pelo script para pastas de caixa de correio.
  
![Exemplo da lista de pastas de caixa de correio e IDs de pasta retornada pelo script](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
O exemplo na etapa 2 mostra a consulta usada para pesquisar a subpasta de limpezas na pasta itens recuperáveis do usuário.
  
### <a name="script-output-for-site-folders"></a>Saída de script para pastas de site

Se você estiver obtendo o caminho da propriedade **documentlink** de sites do SharePoint ou do onedrive for Business, o script se conecta ao centro de conformidade de & de segurança usando o PowerShell remoto, cria uma nova pesquisa de conteúdo que pesquisa o site para pastas e, em seguida, exibe uma lista das pastas localizadas no site especificado. O script exibe o nome de cada pasta e adiciona o prefixo de **documentlink** à URL da pasta. Como a propriedade **documentlink** é uma propriedade pesquisável, você usará o `documentlink:<path>` par propriedade: valor em uma consulta de pesquisa na etapa 2 para pesquisar essa pasta. O script exibe um máximo de 200 pastas de site. Se houver mais de 200 pastas de site, as mais recentes serão exibidas.
  
Veja um exemplo de saída retornada pelo script para pastas de site.
  
![Exemplo da lista de nomes de documentlink para pastas de site retornadas pelo script](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Etapa 2: usar uma ID de pasta ou documentlink para executar uma coleção direcionada

Após executar o script para coletar uma lista de IDs de pasta ou documentlinks para um usuário específico, a próxima etapa para acessar o centro de conformidade de & de segurança e criar uma nova pesquisa de conteúdo para pesquisar uma pasta específica. Você usará o `folderid:<folderid>` `documentlink:<path>` par propriedade ou: valor na consulta de pesquisa que você configurou na caixa palavra-chave de pesquisa de conteúdo (ou como o valor para o parâmetro *ContentMatchQuery* se você usar o cmdlet **New-ComplianceSearch** ). Você pode combinar a `folderid` `documentlink` propriedade ou com outros parâmetros de pesquisa ou condições de pesquisa. Se você incluir apenas a `folderid` `documentlink` propriedade ou na consulta, a pesquisa retornará todos os itens localizados na pasta especificada. 
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre usando a conta e as credenciais que você usou para executar o script na etapa 1.
    
3. No painel esquerdo do centro de conformidade & segurança, clique em **Search** \> **pesquisa de conteúdo**de pesquisa e clique em **novo** ![ ícone de adição ](../media/O365-MDM-CreatePolicy-AddIcon.gif) .
    
4. Na página **Nova pesquisa**, digite um nome para a Pesquisa de Conteúdo. O nome deve ser exclusivo em sua organização. 
    
5. Em **onde você deseja procurar**, faça um dos seguintes, dependendo de como você está pesquisando uma pasta de caixa de correio ou uma pasta de site:
    
    - Clique em **escolher caixas de correio específicas para pesquisar** e, em seguida, adicione a mesma caixa de correio que você especificou ao executar o script na etapa 1. 
    
      Ou
    
    - Clique em **escolher sites específicos para pesquisar** e, em seguida, adicione a URL do site que você especificou ao executar o script na etapa 1. 
    
6. Clique em **Avançar**.
    
7. Na caixa palavra-chave da página **o que você deseja procurar** , Cole o `folderid:<folderid>` ou o `documentlink:<path>` valor retornado pelo script na etapa 1. 
    
    Por exemplo, a consulta na captura de tela a seguir pesquisará qualquer item na subpasta de limpezas na pasta itens recuperáveis do usuário (o valor da `folderid` propriedade da subpasta de limpezas é mostrado na captura de tela na etapa 1):
    
    ![Cole o FolderId ou documentlink na caixa palavra-chave da consulta de pesquisa](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. Clique em **Pesquisar** para iniciar a pesquisa de coleção direcionada. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Exemplos de consultas de pesquisa para coleções direcionadas

Aqui estão alguns exemplos de como usar `folderid` as `documentlink` Propriedades e em uma consulta de pesquisa para executar uma coleção direcionada. Observe que os espaços reservados são usados para o `folderid:<folderid>` e `documentlink:<path>` economizar espaço. 
  
- Este exemplo pesquisa três pastas de caixa de correio diferentes. Você pode usar sintaxe de consulta semelhante para pesquisar as pastas ocultas em uma pasta de itens recuperáveis de um usuário.
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- Este exemplo procura em uma pasta de caixa de correio itens que contenham uma frase exata.
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- Este exemplo pesquisa uma pasta de site (e todas as subpastas) para documentos que contenham as letras "NDA" no título.
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- Este exemplo pesquisa uma pasta de site (e qualquer subpasta) para documentos que foram alterados em um intervalo de datas.
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Mais informações

Tenha em mente os seguintes pontos ao usar o script neste artigo para executar coleções direcionadas.
  
- O script não remove nenhuma pasta dos resultados. Portanto, algumas pastas listadas nos resultados podem não ser pesquisadas (ou retornar itens de zero) porque contêm conteúdo gerado pelo sistema.
    
- Este script retorna apenas as informações da pasta da caixa de correio principal do usuário. Ele não retorna informações sobre pastas na caixa de correio de arquivo morto do usuário.
    
- Ao pesquisar pastas de caixa de correio, somente a pasta especificada (identificada por sua `folderid` Propriedade) será pesquisada; as subpastas não serão pesquisadas. Para pesquisar subpastas, você precisa usar a ID de pasta para a subpasta que você deseja pesquisar. 
    
- Ao pesquisar pastas de site, a pasta (identificado por sua `documentlink` Propriedade) e todas as subpastas serão pesquisadas. 
    
- Ao exportar os resultados de uma pesquisa na qual você só especificou a `folderid` Propriedade na consulta de pesquisa, você pode escolher a primeira opção de exportação, "todos os itens, exceto aqueles que têm um formato não reconhecido, são criptografados ou não foram indexados por outros motivos". Todos os itens na pasta sempre serão exportados, independentemente do status de indexação, porque a ID da pasta é sempre indexada.
