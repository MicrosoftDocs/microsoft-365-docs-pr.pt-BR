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
description: Saiba quais eventos são registrados quando os usuários com permissões de Descoberta eDiscovery atribuídas executam tarefas de Pesquisa de conteúdo, Descoberta Básica e Advanced eDiscovery no centro de conformidade Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cca0cdc02e2c23231637acf6eba2b07144266e36
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888404"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Procurar atividades de descoberta eletrônica no log de auditoria

Atividades relacionadas à Pesquisa de Conteúdo e Descoberta Eletrônica (para Descoberta Eletrônica Principal e Advanced eDiscovery) executadas no centro de conformidade do Microsoft 365 ou executando os cmdlets do PowerShell correspondentes são registradas no log de auditoria. Os eventos são registrados quando os administradores ou gerentes de Descoberta eDiscovery (ou qualquer permissão de Descoberta eDiscovery atribuída pelo usuário) executam as seguintes tarefas de Pesquisa de Conteúdo e Descoberta Básica de Descoberta Microsoft 365 no centro de conformidade do Microsoft 365:
  
- Criando e gerenciando o Core e Advanced eDiscovery casos

- Criando, iniciando e editando pesquisas de conteúdo

- Executar ações de pesquisa, como visualização, exportação e exclusão de resultados de pesquisa

- Gerenciando custodiantes e conjuntos de revisão Advanced eDiscovery

- Configurando a filtragem de permissões para pesquisa de conteúdo

- Gerenciar a função de administrador de Descoberta Eletrônica
  
Para obter mais informações sobre como pesquisar o log de auditoria, as permissões necessárias e exportar resultados de pesquisa, consulte Pesquisar o log de auditoria no centro de conformidade Microsoft 365 [.](search-the-audit-log-in-security-and-compliance.md)
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Como pesquisar e exibir atividades de Descoberta

Atualmente, você precisa fazer algumas coisas específicas para exibir as atividades de Descoberta e No log de auditoria. Veja como.
  
1. Vá até <https://compliance.microsoft.com> e entre usando uma conta corporativa ou de estudante.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Auditoria**.

3. Na lista **lista** da Atividades, em **Atividades** de Descoberta Advanced eDiscovery atividades, **clique** em uma ou mais atividades para pesquisar.

    > [!NOTE]
    > A **lista** lista listada Atividades também inclui um grupo de atividades denominadas **atividades de cmdlet de Descoberta** Eletrônica que retornarão registros do log de auditoria do cmdlet.
  
4. Selecione um intervalo de datas e horas para exibir eventos de Descoberta E que ocorreram nesse período.

5. Na caixa **Usuários,** selecione um ou mais usuários para exibir os resultados da pesquisa. Deixe essa caixa em branco para retornar entradas para todos os usuários.

6. Clique em **Pesquisar** para executar a pesquisa usando seus critérios de pesquisa. 

7. Depois que os resultados da pesquisa são exibidos, você pode clicar em **Filtrar resultados** para filtrar ou classificar os registros de atividade resultantes. Infelizmente, você não pode usar a filtragem para excluir explicitamente determinadas atividades. 

