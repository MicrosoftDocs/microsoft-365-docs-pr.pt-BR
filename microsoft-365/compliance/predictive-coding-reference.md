---
title: Referência de codificação preditiva
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: ''
ms.openlocfilehash: ad9bf2ba40ede2d76246c56bf94b90e0e96aeeff
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288270"
---
# <a name="predictive-coding-reference-preview"></a>Referência de codificação preditiva (visualização)

Este artigo descreve os principais conceitos e métricas da ferramenta de codificação preditiva Advanced eDiscovery. As seções no artigo são listadas em ordem alfabética.

## <a name="confidence-level"></a>Nível de confiança

O nível de confiança é uma configuração avançada quando você cria um modelo de codificação preditivo. Ele define que as métricas de desempenho do modelo (por exemplo, riqueza, precisão e recall) estão dentro de um intervalo especificado (que determina a margem de erro definida para o modelo) que representa os valores verdadeiros das pontuações de previsão que o modelo atribui aos itens no conjunto de revisão. Os valores para o nível de confiança e a margem de erro também ajudam a determinar quantos itens estão incluídos no conjunto de controles. O valor padrão para o nível de confiança é 0,95 ou 95%.

## <a name="control-set"></a>Conjunto de controles

Um conjunto de controles é usado durante o processo de treinamento de um modelo de codificação preditivo. O conjunto de controles é avaliar as pontuações de previsão que o modelo atribui aos itens com a rotulagem que você executa durante as rodadas de treinamento. O tamanho do conjunto de controles baseia-se no número de itens no conjunto de revisão e no nível de confiança e margem de valores de erro definidos ao criar o modelo. Os itens no conjunto de controle nunca mudam e não são identificáveis para os usuários. O número total de itens no conjunto de controles é exibido na página de sobrevoo para uma rodada de treinamento.

## <a name="control-set-confusion-matrix"></a>Matriz de confusão do conjunto de controle

Depois de concluir uma rodada de treinamento, o modelo atribui uma pontuação de previsão aos 10 itens no conjunto de controle que você rotulou durante a rodada de treinamento. O modelo compara a pontuação de previsão desses 10 itens com o rótulo real atribuído ao item durante a rodada de treinamento. Com base nessa comparação, o modelo identifica as seguintes classificações para avaliar o desempenho de previsão do modelo:

<br>

****

|Rótulo|Modelo prevê que item é relevante|Modelo prevê item não é relevante|
|---|---|---|
|**Item de rótulos do revistor como relevante**|Verdadeiro positivo|Falso positivo|
|**Item rótulos do revistor como não relevante**|Falso negativo|Verdadeiro negativo|
|

Com base nessas comparações, o modelo deriva valores para as métricas de pontuação F, precisão e recall e a margem de erro para cada uma delas. O número de cada um dos tipos de confusão da matriz é exibido na página de sobrevoo para uma rodada de treinamento.

## <a name="f-score"></a>Pontuação F

A pontuação F é uma média ponderada das pontuações das métricas de precisão e recall.  O intervalo de pontuações para essa métrica é **de 0** a **1**. Uma pontuação mais próxima **de 1** indica que o modelo detectará com mais precisão itens relevantes. A métrica de pontuação F é exibida no painel do modelo e na página sub-controle para cada rodada de treinamento.

## <a name="margin-of-error"></a>Margem de erro

A margem de erro é uma configuração avançada quando você cria um modo de codificação preditivo. Especifica o grau de erro nas métricas de desempenho (por exemplo, riqueza, precisão e recall) derivados da amostragem aleatória de itens no conjunto de controles. Uma margem de erro menor requer um conjunto de controle maior para garantir que as métricas de desempenho do modelo se enquadram em um intervalo menor. Os valores para a margem de erro e nível de confiança também ajudam a determinar quantos itens estão incluídos no conjunto de controles. O valor padrão para a margem de erro é 0,05 ou 5%.

## <a name="model-stability"></a>Estabilidade do modelo

A estabilidade do modelo indica a capacidade do modelo de prever com precisão se um documento em um conjunto de revisão é relevante ou não relevante. Quando um modelo é instável, pode ser necessário realizar mais rodadas de treinamento para incluir a estabilidade do modelo. Quando o modelo estiver estável, talvez não seja necessário realizar mais rodadas de treinamento. O painel do modelo indica o estado atual da estabilidade do modelo. Quando um modelo é estável, as métricas de desempenho atingiram um nível que corresponde às configurações do nível de confiança e da margem de erro.

