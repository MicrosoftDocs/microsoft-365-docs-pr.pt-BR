---
title: Otimizar imagens nas páginas de site moderno do SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Saiba como usar as ferramentas incluídas no SharePoint Online para otimizar imagens em páginas de site modernas do SharePoint Online.
ms.openlocfilehash: a4f2def86e1378a9fb76ae9ecbe6a55da75ecffc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923011"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a>Otimizar imagens nas páginas de site moderno do SharePoint Online

Este artigo vai ajudá-lo a entender como otimizar imagens nas páginas de site moderno do SharePoint Online.

Para saber mais sobre como otimizar imagens em sites de publicação clássicos, confira [Otimização de imagem do SharePoint Online](image-optimization-for-sharepoint-online.md)..

>[!NOTE]
>Para obter mais informações sobre o desempenho dos portais modernos do SharePoint Online, confira [Desempenho na experiência moderna do SharePoint](/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a>Usar a ferramenta Diagnóstico de página do SharePoint para analisar a otimização de imagens

A ferramenta Diagnóstico de Página para SharePoint é uma extensão do navegador para os novos navegadores Microsoft Edge (https://www.microsoft.com/edge) e Chrome que analisam o portal moderno do SharePoint Online e as páginas clássicas de site de publicação. A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho. Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.

Ao analisar um site moderno do SharePoint com a ferramenta Diagnóstico de página do SharePoint, você pode ver as informações sobre imagens grandes no painel _Testes de diagnóstico_.

Os resultados possíveis incluem:

- **Atenção necessária** (vermelho): a página contém **uma ou mais** imagens com tamanho maior que 300 KB
- **Nenhuma ação necessária** (verde): a página não contém imagens com tamanho maior que 300 KB

Se o resultado **Imagens grandes detectadas** aparecer na seção dos resultados **Atenção necessária**, você poderá clicar no resultado para ver mais detalhes.

![Resultados da ferramenta Diagnóstico de Página](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a>Solucionar problemas de imagens grandes

Se uma página contiver imagens com tamanho superior a 300 KB, selecione o resultado **Imagens grandes detectadas** para ver quais são as imagens muito grandes. Nas páginas modernas do SharePoint Online, as renderizações de imagens são fornecidas e dimensionadas automaticamente, dependendo do tamanho da janela do navegador e da resolução do monitor do cliente. Você sempre deve otimizar as imagens para uso na Web antes de carregá-las no SharePoint Online. Imagens muito grandes serão reduzidas automaticamente em tamanho e resolução, o que pode resultar em características inesperadas de renderização.

Antes de fazer as revisões das páginas para corrigir problemas de desempenho, anote o tempo de carregamento da página nos resultados da análise. Execute a ferramenta novamente após a revisão para ver se o novo resultado está dentro do padrão da linha de base e verifique o tempo de carregamento da nova página para ver se melhorou.

![Resultados do tempo de carregamento da página](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>O tempo de carregamento da página pode variar de acordo com vários fatores, como a carga da rede, hora do dia e outras condições transitórias. Você deve testar o tempo de carregamento da página algumas vezes antes e depois de fazer as alterações para ajudá-lo a calcular uma média dos resultados.

## <a name="related-topics"></a>Tópicos relacionados

[Ajustar o desempenho do SharePoint Online](tune-sharepoint-online-performance.md)

[Ajustar o desempenho do Office 365](tune-microsoft-365-performance.md)

[Desempenho na experiência moderna do SharePoint](/sharepoint/modern-experience-performance)

[Redes de distribuição de conteúdo](content-delivery-networks.md)

[Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)