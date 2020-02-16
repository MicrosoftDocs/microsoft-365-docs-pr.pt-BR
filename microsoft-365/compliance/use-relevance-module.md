---
title: Usar o módulo de relevância para analisar dados em evidência
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
description: ''
ms.openlocfilehash: 0b6c42f594ef10c868051d81b0a7ea4b7ff84e00
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080608"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a>Usar o módulo de relevância para analisar dados em evidência

Em investigações de dados (prévia), o módulo de relevância inclui o treinamento de relevância e a revisão de arquivos relacionados a uma investigação. O fluxo de trabalho de relevância é mostrado e descrito da seguinte maneira:
  
![Fluxo de trabalho de relevância](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Ciclos de avaliação e controle**:
    
  - **Avaliação**: habilita a avaliação prévia com base em uma amostra aleatória de arquivos e usa essa avaliação para aplicar decisões para determinar o desempenho do processo de codificação de previsão. 
    
  - **Track**: calcular e exibir resultados provisórios da avaliação e monitorar a validade estatística do processo. 
    
- **Ciclos de treinamento e acompanhamento**
    
  - **Marca**: as investigações de dados (visualização) aprende critérios de relevância específicos para cada problema com base na revisão iterativa do especialista e na marcação de arquivos individuais.
    
  - **Track**: calcular e exibir resultados provisórios do treinamento de relevância e monitorar a validade estatística do processo. 
    
- **Cálculo de lote**: os critérios de relevância acumulados e aprendidos são aplicados a todo o conjunto de arquivos e uma pontuação de relevância é gerada para cada arquivo.
    
- ****@ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ Os resultados da análise aplicada ao caso inteiro são exibidos após o cálculo de lote, e os dados usados para fazer decisões de revisão
    
- **Test**: os resultados podem ser testados para verificar a validade e a eficácia do processamento de investigações de dados (visualização).

- **Pesquisa**: depois que o fluxo de trabalho de relevância estiver concluído, você poderá usar a saída como ler percentil de um documento para o seu problema ao executar uma consulta dentro do seu conjunto de trabalho.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Diretrizes para treinamento e análise de relevância

Veja a seguir uma visão geral das diretrizes de treinamento e análise de relevância:
  
- **Erros e inconsistências**: se forem feitos erros de marcação durante o treinamento, retorne a amostras de arquivos anteriores para corrigi-los. Se houver muitos erros para corrigir ou se houver uma nova perspectiva do caso ou problema, os critérios de relevância deverão ser redefinidos pelo administrador e o treinamento de relevância reiniciado.
    
- **Marcação e treinamento**: 
    
  - Os arquivos devem ser marcados com base apenas no conteúdo. Não considere metadados, como os responsáveis, a data ou o caminho do arquivo. 
    
  - Não considere indicações de intervalo de datas no texto ao marcar arquivos.
    
  - Não considere imagens gráficas incorporadas ao marcar arquivos.
     
  - Ignorar o texto aplicado à relevância será removido no conteúdo do arquivo exibido no modo de exibição de texto de relevância. Se os valores para ignorar texto tiverem sido definidos após o treinamento de relevância já ter sido iniciado, o novo texto ignorado será aplicado a arquivos de exemplo criados a partir do ponto em que foi definido. O recurso Ignorar texto deve ser usado com cautela, pois seu uso pode reduzir o desempenho da análise de arquivos
    
  - Use a opção **ignorar marcação** apenas quando necessário. As investigações de dados (prévia) não são treinadas com base em arquivos ignorados. Em avaliação, se for difícil dizer se um arquivo é relevante, é melhor marcar como relevante (R) ou não relevante (NR) sempre que possível, em vez de selecionar **ignorar**. Quando a investigação de dados (prévia) avalia o treinamento, ela pode ser vista como esses tipos de arquivos foram processados.
    
  - Até mesmo arquivos com uma quantidade muito pequena de texto extraído deve ser marcado em treinamento como R/NR, e não como "ignorar", quando possível. 
    
  - A marcação pode impactar o classificador, desde que o arquivo seja legível e possa ser marcado como R/NR.
    
  - O número de sequência de arquivo na lista de arquivos de amostra exibidos na guia **marca** permite que o usuário retorne à ordem de exibição original dos arquivos. 
    
  - Você pode retornar a qualquer amostra e alterar a marcação dos arquivos de avaliação e de conjunto de treinamento. As alterações serão aplicadas durante a criação do próximo exemplo.
    
  - Os arquivos do Excel digitalizados no formato PDF devem ser tratados da mesma forma que os arquivos nativos do Excel ao marcar arquivos.
    
  - Quando estiver em dúvida sobre a marcação de relevância de um arquivo, consulte um especialista. Marcações incorretas durante o treinamento de relevância podem causar perda de tempo mais tarde no processo e também podem ter um impacto negativo sobre a qualidade dos resultados gerais.
    
  - As palavras-chave que foram definidas nas listas de palavras-chave serão exibidas em cores para ajudar o usuário a identificar arquivos relevantes durante a marcação.
    
- **Cálculo em lotes**: os arquivos que foram marcados como R/NR pelo especialista receberão uma pontuação de 0 ou 100. Isso se aplica à marcação feita antes do cálculo em lote. Se o especialista tiver alternado o problema para ficar inativo após o cálculo de lote e a marcação contínua desse problema, as pontuações recentemente marcadas não serão 100/0, mas sim a pontuação original.
    
- **Modo de problemas e de amostragem**: problemas geralmente estão desativados quando o trabalho deles é concluído (o treinamento de relevância é estabilizado e o cálculo do lote foi realizado), quando os problemas são cancelados ou quando outro usuário está trabalhando com os problemas.
    
## <a name="steps-in-relevance-training"></a>Etapas no treinamento de relevância

Na guia **controle \> de relevância** , as investigações de dados fornecem recomendações sobre como proceder no processamento, seguindo as próximas etapas. As implicações são descritas abaixo quando cada uma das etapas a seguir é recomendada no processo de treinamento de relevância. 
  
- Marcação/continuação de marcação: marcação de arquivo e classificação de relevância executada por um especialista para cada arquivo e problema em um exemplo.
    
  - Implicação: um exemplo existente precisa ser marcado.
    
- Avaliação/continuação da avaliação: habilita a validação antecipada da relevância do problema de caso e uma exibição preliminar da relevância da população de arquivo importada para o caso atual.
    
  - Implicação: mais avaliação obrigatória ou recomendada.
    
- Treinamento de treinamento/continuação: processo durante o qual as investigações de dados aprendem do especialista, que está marcando os exemplos de arquivos e obtém a capacidade de identificar critérios de relevância pertinentes a cada problema dentro do contexto de cada caso.
    
  - Implicação: o problema precisa de mais treinamento; o próximo exemplo deve ser criado e marcado. 
    
- Cálculo em lote: o processo de relevância no qual as investigações de dados leva o conhecimento adquirido durante o estágio de treinamento e o aplica à população de arquivo inteiro. Todos os arquivos no grupo de arquivos pertinente são avaliados por relevância e recebem uma pontuação de relevância.
    
  - Implicação: o problema foi estabilizado e o cálculo de lote pode ser executado.
    
- Atualização: relevância indica quando um especialista revisa e marca uma amostra de arquivos selecionados a partir de uma carga de arquivos adicional durante um cenário de cargas sem interrupção.
    
  - Implicação: uma nova carga foi adicionada e a atualização é necessária para continuar trabalhando.
    
- Inconsistências de marca: o processo identifica, por meio de um algoritmo de investigações de dados, inconsistências no processo de marcação de arquivos que podem afetar negativamente a análise.
    
  - Implicação: o exemplo a seguir inclui arquivos que foram marcados em exemplos anteriores e sua marcação deve ser refeita.
    
- Classificador de atualização: permite que o usuário Aplique alterações de marcação ou propagação.
    
  - Implicação: as alterações de marcação e propagação podem ser aplicadas sem a necessidade de executar outra amostra de relevância manualmente.
    
- Em retenção: o processo de treinamento de relevância foi concluído.
    
  - Implicação: nenhum treinamento de relevância é necessário neste ponto.
    
Embora as investigações de dados orientam você durante o processo, com as próximas etapas recomendadas em estágios diferentes, também permite navegar entre guias e páginas e fazer escolhas para lidar com situações que possam ser pertinentes a seu caso, problema ou processo de revisão de documento. 
  
É possível aceitar ou substituir as investigações de dados as opções de processamento da próxima etapa. Se você deseja executar uma etapa diferente da próxima etapa recomendada, clique na **próxima etapa** listada na exibição de problema expandida na caixa de diálogo, clique no botão **Modificar** ao lado da próxima etapa e selecione outra opção de próxima etapa. 
  
> [!NOTE]
> Algumas opções podem permanecer desabilitadas após a desbloqueio, pois elas não são suportadas para uso nesse ponto no processo. 
  
## <a name="more-information"></a>Mais informações

[Noções básicas sobre avaliação em relevância](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Marcação e avaliação](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Treinamento de marcação e relevância](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análise de relevância de rastreamento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidindo com base nos resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testando análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md)

[Consultar os dados em evidência](evidence-query.md)
