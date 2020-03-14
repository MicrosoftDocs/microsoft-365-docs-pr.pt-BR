---
title: Pesquisa de Conteúdo no Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: Use a ferramenta Pesquisa de Conteúdo, no centro de conformidade do Office 365 ou do Microsoft 365, para pesquisar conteúdo em caixas de correio, sites do SharePoint Online, contas do OneDrive, Microsoft Teams, grupos do Office 365, grupos do Yammer e conversas do Skype for Business. Você pode usar consultas de pesquisa de palavras-chave e condições de pesquisa para restringir os resultados da pesquisa. Em seguida, você poderá visualizar e exportar os resultados da pesquisa. A Pesquisa de Conteúdo também é uma ferramenta efetiva para pesquisar conteúdo relacionado a uma solicitação do titular dos dados do RGPD.
ms.openlocfilehash: d9fdf5359538209d0793211632979fae1b332d13
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634439"
---
# <a name="content-search-in-office-365"></a>Pesquisa de Conteúdo no Office 365

Use a ferramenta de Descoberta Eletrônica de Pesquisa de Conteúdo no centro de conformidade do Office 365 ou Microsoft 365 para pesquisar itens no local, como email, documentos e conversas de mensagens instantâneas na organização do Office 365. Use esta ferramenta para pesquisar itens nos seguintes serviços do Office 365:
  
- Pastas públicas e caixas de correio do Exchange Online.
    
- Sites do SharePoint Online e contas do OneDrive for Business
    
- Conversas do Skype for Business
    
- Microsoft Teams 

- Grupos do Office 365

- Grupos do Yammer 
    
Após a execução de uma Pesquisa de Conteúdo, o número de locais de conteúdo e um número estimado de resultados de pesquisa serão exibidos nas estatísticas de pesquisa. As estatísticas podem ser visualizadas prontamente, como os locais de conteúdo que têm mais itens que correspondem à consulta de pesquisa. Ao executar uma pesquisa, elas poderão ser visualizadas ou exportadas para um computador local.

## <a name="create-a-search"></a>Criar uma pesquisa

Para ter acesso à página da **Pesquisa de conteúdo** e poder executar pesquisas, visualizar e exportar resultados de pesquisa, um administrador, um responsável pela conformidade ou um gerente de descoberta eletrônica deve ser membro do grupo da função de gerente de descoberta eletrônica do Centro de Conformidade e Segurança. Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).
  
