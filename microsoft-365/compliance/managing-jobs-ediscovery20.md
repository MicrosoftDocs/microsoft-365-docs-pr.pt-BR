---
title: Gerenciar trabalhos na descoberta eletrônica avançada
f1.keywords:
- NOCSH
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
description: Trabalhos de descoberta eletrônica avançados ajudam a acompanhar o status de processos de longa execução relacionados à execução de várias tarefas avançadas de descoberta eletrônica.
ms.openlocfilehash: eca2eff32b54f783c6c983a8a20237db2faf2240
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071568"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Gerenciar trabalhos na descoberta eletrônica avançada

Veja a seguir uma lista dos trabalhos (que geralmente são processos de longa duração) que são controlados na guia **trabalhos** de um caso na descoberta eletrônica avançada. Esses trabalhos são disparados por ações do usuário ao usar e gerenciar ocorrências.

| Tipo de trabalho           | Descrição     |
| :----------------- | :----------     |
|Adicionando dados a um conjunto de revisão | Um usuário adiciona os resultados de uma pesquisa a um conjunto de revisão. Esse trabalho consiste em dois subtrabalhos: </br>• **GatheringItems** -uma lista de itens que correspondem à consulta de pesquisa (e a fonte de dados do Office 365 em que eles estão localizados) é gerada. </br>• **Ingestão & indexação** – os itens que correspondem à consulta de pesquisa são copiados para um local de armazenamento do Azure (em um processo chamado *ingestão*) e os itens no local de armazenamento do Azure são reindexados. Esse novo índice é usado ao consultar e analisar itens no conjunto de dados. </br></br>Para obter mais informações, consulte [Add Search Results to a Review Set](add-data-to-review-set.md). |
|Adicionando dados a outro conjunto de revisão | Um usuário adiciona documentos de uma análise configurada para um conjunto de revisão diferente no mesmo caso. Para obter mais informações, consulte [Adicionar dados a um conjunto de revisão de outro conjunto de revisão](add-data-to-review-set-from-another-review-set.md).|
|Adição de dados que não sejam do Office 365 a um conjunto de revisão | Um usuário carrega dados que não são do Office 365 em um conjunto de revisão. Os dados também são indexados durante esse processo. Por exemplo, os arquivos de um servidor de arquivos local ou de um computador cliente são carregados em um conjunto de revisão. Para obter mais informações, consulte [carregar dados não-Office 365 em um conjunto de revisão](load-non-office365-data.md).| 
|Adicionando dados corrigidos a um conjunto de revisão | Dados com erros de processamento são corrigidos e carregados novamente em um conjunto de revisão. Para saber mais, confira:</br>• [Correção de erro ao processar dados](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Correção de erro de item único](single-item-error-remediation.md)| 
|Comparando conjuntos de carregamento | Um usuário examina as diferenças entre diferentes conjuntos de carga em um conjunto de revisão. Um conjunto de carga é uma instância de adição de dados a um conjunto de revisão. Por exemplo, se você adicionar os resultados de duas pesquisas diferentes ao mesmo conjunto de revisão, cada uma representaria um conjunto de carga. Para obter mais informações, consulte [Manage Load sets](manage-load-sets.md). |
|Reconstrução de conversa|Quando um usuário adiciona os resultados de uma pesquisa a um conjunto de revisão de conversa, as conversas de mensagem instantânea (também chamadas de *conversa encadeadas*) em serviços como o Microsoft Teams são reconstruídas em um arquivo PDF. Esse trabalho também é acionado quando um usuário clica em **ação > criar PDFs de conversa** em um conjunto de revisão. Para obter mais informações, consulte [revisar conversas na descoberta eletrônica avançada](conversation-review-sets.md).
|Convertendo documentos redigidos em PDF|Depois que um usuário anotar um documento em um conjunto de revisão e redigir uma parte dele, ele poderá optar por converter o documento redigido em um arquivo PDF. Isso garante que a parte redigida não será visível se o documento for exportado para apresentação. Para obter mais informações, consulte [exibir documentos em um conjunto de revisão](annotating-and-redacting-documents.md). |
|Estimando resultados de pesquisa | Depois que um usuário cria e executa uma nova pesquisa (ou executa uma pesquisa existente), a ferramenta de pesquisa pesquisa o índice de itens que correspondem à consulta de pesquisa e prepara uma estimativa que inclui o número e o tamanho total de todos os itens pela pesquisa e o número de fontes de dados sear ched.  Para obter mais informações, consulte [coletar dados por um caso](collecting-data-for-ediscovery.md). | 
|Preparando dados para exportação | Um usuário exporta documentos de um conjunto de revisão. Quando o processo de exportação é concluído, ele pode baixar os dados exportados para um computador local. Para obter mais informações, consulte [exportar dados de caso](exporting-data-ediscover20.md). | 
|Preparando para a resolução de erros |Quando um usuário seleciona um arquivo e cria uma nova correção de erro no modo de exibição de erro na guia **processamento** de um caso, a primeira etapa no processo é carregar o arquivo que tem o erro de processamento para um local de armazenamento do Azure na nuvem da Microsoft. Este trabalho acompanha o andamento do processo de carregamento. Para obter mais informações sobre o fluxo de trabalho de correção de erro, consulte [Error remediation When Processing data](error-remediation.md). | 
|Preparando visualização de pesquisa | Depois que um usuário cria e executa uma nova pesquisa (ou executa uma pesquisa existente), a ferramenta de pesquisa prepara um subconjunto de itens de exemplo (que correspondem à consulta de pesquisa) que pode ser visualizado. A visualização dos resultados da pesquisa o ajuda a determinar a eficácia da pesquisa.  Para obter mais informações, consulte [coletar dados por um caso](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Reindexar dados de responsáveis | Quando você adiciona um responsáveis a um caso, todos os itens parcialmente indexados nas fontes de dados selecionadas do responsáveis são reindexados por um processo chamado *indexação avançada*. Esse trabalho também é acionado quando você clica em **Atualizar índice** na guia **processamento** de um caso e quando você atualiza o índice para um determinado profissional na página do menu de propriedades do responsáveis. Para saber mais, confira [indexação avançada de dados de responsáveis](indexing-custodian-data.md).
|Executando o Analytics | Um usuário analisa dados em um conjunto de revisão, executando ferramentas avançadas de análise de descoberta eletrônica, como detecção de duplicidades, análise de threads de email e análise de temas. Para obter mais informações, consulte [analisar dados em um conjunto de revisão](analyzing-data-in-review-set.md). | 
|Marcando documentos | Esse trabalho é acionado quando um usuário clica em **Iniciar trabalho de marcação** no **painel de marcação** ao revisar documentos em um conjunto de revisão. Um usuário pode iniciar esse trabalho depois de marcar documentos em um conjunto de revisão e, em seguida, selecioná-los em massa no painel Exibir documento. Para obter mais informações, consulte [marcas de formatação em documentos em um conjunto de revisão](tagging-documents.md). | 
|||

## <a name="job-status"></a>Status do trabalho

A tabela a seguir descreve os diferentes Estados de status dos trabalhos.

| Status           | Descrição     |
| :----------------- | :----------     |
| Submitted | Um novo trabalho foi criado.  A data e a hora em que o trabalho foi enviado é exibida na coluna **criado** na guia **trabalhos** . |
| Falha no envio | Falha no envio do trabalho.  Você deve tentar executar novamente a ação que disparou o trabalho. |
| Em andamento | O trabalho está em andamento, você pode monitorar o andamento do trabalho na guia **trabalhos** . |
| Foi | O trabalho foi concluído com êxito. A data e hora em que o trabalho foi concluído é exibida na coluna **concluído** da guia **trabalhos** . |
| Parcialmente bem-sucedido | O trabalho foi parcialmente bem-sucedido. Esse status normalmente é retornado quando o trabalho não encontrou dados parcialmente indexados (também chamados de *dados não indexados*) em algumas das fontes de dados do responsáveis.  |
| Falhou | O trabalho falhou.  Você deve tentar executar novamente a ação que disparou o trabalho. Se o trabalho falhar uma segunda vez, recomendamos que você entre em contato com o suporte da Microsoft e forneça as informações de suporte do trabalho. |
|||
