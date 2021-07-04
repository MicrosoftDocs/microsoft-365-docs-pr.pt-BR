---
title: SharePoint Limites do site de portal moderno online
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
description: Saiba mais sobre recomendações de desempenho para sites modernos no SharePoint Online, como limitar chamadas ao Sharepoint e pontos de extremidade externos.
ms.openlocfilehash: 2429869c5397e0260876ee5a765ea18ae3fc42a1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288870"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint Limites do site de portal moderno online

Este artigo fornece recomendações de desempenho para sites de portal modernos SharePoint Online. Use as diretrizes deste artigo para otimizar o desempenho moderno do site do portal e evitar problemas comuns de desempenho.

## <a name="performance-considerations-for-modern-portal-sites"></a>Considerações de desempenho para sites de portal modernos

Do ponto de vista da otimização de desempenho, há algumas características que diferenciam sites de portal modernos. A principal diferença entre a colaboração e sites de portal no SharePoint Online é a escala. Os sites de portal geralmente são esperados para atender a mais exibições de página para um número maior de usuários do que sites de colaboração e provavelmente contêm mais conteúdo estático e menos recursos editáveis. Além disso, a arquitetura de sites modernos difere de sites clássicos, já que a maior parte do processamento envolvido na renderização de páginas e na execução de código ocorre no cliente e não no servidor.

A otimização de desempenho para sites de portal modernos concentra-se principalmente em alguns objetivos gerais:

- Reduzir o tamanho total dos componentes de cada página de site
- Descarrega a hospedagem de arquivos estáticos comuns, como imagens, folhas de estilo e scripts para CDN
- Limitar chamadas para SharePoint e pontos de extremidade externos apenas para o que é necessário
- Evitar solicitações duplicadas para o mesmo conteúdo

Muitas das diretrizes deste artigo se concentram na minimização e otimização de chamadas para SharePoint Online. Fazer chamadas repetitivas sempre que uma página for carregada afetará o desempenho dos usuários, pois as informações serão recuperadas do serviço sempre que ela não tiver sido alterada. Dessa forma, as solicitações SharePoint podem ser categorizadas como chamadas comuns para todos os usuários ou chamadas necessárias para cada usuário individual. Os resultados dessas duas categorias de chamada devem ser armazenados em cache para otimizar a experiência do usuário.

>[!NOTE]
>Use a [ferramenta Diagnóstico de Página SharePoint como](./page-diagnostics-for-spo.md) ponto de partida para analisar métricas de desempenho específicas em SharePoint páginas de site online.

## <a name="modern-portal-site-limits-and-recommendations"></a>Limites e recomendações de site de portal moderno

|**Limite**|**Valor máximo recomendado**|**Anotações**|
|:-----|:-----|:-----|:-----|
|Páginas e itens de notícias  <br/> |5.000 por site  <br/> |Recomendamos limitar o número de páginas e itens de notícias em um site de portal moderno para abaixo de 5.000.  <br/> |
|Web Parts em uma página  <br/> |20 por página  <br/> |Recomendamos o uso de 20 ou menos Web Parts totais por página, incluindo web parts da Microsoft e web parts personalizadas. <br/> Para obter mais informações, consulte [Optimize web part performance in SharePoint Online modern site pages](modern-web-part-optimization.md).  <br/> |
|Web Parts dinâmicas em uma página  <br/> |4 por página  <br/> |Web Parts dinâmicas que fazem uma ou mais consultas para SharePoint buscar os dados mais recentes devem ser limitadas a 4 por página. A _Web_ Part Notícias é um exemplo de uma Web Part dinâmica. <br/> Para obter mais informações, consulte [Optimize web part performance in SharePoint Online modern site pages](modern-web-part-optimization.md).    <br/> |
|Grupos de segurança  <br/> |20 por site  <br/> |O número de grupos de segurança afeta a escala de muitas consultas em sites de portal modernos. Recomendamos que você limite o número de grupos de segurança para o menor conjunto possível, com no máximo 20 por site.  <br/> |
|Itens na navegação do site  <br/> |100 por site  <br/> |Recomendamos adicionar menos de 100 itens à navegação do site e que você use controles de navegação in-loco.  <br/> Para obter mais informações, consulte [Optimize page weight in SharePoint Online modern site pages](modern-page-weight-optimization.md). <br/> |
|Tamanho máximo da imagem  <br/> |300 Kb por imagem  <br/> |Recomendamos limitar o tamanho das imagens a 300kb ou menor e usar um CDN para hospedar imagens, folhas de estilo e scripts. <br/>Para obter mais informações, consulte [Optimize images in SharePoint Online modern site pages](modern-image-optimization.md) and Use the Office 365 Rede de Distribuição de Conteúdo [(CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).  <br/> |
|Usuários com direitos de edição  <br/> |200 usuários por site  <br/> |SharePoint sites de portal são otimizados para exibir e consumir conteúdo. As permissões de edição em um portal devem ser limitadas a um grupo restrito de usuários porque as permissões de edição baixam controles adicionais e, portanto, serão mais lentas para esses usuários. Um número excessivo de usuários com permissões de edição afetará a experiência geral. <br/> |
|IFrames de terceiros  <br/> |2 por página  <br/> |Os iFrames são imprevisíveis e lentos porque carregam uma página externa separada, incluindo todo o conteúdo associado, como javascript, CSS e elementos de estrutura. Se você deve usar iFrames, limite seu número para 2 ou menos por página.<br/> Para obter mais informações, consulte [Optimize iFrames in SharePoint Online modern and classic publishing site pages](modern-iframe-optimization.md). <br/> |
|Chamadas para o serviço UPA  <br/> |1 por usuário por hora  <br/> |Recomendamos que você não faça chamadas _por_ solicitação para o serviço UPA (Aplicativo de Perfil de Usuário). A [API Graph Microsoft](/graph/call-api) e [PageContext](/javascript/api/sp-page-context/pagecontext) podem ser usadas para consultar informações do usuário.  <br/> Se uma chamada de serviço UPA for necessária, faça uma única chamada quando necessário e, em seguida, armazenar em cache as informações para reutilização na mesma sessão. |
|Chamadas para o serviço taxonomia  <br/> |5 por usuário por hora  <br/> |Recomendamos que você não faça chamadas _por_ solicitação para o serviço taxonomia. Se as chamadas de serviço taxonomia são necessárias, armazenar em cache as informações para reutilização na mesma sessão. <br/> Para obter mais informações, consulte [Optimize page calls in SharePoint Online modern and classic publishing site pages](modern-page-call-optimization.md). <br/> |

## <a name="related-topics"></a>Tópicos relacionados

[Criando um portal SharePoint saudável](/sharepoint/portal-health)

[Ajustar o desempenho do SharePoint Online](tune-sharepoint-online-performance.md)

[Ajustar o desempenho do Office 365](tune-microsoft-365-performance.md)

[Limites do SharePoint Online](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Desempenho na experiência moderna do SharePoint](/sharepoint/modern-experience-performance)

[Diretrizes de desempenho para os portais do SharePoint Online](/sharepoint/dev/solution-guidance/portal-performance)
