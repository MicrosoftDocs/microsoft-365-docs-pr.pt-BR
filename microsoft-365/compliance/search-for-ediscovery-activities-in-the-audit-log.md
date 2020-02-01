---
title: Pesquisar atividades de descoberta eletrônica no log de auditoria do Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Saiba como pesquisar o log de auditoria do Office 365 em busca de eventos registrados quando os administradores de conformidade executam tarefas de pesquisa de conteúdo e casos de descoberta eletrônica no centro de conformidade de & de segurança.
ms.openlocfilehash: ef9c40debb8c28f0d017423d29016ca4f52b7a17
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601528"
---
# <a name="search-for-ediscovery-activities-in-the-office-365-audit-log"></a>Pesquisar atividades de descoberta eletrônica no log de auditoria do Office 365

Pesquisa de conteúdo e atividades relacionadas à descoberta eletrônica realizadas no centro de conformidade & segurança ou executando os cmdlets do Windows PowerShell correspondentes são registrados no log de auditoria do Office 365. Os eventos são registrados quando administradores ou administradores de conformidade (ou qualquer usuário que tenha permissões de descoberta eletrônica) executam as seguintes tarefas relacionadas à pesquisa de conteúdo e descoberta eletrônica no centro de conformidade de & de segurança:
  
- Criar e gerenciar casos de Descoberta Eletrônica
    
- Criar, iniciar e editar pesquisas de conteúdo
    
- Executar ações de pesquisa de conteúdo, como visualização, exportação e exclusão de resultados de pesquisa
    
- Configurar a filtragem de permissões para pesquisa de conteúdo
    
- Gerenciar a função de administrador de Descoberta Eletrônica
    
> [!IMPORTANT]
> As atividades descritas neste artigo são apenas o resultado de tarefas de descoberta eletrônica realizadas usando o centro de conformidade do & de segurança. as tarefas de descoberta eletrônica realizadas com o uso da ferramenta de descoberta eletrônica in-loco no Exchange Online ou no centro de descoberta eletrônica no SharePoint Online não estão incluídas. 
  
