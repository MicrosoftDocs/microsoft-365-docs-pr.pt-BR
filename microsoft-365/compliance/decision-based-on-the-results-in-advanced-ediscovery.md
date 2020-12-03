---
title: Decisão com base nos resultados da descoberta eletrônica avançada
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
description: Saiba como a guia decidir em descoberta eletrônica avançada fornece dados que podem ajudá-lo a determinar o tamanho correto do conjunto de arquivos de caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60213226bef1c04767d4be17a09b58d6940ac223
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562962"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a>Decisão com base nos resultados da descoberta eletrônica avançada (clássica)

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 Na descoberta eletrônica avançada, a guia decidir fornece informações adicionais para exibir e usar estatísticas de suporte à decisão para determinar o tamanho do conjunto de análise de arquivos de caso. 
  
## <a name="using-the-decide-tab"></a>Usando a guia decidir

![Decisão de Relevância](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Esta guia inclui os seguintes componentes:
  
- **Problema**: aqui, você pode selecionar o problema de interesse na lista. 
    
- **Taxa de recuperação de revisão**: comparações de análise de descoberta eletrônica avançada de acordo com as pontuações de relevância. O ponto de corte no gráfico representa a porcentagem de arquivos a serem revisados, mapeados para uma pontuação de relevância. Isso é usado na fase de teste de relevância e como um limite de exportação para a seleção. O ponto de corte padrão, para o número de arquivos a serem revisados, é o ponto no qual o equilíbrio entre recall e Precision é ideal. O ponto de corte real deve ser determinado pelo usuário dependendo dos objetivos e da troca de custo (% revisão) e risco (% recall). Usando o controle deslizante, você pode ajustar o ponto de corte e ver o efeito no gráfico e nos parâmetros, ao ajustar a porcentagem de arquivos relevantes a serem recuperados e antes de validar uma decisão.
    
- **Parâmetros**: revisar, renovar, os parâmetros de custo total relevantes e totais são estatísticas calculadas cumulativas referentes ao conjunto de revisão em relação à coleção para o caso inteiro. As definições desses parâmetros são as seguintes:
    
    **Revisão**: porcentagem de arquivos a serem revisados com base nesse corte. 
    
    **Recall**: porcentagem de arquivos relevantes no conjunto de revisão. 
    
    **Próximo relevante**: custo para revisar e identificar um arquivo relevante adicional que não está atualmente no conjunto de revisão. 
    
    **Custo total**: custo para a revisão desse percentual dos arquivos de caso. As configurações de parâmetros de custo podem ser definidas pelo gerente de caso.
    
- **Distribuição por Pontuação de relevância**: os arquivos na exibição cinza escuro à esquerda estão abaixo da Pontuação de corte. Uma dica de ferramenta exibe a pontuação de relevância e a porcentagem relacionada de arquivos no conjunto de arquivos de revisão em relação ao total de arquivos.
    
O painel de detalhes expandido exibe detalhes adicionais. Os arquivos nas figuras de coleção não incluem arquivos vazios ou nebulous. Os números de arquivos da família representam arquivos que não são carregados em relevância, ainda que sejam contados como parte da família.
  
## <a name="related-topics"></a>Tópicos relacionados

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre avaliação em relevância](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Marcação e avaliação](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Realizando treinamento de relevância](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Análise de relevância de rastreamento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Testando análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md)

