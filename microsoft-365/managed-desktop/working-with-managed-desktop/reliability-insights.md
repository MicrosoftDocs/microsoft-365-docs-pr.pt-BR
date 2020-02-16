---
title: Insights de confiabilidade
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b7f56a64f1846676f458f7b3ddb210e84b9ca8f7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085661"
---
# <a name="reliability-insights"></a>Insights de confiabilidade

Este modo de exibição fornece um resumo de integridade dos dispositivos gerenciados. Para exibir os dados de confiabilidade, selecione a guia **confiabilidade** .


![Painel de confiabilidade: confiabilidade entre dispositivos no canto superior esquerdo, confiabilidade através do gráfico de tempo no canto superior direito, principais problemas na parte inferior. Botões de ajuda e comentários no canto inferior direito.](../../media/insights_reliability.png)

A seção **confiabilidade entre dispositivos** oferece um resumo de integridade rápida de sua implantação nos últimos 14 dias, relatando a porcentagem de dispositivos considerados como "saudáveis" e o tempo médio observado desde a última falha relatada. 

 
O gráfico de **confiabilidade ao longo do tempo** indica o número de dispositivos com erros críticos e o número total de erros críticos observados ao longo do tempo.

A seção **principais problemas** detalha os problemas detectados específicos que afetam pelo menos 5% dos seus dispositivos gerenciados. Os detalhes relatados incluem:

- O tipo de problema
    - O aplicativo falha, no qual um aplicativo para de funcionar ou pára inesperadamente
    - O aplicativo paralisa, onde um aplicativo pára de responder à entrada
    - Erros críticos, que ocorrem quando o Windows encontrou um problema que não pode se recuperar de
- O número de dispositivos afetados pelo mesmo problema
- A porcentagem de dispositivos gerenciados que o número representa
- A contagem total de ocorrências do problema específico
- O componente de software que parece ser a origem do problema
- A categoria do problema detectado:
    - Navegador (borda, Chrome, IE)
    - Desconhecido (componentes não Microsoft)
    - Driver (áudio, gráficos ou outros drivers)
    - Produtividade (margem de atraso, pacotes G-Suites, Microsoft Office e seus complementos ou extensões, equipes)
    - Mídia (imagem, música ou aplicativos de vídeo
    - Segurança (componentes de segurança do Windows)
- O status atual como operações de área de trabalho gerenciada da Microsoft investiga e corrige o problema