Para obter mais informações sobre como pesquisar o log de auditoria do Office 365, as permissões necessárias e exportar os resultados da pesquisa, confira [Pesquisar o log de auditoria no centro de conformidade de & de segurança](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Como Pesquisar e exibir atividades de descoberta eletrônica

Atualmente, você precisa fazer algumas coisas específicas para exibir as atividades de descoberta eletrônica no log de auditoria do Office 365. Veja como.
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre no Office 365 usando a sua conta corporativa ou de estudante.
    
3. No painel esquerdo, clique em **Pesquisar**e, em seguida, clique em **pesquisa de log de auditoria**.
    
4. Na lista suspensa **atividades** , em **atividades de descoberta eletrônica**, clique em uma ou mais atividades a serem pesquisadas. Ou você pode clicar em **atividades de descoberta eletrônica** para pesquisar todas as atividades relacionadas à descoberta eletrônica. 
    
    > [!NOTE]
    > A lista suspensa atividades também inclui um grupo de atividades denominadas **atividades de cmdlet de descoberta eletrônica** que retornarão registros do log de auditoria de cmdlet. 
  
5.  Selecione um intervalo de data e hora para exibir eventos de descoberta eletrônica que ocorreram dentro desse período. 
    
6. Na caixa **usuários** , selecione um ou mais usuários para exibir os resultados da pesquisa. Deixe esta caixa em branco para retornar entradas para todos os usuários. 
    
7. Clique em **Pesquisar** para executar a pesquisa usando seus critérios de pesquisa.  
    
8. Depois que os resultados da pesquisa são exibidos, você pode clicar em **filtrar resultados** para filtrar ou classificar os registros de atividade resultantes. Infelizmente, não é possível usar a filtragem para excluir explicitamente determinadas atividades. 
    
9. Para exibir detalhes sobre uma atividade, clique no registro da atividade na lista de resultados da pesquisa. 
    
    É exibida uma página de saída de **detalhes** que contém as propriedades detalhadas do registro de eventos. Para exibir detalhes adicionais, clique em **mais informações**. Para obter uma descrição dessas propriedades, consulte a seção [propriedades detalhadas para atividades de descoberta eletrônica](#detailed-properties-for-ediscovery-activities) . 

  
## <a name="ediscovery-activities"></a>Atividades de Descoberta Eletrônica

A tabela a seguir descreve a pesquisa de conteúdo e as atividades relacionadas à descoberta eletrônica que são registradas quando um administrador ou usuário realiza uma atividade relacionada à descoberta eletrônica usando o centro de conformidade do & de segurança ou executando o cmdlet correspondente no PowerShell remoto conectado ao centro de conformidade & segurança da sua organização. 
  
> [!NOTE]
> As atividades de descoberta eletrônica descritas nesta seção fornecem informações semelhantes às atividades de cmdlet de descoberta eletrônica descritas na próxima seção. Recomendamos que você use as atividades de descoberta eletrônica descritas nesta seção, pois elas aparecerão nos resultados da pesquisa de log de auditoria em 30 minutos. É necessário até 24 horas para que as atividades do cmdlet de descoberta eletrônica apareçam nos resultados da pesquisa de log de auditoria. 
  
|**Nome amigável**|**Operação**|**Cmdlet correspondente**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Membro adicionado ao caso de descoberta eletrônica  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Um usuário foi adicionado como um membro de uma ocorrência de descoberta eletrônica. Como um membro de um caso, um usuário pode realizar várias tarefas relacionadas a maiúsculas e minúsculas, dependendo se foram atribuídas as permissões necessárias.  <br/> |
|Pesquisa de conteúdo alterada  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Uma pesquisa de conteúdo existente foi alterada. As alterações podem incluir adição ou remoção de locais de conteúdo ou edição da consulta de pesquisa.  <br/> |
|Associação de administrador de descoberta eletrônica alterada  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |A lista de administradores de descoberta eletrônica em sua organização foi alterada. Essa atividade é registrada quando a lista de administradores de descoberta eletrônica é substituída por um grupo de novos usuários. Se um único usuário for adicionado ou removido, a operação CaseAdminAdded será registrada.  <br/> |
|Ocorrência de descoberta eletrônica alterada  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Uma ocorrência de descoberta eletrônica foi alterada. As alterações incluem fechar uma ocorrência aberta ou reabrir uma ocorrência fechada.  <br/> |
|Associação de ocorrência de descoberta eletrônica alterada  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |A lista de membros de um caso de descoberta eletrônica foi alterada. Essa atividade é registrada quando todos os membros são substituídos por um grupo de novos usuários. Se um único membro for adicionado ou removido, a operação CaseMemberAdded ou CaseMemberRemoved será registrada.  <br/> |
|Filtro de permissões de pesquisa alterado  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Um filtro de permissões de pesquisa foi alterado.  <br/> |
|Consulta de pesquisa de retenção de caso de descoberta eletrônica alterada  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Um bloqueio baseado em consulta associado a um caso de descoberta eletrônica foi alterado. As alterações possíveis incluem a edição da consulta ou do intervalo de datas de uma retenção baseada em consulta.  <br/> |
|Item de visualização de pesquisa de conteúdo baixado  <br/> |PreviewItemDownloaded  <br/> |Não disponível  <br/> |Um usuário baixou um item para seu computador local (clicando no link **baixar item original** ) ao visualizar os resultados da pesquisa.  <br/> |
|Item de visualização de pesquisa de conteúdo listado  <br/> |PreviewItemListed  <br/> |Não disponível  <br/> |Um usuário clicou em **Visualizar resultados da pesquisa** para exibir a página Visualizar resultados da pesquisa, que lista até 1000 itens dos resultados de uma pesquisa de conteúdo.  <br/> |
|Item de visualização de pesquisa de conteúdo exibido  <br/> |PreviewItemRendered  <br/> |Não disponível  <br/> |Um gerente de descoberta eletrônica exibiu um item clicando nele ao visualizar os resultados da pesquisa.  <br/> |
|Pesquisa de conteúdo criada  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Uma nova pesquisa de conteúdo foi criada.  <br/> |
|Administrador de descoberta eletrônica criado  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Um usuário foi adicionado como um administrador de descoberta eletrônica na organização.  <br/> |
|Ocorrência de descoberta eletrônica criada  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Um caso de descoberta eletrônica foi criado. Quando um caso é criado, você só precisa dar um nome a ele. Outras tarefas relacionadas a maiúsculas e minúsculas, como a adição de membros, a criação de isenções e a criação de pesquisas de conteúdo associadas ao caso de eventos adicionais serem registrados.  <br/> |
|Filtro de permissões de pesquisa criado  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Um filtro de permissões de pesquisa foi criado.  <br/> |
|Consulta de pesquisa de retenção de caso de descoberta eletrônica criada  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Um bloqueio baseado em consulta associado a um caso de descoberta eletrônica foi criado.  <br/> |
|Pesquisa de conteúdo excluída  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Uma pesquisa de conteúdo existente foi excluída.  <br/> |
|Administrador de descoberta eletrônica excluído  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Um administrador de descoberta eletrônica foi excluído da sua organização.  <br/> |
|Caso de descoberta eletrônica excluída  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Uma ocorrência de descoberta eletrônica foi excluída. Observe que qualquer retenção associada ao caso deve ser removido para que o caso possa ser excluído.  <br/> |
|Filtro de permissões de pesquisa excluído  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Um filtro de permissões de pesquisa foi excluído.  <br/> |
|Consulta de pesquisa de retenção de caso de descoberta eletrônica excluída  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Um bloqueio baseado em consulta associado a um caso de descoberta eletrônica foi excluído. Remover a consulta da retenção geralmente é o resultado da exclusão de uma isenção. Quando uma consulta de bloqueio ou retenção é excluída, os locais de conteúdo que estavam em retenção são lançados.  <br/> |
|Exportação baixa de pesquisa de conteúdo  <br/> |SearchExportDownloaded  <br/> |Não disponível  <br/> |Um usuário baixou os resultados de uma pesquisa de conteúdo para o computador local. Observe que uma **exportação iniciada da atividade de pesquisa de conteúdo** deve ser iniciada para que os resultados da pesquisa possam ser baixados.  <br/> |
|Resultados visualizados da pesquisa de conteúdo  <br/> |SearchPreviewed  <br/> |Não disponível  <br/> |Um usuário visualize os resultados de uma pesquisa de conteúdo.  <br/> |
|Resultados excluídos da pesquisa de conteúdo  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Um usuário limpou os resultados de uma pesquisa de conteúdo executando o comando **New-ComplianceSearchAction-Purge** .  <br/> |
|Análise de pesquisa de conteúdo removida  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de preparação de pesquisa de conteúdo (para preparar resultados de pesquisa para a descoberta eletrônica avançada do Office 365) foi excluída. Se a ação de preparação tiver menos de duas semanas, os resultados da pesquisa que foram preparados para descoberta eletrônica avançada foram excluídos da área de armazenamento do Microsoft Azure. Se a ação de preparação tiver mais de duas semanas, esse evento indicará que somente a ação de preparação correspondente foi excluída.  <br/> |
|Exportação de pesquisa de conteúdo removida  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de exportação de pesquisa de conteúdo foi excluída. Se a ação de exportação tiver menos de duas semanas, os resultados da pesquisa que foram carregados para a área de armazenamento do Microsoft Azure foram excluídos. Se a ação de exportação tiver mais de duas semanas, esse evento indicará que somente a ação de exportação correspondente foi excluída.  <br/> |
|Membro removido da ocorrência de descoberta eletrônica  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Um usuário foi removido como membro de uma ocorrência de descoberta eletrônica.  <br/> |
|Removidos resultados da visualização da pesquisa de conteúdo  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de visualização de pesquisa de conteúdo foi excluída.  <br/> |
|Ação de limpeza removida executada na pesquisa de conteúdo  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de limpeza de pesquisa de conteúdo foi excluída.  <br/> |
|Relatório de pesquisa removido  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Uma ação de relatório de exportação de pesquisa de conteúdo foi excluída.  <br/> |
|Análise de pesquisa de conteúdo iniciada  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Os resultados de uma pesquisa de conteúdo foram preparados para análise na descoberta eletrônica avançada.  <br/> |
|Pesquisa de conteúdo iniciada  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Uma pesquisa de conteúdo foi iniciada. Quando você cria ou altera uma pesquisa de conteúdo usando a GUI do centro de conformidade & segurança, a pesquisa é iniciada automaticamente. Se você criar ou alterar uma pesquisa usando o cmdlet **New-ComplianceSearch** ou **set-ComplianceSearch** , será necessário executar o cmdlet **Start-ComplianceSearch** para iniciar a pesquisa.  <br/> |
|Exportação de pesquisa de conteúdo iniciada  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Um usuário exportou os resultados de uma pesquisa de conteúdo.  <br/> |
|Relatório de exportação iniciado  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Um usuário exportou um relatório de pesquisa de conteúdo.  <br/> |
|Pesquisa de conteúdo interrompida  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Um usuário interrompeu uma pesquisa de conteúdo.  <br/> |
  
## <a name="ediscovery-cmdlet-activities"></a>atividades de cmdlet de descoberta eletrônica

A tabela a seguir lista os registros de log de auditoria de cmdlet que são registrados quando um administrador ou usuário realiza uma atividade relacionada à descoberta eletrônica usando o centro de conformidade do & de segurança ou executando o cmdlet correspondente no PowerShell remoto conectado ao centro de conformidade & segurança da sua organização. Observe que as informações detalhadas no registro de log de auditoria são diferentes para as atividades de cmdlet listadas nesta tabela e as atividades de descoberta eletrônica descritas na seção anterior. 
  
Conforme mencionado anteriormente, é necessário até 24 horas para atividades de cmdlet de descoberta eletrônica serem exibidas nos resultados de pesquisa do log de auditoria.
  
> [!TIP]
> Os cmdlets na coluna **operação** da tabela a seguir são vinculados ao tópico da ajuda do cmdlet correspondente no TechNet. Vá para o tópico de ajuda do cmdlet para obter uma descrição dos parâmetros disponíveis para cada cmdlet. O parâmetro e o valor de parâmetro que foram usados com um cmdlet estão incluídos na entrada de log de auditoria para cada atividade de cmdlet de descoberta eletrônica registrada. 
  
|**Nome amigável**|**Operação (cmdlet)**|**Descrição**|
|:-----|:-----|:-----|
|Criação de retenção em caso de descoberta eletrônica  <br/> |[New-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |Uma retenção foi criada para uma ocorrência de descoberta eletrônica. Uma retenção pode ser criada com ou sem a especificação de uma fonte de conteúdo. Se as fontes de conteúdo forem especificadas, elas serão identificadas na entrada do log de auditoria.  <br/> |
|Excluído o bloqueio de ocorrência de descoberta eletrônica  <br/> |[Remove-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |Uma retenção associada a um caso de descoberta eletrônica foi excluída. Excluir uma isenção libera todos os locais de conteúdo da isenção. A exclusão da retenção também resulta na exclusão das regras de bloqueio de caso associadas à retenção (consulte **Remove-CaseHoldRule** abaixo).  <br/> |
|Retenção alterada no caso de descoberta eletrônica  <br/> |[Set-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |Uma retenção associada a uma descoberta eletrônica foi alterada. As alterações possíveis incluem adição ou remoção de locais de conteúdo ou desativação (desabilitando) a retenção.  <br/> |
|Consulta de pesquisa de retenção de caso de descoberta eletrônica criada  <br/> |[New-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |Um bloqueio baseado em consulta associado a um caso de descoberta eletrônica foi criado.  <br/> |
|Consulta de pesquisa de retenção de caso de descoberta eletrônica excluída  <br/> |[Remove-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |Um bloqueio baseado em consulta associado a um caso de descoberta eletrônica foi excluído. Remover a consulta da retenção geralmente é o resultado da exclusão de uma isenção. Quando uma consulta de bloqueio ou retenção é excluída, os locais de conteúdo que estavam em retenção são lançados.  <br/> |
|Consulta de pesquisa de retenção de caso de descoberta eletrônica alterada  <br/> |[Set-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |Um bloqueio baseado em consulta associado a um caso de descoberta eletrônica foi alterado. As alterações possíveis incluem a edição da consulta ou do intervalo de datas de uma retenção baseada em consulta.  <br/> |
|Ocorrência de descoberta eletrônica criada  <br/> |[New-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |Um caso de descoberta eletrônica foi criado. Quando um caso é criado, você só precisa dar um nome a ele. Outras tarefas relacionadas a maiúsculas e minúsculas, como a adição de membros, a criação de isenções e a criação de pesquisas de conteúdo associadas ao caso de eventos adicionais serem registrados.  <br/> |
|Caso de descoberta eletrônica excluída  <br/> |[Remove-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |Uma ocorrência de descoberta eletrônica foi excluída. Observe que qualquer retenção associada ao caso deve ser removido para que o caso possa ser excluído.  <br/> |
|Ocorrência de descoberta eletrônica alterada  <br/> |[Set-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |Uma ocorrência de descoberta eletrônica foi alterada. As alterações incluem fechar uma ocorrência aberta ou reabrir uma ocorrência fechada.  <br/> |
|Membro adicionado ao caso de descoberta eletrônica  <br/> |[Add-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |Um usuário foi adicionado como um membro de uma ocorrência de descoberta eletrônica. Como um membro de um caso, um usuário pode realizar várias tarefas relacionadas a maiúsculas e minúsculas, dependendo se foram atribuídas as permissões necessárias.  <br/> |
|Membro removido da ocorrência de descoberta eletrônica  <br/> |[Remove-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |Um usuário foi removido como membro de uma ocorrência de descoberta eletrônica.  <br/> |
|Associação de ocorrência de descoberta eletrônica alterada  <br/> |[Update-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |A lista de membros de um caso de descoberta eletrônica foi alterada. Essa atividade é registrada quando todos os membros são substituídos por um grupo de novos usuários. Se um único membro for adicionado ou removido, a operação **Add-ComplianceCaseMember** ou **Remove-ComplianceCaseMember** será registrada.  <br/> |
|Pesquisa de conteúdo criada  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |Uma nova pesquisa de conteúdo foi criada.  <br/> |
|Pesquisa de conteúdo excluída  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |Uma pesquisa de conteúdo existente foi excluída.  <br/> |
|Pesquisa de conteúdo alterada  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |Uma pesquisa de conteúdo existente foi alterada. As alterações podem incluir a adição ou remoção de locais de conteúdo pesquisados e edição da consulta de pesquisa.  <br/> |
|Pesquisa de conteúdo iniciada  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |Uma pesquisa de conteúdo foi iniciada. Quando você cria ou altera uma pesquisa de conteúdo usando a GUI do centro de conformidade & segurança, a pesquisa é iniciada automaticamente. Se você criar ou alterar uma pesquisa usando o cmdlet **New-ComplianceSearch** ou **set-ComplianceSearch** , será necessário executar o cmdlet **Start-ComplianceSearch** para iniciar a pesquisa.  <br/> |
|Pesquisa de conteúdo interrompida  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |Uma pesquisa de conteúdo que estava sendo executada foi interrompida.  <br/> |
|Ação de pesquisa de conteúdo criada  <br/> |[New-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |Uma ação de pesquisa de conteúdo foi criada. As ações de pesquisa de conteúdo incluem visualização de resultados de pesquisa, exportação de resultados de pesquisa, preparação de resultados de pesquisa para análise na descoberta eletrônica avançada do Office 365 e exclusão permanente de itens que correspondam aos critérios de pesquisa de uma pesquisa de conteúdo.  <br/> |
|Ação de pesquisa de conteúdo excluída  <br/> |[Remove-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |Uma ação de pesquisa de conteúdo foi excluída.  <br/> |
|Filtro de permissões de pesquisa criado  <br/> |[New-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |Um filtro de permissões de pesquisa foi criado.  <br/> |
|Filtro de permissões de pesquisa excluído  <br/> |[Remove-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |Um filtro de permissões de pesquisa foi excluído.  <br/> |
|Filtro de permissões de pesquisa alterado  <br/> |[Set-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |Um filtro de permissões de pesquisa foi alterado.  <br/> |
|Administrador de descoberta eletrônica criado  <br/> |[Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |Um usuário foi adicionado como administrador de descoberta eletrônica em sua organização.  <br/> |
|Administrador de descoberta eletrônica excluído  <br/> |[Remove-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |Um administrador de descoberta eletrônica foi excluído da sua organização.  <br/> |
|Associação de administrador de descoberta eletrônica alterada  <br/> |[Update-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |A lista de administradores de descoberta eletrônica em sua organização foi alterada. Essa atividade é registrada quando a lista de administradores de descoberta eletrônica é substituída por um grupo de novos usuários. Se um único usuário é adicionado ou removido, a operação **Add-eDiscoveryCaseAdmin** ou **Remove-eDiscoveryCaseAdmin** é registrada.  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>Propriedades detalhadas para atividades de descoberta eletrônica

A tabela a seguir descreve as propriedades que são incluídas quando você clica em **mais informações** na página de **detalhes** de uma atividade de descoberta eletrônica listada nos resultados da pesquisa. Essas propriedades também estão incluídas no arquivo CSV quando você exporta os resultados da pesquisa de log de auditoria. Observe que um registro de log de auditoria para uma atividade de descoberta eletrônica não incluirá todas as propriedades detalhadas listadas abaixo. 
  
> [!TIP]
> Quando você exporta os resultados da pesquisa, o arquivo CSV contém uma coluna chamada **Detail**, que contém as propriedades detalhadas descritas na tabela a seguir em uma propriedade de vários valores. Você pode usar o recurso de consulta de energia no Excel para dividir esta coluna em várias colunas, de forma que cada propriedade terá sua própria coluna. Isso permitirá que você classifique e filtre em uma ou mais dessas propriedades. Para obter mais informações, consulte a seção "exportar os resultados da pesquisa para um arquivo" em [Pesquisar o log de auditoria](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Propriedade**|**Descrição**|
|:-----|:-----|
|Caso  <br/> |A identidade (GUID) da ocorrência de descoberta eletrônica que foi criada, alterada ou excluída.  <br/> |
|ClientApplication  <br/> |as atividades de cmdlet de descoberta eletrônica têm um valor da **EMC** para esta propriedade. Isso indica que a atividade foi realizada usando a GUI do centro de conformidade do & de segurança ou executando o cmdlet no PowerShell.  <br/> |
|ClientIP  <br/> |O endereço IP do dispositivo que foi usado quando a atividade foi registrada. O endereço IP é exibido em um formato de endereço IPv4 ou IPv6.  <br/> |
|ClientRequestId  <br/> | Para atividades de descoberta eletrônica, essa propriedade geralmente está em branco.  <br/> |
|CmdletVersion  <br/> |O número de compilação da versão do centro de conformidade & segurança em execução em sua organização.  <br/> |
|CreationTime  <br/> |A data e hora no tempo universal coordenado (UTC) quando a atividade de descoberta eletrônica foi concluída.  <br/> |
|EffectiveOrganization  <br/> |O nome da sua organização do Office 365.  <br/> |
|ExchangeLocations  <br/> |As caixas de correio do Exchange Online que estão incluídas em uma pesquisa de conteúdo ou colocadas em espera em uma ocorrência de descoberta eletrônica.  <br/> |
|Exclusões  <br/> |Locais de caixa de correio ou de site excluídos de uma pesquisa de conteúdo ou de um bloqueio em uma ocorrência de descoberta eletrônica.  <br/> |
|ExtendedProperties  <br/> |Propriedades adicionais de uma pesquisa de conteúdo, uma ação de pesquisa de conteúdo ou uma retenção em caso de descoberta eletrônica, como o GUID do objeto e os parâmetros de cmdlet e cmdlet correspondentes que foram usados quando a atividade foi realizada.  <br/> |
|Id  <br/> |A ID da entrada de relatório. A ID identifica exclusivamente a entrada do log de auditoria.  <br/> |
|NonPIIParameters  <br/> |Uma lista dos parâmetros (sem qualquer valor) que foram usados com o cmdlet identificado na Propriedade Operation. Os parâmetros listados nesta propriedade são os mesmos que os listados na Propriedade Parameters.  <br/> |
|ObjectId  <br/> |O GUID ou o nome do objeto (por exemplo, uma pesquisa de conteúdo ou um caso de descoberta eletrônica) que foi criado, alterado ou excluído pela atividade listada na Propriedade Operation. Esse objeto também é identificado na coluna item nos resultados de pesquisa do log de auditoria.  <br/> |
|ObjectType  <br/> |O tipo de objeto de descoberta eletrônica que o usuário criou, excluiu ou modificou; por exemplo, uma ação de pesquisa de conteúdo (Visualizar, exportar ou limpar), uma ocorrência de descoberta eletrônica ou uma pesquisa de conteúdo.  <br/> |
|Operation  <br/> |O nome da operação que corresponde à atividade de descoberta eletrônica executada.  <br/> |
|OrganizationId  <br/> |O GUID da sua organização do Office 365.  <br/> |
|Parâmetros  <br/> |O nome e o valor dos parâmetros que foram usados com o cmdlet correspondente.  <br/> |
|PublicFolderLocations  <br/> |Os locais de pasta pública no Exchange Online que estão incluídos em uma pesquisa de conteúdo ou colocados em retenção em uma ocorrência de descoberta eletrônica.  <br/> |
|Consulta  <br/> |A consulta de pesquisa associada à atividade, como uma pesquisa de conteúdo ou uma retenção baseada em consulta.  <br/> |
|RecordType  <br/> |O tipo de operação indicado pelo registro. O valor **18** indica um evento relacionado a uma atividade listada na seção [atividades de cmdlet de descoberta eletrônica](#ediscovery-cmdlet-activities) . Um valor de **24** indica um evento relacionado a uma atividade listada na seção [como Pesquisar e exibir atividades de descoberta eletrônica](#how-to-search-for-and-view-ediscovery-activities) .  <br/> |
|ResultStatus  <br/> |Indica se a ação (especificada na propriedade Operation) foi bem-sucedida ou não.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica que a atividade era um evento de centro de conformidade de & de segurança. Todas as atividades de descoberta eletrônica terão o valor **0** para esta propriedade.  <br/> |
|SharepointLocations  <br/> |Os sites do SharePoint Online que estão incluídos em uma pesquisa de conteúdo ou colocados em retenção em uma ocorrência de descoberta eletrônica.  <br/> |
|StartTime  <br/> |A data e hora no tempo universal coordenado (UTC) quando a atividade de descoberta eletrônica foi iniciada.  <br/> |
|UserId  <br/> |O usuário que realizou a atividade (especificado na Propriedade Operation) que resultou no registro que está sendo registrado em log. Observe que os registros de atividade de descoberta eletrônica realizadas por contas de sistema (como o NT AUTHORITY\SYSTEM) também estão incluídos no log de auditoria.  <br/> |
|UserKey  <br/> |Uma ID alternativa para o usuário identificado na propriedade UserId. Para atividades de descoberta eletrônica, o valor dessa propriedade é geralmente o mesmo que a propriedade UserId.  <br/> |
|UserServicePlan  <br/> |A assinatura do Office 365 usada por sua organização. Para atividades de descoberta eletrônica, essa propriedade geralmente está em branco.  <br/> |
|UserType  <br/> |O tipo de usuário que executou a operação. Os valores a seguir indicam o tipo de usuário.  <br/> 0 um usuário regular. 2 um administrador na sua organização do Office 365. 3 uma conta de administrador de datacenter da Microsoft ou sistema de datacenter. 4 uma conta do sistema. 5 um aplicativo. 6 uma entidade de serviço. |
|Versão  <br/> |Indica o número da versão da atividade (identificado pela Propriedade Operation) registrada.  <br/> |
|Workload  <br/> |O serviço do Office 365 em que a atividade ocorreu. Para atividades de descoberta eletrônica, o valor é **SecurityComplianceCenter**.  <br/> |