1. Vá para [https://protection.office.com](https://protection.office.com) e entre usando o email e a senha do Office 365.
    
2. Clique em **Pesquisar** \> **Pesquisa de conteúdo**.
    
3. Na página de **Pesquisa**, clique na seta ao lado do ![ícone Adicionar](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Nova pesquisa**. 
    
    ![A Nova lista suspensa de pesquisa](../media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    Você pode escolher uma das seguintes opções:
    
    - **Pesquisa dirigida:** Essa opção inicia um assistente que o orientará durante a criação da pesquisa. A interface do usuário usada para selecionar locais de conteúdo e criar a consulta de pesquisa é igual à opção **Nova pesquisa**. 
    
    - **Nova pesquisa:** Essa opção exibe uma interface do usuário atualizada para criar uma pesquisa. Essa é a opção padrão se você clicar em **Nova pesquisa**.
    
    - **Pesquisar por Lista de IDs** – Essa opção permite pesquisar mensagens de email específicas e outros itens da caixa de correio usando uma lista de IDs do Exchange. Para criar uma pesquisa de lista de IDs (chamada formalmente de pesquisa direcionada), envie um arquivo de valores separados por vírgula (CSV) que identifique os itens específicos da caixa de correio a serem pesquisados. Para obter instruções, confira [Preparar um arquivo CSV para uma lista de IDs de Pesquisa de Conteúdo no Office 365](csv-file-for-an-id-list-content-search.md).
    
    O restante das etapas desse procedimento segue o novo fluxo de trabalho de pesquisa padrão.
    
4. Clique em **Nova pesquisa** na lista suspensa. 
    
5. Em **Consulta de pesquisa**, especifique o seguinte:
    
    ![Especifique palavras-chave, condições e locais a serem pesquisados](../media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - **Palavras-chave a pesquisar:** Digite uma consulta de pesquisa na caixa de **Palavras-chave**. Você pode especificar palavras-chave, propriedades de mensagem como datas enviadas e recebidas, ou ainda, propriedades do documento como nomes de arquivos ou a data em que um documento foi alterado pela última vez. Faça consultas mais complexas que usam um operador Booleano, **E**, **OU**, **NÃO** e **PRÓXIMO**. Você também pode procurar informações confidenciais (por exemplo, números de seguridade social) em documentos ou pesquisar documentos que foram compartilhados externamente. Se você deixar a caixa de palavra-chave vazia, todo o conteúdo localizado nos locais de conteúdo especificado será incluído nos resultados da pesquisa.
    
      Como alternativa, você pode clicar na caixa de seleção **Mostrar lista de palavras-chave** e digitar uma palavra-chave em cada linha. Ao fazer isso, as palavras-chave em cada linha serão conectadas por um operador lógico (**c:s**) com funcionalidade semelhante ao operador **OU** na consulta de pesquisa criada. 
    
      Por que usar a lista de palavras-chave? Para obter estatísticas que mostram quantos itens correspondem a cada palavra-chave. Isso ajudará a identificar rapidamente quais palavras-chave são as mais recentes. Também poderá usar uma frase de palavra-chave (entre parênteses) em uma linha. Para obter mais informações sobre as estatísticas de pesquisa, confira [Exibir estatísticas da palavra-chave para Resultados de Pesquisa de Conteúdo](view-keyword-statistics-for-content-search.md).

     > [!NOTE]
     > Para ajudar a reduzir problemas causados por listas de palavras-chave muito extensas, agora você está limitado a um máximo de 20 linhas na lista de palavras-chave.
    
    - **Condições:** Você também pode adicionar condições a uma consulta de pesquisa para restringir a pesquisa e produzir um conjunto de resultados mais refinado. Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa. Uma condição é logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) por um operador lógico (**c:c**) parecido com a funcionalidade do operador **E**. Isso significa que os itens precisam atender à consulta de palavras-chave e uma ou mais condições para serem incluídas nos resultados. É assim que as condições ajudam a restringir os resultados. Para obter uma lista e uma descrição das condições que podem ser usadas em uma consulta de pesquisa, confira a seção "Condições de pesquisa" em [Consultas de palavra-chave e condições ou critérios de pesquisa para a Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md#search-conditions).
    
       - **Locais:** Escolha os locais de conteúdo a serem pesquisados.
    
      - **Todos os locais:** Use essa opção para pesquisar todos os locais de conteúdo em sua organização. Isso inclui e-mails em todas as caixas de correio do Exchange (incluindo todas as caixas de correio inativas e caixas de correio de todas as equipes da Microsoft, do Yammer e do Office 365), todas as conversas do Skype for Business, todos os sites do SharePoint e do OneDrive for Business (incluindo o sites para todos os grupos do Microsoft Teams, do Yammer e do Office 365), e itens em todas as pastas públicas do Exchange.
    
      - **Locais específicos:** Use essa opção para pesquisar locais de conteúdo específicos. Você poderá pesquisar todos os locais de conteúdo de um serviço específico do Office 365 (por exemplo, pesquisar em todas as caixas de correio do Exchange ou pesquisar conteúdo em todos os sites do SharePoint) ou pesquisar locais específicos em qualquer um dos serviços do Office 365 exibidos. 
    
        ![Interface do usuário para escolher locais de conteúdo para pesquisar](../media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         Também é possível adicionar grupos de distribuição à lista de caixas de correio do Exchange para pesquisar. Para grupos de distribuição, as caixas de correio dos membros do grupo são pesquisadas. Não há suporte para grupos dinâmicos de distribuição.
    
       > [!NOTE]
       > Quando você pesquisa todos os locais de caixa de correio ou apenas caixas de correio específicas, os dados de outros aplicativos do Office 365 salvos nas caixas de correio do usuário são incluídos quando você exporta os resultados de uma pesquisa de conteúdo. Esses dados não serão incluídos nos resultados de pesquisa estimados e não estarão disponíveis para visualização. Eles serão incluídos na exportação e no download dos resultados da pesquisa. Para obter mais informações, confira [Conteúdo armazenado nas caixas de correio do Exchange Online](what-is-stored-in-exo-mailbox.md).
   
6. Depois de configurar a consulta de pesquisa, clique em **Salvar e executar**.
    
7. Na página **Salvar pesquisa**, digite um nome para a pesquisa e uma descrição opcional que ajude a identificar a pesquisa. O nome da pesquisa deve ser exclusivo na organização. 
    
8. Clique em **Salvar** para iniciar a pesquisa. 
    
    Depois de salvar e executar a pesquisa, todos os resultados retornados pela pesquisa serão exibidos no painel de resultados. Dependendo de como a configuração de visualização foi definida, os resultados da pesquisa serão exibidos ou você precisará clicar em **Visualizar resultados** para visualizá-los. Veja mais detalhes na próxima seção. 
    
Para acessar a pesquisa de conteúdo novamente ou acessar outras pesquisas de conteúdo listadas na página **Pesquisa de conteúdo**, selecione a pesquisa e clique em **Abrir**. 
  
Para limpar os resultados ou criar outra pesquisa, clique em ![Adicionar ícone](../media/O365-MDM-CreatePolicy-AddIcon.gif) **Nova pesquisa**. 
  
## <a name="preview-search-results"></a>Visualização de resultados de pesquisa

Há dois parâmetros de configuração para visualizar os resultados de pesquisa. Após executar uma nova pesquisa ou abrir uma pesquisa existente, clique em **Resultados individuais** para exibir as seguintes configurações de visualização: 
  
![Visualizar configurações de resultados de pesquisa](../media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **Visualizar resultados automaticamente:** Essa configuração exibe os resultados após a execução de uma pesquisa.
    
2. **Visualizar resultados manualmente:** Essa configuração exibe espaços reservados no painel de resultados da pesquisa e exibe o botão **Visualizar resultados** que você deve clicar para exibir os resultados da pesquisa. Esta é a configuração padrão. Ela ajuda a melhorar o desempenho da pesquisa ao não exibir automaticamente os resultados quando uma pesquisa existente é aberta. 
    
Existem limites relacionados à quantidade de itens disponíveis para visualização. Para obter mais informações, confira [Limites de Pesquisa de Conteúdo](limits-for-content-search.md). 
  
Para obter uma lista dos tipos de arquivos compatíveis que podem ser visualizados, confira [Visualização de resultados da pesquisa](#previewing-search-results) na seção "Mais informações sobre pesquisa de conteúdo". Se um tipo de arquivo não for compatível com a visualização ou não puder baixar uma cópia de um documento, clique em **Baixar arquivo original** para baixá-lo em seu computador local. Para páginas da Web .aspx, a URL da página está incluída, mas pode ser que não haja permissões para acessar a página. 
  
Observe que itens não indexados não estão disponíveis para visualização.
  
## <a name="view-information-and-statistics-about-a-search"></a>Exibir informações e estatísticas sobre uma pesquisa

Após criar e executar uma pesquisa de conteúdo, será possível ver estatísticas sobre os resultados estimados da pesquisa. Ela incluirá um resumo dos resultados da pesquisa, as estatísticas da consulta, como o número de locais de conteúdo com os itens que correspondem à consulta da pesquisa e o nome dos locais de conteúdo que têm mais itens correspondentes. Você poderá exibir as estatísticas de uma ou mais pesquisas de conteúdo. O que permite comparar rapidamente os resultados para várias pesquisas e tomar decisões sobre a eficácia das consultas de pesquisa.
  
Você também poderá baixar as estatísticas da pesquisa e as estatísticas da palavra-chave para um arquivo CSV. Isso permite usar os recursos de filtragem e classificação no Excel para comparar resultados e preparar relatórios para os resultados da pesquisa.
  
Para visualizar as estatísticas de pesquisa:
  
1. Na página **Pesquisa de conteúdo**, clique em **Abrir** e depois, clique na pesquisa para a qual você deseja exibir as estatísticas. 
    
2. Na página do submenu, clique em **Abrir consulta**. 
    
3. Na lista suspensa **Resultados individuais**, clique em **Estatísticas de pesquisa**.
    
4. Na lista suspensa **Tipo**, clique em uma das seguintes opções, dependendo das estatísticas de pesquisa que você deseja visualizar. 
    
  - **Resumo**: Exibe as estatísticas de cada tipo de locais de conteúdo pesquisado. Tal resumo contém o número de locais de conteúdo com os itens correspondentes à consulta de pesquisa, o número total e o tamanho dos itens de resultado da pesquisa. Esta é a configuração padrão.
    
  - **Consultas:** Exibe estatísticas sobre a consulta de pesquisa. Já esse inclui o tipo de local de conteúdo ao qual as estatísticas de consulta são aplicáveis, parte da consulta de pesquisa à qual as estatísticas são aplicáveis (observe que **Primário** indica toda a consulta de pesquisa), o número de locais de conteúdo que contêm itens correspondentes à consulta de pesquisa, o número total, tamanho e os itens que foram encontrados (no local de conteúdo especificado) correspondentes à consulta de pesquisa. As estatísticas para itens não indexados (também chamados de *itens parcialmente indexados*) também são exibidas. No entanto, apenas itens parcialmente indexados de caixas de correio estão inclusos nas estatísticas. Itens parcialmente indexados do SharePoint e do OneDrive não são incluídos nas estatísticas.
    
  - **Principais locais:** Exibe estatísticas sobre o número de itens que correspondem à consulta de pesquisa em cada local de conteúdo. Os primeiros 1.000 locais são exibidos.
    
Para obter mais informações sobre as estatísticas de pesquisa, confira [Exibir estatísticas da palavra-chave para resultados de Pesquisa de Conteúdo](view-keyword-statistics-for-content-search.md).
  
  
## <a name="export-search-results"></a>Exportar resultados de pesquisa

Depois que uma pesquisa é executada com êxito, você pode exportar os resultados para um computador local. Quando você exporta os resultados de email, eles são baixados para o computador como arquivos PST ou como mensagens individuais (arquivos .msg). Quando você exporta o conteúdo de sites do SharePoint e do OneDrive, cópias dos documentos nativos do Office são exportadas. Também há outros documentos e relatórios que são incluídos com os resultados da pesquisa exportados. Você também pode exportar o relatório de resultados da pesquisa e não os itens reais.
  
Exportar resultados de pesquisa:
  
1. Na página **Pesquisa de conteúdo**, clique na pesquisa para a qual você deseja atualizar os resultados. 
    
2. Na página do submenu, clique em ![Exportar ícone de resultados de pesquisa](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Mais** e em seguida, clique em **Exportar resultados**. Também é possível exportar um relatório de resultados de pesquisa.
    
3. Complete as seções na página do submenu **Exportar resultados**. Use a barra de rolagem para exibir todas as opções de exportação. 
    
Para obter instruções mais detalhadas e dicas de solução de problemas, confira:
  
- [Exportar resultados de Pesquisa de Conteúdo](export-search-results.md)
    
- [Exportar um relatório da Pesquisa de Conteúdo](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a>Para obter mais informações sobre pesquisa de conteúdo

Consulte as seções a seguir para obter mais informações sobre pesquisas de conteúdo.
  
[Limites da pesquisa de conteúdo](#content-search-limits)
  
[Criar uma consulta de pesquisa](#building-a-search-query)
  
[Pesquisar contas do OneDrive](#searching-onedrive-accounts)
  
[Pesquisar por Microsoft Teams e Grupos do Office 365 ](#searching-microsoft-teams-and-office-365-groups)

[Pesquisar grupos do Yammer](#searching-yammer-groups)
  
[Pesquisar caixas de correio inativas](#searching-inactive-mailboxes)
  
[Pesquisar caixas de correio desconectadas ou que tiveram a licença removida](#searching-disconnected-or-de-licensed-mailboxes)

[Visualizar os resultados de pesquisa](#previewing-search-results)
  
[Itens parcialmente indexados](#partially-indexed-items)

[Pesquisa de conteúdo em um ambiente Multi-Geo do SharePoint (englobando diferente áreas geográficas)](#searching-for-content-in-a-sharepoint-multi-geo-environment)
  
### <a name="content-search-limits"></a>Limites da pesquisa de conteúdo

- Para obter uma descrição dos limites que são aplicados ao recurso de Pesquisa de Conteúdo, confira [Limites de Pesquisa de Conteúdo](limits-for-content-search.md).
    
- A Microsoft coleta informações sobre o desempenho das Pesquisas de Conteúdo executadas por todas as organizações do Office 365. Embora a complexidade da consulta de pesquisa possa afetar os tempos de pesquisa, o maior fator que afeta o tempo de duração das pesquisas é o número de caixas de correio pesquisadas. Embora a Microsoft não forneça um Contrato de Nível de Serviço para os tempos de pesquisa, a tabela a seguir lista os tempos médios de pesquisa para uma Pesquisa de Conteúdo com base no número de caixas de correio incluídas na pesquisa.
    
|**Número de caixas de correio**|**Tempo médio de pesquisa**|
|:-----|:-----|
|100  <br/> |30 segundos  <br/> |
|1.000  <br/> |45 segundos  <br/> |
|10.000  <br/> |4 minutos  <br/> |
|25.000  <br/> |10 minutos  <br/> |
|50.000  <br/> |20 minutos  <br/> |
|100.000  <br/> |25 minutos  <br/> |
  
### <a name="building-a-search-query"></a>Criar uma consulta de pesquisa

Para obter informações detalhadas sobre como criar uma consulta de pesquisa usando operadores de pesquisa booleanos e condições de pesquisa, como também ao pesquisar tipos de informações confidenciais e conteúdo compartilhado com usuários de fora da organização, confira [Consultas de palavras-chave e condições de pesquisa para Pesquisa de conteúdo ](keyword-queries-and-search-conditions.md).
  
Lembre-se do seguinte ao usar a lista de palavras-chave para criar uma consulta de pesquisa.
  
- É necessário selecionar a caixa de seleção **Mostrar lista de palavras-chave** e digitar cada palavra-chave em uma linha separada para criar uma consulta de pesquisa em que as palavras-chave (ou frases de palavras-chave) de cada linha sejam conectadas pelo operador **OU**. Caso cole uma lista de palavras-chave na caixa de palavras-chave ou pressione a tecla **Enter** depois de digitar uma palavra-chave, elas não serão conectadas pelo operador **OU**. Veja a seguir uma maneira correta e outra incorreta de como adicionar uma lista de palavras-chave. 
    
    **Incorreto**
    
    ![A maneira incorreta de formatar uma lista de palavras-chave (colando a lista na caixa de palavra-chave)](../media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Correto**
    
    ![A maneira correta de formatar uma lista de palavras-chave (selecionando a caixa de seleção e, em seguida, colando a lista)](../media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- Você também pode preparar uma lista de palavras-chave ou frases de palavra-chave em um arquivo do Excel ou em um arquivo de texto simples e, em seguida, copiar e colar a lista na lista de palavras-chave. Para fazer isso, é preciso selecionar a caixa de seleção **Mostrar lista de palavras-chave**. Em seguida, clique na primeira linha da lista de palavras-chave e cole a sua lista. Cada linha do Excel ou do arquivo de texto é colada em uma linha separada na lista de palavras-chave. 
    
- Depois de criar uma consulta usando a lista de palavras-chave, é uma boa ideia verificar a sintaxe da consulta de pesquisa para que a consulta de pesquisa seja a desejada. Na consulta de pesquisa exibida em **Consulta** no painel de detalhes, as palavras-chave são separadas pelo texto **(c:s)**. Isso indica que as palavras-chave estão conectadas por um operador lógico semelhante em funcionalidade ao operador **OU**. Da mesma forma, se a consulta de pesquisa incluir condições, as palavras-chave e as condições serão separadas pelo texto **(c:c)**. Isso indica que as palavras-chave estão conectadas por um operador lógico semelhante em funcionalidade ao operador **E**. Veja um exemplo de consulta de pesquisa (exibido no painel de Detalhes) que resulta ao usar a lista de palavras-chave e uma condição. 
    
    ![Exemplo de consulta que é criada ao usar a lista de palavras-chave e uma condição](../media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- Ao executar uma pesquisa de conteúdo, o Office 365 verifica automaticamente a consulta de pesquisa para caracteres sem suporte e para operadores booleanos que podem não estar em maiúsculas. Os caracteres sem suporte geralmente estão ocultos e costumam causar um erro de pesquisa ou retornam resultados inesperados. Para obter mais informações sobre os caracteres sem suporte que estão marcados, confira [Verifique se há erros na consulta da Pesquisa de Conteúdo](check-your-content-search-query-for-errors.md).
    
- Se você tiver uma consulta de pesquisa que contenha palavras-chave para caracteres que não estão em inglês (como caracteres chineses), clique em **Idioma/país de consulta**![Ícone de Idioma/país de consulta na Pesquisa de conteúdo](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e selecione um valor de código cultural de idioma/país para a pesquisa. O padrão idioma/região é neutro. Como saber se é preciso alterar a configuração de idioma para uma pesquisa de conteúdo? Se você tiver certeza de que os locais de conteúdo contêm os caracteres que não estão em inglês que você está procurando, mas a pesquisa não retorna nenhum resultado, a configuração de idioma pode ser a causa. 
  
### <a name="searching-onedrive-accounts"></a>Pesquisar contas do OneDrive

- Para coletar uma lista das URLs dos sites do OneDrive na organização, confira [Criar uma lista de todos os locais do OneDrive na organização](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Esse script neste artigo cria um arquivo de texto que contém uma lista de todos os sites do OneDrive. Para executar esse script, é necessário instalar e usar o Shell de Gerenciamento Online do SharePoint. Não se esqueça de acrescentar a URL do domínio MySite da organização para cada site do OneDrive que você deseja pesquisar. Este é o domínio que contém todos os seus OneDrive; por exemplo, `https://contoso-my.sharepoint.com`. Veja um exemplo de URL para o site do OneDrive de um usuário: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
    
    No caso raro de acontecer do nome principal do usuário (UPN) ser alterado, a URL do local do OneDrive dessa pessoa é alterada para incorporar o novo UPN. Se isso acontecer, será preciso modificar uma pesquisa de conteúdo adicionando a nova URL do OneDrive do usuário e remover a antiga.
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>Pesquisar por Microsoft Teams e Grupos do Office 365

Você pode pesquisar na caixa de correio associada a um Grupo do Office 365 ou ao Microsoft Teams. Como o Microsoft Teams se baseia nos Grupos do Office 365, a pesquisa é semelhante. Em ambos os casos, apenas a caixa de correio do grupo ou da equipe são pesquisadas. As caixas de correio do grupo ou membros da equipe não são pesquisadas. Para pesquisá-los, você precisa adicioná-los especificamente à pesquisa.
  
Lembre-se do seguinte ao pesquisar o conteúdo do Microsoft Teams e dos grupos do Office 365.
  
- Para pesquisar conteúdo localizado no Teams e em Grupos do Office 365, é necessário especificar a caixa de correio e o site do SharePoint associados a uma equipe ou grupo.
    
- Execute o cmdlet **Get-UnifiedGroup** no Exchange Online para exibir as propriedades de uma equipe ou de um grupo do Office 365. Esta é uma boa maneira de obter a URL do site associado a uma equipe ou a um grupo. Por exemplo, o comando abaixo exibe as propriedades selecionadas para um grupo do Office365 chamado de Equipe de Liderança Sênior: 
    
  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroup**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser membro de um grupo de funções atribuído à função de Destinatários Somente Leitura. 
  
- Quando uma caixa de correio de usuário é pesquisada, qualquer equipe ou Grupo do Office 365 do qual o usuário seja membro não serão pesquisados. Da mesma forma, quando você pesquisa uma equipe ou um Grupo do Office 365, somente a caixa de correio e o site do grupo especificados são pesquisados. As caixas de correio e as contas do OneDrive for Business dos membros do grupo não são pesquisadas, a menos que você as adicione explicitamente à pesquisa.
    
- Para obter uma lista dos membros de uma equipe ou um Grupo do Office 365, você pode exibir as propriedades na página **Início \> Grupos** no centro de administração do Microsoft 365. Como alternativa, execute o comando a seguir no PowerShell do Exchange Online: 
    
  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroupLinks**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser um membro de um grupo de funções atribuído à função Destinatários Somente Leitura. 
  
- As conversas que fazem parte de um canal do Teams são armazenadas na caixa de correio associada à equipe. Da mesma forma, os arquivos que os membros da equipe compartilham em um canal são armazenados no site do SharePoint da equipe. Portanto, é preciso adicionar a caixa de correio da equipe e o site do SharePoint como um local de conteúdo para pesquisar conversas e arquivos em um canal.
    
- Como alternativa, as conversas que fazem parte da Lista de chat no Teams são armazenadas na caixa de correio do Exchange Online dos usuários que participam do chat. E os arquivos que um usuário compartilha nas conversas do Chat são armazenados na conta do OneDrive for Business do usuário que compartilha o arquivo. Portanto, é preciso adicionar as caixas de correio do usuário individual e as contas do OneDrive for Business como locais de conteúdo para pesquisar conversas e arquivos na Lista de chat.
    
    > [!NOTE]
    > Em uma implantação híbrida do Exchange, os usuários com uma caixa de correio local podem participar de conversas que fazem parte da Lista de chat no Teams. Nesse caso, o conteúdo dessas conversas também pode ser pesquisado porque é salvo em uma área de armazenamento baseada na nuvem (chamada de *caixa de correio baseada na nuvem para usuários locais*) para usuários que possuem uma caixa de correio local. Para obter mais informações, consulte [Pesquisar caixas de correio baseadas na nuvem para usuários locais no Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).
  
- Todas as equipes ou canal de equipe contêm um Wiki para anotações e colaboração. O conteúdo Wiki é salvo automaticamente em um arquivo com um formato .mht. Esse arquivo é armazenado na biblioteca de documentos de Dados do Wiki do Teams no site do SharePoint da equipe. Você pode usar a ferramenta de Pesquisa de Conteúdo para pesquisar o Wiki ao especificar o site do SharePoint da equipe como o local de conteúdo a ser pesquisado. 
    
    > [!NOTE]
    > O recurso de pesquisar o Wiki de uma equipe ou canal (quando você pesquisa o site do SharePoint da equipe) foi lançado em 22 de junho de 2017. As páginas Wiki que foram salvas ou atualizadas nesta data ou após estarão disponíveis para serem pesquisadas. As páginas Wiki salvas pela última vez ou atualizadas antes dessa data não estarão disponíveis para a pesquisa. 
 
- As informações resumidas para reuniões e chamadas em um canal do Teams também são armazenadas nas caixas de correio de usuários que discam para a reunião ou chamada. Isso significa que você pode usar a Pesquisa de Conteúdo para pesquisar esses registros de resumo. Essas informações de resumo incluem: 
  
  - Data, hora de início, hora de término e duração de uma reunião ou chamada

  - A data e a hora em que cada participante ingressou na reunião ou chamada.

  - Chamadas enviadas para caixa postal

  - Chamadas perdidas ou não respondidas

  - Transferências de chamadas, que são representadas como duas chamadas separadas

  Pode levar até 8 horas para que os registros de reunião e de chamada estejam disponíveis para pesquisa.

  Nos resultados da pesquisa, os resumos de reuniões são identificados como **Reunião** no **Campo de tipo** e os resumos de chamadas são identificados como **Chamada**. Além disso, as conversas que fazem parte de um canal do Teams e chats 1xN são identificadas como **Mensagens instantâneas ** no campo de **Tipo**.
  
  ![As reuniões, chamadas e chats 1xN do Teams são identificados no campo de Tipo](../media/O365-ContentSearch-Teams-MessageKind.png)

- Você pode usar a propriedade de email **Tipo**ou a condição de pesquisa **Tipo de mensagem** para pesquisar especificamente por conteúdo no Teams. 
  
  - Para usar a propriedade **Tipo** como parte da consulta de pesquisa de palavras-chave, na caixa **Palavras-chave** de uma consulta de pesquisa, digite `kind:microsoftteams`.

    ![Use o termo tipo:microsoftteams na caixa Palavras-chave](../media/O365-ContentSearch-Teams-Keywords.png)
  
  - Para utilizar uma condição de pesquisa, adicione a condição de **Tipo de mensagem** e use o valor `microsoftteams`. 

    ![Utilize a condição de Tipo de mensagem com o valor microsoftteams.](../media/O365-ContentSearch-Teams-MessageKindCondition.png)

Observe que as condições estão logicamente associadas à consulta de palavra-chave pelo operador **E (AND)**. Isso significa que um item deve corresponder à consulta da palavra-chave e à condição da pesquisa para aparecer nos resultados da pesquisa. Para saber mais, consulte a seção “Diretrizes de condições de uso” em [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions).
  
### <a name="searching-yammer-groups"></a>Pesquisar grupos do Yammer

Você pode usar a propriedade de e-mail **ItemClass** ou o critério de pesquisa **Tipo** para pesquisar itens de conversa especificamente nos grupos do Yammer.

  - Para usar a propriedade **ItemClass** como parte da consulta de pesquisa de palavra-chave, na caixa **palavras-chave** de uma consulta de pesquisa, você pode digitar uma (ou todas) as seguintes propriedades: pares de valores:

     - ItemClass:IPM.Yammer.message
     - ItemClass:IPM.Yammer.poll
     - ItemClass:IPM.Yammer.praise
     - ItemClass:IPM.Yammer.question
  
    Por exemplo, você pode usar a seguinte consulta de pesquisa para retornar mensagens do Yammer e itens de elogio do Yammer:

    ![Usar a propriedade ItemClass para procurar itens do Yammer](../media/YammerContentSearch1.png)
  
  - Como alternativa, você pode usar a condição de e-mail**Tipo** e selecionar **mensagens do Yammer** para retornar itens do Yammer. Por exemplo, a seguinte consulta de pesquisa retornará todos os itens de conversa do Yammer que contenham a palavra-chave "confidencial". 

    ![Use o cartão de condição de tipo para pesquisar itens de conversa do Yammer](../media/YammerContentSearch2.png)

### <a name="searching-inactive-mailboxes"></a>Pesquisar caixas de correio inativas

Você pode pesquisar por caixas de correio inativas em uma pesquisa de conteúdo. Para ver uma lista das caixas de correio inativas na sua organização, execute o comando  `Get-Mailbox -InactiveMailboxOnly`no PowerShell do Exchange Online. Como alternativa, vá para **Governança de informações** \> **Retenção** no Centro de Conformidade e Segurança, e em seguida, clique em **Mais**![Reticências da Barra de Navegação](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Caixas de correio inativas**.
  
Eis alguns pontos a serem levados em consideração durante a pesquisa de caixas de correio inativas.

- Se uma pesquisa de conteúdo incluir uma caixa de correio de usuário e essa caixa de correio depois for desativada, a pesquisa de conteúdo continuará a pesquisar a caixa de correio inativa ao executar a pesquisa novamente.
    
- Em alguns casos, um usuário pode ter uma caixa de correio ativa e uma inativa com o mesmo endereço SMTP. Nesse caso, apenas a caixa de correio específica que você selecionar como local para uma pesquisa de conteúdo será pesquisada. Em outras palavras, se você adicionar a caixa de correio de um usuário a uma pesquisa, não será possível supor que as caixas de correio ativas e inativas sejam pesquisadas. Somente a caixa de correio que você adicionar explicitamente à pesquisa será pesquisada.
    
- Você pode usar o Centro de Conformidade & Segurança do PowerShell para criar uma pesquisa de conteúdo para pesquisar uma caixa de correio inativa. Para fazer isso, você precisa acrescentar um ponto (. ) ao endereço de email da caixa de correio inativa. Por exemplo, o comando a seguir cria uma pesquisa de conteúdo que pesquisa uma caixa de correio inativa com o endereço de email pavelb@contoso.onmicrosoft.com:

   ``` 
   New-ComplianceSearch -Name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- Não é recomendável de forma alguma que você tenha uma caixa de correio ativa e uma inativa com o mesmo endereço SMTP. Se você precisar reutilizar o endereço SMTP atribuído atualmente a uma caixa de correio inativa, é recomendável recuperar a caixa de correio inativa ou restaurar o conteúdo de uma caixa de correio inativa para uma ativa (ou o arquivo de uma caixa de correio ativa) e excluir a caixa de correio inativa. Para obter mais informações, consulte um dos seguintes tópicos:
    
  - [Recuperar uma caixa de correio inativa no Office 365](recover-an-inactive-mailbox.md)
    
  - [Restaurar uma caixa de correio inativa no Office 365](restore-an-inactive-mailbox.md)
    
  - [Excluir uma caixa de correio inativa no Office 365](delete-an-inactive-mailbox.md)

### <a name="searching-disconnected-or-de-licensed-mailboxes"></a>Pesquisar caixas de correio desconectadas ou que tiveram a licença removida

Se a licença do Exchange Online ( ou a licença inteira do Office 365) for removida de uma conta de usuário no Office 365 ou no Azure Active Directory, a caixa de correio do usuário se tornará uma caixa de correio *desconectada*. Isso significa que a caixa de correio não está mais associada à conta de usuário. Veja o que acontece ao pesquisar caixas de correio desconectadas:

- Se a licença for removida de uma caixa de correio, esta não será mais pesquisável. 

- Se uma pesquisa de conteúdo existente incluir uma caixa de correio em que a licença for removida, nenhum resultado da pesquisa da caixa de correio desconectada será retornado se você executar novamente a pesquisa de conteúdo.

- Se você usar o cmdlet **New-ComplianceSearch** para criar uma pesquisa de conteúdo e especificar um caixa de correio desconectada como o local de conteúdo do Exchange para pesquisar, a pesquisa de conteúdo não retornará resultados de pesquisa da caixa de correio desconectada.

Se você precisar preservar os dados em uma caixa de correio desconectada para que possam ser pesquisados, você deve colocar a caixa de correio em retenção antes de remover a licença. Isso preserva os dados e mantém a caixa de correio desconectada pesquisável até que a retenção seja removida. Para saber mais sobre retenções, confira [Como identificar o tipo de retenção de uma caixa de correio do Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

### <a name="previewing-search-results"></a>Visualizar os resultados de pesquisa

É possível visualizar os tipos de arquivo com suporte no painel de visualização. Se não houver suporte para um tipo de arquivo, será necessário baixar uma cópia do arquivo no computador local para visualizá-lo. Os seguintes tipos de arquivo têm suporte e podem ser visualizados no painel de resultados da pesquisa.
  
- .txt, .html, .mhtml
    
- .eml
    
- .doc, .docx, .docm
    
- .pptm, .pptx
    
- .pdf
    
Além disso, os seguintes tipos de contêiner de arquivos possuem suporte. Você pode exibir a lista de arquivos no contêiner no painel de visualização.
  
- .zip
    
- .gzip
    
### <a name="partially-indexed-items"></a>Itens parcialmente indexados

- Como explicado anteriormente, os itens parcialmente indexados na caixa de correio são incluídos nos resultados estimados da pesquisa. Itens parcialmente indexados do SharePoint e do OneDrive não são incluídos nos resultados estimados da pesquisa. 
    
- Se um item parcialmente indexado corresponder à consulta de pesquisa (porque outras propriedades do documento ou mensagem atendem aos critérios de pesquisa), não será incluído no número estimado de itens não indexados. Se um item parcialmente indexado for excluído pelos critérios de pesquisa, ele não será incluído no número estimado de itens não indexados. Para obter mais informações, consulte [Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365](partially-indexed-items-in-content-search.md).

### <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a>Pesquisa de conteúdo em um ambiente Multi-Geo do SharePoint (englobando diferente áreas geográficas)

Se for necessário que um gerente de Descoberta Eletrônica pesquise conteúdo no SharePoint e no OneDrive em um [ambiente multi-geo do SharePoint](https://go.microsoft.com/fwlink/?linkid=860840), você precisará fazer o seguinte:
   
1. Crie uma conta de usuário separada para cada área geográfica satélite que o gerenciador de Descoberta Eletrônica precisa pesquisar. Para pesquisar conteúdo nos sites dessa área geográfica, o gerenciador de Descoberta Eletrônica deve entrar na conta que você criou para aquela área e executar uma pesquisa de conteúdo.

2. Crie um filtro de permissões de pesquisa para cada área geográfica satélite que o gerenciador de Descoberta Eletrônica precise pesquisar. Cada um desses filtros de permissões de pesquisa limita o escopo da pesquisa de conteúdo a uma área geográfica específica quando o gerenciador de Descoberta Eletrônica está conectado à conta de usuário associada à essa área.
 
> [!TIP]
> Você não precisa usar essa estratégia ao usar a ferramenta de pesquisa na[Descoberta Eletrônica Avançada](overview-ediscovery-20.md). Isso ocorre porque todos os data centers são pesquisados quando você pesquisa sites do SharePoint e contas do OneDrive em Descoberta Eletrônica Avançada. Você deve usar essa estratégia de contas de usuário específicas de região e esses filtros de permissões de pesquisa somente quando usar a ferramenta Pesquisa de Conteúdo e executar pesquisas associadas a [casos de Descoberta Eletrônica](ediscovery-cases.md). 


Por exemplo, digamos que um gerenciador de Descoberta Eletrônica precise pesquisar o conteúdo do SharePoint e do OneDrive em áreas satélite na América do Norte, Europa e Pacífico Asiático. A primeira etapa é criar três contas de usuários, uma para cada área. A próxima etapa é criar três filtros de permissões de pesquisa, um para cada área *e* conta de usuário correspondente. Aqui estão exemplos de três filtros de permissões de pesquisa para esse cenário. Em cada um desses exemplos, o parâmetro **Região** especifica o local do data center do SharePoint para aquela região geográfica enquanto o parâmetro **Usuários** especifica a conta do usuário correspondente. 

**América do Norte**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

**Europa**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

**Pacífico Asiático**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

Lembre-se do seguinte ao usar filtros de permissão de pesquisa para pesquisar conteúdo em ambientes de regiões diversas:

- O parâmetro **Região**direciona as pesquisas para a área de satélite especificada. Se um gerente de Descoberta Eletrônica só pesquisa sites do SharePoint e do OneDrive fora da região especificada no filtro permissões de pesquisa, nenhum resultado de pesquisa será mostrado. 

- O parâmetro **Região** não controla as pesquisas de caixas de correio do Exchange. Todos os datacenters são pesquisados quando se pesquisa caixas de correio. 
    
Para obter mais informações sobre como usar filtros de permissões de pesquisa em um ambiente de várias regiões, confira a seção "Pesquisa e exportação de conteúdo em ambientes Multi-Geo" em[Configurar limites de conformidade para investigações de Descoberta Eletrônica](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).
