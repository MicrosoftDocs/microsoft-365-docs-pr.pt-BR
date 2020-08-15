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
description: Saiba mais sobre as recomendações de desempenho para sites modernos no SharePoint Online, como limitar chamadas para os pontos de extremidade externos e do SharePoint.
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

Do ponto de vista da otimização de desempenho, há algumas características que tornam os sites de portal modernos exclusivos. A principal diferença entre os sites de colaboração e de portal no SharePoint Online é dimensionada. Os sites de portal geralmente são esperados para servir mais exibições de página para um número maior de usuários do que os sites de colaboração e provavelmente contêm mais conteúdo estático e menos recursos editáveis. Além disso, a arquitetura de sites modernos difere de sites clássicos, pois a maior parte do processamento envolvido na renderização de páginas e o código em execução ocorre no cliente, e não no servidor.

A otimização de desempenho para sites de portal modernos é voltada principalmente para alguns objetivos gerais:

- Reduzir o tamanho total dos componentes de cada página de site
- Descarregamento da Hospedagem de arquivos estáticos comuns, como imagens, folhas de estilo e scripts para a CDN
- Limitar as chamadas para o SharePoint e pontos de extremidade externos somente para o que é necessário
- Evitar solicitações duplicadas para o mesmo conteúdo

Muitas das diretrizes neste artigo se concentram em minimizar e otimizar chamadas para o SharePoint Online. Fazer chamadas repetitivas toda vez que uma página é carregada afetará o desempenho dos usuários à medida que as informações serão recuperadas do serviço a cada vez, mesmo que não tenham sido alteradas. Assim, as solicitações para o SharePoint podem ser categorizadas como chamadas comuns para todos os usuários ou chamadas necessárias para cada usuário individual. Os resultados dessas duas categorias de chamada devem ser armazenados em cache para otimizar a experiência do usuário.

>[!NOTE]
>Use a [ferramenta diagnóstico de página para SharePoint](https://aka.ms/perftool) como ponto de partida para analisar métricas de desempenho específicas em páginas de site do SharePoint Online.

## <a name="modern-portal-site-limits-and-recommendations"></a>Limites e recomendações do site de portal moderno

|**Limite**|**Valor máximo recomendado**|**Observações**|
|:-----|:-----|:-----|:-----|
|Páginas e itens de notícias  <br/> |5.000 por site  <br/> |Recomendamos limitar o número de páginas e itens de notícias em um site de portal moderno para abaixo de 5.000.  <br/> |
|Web Parts em uma página  <br/> |20 por página  <br/> |Recomendamos usar o total de 20 ou menos Web Parts por página, incluindo Web Parts da Microsoft e Web Parts personalizadas. <br/> Para obter mais informações, consulte [otimizar o desempenho da Web Part em páginas do site moderno do SharePoint Online](modern-web-part-optimization.md).  <br/> |
|Web Parts dinâmicas em uma página  <br/> |4 por página  <br/> |Web Parts dinâmicas que fazem com que uma ou mais consultas para o SharePoint busquem os dados mais recentes devem ser limitadas a 4 por página. A Web Part _News_ é um exemplo de uma Web Part dinâmica. <br/> Para obter mais informações, consulte [otimizar o desempenho da Web Part em páginas do site moderno do SharePoint Online](modern-web-part-optimization.md).    <br/> |
|Grupos de segurança  <br/> |20 por site  <br/> |O número de grupos de segurança afeta a escala de muitas consultas em sites de portal modernos. Recomendamos que você limite o número de grupos de segurança para o menor conjunto possível, com, no máximo, 20 por site.  <br/> |
|Itens na navegação do site  <br/> |100 por site  <br/> |É recomendável adicionar menos de 100 itens à navegação do site e fazer uso de controles de navegação prontos.  <br/> Para obter mais informações, consulte [otimizar o peso da página em páginas do site moderno do SharePoint Online](modern-page-weight-optimization.md). <br/> |
|Tamanho máximo da imagem  <br/> |300 KB por imagem  <br/> |É recomendável limitar o tamanho de imagens para 300kb ou menores e usar uma CDN para hospedar imagens, folhas de estilo e scripts. <br/>Para obter mais informações, consulte [otimizar imagens em páginas de site modernas do SharePoint](modern-image-optimization.md) e [usar a CDN (rede de distribuição de conteúdo) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md).  <br/> |
|Usuários com direitos de edição  <br/> |200 usuários por site  <br/> |Os sites de portal do SharePoint são otimizados para visualização e consumo de conteúdo. As permissões de edição em um portal devem ser limitadas a um grupo restrito de usuários, pois as permissões de edição baixam controles adicionais e, portanto, executarão mais lentas para esses usuários. Portanto, um número excessivo de usuários com permissões de edição afetará a experiência geral. <br/> |
|IFrames de terceiros  <br/> |2 por página  <br/> |os iFrames são invisíveis com lentidão, pois carregam uma página externa separada, incluindo todo o conteúdo associado, como elementos JavaScript, CSS e Framework. Se você precisar usar iFrames, limite o número de 2 ou menos por página.<br/> Para obter mais informações, consulte [otimizar iframes nas páginas do site de publicação clássica e clássica do SharePoint Online](modern-iframe-optimization.md). <br/> |
|Chamadas para o serviço UPA  <br/> |1 por usuário por hora  <br/> |Recomendamos que você não faça chamadas _por solicitação_ para o serviço UPA (aplicativo de perfil de usuário). A [API do Microsoft Graph](https://docs.microsoft.com/graph/call-api) e o [PageContext](https://docs.microsoft.com/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) podem ser usados para consultar informações do usuário.  <br/> Se uma chamada de serviço UPA for necessária, faça uma única chamada quando necessário e, em seguida, armazene em cache as informações para reutilização na mesma sessão. |
|Chamadas para o serviço de taxonomia  <br/> |5 por usuário por hora  <br/> |Recomendamos que você não faça chamadas _por solicitação_ para o serviço de taxonomia. Se as chamadas de serviço de taxonomia forem necessárias, armazene em cache as informações para reutilização na mesma sessão. <br/> Para saber mais, confira [otimizar as chamadas de página no SharePoint Online páginas de site de publicação clássicas e clássicas](modern-page-call-optimization.md). <br/> |

## <a name="related-topics"></a>Tópicos relacionados

[Criando um portal do SharePoint saudável](https://docs.microsoft.com/sharepoint/portal-health)

[Ajustar o desempenho do SharePoint Online](tune-sharepoint-online-performance.md)

[Ajustar o desempenho do Office 365](tune-microsoft-365-performance.md)

[Limites do SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Desempenho na experiência moderna do SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Diretrizes de desempenho para os portais do SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-performance)
