---
title: Planejando seu plano de lançamento do portal no SharePoint Online
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
description: Este artigo descreve como você pode planejar o lançamento do portal no SharePoint Online e quais etapas tomar para um lançamento bem-sucedido
ms.openlocfilehash: d77baac6209a4002bb1c27513d5ccfdf5c4ac28a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905687"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Planejando seu plano de lançamento do portal no SharePoint Online

Um portal é um site do SharePoint na intranet que tem um grande número de visualizadores de site que consomem o conteúdo dele. Em grandes organizações pode haver vários deles; por exemplo, um portal da empresa e um portal do RH. Normalmente, os portais têm relativamente poucas pessoas que criam e escrevem o site e seu conteúdo. A maioria dos visitantes do portal apenas lê e consome o conteúdo.

Este artigo descreve como planejar seu plano de implantação e distribuição para SharePoint Online. Ele também fornece abordagens a seguir, pois o teste de carga tradicional não é permitido no SharePoint Online. SharePoint Online é um serviço de nuvem e os recursos de carga, a saúde e o equilíbrio geral de carga no serviço são gerenciados pela Microsoft.

Para ajudar na criação de um portal bem-sucedido, siga os princípios básicos, práticas e recomendações detalhados na [criação,](/sharepoint/portal-health) no lançamento e na manutenção de um portal saudável 

A abordagem de implantação é realçada abaixo.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Visão geral do planejamento de capacidade no SharePoint Online
Para usar com eficiência a capacidade e lidar com o crescimento inesperado, em qualquer farm, temos a automação que rastreia determinados cenários de uso. Embora o crescimento exato seja imprevisível para qualquer locatário em qualquer farm, a soma agregada de solicitações é previsível ao longo do tempo. Ao identificar as tendências de crescimento no SharePoint Online, podemos planejar a expansão futura. Para obter mais informações sobre [planejamento de capacidade e teste de carga SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).

Uma parte importante de um lançamento bem-sucedido é a abordagem "wave" ou "phased roll-out" detalhada abaixo. 

## <a name="can-i-load-test-sharepoint-online"></a>Posso carregar o teste SharePoint Online?
SharePoint Online é um ambiente compartilhado com vários locatários que é balanceado entre farms e a escala é ajustada de forma contínua. Carregar testes de um ambiente, como SharePoint Online, cuja escala muda continuamente não só lhe dará resultados inesperados, mas não é permitido. 

Saiba mais: [Planejamento de capacidade e teste de carga SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Otimizar páginas seguindo as diretrizes recomendadas
As páginas de uma implantação local não devem ser movidas simplesmente como estão no SharePoint Online sem revisá-las em relação às diretrizes recomendadas para o SharePoint Online. A melhor abordagem é sempre otimizar qualquer home page para qualquer site ou portal no SharePoint, pois é onde a maioria dos usuários em sua organização acessará como ponto de partida para seus sites.

Alguns fatores básicos devem ser considerados:
- As implantações locais podem aproveitar caches tradicionais do lado do servidor, como cache de objeto, cache de saída e cache de blob. Com as diferenças de topologia na nuvem, essas opções não estão necessariamente disponíveis, pois as diferenças de escala significativas as torna menos viáveis.
- Quaisquer páginas / recursos / personalizações usadas para consumo de nuvem devem ser otimizadas para latência mais alta, bem como para os locais distribuídos dos usuários, para que os usuários em áreas ou regiões diferentes tenham uma experiência mais consistente. A nuvem oferece otimizações como redes de entrega de conteúdo (CDN) para otimizar para uma base de usuários distribuídos, bem como para o SharePoint moderno, o último bem conhecido (LKG) é utilizado por nossas Web Parts fora da caixa (OOTB).

### <a name="what-to-do"></a>O que fazer:
 - Para todas as páginas de site no SharePoint Online, use a ferramenta Diagnóstico de Página [,](./page-diagnostics-for-spo.md)que é uma extensão Chromium que ajudará na análise e no fornecimento de orientações. Isso pode ser usado por proprietários de sites, editores, administradores e desenvolvedores, pois foi projetado para ser um ponto de partida para análise e otimização.
 - Os desenvolvedores também devem usar ferramentas de desenvolvimento, como a ferramenta de desenvolvedor do navegador F12, bem como CTRL-F12 no navegador em páginas modernas. [O Fiddler](https://www.telerik.com/download/fiddler) também pode ser usado para revisar o peso do tamanho (o tamanho da página em megabytes) da página e o número de chamadas e elementos que impactam a carga geral da página. 

Esta seção foi um breve resumo para otimizar páginas.  Para saber mais, confira: [Criando, iniciando e mantendo um portal saudável.](/sharepoint/portal-health)

## <a name="follow-a-wave--phased-roll-out-approach"></a>Siga uma abordagem de lançamento wave /phased
A abordagem tradicional do big bang para inícios de site não permitirá a verificação de que personalizações, fontes externas, serviços ou processos foram testados na escala correta. Isso não significa que levará meses para ser lançado, mas é recomendado ao longo de pelo menos vários dias, dependendo do tamanho da sua organização. Seguindo um plano de rolagem de onda, portanto, você tem a opção de pausar e resolver problemas antes de prosseguir com a próxima fase e, portanto, reduz o número potencial de usuários afetados por quaisquer problemas. SharePoint como um serviço dimensiona sua capacidade com base no uso e no uso previsto e, embora não precisemos que você nos notifique sobre seu lançamento, você deve seguir as diretrizes para garantir o sucesso.
  
Como mostrado na imagem a seguir, muitas vezes o número de usuários convidados é significativamente maior do que aqueles que realmente usam o site. Esta imagem mostra uma estratégia sobre como lançar uma versão. Esse método ajuda a identificar maneiras de melhorar SharePoint site antes que a maioria dos usuários o veja.
  
![Gráfico mostrando usuários convidados e ativos](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
Na fase piloto, é bom receber comentários dos usuários em que a organização confia e sabe que estará envolvida. Dessa forma, é possível avaliar como o sistema está sendo usado, bem como como ele está executando.
  
Durante cada uma das ondas, reúna comentários do usuário em torno dos recursos, bem como o desempenho durante cada onda de implantação. Isso tem a vantagem de introduzir lentamente o sistema e fazer melhorias à medida que o sistema obtém mais uso. Isso também nos permite reagir à carga aumentada à medida que o site é lançado para mais e mais usuários e combinado com seguir as diretrizes para otimização de página garante uma experiência positiva para seus usuários.

### <a name="what-to-do"></a>O que fazer:
- Decida o momento de cada fase e verifique se você tem uma oportunidade de contingência/pausa, caso precise fazer ajustes antes de continuar
- Planeje seu primeiro grupo de usuários que você deseja habilitar, para garantir que você receba os comentários necessários para avançar. Isso significa que, sempre que possível, selecione um grupo ativo de usuários que fornecerá comentários em tempo hábil
- Ao planejar cada onda, tente começar com uma pequena base de usuários (menos de 5.000 usuários) e, em seguida, aumente os tamanhos de grupo à medida que você prosseguir com cada onda. Isso ajuda a criar uma abordagem escalonada e permite oportunidades de pausa mais fáceis que podem ser necessárias.