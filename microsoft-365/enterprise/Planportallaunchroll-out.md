---
title: Planejando o plano de distribuição de início do portal no SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: Este artigo descreve como você pode planejar o lançamento do portal no SharePoint Online e quais etapas executar para um lançamento bem-sucedido
ms.openlocfilehash: e22fa4d9cbfed79841d844f111e3eb91a708512e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687501"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Planejando o plano de distribuição de início do portal no SharePoint Online

Um portal é um site do SharePoint na intranet que tem um grande número de visualizadores de site que consomem o conteúdo dele. Em grandes organizações pode haver vários deles; por exemplo, um portal da empresa e um portal do RH. Normalmente, os portais têm relativamente poucas pessoas que criam e escrevem o site e seu conteúdo. A maioria dos visitantes do portal apenas lê e consome o conteúdo.

Este artigo descreve como planejar a implantação e o plano de distribuição para o SharePoint Online. Também fornece abordagens para seguir, pois o teste de carga tradicional não é permitido no SharePoint Online. O SharePoint Online é um serviço de nuvem e os recursos de carga, a integridade e o equilíbrio geral de carga no serviço são gerenciados pela Microsoft.

Para ajudar na criação de um portal bem-sucedido, siga os princípios básicos, as práticas e as recomendações detalhadas na [criação, inicialização e manutenção de um portal saudável](https://go.microsoft.com/fwlink/?linkid=2105838) 

A abordagem de implantação está realçada abaixo.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Visão geral do planejamento de capacidade no SharePoint Online
Para usar eficientemente a capacidade e lidar com o crescimento inesperado, em qualquer farm, temos automação que controla determinados cenários de uso. Embora o crescimento exato seja imprevisível para qualquer um locatário em qualquer farm, a soma de solicitações agregada é previsível ao longo do tempo. Identificando as tendências de crescimento no SharePoint Online, podemos planejar a expansão futura. Para obter mais informações sobre [planejamento de capacidade e teste de carga do SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).

Uma parte importante de um lançamento bem-sucedido é a abordagem de "onda" ou "distribuição em fases", detalhada abaixo. 

## <a name="can-i-load-test-sharepoint-online"></a>Posso carregar o SharePoint Online de teste?
O SharePoint Online é um ambiente multilocatário compartilhado que é balanceado entre farms e a escala é ajustada de acordo com o andamento. O teste de carga de um ambiente, como o SharePoint Online, cuja escala muda continuamente não fornecerá resultados inesperados, mas não é permitido. 

Saiba mais:  [planejamento de capacidade e teste de carga do SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Otimizar páginas seguindo as diretrizes recomendadas
As páginas de uma implantação local não devem ser movidas como estão no SharePoint Online sem analisá-las em relação às diretrizes recomendadas para o SharePoint Online. A melhor abordagem é sempre otimizar qualquer Home Page para qualquer site ou portal no SharePoint, pois a maioria dos usuários em sua organização acessará como o ponto de partida para seus sites.

Alguns fatores básicos devem ser considerados:
- As implantações locais podem aproveitar caches tradicionais do lado do servidor, como cache de objetos, cache de saída e cache de BLOB. Com as diferenças de topologia na nuvem, essas opções não estão necessariamente disponíveis, pois as diferenças de escala enorme as tornam menos viáveis.
- Qualquer página/recurso/personalização usada para o consumo em nuvem deve ser otimizado para maior latência, bem como para os locais distribuídos dos usuários, de forma que os usuários em diferentes áreas ou regiões tenham uma experiência mais consistente. A nuvem oferece otimizações como redes de distribuição de conteúdo (CDN) para otimizar para uma base de usuários distribuídos, bem como para o SharePoint moderno, a última boa conhecida (LKG) é utilizada por nossas Web Parts de uso inativa (OOTB).

### <a name="what-to-do"></a>O que fazer:
 - Para todas as páginas do site no SharePoint Online, use a [ferramenta diagnóstico de página](https://aka.ms/perftool), que é uma extensão do Chromium que auxiliará na análise e fornecimento de orientações. Isso pode ser usado por proprietários de site, editores, administradores e desenvolvedores, já que é projetado para ser um ponto de partida para análise e otimização.
 - Os desenvolvedores também devem usar ferramentas de desenvolvimento como a ferramenta de desenvolvedor F12 do navegador, bem como CTRL-F12 no navegador em páginas modernas. O [Fiddler](https://www.telerik.com/download/fiddler) também pode ser usado para revisar o peso do tamanho (o tamanho da página em megabytes) da página e o número de chamadas e elementos que afetam a carga geral da página. 

Esta seção foi um breve resumo para otimizar páginas.  Para saber mais, confira:  [Creating, launching and maintaining a Healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).

## <a name="follow-a-wave--phased-roll-out-approach"></a>Seguir uma abordagem de distribuição de onda/em fases
A abordagem de Big Bang tradicional para os lançamentos de site não permitirá a verificação de que personalizações, fontes externas, serviços ou processos foram testados na escala direita. Isso não significa que levará meses para iniciar, mas é recomendável mais de pelo menos vários dias, dependendo do tamanho da sua organização. Após um plano de distribuição de ondas, você terá a opção de pausar e resolver problemas antes de prosseguir com a próxima fase e, portanto, reduzirá o número potencial de usuários afetados por qualquer problema. O SharePoint como um serviço dimensiona sua capacidade com base no uso e no uso previsto e, embora não seja necessário notificá-los do lançamento, siga as diretrizes para garantir o sucesso.
  
Conforme mostrado na imagem a seguir, muitas vezes o número de usuários convidados é significativamente maior do que aqueles que realmente usam o site. Esta imagem mostra uma estratégia de implantação de uma versão. Este método ajuda a identificar maneiras de melhorar o site do SharePoint antes que a maioria dos usuários o veja.
  
![Gráfico mostrando usuários convidados e ativos](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
Na fase piloto, é bom obter comentários dos usuários que a organização confia e sabe que serão envolvidos. Dessa forma, é possível avaliar como o sistema está sendo usado, além de como ele está sendo executado.
  
Durante cada uma das ondas, reúna os comentários dos usuários em torno dos recursos, bem como o desempenho durante cada onda de implantação. Isso tem a vantagem de apresentar lentamente o sistema e fazer melhorias à medida que o sistema é mais usado. Isso também nos permite reagir à maior carga à medida que o site é implantado em mais e mais usuários e combinado com as diretrizes para otimização de página garante uma experiência positiva para seus usuários.

### <a name="what-to-do"></a>O que fazer:
- Decida sobre o momento de cada fase e certifique-se de que você tem uma oportunidade de contingência/pausa, caso precise fazer ajustes antes de continuar
- Planeje seu primeiro grupo de usuários que você deseja habilitar, para garantir que você receba os comentários de que você precisa para avançar. Isso significa que, quando possível, selecione um grupo ativo de usuários que fornecerá comentários de forma oportuna
- Ao planejar cada onda, experimente e comece com uma pequena base de usuários (menos de 5000 usuários) e, em seguida, aumente os tamanhos de grupo conforme você prossegue com cada onda. Isso ajuda a criar uma abordagem escalonada e permite oportunidades de pausa mais fáceis que podem ser necessárias.
