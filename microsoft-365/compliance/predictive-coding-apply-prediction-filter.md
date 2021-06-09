---
title: Aplicar o filtro de pontuação de previsão a itens em um conjunto de revisão
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
description: Use um filtro de pontuação de previsão para exibir itens que um modelo de codificação preditivo como previsto como relevante ou não relevante.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822462"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>Aplicar um filtro de pontuação de previsão a um conjunto de revisão (visualização)

Depois de criar um modelo de codificação preditiva no Advanced eDiscovery e treiná-lo até o ponto em que ele está estável, você pode aplicar o filtro de pontuação de previsão para exibir itens de conjunto de revisão que o modelo determinou são relevantes (ou não relevantes). Quando você cria um modelo, um filtro de pontuação de previsão correspondente também é criado. Você pode usar esse filtro para exibir itens atribuídos a uma pontuação de previsão dentro de um intervalo especificado. Em geral, as pontuações de previsão entre 0 e **0,5** são atribuídas a itens que o modelo previu não são relevantes.  Itens atribuídos a pontuações de previsão entre **.5** e **1.0** são itens que o modelo previu são relevantes.

Aqui estão duas maneiras de usar o filtro de pontuação de previsão:

- Priorizar a revisão de itens em um conjunto de revisão que o modelo previu são relevantes.

- Os itens do conjunto de revisão que o modelo previu não são relevantes. Alternativa, você pode usar o filtro de pontuação de previsão para des priorizar a revisão de itens não relevantes.

## <a name="before-you-apply-a-prediction-score-filter"></a>Antes de aplicar um filtro de pontuação de previsão

- Crie um modelo de codificação preditiva para que um filtro de pontuação de previsão correspondente seja criado.

- Você pode aplicar um filtro de pontuação de previsão após qualquer uma das rodadas de treinamento. Mas você pode esperar depois de executar várias rodadas ou até que o modelo seja estável antes de usar o filtro de pontuação de previsão.

## <a name="apply-a-prediction-score-filter"></a>Aplicar um filtro de pontuação de previsão

1. No centro Microsoft 365 de conformidade, abra o caso Advanced eDiscovery, selecione a guia Revisar **conjuntos** e abra o conjunto de revisão.

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

  > [!TIP]
  > Para exibir a pontuação real da previsão atribuir a um documento, você pode clicar na guia **Metadados** no painel de leitura. As pontuações de previsão de todos os modelos no conjunto de revisão são exibidas na propriedade de metadados **RelevanceScores.**

## <a name="more-information"></a>Mais informações

- Para obter mais informações sobre como usar filtros, consulte [Query and filter content in a review set](review-set-search.md).
