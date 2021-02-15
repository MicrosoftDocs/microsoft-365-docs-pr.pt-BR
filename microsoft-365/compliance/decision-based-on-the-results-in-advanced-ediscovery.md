---
title: Decisão com base nos resultados da Descoberta Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Saiba como a guia Decidir na Descoberta eDiscovery Avançada fornece dados que podem ajudá-lo a determinar o tamanho correto do conjunto de revisão de arquivos de ocorrência.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769146"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Decisões baseadas em resultados de relevância na Descoberta Descoberta Avançada
  
No módulo Relevância na Descoberta eDiscovery Avançada, a guia Decidir fornece informações adicionais para exibir e usar estatísticas de suporte à decisão para determinar o tamanho do conjunto de revisão de arquivos de caso.
  
## <a name="using-the-decide-tab"></a>Usando a guia Decidir

![Decisão de Relevância](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Essa guia inclui os seguintes componentes:
  
- **Problema:** a partir daqui, você pode selecionar o problema de interesse na lista.

- **Taxa de reavaliação-recall:** comparações da revisão de Descobertas De acordo com as pontuações de relevância. O ponto de corte no gráfico representa a porcentagem de arquivos a analisar, mapeado para uma pontuação de Relevância. Isso é usado na fase teste de relevância e como um limite de exportação para o descarte. O ponto de corte padrão, para o número de arquivos a analisar, está no ponto em que o equilíbrio entre Recall e Precision é ideal. O ponto de corte real deve ser determinado pelo usuário, dependendo dos objetivos, da troca de custo (%review) e do risco (%recall). Usando o controle deslizante, você pode ajustar o ponto de corte e ver o efeito no gráfico e nos parâmetros, ao ajustar a porcentagem de arquivos relevantes a serem recuperados e antes de validar uma decisão.

- **Parâmetros:** Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case. As definições para esses parâmetros são as seguinte:

  - **Revisão:** Porcentagem de arquivos a analisar com base nesse corte.

  - **Recall:** porcentagem de arquivos relevantes no conjunto de revisão.

  - **Próximo relevante:** custo para revisar e identificar outro arquivo relevante que não está atualmente no conjunto de revisão.

  - **Custo total**: custo para analisar essa porcentagem dos arquivos de ocorrência. As configurações de parâmetro de custo podem ser definidas pelo Gerenciador de ocorrências.

  - **Distribuição por pontuação de relevância:** os arquivos na exibição cinza escuro à esquerda estão abaixo da pontuação de recorte. Uma dica de ferramenta exibe a pontuação de relevância e a porcentagem relacionada de arquivos no conjunto de arquivos de revisão em relação ao total de arquivos.

O painel **Detalhes** expandido exibe mais detalhes. Arquivos em figuras de coleção não incluem arquivos vazios ou nebulous. Os arquivos de família representam arquivos que não são carregados em Relevância, mas ainda contabilizados como parte da família.
