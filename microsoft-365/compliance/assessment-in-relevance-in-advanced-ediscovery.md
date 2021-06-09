---
title: Entender a Avaliação em Relevância no Advanced eDiscovery
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
description: Obter uma visão geral do estágio de Avaliação e sua função na determinação da riqueza de problemas durante o treinamento de relevância no Microsoft 365 Advanced eDiscovery.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769272"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Avaliação no módulo De relevância no Advanced eDiscovery
  
Advanced eDiscovery permite a avaliação antecipada, por exemplo, para os problemas definidos e os dados importados para um caso. Advanced eDiscovery permite ao especialista tomar decisões sobre uma abordagem adotada e aplicar essas decisões ao projeto de revisão de documentos.
  
## <a name="understanding-assessment"></a>Noções básicas sobre avaliação

Em Avaliação, o especialista analisa um conjunto aleatório de pelo menos 500 arquivos, que são usados para determinar a riqueza dos problemas e para produzir estatísticas que refletem os resultados do treinamento. A avaliação é bem-sucedida quando arquivos relevantes suficientes são encontrados para alcançar um nível estatístico que ajudará Advanced eDiscovery relevância para fornecer estatísticas precisas e determinar efetivamente o ponto de estabilização no processo de treinamento. 
  
Quanto maior o número de arquivos relevantes no conjunto de avaliação, mais precisas as estatísticas e a eficácia do algoritmo de estabilidade. O número de arquivos relevantes nos arquivos de avaliação depende da riqueza do problema. Richness é a porcentagem estimada de arquivos relevantes no conjunto relevante para um problema. Problemas com maior riqueza atingirão um número maior de arquivos relevantes mais rapidamente do que problemas com menor riqueza. Problemas com uma riqueza extremamente baixa (por exemplo, 2% ou menos) exigirão um conjunto de avaliação muito grande para alcançar um número significativo de arquivos Relevantes.
  
As estatísticas, que são apresentadas nas guias Acompanhar e Decidir durante o treinamento e após o cálculo em lotes, incluem estimativas de recall para diferentes conjuntos de revisão. Em estatísticas, as estimativas baseadas em um conjunto de exemplos (nesse caso, os arquivos de avaliação) incluem a margem de erro e o nível de confiança dessa margem de erro. Por exemplo, o recall estimado de 80% pode ter uma margem de erro de mais ou menos 5% com um nível de confiança de 95%. Isso significa que o recall estimado é, na verdade, de 75% a 85% e essa estimativa tem 95% de confiança. Quanto maior o conjunto de avaliação, a margem de erro fica menor e as estatísticas são mais precisas. 
  
Depois que o especialista revisa um conjunto inicial de 500 arquivos, a Relevância pode determinar a margem atual de erro dos valores de recall. A relevância também recomendará uma margem de erro padrão para alcançar para otimizar o conjunto de avaliação. Aqui estão alguns exemplos:
  
- Se o conjunto de avaliação já gerou uma margem de erro de mais ou menos 10%, a Relevância recomendará passar para o treinamento (nenhuma revisão adicional de avaliação é necessária). 

- Se o conjunto de avaliação gerou uma margem de erro de mais ou menos 13%, a Relevância pode recomendar a revisão de outro conjunto de arquivos de avaliação para atingir uma margem menor. 

- Se a riqueza for extremamente baixa, a Relevância pode recomendar interromper a avaliação mesmo que a margem de erro seja grande (tornando as estatísticas impraticáveis), pois o conjunto de avaliação necessário para atingir uma margem de erro útil é muito grande.

Cada problema tem sua própria riqueza, margem atual de erro e, como resultado, número estimado de arquivos de avaliação adicionais. O próximo conjunto de avaliação é criado de acordo com o número máximo de arquivos (até 1.000 em um único conjunto).
  
Você pode aceitar as recomendações de relevância ou ajustar a margem atual de erro de acordo com suas necessidades. A margem de erro atual padrão é determinada para recall igual ou superior a 75%.
  
> [!NOTE]
> O estágio de Avaliação pode ser ignorado, na guia Faixa de Relevância  no exibição expandido para um problema, limpando a caixa de seleção Avaliação por problema e, em seguida, para "todos os problemas". **\>** Como resultado, não haverá estatísticas para esse problema. A limpeza **da caixa de** seleção Avaliação só pode ser feita antes da avaliação ser realizada. Quando há vários problemas em um caso, a avaliação só será ignorada se a caixa de seleção for desapurada para cada problema.
