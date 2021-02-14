---
title: Percepções de confiabilidade
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950337"
---
# <a name="reliability-insights"></a>Percepções de confiabilidade

Esta exibição fornece um resumo de saúde de seus dispositivos gerenciados. Para exibir dados de confiabilidade, selecione a **guia** Confiabilidade.


![Painel de confiabilidade: confiabilidade entre dispositivos no canto superior esquerdo, confiabilidade ao longo do tempo gráfico no canto superior direito, tabela de problemas superior na parte inferior. Botões de ajuda e comentários no canto inferior direito.](../../media/insights_reliability.png)

A seção **Confiabilidade** entre dispositivos oferece um resumo rápido da sua implantação nos últimos 14 dias, relatando a porcentagem de dispositivos considerados " health" e o tempo média observado desde a última falha relatada. 

 
O **gráfico Confiabilidade ao** longo do tempo à direita relata o número de dispositivos com erros críticos e o número total de erros críticos observados ao longo do tempo.

A **seção Principais problemas** detalha problemas detectados específicos que afetam pelo menos 5% de seus dispositivos gerenciados. Os detalhes relatados incluem:

- O tipo de problema
    - O aplicativo falha, em que um aplicativo para de funcionar ou para inesperadamente
    - O aplicativo trava, onde um aplicativo para de responder à entrada
    - Erros críticos, que ocorrem quando o Windows encontra um problema do qual ele não pode se recuperar
- O número de dispositivos afetados pelo mesmo problema
- A porcentagem de dispositivos gerenciados que o número representa
- A contagem total de ocorrências do problema específico
- O componente de software que parece ser a origem do problema
- A categoria do problema detectado:
    - Navegador (Edge, Chrome, IE)
    - Desconhecido (componentes que não são da Microsoft)
    - Driver (áudio, elementos gráficos ou outros drivers)
    - Produtividade (Slack, G-Suites, Microsoft Office e seus complementos ou extensões, Teams)
    - Mídia (aplicativos de imagem, música ou vídeo
    - Segurança (componentes de segurança do Windows)
- O status atual como Operações da Área de Trabalho Gerenciada da Microsoft investiga e corre o problema

