---
title: Gerenciar trabalhos na Descoberta Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Os trabalhos de Descobertas Avançadas ajudam a acompanhar o status de processos de longa execução relacionados à execução de várias tarefas de Descoberta Avançada.
ms.openlocfilehash: f5c366b8809b1b5c08b15972118c40d7d29e33c4
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750762"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Gerenciar trabalhos na Descoberta Avançada

Aqui está uma lista dos trabalhos (que normalmente são processos de longa execução) que são rastreados na guia **Trabalhos** de um caso na Descoberta Avançada. Esses trabalhos são disparados por ações do usuário ao usar e gerenciar casos.

| Tipo de trabalho           | Descrição     |
| :----------------- | :----------     |
|Adicionando dados a um conjunto de revisão | Um usuário adiciona os resultados de uma pesquisa a um conjunto de revisão. Esse trabalho consiste em dois sub trabalhos: </br>• **GatheringItems** - Uma lista de itens que corresponderem à consulta de pesquisa (e à fonte de dados do Microsoft 365 em que eles estão localizados) é gerada. </br>• **Ingestão & Indexação** - Os itens que corresponderem à consulta de pesquisa são copiados para um local de armazenamento do Azure (em um processo chamado *ingestão)* e, em seguida, esses itens no local de armazenamento do Azure são reindexados. Esse novo índice é usado ao consultar e analisar itens no conjunto de dados. </br></br>Para obter mais informações, [consulte Adicionar resultados de pesquisa a um conjunto de revisão.](add-data-to-review-set.md) |
|Adicionando dados a outro conjunto de revisão | Um usuário adiciona documentos de um conjunto de revisão a um conjunto de revisão diferente no mesmo caso. Para obter mais informações, [consulte Adicionar dados a um conjunto de revisão de outro conjunto de revisão.](add-data-to-review-set-from-another-review-set.md)|
|Adicionando dados que não são do Microsoft 365 a um conjunto de revisão | Um usuário carrega dados que não são do Microsoft 365 para um conjunto de revisão. Os dados também são indexados durante esse processo. Por exemplo, arquivos de um servidor de arquivos local ou de um computador cliente são carregados para um conjunto de revisão. Para obter mais informações, [consulte Carregar dados que não são do Microsoft 365 em um conjunto de revisão.](load-non-office-365-data-into-a-review-set.md)| 
|Adicionando dados remediados a um conjunto de revisão | Os dados com erros de processamento são remediados e carregados de volta em um conjunto de revisão. Para saber mais, confira:</br>• [Correção de erros ao processar dados](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Correção de erro de item único](single-item-error-remediation.md)| 
|Comparando conjuntos de carga | Um usuário analisa as diferenças entre diferentes conjuntos de carga em um conjunto de revisão. Um conjunto de carga é uma instância de adição de dados a um conjunto de revisão. Por exemplo, se você adicionar os resultados de duas pesquisas diferentes ao mesmo conjunto de revisão, cada uma representará um conjunto de carga. |
|Reconstrução da conversa|Quando um usuário adiciona os resultados de uma pesquisa a um conjunto de revisão de conversa, as conversas de mensagens instantâneas (também chamadas de conversas encadeadas) em serviços como o Microsoft Teams são reconstruídas em um arquivo PDF. Esse trabalho também é disparado quando um usuário clica em **Ação > Criar PDFs** de conversa em um conjunto de revisão. Para obter mais informações, [consulte Review conversations in Advanced eDiscovery](conversation-review-sets.md).
|Converter documentos editados em PDF|Depois que um usuário anota um documento em um conjunto de revisão e reacta uma parte dele, ele pode optar por converter o documento editado em um arquivo PDF. Isso garante que a parte redacted não ficará visível se o documento for exportado para apresentação. Para obter mais informações, [consulte Exibir documentos em um conjunto de revisão.](annotating-and-redacting-documents.md) |
|Estimando resultados de pesquisa | Depois que um usuário cria e executa uma nova pesquisa (ou executa uma pesquisa existente), a ferramenta de pesquisa pesquisa o índice de itens que corresponderem à consulta de pesquisa e prepara uma estimativa que inclui o número e o tamanho total de todos os itens pela pesquisa e o número de fontes de dados pesquisadas.  Para obter mais informações, [consulte Coletar dados para uma ocorrência.](collecting-data-for-ediscovery.md) | 
|Preparando dados para exportação | Um usuário exporta documentos de um conjunto de revisão. Quando o processo de exportação estiver concluído, eles poderão baixar os dados exportados para um computador local. Para obter mais informações, consulte [Exportar dados de caso.](exporting-data-ediscover20.md) | 
|Preparando-se para resolução de erros |Quando um usuário seleciona um arquivo e cria uma nova correção de erro no modo de exibição De erro na guia Processamento de um caso, a primeira etapa do processo é carregar o arquivo que tem o erro de processamento para um local de armazenamento do Azure na nuvem da Microsoft.  Esse trabalho rastreia o progresso do processo de carregamento. Para obter mais informações sobre o fluxo de trabalho de correção de erros, consulte Correção [de erro ao processar dados.](error-remediation-when-processing-data-in-advanced-ediscovery.md) | 
|Preparando a visualização da pesquisa | Depois que um usuário cria e executa uma nova pesquisa (ou executa uma pesquisa existente), a ferramenta de pesquisa prepara um subconjunto de exemplo de itens (que corresponderem à consulta de pesquisa) que podem ser visualizados. A visualização dos resultados da pesquisa ajuda a determinar a eficácia da pesquisa.  Para obter mais informações, [consulte Coletar dados para uma ocorrência.](collecting-data-for-ediscovery.md#view-search-results-and-statistics) | 
|Indexação de dados custodiante | Quando você adiciona um custodiante a uma ocorrência, todos os itens parcialmente indexados nas fontes de dados selecionadas do custodiante são reindexados por um processo chamado *indexação avançada.* Esse trabalho também é acionado quando  você clica em Atualizar índice na guia Processamento de uma ocorrência e quando você atualiza o índice de um custodiante específico na página do flyout de propriedades custodiantes.  Para obter mais informações, [consulte Indexação avançada de dados custodiante](indexing-custodian-data.md).
|Executando análises | Um usuário analisa os dados em um conjunto de revisão executando ferramentas de análise de Descoberta Automática Avançada, como detecção quase duplicada, análise de threading de email e análise de temas. Para obter mais informações, [consulte Analisar dados em um conjunto de revisão.](analyzing-data-in-review-set.md) | 
|Marcar documentos | Esse trabalho é acionado quando um usuário clica  em **Iniciar** marcação no painel marcação ao revisar documentos em um conjunto de revisão. Um usuário pode iniciar esse trabalho depois de marcar documentos em um conjunto de revisão e, em seguida, selecioná-los em massa no painel de exibição do documento. Para obter mais informações, consulte [Documentos de marca em um conjunto de revisão.](tagging-documents.md) | 
|||

## <a name="job-status"></a>Status do trabalho

A tabela a seguir descreve os diferentes estados de status para trabalhos.

| Status           | Descrição     |
| :----------------- | :----------     |
| Submitted | Um novo trabalho foi criado.  A data e a hora em que o trabalho foi enviado é exibida na coluna **Criado** **na** guia Trabalhos. |
| Falha no envio | O envio de trabalho falhou.  Você deve tentar re-acionar o trabalho. |
| Em andamento | O trabalho está em andamento. Você pode monitorar o progresso do trabalho na **guia** Trabalhos. |
| Bem-sucedido | O trabalho foi concluído com êxito. A data e a hora em que  o trabalho foi concluído é exibida na coluna Concluído, na **guia** Trabalhos. |
| Parcialmente bem-sucedido | O trabalho foi parcialmente bem-sucedido. Esse status normalmente é retornado quando o trabalho não encontra dados parcialmente indexados (também chamados de dados não indexados) em algumas das fontes de dados custodiante.  |
| Falhou | O trabalho falhou.  Você deve tentar re-acionar o trabalho. Se o trabalho falhar uma segunda vez, recomendamos que você entre em contato com o Suporte da Microsoft e forneça as informações de suporte do trabalho. |
|||
