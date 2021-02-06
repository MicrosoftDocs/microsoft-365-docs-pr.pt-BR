---
title: Módulo Desaconsuência da Relevância na Descoberta Avançada
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
ms.collection: M365-security-compliance
description: O módulo Relevância na Descoberta Avançada será retirado em 10 de março de 2021. Este artigo explica o que fazer antes que a Relevância seja retirada. Especificamente, concluindo todos os modelos não concluídos executando o cálculo em lotes para que você possa manter os metadados do modelo.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122521"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Baixa do módulo Relevância na Descoberta Avançada

Em 10 de março de 2021, estamos retirando o módulo Relevância na Descoberta Avançada. Essa baixa significa que as organizações não terão mais acesso ao módulo Relevância (gerenciando a relevância do conjunto de revisão em um caso de Descoberta Eletrônico Avançada) ou poderão acessar quaisquer modelos de Relevância  >   existentes. O módulo de Relevância atual que está sendo retirado será substituído por uma nova solução de codificação preditiva no 2º trimestre de 2021. Essa nova funcionalidade permitirá que as organizações criem seus próprios modelos de codificação preditiva em um fluxo de trabalho mais fácil e intuitivo.

Para se preparar para essa futura desaportação, recomendamos que as organizações que usam o módulo de Relevância exportem a saída do modelo antes da data de reforma, executando um cálculo em lotes para todos os modelos existentes. Todas as pontuações de Relevância do seu modelo serão armazenadas permanentemente no conjunto de revisão correspondente e acessíveis quando os documentos são exportados. As pontuações de relevância também são mantidas como metadados no arquivo de carregamento. Além disso, você ainda poderá filtrar o conteúdo no conjunto de revisão com base na pontuação de relevância e ter acesso a todos os metadados produzidos por seus modelos de Relevância.

## <a name="complete-unfinished-models"></a>Concluir modelos não concluídos

Para qualquer modelo de Relevância não concluído, conclua a avaliação, o treinamento e o cálculo em lotes para que você possa aplicar o modelo aos documentos em um conjunto de revisão. A conclusão do cálculo em lotes preservará as informações após a data de conclusão do módulo relevância.

Aqui estão as etapas para concluir todos os modelos não concluídos:

1. Treine seu modelo até que ele esteja estabilizado e pronto para o cálculo em lotes. Consulte [Marcação e treinamento de relevância.](tagging-and-relevance-training-in-advanced-ediscovery.md)

   A captura de tela a seguir mostra um módulo que está pronto para um cálculo em lotes. Observe que a Avaliação e Treinamento está concluída, e a próxima etapa é executar o cálculo em lotes.

   ![Captura de tela do modelo pronto para cálculo em lotes](../media/ReadyForBatchCalculation.png)

2. Execute o cálculo em lotes. Consulte [Executando o cálculo em lotes.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)

3. Verifique se o cálculo do lote foi bem-sucedido. Consulte [Resultados de cálculo em lotes.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)

Para ajuda com a conclusão de modelos de relevância não concluídos, entre em contato com o Suporte da Microsoft.