## <a name="overturn-rate"></a>Taxa de overturn

A taxa de rebaixamento é a porcentagem de itens no conjunto de revisão onde a pontuação de previsão foi alterada entre as rodadas de treinamento. Um modelo é considerado estável quando a taxa de rebaixamento é inferior a 5%. A métrica de taxa de rebaixamento é exibida no painel do modelo e na página de sobrevoo para cada rodada de treinamento. A taxa de rebaixamento para a primeira rodada de treinamento é zero porque não há uma pontuação de previsão anterior a ser anulada.

## <a name="precision"></a>Precisão

A métrica de precisão mede a proporção de itens que são realmente relevantes entre os itens previstos pelo modelo. Isso significa que os itens no conjunto de controles onde o rótulo é relevante pelo revistor e previstos como relevantes pelo modelo. O intervalo de pontuações para essa métrica é **de 0** a **1**. Uma pontuação mais próxima **de 1** indica que o modelo identificará menos itens não relevantes. A métrica de precisão é exibida no painel do modelo e na página de sobrevoo para cada rodada de treinamento.

## <a name="prediction-score"></a>Pontuação de previsão

Esta é a pontuação que um modelo atribui a cada documento em um conjunto de revisão. A pontuação se baseia na relevância do documento em comparação com o aprendizado do modelo nas rodadas de treinamento. Em geral, itens com pontuações de previsão entre **0** e **0,5** são considerados não relevantes e itens com pontuações de previsão entre **0,5** e **1** são considerados relevantes. A pontuação de previsão está contida em um campo de metadados de documento. Você pode usar um filtro de previsão para exibir os itens em um conjunto de revisão que se enquadram em um intervalo de previsão especificado.

## <a name="recall"></a>Recall

A métrica de recall mede a proporção de itens que o modelo previu eram relevantes entre os itens que são realmente relevantes. Isso significa que os itens no conjunto de controles que o modelo previu eram relevantes também foram rotulados como relevantes pelo revistor. O intervalo de pontuações para essa métrica é **de 0** a **1**. Uma pontuação mais próxima **de 1** indica que o modelo identificará uma parte maior de itens relevantes. A métrica de recall é exibida no painel do modelo e na página de sobrevoo para cada rodada de treinamento.

## <a name="review-set"></a>Conjuntos de revisão

Um conjunto de revisão fornece o escopo de um modelo de codificação preditivo. Quando você cria um novo modelo para o conjunto de revisão, os itens para o conjunto de controles e conjuntos de treinamento são selecionados no conjunto de revisão. Quando o modelo atribui pontuações de previsão, ele atribui a essas pontuações os itens na revisão. Você precisa adicionar todos os itens ao conjunto de revisão antes de criar um modelo de codificação preditivo. Se você adicionar itens depois de criar um modelo, esses itens não receberão uma pontuação de previsão.

## <a name="richness"></a>Richness

A métrica de riqueza mede a porcentagem de itens do conjunto de revisão que o modelo prevê como relevante. O intervalo de pontuações para essa métrica é **de 0** a **1**. A métrica de riqueza é exibida no painel do modelo.

## <a name="sampled-items"></a>Itens amostrados

O termo exemplo de *itens* é uma referência a exemplo aleatório de itens em um conjunto de revisão (que contêm texto) que são selecionados e associados ao conjunto de controle ao criar um modelo de codificação preditivo. Um exemplo aleatório de itens também é selecionado para cada rodada de treinamento. Os itens selecionados para o conjunto de controle de um modelo nunca são incluídos em um conjunto de treinamento para esse mesmo modelo. O inverso também é verdadeiro: os itens do conjunto de treinamento nunca são incluídos no conjunto de controles.

## <a name="training-set"></a>Conjunto de treinamento

O modelo seleciona aleatoriamente itens do conjunto de revisão e os adiciona a um conjunto de treinamento. Durante uma rodada de treinamento, os itens do conjunto de treinamento (além de itens do conjunto de controle) são apresentados a você para que você possa rotular cada um deles como "relevante" ou "não relevante". Esse processo de rotulagem ou "treinamento" ajuda o modelo a aprender a prever quais itens na revisão são relevantes ou não relevantes. Sempre que você executa uma rodada de treinamento, o modelo seleciona mais itens da revisão e os adiciona ao conjunto de treinamento para essa rodada de treinamento. Os itens do conjunto de controle nunca são selecionados para um conjunto de treinamento.
