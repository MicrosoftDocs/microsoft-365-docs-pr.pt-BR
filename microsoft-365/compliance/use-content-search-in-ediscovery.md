---
title: Usar a pesquisa de conteúdo no seu fluxo de trabalho de descoberta eletrônica
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'Use um script do PowerShell para criar uma pesquisa de descoberta eletrônica in-loco no Exchange Online com base em uma pesquisa criada no centro de conformidade do & de segurança. '
ms.openlocfilehash: f3d5eb76dfa91334bccae42e0ddb66a71f739a6f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073057"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>Usar a Pesquisa de Conteúdo no seu fluxo de trabalho de descoberta eletrônica

O recurso de pesquisa de conteúdo no centro de conformidade & segurança permite pesquisar todas as caixas de correio em sua organização. Ao contrário da descoberta eletrônica in-loco no Exchange Online (onde você pode pesquisar até 10.000 caixas de correio), não há limites para o número de caixas de correio de destino em uma única pesquisa. Para cenários que exigem a execução de pesquisas em toda a organização, você pode usar a Pesquisa de Conteúdo para pesquisar todas as caixas de correio. Em seguida, você pode usar os recursos de fluxo de trabalho de descoberta eletrônica in-loco para realizar outras tarefas relacionadas à descoberta eletrônica, como colocar caixas de correio em espera e exportar resultados de pesquisa. Por exemplo, vamos supor que você precise pesquisar todas as caixas de correio para identificar os responsáveis específicos por um caso jurídico. Você pode usar a pesquisa de conteúdo no centro de conformidade de & de segurança para pesquisar todas as caixas de correio em sua organização para identificar as que estão respondendo ao caso. Em seguida, você pode usar essa lista de caixas de correio de responsáveis como caixas de correio de origem para uma pesquisa de descoberta eletrônica in-loco no Exchange Online. O uso da descoberta eletrônica in-loco também permite que você coloque uma retenção nas caixas de correio de origem, copie os resultados da pesquisa para uma caixa de correio de descoberta e exporte os resultados da pesquisa.
  
Este tópico inclui um script que você pode executar para criar uma pesquisa de descoberta eletrônica in-loco no Exchange Online usando a lista de caixas de correio de origem e consulta de pesquisa de uma pesquisa criada no centro de conformidade de segurança &. Esta é uma visão geral do processo:
  
