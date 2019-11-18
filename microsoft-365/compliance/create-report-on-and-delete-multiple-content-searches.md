---
title: Criar, gerar relatórios sobre e excluir várias Pesquisas de Conteúdo
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Saiba como automatizar tarefas de pesquisa de conteúdo, como a criação de pesquisas e a execução de relatórios por meio de scripts do PowerShell no centro de conformidade de & de segurança no Office 365.
ms.openlocfilehash: 43f6046521ef121f52b2a5abe26d2cd6a322d22c
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38684983"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>Criar, gerar relatórios sobre e excluir várias Pesquisas de Conteúdo

 Criar e relatar rapidamente pesquisas de descoberta é geralmente uma etapa importante na descoberta eletrônica e investigações quando você está tentando saber mais sobre os dados subjacentes, e a riqueza e a qualidade das pesquisas. Para ajudá-lo a fazer isso, o PowerShell do centro de conformidade e segurança & oferece um conjunto de cmdlets para automatizar tarefas de pesquisa de conteúdo demoradas. Esses scripts fornecem uma maneira rápida e fácil de criar várias pesquisas e, em seguida, executar relatórios dos resultados estimados da pesquisa que podem ajudá-lo a determinar a quantidade de dados em questão. Você também pode usar os scripts para criar versões diferentes de pesquisas para comparar os resultados que cada um produz. Esses scripts podem ajudá-lo a identificar e analisar os dados de forma rápida e eficiente. 
  
## <a name="before-you-begin"></a>Antes de começar

- Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade do & de segurança para executar os scripts descritos neste tópico. 
    
- Para coletar uma lista das URLs para os sites do OneDrive for Business em sua organização que você pode adicionar ao arquivo CSV na etapa 1, consulte [criar uma lista de todos os locais do onedrive em sua organização](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a). 
    
- Certifique-se de salvar todos os arquivos que você criou neste tópico para a mesma pasta. Isso facilitará a execução dos scripts.
    
- Os scripts incluem um tratamento de erros mínimo. Seu objetivo principal é criar, relatar e excluir rapidamente várias pesquisas de conteúdo.
    
- Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>Etapa 1: criar um arquivo CSV que contenha informações sobre as pesquisas que você deseja executar

O arquivo de valor separado por vírgula (CSV) que você criou nesta etapa contém uma linha para cada usuário que deseja pesquisar. Você pode pesquisar a caixa de correio do Exchange Online do usuário (que inclui a caixa de correio de arquivo morto, se ela estiver habilitada) e seu site do OneDrive for Business. Ou você pode pesquisar apenas a caixa de correio ou o site do OneDrive for Business. Você também pode pesquisar qualquer site em sua organização do SharePoint Online. O script executado na etapa 3 criará uma pesquisa separada para cada linha no arquivo CSV. 
  
1. Copie e cole o texto a seguir em um arquivo. txt usando o bloco de notas. Salve esse arquivo em uma pasta no computador local. Você também salvará outros scripts nessa pasta.
    
    ```text
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    A primeira linha, ou linha de cabeçalho, do arquivo lista os parâmetros que serão usados pelo cmdlet **New-ComplianceSearch** (no script na etapa 3) para criar novas pesquisas de conteúdo. Os nomes dos parâmetros são separados por vírgula. Certifique-se de que não haja espaços na linha de cabeçalho. Cada linha sob a linha de cabeçalho representa os valores de parâmetro de cada pesquisa. Certifique-se de substituir os dados de espaço reservado no arquivo CSV pelos dados reais. 
    
2. Abra o arquivo. txt no Excel e use as informações da tabela a seguir para editar o arquivo com as informações de cada pesquisa. 
    
    |**Parâmetro**|**Description**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |O endereço SMTP da caixa de correio do usuário.  <br/> |
    | `SharePointLocation` <br/> |A URL do site do OneDrive for Business do usuário ou a URL de qualquer site em sua organização. Para a URL dos sites do OneDrive for Business, use este formato ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `:. Por exemplo, `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.  <br/> |
    | `ContentMatchQuery` <br/> |A consulta de pesquisa para a pesquisa. Para obter mais informações sobre como criar uma consulta de pesquisa, consulte [keyword queries and Search Conditions for Content Search](keyword-queries-and-search-conditions.md).  <br/> |
    | `StartDate` <br/> |Para email, a data de ou após uma mensagem foi recebida por um destinatário ou enviada pelo remetente. Para documentos em sites do SharePoint ou do OneDrive for Business, a data da última modificação de um documento.  <br/> |
    | `EndDate` <br/> |Para email, a data de ou antes de uma mensagem foi enviada por um enviado pelo usuário. Para documentos em sites do SharePoint ou do OneDrive for Business, a data em ou antes da última modificação de um documento.  <br/> |
   
3. Salve o arquivo do Excel como um arquivo CSV em uma pasta no computador local. O script criado na etapa 3 usará as informações neste arquivo CSV para criar as pesquisas. 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Etapa 2: conectar-se ao PowerShell do centro de conformidade & segurança

A próxima etapa é conectar-se ao PowerShell do centro de conformidade & segurança para sua organização.
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `ConnectSCC.ps1`. Salve o arquivo na mesma pasta em que você salvou o arquivo CSV na etapa 1.
    
    ```powershell
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. No computador local, abra o Windows PowerShell, vá para a pasta onde o script criado na etapa anterior está localizado e, em seguida, execute o script; por exemplo:
    
    ```powershell
    .\ConnectSCC.ps1
    ```

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>Etapa 3: executar o script para criar e iniciar as pesquisas

