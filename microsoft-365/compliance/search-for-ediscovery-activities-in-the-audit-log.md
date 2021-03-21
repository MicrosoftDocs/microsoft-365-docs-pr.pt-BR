---
title: Procurar atividades de descoberta eletrônica no log de auditoria
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Saiba quais eventos são registrados quando os usuários atribuídos a permissões de Descoberta eDiscovery executam tarefas de Pesquisa de Conteúdo e Descoberta Principal na Central de Conformidade & Segurança.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7324cf610373202cdc24f48c23dc0647d4a21ea8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922483"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Procurar atividades de descoberta eletrônica no log de auditoria

Atividades relacionadas à Pesquisa de Conteúdo e Descoberta Eletrônica (para Descoberta Eletrônica Básica e Descoberta Eletrônica Avançada) executadas no Centro de Conformidade do & de Segurança ou executando os cmdlets correspondentes do PowerShell são registrados no log de auditoria. Os eventos são registrados quando os administradores ou gerentes de Descoberta eDiscovery (ou qualquer permissão de Descoberta eDiscovery atribuída pelo usuário) executam as seguintes tarefas de Pesquisa de Conteúdo e Descoberta Principal de Descoberta Digital no Centro de Conformidade & Segurança:
  
- Criando e gerenciando casos de Descoberta Básica e Avançada

- Criar, iniciar e editar pesquisas de conteúdo

- Executar ações de pesquisa de conteúdo, como visualização, exportação e exclusão de resultados de pesquisa

- Gerenciando custodiantes e conjuntos de revisão na Descoberta Avançada

- Configurar a filtragem de permissões para pesquisa de conteúdo

- Gerenciar a função de administrador de Descoberta Eletrônica

> [!IMPORTANT]
> As atividades descritas neste artigo são apenas o resultado de tarefas de Descoberta eDiscovery executadas usando o Centro de Conformidade & Segurança. As tarefas de Descoberta Virtual que foram executadas usando a ferramenta In-Place Descoberta Virtual no Exchange Online ou o Centro de Descoberta Virtual no SharePoint Online não estão incluídas. 
  
Para obter mais informações sobre como pesquisar o log de auditoria, as permissões necessárias e exportar resultados da pesquisa, consulte Pesquisar o log de auditoria no Centro de Conformidade & [Segurança.](search-the-audit-log-in-security-and-compliance.md)
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Como pesquisar e exibir atividades de Descoberta

Atualmente, você precisa fazer algumas coisas específicas para exibir as atividades de Descoberta e No log de auditoria. Veja como.
  
