---
title: Módulo de codificação preditiva para Advanced eDiscovery (visualização)
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
description: O novo módulo de codificação preditiva no Advanced eDiscovery usa aprendizado de máquina para analisar itens em um conjunto de revisão para prever quais itens são relevantes para seu caso ou investigação.
ms.openlocfilehash: 3c8fbd75bd585dd6ae722bf17deea906611d8df6
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822028"
---
# <a name="learn-about-predictive-coding-in-advanced-ediscovery-preview"></a>Saiba mais sobre codificação preditiva em Advanced eDiscovery (visualização)

O módulo de codificação preditiva no Advanced eDiscovery usa os recursos inteligentes de aprendizado de máquina para ajudá-lo a reduzir a quantidade de conteúdo a ser revisado. A codificação preditiva ajuda você a reduzir e a reduzir grandes volumes de conteúdo de caso para um conjunto relevante de itens que você pode priorizar para revisão. Isso é feito criando e treinando seus próprios modelos de codificação preditivos que ajudam você a priorizar a revisão dos itens mais relevantes em um conjunto de revisão.

O módulo de codificação preditiva foi projetado para simplificar a complexidade do gerenciamento de um modelo em um conjunto de revisão e fornecer uma abordagem iterativa para treinar seu modelo para que você possa começar mais rapidamente com os recursos de aprendizado de máquina no Advanced eDiscovery. Para começar, você pode criar um modelo, rotular até 50 itens como relevantes ou não relevantes. O sistema usa esse treinamento para aplicar pontuações de previsão a cada item no conjunto de revisão. Isso permite filtrar itens com base na pontuação de previsão, o que permite que você revise primeiro os itens mais relevantes (ou não relevantes). Se você quiser treinar modelos com maiores precisões e taxas de recall, poderá continuar rotulando itens em rodadas de treinamento subsequentes até que o modelo se estabiliza.  

## <a name="the-predictive-coding-workflow"></a>O fluxo de trabalho de codificação preditiva

Aqui está uma visão geral e uma descrição de cada etapa do fluxo de trabalho de codificação preditiva. Para obter uma descrição mais detalhada dos conceitos e terminologia do processo de codificação preditiva, consulte [Referência de codificação preditiva](predictive-coding-reference.md).

![Fluxo de trabalho de codificação preditiva](..\media\PredictiveCodingWorkflow.png)

1. **Crie um novo modelo de codificação preditiva no conjunto de revisão**. A primeira etapa é criar um novo modelo de codificação preditiva no conjunto de revisão. Você deve ter pelo menos 2.000 itens no conjunto de revisão para criar um modelo. Depois de criar um modelo, o sistema determinará o número de itens a ser usado como um *conjunto de controle*. O conjunto de controles é usado durante o processo de treinamento para avaliar as pontuações de previsão que o modelo atribui aos itens com a rotulagem que você executa durante as rodadas de treinamento. O tamanho do conjunto de controles baseia-se no número de itens no conjunto de revisão e no nível de confiança e margem de valores de erro definidos ao criar o modelo. Os itens no conjunto de controle nunca mudam e não são identificáveis para os usuários.

   Para obter mais informações, [consulte Create a predictive coding model](predictive-coding-create-model.md).

2. **Conclua a primeira rodada de treinamento rotulando itens como relevantes ou não relevantes.** A próxima etapa é treinar o modelo iniciando a primeira rodada de treinamento. Quando você inicia uma rodada de treinamento, o modelo seleciona aleatoriamente itens adicionais do conjunto de revisão, que é chamado de conjunto *de treinamento*. Esses itens (do conjunto de controles e do conjunto de treinamento) são apresentados a você para que você possa rotular cada um deles como "relevante" ou "não relevante". A relevância é baseada no conteúdo do item e não em nenhum dos metadados do documento. Depois de concluir o processo de rotulagem na rodada de treinamento, o modelo "aprenderá" com base em como você rotulou os itens no conjunto de treinamento. Com base nesse treinamento, o modelo processará os itens no conjunto de revisão e aplicará uma pontuação de previsão a cada um.

   Para obter mais informações, [consulte Train a predictive coding model](predictive-coding-train-model.md).

3. **Aplicar o filtro de pontuação de previsão a itens no conjunto de revisão**. Após a conclusão da etapa de treinamento anterior, a próxima etapa é aplicar o filtro de pontuação de previsão aos itens da revisão para exibir os itens que o modelo determinou que são "mais relevantes" (como alternativa, você também pode usar um filtro de previsão para exibir itens que "não são relevantes"). Ao aplicar o filtro de previsão, especifique um intervalo de pontuações de previsão para filtrar. O intervalo de pontuações de previsão está entre **0** e **1**, sendo **0** "não relevante" **e 1 relevante.** Em geral, itens com pontuações de previsão entre **0** e **0,5** são considerados "não relevantes" e itens com pontuações de previsão entre **0,5** e **1** são considerados relevantes.

   Para obter mais informações, [consulte Aplicar um filtro de previsão a um conjunto de revisão](predictive-coding-apply-prediction-filter.md).

4. **Execute mais rodadas de treinamento até que o modelo estabiliza**. Você pode realizar rodadas adicionais de treinamento se quiser criar um modelo com uma precisão maior de previsão e taxas de recall maiores. *A taxa de* recall mede a proporção de itens que o modelo previu eram relevantes entre os itens que são realmente relevantes (aqueles marcados como relevantes durante o treinamento). A pontuação da taxa de recall varia **de 0** a **1**. Uma pontuação mais próxima **de 1** indica que o modelo identificará itens mais relevantes. Em uma nova rodada de treinamento, você rotula itens adicionais em um novo conjunto de treinamento. Depois de concluir essa rodada de treinamento, o modelo é atualizado com base no novo aprendizado da sua rodada mais recente de rotular itens no conjunto de treinamento. O modelo processará os itens no conjunto de revisão novamente e aplicará novas pontuações de previsão. Você pode continuar realizando rodadas de treinamento até que seu modelo se estabiliza. Um modelo é considerado estabilizado quando a taxa de rotatividade após a última rodada de treinamento é inferior a 5%. *A taxa de* rotatividade é definida como porcentagem de itens em um conjunto de revisão onde a pontuação de previsão foi alterada entre as rodadas de treinamento. O painel de codificação preditiva exibe informações e estatísticas que ajudam você a avaliar a estabilidade de um modelo.

5. **Aplique o filtro de pontuação de previsão "final" para revisar itens definidos para priorizar a revisão**. Depois de concluir todas as rodadas de treinamento e estabilizar o modelo, a última etapa é aplicar a pontuação final de previsão ao conjunto de revisão para priorizar a revisão de itens relevantes e não relevantes. Essa é a mesma tarefa que você realizou na etapa 3, mas neste ponto o modelo é estável e você não planeja executar mais rodadas de treinamento.
