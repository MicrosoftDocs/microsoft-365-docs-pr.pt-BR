---
title: Treine um modelo de codificação preditiva Advanced eDiscovery
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
ms.openlocfilehash: 84ec1ad42f2cec2487debe7160a3f24e09bdd830
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288186"
---
# <a name="train-a-predictive-coding-model-preview"></a>Treinar um modelo de codificação preditiva (visualização)

Depois de criar um modelo de codificação preditiva no Advanced eDiscovery, a próxima etapa é executar a primeira rodada de treinamento para treinar o modelo sobre o conteúdo relevante e não relevante no conjunto de revisão. Depois de concluir a primeira rodada de treinamento, você pode realizar rodadas de treinamento subsequentes para melhorar a capacidade do modelo de prever conteúdo relevante e não relevante.

Para revisar o fluxo de trabalho de codificação preditivo, [consulte Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-train-a-model"></a>Antes de treinar um modelo

- Durante uma rodada de treinamento, rotule itens como **Relevantes** ou **Não relevantes** com base na relevância do conteúdo no documento. Não basee sua decisão nos valores nos campos de metadados. Por exemplo, para mensagens de email ou Teams conversas, não basee sua decisão de rotulagem nos participantes da mensagem.

## <a name="train-a-model-for-the-first-time"></a>Treinar um modelo pela primeira vez

1. Na Centro de conformidade do Microsoft 365, abra uma caixa Advanced eDiscovery e selecione a guia **Revisar conjuntos.**

2. Abra um conjunto de revisão e clique em **Análise**  >  **Gerenciar codificação preditiva (visualização)**.

3. Na página **Modelos de codificação preditiva (visualização),** selecione o modelo que você deseja treinar.

4. Na guia **Visão** geral, em **Round 1**, clique **em Iniciar próxima rodada de treinamento.**

   A **guia** Treinamento é exibida e contém 50 itens para você rotular.

5. Revise cada documento e selecione o botão **Relevante** ou **Não relevante** na parte inferior do painel de leitura para rotulá-lo.

   ![Rotular cada documento como relevante ou não relevante](..\media\TrainModel1.png)

6. Depois de rotular todos os 50 itens, clique em **Concluir**.

    O sistema levará alguns minutos para "aprender" com a rotulagem e atualizar o modelo. Quando esse processo é concluído, um status de **Ready** é exibido para o modelo na página Modelos de codificação preditiva **(visualização).**

## <a name="perform-additional-training-rounds"></a>Executar rodadas de treinamento adicionais

Depois de executar a primeira rodada de treinamento, você pode executar rodadas de treinamento subsequentes seguindo as etapas da seção anterior. A única diferença é que o número da rodada de treinamento será atualizado na guia Visão geral **do** modelo. Por exemplo, depois de executar a primeira rodada de treinamento, você pode clicar em **Iniciar** a próxima rodada de treinamento para iniciar a segunda rodada de treinamento. E assim por diante.

Cada rodada de treinamento (as que estão em andamento e as que estão concluídas) é exibida na guia **Treinamento** para o modelo. Quando você seleciona uma rodada de treinamento, uma página de sobrevoo com informações e métricas para a rodada é exibida.

## <a name="what-happens-after-you-perform-a-training-round"></a>O que acontece após a realização de uma rodada de treinamento

Depois de executar a primeira rodada de treinamento, é iniciado um trabalho que faz as seguintes coisas:

- Com base na forma como você rotulou os 40 itens no conjunto de treinamento, o modelo aprende com sua rotulagem e se atualiza para se tornar mais preciso.

- Em seguida, o modelo processa cada item em todo o conjunto de revisão e atribui uma pontuação de previsão entre **0** (não relevante) e **1** (relevante).

- O modelo atribui uma pontuação de previsão aos 10 itens no conjunto de controle que você rotulou durante a rodada de treinamento. O modelo compara a pontuação de previsão desses 10 itens com o rótulo real atribuído ao item durante a rodada de treinamento. Com base nessa comparação, o modelo identifica a seguinte classificação (chamada de matriz de confusão do conjunto de controle *)* para avaliar o desempenho de previsão do modelo:

  <br>

  ****

  |Rótulo|Modelo prevê que item é relevante|Modelo prevê item não é relevante|
  |---|---|---|
  |**Item de rótulos do revistor como relevante**|Verdadeiro positivo|Falso positivo|
  |**Item rótulos do revistor como não relevante**|Falso negativo|Verdadeiro negativo|
  |

  Com base nessas comparações, o modelo deriva valores para as métricas de pontuação F, precisão e recall e a margem de erro para cada uma delas. As pontuações dessas métricas de desempenho do modelo são exibidas em uma página de sobrevoo para a rodada de treinamento. Para uma descrição dessas métricas, consulte [Referência de codificação preditiva](predictive-coding-reference.md).

- Por fim, o modelo determina os próximos 50 itens que serão usados para a próxima rodada de treinamento. Dessa vez, o modelo pode selecionar 20 itens do conjunto de controle e 30 novos itens do conjunto de revisão e designá-los como o conjunto de treinamento para a próxima rodada. A amostragem da próxima rodada de treinamento não é amostrada uniformemente. O modelo otimizará a seleção de amostragem de itens do conjunto de revisão para selecionar itens onde a previsão é ambígua, o que significa que a pontuação de previsão está no intervalo de 0,5. Esse processo é conhecido como *seleção parcial.*

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a>O que acontece após a realização de rodadas de treinamento subsequentes

Depois de executar as rodadas de treinamento subsequentes (após a primeira rodada de treinamento), o modelo faz as seguintes coisas:

- O modelo é atualizado com base nos rótulos que você aplicou ao conjunto de treinamento nessa rodada de treinamento.

- O sistema avalia a pontuação de previsão do modelo nos itens no conjunto de controle e verifica se a pontuação se alinha com a forma como você rotulou itens no conjunto de controles. A avaliação é realizada em todos os itens rotulados do conjunto de controle para todas as rodadas de treinamento. Os resultados dessa avaliação são incorporados no painel na guia **Visão** geral do modelo.

- O modelo atualizado reprocessa cada item no conjunto de revisão e atribui a cada item uma pontuação de previsão atualizada.

## <a name="next-steps"></a>Próximas etapas

Depois de executar a primeira rodada de treinamento, você pode executar mais rodadas de treinamento ou aplicar o filtro de pontuação de previsão do modelo ao conjunto de revisão para exibir os itens que o modelo previu como relevantes ou não relevantes. Para obter mais informações, [consulte Aplicar um filtro de pontuação de previsão a um conjunto de revisão](predictive-coding-apply-prediction-filter.md).