[Etapa 1: Criar uma Pesquisa de Conteúdo para pesquisar todas as caixas de correio em sua organização](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[Etapa 2: conectar-se ao \& centro de conformidade de segurança e ao Exchange Online em uma única sessão remota do PowerShell](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[Etapa 3: Execute o script para criar uma pesquisa de Descoberta Eletrônica In-loco na Pesquisa de Conteúdo](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[Step 4: Start the In-Place eDiscovery search](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>Etapa 1: Criar uma Pesquisa de Conteúdo para pesquisar todas as caixas de correio em sua organização

A primeira etapa é usar o centro de conformidade de & de segurança (ou o PowerShell de segurança & do centro de conformidade) para criar uma pesquisa de conteúdo que pesquise todas as caixas de correio em sua organização. Não há qualquer limite para o número de caixas de correio em uma única pesquisa de conteúdo. Especifica uma consulta de palavra-chave apropriada (ou uma consulta de tipos de informações confidenciais) para que a pesquisa retorne apenas as caixas de correio de origem relevantes para a investigação. Se for necessário, refine a consulta de pesquisa para restringir o escopo dos resultados da pesquisa e as caixas de correio de origem retornadas.
  
> [!NOTE]
> Se a pesquisa de conteúdo de origem não retornar qualquer resultado, a Descoberta Eletrônica In-loco não será criada quando você executar o script na Etapa 3. Talvez seja necessário revisar a consulta de pesquisa e executar novamente a pesquisa de conteúdo para retornar os resultados de pesquisa. 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a>Usar o Centro de Conformidade e Segurança para pesquisar todas as caixas de correio

1. [Vá para o centro de conformidade & segurança](go-to-the-securitycompliance-center.md). 
    
2. Clique em**pesquisa de conteúdo**de **pesquisa** > e clique em novo ícone](media/O365-MDM-CreatePolicy-AddIcon.gif)de adição de **pesquisa** ![.
    
3. Na página **Nova pesquisa**, digite um nome para a pesquisa de conteúdo. 
    
4. Em **Onde você deseja que procuremos?**, clique em **Pesquisar todas as caixas de correio** e clique em **Avançar**.
    
5. Na caixa sob o **que você deseja que procuremos?**, digite uma consulta de pesquisa na caixa. Você pode especificar palavras-chave, propriedades de mensagem, como datas de envio e recebimento, ou propriedades de documento, como nomes de arquivo ou a data em que um documento foi alterado pela última vez. Você pode usar consultas mais complexas que usam um operador Boolean, como e, ou, não ou NEAR, ou também pode pesquisar informações confidenciais (como números de seguridade social) em mensagens. Para obter mais informações sobre a criação de consultas de pesquisa, consulte [keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
6. Clique em **Pesquisar** para salvar as configurações da pesquisa e iniciá-la. 
    
    Após um tempo, uma estimativa dos resultados da pesquisa são exibidos no painel de detalhes. A estimativa inclui o tamanho total e o número de itens dos resultados da pesquisa. Após a conclusão da pesquisa, você poderá visualizar os resultados. Se necessário, clique em **Atualizar**![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar as informações no painel de detalhes. 
    
7.  Se for necessário, refine a consulta de pesquisa para restringir o escopo dos resultados da pesquisa e reinicie a pesquisa. 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>Usar o centro de conformidade & o PowerShell para pesquisar todas as caixas de correio

Você também pode usar o cmdlet **New-ComplianceSearch** para pesquisar em todas as caixas de correio em sua organização. A primeira etapa é [conectar-se ao PowerShell do centro de conformidade & segurança](https://go.microsoft.com/fwlink/p/?LinkID=627084).
  
Veja um exemplo de como usar o PowerShell para pesquisar todas as caixas de correio em sua organização. A consulta de pesquisa retorna todas as mensagens enviadas entre 1º de janeiro de 2015 e 30 de junho de 2015 e que contenham a frase "relatório financeiro" na linha de assunto. O primeiro comando cria a pesquisa e o segundo comando executa a pesquisa. 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

Para obter mais informações, consulte [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>Verifique o número de caixas de correio de origem na pesquisa de conteúdo

Uma pesquisa de conteúdo retorna um máximo de 1.000 caixas de correio de origem que contêm resultados de pesquisa. Se houver mais de 1.000 caixas de correio que contenham conteúdo que corresponda à consulta de pesquisa, somente as primeiras caixas de correio de 1.000 com a maioria dos resultados de pesquisa serão incluídas na pesquisa de conteúdo que você criou na etapa anterior. Portanto, se mais de 1.000 caixas de correio contiverem resultados de pesquisa, algumas dessas caixas de correio não serão incluídas na lista de caixas de correio de origem copiadas para a nova pesquisa de descoberta eletrônica in-loco criada na etapa 3. 
  
Para ajudá-lo a criar uma pesquisa de conteúdo com mais de 1.000 caixas de correio de origem, siga estas etapas para executar um script que exibe o número de caixas de correio de origem (que contêm resultados de pesquisa) retornado pela pesquisa de conteúdo que você criou na etapa 1. 
  
1. Salve o seguinte texto em um arquivo de script do PowerShell usando um sufixo de nome de arquivo. ps1. Por exemplo, você pode salvá-lo em um arquivo `SourceMailboxes.ps1`chamado.
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. Em segurança & centro de conformidade do PowerShell, vá para a pasta onde o script criado na etapa anterior está localizado e, em seguida, execute o script; por exemplo:
    
    ```
    .\SourceMailboxes.ps1
    ```

3. Quando receber a solicitação pelo script, digite o nome da pesquisa de conteúdo criada na Etapa 1.
    
    O script exibe o número de caixas de correio de origem que contêm os resultados de pesquisa.
    
Se houver mais de 1.000 caixas de correio de origem, tente criar duas (ou mais) pesquisas de conteúdo. Por exemplo, pesquise metade das caixas de correio da organização em uma pesquisa de conteúdo, e a outra metade em outra pesquisa de conteúdo. Você também pode alterar os critérios de pesquisa para reduzir o número de caixas de correio que contêm os resultados de pesquisa. Por exemplo, você pode incluir um intervalo de datas ou refinar a consulta de palavra-chave.
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Etapa 2: conectar-se ao \& centro de conformidade de segurança e ao Exchange Online em uma única sessão remota do PowerShell

A próxima etapa é conectar o Windows PowerShell ao centro de conformidade de & de segurança e à sua organização do Exchange Online. Isso é necessário porque o script executado na etapa 3 requer acesso aos cmdlets de pesquisa de conteúdo no centro de conformidade e segurança & e nos cmdlets de descoberta eletrônica in-loco no Exchange Online.
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1. Por exemplo, você pode salvá-lo em um arquivo `ConnectEXO-CC.ps1`chamado.
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. No computador local, abra o Windows PowerShell, vá para a pasta onde o script criado na etapa anterior está localizado e, em seguida, execute o script; por exemplo:
    
    ```
    .\ConnectEXO-CC.ps1
    ```

Como saber se funcionou? Depois de executar o script, os cmdlets do centro de conformidade & segurança e do Exchange Online são importados para sua sessão local do PowerShell. Se nenhum erro aparecer, a conexão terá sido estabelecida. Um teste rápido é executar um cmdlet de segurança & o centro de conformidade — por exemplo, **install-UnifiedCompliancePrerequisite** — e um cmdlet do Exchange Online, como o **Get-Mailbox**. 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>Etapa 3: Execute o script para criar uma pesquisa de Descoberta Eletrônica In-loco na Pesquisa de Conteúdo

Depois de criar a sessão de dois PowerShell na etapa 2, a próxima etapa é executar um script que converta uma pesquisa de conteúdo existente em uma pesquisa de descoberta eletrônica in-loco. Veja a seguir o que o script faz:
  
- Solicita o nome da pesquisa de conteúdo para a conversão.
    
- Verifica se a pesquisa de conteúdo foi concluída. Se a pesquisa de conteúdo não retornar resultados, e a Descoberta Eletrônica In-loco não for criada.
    
- Salva uma lista das caixas de correio de origem da pesquisa de conteúdo que contêm os resultados de pesquisa para uma variável.
    
- Cria uma nova pesquisa de Descoberta Eletrônica In-loco, com as seguintes propriedades. Observe que a nova pesquisa não foi iniciada. Você poderá iniciá-la na Etapa 4.
    
  - **Name** -o nome da nova pesquisa usa este formato: \<nome da pesquisa\>de conteúdo _MBSearch1. Se você executar o script novamente e usar a mesma pesquisa de conteúdo de origem, a pesquisa será \<nomeada como nome de\>pesquisa de conteúdo _MBSearch2.
    
  - **Caixas de correio de origem** -todas as caixas de correio da pesquisa de conteúdo que contêm resultados de pesquisa. 
    
  - **Consulta de pesquisa** – a nova pesquisa usa a consulta de pesquisa da pesquisa de conteúdo. Se a pesquisa de conteúdo incluir todo o conteúdo (quando a consulta de pesquisa estiver em branco), a nova pesquisa também terá uma consulta de pesquisa em branco e incluirá todo o conteúdo encontrado nas caixas de correio de origem. 
    
  - **Estimar somente pesquisa** – a nova pesquisa está marcada como uma pesquisa somente estimada. Ela não copiará resultados da pesquisa para uma caixa de correio de descoberta depois de iniciá-la. 
    
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo ps1. Por exemplo, você pode salvá-lo em um arquivo `CreateMBSearchFromComplianceSearch.ps1`chamado.
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. Na sessão do Windows PowerShell que você criou na etapa 2, vá para a pasta onde o script criado na etapa anterior está localizado e, em seguida, execute o script; por exemplo:
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. Quando solicitado pelo script, digite o nome da pesquisa de conteúdo que você deseja converter em uma pesquisa de descoberta eletrônica in-loco (por exemplo, a pesquisa que você criou na etapa 1) e pressione **Enter**.
    
    Se o script for bem-sucedido, uma nova pesquisa de Descoberta Eletrônica In-loco será criada com um status de **NotStarted**. Execute o comando `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` para exibir as propriedades da nova pesquisa. 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>Etapa 4: Iniciar a pesquisa de Descoberta Eletrônica In-loco

O script executado na Etapa 3 cria uma nova pesquisa de Descoberta Eletrônica In-loco, mas não a inicia. A próxima etapa é iniciar a pesquisa para que você possa obter uma estimativa dos resultados da pesquisa.
  
1. No centro de administração do Exchange (Eat), vá para **Gerenciamento** \> **de conformidade e descoberta &amp; eletrônica in-loco**.
    
2. No modo de exibição de lista, selecione a pesquisa de Descoberta Eletrônica In-loco que você criou na Etapa 3.
    
3. ![](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> Clique **em Pesquisar ícone** de pesquisa **estimar os resultados da pesquisa** para iniciar a pesquisa e retornar uma estimativa do tamanho total e do número de itens retornados pela pesquisa. 
    
    As estimativas são exibidas no painel de detalhes. Clique em **Atualizar** ![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar as informações exibidas no painel de detalhes. 
    
4. Para visualizar os resultados após a conclusão da pesquisa, clique em **Visualizar resultados da pesquisa** no painel de detalhes.
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>Próximas etapas após a criação e execução da pesquisa de Descoberta Eletrônica In-loco

Depois de criar e iniciar a pesquisa de Descoberta Eletrônica In-loco criada pelo script na Etapa 3, você pode usar o fluxo de trabalho normal de Descoberta Eletrônica In-loco para executar ações de Descoberta Eletrônica diferentes nos resultados da pesquisa.
  
### <a name="create-an-in-place-hold"></a>Criar um Bloqueio In-loco

1. No Eat, vá para **Gerenciamento** \> **de conformidade e descoberta eletrônica &amp; in-loco**.
    
2. No modo de exibição de lista, selecione a pesquisa de descoberta eletrônica in-loco que você criou na etapa 3 **** ![e clique em](media/O365-MDM-CreatePolicy-EditIcon.gif)editar ícone de edição.
    
3. Na página **Bloqueio In-loco**, marque a caixa de seleção **Colocar conteúdo correspondente à consulta de pesquisa nas caixas de correio selecionadas em bloqueio** e selecione uma das seguintes opções: 
    
  - **Reter indefinidamente** -escolha essa opção para colocar os itens retornados pela pesquisa em um bloqueio indefinido. Itens retidos serão preservados até que você remova a caixa de correio da pesquisa ou remova a pesquisa. 
    
  - **Especificar o número de dias para reter itens em relação à sua data de recebimento** -escolha esta opção para reter itens por um período específico. A duração é calculada a partir da data em que um item de caixa de correio é recebido ou criado. 
    
4. Clique em **Salvar** para criar o Bloqueio In-loco e reiniciar a pesquisa. 
    
[Return to top](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>Copiar os resultados da pesquisa

1. No Eat, vá para **Gerenciamento** \> **de conformidade e descoberta eletrônica &amp; in-loco**.
    
2. No modo de exibição de lista, selecione a pesquisa de Descoberta Eletrônica In-loco que você criou na Etapa 3.
    
3. ![](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)Clique **em ícone pesquisa de** pesquisa e, em seguida, clique em **copiar resultados da pesquisa** na lista suspensa. 
    
4. Em **Copiar Resultados da Pesquisa**, selecione uma das seguintes opções:
    
    - **Incluir itens não pesquisáveis** -Marque essa caixa de seleção para incluir itens de caixa de correio que não puderam ser pesquisados (por exemplo, mensagens com anexos de tipos de arquivo que não puderam ser indexados pela pesquisa do Exchange). 
    
    - **Habilitar eliminação de duplicação** : Marque essa caixa de seleção para excluir mensagens duplicadas. Somente uma única instância de uma mensagem será copiada para a caixa de correio de descoberta. 
    
    - **Habilitar registro em log completo** -Marque essa caixa de seleção para incluir um log completo dos resultados da pesquisa. 
    
    - **Enviar-me email quando a cópia estiver concluída** -Marque essa caixa de seleção para obter uma notificação por email quando a pesquisa estiver concluída. 
    
    - **Copie os resultados para esta caixa de correio de descoberta** , clique em **procurar** para selecionar a caixa de correio de descoberta onde você deseja copiar os resultados da pesquisa. 
    
5. Clique em **Copiar** para iniciar o processo de cópia dos resultados da pesquisa para a caixa de correio de descoberta especificada. 
    
6. Clique em **Atualizar** ![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar as informações sobre o status de cópia exibido no painel de detalhes. 
    
7. Após a conclusão da cópia, clique em **Abrir** para abrir a caixa de correio de descoberta e exibir os resultados da pesquisa. 
  
### <a name="export-the-search-results"></a>Exportar os resultados da pesquisa

1. No Eat, vá para **Gerenciamento** \> **de conformidade e descoberta eletrônica &amp; in-loco**.
    
2. No modo de exibição de lista, selecione a pesquisa de Descoberta Eletrônica In-loco criada na Etapa 3 e clique em **Exportar para um arquivo PST**.
    
3. Na janela **Ferramenta de Exportação de PST de Descoberta Eletrônica**, faça o seguinte: 
    
    - Clique em **Procurar** para especificar o local para o qual você deseja baixar o arquivo PST. 
    
    - Clique na caixa de seleção **Habilitar deduplicação** para excluir as mensagens duplicadas. Somente uma única instância de uma mensagem será incluída no arquivo PST. 
    
    - Clique na caixa de seleção **Incluir itens não pesquisáveis** para incluir itens da caixa de correio que não puderam ser pesquisados (por exemplo, mensagens com anexos dos tipos de arquivo que não puderam ser indexadas pela Pesquisa do Exchange). Os itens não pesquisáveis são exportados para um arquivo PST separado. 
    
4. Clique em **Iniciar** para exportar os resultados da pesquisa para um arquivo PST. 
    
    Uma janela é exibida contendo as informações do status sobre o processo de exportação.
