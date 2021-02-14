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
description: Saiba quais eventos são registrados quando os usuários com permissões de Descoberta eDiscovery atribuídas executam tarefas de Pesquisa de Conteúdo e Descobertas Principais no Centro de Conformidade & Segurança.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 529e1a0ac3dc66ac15bd1b3fbcde466fb36d5f4e
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357541"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Procurar atividades de descoberta eletrônica no log de auditoria

Atividades relacionadas à Pesquisa de Conteúdo e Descoberta Eletrônica (para Descoberta Eletrônica Principal e Descoberta Eletrônica Avançada) executadas no Centro de Conformidade do & de Segurança ou pela execução dos cmdlets do PowerShell correspondentes são registradas no log de auditoria. Os eventos são registrados quando os administradores ou gerentes de Descoberta eDiscovery (ou qualquer usuário com permissões de Descoberta eDiscovery) executam as seguintes tarefas de Pesquisa de Conteúdo e Descobertas Principais no Centro de Conformidade & Segurança:
  
- Criando e gerenciando ocorrências de Descobertas Principais e Avançadas

- Criar, iniciar e editar pesquisas de conteúdo

- Executar ações de pesquisa de conteúdo, como visualização, exportação e exclusão de resultados de pesquisa

- Gerenciando custodiantes e conjuntos de revisão na Descoberta Avançada

- Configurar a filtragem de permissões para pesquisa de conteúdo

- Gerenciar a função de administrador de Descoberta Eletrônica

> [!IMPORTANT]
> As atividades descritas neste artigo são apenas o resultado de tarefas de Descoberta eDiscovery realizadas usando o Centro de Conformidade & Segurança. As tarefas de Descoberta e Que foram executadas usando a ferramenta In-Place Descoberta eDiscovery no Exchange Online ou o Centro de Descobertas No SharePoint Online não estão incluídas. 
  
Para obter mais informações sobre como pesquisar o log de auditoria, as permissões necessárias e exportar resultados de pesquisa, consulte Pesquisar o log de auditoria no Centro de Conformidade e Segurança [&.](search-the-audit-log-in-security-and-compliance.md)
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Como pesquisar e exibir atividades de Descoberta

Atualmente, você precisa fazer algumas coisas específicas para exibir as atividades de Descoberta eDiscovery no log de auditoria. Veja como.
  
