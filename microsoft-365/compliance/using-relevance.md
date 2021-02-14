---
title: Usar o módulo Relevância para analisar dados na Descoberta Eletrônico Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como o módulo relevância analisa dados em evidência com uma descrição do fluxo de trabalho de relevância e etapas de treinamento na Descoberta Avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286057"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a>Usar o módulo Relevância para analisar dados na Descoberta Eletrônico Avançada

Na Descoberta Avançada, o módulo Relevância inclui o treinamento de relevância e a revisão de arquivos relacionados a um caso. Para usar o fluxo de trabalho de Relevância, vá para Gerenciar conjunto de revisão dentro de um conjunto de revisão e clique em Mostrar Relevância. Há algumas etapas que você precisa concluir antes de iniciar o fluxo de trabalho:

- Processo: cada conjunto de carga adicionado ao conjunto de revisão será aparecer como um "contêiner" aqui. Você precisa processar esses documentos antes de adicioná-los ao módulo relevância; Também é aqui que você pode marcá-los como seed ou pré-marcado para um problema específico.

- Adicionar à Relevância: Em Cargas de Relevância, você pode adicionar documentos que foram processados para \> Relevância para torná-los disponíveis para treinamento.

O fluxo de trabalho relevância é mostrado e descrito da seguinte forma:
  
