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
description: Trabalhos avançados de Descoberta e Ajudam você a rastrear o status de processos de longa duração relacionados à execução de várias tarefas avançadas de Descoberta e Descoberta.
ms.openlocfilehash: 7b80df3f9891105d59a1741e9e0288ef0e67c25e
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454652"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Gerenciar trabalhos na Descoberta Avançada

Aqui está uma lista dos trabalhos (que normalmente são processos de longa duração) que são rastreados na guia **Trabalhos** de um caso em Descoberta Avançada. Esses trabalhos são disparados por ações do usuário ao usar e gerenciar casos.

| Tipo de trabalho           | Descrição     |
| :----------------- | :----------     |
|Adicionar dados a um conjunto de revisão | Um usuário adiciona os resultados de uma pesquisa a um conjunto de revisão. Este trabalho consiste em dois sub trabalhos: </br>• **GatheringItems** - Uma lista de itens que combinam com a consulta de pesquisa (e a fonte de dados do Microsoft 365 em que eles estão localizados) é gerada. </br>• **Ingestão & Indexação** - Os itens que corresponderem à consulta de pesquisa são copiados para um local de Armazenamento do Azure (em um processo chamado *ingestão*) e, em seguida, esses itens no local de Armazenamento do Azure são reindexados. Esse novo índice é usado ao consultar e analisar itens no conjunto de dados. </br></br>Para obter mais informações, [consulte Adicionar resultados de pesquisa a um conjunto de revisão](add-data-to-review-set.md). |
|Adicionar dados a outro conjunto de revisão | Um usuário adiciona documentos de um conjunto de revisão a um conjunto de revisão diferente no mesmo caso. Para obter mais informações, [consulte Adicionar dados a um conjunto de revisão de outro conjunto de revisão.](add-data-to-review-set-from-another-review-set.md)|
|Adicionar dados que não são do Microsoft 365 a um conjunto de revisão | Um usuário carrega dados que não são do Microsoft 365 para um conjunto de revisão. Os dados também são indexados durante esse processo. Por exemplo, arquivos de um servidor de arquivos local ou de um computador cliente são carregados para um conjunto de revisão. Para obter mais informações, [consulte Load non-Microsoft 365 data into a review set](load-non-office-365-data-into-a-review-set.md).| 
|Adicionar dados remediados a um conjunto de revisão | Os dados com erros de processamento são remediados e carregados de volta em um conjunto de revisão. Para saber mais, confira:</br>• [Correção de erros ao processar dados](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Correção de erro de item único](single-item-error-remediation.md)| 
|Comparando conjuntos de carga | Um usuário analisa as diferenças entre conjuntos de carga diferentes em um conjunto de revisão. Um conjunto de carga é uma instância de adicionar dados a um conjunto de revisão. Por exemplo, se você adicionar os resultados de duas pesquisas diferentes ao mesmo conjunto de revisão, cada uma representará um conjunto de carga. |
|Reconstrução de conversa|Quando um usuário adiciona os resultados de uma pesquisa a um conjunto de revisão de conversa, as conversas de mensagens instantâneas (também chamadas de conversas encadeadas *)* em serviços como o Microsoft Teams são reconstruídas em um arquivo PDF. Esse trabalho também é acionado quando um usuário clica em **Ação > Criar PDFs de conversa** em um conjunto de revisão. Para obter mais informações, [consulte Review conversations in Advanced eDiscovery](conversation-review-sets.md).
|Converter documentos redacted em PDF|Depois que um usuário anota um documento em um conjunto de revisão e redacta uma parte dele, ele pode optar por converter o documento redacted em um arquivo PDF. Isso garante que a parte redacted não ficará visível se o documento for exportado para apresentação. Para obter mais informações, [consulte Exibir documentos em um conjunto de revisão](annotating-and-redacting-documents.md). |
|Estimando resultados da pesquisa | Depois que um usuário cria e executa uma nova pesquisa (ou executa uma pesquisa existente), a ferramenta de pesquisa pesquisa o índice de itens que corresponderem à consulta de pesquisa e prepara uma estimativa que inclui o número e o tamanho total de todos os itens pela pesquisa e o número de fontes de dados pesquisadas.  Para obter mais informações, consulte [Coletar dados para um caso](collecting-data-for-ediscovery.md). | 
|Preparando dados para exportação | Um usuário exporta documentos de um conjunto de revisão. Quando o processo de exportação for concluído, eles poderão baixar os dados exportados para um computador local. Para obter mais informações, consulte [Exportar dados de caso](exporting-data-ediscover20.md). | 
|Preparando-se para a resolução de erros |Quando um usuário seleciona um arquivo e cria uma nova correção de erro no modo de exibição Erro na guia Processamento de um caso, a primeira etapa do processo é carregar o arquivo que tem o erro de processamento em um local de Armazenamento do Azure na nuvem da Microsoft.  Esse trabalho rastreia o andamento do processo de carregamento. Para obter mais informações sobre o fluxo de trabalho de correção de erros, consulte [Error remediation when processing data](error-remediation-when-processing-data-in-advanced-ediscovery.md). | 
|Preparando a visualização de pesquisa | Depois que um usuário cria e executa uma nova pesquisa (ou executa uma pesquisa existente), a ferramenta de pesquisa prepara um subconjunto de exemplo de itens (que combinam com a consulta de pesquisa) que pode ser visualizado. Visualizar os resultados da pesquisa ajuda a determinar a eficácia da pesquisa.  Para obter mais informações, consulte [Coletar dados para um caso](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Re indexação de dados custodiados | Quando você adiciona um custodiante a um caso, todos os itens parcialmente indexados nas fontes de dados selecionadas do custodiante são reindexados por um processo chamado *indexação avançada*. Esse trabalho também é acionado quando  você clica em Atualizar índice na guia Processamento de uma ocorrência e quando você atualiza o índice para um custodiante específico na página de sobrevoo de propriedades custodiantes.  Para obter mais informações, consulte [Indexação avançada de dados custodiados](indexing-custodian-data.md).
|Executando análise | Um usuário analisa dados em um conjunto de revisão executando ferramentas de análise de Descoberta Automática Avançada, como detecção quase duplicada, análise de threading de email e análise de temas. Para obter mais informações, consulte [Analisar dados em um conjunto de revisão](analyzing-data-in-review-set.md). | 
|Marcando documentos | Esse trabalho é acionado quando um usuário clica em Iniciar o trabalho de **marcação** no painel **Marcação** ao revisar documentos em um conjunto de revisão. Um usuário pode iniciar esse trabalho depois de marcar documentos em um conjunto de revisão e, em seguida, seleciona-los em massa no painel do documento de exibição. Para obter mais informações, consulte [Tag documents in a review set](tagging-documents.md). | 
|||

## <a name="job-status"></a>Status do trabalho

A tabela a seguir descreve os diferentes estados de status para trabalhos.

| Status           | Descrição     |
| :----------------- | :----------     |
| Submitted | Um novo trabalho foi criado.  A data e a hora em que o trabalho foi enviado é exibida na coluna **Criado** na **guia Trabalhos.** |
| Falha no envio | O envio do trabalho falhou.  Você deve tentar reprisar a ação que disparou o trabalho. |
| Em andamento | O trabalho está em andamento, você pode monitorar o andamento do trabalho na **guia Trabalhos.** |
| Bem-sucedido | O trabalho foi concluído com êxito. A data e a hora em que o trabalho foi concluído é exibido na coluna **Concluído** na **guia Trabalhos.** |
| Parcialmente bem-sucedido | O trabalho foi bem-sucedido. Esse status normalmente é retornado quando o trabalho não encontra dados parcialmente indexados (também chamados de dados não indexados *)* em algumas das fontes de dados custodiadas.  |
| Falhou | O trabalho falhou.  Você deve tentar reprisar a ação que disparou o trabalho. Se o trabalho falhar uma segunda vez, recomendamos que você entre em contato com o Suporte da Microsoft e forneça as informações de suporte do trabalho. |
|||
