---
title: Entender a avaliação em relevância na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Obtenha uma visão geral do estágio de avaliação e sua função para determinar a riqueza de problemas durante o treinamento de relevância no Microsoft 365 Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: afd4f1f549d52652ac02cfa410efc507ece58910
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818410"
---
# <a name="understand-assessment-in-relevance-in-advanced-ediscovery-classic"></a>Entender a avaliação em relevância na descoberta eletrônica avançada (clássica)

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
A descoberta eletrônica avançada permite a avaliação prévia, por exemplo, para os problemas definidos e os dados importados para um caso. A descoberta eletrônica avançada permite que o especialista tome decisões sobre uma abordagem adotada e aplique essas decisões ao projeto de revisão do documento.
  
## <a name="understanding-assessment"></a>Noções básicas sobre avaliação

Em avaliação, o especialista revisa um conjunto aleatório de pelo menos 500 arquivos, que são usados para determinar a riqueza dos problemas e produzir estatísticas que refletem os resultados de treinamento. A avaliação é bem-sucedida quando são encontrados arquivos relevantes suficientes para atingir um nível estatístico que ajudará a garantir a relevância avançada de descoberta eletrônica para fornecer estatísticas precisas e para determinar efetivamente o ponto de estabilização no processo de treinamento. 
  
Quanto maior o número de arquivos relevantes no conjunto de avaliação, mais precisos são as estatísticas e a eficácia do algoritmo de estabilidade. O número de arquivos relevantes dentro dos arquivos de avaliação depende da riqueza do problema. Riqueza é a porcentagem estimada de arquivos relevantes no conjunto relevante para um problema. Problemas com maior riqueza atingirão um número maior de arquivos relevantes mais rapidamente do que problemas com riqueza inferior. Problemas com riqueza extremamente baixa (por exemplo, 2% ou menos) exigirão um conjunto de avaliação muito grande para alcançar um número significativo de arquivos relevantes.
  
As estatísticas, que são apresentadas no controle e decidem as guias durante o treinamento e depois do cálculo em lotes, incluem estimativas de recall para diferentes conjuntos de revisão. Em estatísticas, as estimativas baseadas em um conjunto de amostra (neste caso, os arquivos de avaliação) incluem a margem de erro e o nível de confiança dessa margem de erro. Por exemplo, a recuperação estimada de 80% pode ter uma margem de erro de mais ou menos 5% com um nível de confiança de 95%. Isso significa que a RECALL estimada é de 75%-85% e esta estimativa tem 95% de confiança. Quanto maior o conjunto de avaliação, a margem de erro torna-se menor e as estatísticas são mais precisas. 
  
Depois que o especialista revisa um conjunto de avaliação inicial de 500 arquivos, a relevância pode determinar a margem atual de erro dos valores de recuperação. A relevância também recomenda uma margem de erro padrão para alcançar a otimização do conjunto de avaliação. Aqui estão alguns exemplos:
  
- Se o conjunto de avaliação já tiver resultado uma margem de erro de mais ou menos 10%, a relevância recomendará a migração para o treinamento (nenhuma análise adicional da avaliação é necessária). 
    
- Se o conjunto de avaliação tiver uma margem de erro de mais ou menos 13%, a relevância poderá recomendar a revisão de outro conjunto de arquivos de avaliação para alcançar uma margem menor. 
    
- Se a riqueza for extremamente baixa, a relevância poderá ser recomendável parando a avaliação, mesmo que a margem de erro seja grande (tornando as estatísticas impraticáveis) porque o conjunto de avaliação necessário para atingir uma margem de erro útil é muito grande.
    
Cada problema tem sua própria riqueza, margem atual de erro e, como resultado, o número estimado de arquivos de avaliação adicionais. O próximo conjunto de avaliação é criado de acordo com o número máximo de arquivos (até 1.000 em um único conjunto).
  
Você pode aceitar as recomendações de relevância ou ajustar a margem de erro atual de acordo com suas necessidades. A margem de erro atual padrão é determinada para a recuperação em igual ou acima de 75%.
  
> [!NOTE]
> O estágio de avaliação pode ser ignorado, na guia ** \> controle de relevância** no modo de exibição expandido para um problema, desmarcando a caixa de seleção de **avaliação** por problema e, em seguida, para "todos os problemas". No entanto, como resultado, não haverá estatísticas para esse problema. > limpar a caixa de seleção de **avaliação** só pode ser feita antes da avaliação ser realizada. Onde houver vários problemas em um caso, a avaliação será ignorada somente se a caixa de seleção estiver desmarcada para cada problema 
  
## <a name="related-topics"></a>Tópicos relacionados

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Marcação e avaliação](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Treinamento de marcação e relevância](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análise de relevância de rastreamento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidindo com base nos resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testando análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md)

