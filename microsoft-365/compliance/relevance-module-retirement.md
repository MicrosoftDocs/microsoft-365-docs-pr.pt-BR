---
title: Módulo de ressalção de relevância no Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: O módulo De relevância no Advanced eDiscovery será retirado em 10 de março de 2021. Este artigo explica o que fazer antes que a Relevância seja retirada. Especificamente, concluindo quaisquer modelos não concluídos executando o cálculo em lotes para que você possa manter os metadados do modelo.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821992"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Ressalção do módulo De relevância no Advanced eDiscovery

Em 10 de março de 2021, estamos retirando o módulo De relevância no Advanced eDiscovery. Essa aposentadoria significa que as organizações não terão mais acesso ao módulo De relevância (indo para Gerenciar a relevância do conjunto de revisão em um caso Advanced eDiscovery) ou poderão acessar quaisquer modelos de  >   Relevância existentes. O módulo de Relevância atual que está sendo retirado será substituído por uma nova solução de codificação preditiva no 2º trimestre de 2021. Essa nova funcionalidade permitirá que as organizações criem seus próprios modelos de codificação preditivos em um fluxo de trabalho mais fácil e intuitivo.

Para se preparar para essa próxima aposentadoria, recomendamos que as organizações que usam o módulo De relevância exportem a saída do modelo antes da data de aposentadoria executando um cálculo em lotes para todos os modelos existentes. Todas as pontuações de Relevância do seu modelo serão armazenadas permanentemente no conjunto de revisão correspondente e acessíveis quando os documentos são exportados. As pontuações de relevância também são mantidas como metadados no arquivo de carga. Além disso, você ainda poderá filtrar conteúdo no conjunto de revisão com base na pontuação de relevância e ter acesso a todos os metadados produzidos por seus modelos de Relevância.

## <a name="complete-unfinished-models"></a>Concluir modelos não concluídos

Para quaisquer modelos de Relevância não concluídos, conclua a avaliação, o treinamento e o cálculo em lotes para que você possa aplicar o modelo aos documentos em um conjunto de revisão. Concluir o cálculo em lotes preservará as informações após a data de aposentadoria do módulo De relevância.

Aqui estão as etapas para concluir quaisquer modelos não concluídos:

1. Treine seu modelo até que ele esteja estabilizado e pronto para cálculo em lotes. Consulte [Treinamento de marcação e relevância.](tagging-and-relevance-training-in-advanced-ediscovery.md)

   A captura de tela a seguir mostra um módulo que está pronto para um cálculo batch. Observe que a Avaliação e Treinamento está concluída e a próxima etapa é executar o cálculo em lotes.

   ![Captura de tela do modelo pronto para cálculo em lotes](../media/ReadyForBatchCalculation.png)

2. Execute o cálculo batch. Consulte [Perform Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).

3. Verifique se o cálculo em lotes foi bem-sucedido. Consulte [Resultados de cálculo em lotes](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).

Para ajudar a concluir modelos de relevância não concluídos, entre em contato com o Suporte da Microsoft.