O script nesta etapa criará uma pesquisa de conteúdo separada para cada linha no arquivo CSV que você criou na etapa 1. Ao executar esse script, você será solicitado a fornecer dois valores:
  
- **ID do grupo de pesquisa** -este nome oferece uma maneira fácil de organizar as pesquisas criadas a partir do arquivo CSV. Cada pesquisa criada é nomeada com a ID do grupo de pesquisa e, em seguida, um número é acrescentado ao nome da pesquisa. Por exemplo, se você inserir **ContosoCase** para a ID do grupo de pesquisa, as pesquisas serão nomeadas **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**e assim por diante. Observe que o nome digitado diferencia maiúsculas de minúsculas. Quando você usa a ID do grupo de pesquisa na etapa 4 e a etapa 5, é necessário usar o mesmo caso que você fez ao criá-la. 
    
- **Arquivo CSV** -o nome do arquivo CSV que você criou na etapa 1. Certifique-se de incluir o uso do nome de arquivo completo, inclua a extensão de arquivo. csv; por exemplo, `ContosoCase.csv`.
    
Para executar o script:

1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `CreateSearches.ps1`. Salve o arquivo na mesma pasta onde você salvou os outros arquivos.
    
  ```Powershell
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. No Windows PowerShell, vá para a pasta onde você salvou o script na etapa anterior e execute o script; por exemplo:
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. No prompt **ID do grupo de pesquisa** , digite um nome de grupo de pesquisa e pressione **Enter**. por exemplo, `ContosoCase`. Lembre-se de que esse nome diferencia maiúsculas de minúsculas, portanto, você terá que digitá-lo da mesma maneira nas etapas subsequentes.
    
4. No prompt de **arquivo CSV de origem** , digite o nome do arquivo CSV, incluindo a extensão de arquivo. csv; por exemplo, `ContosoCase.csv`.
    
5. Pressione **Enter** para continuar executando o script. 
    
    O script exibe o progresso da criação e execução das pesquisas. Quando o script é concluído, ele retorna ao prompt. 
    
    ![Exemplo de saída da execução do script para criar várias pesquisas de conformidade](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>Etapa 4: executar o script para relatar as estimativas de pesquisa

Após criar as pesquisas, a próxima etapa é executar um script que exibe um relatório simples do número de visitas de pesquisa para cada pesquisa criada na etapa 3. O relatório também inclui o tamanho dos resultados de cada pesquisa e o número total de acertos e o tamanho total de todas as pesquisas. Ao executar o script de relatório, você será solicitado a solicitar o ID do grupo de pesquisa e um nome de arquivo CSV se quiser salvar o relatório em um arquivo CSV.
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `SearchReport.ps1`. Salve o arquivo na mesma pasta onde você salvou os outros arquivos.
    
  ```Powershell
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. No Windows PowerShell, vá para a pasta onde você salvou o script na etapa anterior e execute o script; por exemplo:
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. No prompt **ID do grupo de pesquisa** , digite um nome de grupo de pesquisa e pressione **Enter**. por exemplo `ContosoCase`. Lembre-se de que esse nome diferencia maiúsculas de minúsculas, portanto, você terá que digitá-la da mesma maneira que fez ao executar o script na etapa 3.
    
4. No **caminho do arquivo para salvar o relatório em um arquivo CSV (deixe em branco para exibir o relatório)** , digite um nome de arquivo completo para o caminho de arquivo (incluindo a extensão de arquivo. csv) se quiser salvar o relatório em um arquivo CSV. nome do arquivo CSV, incluindo a extensão de arquivo. csv. Por exemplo, você poderia digitar `ContosoCaseReport.csv` para salvá-lo no diretório atual ou poderia digitar `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` para salvá-lo em uma pasta diferente. Você também pode deixar o prompt em branco para exibir o relatório, mas não salvá-lo em um arquivo. 
    
5. Pressione **Enter**.
    
    O script exibe o progresso da criação e execução das pesquisas. Quando o script estiver concluído, o relatório será exibido. 
    
    ![Executar o relatório de pesquisa para exibir as estimativas para o grupo de pesquisa](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> Se a mesma caixa de correio ou site for especificado como um local de conteúdo em mais de uma pesquisa em um grupo de pesquisa, a estimativa de resultados total no relatório (para o número de itens e o tamanho total) poderá incluir resultados para os mesmos itens. Isso ocorre porque o mesmo documento ou mensagem de email será contado mais de uma vez se corresponder à consulta de pesquisas diferentes no grupo de pesquisa. 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>Etapa 5: executar o script para excluir as pesquisas

Como você pode estar criando muitas pesquisas, esse último script simplesmente facilita a exclusão rápida das pesquisas que você criou na etapa 3. Assim como os outros scripts, isso também solicita a ID do grupo de pesquisa. Todas as pesquisas com a ID do grupo de pesquisa no nome da pesquisa serão excluídas quando você executar esse script. 
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `DeleteSearches.ps1`. Salve o arquivo na mesma pasta onde você salvou os outros arquivos.
    
  ```Powershell
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. No Windows PowerShell, vá para a pasta onde você salvou o script na etapa anterior e execute o script; por exemplo:
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. No prompt **ID do grupo de pesquisa** , digite um nome de grupo de pesquisa para as pesquisas que você deseja excluir e pressione **Enter**. por exemplo, `ContosoCase`. Lembre-se de que esse nome diferencia maiúsculas de minúsculas, portanto, você terá que digitá-la da mesma maneira que fez ao executar o script na etapa 3.
    
    O script exibe o nome de cada pesquisa que foi excluída.
    
    ![Executar o script para excluir as pesquisas no grupo de pesquisa](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
