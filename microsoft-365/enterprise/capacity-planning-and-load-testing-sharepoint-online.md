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
description: Este artigo descreve como você pode implantar no SharePoint Online sem executar testes de carga tradicionais, já que não é permitido.
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905219"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Planejamento de capacidade e teste de carregamento do SharePoint Online
Este artigo descreve como você pode implantar no SharePoint Online sem testes de carga tradicionais, já que o teste de carga não é permitido no SharePoint Online. SharePoint Online é um serviço de nuvem e os recursos de carga, a saúde e o equilíbrio geral de carga no serviço são gerenciados pela Microsoft.
  
A melhor abordagem para garantir o sucesso de iniciar seu site é seguir princípios básicos, práticas e recomendações que são realçadas no plano de lançamento do [seu portal.](planportallaunchroll-out.md)

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Visão geral de como SharePoint Online executa o planejamento de capacidade 
Um dos principais benefícios do SharePoint Online em uma implantação local é a elasticidade da nuvem, bem como otimizações para usuários em regiões distribuídas. Nosso ambiente de grande escala é definido para ajudar milhões de usuários diariamente, portanto, é importante lidar com a capacidade efetivamente equilibrando e expandindo farms.
  
Embora o crescimento geralmente seja imprevisível para qualquer locatário em qualquer farm, a soma agregada de solicitações é previsível ao longo do tempo. Ao identificar as tendências de crescimento no SharePoint Online, podemos planejar a expansão futura.
  
Para usar com eficiência a capacidade e lidar com o crescimento inesperado, em qualquer farm, temos a automação que rastreia e monitora vários elementos do serviço. Várias métricas são usadas, com uma das principais sendo a carga da CPU, que é usada como um sinal para dimensionar servidores front-end. Além disso, recomendamos uma abordagem em [fases/onda,](planportallaunchroll-out.md)pois os ambientes SQL serão dimensionados de acordo com a carga e o crescimento ao longo do tempo, e seguir as fases e ondas permite a distribuição correta dessa carga e crescimento. 

A capacidade é mais do que apenas adicionar mais hardware em uma base contínua, mas também pertence ao gerenciamento e ao controle dessa capacidade para garantir que ele está atendendo a solicitações de carga válidas. Recomendamos que os clientes sigam as diretrizes recomendadas para garantir que eles tenham a melhor experiência. Isso também significa que temos padrões e controles de coação no local para garantir que não permitamos comportamentos "abusivos" no serviço. Embora nem todo o comportamento "ruim" seja intencional, precisamos garantir que limitemos o efeito desse comportamento. Para obter mais informações sobre a aceleração e como evitá-la, consulte o artigo sobre como evitar a aceleração [do](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) artigo de orientação.

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Por que você não pode carregar o teste SharePoint Online
Com ambientes locais, o teste de carga é usado para validar a suposição de escala e, em última análise, encontrar o ponto de quebra de um farm; saturando-o com carga. 

Com SharePoint Online, precisamos fazer as coisas de forma diferente porque a escala é relativamente fluida e ajusta, acelera e controla a carga, com base em determinada heurística. Sendo um ambiente de vários locatários em grande escala, devemos proteger todos os locatários no mesmo farm, portanto, vamos acelerar automaticamente todos os testes de carga. No entanto, se você tentar carregar o teste, além de ser acelerada, receberá resultados frustrantes e possivelmente enganosos, pois o farm testado hoje provavelmente terá alterações de escala durante a janela de teste ou horas após o teste, pois as ações de balanceamento de escala e de farm são executadas de forma contínua.

Em vez de tentar carregar o teste SharePoint como um serviço, concentre-se em seguir as práticas recomendadas e siga as diretrizes [Criar,](/sharepoint/portal-health) iniciar e manter um portal saudável.