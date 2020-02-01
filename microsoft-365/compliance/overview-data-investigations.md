---
title: Visão geral das investigações de dados (prévia) no Microsoft 365
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
description: Este artigo descreve a nova ferramenta de investigações de dados (visualização) no Microsoft 365.
ms.openlocfilehash: cd60b16f6d0f968c0c87f3e44ee2f643c90ebb10
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597788"
---
# <a name="overview-of-data-investigations-preview-in-microsoft-365"></a>Visão geral das investigações de dados (prévia) no Microsoft 365

Um despejo de dados ocorre quando um documento que contém conteúdo confidencial, confidencial ou mal-intencionado é liberado em um ambiente não confiável. Quando um despejo de dados é detectado, é importante conter rapidamente o ambiente, avaliar o tamanho e os locais do derramamento, examinar as atividades do usuário em torno dele e, em seguida, excluir os dados derramados do serviço. Usando a nova ferramenta de investigações de dados (visualização), você pode pesquisar dados confidenciais, mal-intencionados ou incorretos no Office 365, investigar o que aconteceu e tomar as medidas apropriadas para corrigir o derramamento.  

Este artigo descreve como usar os recursos da nova ferramenta de investigações de dados (visualização) para lidar com um cenário de derramamento de dados.

## <a name="permissions"></a>Permissões

Para acessar e conduzir uma investigação de dados, você precisa ser membro do grupo de função do investigador de dados. Para obter mais informações, consulte [atribuir permissões para investigações de dados](permissions.md).

## <a name="data-investigations-preview-workflow"></a>Fluxo de trabalho de investigações de dados (prévia) 

As seções a seguir descrevem cada etapa no fluxo de trabalho interno em investigações de dados (prévia). A captura de tela a seguir mostra a guia **início** de uma investigação chamada *alto risco: vazamento de documentos financeiros*. 

![Fluxo de trabalho na ferramenta de investigações de dados](media/DataInvestigationsWorkflow.png)

## <a name="search-for-sensitive-malicious-or-misplaced-data"></a>Procurar dados confidenciais, mal-intencionados ou colocados no local errado

Use a guia **pesquisas** para criar pesquisas para localizar os dados do Office 365 que você deseja corrigir. Você pode criar e executar pesquisas baseadas em consulta para identificar um conjunto de mensagens e documentos de email que podem conter dados derramados e, em seguida, coletá-los como evidências para análise e análise. Além disso, você pode usar a ferramenta de pesquisa para visualizar documentos de amostra e exibir estatísticas de pesquisa que podem ajudá-lo a refinar e aprimorar os resultados da pesquisa. Quando estiver satisfeito de que os resultados da pesquisa contenham todos os dados relevantes para a investigação, adicione os resultados da pesquisa ao conjunto de evidências para análise adicional, avaliação de impacto e realização de ações corretivas conforme necessário. Para saber mais, confira [Pesquisar dados em uma investigação](search-for-data.md).

## <a name="review-and-investigate-evidence"></a>Analisar e investigar evidências

Use a guia **evidência** para investigar os dados que você coletou do serviço em tempo real, que neste caso é o Office 365. Os dados no conjunto de evidências é um instantâneo dos resultados de pesquisa coletados. Quando você adiciona resultados de pesquisa como evidência, um processo é disparado para extrair arquivos, metadados e texto. Quando esse processo é concluído, a ferramenta de investigações de dados cria um novo índice de todos os dados e o adiciona a um conjunto de evidências. Para qualquer investigação sensível ao tempo, isso permite que você contenha rapidamente o ambiente, excluindo os dados localizados nos locais de conteúdo originais (no Live Service) ao investigar as evidências coletadas em um ambiente em quarentena. Depois que a evidência é coletada, você pode executar mais consultas para restringir os dados por intervalo de tempo, tipos de arquivo, proprietários de dados e outros tipos de condições. Por exemplo, usando as condições autor, remetente e destinatário, você pode identificar rapidamente aqueles que estavam envolvidos no despejo dos dados e se qualquer um dos dados derramados foi compartilhado com pessoas de fora da sua organização.

Você também pode executar a análise avançada nas evidências coletadas. Isso pode fornecer temas gerais e organizar evidências por threads de email, duplicatas exatas e quase duplicatas para facilitar sua investigação. Você pode revisar documentos no modo de exibição de texto extraído ou no formato de arquivo nativo e marcá-los com resultados de investigação. Para saber mais, confira:

  - [Revisar dados em evidência](review-data-in-evidence.md)

  - [Executar análise para investigar mais rápido](run-analytics-to-investigate-faster.md)


## <a name="managing-people-of-interest"></a>Gerenciando pessoas de interesse

Use a guia **pessoas de interesse** para adicionar e gerenciar as pessoas que você identificou como pessoas de interesse durante a investigação da evidência. Quando você adiciona pessoas de interesse, suas fontes de dados, como a sua caixa de correio e a conta do OneDrive, são identificadas e mapeadas. Em seguida, você pode escopor pesquisas pesquisando somente os locais de conteúdo dessas pessoas. Quando delimitado por pessoas de interesse, as pesquisas são mais eficientes e precisas porque a ferramenta reprocessa quaisquer dados não indexados, como imagens ou tipos de arquivo não suportados. Na guia **pessoas de interesse** , você também pode exibir e pesquisar a atividade de log de auditoria dessas pessoas para ajudar a investigar ainda mais. Você pode adicionar mais pessoas de interesse durante a investigação. Para obter mais informações, consulte [gerenciar pessoas de interesse em uma investigação](manage-people-of-interest.md).

## <a name="indexing-the-data-of-people-of-interest"></a>Indexando os dados de pessoas de interesse

Adicionar uma pessoa de interesse a uma investigação reindexa todos os itens parcialmente indexados das fontes de dados da pessoa. Esse processo é chamado de *indexação avançada*. A indexação avançada reprocessa dados, como imagens e tipos de arquivo não suportados, de forma que esses dados sejam totalmente detectáveis quando você executa pesquisas para coletar dados de uma investigação. Use a guia **processamento** para monitorar o status da indexação avançada e corrigir qualquer erro de processamento que possa ocorrer usando um processo chamado *correção de erros*. Confira mais informações em [correção de erros ao processar dados para uma investigação](error-remediation.md).

## <a name="exporting-data"></a>Exportando dados

Se você quiser exportar dados, use a guia **exportações** para gerenciar um trabalho de exportação e baixar dados do conjunto de evidências. Quando você exporta evidências, os dados são carregados em um local de armazenamento do Azure e, em seguida, estão disponíveis para download em um computador local. Na guia **exportações** , você pode obter a URL do local de armazenamento do Azure e a chave de avaliação de armazenamento, que são necessárias para baixar os dados exportados. Para obter mais informações, consulte [exportar dados de uma investigação](export-data.md).

## <a name="managing-jobs"></a>Gerenciando trabalhos

Use a guia **trabalhos** para monitorar os processos de execução demorada para tarefas relacionadas à investigação. Isso inclui trabalhos para executar pesquisas, adicionar dados a um conjunto de evidências, reindexar dados e exportar evidências. Por exemplo, você pode criar uma pesquisa na guia **pesquisas** que inclui várias fontes de dados. O status desse processo de pesquisa é exibido na guia **trabalhos** . Para obter mais informações, consulte [Manage Jobs in a data Investigation](manage-jobs.md).

## <a name="configuring-investigation-settings"></a>Definindo configurações de investigação

Use a guia **configurações** para definir as configurações de toda a investigação. Isso inclui adicionar membros a uma investigação, fechar ou excluir uma investigação e configurar o comportamento de pesquisa e análise.
