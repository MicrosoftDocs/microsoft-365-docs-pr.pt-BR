---
title: Planejamento de capacidade e teste de carregamento do SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
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
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: Este artigo descreve como você pode implantar no SharePoint Online sem executar testes de carga tradicionais, pois ele não é permitido.
ms.openlocfilehash: a20ed3b5f9b3108d90ec912ec78efa348d4281b1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687364"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Planejamento de capacidade e teste de carregamento do SharePoint Online
Este artigo descreve como você pode implantar no SharePoint Online sem testes de carga tradicionais, pois o teste de carga não é permitido no SharePoint Online. O SharePoint Online é um serviço de nuvem e os recursos de carga, a saúde e o equilíbrio geral da carga no serviço são gerenciados pela Microsoft.
  
A melhor abordagem para garantir o sucesso de iniciar seu site é seguir princípios básicos, práticas e recomendações que são destacados no plano de lançamento da sua lançamento [do portal.](planportallaunchroll-out.md)

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Visão geral de como o SharePoint Online executa o planejamento de capacidade 
Um dos principais benefícios do SharePoint Online em uma implantação local é a elasticidade da nuvem, bem como otimizações para usuários em regiões distribuídas. Nosso ambiente de grande escala é definido para suportar milhões de usuários diariamente, portanto, é importante lidar com a capacidade efetivamente balanceando e expandindo farms.
  
Embora o crescimento geralmente seja imprevisível para qualquer locatário em qualquer farm, a soma agregada de solicitações é previsível ao longo do tempo. Identificando as tendências de crescimento no SharePoint Online, podemos planejar uma expansão futura.
  
Para usar com eficiência a capacidade e lidar com o crescimento inesperado, em qualquer farm, temos automação que rastreia e monitora vários elementos do serviço. Várias métricas são utilizadas, sendo uma das principais a carga da CPU, que é usada como um sinal para dimensionar servidores front-end. Além disso, recomendamos uma abordagem em [fases/onda,](planportallaunchroll-out.md)pois os ambientes SQL serão dimensionados de acordo com a carga e o crescimento ao longo do tempo, e seguir as fases e ondas permite a distribuição correta dessa carga e crescimento. 

A capacidade é mais do que apenas a adição contínua de mais hardware, mas também refere-se ao gerenciamento e controle dessa capacidade para garantir que ela está atendendo a solicitações de carga válidas. Recomendamos que os clientes sigam as orientações recomendadas para garantir que tenham a melhor experiência. Isso também significa que temos padrões e controles de throttling no local para garantir que não permitamos o comportamento "abusivo" no serviço. Embora nem todo o comportamento "ruim" seja intencional, precisamos garantir que limitamos o efeito desse comportamento. Para obter mais informações sobre a aceleração e como evitá-la, consulte o artigo sobre como evitar a aceleração do artigo [de orientação.](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Por que não é possível carregar o SharePoint Online de teste
Com ambientes locais, o teste de carga é usado para validar a suposição de escala e, em última análise, encontrar o ponto de quebra de um farm; saturando-o com carga. 

Com o SharePoint Online, precisamos fazer as coisas de maneira diferente porque a escala é relativamente fluida e ajusta, acelera e controla a carga, com base em determinadas heurísticas. Por sermos um ambiente multi-locatário de grande escala, devemos proteger todos os locatários no mesmo farm, portanto, aceleraremos automaticamente todos os testes de carga. No entanto, se você tentar carregar o teste, além de ser acelerada, receberá resultados enganosos e potencialmente enganosos, pois o farm testado hoje provavelmente terá alterações de escala durante a janela de teste ou dentro de horas após o teste, pois as ações de balanceamento de escala e de farm são executadas de forma contínua.

Em vez de tentar carregar o SharePoint de teste como um serviço, concentre-se em seguir as práticas recomendadas e siga as orientações de [criação,](https://go.microsoft.com/fwlink/?linkid=2105838) lançamento e manutenção de um portal saudável.
