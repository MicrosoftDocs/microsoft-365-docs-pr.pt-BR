---
title: Gerenciar trabalhos em investigações de dados
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Você pode acompanhar o status de processos de execução longa que resultam na execução de tarefas na ferramenta de investigações de dados no centro de conformidade do & de segurança.
ms.openlocfilehash: 0c93df9e7d5ec176c2150e706fe99ed239be8527
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072792"
---
# <a name="manage-jobs-in-data-investigations-preview"></a>Gerenciar trabalhos em investigações de dados (versão prévia)

Veja a seguir uma lista dos trabalhos (que geralmente são processos de longa duração) que são controlados na guia **trabalhos** de uma investigação em investigações de dados (versão prévia). Esses trabalhos são disparados por ações do usuário ao usar e gerenciar investigações.

| Tipo de trabalho           | Descrição     |
| :----------------- | :----------     |
|Adicionando dados a um conjunto de evidência | Um usuário adiciona os resultados de uma pesquisa a um conjunto de evidências.  Para saber mais, confira [Pesquisar dados em uma investigação](search-for-data.md). |
|Adicionar dados a outro conjunto de evidência | Um usuário adiciona documentos de um conjunto de evidências a um conjunto diferente de evidências no mesmo caso.|
|Adição de dados que não sejam do Office 365 a um conjunto de evidências | Um usuário carrega dados que não são do Office 365 em um conjunto de evidências. Os dados também são indexados durante esse processo. Por exemplo, os arquivos de um servidor de arquivos local ou de um computador cliente são carregados em um conjunto de evidências. Para obter mais informações, consulte [carregar dados não-Office 365 em evidência](load-non-office365-data.md).| 
|Adicionando dados corrigidos a um conjunto de evidências | Dados com erros de processamento são corrigidos e carregados novamente em um conjunto de evidências. Confira mais informações em [correção de erros ao processar dados para uma investigação](error-remediation.md). | 
|Comparando conjuntos de carregamento | Um usuário examina as diferenças entre diferentes conjuntos de carga em um conjunto de evidências. Um conjunto de carga é uma instância de adição de dados a um conjunto de evidências. Por exemplo, se você adicionar os resultados de duas pesquisas diferentes ao mesmo conjunto de evidência, cada uma delas representaria um conjunto de carga. Para obter mais informações, consulte [Manage Load sets](manage-load-sets.md). |
|Convertendo documentos redigidos em PDF|Após um usuário anotar um documento em um conjunto de evidência e redigir uma parte dele, ele poderá optar por converter o documento redigido em um arquivo PDF. Isso garante que a parte redigida não será visível quando o documento for exportado para apresentação. Para obter mais informações, consulte [revisar dados em evidência](review-data-in-evidence.md). |
|Excluir itens de locais originais | Esse trabalho é acionado quando um usuário seleciona a caixa de correio e itens de site em um conjunto de evidências e, em seguida, clica em **excluir itens de locais originais** no menu **ação** para excluí-los. Este trabalho acompanha o progresso de exclusão reversível dos itens selecionados de seus locais de conteúdo original. Para obter mais informações, consulte [excluir itens do local original](delete-items-from-original-locations.md).|
|Estimando resultados de pesquisa | Depois que um usuário cria e executa uma nova pesquisa (ou executa uma pesquisa existente), a ferramenta de pesquisa pesquisa o índice de itens que correspondem à consulta de pesquisa e prepara uma estimativa que inclui o número e o tamanho total de todos os itens pela pesquisa e o número de fontes de dados Sea rched.  Para saber mais, confira [Pesquisar dados em uma investigação](search-for-data.md). | 
|Preparando dados para exportação | Um usuário exporta documentos de um conjunto de evidências. Quando o processo de exportação é concluído, ele pode baixar os dados exportados para um computador local. Para obter mais informações, consulte [exportar dados de uma investigação](export-data.md). | 
|Preparando para a resolução de erros |Quando um usuário seleciona um arquivo e cria uma correção de erro no modo de exibição de erro na guia **processamento** de uma investigação, a primeira etapa do processo é carregar o arquivo que tem o erro de processamento para um local de armazenamento do Azure na nuvem da Microsoft. Este trabalho acompanha o andamento do processo de carregamento. Para obter mais informações sobre o fluxo de trabalho de correção de erro, consulte [Error remediation When Processing data for a Investigation](error-remediation.md).| 
|Preparando visualização de pesquisa | Depois que um usuário cria e executa uma nova pesquisa (ou executa uma pesquisa existente), a ferramenta de pesquisa prepara um subconjunto de itens de exemplo (que correspondem à consulta de pesquisa) que pode ser visualizado. A visualização dos resultados da pesquisa pode ajudá-lo a determinar a eficácia da pesquisa.  Para saber mais, confira [Pesquisar dados em uma investigação](search-for-data.md). | 
|Indexar novamente os dados de pessoas de interesse | Quando você adiciona uma pessoa de interesse a uma investigação, todos os itens parcialmente indexados na pessoa de fontes de dados selecionadas de interesse são re-indexados por um processo chamado *indexação avançada*. Esse trabalho também é acionado quando você clica em **Atualizar índice** no modo de exibição de índice na guia **processamento** de uma investigação. Para obter mais informações, consulte [indexação avançada de dados para uma investigação](index-data-people-of-interest.md).
|Executando o Analytics | Um usuário analisa dados em um conjunto de evidências executando ferramentas de análise, como detecção de duplicidades, análise de threads de email e análise de temas. Para obter mais informações, consulte [executar análise para investigar mais rápido](run-analytics-to-investigate-faster.md). | 
|Marcando documentos | Esse trabalho é acionado quando um usuário clica em **Iniciar trabalho de marcação** no **painel de marcação** ao revisar documentos em um conjunto de evidências. Um usuário pode iniciar esse trabalho depois de marcar documentos em um conjunto de evidências e, em seguida, selecioná-los em massa no painel Exibir documento. Para obter mais informações, consulte [tag Documents in Evidence](tag-documents.md). | 
|||

## <a name="job-status"></a>Status do trabalho

A tabela a seguir descreve os diferentes Estados de status dos trabalhos.

| Status           | Descrição     |
| :----------------- | :----------     |
| Submitted | Um novo trabalho foi criado.  A data e a hora em que o trabalho foi enviado é exibida na coluna **criado** na guia **trabalhos** . |
| Falha no envio | Falha no envio do trabalho.  Você deve tentar executar novamente a ação que disparou o trabalho. |
| Em andamento | O trabalho está em andamento. Você pode monitorar o andamento do trabalho na guia **trabalhos** . |
| Foi | O trabalho foi concluído com êxito. A data e hora em que o trabalho foi concluído é exibida na coluna **concluído** da guia **trabalhos** . |
| Parcialmente bem-sucedido | O trabalho foi parcialmente bem-sucedido. |
| Failed | O trabalho falhou.  Você deve tentar executar novamente a ação que disparou o trabalho. Se o trabalho falhar uma segunda vez, recomendamos que você entre em contato com o suporte da Microsoft e forneça as informações de suporte do trabalho. |
|||
