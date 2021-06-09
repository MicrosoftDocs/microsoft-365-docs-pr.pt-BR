---
title: Codificação preditiva em Advanced eDiscovery - Início rápido
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
description: Saiba como começar a usar o módulo de codificação preditiva Advanced eDiscovery. Este artigo orienta você sobre o processo de ponta a ponta do uso da codificação preditiva para identificar conteúdo em um conjunto de revisão mais relevante para sua investigação.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822470"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>Início rápido: codificação preditiva no Advanced eDiscovery (visualização)

Este artigo apresenta um início rápido para o uso da codificação preditiva Advanced eDiscovery. O módulo de codificação preditiva no Advanced eDiscovery usa os recursos inteligentes de aprendizado de máquina no Advanced eDiscovery para ajudá-lo a reduzir a quantidade de conteúdo a ser revisado. A codificação preditiva ajuda você a reduzir e a reduzir grandes volumes de conteúdo de caso para um conjunto relevante de itens que você pode priorizar para revisão. Isso é feito criando e treinando seus próprios modelos de codificação preditivos que ajudam você a priorizar a revisão dos itens mais relevantes em um conjunto de revisão.

Aqui está uma visão geral rápida do processo de codificação preditiva:

![Processo de início rápido para codificação de previsão](..\media\PredictiveCodingQuickStartProcess.png)

Para começar, crie um modelo, rotule até 50 itens como relevantes ou não relevantes. Em seguida, o sistema usa esse treinamento para aplicar pontuações de previsão a cada item no conjunto de revisão. Isso permite filtrar itens com base na pontuação de previsão, o que permite que você revise primeiro os itens mais relevantes (ou não relevantes). Se você quiser treinar modelos com maiores precisões e taxas de recall, poderá continuar rotulando itens em rodadas de treinamento subsequentes até que o modelo se estabiliza. Depois que o modelo for estabilizado, você poderá aplicar o filtro de previsão final para priorizar itens para revisão.

Para uma visão geral detalhada da codificação preditiva, consulte [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).

## <a name="step-1-create-a-new-predictive-coding-model"></a>Etapa 1: Criar um novo modelo de codificação preditiva

A primeira etapa é criar um novo modelo de codificação preditiva no conjunto de revisão

1. No centro Microsoft 365 de conformidade, abra uma caixa Advanced eDiscovery e selecione a guia **Revisar conjuntos.**

2. Abra um conjunto de revisão e clique em **Análise**  >  **Gerenciar codificação preditiva (visualização)**.

   ![Clique no menu suspenso Analisar no conjunto de revisão para ir para a página codificação preditiva](..\media\ManagePredictiveCoding.png)

3. Na página **Modelos de codificação preditiva (visualização),** clique **em Novo modelo**.

4. Na página de sobrevoo, digite um nome para o modelo e uma descrição opcional.

5. Clique **em Salvar** para criar o modelo.

   O sistema levará alguns minutos para preparar seu modelo. Depois que estiver pronto, você poderá executar a primeira rodada de treinamento.

Para obter instruções mais detalhadas, consulte [Create a predictive coding model](predictive-coding-create-model.md).

## <a name="step-2-perform-the-first-training-round"></a>Etapa 2: Executar a primeira rodada de treinamento

Depois de criar o modelo, a próxima etapa é concluir a primeira rodada de treinamento rotulando itens como relevantes ou não relevantes.

1. Abra o conjunto de revisão e clique em **Análise**  >  **Gerenciar codificação preditiva (visualização)**.

2. Na página **Modelos de codificação preditiva (visualização),** selecione o modelo que você deseja treinar.

3. Na guia **Visão** geral, em **Round 1**, clique **em Iniciar próxima rodada de treinamento.**

   A **guia** Treinamento é exibida e contém 50 itens para você rotular.

4. Revise cada documento e selecione o botão **Relevante** ou **Não relevante** na parte inferior do painel de leitura para rotulá-lo.

   ![Rotular cada documento como relevante ou não relevante](..\media\TrainModel1.png)

5. Depois de rotular todos os 50 itens, clique em **Concluir**.

    O sistema levará alguns minutos para "aprender" com a rotulagem e atualizar o modelo. Quando esse processo é concluído, um status de **Ready** é exibido para o modelo na página Modelos de codificação preditiva **(visualização).**

Para obter instruções mais detalhadas, consulte [Train a predictive coding model](predictive-coding-train-model.md).

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>Etapa 3: Aplicar o filtro de pontuação de previsão a itens no conjunto de revisão

Depois de executar na locação de uma rodada de treinamento, você pode aplicar o filtro de pontuação de previsão aos itens no conjunto de revisão. Isso permite que você revise os itens que o modelo previu como relevantes ou não relevantes.   

1. Abra o conjunto de revisão.

   ![Clique em Filtros para exibir a página de sobrevoo Filtros](..\media\PredictionScoreFilter0.png)

   Os filtros padrão pré-carregados são exibidos na parte superior da página de conjunto de revisão. Você pode deixá-los definidos como **Qualquer**.

2. Clique **em Filtros** para exibir a página de sobrevoo **Filtros.**

3. Expanda **a seção Análise & codificação preditiva** para exibir um conjunto de filtros.

      ![Filtro de pontuação de previsão na seção Análise & codificação preditiva](..\media\PredictionScoreFilter1.png)

   A convenção de nomenisagem para filtros de pontuação de previsão é **Pontuação de previsão (nome do modelo)**. Por exemplo, o nome do filtro de pontuação de previsão para um modelo chamado **Modelo A** é **Pontuação de Previsão (Modelo A)**.

4. Selecione o filtro de pontuação de previsão que você deseja usar e clique em **Feito**.

5. Na página conjunto de revisão, clique no menu suspenso para o filtro de pontuação de previsão e digite valores mínimos e máximos para o intervalo de pontuação de previsão. Por exemplo, a captura de tela a seguir mostra um intervalo de pontuação de previsão entre **.5** e **1,0**.

   ![Valores mínimos e máximos para o filtro de pontuação de previsão](..\media\PredictionScoreFilter2.png)

6. Clique fora do filtro para aplicar automaticamente o filtro ao conjunto de revisão.

  Uma lista de documentos com uma pontuação de previsão dentro do intervalo especificado é exibida na página conjunto de revisão.

Para obter instruções mais detalhadas, consulte Aplicar um filtro [de previsão a um conjunto de revisão](predictive-coding-apply-prediction-filter.md).

## <a name="step-4-perform-more-training-rounds"></a>Etapa 4: Executar mais rodadas de treinamento

Mais do que provável, você terá que executar mais rodadas de treinamento para treinar o módulo para prever melhor os itens relevantes e não relevantes no conjunto de revisão. Em geral, você treinará o modelo vezes suficientes até que ele se estabiliza o suficiente para atender aos seus requisitos.

Para obter mais informações, consulte [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>Etapa 5: aplicar o filtro de pontuação de previsão final para priorizar a revisão

Repita as instruções na Etapa 3 para aplicar a pontuação final de previsão ao conjunto de revisão para priorizar a revisão de itens relevantes e não relevantes depois de concluir todas as rodadas de treinamento e estabilizar o modelo.
