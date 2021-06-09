---
title: Criar um modelo de codificação preditiva em Advanced eDiscovery
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
description: Saiba como criar um modelo de codificação preditiva em Advanced eDiscovery. Esta é a primeira etapa para usar os recursos de aprendizado de máquina no Advanced eDiscovery para ajudá-lo a identificar conteúdo relevante e não relevante em um conjunto de revisão.
ms.openlocfilehash: 7724062848d8d757fbfd3a7870853d6f2c409d84
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822473"
---
# <a name="create-a-predictive-coding-model-preview"></a>Criar um modelo de codificação preditiva (visualização)

A primeira etapa do uso dos recursos de aprendizado de máquina da codificação preditiva no Advanced eDiscovery é criar um modelo de codificação preditivo. Depois de criar um modelo, você pode treiná-lo para identificar o conteúdo relevante e não relevante em um conjunto de revisão.

Para revisar o fluxo de trabalho de codificação preditivo, [consulte Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-create-a-model"></a>Antes de criar um modelo

- Deve haver no mínimo 2.000 itens em um conjunto de revisão para criar um modelo de codificação preditivo.

- Certifique-se de comprometer todas as coleções ao conjunto de revisão antes de criar um modelo. Os itens adicionados a um conjunto de revisão após a criação do modelo não serão processados e atribuídos a uma pontuação de previsão gerada pelo modelo.

- Qualquer item no conjunto de revisão que não contenha texto não será processado pelo modelo ou atribuído a uma pontuação de previsão. Os itens com texto serão incluídos no conjunto de controles ou em um conjunto de treinamento.

## <a name="create-a-model"></a>Criar um modelo

1. No centro Microsoft 365 de conformidade, abra uma caixa Advanced eDiscovery e selecione a guia **Revisar conjuntos.**

2. Abra um conjunto de revisão e clique em **Análise**  >  **Gerenciar codificação preditiva (visualização)**.

   ![Clique no menu suspenso Analisar no conjunto de revisão para ir para a página codificação preditiva](..\media\ManagePredictiveCoding.png)

3. Na página **Modelos de codificação preditiva (visualização),** clique **em Novo modelo**.

4. Na página de sobrevoo, digite um nome para o modelo e uma descrição opcional.

5. Opcionalmente, você pode configurar configurações avançadas (clicando em **Opções** avançadas na página de sobrevoo) relacionadas ao nível de confiança e à margem de erro. Essas configurações afetam o número de itens incluídos no conjunto de controles. O *conjunto de controles* é usado durante o processo de treinamento para avaliar as pontuações de previsão que o modelo atribui aos itens com a rotulagem que você executa durante as rodadas de treinamento. Se sua organização tiver diretrizes sobre o nível de confiança e a margem de erro para revisão de documentos, especifique-as nas caixas apropriadas. Caso contrário, use as configurações padrão.

6. Clique **em Salvar** para criar o modelo.

   O sistema levará alguns minutos para preparar seu modelo. Depois que estiver pronto, você poderá executar a primeira rodada de treinamento.

## <a name="what-happens-after-you-create-a-model"></a>O que acontece depois de criar um modelo

Depois de criar um modelo, as seguintes coisas ocorrem em segundo plano durante a criação e preparação do modelo:

- O sistema calcula o número de itens para o conjunto de controles. Esse tamanho se baseia no número de itens no conjunto de revisão e nas configurações para o nível de confiança e a margem de erro. Os itens para o conjunto de controles são selecionados aleatoriamente e designados como itens de conjunto de controle. O sistema inclui 10 itens do conjunto de controles na primeira rodada de treinamento.

- O sistema seleciona aleatoriamente 40 itens do conjunto de revisão a serem incluídos no conjunto de treinamento para a primeira rodada de treinamento. Portanto, a primeira rodada de treinamento inclui 50 itens para rotulagem: 40 itens do conjunto de treinamento e 10 itens do conjunto de controle.

## <a name="next-steps"></a>Próximas etapas

Depois de criar um modelo para um conjunto de revisão, a próxima etapa é realizar rodadas de treinamento para "ensinar" o modelo a identificar conteúdo relevante para sua investigação. Para obter mais informações, [consulte Train a predictive coding model](predictive-coding-train-model.md).
