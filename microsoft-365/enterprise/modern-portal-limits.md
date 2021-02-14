---
title: Limites do site de portal moderno do SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: Saiba mais sobre as recomendações de desempenho para sites modernos no SharePoint Online, como limitar chamadas para o Sharepoint e pontos de extremidade externos.
ms.openlocfilehash: 2afca20183bef8c8f6dda9bdc35a44e5153ef07c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687372"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>Limites do site de portal moderno do SharePoint Online

Este artigo fornece recomendações de desempenho para sites de portal modernos no SharePoint Online. Use as diretrizes deste artigo para otimizar o desempenho do site de portal moderno e evitar problemas comuns de desempenho.

## <a name="performance-considerations-for-modern-portal-sites"></a>Considerações de desempenho para sites de portal modernos

Do ponto de vista da otimização de desempenho, há algumas características que fazem com que os sites de portal modernos sejam exclusivos. A principal diferença entre sites de portal e colaboração no SharePoint Online é a escala. Geralmente, espera-se que os sites de portal sirva mais exibições de página para um número maior de usuários do que sites de colaboração e provavelmente contêm mais conteúdo estático e menos recursos editáveis. Além disso, a arquitetura de sites modernos difere dos sites clássicos, já que a maior parte do processamento envolvido na renderização de páginas e na execução do código ocorre no cliente em vez do servidor.

A otimização de desempenho para sites de portal modernos se concentra principalmente em alguns objetivos gerais:

- Reduzir o tamanho total dos componentes de cada página do site
- Descarregar a hospedagem de arquivos estáticos comuns, como imagens, folhas de estilo e scripts para a CDN
- Limitar chamadas para o SharePoint e pontos de extremidade externos apenas para o que é necessário
- Evitar solicitações duplicadas para o mesmo conteúdo

Muitas das diretrizes neste artigo se concentram em minimizar e otimizar as chamadas para o SharePoint Online. Fazer chamadas repetitivas sempre que uma página for carregada afetará o desempenho dos usuários, pois as informações serão recuperadas do serviço sempre, mesmo que não tenha sido alterada. Dessa forma, as solicitações para o SharePoint podem ser categorizadas como chamadas comuns para todos os usuários ou chamadas necessárias para cada usuário individual. Os resultados dessas duas categorias de chamada devem ser armazenados em cache para otimizar a experiência do usuário.

>[!NOTE]
>Use a [ferramenta Diagnóstico de Página para SharePoint](https://aka.ms/perftool) como ponto de partida para analisar métricas de desempenho específicas nas páginas do site do SharePoint Online.

## <a name="modern-portal-site-limits-and-recommendations"></a>Limites e recomendações do site de portal moderno

|**Limite**|**Valor máximo recomendado**|**Anotações**|
|:-----|:-----|:-----|:-----|
|Páginas e itens de notícias  <br/> |5.000 por site  <br/> |Recomendamos limitar o número de páginas e itens de notícias em um site de portal moderno para menos de 5.000.  <br/> |
|Web Parts em uma página  <br/> |20 por página  <br/> |Recomendamos o uso de 20 ou menos Web Parts totais por página, incluindo web parts da Microsoft e web parts personalizadas. <br/> Para saber mais, confira Otimizar o desempenho da Web Part nas páginas do site moderno do [SharePoint Online.](modern-web-part-optimization.md)  <br/> |
|Web Parts dinâmicas em uma página  <br/> |4 por página  <br/> |As Web Parts dinâmicas que fazem uma ou mais consultas ao SharePoint para buscar os dados mais recentes devem ser limitadas a 4 por página. A _Web_ Part notícias é um exemplo de uma web part dinâmica. <br/> Para saber mais, confira Otimizar o desempenho da Web Part nas páginas do site moderno do [SharePoint Online.](modern-web-part-optimization.md)    <br/> |
|Grupos de segurança  <br/> |20 por site  <br/> |O número de grupos de segurança afeta a escala de muitas consultas em sites de portal modernos. Recomendamos que você limite o número de grupos de segurança ao menor conjunto possível, com no máximo 20 por site.  <br/> |
|Itens na navegação do site  <br/> |100 por site  <br/> |Recomendamos adicionar menos de 100 itens à navegação no site e que você use controles de navegação internos.  <br/> Para saber mais, confira [Otimizar o peso da página nas páginas do site moderno do SharePoint Online.](modern-page-weight-optimization.md) <br/> |
|Tamanho máximo da imagem  <br/> |300 Kb por imagem  <br/> |Recomendamos limitar o tamanho das imagens a 300kb ou menos e usar uma CDN para hospedar imagens, folhas de estilo e scripts. <br/>Para saber mais, confira Otimizar imagens em páginas de site modernas do [SharePoint Online](modern-image-optimization.md) e usar a Rede de Distribuição de Conteúdo [(CDN) do Office 365 com o SharePoint Online.](use-microsoft-365-cdn-with-spo.md)  <br/> |
|Usuários com direitos de edição  <br/> |200 usuários por site  <br/> |Os sites de portal do SharePoint são otimizados para exibição e consumo de conteúdo. As permissões de edição em um portal devem ser limitadas a um grupo restrito de usuários porque as permissões de edição baixam controles adicionais e, portanto, terão um desempenho mais lento para esses usuários. Um número excessivo de usuários com permissões de edição afetará a experiência geral. <br/> |
|IFrames de terceiros  <br/> |2 por página  <br/> |Os iFrames são imprevisíveis lentos porque carregam uma página externa separada, incluindo todo o conteúdo associado, como javascript, CSS e elementos de estrutura. Se você tiver que usar iFrames, limite seu número a 2 ou menos por página.<br/> Para saber mais, confira [Otimizar iFrames nas](modern-iframe-optimization.md)páginas de site de publicação clássica e modernas do SharePoint Online. <br/> |
|Chamadas para o serviço UPA  <br/> |1 por usuário por hora  <br/> |Recomendamos que você não faça chamadas _por solicitação_ para o serviço UPA (Aplicativo de Perfil de Usuário). A [API do Microsoft Graph](https://docs.microsoft.com/graph/call-api) e [PageContext](https://docs.microsoft.com/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) podem ser usadas para consultar informações do usuário.  <br/> Se uma chamada de serviço UPA for necessária, faça uma única chamada quando necessário e, em seguida, armazenar em cache as informações para reutilização na mesma sessão. |
|Chamadas para o serviço de Taxonomia  <br/> |5 por usuário por hora  <br/> |Recomendamos que você não faça _chamadas por_ solicitação para o serviço de Taxonomia. Se as chamadas de serviço de taxonomia são necessárias, armazenar em cache as informações para reutilização na mesma sessão. <br/> Para saber mais, confira Otimizar chamadas de página nas páginas do site de publicação clássico e moderno do [SharePoint Online.](modern-page-call-optimization.md) <br/> |

## <a name="related-topics"></a>Tópicos relacionados

[Criando um portal compartilhamento do SharePoint](https://docs.microsoft.com/sharepoint/portal-health)

[Ajustar o desempenho do SharePoint Online](tune-sharepoint-online-performance.md)

[Ajustar o desempenho do Office 365](tune-microsoft-365-performance.md)

[Limites do SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Desempenho na experiência moderna do SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Diretrizes de desempenho para os portais do SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-performance)
