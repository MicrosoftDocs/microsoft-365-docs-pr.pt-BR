---
title: Módulo de codificação preditiva para Descoberta Avançada (visualização)
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
description: O novo módulo de codificação preditiva na Descoberta Eletrônica Avançada usa aprendizado de máquina para analisar documentos em um conjunto de revisão para prever quais documentos são relevantes para seu caso ou investigação.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382944"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>Módulo de codificação preditiva para Descoberta Avançada (visualização)

Usando o novo módulo de codificação preditiva na Descoberta Avançada, você pode criar e criar um modelo para priorizar a revisão de documentos começando com os documentos mais relevantes. Para começar, você pode criar um modelo, rotular até 50 documentos e filtrar documentos por pontuações de previsão de modelo para revisar documentos relevantes não relevantes.

Aqui está uma visão geral rápida do fluxo de trabalho:

1. Abra o módulo de codificação preditiva em um conjunto de revisão.

   ![Clique na lista suspenso Analisar em uma revisão para ir para o módulo de codificação preditiva](..\media\PredictiveCoding1.png)

2. Na página **Modelos de codificação preditiva,** clique em **Novo modelo** para criar um novo modelo de codificação preditiva.

   ![Criar um novo modelo](..\media\PredictiveCoding2.png)

3. Rotule pelo menos 50 documentos **como Relevantes** **ou Não Relevantes.** Essa rotulagem é usada para treinar o sistema.

   ![Rotular documentos como relevantes ou não relevantes para treinar o sistema](..\media\PredictiveCoding3.png)

4. Aplique o **filtro de pontuação** previsão para seu modelo ao conjunto de revisão. Para fazer isso:

   1. No conjunto de revisão, clique em **Filtros**.
   2. Na página **Sobrevoo Filtros,** expanda a  seção **Análise/ML** e selecione Caixa de seleção Pontuação de previsão para o modelo que você deseja aplicar.
   3. No filtro **de pontuação previsão,** especifique uma pontuação de previsão. O filtro exibirá os documentos no conjunto de revisão que corresponderem à pontuação de previsão.

      ![Especificar uma pontuação de previsão para filtrar documentos](..\media\PredictiveCoding4.png)

5. Monitore o desempenho, o status e a estabilidade do seu modelo.

   ![Monitorar o desempenho, o status e a estabilidade do seu modelo](..\media\PredictiveCoding5.png)