8. Para exibir detalhes sobre uma atividade, clique no registro de atividades na lista de resultados da pesquisa. 

    Uma **página de** sobrevoo Detalhes é exibida que contém as propriedades detalhadas do registro de evento. Para exibir detalhes adicionais, clique **em Mais informações.** Para uma descrição dessas propriedades, consulte a [seção Propriedades detalhadas para atividades de Descoberta](#detailed-properties-for-ediscovery-activities) e.

9. Se desejado, você pode exportar os resultados da pesquisa de log de auditoria para um arquivo CSV e, em seguida, usar o recurso Excel Consulta do Power para formatar e filtrar esses registros. Para saber mais, confira [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>Atividades de Descoberta Eletrônica

A tabela a seguir descreve as atividades de Pesquisa de Conteúdo e Descoberta Básica de eDiscovery que são registradas quando um administrador ou gerente de Descoberta eDiscovery executa uma atividade relacionada à Descoberta eDiscovery usando o centro de conformidade Microsoft 365. Algumas atividades realizadas Advanced eDiscovery podem ser retornadas quando você pesquisa atividades nesta lista.
  
> [!NOTE]
> As atividades de Descoberta Eletrônica descritas nesta seção fornecem informações semelhantes às atividades de cmdlet de Descoberta Eletrônica descritas na próxima seção. Recomendamos que você use as atividades de Descoberta Externa descritas nesta seção porque elas aparecerão nos resultados da pesquisa de log de auditoria dentro de 30 minutos. Pode levar até 24 horas para que as atividades de cmdlet de Descoberta Eletrônica apareçam nos resultados da pesquisa de log de auditoria.
  
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
|Item de visualização de pesquisa de conteúdo listado  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Um usuário clicou em **Visualizar** resultados da pesquisa para exibir a página de resultados da pesquisa de visualização, que lista até 1.000 itens dos resultados de uma pesquisa.  <br/> |
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
|Resultados limpos da pesquisa de conteúdo  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Um usuário limpou os resultados de uma pesquisa de conteúdo executando o **comando New-ComplianceSearchAction -Purge.**  <br/> |
|Análise removida da pesquisa de conteúdo  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de preparação da pesquisa de conteúdo (para preparar os resultados da pesquisa Advanced eDiscovery) foi excluída. Se a ação de preparação tiver menos de duas semanas, os resultados da pesquisa que foram preparados para Advanced eDiscovery foram excluídos da área de Microsoft Azure de armazenamento. Se a ação de preparação tiver mais de 2 semanas, esse evento indicará que somente a ação de preparação correspondente foi excluída.  <br/> |
|Exportação removida da pesquisa de conteúdo  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de exportação de pesquisa de conteúdo foi excluída. Se a ação de exportação tiver menos de duas semanas, os resultados da pesquisa que foram carregados na área de armazenamento Microsoft Azure foram excluídos. Se a ação de exportação tiver mais de 2 semanas, esse evento indicará que somente a ação de exportação correspondente foi excluída.  <br/> |
|Membro removido do caso de Descoberta E  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Um usuário foi removido como membro de um caso de Descoberta e.  <br/> |
|Resultados de visualização removidos da pesquisa de conteúdo  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de visualização de pesquisa de conteúdo foi excluída.  <br/> |
|Ação de limpeza removida executada na pesquisa de conteúdo  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de limpeza de pesquisa de conteúdo foi excluída.  <br/> |
|Relatório de pesquisa removido  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de relatório de exportação de pesquisa de conteúdo foi excluída.  <br/> |
|Análise iniciada da pesquisa de conteúdo  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Os resultados de uma pesquisa de conteúdo foram preparados para análise em Advanced eDiscovery.  <br/> |
|Pesquisa de conteúdo iniciada  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Uma pesquisa de conteúdo foi iniciada. Quando você cria ou altera uma pesquisa de conteúdo usando o Microsoft 365 de conformidade, a pesquisa é iniciada automaticamente.<br/> |
|Exportação iniciada da pesquisa de conteúdo  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Um usuário exportou os resultados de uma pesquisa de conteúdo.  <br/> |
|Relatório de exportação iniciado  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Um usuário exportou um relatório de pesquisa de conteúdo.  <br/> |
|Pesquisa de conteúdo interrompida  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Um usuário interrompeu uma pesquisa de conteúdo.  <br/> |
|(nenhum)|CaseViewed|Get-ComplianceCase|Um usuário exibiu um caso core de Descoberta eDiscovery no centro de conformidade. O registro de auditoria para esse evento inclui o nome do caso que foi exibido. |
|(nenhum)|SearchViewed|Get-ComplianceSearch|Um usuário exibiu uma pesquisa de conteúdo no  centro de conformidade acessando a pesquisa na guia Pesquisas em um caso de Descoberta Interna ou acessando-a na página de pesquisa **de** conteúdo. O registro de auditoria para esse evento inclui a identidade da pesquisa que foi exibida.|
|(nenhum)|ViewedSearchExported|Get-ComplianceSearchAction -Export|Um usuário exibiu uma exportação de pesquisa de conteúdo no centro de conformidade acessando a exportação na guia **Exportações** na página **Pesquisa de** conteúdo. Essa atividade também é registrada quando um usuário visualiza uma exportação associada a um caso de Descoberta Interna.|
|(nenhum)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|Um usuário visualizava os resultados de uma pesquisa de conteúdo no centro de conformidade. Essa atividade também é registrada quando um usuário visualiza os resultados de uma pesquisa associada a um caso de Descoberta Interna.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Atividades de Descoberta Eletrônica Avançada

A tabela a seguir descreve as Advanced eDiscovery registradas no log de auditoria. Essas atividades podem ser usadas para ajudá-lo a acompanhar a progressão da atividade em um Advanced eDiscovery caso.

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

A tabela a seguir lista os registros de log de auditoria de cmdlet que são registrados quando um administrador ou usuário executa uma atividade relacionada à Descoberta Eletrônica usando o centro de conformidade ou executando o cmdlet correspondente no Centro de Conformidade e Segurança & do PowerShell. As informações detalhadas no registro de log de auditoria são diferentes para as atividades de cmdlet listadas nesta tabela e as atividades de Descoberta Eletrônica descritas na seção anterior.
  
Conforme mencionado anteriormente, pode levar até 24 horas para que as atividades de cmdlet de Descoberta Eletrônica apareçam nos resultados da pesquisa de log de auditoria.
  
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
|Pesquisa de conteúdo iniciada  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |Uma pesquisa de conteúdo foi iniciada. Quando você cria ou altera uma pesquisa de conteúdo usando a GUI do centro de conformidade, a pesquisa é iniciada automaticamente. Se você criar ou alterar uma pesquisa usando o cmdlet **New-ComplianceSearch** ou **Set-ComplianceSearch,** será necessário executar o cmdlet **Start-ComplianceSearch** para iniciar a pesquisa.  <br/> |
|Pesquisa de conteúdo interrompida  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |Uma pesquisa de conteúdo que estava em execução foi interrompida.  <br/> |
|Ação de pesquisa de conteúdo criada  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |Uma ação de pesquisa de conteúdo foi criada. As ações de pesquisa de conteúdo incluem a visualização de resultados da pesquisa, a exportação de resultados da pesquisa, a preparação dos resultados da pesquisa para análise no Advanced eDiscovery e a exclusão permanente de itens que corresponderem aos critérios de pesquisa de uma pesquisa de conteúdo.  <br/> |
|Ação de pesquisa de conteúdo excluída  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |Uma ação de pesquisa de conteúdo foi excluída.  <br/> |
|Filtro de permissões de pesquisa criado  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |Um filtro de permissões de pesquisa foi criado.  <br/> |
|Filtro de permissões de pesquisa excluídas  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |Um filtro de permissões de pesquisa foi excluído.  <br/> |
|Filtro de permissões de pesquisa alterado  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |Um filtro de permissões de pesquisa foi alterado.  <br/> |
|Administrador criado de Descoberta e  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |Um usuário foi adicionado como Administrador de Descobertas Esdiscovery em sua organização.  <br/> |
|Administrador de Descoberta e-Descobrir Excluído  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |Um Administrador de Descoberta e Descoberta Foi excluído da sua organização.  <br/> |
|Associação de administrador de Descobertas E Alteradas  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |A lista de Administradores de Descobertas Desdiscovery em sua organização foi alterada. Essa atividade é registrada quando a lista de Administradores de Descoberta Externa é substituída por um grupo de novos usuários. Se um único usuário for adicionado ou removido, a operação **Add-eDiscoveryCaseAdmin** ou **Remove-eDiscoveryCaseAdmin** será registrada.  <br/> |
|(nenhum)|[Get-ComplianceCase](/powershell/module/exchange/get-compliancecase) <br/>|Essa atividade é registrada quando um usuário visualiza uma lista de principais casos de Descoberta Advanced eDiscovery. Essa atividade também é registrada quando um usuário visualiza um caso específico no Core eDiscovery. Quando um usuário visualiza um caso específico, o registro de auditoria inclui a identidade do caso que foi exibido. Se o usuário exibiu apenas uma lista de casos, o registro de auditoria não contém uma identidade de caso.|
|(nenhum)|[Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)|Essa atividade é registrada quando um usuário visualiza uma lista de pesquisas de conteúdo ou pesquisas associadas a um caso de Descoberta Interna. Essa atividade também é registrada quando um usuário visualiza uma pesquisa de Conteúdo específica ou visualiza uma pesquisa específica associada a um caso de Descoberta Principal. Quando um usuário visualiza uma pesquisa específica, o registro de auditoria inclui a identidade da pesquisa que foi exibida. Se o usuário exibiu apenas uma lista de pesquisas, o registro de auditoria não contém uma identidade de pesquisa.
|(nenhum)|[Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)|Essa atividade é registrada quando um usuário visualiza uma lista de ações de pesquisa de conformidade (como exportações, visualizações ou limpezas) ou ações associadas a um caso de Descoberta Principal de Descoberta Externa. Essa atividade também é registrada quando um usuário visualiza uma ação de pesquisa de conformidade específica (como uma exportação) ou visualiza uma ação específica associada a um caso core de Descoberta eDiscovery. Quando um usuário visualiza uma ação de pesquisa, o registro de auditoria inclui a identidade da ação de pesquisa que foi exibida. Se o usuário exibiu apenas uma lista de ações, o registro de auditoria não contém uma identidade de ação.|
||||

## <a name="detailed-properties-for-ediscovery-activities"></a>Propriedades detalhadas para atividades de Descoberta e

A tabela a seguir descreve as propriedades  incluídas  quando você clica em Mais informações na página Detalhes de uma atividade de Descoberta Externa listada nos resultados da pesquisa. Essas propriedades também são incluídas no arquivo CSV quando você exporta os resultados da pesquisa de log de auditoria. Um registro de log de auditoria para uma atividade de Descoberta Externa não incluirá todas as propriedades detalhadas listadas abaixo.
  
> [!TIP]
> Quando você exporta os resultados da pesquisa, o arquivo CSV contém uma coluna chamada **Detail**, que contém as propriedades detalhadas descritas na tabela a seguir em uma propriedade de vários valores. Você pode usar o recurso De consulta do Power Excel dividir essa coluna em várias colunas para que cada propriedade tenha sua própria coluna. Isso permitirá classificar e filtrar uma ou mais dessas propriedades. Para obter mais informações, consulte a seção "Exportar os resultados da pesquisa para um arquivo" em [Pesquisar o log de auditoria](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Property**|**Descrição**|
|:-----|:-----|
|Caso  <br/> |A identidade (GUID) do caso de Descoberta Digital que foi criado, alterado ou excluído.  <br/> |
|ClientApplication  <br/> |As atividades de cmdlet de Descoberta Eletrônica têm um valor **do EMC** para essa propriedade. Isso indica que a atividade foi executada usando a GUI do centro de conformidade ou executando o cmdlet no PowerShell.  <br/> |
|ClientIP  <br/> |O endereço IP do dispositivo que foi usado quando a atividade foi registrada. O endereço IP é exibido em um formato de endereço IPv4 ou IPv6.  <br/> |
|ClientRequestId  <br/> | Para atividades de Descoberta Livre, essa propriedade normalmente está em branco.  <br/> |
|CmdletVersion  <br/> |O número de com build da versão do centro de conformidade em execução em sua organização.  <br/> |
|CreationTime  <br/> |A data e a hora em UtC (Tempo Universal Coordenado) quando a atividade de Descoberta e Descoberta Foi concluída.  <br/> |
|EffectiveOrganization  <br/> |O nome da organização do Microsoft 365.  <br/> |
|ExchangeLocations  <br/> |As Exchange Online caixas de correio incluídas em uma pesquisa de conteúdo ou colocadas em espera em um caso de Descoberta Eletrônico.  <br/> |
|Exclusões  <br/> |Caixas de correio ou locais de site excluídos de uma pesquisa de conteúdo ou de uma responsabilidade em um caso de Descoberta Eletrônico.  <br/> |
|ExtendedProperties  <br/> |Propriedades adicionais de uma pesquisa de conteúdo, de uma ação de pesquisa de conteúdo ou de uma ocorrência de Descoberta Eletrônica, como o GUID do objeto e os parâmetros de cmdlet e cmdlet correspondentes que foram usados quando a atividade foi executada.  <br/> |
|Id  <br/> |A ID da entrada do relatório. A ID identifica exclusivamente a entrada do log de auditoria.  <br/> |
|NonPIIParameters  <br/> |Uma lista dos parâmetros (sem nenhum valor) que foram usados com o cmdlet identificado na propriedade Operation. Os parâmetros listados nesta propriedade são os mesmos listados na propriedade Parameters.  <br/> |
|ObjectId  <br/> |O GUID ou o nome do objeto (por exemplo, uma pesquisa de conteúdo ou um caso de Descoberta Principal) que foi criado, acessado, alterado ou excluído pela atividade listada na propriedade Operation. Esse objeto também é identificado na coluna Item nos resultados da pesquisa de log de auditoria.  <br/> |
|ObjectType  <br/> |O tipo de objeto eDiscovery que o usuário criou, excluiu ou modificou; por exemplo, uma ação de pesquisa de conteúdo (visualização, exportação ou limpeza), um caso de Descoberta E ou uma pesquisa de conteúdo.  <br/> |
|Operação  <br/> |O nome da operação que corresponde à atividade de Descoberta e Que foi executada.  <br/> |
|OrganizationId  <br/> |O GUID para sua Microsoft 365 organização.  <br/> |
|Parâmetros  <br/> |O nome e o valor dos parâmetros que foram usados com o cmdlet correspondente.  <br/> |
|PublicFolderLocations  <br/> |Os locais de pasta pública em Exchange Online que são incluídos em uma pesquisa de conteúdo ou colocados em espera em um caso de Descoberta E.  <br/> |
|Consulta  <br/> |A consulta de pesquisa associada à atividade, como uma pesquisa de conteúdo ou uma espera baseada em consulta.  <br/> |
|RecordType  <br/> |O tipo de operação indicado pelo registro. O valor **18** indica um evento relacionado a uma atividade listada na seção [atividades do cmdlet eDiscovery.](#ediscovery-cmdlet-activities) Um valor **de 24** indica um evento relacionado a uma atividade listada na seção Como pesquisar e exibir atividades de [Descoberta](#how-to-search-for-and-view-ediscovery-activities) Externa.  <br/> |
|ResultStatus  <br/> |Indica se a ação (especificada na propriedade Operation) foi bem-sucedida ou não.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica que a atividade foi um evento do centro de conformidade. Todas as atividades de Descoberta Livre terão um valor **0** para essa propriedade.  <br/> |
|SharepointLocations  <br/> |Os SharePoint online incluídos em uma pesquisa de conteúdo ou colocados em espera em um caso de Descoberta Virtual.  <br/> |
|StartTime  <br/> |A data e a hora em UtC (Tempo Universal Coordenado) quando a atividade de Descoberta e Descoberta Foi iniciada.  <br/> |
|UserId  <br/> |O usuário que realizou a atividade (especificada na propriedade Operation) que resultou no registro sendo registrado. Registros para atividades de Descoberta Eletrônico realizadas por contas do sistema (como NT AUTHORITY\SYSTEM) também são incluídos no log de auditoria.  <br/> |
|UserKey  <br/> |Uma ID alternativa para o usuário identificado na propriedade UserId. Para atividades de Descoberta e, em geral, o valor dessa propriedade é o mesmo da propriedade UserId.  <br/> |
|UserServicePlan  <br/> |A assinatura usada pela sua organização. Para atividades de Descoberta Livre, essa propriedade normalmente está em branco.  <br/> |
|UserType  <br/> |O tipo de usuário que executou a operação. Os valores a seguir indicam o tipo de usuário.  <br/> 0 Um usuário normal. 2 Um administrador em sua organização. 3 Um administrador de datacenter da Microsoft ou uma conta do sistema de datacenter. 4 Uma conta do sistema. 5 Um aplicativo. 6 Uma entidade de serviço. |
|Versão  <br/> |Indica o número da versão da atividade (identificada pela propriedade Operation) que está registrada.  <br/> |
|Workload  <br/> |O serviço em que a atividade ocorreu. Para atividades de Descoberta Digital, o valor **é SecurityComplianceCenter**.  <br/> |
