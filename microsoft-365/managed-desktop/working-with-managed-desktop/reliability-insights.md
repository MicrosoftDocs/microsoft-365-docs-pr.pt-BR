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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739751"
---
# <a name="reliability-insights"></a>Percepções de confiabilidade

Esta exibição fornece um resumo de saúde de seus dispositivos gerenciados. Para exibir dados de confiabilidade, selecione a guia **Confiabilidade.**


![Painel de confiabilidade: confiabilidade entre dispositivos no canto superior esquerdo, confiabilidade ao longo do gráfico de tempo no canto superior direito, tabela de problemas superiores na parte inferior. Botões de ajuda e comentários no canto inferior direito.](../../media/insights_reliability.png)

A **seção Confiabilidade** entre dispositivos oferece um resumo rápido da sua implantação nos últimos 14 dias informando a porcentagem de dispositivos considerados "saudáveis" e o tempo média observado desde a última falha relatada. 

 
O **gráfico De confiabilidade** ao longo do tempo à direita relata o número de dispositivos com erros críticos e o número total de erros críticos observados ao longo do tempo.

A **seção Principais problemas** detalha problemas detectados específicos que afetam pelo menos 5% dos dispositivos gerenciados. Os detalhes relatados incluem:

- O tipo de problema
    - Falhas no aplicativo, em que um aplicativo para de funcionar ou para inesperadamente
    - O aplicativo trava, onde um aplicativo para de responder à entrada
    - Erros críticos, que ocorrem quando Windows encontrou um problema do qual não pode se recuperar
- O número de dispositivos afetados pelo mesmo problema
- A porcentagem de dispositivos gerenciados que o número representa
- A contagem total de ocorrências do problema específico
- O componente de software que parece ser a origem do problema
- A categoria do problema detectado:
    - Navegador (Edge, Chrome, IE)
    - Desconhecido (componentes que não são da Microsoft)
    - Driver (áudio, gráficos ou outros drivers)
    - Produtividade (Slack, G-Suites, Microsoft Office e seus complementos ou extensões, Teams)
    - Mídia (aplicativos de imagem, música ou vídeo
    - Segurança (Windows de segurança)
- O status atual como Área de Trabalho Gerenciada da Microsoft Operações investiga e correção do problema