1. Acesse [https://protection.office.com](https://protection.office.com).

2. Entre usando sua conta de trabalho ou da escola.

3. No painel esquerdo, clique em **Pesquisar** e clique em **Pesquisa de log de auditoria.**

4. Na lista **de** Atividades,  em Atividades, em Atividades de Descoberta e ou Atividades de Descoberta **Avançada,** clique em uma ou mais atividades para pesquisar.

    > [!NOTE]
    > A **lista** drop-down Atividades também inclui um grupo de atividades chamadas **atividades de cmdlet** de Descoberta Eletrônica que retornarão registros do log de auditoria do cmdlet.
  
5. Selecione um intervalo de datas e horas para exibir os eventos de Descoberta eDiscovery que ocorreram dentro desse período. 

6. Na caixa **Usuários,** selecione um ou mais usuários para exibir os resultados da pesquisa. Deixe essa caixa em branco para retornar entradas para todos os usuários.

7. Clique em **Pesquisar** para executar a pesquisa usando seus critérios de pesquisa. 

8. Depois que os resultados da pesquisa são exibidos, você pode clicar em Filtrar **resultados** para filtrar ou classificar os registros de atividade resultantes. Infelizmente, você não pode usar a filtragem para excluir explicitamente determinadas atividades. 

9. Para exibir detalhes sobre uma atividade, clique no registro de atividade na lista de resultados da pesquisa. 

    É **exibida uma** página de detalhes que contém as propriedades detalhadas do registro de evento. Para exibir detalhes adicionais, clique **em Mais informações.** Para uma descrição dessas propriedades, consulte [a seção Propriedades detalhadas para atividades de Descobertas e Descobertas.](#detailed-properties-for-ediscovery-activities)

10. Se desejado, você pode exportar os resultados da pesquisa de log de auditoria para um arquivo CSV e, em seguida, usar o recurso Excel Power Query para formatar e filtrar esses registros. Para saber mais, confira [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>Atividades de Descoberta Eletrônica

A tabela a seguir descreve as atividades de Pesquisa de Conteúdo e Descoberta Eletrônica Principal registradas quando um administrador ou gerente de Descoberta Eletrônica executa uma atividade relacionada à Descoberta Eletrônica usando o Centro de Conformidade do & de Segurança ou executando o cmd & let correspondente no PowerShell do Centro de Conformidade e Segurança. Observe também que algumas atividades executadas em Avançado serão retornadas quando você pesquisar atividades nessa lista.
  
> [!NOTE]
> As atividades de Descoberta Eletrônica descritas nesta seção fornecem informações semelhantes às atividades de cmdlet de Descoberta Eletrônica descritas na próxima seção. Recomendamos que você use as atividades de Descoberta e descritas nesta seção porque elas aparecerão nos resultados da pesquisa do log de auditoria em 30 minutos. Leva até 24 horas para que as atividades do cmdlet de Descoberta Eletrônica apareçam nos resultados da pesquisa do log de auditoria. 
  
|**Nome amigável**|**Operação**|**Cmdlet correspondente**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Membro adicionado à ocorrência de Descoberta eDiscovery  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Um usuário foi adicionado como membro de uma ocorrência de Descoberta eDiscovery. Como membro de uma ocorrência, um usuário pode executar várias tarefas relacionadas a ocorrências, dependendo se as permissões necessárias foram atribuídas a ele.  <br/> |
|Pesquisa de conteúdo alterada  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Uma pesquisa de conteúdo existente foi alterada. As alterações podem incluir a adição ou remoção de locais de conteúdo ou a edição da consulta de pesquisa.  <br/> |
|Associação de administrador de Descobertas e Descobertas  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |A lista de Administradores de Descobertas Na sua organização foi alterada. Essa atividade é registrada quando a lista de Administradores de Descobertas e é substituída por um grupo de novos usuários. Se um único usuário for adicionado ou removido, a operação CaseAdminAdded será registrada.  <br/> |
|Caso de Descoberta eDiscovery alterado  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Um caso de Descoberta eDiscovery foi alterado. As alterações incluem fechar uma ocorrência aberta ou reabrir uma ocorrência fechada.  <br/> |
|Associação de caso de Descoberta eDiscovery alterada  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |A lista de associações de um caso de Descoberta eDiscovery foi alterada. Essa atividade é registrada quando todos os membros são substituídos por um grupo de novos usuários. Se um único membro for adicionado ou removido, a operação CaseMemberAdded ou CaseMemberRemoved será registrada.  <br/> |
|Filtro de permissões de pesquisa alterado  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Um filtro de permissões de pesquisa foi alterado.  <br/> |
|Consulta de pesquisa alterada para a espera de caso de Descoberta  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Uma espera baseada em consulta associada a um caso de Descoberta e Foi alterada. As alterações possíveis incluem a edição da consulta ou do intervalo de datas para uma espera baseada em consulta.  <br/> |
|Item de visualização de pesquisa de conteúdo baixado  <br/> |PreviewItemDownloaded  <br/> |N/D  <br/> |Um usuário baixou um item para o computador local (clicando no link Baixar **item original)** ao visualizar os resultados da pesquisa.  <br/> |
|Item de visualização de pesquisa de conteúdo listado  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Um usuário **clicou** em Visualizar resultados da pesquisa para exibir a página de resultados da pesquisa de visualização, que lista até 1.000 itens dos resultados de uma Pesquisa de Conteúdo.  <br/> |
|Item de visualização de pesquisa de conteúdo exibido  <br/> |PreviewItemRendered  <br/> |N/D  <br/> |Um gerente de Descoberta eDiscovery visualizou um item clicando nele ao visualizar os resultados da pesquisa.  <br/> |
|Pesquisa de conteúdo criada  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Uma nova pesquisa de conteúdo foi criada.  <br/> |
|Administrador de Descobertas EDiscovery criado  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Um usuário foi adicionado como Um Administrador de Descobertas Na organização.  <br/> |
|Caso de Descoberta eDiscovery criado  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Uma ocorrência de Descoberta eDiscovery foi criada. Quando uma ocorrência é criada, você só precisa dar um nome a ela. Outras tarefas relacionadas a caso, como adicionar membros, criar retém e criar pesquisas de conteúdo associadas ao caso resultam em eventos adicionais registrados.  <br/> |
|Filtro de permissões de pesquisa criado  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Um filtro de permissões de pesquisa foi criado.  <br/> |
|Consulta de pesquisa criada para a espera de caso de Descoberta  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Foi criada uma espera baseada em consulta associada a um caso de Descoberta eDiscovery.  <br/> |
|Pesquisa de conteúdo excluída  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Uma pesquisa de conteúdo existente foi excluída.  <br/> |
|Administrador de Descoberta eDiscovery excluído  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Um Administrador de Descobertas e Descobertas Foi excluído da sua organização.  <br/> |
|Caso de Descoberta eDiscovery excluído  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Uma ocorrência de Descoberta eDiscovery foi excluída. Qualquer espera associada à ocorrência precisa ser removida antes que o caso possa ser excluído.  <br/> |
|Filtro de permissões de pesquisa excluído  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Um filtro de permissões de pesquisa foi excluído.  <br/> |
|Consulta de pesquisa excluída para a responsabilidade de ocorrência de Descoberta  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Uma reter baseada em consulta associada a um caso de Descoberta eDiscovery foi excluída. Remover a consulta da isenção geralmente é o resultado da exclusão de uma isenção. Quando uma consulta de isenção ou isenção é excluída, os locais de conteúdo que estavam em espera são liberados.  <br/> |
|Exportação baixada da pesquisa de conteúdo  <br/> |SearchExportDownloaded  <br/> |N/D  <br/> |Um usuário baixou os resultados de uma pesquisa de conteúdo para o computador local. Uma **exportação iniciada da atividade de pesquisa** de conteúdo deve ser iniciada antes que os resultados da pesquisa possam ser baixados.  <br/> |
|Resultados visualizados da pesquisa de conteúdo  <br/> |SearchPreviewed  <br/> |N/D  <br/> |Um usuário visualiza os resultados de uma pesquisa de conteúdo.  <br/> |
|Resultados limpos da pesquisa de conteúdo  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Um usuário limpa os resultados de uma Pesquisa de Conteúdo executando **o comando New-ComplianceSearchAction -Purge.**  <br/> |
|Análise removida da pesquisa de conteúdo  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de preparação de pesquisa de conteúdo (para preparar os resultados da pesquisa para a Descoberta Avançada) foi excluída. Se a ação de preparação tiver menos de duas semanas, os resultados da pesquisa que foram preparados para a Descoberta Avançada foram excluídos da área de armazenamento do Microsoft Azure. Se a ação de preparação tiver mais de 2 semanas, esse evento indicará que apenas a ação de preparação correspondente foi excluída.  <br/> |
|Exportação removida da pesquisa de conteúdo  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de exportação de pesquisa de conteúdo foi excluída. Se a ação de exportação tiver menos de duas semanas, os resultados da pesquisa que foram carregados para a área de armazenamento do Microsoft Azure foram excluídos. Se a ação de exportação tiver mais de 2 semanas, esse evento indicará que apenas a ação de exportação correspondente foi excluída.  <br/> |
|Membro removido da ocorrência de Descoberta eDiscovery  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Um usuário foi removido como membro de uma ocorrência de Descoberta eDiscovery.  <br/> |
|Resultados de visualização removidos da pesquisa de conteúdo  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de visualização de pesquisa de conteúdo foi excluída.  <br/> |
|Ação de limpeza removida executada na pesquisa de conteúdo  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de limpeza de pesquisa de conteúdo foi excluída.  <br/> |
|Relatório de pesquisa removido  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de relatório de exportação de pesquisa de conteúdo foi excluída.  <br/> |
|Análise iniciada da pesquisa de conteúdo  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Os resultados de uma pesquisa de conteúdo foram preparados para análise na Descoberta Avançada.  <br/> |
|Pesquisa de conteúdo iniciada  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Uma pesquisa de conteúdo foi iniciada. Quando você cria ou altera uma pesquisa de conteúdo usando a GUI do Centro de & Conformidade e Segurança, a pesquisa é iniciada automaticamente. Se você criar ou alterar uma pesquisa usando o cmdlet **New-ComplianceSearch** ou **Set-ComplianceSearch,** será necessário executar o cmdlet **Start-ComplianceSearch** para iniciar a pesquisa.  <br/> |
|Iniciado a exportação de pesquisa de conteúdo  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Um usuário exportou os resultados de uma pesquisa de conteúdo.  <br/> |
|Iniciado relatório de exportação  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Um usuário exportou um relatório de pesquisa de conteúdo.  <br/> |
|Pesquisa de conteúdo interrompida  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Um usuário interrompeu uma pesquisa de conteúdo.  <br/> |
|(nenhum)|CaseViewed|Get-ComplianceCase|Um usuário visualizou a  lista de ocorrências na página descoberta eletrônica no centro de conformidade e segurança ou executando o cmdlet.|
|(nenhum)|SearchViewed|Get-ComplianceSearch|Um usuário visualizou a lista em  pesquisas de conteúdo (listadas na guia Pesquisas) no centro de conformidade e segurança ou executando o cmdlet. Essa atividade também é registrada quando um usuário visualiza a lista de pesquisas de conteúdo  associadas a um caso de Descoberta eDiscovery (clicando na guia Pesquisas em uma ocorrência) ou executando o comando **Get-ComplianceSearch -Case.**|
|(nenhum)|ViewedSearchExported|Get-ComplianceSearchAction -Export|Um usuário visualizou a lista de trabalhos de exportação de pesquisa de conteúdo **(listados** na guia Exportações) no centro de conformidade e segurança ou executando o cmdlet. Essa atividade também é registrada quando um usuário visualiza a lista de trabalhos  de exportação em um caso de Descoberta eDiscovery (listado na guia Exportações em um caso) ou executando o comando **Get-ComplianceSearchAction -Case -Export.**|
|(nenhum)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|Um usuário visualiza os resultados de uma pesquisa de conteúdo no centro de conformidade e segurança ou executando o cmdlet.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Atividades de Descoberta Eletrônica Avançada

A tabela a seguir descreve as atividades de Descoberta e Avançada registradas no log de auditoria. Essas atividades (além de atividades relevantes de Descoberta Automática podem ser usadas para ajudá-lo a acompanhar a progressão da atividade em um caso de Descoberta Automática Avançada.

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

A tabela a seguir lista os registros de log de auditoria do cmdlet registrados quando um administrador ou usuário executa uma atividade relacionada à Descoberta Eletrônica usando o Centro de Conformidade do & de Segurança ou executando o cmdlet correspondente no PowerShell remoto conectado ao Centro de Conformidade e Segurança & da sua organização. As informações detalhadas no registro do log de auditoria são diferentes para as atividades de cmdlet listadas nesta tabela e as atividades de Descoberta Eletrônica descritas na seção anterior.
  
Conforme mencionado anteriormente, leva até 24 horas para que as atividades do cmdlet de Descoberta Eletrônica apareçam nos resultados da pesquisa do log de auditoria.
  
> [!TIP]
> Os cmdlets na **coluna Operação** na tabela a seguir estão vinculados ao tópico de ajuda do cmdlet correspondente no TechNet. Vá para o tópico de ajuda do cmdlet para ver uma descrição dos parâmetros disponíveis para cada cmdlet. O parâmetro e o valor do parâmetro que foram usados com um cmdlet são incluídos na entrada do log de auditoria para cada atividade de cmdlet de Descoberta Eletrônica registrada. 
  
|**Nome amigável**|**Operação (cmdlet)**|**Descrição**|
|:-----|:-----|:-----|
|Criação de espera no caso de Descoberta eDiscovery  <br/> |[New-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |Uma espera foi criada para um caso de Descoberta eDiscovery. Uma espera pode ser criada com ou sem especificar uma fonte de conteúdo. Se as fontes de conteúdo são especificadas, elas serão identificadas na entrada do log de auditoria.  <br/> |
|Exclusão de responsabilidade da ocorrência de Descoberta eDiscovery  <br/> |[Remove-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |Foi excluída uma isenção associada a uma ocorrência de Descoberta eDiscovery. A exclusão de uma espera libera todos os locais de conteúdo da espera. A exclusão da espera também resulta na exclusão das regras de união de caso associadas à união (consulte **Remove-CaseHoldRule** abaixo).  <br/> |
|Re espera alterada no caso de Descoberta eDiscovery  <br/> |[Set-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |Uma isenção associada a um eDiscovery foi alterada. As alterações possíveis incluem adicionar ou remover locais de conteúdo ou desativar (desabilitar) a espera.  <br/> |
|Consulta de pesquisa criada para a espera de caso de Descoberta  <br/> |[New-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |Foi criada uma espera baseada em consulta associada a um caso de Descoberta eDiscovery.  <br/> |
|Consulta de pesquisa excluída para a responsabilidade de ocorrência de Descoberta  <br/> |[Remove-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |Uma reter baseada em consulta associada a um caso de Descoberta eDiscovery foi excluída. Remover a consulta da isenção geralmente é o resultado da exclusão de uma isenção. Quando uma consulta de isenção ou isenção é excluída, os locais de conteúdo que estavam em espera são liberados.  <br/> |
|Consulta de pesquisa alterada para a espera de caso de Descoberta  <br/> |[Set-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |Uma espera baseada em consulta associada a um caso de Descoberta e Foi alterada. As alterações possíveis incluem a edição da consulta ou do intervalo de datas para uma espera baseada em consulta.  <br/> |
|Caso de Descoberta eDiscovery criado  <br/> |[New-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |Uma ocorrência de Descoberta eDiscovery foi criada. Quando uma ocorrência é criada, você só precisa dar um nome a ela. Outras tarefas relacionadas a caso, como adicionar membros, criar retém e criar pesquisas de conteúdo associadas ao caso resultam em eventos adicionais registrados.  <br/> |
|Caso de Descoberta eDiscovery excluído  <br/> |[Remove-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |Uma ocorrência de Descoberta eDiscovery foi excluída. Qualquer espera associada à ocorrência precisa ser removida antes que o caso possa ser excluído.  <br/> |
|Caso de Descoberta eDiscovery alterado  <br/> |[Set-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |Um caso de Descoberta eDiscovery foi alterado. As alterações incluem fechar uma ocorrência aberta ou reabrir uma ocorrência fechada.  <br/> |
|Membro adicionado à ocorrência de Descoberta eDiscovery  <br/> |[Add-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |Um usuário foi adicionado como membro de uma ocorrência de Descoberta eDiscovery. Como membro de uma ocorrência, um usuário pode executar várias tarefas relacionadas a ocorrências, dependendo se as permissões necessárias foram atribuídas a ele.  <br/> |
|Membro removido da ocorrência de Descoberta eDiscovery  <br/> |[Remove-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |Um usuário foi removido como membro de uma ocorrência de Descoberta eDiscovery.  <br/> |
|Associação de caso de Descoberta eDiscovery alterada  <br/> |[Update-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |A lista de associações de um caso de Descoberta eDiscovery foi alterada. Essa atividade é registrada quando todos os membros são substituídos por um grupo de novos usuários. Se um único membro for adicionado ou removido, a operação **Add-ComplianceCaseMember** ou **Remove-ComplianceCaseMember** será registrada.  <br/> |
|Pesquisa de conteúdo criada  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |Uma nova pesquisa de conteúdo foi criada.  <br/> |
|Pesquisa de conteúdo excluída  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |Uma pesquisa de conteúdo existente foi excluída.  <br/> |
|Pesquisa de conteúdo alterada  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |Uma pesquisa de conteúdo existente foi alterada. As alterações podem incluir a adição ou remoção de locais de conteúdo pesquisados e edição da consulta de pesquisa.  <br/> |
|Pesquisa de conteúdo iniciada  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |Uma pesquisa de conteúdo foi iniciada. Quando você cria ou altera uma pesquisa de conteúdo usando a GUI do Centro de & Conformidade e Segurança, a pesquisa é iniciada automaticamente. Se você criar ou alterar uma pesquisa usando o cmdlet **New-ComplianceSearch** ou **Set-ComplianceSearch,** será necessário executar o cmdlet **Start-ComplianceSearch** para iniciar a pesquisa.  <br/> |
|Pesquisa de conteúdo interrompida  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |Uma pesquisa de conteúdo em execução foi interrompida.  <br/> |
|Ação de pesquisa de conteúdo criada  <br/> |[New-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |Uma ação de pesquisa de conteúdo foi criada. As ações de pesquisa de conteúdo incluem a visualização dos resultados da pesquisa, a exportação dos resultados da pesquisa, a preparação dos resultados da pesquisa para análise na Descoberta Avançada e a exclusão permanente de itens que corresponderem aos critérios de pesquisa de uma pesquisa de conteúdo.  <br/> |
|Ação de pesquisa de conteúdo excluída  <br/> |[Remove-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |Uma ação de pesquisa de conteúdo foi excluída.  <br/> |
|Filtro de permissões de pesquisa criado  <br/> |[New-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |Um filtro de permissões de pesquisa foi criado.  <br/> |
|Filtro de permissões de pesquisa excluído  <br/> |[Remove-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |Um filtro de permissões de pesquisa foi excluído.  <br/> |
|Filtro de permissões de pesquisa alterado  <br/> |[Set-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |Um filtro de permissões de pesquisa foi alterado.  <br/> |
|Administrador de Descobertas EDiscovery criado  <br/> |[Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |Um usuário foi adicionado como Administrador de Descobertas e Descobertas Na sua organização.  <br/> |
|Administrador de Descoberta eDiscovery excluído  <br/> |[Remove-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |Um Administrador de Descobertas e Descobertas Foi excluído da sua organização.  <br/> |
|Associação de administrador de Descobertas e Descobertas  <br/> |[Update-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |A lista de Administradores de Descobertas Na sua organização foi alterada. Essa atividade é registrada quando a lista de Administradores de Descobertas e é substituída por um grupo de novos usuários. Se um único usuário for adicionado ou removido, a operação **Add-eDiscoveryCaseAdmin** ou **Remove-eDiscoveryCaseAdmin** será registrada.  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>Propriedades detalhadas para atividades de Descobertas e Descobertas

A tabela a seguir descreve as propriedades  que são  incluídas quando você clica em Mais informações na página Detalhes de uma atividade de Descoberta e Listada nos resultados da pesquisa. Essas propriedades também são incluídas no arquivo CSV quando você exporta os resultados da pesquisa do log de auditoria. Um registro de log de auditoria para uma atividade de Descoberta e não incluirá todas as propriedades detalhadas listadas abaixo. 
  
> [!TIP]
> Quando você exporta os resultados da pesquisa, o arquivo CSV contém uma coluna chamada **Detalhe**, que contém as propriedades detalhadas descritas na tabela a seguir em uma propriedade de vários valores. Você pode usar o recurso Power Query no Excel para dividir essa coluna em várias colunas para que cada propriedade tenha sua própria coluna. Isso permitirá classificar e filtrar uma ou mais dessas propriedades. Para obter mais informações, consulte a seção "Exportar os resultados da pesquisa para um arquivo" em [Pesquisar o log de auditoria.](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file) 
  
|**Propriedade**|**Descrição**|
|:-----|:-----|
|Caso  <br/> |A identidade (GUID) da ocorrência de Descoberta eDiscovery que foi criada, alterada ou excluída.  <br/> |
|ClientApplication  <br/> |As atividades do cmdlet de Descoberta Eletrônica têm um valor **do EMC** para essa propriedade. Isso indica que a atividade foi realizada usando a GUI do Centro de & Conformidade e Segurança ou executando o cmdlet no PowerShell.  <br/> |
|ClientIP  <br/> |O endereço IP do dispositivo que foi usado quando a atividade foi registrada. O endereço IP é exibido em um formato de endereço IPv4 ou IPv6.  <br/> |
|ClientRequestId  <br/> | Para atividades de Descoberta e, em geral, essa propriedade fica em branco.  <br/> |
|CmdletVersion  <br/> |O número do build da versão do Centro de Conformidade & segurança em execução em sua organização.  <br/> |
|CreationTime  <br/> |A data e a hora no Tempo Universal Coordenado (UTC) em que a atividade de Descoberta eDiscovery foi concluída.  <br/> |
|EffectiveOrganization  <br/> |O nome da organização do Microsoft 365.  <br/> |
|ExchangeLocations  <br/> |As caixas de correio do Exchange Online incluídas em uma pesquisa de conteúdo ou colocadas em espera em um caso de Descoberta Eletrônico.  <br/> |
|Exclusões  <br/> |Locais de caixa de correio ou site excluídos de uma pesquisa de conteúdo ou de uma responsabilidade em um caso de Descoberta Eletrônico.  <br/> |
|ExtendedProperties  <br/> |Propriedades adicionais de uma pesquisa de conteúdo, uma ação de pesquisa de conteúdo ou re espera em um caso de Descoberta Eletrônica, como o GUID do objeto e os parâmetros de cmdlet e cmdlet correspondentes que foram usados quando a atividade foi executada.  <br/> |
|Id  <br/> |A ID da entrada do relatório. A ID identifica exclusivamente a entrada do log de auditoria.  <br/> |
|NonPIIParameters  <br/> |Uma lista dos parâmetros (sem valores) que foram usados com o cmdlet identificado na propriedade Operation. Os parâmetros listados nesta propriedade são os mesmos listados na propriedade Parameters.  <br/> |
|ObjectId  <br/> |O GUID ou o nome do objeto (por exemplo, uma Pesquisa de Conteúdo ou uma ocorrência de Descoberta eDiscovery) que foi criado, alterado ou excluído pela atividade listada na propriedade Operation. Esse objeto também é identificado na coluna Item nos resultados de pesquisa do log de auditoria.  <br/> |
|ObjectType  <br/> |O tipo de objeto eDiscovery que o usuário criou, excluiu ou modificou; por exemplo, uma ação de pesquisa de conteúdo (visualização, exportação ou limpeza), uma ocorrência de Descoberta eDiscovery ou uma pesquisa de conteúdo.  <br/> |
|Operation  <br/> |O nome da operação que corresponde à atividade de Descoberta eDiscovery que foi executada.  <br/> |
|OrganizationId  <br/> |O GUID da sua organização do Microsoft 365.  <br/> |
|Parâmetros  <br/> |O nome e o valor dos parâmetros que foram usados com o cmdlet correspondente.  <br/> |
|PublicFolderLocations  <br/> |Os locais de pastas públicas no Exchange Online que estão incluídos em uma pesquisa de conteúdo ou colocados em espera em um caso de Descoberta eDiscovery.  <br/> |
|Consulta  <br/> |A consulta de pesquisa associada à atividade, como uma pesquisa de conteúdo ou uma espera baseada em consulta.  <br/> |
|RecordType  <br/> |O tipo de operação indicado pelo registro. O valor **18** indica um evento relacionado a uma atividade listada na seção de atividades [do cmdlet](#ediscovery-cmdlet-activities) de Descoberta Eletrônica. Um valor **24** indica um evento relacionado a uma atividade listada na seção Como pesquisar e exibir as atividades [de](#how-to-search-for-and-view-ediscovery-activities) Descoberta.  <br/> |
|ResultStatus  <br/> |Indica se a ação (especificada na propriedade Operation) foi bem-sucedida ou não.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica que a atividade foi um evento do Centro de Conformidade & segurança. Todas as atividades de Descobertas Do eDiscovery terão um valor **0** para essa propriedade.  <br/> |
|SharepointLocations  <br/> |Os sites do SharePoint Online incluídos em uma pesquisa de conteúdo ou colocados em espera em um caso de Descoberta Virtual.  <br/> |
|StartTime  <br/> |A data e a hora no Tempo Universal Coordenado (UTC) em que a atividade de Descoberta eDiscovery foi iniciada.  <br/> |
|UserId  <br/> |O usuário que realizou a atividade (especificada na propriedade Operation) que resultou no registro sendo registrado. Os registros da atividade de Descoberta Eletrônico executados por contas do sistema (como NT AUTHORITY\SYSTEM) também são incluídos no log de auditoria.  <br/> |
|UserKey  <br/> |Uma ID alternativa para o usuário identificado na propriedade UserId. Para atividades de Descoberta e, em geral, o valor dessa propriedade é o mesmo que a propriedade UserId.  <br/> |
|UserServicePlan  <br/> |A assinatura usada por sua organização. Para atividades de Descoberta e, em geral, essa propriedade fica em branco.  <br/> |
|UserType  <br/> |O tipo de usuário que executou a operação. Os seguintes valores indicam o tipo de usuário.  <br/> 0 Um usuário normal. 2 Um administrador em sua organização. 3 Uma conta de administrador de datacenter ou de sistema de datacenter da Microsoft. 4 Uma conta de sistema. 5 Um aplicativo. 6 Uma entidade de serviço. |
|Versão  <br/> |Indica o número da versão da atividade (identificada pela propriedade Operation) que está registrada.  <br/> |
|Workload  <br/> |O serviço em que a atividade ocorreu. Para atividades de Descoberta eDiscovery, o valor **é SecurityComplianceCenter**.  <br/> |