---
title: Entender a Avaliação em Relevância na Descoberta Avançada de EDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Obter uma visão geral do estágio de Avaliação e sua função na determinação da riqueza dos problemas durante o treinamento de Relevância na Descoberta Eletrônico Avançada do Microsoft 365.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769272"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Avaliação no módulo relevância na Descoberta eDiscovery Avançada
  
A Descoberta Avançada permite a avaliação antecipada, por exemplo, dos problemas definidos e dos dados importados para um caso. A Descoberta Avançada permite que o especialista toma decisões sobre uma abordagem adotada e aplique essas decisões ao projeto de revisão de documentos.
  
## <a name="understanding-assessment"></a>Noções básicas sobre avaliação

Na Avaliação, o especialista revisa um conjunto aleatório de pelo menos 500 arquivos, que são usados para determinar a riqueza dos problemas e para produzir estatísticas que reflitam os resultados do treinamento. A avaliação é bem-sucedida quando arquivos relevantes suficientes são encontrados para alcançar um nível estatístico que ajudará a Relevância de Descoberta Eletrônica Avançada a fornecer estatísticas precisas e determinar efetivamente o ponto de estabilização no processo de treinamento. 
  
Quanto maior o número de arquivos relevantes no conjunto de avaliação, mais precisas as estatísticas e a eficácia do algoritmo de estabilidade. O número de arquivos relevantes nos arquivos de avaliação depende da riqueza do problema. A riqueza é a porcentagem estimada de arquivos relevantes no conjunto relevantes para um problema. Problemas com maior riqueza atingirão um número maior de arquivos relevantes mais rapidamente do que problemas com menor riqueza. Problemas com uma riqueza extremamente baixa (por exemplo, 2% ou menos) exigirão um conjunto de avaliação muito grande para alcançar um número significativo de arquivos relevantes.
  
As estatísticas, que são apresentadas nas guias Controlar e Decidir durante o treinamento e após o cálculo em lotes, incluem estimativas de recall para diferentes conjuntos de revisão. Em estatísticas, as estimativas baseadas em um conjunto de amostras (neste caso, os arquivos de avaliação) incluem a margem de erro e o nível de confiança dessa margem de erro. Por exemplo, o recall estimado de 80% pode ter uma margem de erro de mais ou menos 5% com um nível de confiança de 95%. Isso significa que o recall estimado é, na verdade, de 75% a 85% e essa estimativa tem confiança de 95%. Quanto maior o conjunto de avaliação, a margem de erro se torna menor e as estatísticas são mais precisas. 
  
Depois que o especialista analisa um conjunto inicial de 500 arquivos de avaliação, a Relevância pode determinar a margem atual de erro dos valores de recall. A relevância também recomenda uma margem de erro padrão para alcançar a otimização do conjunto de avaliação. Aqui estão alguns exemplos:
  
- Se o conjunto de avaliação já tiver resultado em uma margem de erro de mais ou menos 10%, a Relevância recomendará passar para o treinamento (nenhuma avaliação adicional é necessária). 

- Se o conjunto de avaliação tiver resultado em uma margem de erro de mais ou menos 13%, a Relevância poderá recomendar a revisão de outro conjunto de arquivos de avaliação para alcançar uma margem menor. 

- Se a riqueza for extremamente baixa, a relevância pode recomendar parar a avaliação mesmo que a margem de erro seja grande (tornando as estatísticas impraticáveis), porque o conjunto de avaliação necessário para alcançar uma margem útil de erro é muito grande.

Cada problema tem sua própria riqueza, margem atual de erro e, como resultado, número estimado de arquivos de avaliação adicionais. O próximo conjunto de avaliação é criado de acordo com o número máximo de arquivos (até 1.000 em um único conjunto).
  
Você pode aceitar as recomendações de relevância ou ajustar a margem de erro atual de acordo com suas necessidades. A margem atual padrão do erro é determinada para recall em igual ou superior a 75%.
  
> [!NOTE]
> O estágio Avaliação pode ser ignorado, na guia Controle de Relevância na  exibição expandida de um problema, des limpando a caixa de seleção Avaliação por problema e, em seguida, para "todos os problemas". **\>** Como resultado, não haverá estatísticas para esse problema. Limpar a **caixa de** seleção Avaliação só pode ser feita antes da avaliação ser executada. Quando vários problemas existirem em um caso, a avaliação será ignorada somente se a caixa de seleção estiver des clara para cada problema.