![Fluxo de trabalho de relevância](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Ciclos de avaliação e rastreamento:**
    
  - **Avaliação:** permite a avaliação antecipada com base em uma amostra aleatória de arquivos e usa essa avaliação para aplicar decisões para determinar o desempenho do processo de codificação preditiva. 
    
  - **Controle:** calcule e exibe os resultados provisórios da avaliação enquanto monitora a validade estatística do processo. 
    
- **Ciclos de treinamento e rastreamento**
    
  - **Marca**: a Descoberta Avançada aprende os critérios de relevância específicos para cada problema com base na revisão iterativa do especialista e na marcação de arquivos individuais.
    
  - **Controle:** calcule e exibe os resultados provisórios do treinamento de relevância enquanto monitora a validade estatística do processo. 
    
- **Cálculo em** lotes : Os critérios de relevância acumulados e aprendidas são aplicados a todo o conjunto de arquivos, e uma pontuação de Relevância é gerada para cada arquivo.
    
- **Decidir:** os resultados da análise aplicados a todo o caso são exibidos após o cálculo em lotes, e os dados usados para tomar decisões de revisão de documentos são exibidos.
    
- **Teste:** os resultados podem ser testados para verificar a validade e a eficácia do processamento de Descobertas Públicas Avançada.

- **Pesquisa:** depois que o fluxo de trabalho de Relevância for concluído, você poderá usar a saída, como o percentil de leitura de um documento, para o problema ao executar uma consulta no conjunto de revisão.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Diretrizes para treinamento e revisão de relevância

A seguir está uma visão geral das diretrizes de treinamento e revisão de relevância:
  
- **Erros e inconsistências:** se erros de marcação são feitos durante o treinamento, retorne aos exemplos de arquivo anteriores para corrigi-los. Se houver muitos erros para corrigir ou se houver uma nova perspectiva do caso ou do problema, os critérios de relevância deverão ser redefinidos pelo Administrador e o treinamento de Relevância será reiniciado.
    
- **Marcação e treinamento:** 
    
  - Os arquivos devem ser marcados com base apenas no conteúdo. Não considere metadados, como custodiante, data ou caminho do arquivo. 
    
  - Não considere indicações de intervalo de datas no texto ao marcar arquivos.
    
  - Não considere imagens gráficas incorporadas ao marcar arquivos.
     
  - Ignorar o texto aplicado à relevância será removido do conteúdo do arquivo exibido no ponto de vista de texto em Relevância. Se os valores para Ignorar texto foram definidos após o treinamento de relevância já iniciado, o novo texto ignorado será aplicado aos arquivos de exemplo criados a partir do ponto em que foi definido. O recurso Ignorar Texto deve ser usado com cautela, pois seu uso pode reduzir o desempenho da análise de arquivos
    
  - Use a **opção de marcação** Ignorar somente quando necessário. A Descoberta Avançada não treinará com base em arquivos ignorados. Na avaliação, se for difícil dizer se um arquivo é relevante, é melhor marcar como Relevante (R) ou Não Relevante (NR) sempre que possível, em vez de selecionar **Skip**. Quando a Descoberta Avançada avalia o treinamento, pode-se ver o quão bem esses tipos de arquivos foram processados.
    
  - Mesmo arquivos com uma quantidade muito pequena de texto extraído devem ser marcados no treinamento como R/NR, em vez de "Ignorar", quando possível. 
    
  - A marcação pode afetar o classificador, desde que o arquivo seja acessível e possa ser marcado como R/NR.
    
  - O número da sequência de arquivos na lista de arquivos de exemplo exibido na guia **Marca** permite que o usuário retorne à ordem original exibida dos arquivos. 
    
  - Você pode voltar a qualquer exemplo e alterar a marcação dos arquivos do conjunto de avaliação e treinamento. As alterações serão aplicadas ao criar o próximo exemplo.
    
  - Os arquivos verificados do Excel no formato PDF devem ser tratados da mesma forma que os arquivos nativos do Excel ao marcar arquivos.
    
  - Quando estiver em dúvida sobre a marcação de Relevância de um arquivo, consulte um especialista. A marcação incorreta durante o treinamento de relevância pode levar a perda de tempo mais tarde no processo e também pode ter um impacto negativo sobre a qualidade dos resultados gerais.
    
  - Palavras-chave definidas nas listas de palavras-chave serão exibidas em cores para ajudar o usuário a identificar arquivos relevantes durante a marcação.
    
- **Cálculo em** lote: os arquivos marcados como R/NR pelo especialista receberão uma pontuação de 0 ou 100. Isso se aplica à marcação feita antes do cálculo em lotes. Se o especialista alternou o problema para Ocioso após o Cálculo em Lote e continua marcando esse problema, as pontuações recém-marcadas não serão 100/0, mas sim a pontuação original.
    
- Issues **and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.
    
## <a name="steps-in-relevance-training"></a>Etapas do treinamento em relevância

Na guia **Controle de \> Relevância,** a Descoberta Avançada fornece recomendações sobre como prosseguir no processamento, com as próximas etapas. As implicações são descritas abaixo quando cada uma das etapas a seguir é recomendada no processo de treinamento de relevância. 
  
- Marcação/ Continuar marcação: Revisão de arquivo e marcação de relevância executadas por um especialista para cada arquivo e problema em um exemplo.
    
  - Implicação: um exemplo existente precisa ser marcado.
    
- Avaliação/continuar avaliação: permite a validação antecipada da relevância do problema de caso e uma visão preliminar da relevância da população de arquivos importada para o caso atual.
    
  - Implicação: mais avaliação é necessária ou recomendada.
    
- Treinamento/Continuar treinamento: processo durante o qual a Descoberta Avançada do eDiscovery aprende com o especialista que está marcando os exemplos de arquivo e adquire a capacidade de identificar critérios de relevância pertinentes a cada problema no contexto de cada caso.
    
  - Implicação: o problema precisa de mais treinamento; o próximo exemplo deve ser criado e marcado. 
    
- Cálculo em lotes: processo de relevância no qual a Descoberta Eletrônico Avançada pega o conhecimento adquirido durante o estágio de treinamento e o aplica a toda a população de arquivos. Todos os arquivos no grupo de arquivos pertinentes são avaliados para relevância e atribuídos com uma pontuação de relevância.
    
  - Implicação: o problema está estabilizado, e o cálculo em lote pode ser executado.
    
- Catch-up: A relevância indica quando um especialista revisa e marca um exemplo de arquivos selecionados de uma carga de arquivo adicional durante um cenário de Rolagem de Cargas.
    
  - Implicação: uma nova carga foi adicionada, e o catch-up é necessário para continuar funcionando.
    
- Inconsistências de marca: o processo identifica, por meio de um algoritmo de Descoberta Avançada, inconsistências no processo de marcação de arquivo que podem afetar negativamente a análise.
    
  - Implicação: o próximo exemplo incluirá arquivos que foram marcados em exemplos anteriores, e sua marcação deve ser refeita.
    
- Classificador de atualização: permite que o usuário aplique alterações de marcação ou de complicação.
    
  - Implicação: as alterações de marcação e de complicação podem ser aplicadas sem a necessidade de executar manualmente outro exemplo de Relevância.
    
- Em espera: O processo de treinamento de relevância foi concluído.
    
  - Implicação: nenhum treinamento de relevância é necessário neste momento.
    
Embora a Descoberta Avançada o guie pelo processo, com as próximas etapas recomendadas em diferentes estágios, ela também permite navegar entre guias e páginas e fazer escolhas para abordar situações que podem ser pertinentes ao seu processo individual de caso, problema ou revisão de documentos. 
  
É possível aceitar ou substituir as opções de processamento da Próxima etapa da Descoberta Avançada. Se você deseja executar uma etapa diferente da  próxima etapa recomendada, clique na próxima etapa  listada na exibição do problema expandido na caixa de diálogo, clique no botão Modificar ao lado da próxima etapa e selecione outra opção próxima etapa. 
  
> [!NOTE]
> Algumas opções podem permanecer desabilitadas após o desbloqueio, pois não há suporte para uso nesse momento no processo. 
  
## <a name="more-information"></a>Mais informações

[Noções básicas sobre avaliação em relevância](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Marcação e avaliação](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Treinamento de marcação e relevância](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Rastreando a análise de relevância](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir com base nos resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testando a análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md)

[Consultar os dados em um conjunto de revisão](review-set-search.md)