1. Acesse [https://protection.office.com](https://protection.office.com).

2. Entre usando sua conta de trabalho ou da escola.

3. No painel esquerdo, clique em **Pesquisar** e clique em **Pesquisa de log de auditoria.**

4. Na lista **lista** da Atividades, em **Atividades** de Descoberta e Ou Atividades de Descoberta Avançada **,** clique em uma ou mais atividades para pesquisar.

    > [!NOTE]
    > A **lista** lista listada Atividades também inclui um grupo de atividades denominadas **atividades de cmdlet de Descoberta** Eletrônica que retornarão registros do log de auditoria do cmdlet.
  
5. Selecione um intervalo de datas e horas para exibir eventos de Descoberta E que ocorreram nesse período. 

6. Na caixa **Usuários,** selecione um ou mais usuários para exibir os resultados da pesquisa. Deixe essa caixa em branco para retornar entradas para todos os usuários.

7. Clique em **Pesquisar** para executar a pesquisa usando seus critérios de pesquisa. 

8. Depois que os resultados da pesquisa são exibidos, você pode clicar em **Filtrar resultados** para filtrar ou classificar os registros de atividade resultantes. Infelizmente, você não pode usar a filtragem para excluir explicitamente determinadas atividades. 

9. Para exibir detalhes sobre uma atividade, clique no registro de atividades na lista de resultados da pesquisa. 

    Uma **página de** sobrevoo Detalhes é exibida que contém as propriedades detalhadas do registro de evento. Para exibir detalhes adicionais, clique **em Mais informações.** Para uma descrição dessas propriedades, consulte a [seção Propriedades detalhadas para atividades de Descoberta](#detailed-properties-for-ediscovery-activities) e.

10. Se desejado, você pode exportar os resultados da pesquisa de log de auditoria para um arquivo CSV e, em seguida, usar o recurso De consulta do Excel Power para formatar e filtrar esses registros. Para saber mais, confira [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>Atividades de Descoberta Eletrônica

A tabela a seguir descreve as atividades de Pesquisa de Conteúdo e Descoberta Eletrônica Principal que são registradas quando um administrador ou gerente de Descoberta Eletrônica executa uma atividade relacionada à Descoberta Eletrônica usando o Centro de Conformidade de Segurança & ou executando o cmdlet correspondente no Centro de Conformidade e Segurança & do PowerShell. Observe também que algumas atividades realizadas no Advanced serão retornadas quando você pesquisar atividades nesta lista.
  
> [!NOTE]
> As atividades de Descoberta Eletrônica descritas nesta seção fornecem informações semelhantes às atividades de cmdlet de Descoberta Eletrônica descritas na próxima seção. Recomendamos que você use as atividades de Descoberta Externa descritas nesta seção porque elas aparecerão nos resultados da pesquisa de log de auditoria dentro de 30 minutos. Leva até 24 horas para que as atividades do cmdlet eDiscovery apareçam nos resultados da pesquisa de log de auditoria. 
  
|**Nome amigável**|**Operação**|**Cmdlet correspondente**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Membro adicionado ao caso de Descoberta E  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Um usuário foi adicionado como membro de um caso de Descoberta e. Como membro de uma ocorrência, um usuário pode executar várias tarefas relacionadas a casos, dependendo se as permissões necessárias foram atribuídas.  <br/> |
|Pesquisa de conteúdo alterada  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Uma pesquisa de conteúdo existente foi alterada. As alterações podem incluir adicionar ou remover locais de conteúdo ou editar a consulta de pesquisa.  <br/> |
|Associação de administrador de Descobertas E Alteradas  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |A lista de Administradores de Descobertas Desdiscovery em sua organização foi alterada. Essa atividade é registrada quando a lista de Administradores de Descoberta Externa é substituída por um grupo de novos usuários. Se um único usuário for adicionado ou removido, a operação CaseAdminAdded será registrada.  <br/> |
|Caso de Descoberta eDiscovery alterado  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Um caso de Descoberta E Foi alterado. As alterações incluem fechar um caso aberto ou reabrir um caso fechado.  <br/> |
|Associação de caso de Descoberta E Alterada  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |A lista de associação de um caso de Descoberta E foi alterada. Essa atividade é registrada quando todos os membros são substituídos por um grupo de novos usuários. Se um único membro for adicionado ou removido, a operação CaseMemberAdded ou CaseMemberRemoved será registrada.  <br/> |
|Filtro de permissões de pesquisa alterado  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Um filtro de permissões de pesquisa foi alterado.  <br/> |
|Consulta de pesquisa alterada para a preensão de caso de Descoberta e  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Uma responsabilidade baseada em consulta associada a um caso de Descoberta E foi alterada. As alterações possíveis incluem a edição da consulta ou intervalo de datas para uma espera baseada em consulta.  <br/> |
|Item de visualização de pesquisa de conteúdo baixado  <br/> |PreviewItemDownloaded  <br/> |N/D  <br/> |Um usuário baixou um item no computador local (clicando no link **Baixar item original)** ao visualizar os resultados da pesquisa.  <br/> |
|Item de visualização de pesquisa de conteúdo listado  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Um usuário clicou em **Visualizar** resultados da pesquisa para exibir a página de resultados da pesquisa de visualização, que lista até 1.000 itens dos resultados de uma Pesquisa de Conteúdo.  <br/> |
|Item de visualização de pesquisa de conteúdo exibido  <br/> |PreviewItemRendered  <br/> |N/D  <br/> |Um gerente de Descoberta Desdiscovery exibiu um item clicando nele ao visualizar os resultados da pesquisa.  <br/> |
|Pesquisa de conteúdo criada  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Uma nova pesquisa de conteúdo foi criada.  <br/> |
|Administrador criado de Descoberta e  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Um usuário foi adicionado como Administrador de Descobertas E Na organização.  <br/> |
|Caso de Descoberta Desdiscovery criado  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Foi criado um caso de Descoberta eDiscovery. Quando um caso é criado, você só precisa dar um nome a ele. Outras tarefas relacionadas a casos, como adicionar membros, criar respeções e criar pesquisas de conteúdo associadas ao caso resultam em eventos adicionais sendo registrados.  <br/> |
|Filtro de permissões de pesquisa criado  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Um filtro de permissões de pesquisa foi criado.  <br/> |
|Consulta de pesquisa criada para a preensão de caso de Descoberta e  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Uma responsabilidade baseada em consulta associada a um caso de Descoberta E foi criada.  <br/> |
|Pesquisa de conteúdo excluída  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Uma pesquisa de conteúdo existente foi excluída.  <br/> |
|Administrador de Descoberta e-Descobrir Excluído  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Um Administrador de Descoberta e Descoberta Foi excluído da sua organização.  <br/> |
|Caso de Descoberta EDiscovery excluído  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Um caso de Descoberta eDiscovery foi excluído. Qualquer responsabilidade associada à ocorrência deve ser removida antes que o caso possa ser excluído.  <br/> |
|Filtro de permissões de pesquisa excluídas  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Um filtro de permissões de pesquisa foi excluído.  <br/> |
|Consulta de pesquisa excluída para a espera de caso de Descoberta e  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Uma responsabilidade baseada em consulta associada a um caso de Descoberta eDiscovery foi excluída. Remover a consulta da espera geralmente é o resultado da exclusão de uma remoção. Quando uma consulta de espera ou de espera é excluída, os locais de conteúdo que estavam em espera são liberados.  <br/> |
|Exportação baixada da pesquisa de conteúdo  <br/> |SearchExportDownloaded  <br/> |N/D  <br/> |Um usuário baixou os resultados de uma pesquisa de conteúdo em seu computador local. Uma **exportação iniciada da atividade de pesquisa** de conteúdo deve ser iniciada antes que os resultados da pesquisa possam ser baixados.  <br/> |
|Resultados visualizados da pesquisa de conteúdo  <br/> |SearchPreviewed  <br/> |N/D  <br/> |Um usuário visualizava os resultados de uma pesquisa de conteúdo.  <br/> |
|Resultados limpos da pesquisa de conteúdo  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Um usuário limpou os resultados de uma Pesquisa de Conteúdo executando o **comando New-ComplianceSearchAction -Purge.**  <br/> |
|Análise removida da pesquisa de conteúdo  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de preparação da pesquisa de conteúdo (para preparar os resultados da pesquisa para a Descoberta Avançada) foi excluída. Se a ação de preparação tiver menos de duas semanas, os resultados da pesquisa que foram preparados para a Descoberta Avançada foram excluídos da área de armazenamento do Microsoft Azure. Se a ação de preparação tiver mais de 2 semanas, esse evento indicará que somente a ação de preparação correspondente foi excluída.  <br/> |
|Exportação removida da pesquisa de conteúdo  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de exportação de pesquisa de conteúdo foi excluída. Se a ação de exportação tiver menos de duas semanas, os resultados da pesquisa que foram carregados na área de armazenamento do Microsoft Azure foram excluídos. Se a ação de exportação tiver mais de 2 semanas, esse evento indicará que somente a ação de exportação correspondente foi excluída.  <br/> |
|Membro removido do caso de Descoberta E  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Um usuário foi removido como membro de um caso de Descoberta e.  <br/> |
|Resultados de visualização removidos da pesquisa de conteúdo  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de visualização de pesquisa de conteúdo foi excluída.  <br/> |
|Ação de limpeza removida executada na pesquisa de conteúdo  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de limpeza de pesquisa de conteúdo foi excluída.  <br/> |
|Relatório de pesquisa removido  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de relatório de exportação de pesquisa de conteúdo foi excluída.  <br/> |
|Análise iniciada da pesquisa de conteúdo  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Os resultados de uma pesquisa de conteúdo foram preparados para análise na Descoberta Avançada.  <br/> |
|Pesquisa de conteúdo iniciada  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Uma pesquisa de conteúdo foi iniciada. Quando você cria ou altera uma pesquisa de conteúdo usando a GUI do Centro de Conformidade & segurança, a pesquisa é iniciada automaticamente. Se você criar ou alterar uma pesquisa usando o cmdlet **New-ComplianceSearch** ou **Set-ComplianceSearch,** será necessário executar o cmdlet **Start-ComplianceSearch** para iniciar a pesquisa.  <br/> |
|Exportação iniciada da pesquisa de conteúdo  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Um usuário exportou os resultados de uma pesquisa de conteúdo.  <br/> |
|Relatório de exportação iniciado  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Um usuário exportou um relatório de pesquisa de conteúdo.  <br/> |
|Pesquisa de conteúdo interrompida  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Um usuário interrompeu uma pesquisa de conteúdo.  <br/> |
|(nenhum)|CaseViewed|Get-ComplianceCase|Um usuário exibiu a lista de casos na página **Descoberta** Eletrônica no centro de segurança e conformidade ou executando o cmdlet.|
|(nenhum)|SearchViewed|Get-ComplianceSearch|Um usuário exibiu a lista em  pesquisas de conteúdo (listadas na guia Pesquisas) no centro de segurança e conformidade ou executando o cmdlet. Essa atividade também é registrada quando um usuário visualiza a lista de pesquisas de conteúdo  associadas a um caso de Descoberta De eDiscovery (clicando na guia Pesquisas em um caso) ou executando o comando **Get-ComplianceSearch -Case.**|
|(nenhum)|ViewedSearchExported|Get-ComplianceSearchAction -Export|Um usuário exibiu a lista de trabalhos de exportação de pesquisa de conteúdo (listados na guia **Exportações)** no centro de segurança e conformidade ou executando o cmdlet. Essa atividade também é registrada quando um usuário visualiza a lista de trabalhos de exportação em um caso de Descoberta E (listado na guia **Exportações** em um caso) ou executando o comando **Get-ComplianceSearchAction -Case -Export.**|
|(nenhum)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|Um usuário visualiza os resultados de uma pesquisa de conteúdo no centro de segurança e conformidade ou executando o cmdlet.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Atividades de Descoberta Eletrônica Avançada

A tabela a seguir descreve as atividades de Descoberta Externa Avançada registradas no log de auditoria. Essas atividades (além de atividades relevantes de Descoberta Automática podem ser usadas para ajudá-lo a acompanhar a progressão da atividade em um caso de Descoberta Automática Avançada.

|**Nome amigável**|**Operação**|**Descrição**|
|:-----|:-----|:-----|
|Adicionar dados a outro conjunto de revisão|AddWorkingSetQueryToWorkingSet|O usuário adicionou documentos de uma revisão definida para outro conjunto de revisão.|
|Dados adicionados ao conjunto de revisão|AddQueryToWorkingSet|O usuário adicionou os resultados da pesquisa de uma pesquisa de conteúdo associada a um caso de Descoberta Eletrônica Avançada a um conjunto de revisão.|
|Dados que não são da Microsoft 365 adicionados ao conjunto de revisão|AddNonOffice365DataToWorkingSet|Usuário adicionou dados que não são da Microsoft 365 a um conjunto de revisão.|
|Documentos remedidos adicionados ao conjunto de revisão|AddRemediatedData|O usuário carrega documentos com erros de indexação corrigidos em um conjunto de revisão.|
|Dados analisados no conjunto de revisão|RunAlgo|O usuário realizou a análise nos documentos em um conjunto de revisão.|
|Documento com anotações no conjunto de revisão|AnnotateDocument|O usuário anota um documento em um conjunto de revisão. As anotações incluem a redação de conteúdo em um documento.|
|Conjuntos de carga comparados|LoadComparisonJob|O usuário comparou dois conjuntos de carga diferentes em um conjunto de revisão. Um conjunto de carga é quando os dados de uma pesquisa de conteúdo que estão associados ao caso são adicionados a um conjunto de revisão.|
|Documentos redigidos convertidos em PDF|BurnJob|O usuário converteu todos os documentos redigidos em uma revisão definida como arquivos PDF.|
|Conjunto de revisão criado|CreateWorkingSet|O usuário criou um conjunto de revisão.|
|Pesquisa de conjunto de revisão criada|CreateWorkingSetSearch|O usuário criou uma consulta de pesquisa que procura os documentos em um conjunto de revisão.|
|Marca criada|CreateTag|O usuário criou um grupo de marcas em um conjunto de revisão. Um grupo de marcas pode conter uma ou mais marcas filho. Essas marcas são usadas para marcar documentos no conjunto de revisão.|
|Pesquisa do conjunto de revisão excluído|DeleteWorkingSetSearch|O usuário excluiu uma consulta de pesquisa em um conjunto de revisão.|
|Marca excluída|DeleteTag|O usuário excluiu um grupo de marcas em um conjunto de revisão.|
|Documento baixado|DownloadDocument|O usuário baixou um documento de um conjunto de revisão.|
|Marca editada|UpdateTag|O usuário alterou uma marca em um conjunto de revisão.|
|Documentos exportados do conjunto de revisão|ExportJob|O usuário exporta documentos de um conjunto de revisão.|
|Configuração de caso modificado|UpdateCaseSettings|O usuário modifica as configurações de uma ocorrência. As configurações da ocorrência incluem informações sobre o caso, permissões de acesso e configurações que controlam o comportamento da pesquisa e da análise.|
|Pesquisa do conjunto de revisão modificada|UpdateWorkingSetSearch|O usuário editou uma consulta de pesquisa em um conjunto de revisão.|
|Pesquisa do conjunto de revisão vizualizada|PreviewWorkingSetSearch|O usuário visualizou os resultados de uma consulta de pesquisa em um conjunto de revisão.|
|Documentos de erro corrigidos|ErrorRemediationJob|O usuário corrige os arquivos que contêm erros de indexação.|
|Documento marcado|TagFiles|O usuário marca um documento em um conjunto de revisão.|
|Resultados marcados de uma consulta|TagJob|O usuário marca todos os documentos que correspondem aos critérios da consulta de pesquisa em um conjunto de revisão.|
|Documento exibido no conjunto de revisão|ViewDocument|O usuário visualiza um documento em um conjunto de revisão.|
|||

## <a name="ediscovery-cmdlet-activities"></a>Atividades de cmdlet de Descoberta Eletrônica

A tabela a seguir lista os registros de log de auditoria de cmdlet que são registrados quando um administrador ou usuário executa uma atividade relacionada à Descoberta Eletrônica usando o Centro de Conformidade do & de Segurança ou executando o cmdlet correspondente no PowerShell remoto que está conectado ao Centro de Conformidade & Segurança da sua organização. As informações detalhadas no registro de log de auditoria são diferentes para as atividades de cmdlet listadas nesta tabela e as atividades de Descoberta Eletrônica descritas na seção anterior.
  
Como mencionado anteriormente, leva até 24 horas para que as atividades de cmdlet de Descoberta Eletrônica apareçam nos resultados da pesquisa de log de auditoria.
  
> [!TIP]
> Os cmdlets na coluna **Operação** na tabela a seguir são vinculados ao tópico de ajuda de cmdlet correspondente no TechNet. Vá até o tópico de ajuda do cmdlet para ver uma descrição dos parâmetros disponíveis para cada cmdlet. O parâmetro e o valor do parâmetro que foram usados com um cmdlet são incluídos na entrada de log de auditoria para cada atividade de cmdlet de Descoberta Eletrônica registrada. 
  
|**Nome amigável**|**Operação (cmdlet)**|**Descrição**|
|:-----|:-----|:-----|
|Ressução criada no caso de Descoberta Desdiscovery  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |Uma responsabilidade foi criada para um caso de Descoberta E. Uma espera pode ser criada com ou sem especificar uma fonte de conteúdo. Se as fontes de conteúdo são especificadas, elas serão identificadas na entrada do log de auditoria.  <br/> |
|Reter excluído do caso de Descoberta E  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |Uma isenção associada a um caso de Descoberta Desdiscovery foi excluída. A exclusão de uma espera libera todos os locais de conteúdo da espera. A exclusão da união também resulta na exclusão das regras de espera de caso associadas à união (consulte **Remove-CaseHoldRule** abaixo).  <br/> |
|Ressução alterada no caso de Descoberta e  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |Uma responsabilidade associada a uma Descoberta eDiscovery foi alterada. As alterações possíveis incluem adicionar ou remover locais de conteúdo ou desativar (desabilitar) a espera.  <br/> |
|Consulta de pesquisa criada para a preensão de caso de Descoberta e  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |Uma responsabilidade baseada em consulta associada a um caso de Descoberta E foi criada.  <br/> |
|Consulta de pesquisa excluída para a espera de caso de Descoberta e  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |Uma responsabilidade baseada em consulta associada a um caso de Descoberta eDiscovery foi excluída. Remover a consulta da espera geralmente é o resultado da exclusão de uma remoção. Quando uma consulta de espera ou de espera é excluída, os locais de conteúdo que estavam em espera são liberados.  <br/> |
|Consulta de pesquisa alterada para a preensão de caso de Descoberta e  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |Uma responsabilidade baseada em consulta associada a um caso de Descoberta E foi alterada. As alterações possíveis incluem a edição da consulta ou intervalo de datas para uma espera baseada em consulta.  <br/> |
|Caso de Descoberta Desdiscovery criado  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |Foi criado um caso de Descoberta eDiscovery. Quando um caso é criado, você só precisa dar um nome a ele. Outras tarefas relacionadas a casos, como adicionar membros, criar respeções e criar pesquisas de conteúdo associadas ao caso resultam em eventos adicionais sendo registrados.  <br/> |
|Caso de Descoberta EDiscovery excluído  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |Um caso de Descoberta eDiscovery foi excluído. Qualquer responsabilidade associada à ocorrência deve ser removida antes que o caso possa ser excluído.  <br/> |
|Caso de Descoberta eDiscovery alterado  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |Um caso de Descoberta E Foi alterado. As alterações incluem fechar um caso aberto ou reabrir um caso fechado.  <br/> |
|Membro adicionado ao caso de Descoberta E  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |Um usuário foi adicionado como membro de um caso de Descoberta e. Como membro de uma ocorrência, um usuário pode executar várias tarefas relacionadas a casos, dependendo se as permissões necessárias foram atribuídas.  <br/> |
|Membro removido do caso de Descoberta E  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |Um usuário foi removido como membro de um caso de Descoberta e.  <br/> |
|Associação de caso de Descoberta E Alterada  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |A lista de associação de um caso de Descoberta E foi alterada. Essa atividade é registrada quando todos os membros são substituídos por um grupo de novos usuários. Se um único membro for adicionado ou removido, a **operação Add-ComplianceCaseMember** **ou Remove-ComplianceCaseMember** será registrada.  <br/> |
|Pesquisa de conteúdo criada  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |Uma nova pesquisa de conteúdo foi criada.  <br/> |
|Pesquisa de conteúdo excluída  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |Uma pesquisa de conteúdo existente foi excluída.  <br/> |
|Pesquisa de conteúdo alterada  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |Uma pesquisa de conteúdo existente foi alterada. As alterações podem incluir adicionar ou remover locais de conteúdo pesquisados e editar a consulta de pesquisa.  <br/> |
|Pesquisa de conteúdo iniciada  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |Uma pesquisa de conteúdo foi iniciada. Quando você cria ou altera uma pesquisa de conteúdo usando a GUI do Centro de Conformidade & segurança, a pesquisa é iniciada automaticamente. Se você criar ou alterar uma pesquisa usando o cmdlet **New-ComplianceSearch** ou **Set-ComplianceSearch,** será necessário executar o cmdlet **Start-ComplianceSearch** para iniciar a pesquisa.  <br/> |
|Pesquisa de conteúdo interrompida  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |Uma pesquisa de conteúdo que estava em execução foi interrompida.  <br/> |
|Ação de pesquisa de conteúdo criada  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |Uma ação de pesquisa de conteúdo foi criada. As ações de pesquisa de conteúdo incluem a visualização de resultados da pesquisa, a exportação de resultados da pesquisa, a preparação dos resultados da pesquisa para análise na Descoberta Avançada e a exclusão permanente de itens que corresponderem aos critérios de pesquisa de uma pesquisa de conteúdo.  <br/> |
|Ação de pesquisa de conteúdo excluída  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |Uma ação de pesquisa de conteúdo foi excluída.  <br/> |
|Filtro de permissões de pesquisa criado  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |Um filtro de permissões de pesquisa foi criado.  <br/> |
|Filtro de permissões de pesquisa excluídas  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |Um filtro de permissões de pesquisa foi excluído.  <br/> |
|Filtro de permissões de pesquisa alterado  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |Um filtro de permissões de pesquisa foi alterado.  <br/> |
|Administrador criado de Descoberta e  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |Um usuário foi adicionado como Administrador de Descobertas Esdiscovery em sua organização.  <br/> |
|Administrador de Descoberta e-Descobrir Excluído  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |Um Administrador de Descoberta e Descoberta Foi excluído da sua organização.  <br/> |
|Associação de administrador de Descobertas E Alteradas  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |A lista de Administradores de Descobertas Desdiscovery em sua organização foi alterada. Essa atividade é registrada quando a lista de Administradores de Descoberta Externa é substituída por um grupo de novos usuários. Se um único usuário for adicionado ou removido, a operação **Add-eDiscoveryCaseAdmin** ou **Remove-eDiscoveryCaseAdmin** será registrada.  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>Propriedades detalhadas para atividades de Descoberta e

A tabela a seguir descreve as propriedades  incluídas  quando você clica em Mais informações na página Detalhes de uma atividade de Descoberta Externa listada nos resultados da pesquisa. Essas propriedades também são incluídas no arquivo CSV quando você exporta os resultados da pesquisa de log de auditoria. Um registro de log de auditoria para uma atividade de Descoberta Externa não incluirá todas as propriedades detalhadas listadas abaixo. 
  
> [!TIP]
> Quando você exporta os resultados da pesquisa, o arquivo CSV contém uma coluna chamada **Detail**, que contém as propriedades detalhadas descritas na tabela a seguir em uma propriedade de vários valores. Você pode usar o recurso Consulta do Power no Excel para dividir essa coluna em várias colunas para que cada propriedade tenha sua própria coluna. Isso permitirá classificar e filtrar uma ou mais dessas propriedades. Para obter mais informações, consulte a seção "Exportar os resultados da pesquisa para um arquivo" em [Pesquisar o log de auditoria](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Propriedade**|**Descrição**|
|:-----|:-----|
|Caso  <br/> |A identidade (GUID) do caso de Descoberta Digital que foi criado, alterado ou excluído.  <br/> |
|ClientApplication  <br/> |As atividades de cmdlet de Descoberta Eletrônica têm um valor **do EMC** para essa propriedade. Isso indica que a atividade foi executada usando a GUI do Centro de Conformidade & segurança ou executando o cmdlet no PowerShell.  <br/> |
|ClientIP  <br/> |O endereço IP do dispositivo que foi usado quando a atividade foi registrada. O endereço IP é exibido em um formato de endereço IPv4 ou IPv6.  <br/> |
|ClientRequestId  <br/> | Para atividades de Descoberta Livre, essa propriedade normalmente está em branco.  <br/> |
|CmdletVersion  <br/> |O número de com build da versão do Centro de Conformidade & segurança em execução em sua organização.  <br/> |
|CreationTime  <br/> |A data e a hora em UtC (Tempo Universal Coordenado) quando a atividade de Descoberta e Descoberta Foi concluída.  <br/> |
|EffectiveOrganization  <br/> |O nome da organização do Microsoft 365.  <br/> |
|ExchangeLocations  <br/> |As caixas de correio do Exchange Online incluídas em uma pesquisa de conteúdo ou colocadas em espera em um caso de Descoberta Eletrônico.  <br/> |
|Exclusões  <br/> |Caixas de correio ou locais de site excluídos de uma pesquisa de conteúdo ou de uma responsabilidade em um caso de Descoberta Eletrônico.  <br/> |
|ExtendedProperties  <br/> |Propriedades adicionais de uma pesquisa de conteúdo, de uma ação de pesquisa de conteúdo ou de uma ocorrência de Descoberta Eletrônica, como o GUID do objeto e os parâmetros de cmdlet e cmdlet correspondentes que foram usados quando a atividade foi executada.  <br/> |
|Id  <br/> |A ID da entrada do relatório. A ID identifica exclusivamente a entrada do log de auditoria.  <br/> |
|NonPIIParameters  <br/> |Uma lista dos parâmetros (sem nenhum valor) que foram usados com o cmdlet identificado na propriedade Operation. Os parâmetros listados nesta propriedade são os mesmos listados na propriedade Parameters.  <br/> |
|ObjectId  <br/> |O GUID ou o nome do objeto (por exemplo, uma Pesquisa de Conteúdo ou um caso de Descoberta De Conteúdo) que foi criado, alterado ou excluído pela atividade listada na propriedade Operation. Esse objeto também é identificado na coluna Item nos resultados da pesquisa de log de auditoria.  <br/> |
|ObjectType  <br/> |O tipo de objeto eDiscovery que o usuário criou, excluiu ou modificou; por exemplo, uma ação de pesquisa de conteúdo (visualização, exportação ou limpeza), um caso de Descoberta E ou uma pesquisa de conteúdo.  <br/> |
|Operação  <br/> |O nome da operação que corresponde à atividade de Descoberta e Que foi executada.  <br/> |
|OrganizationId  <br/> |O GUID da sua organização do Microsoft 365.  <br/> |
|Parâmetros  <br/> |O nome e o valor dos parâmetros que foram usados com o cmdlet correspondente.  <br/> |
|PublicFolderLocations  <br/> |Os locais de pasta pública no Exchange Online incluídos em uma pesquisa de conteúdo ou colocados em espera em um caso de Descoberta Virtual.  <br/> |
|Consulta  <br/> |A consulta de pesquisa associada à atividade, como uma pesquisa de conteúdo ou uma espera baseada em consulta.  <br/> |
|RecordType  <br/> |O tipo de operação indicado pelo registro. O valor **18** indica um evento relacionado a uma atividade listada na seção [atividades do cmdlet eDiscovery.](#ediscovery-cmdlet-activities) Um valor **de 24** indica um evento relacionado a uma atividade listada na seção Como pesquisar e exibir atividades de [Descoberta](#how-to-search-for-and-view-ediscovery-activities) Externa.  <br/> |
|ResultStatus  <br/> |Indica se a ação (especificada na propriedade Operation) foi bem-sucedida ou não.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica que a atividade foi um evento & Centro de Conformidade. Todas as atividades de Descoberta Livre terão um valor **0** para essa propriedade.  <br/> |
|SharepointLocations  <br/> |Os sites do SharePoint Online incluídos em uma pesquisa de conteúdo ou colocados em espera em um caso de Descoberta Virtual.  <br/> |
|StartTime  <br/> |A data e a hora em UtC (Tempo Universal Coordenado) quando a atividade de Descoberta e Descoberta Foi iniciada.  <br/> |
|UserId  <br/> |O usuário que realizou a atividade (especificada na propriedade Operation) que resultou no registro sendo registrado. Registros para atividades de Descoberta Eletrônico realizadas por contas do sistema (como NT AUTHORITY\SYSTEM) também são incluídos no log de auditoria.  <br/> |
|UserKey  <br/> |Uma ID alternativa para o usuário identificado na propriedade UserId. Para atividades de Descoberta e, em geral, o valor dessa propriedade é o mesmo da propriedade UserId.  <br/> |
|UserServicePlan  <br/> |A assinatura usada pela sua organização. Para atividades de Descoberta Livre, essa propriedade normalmente está em branco.  <br/> |
|UserType  <br/> |O tipo de usuário que executou a operação. Os valores a seguir indicam o tipo de usuário.  <br/> 0 Um usuário normal. 2 Um administrador em sua organização. 3 Um administrador de datacenter da Microsoft ou uma conta do sistema de datacenter. 4 Uma conta do sistema. 5 Um aplicativo. 6 Uma entidade de serviço. |
|Versão  <br/> |Indica o número da versão da atividade (identificada pela propriedade Operation) que está registrada.  <br/> |
|Workload  <br/> |Oserviço em que a atividade ocorreu. Para atividades de Descoberta Digital, o valor **é SecurityComplianceCenter**.  <br/> |