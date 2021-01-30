---
title: Microsoft 365 Network Insights (visualização)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (visualização)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055468"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (visualização)

**As informações de** rede são métricas de desempenho coletadas do locatário do Microsoft 365 e estão disponíveis somente para exibição por usuários administrativos em seu locatário. Insights são exibidos no Centro de administração do Microsoft 365 em <https://portal.microsoft.com/adminportal/home#/networkperformance> .

As informações se destinam a ajudar a projetar perímetros de rede para seus locais de escritório. Cada insight fornece detalhes ao vivo sobre as características de desempenho de um problema comum específico para cada local geográfico onde os usuários estão acessando seu locatário.

Há seis informações de rede específicas que podem ser mostradas para cada local do escritório:

- [Saída de rede em backhaul](#backhauled-network-egress)
- [Dispositivo intermediário de rede](#network-intermediary-device)
- [Melhor desempenho detectado para clientes próximos a você](#better-performance-detected-for-customers-near-you)
- [Uso de uma porta frontal de serviço do Exchange Online não ideal](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Uso de uma porta frontal de serviço do SharePoint Online não ideal](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Baixa velocidade de download da porta frontal do SharePoint](#low-download-speed-from-sharepoint-front-door)
- [Saída de rede ideal do usuário da China](#china-user-optimal-network-egress)

Há duas percepções de rede no nível do locatário que podem ser mostradas para o locatário. Eles também aparecem nas páginas de pontuação producvitivy:

- [Conexões amostradas do Exchange impactadas por problemas de conectividade](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Conexões amostradas do SharePoint impactadas por problemas de conectividade](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Informações de rede, recomendações de desempenho e avaliações no Centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para locatários do Microsoft 365 que foram inscritos no programa de visualização de recursos.

## <a name="backhauled-network-egress"></a>Saída de rede em backhaul

Esse insight será exibido se o serviço de informações de rede detectar que a distância de um determinado local do usuário até a saída da rede é maior que 500 km (800 km) de distância, indicando que o tráfego do Microsoft 365 está sendo reformulado para um proxy ou dispositivo de borda da Internet comum.

Esse insight é abreviado como "Saída" em algumas exibições resumidas.

![Saída de rede em backhaul](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Cenário

Isso identifica que a distância entre o local do escritório e a saída da rede é de mais de 500 milhas (800 km). O local do escritório é identificado por um local de máquina cliente ofuscado e o local de saída de rede é identificado usando o Endereço IP reverso para os bancos de dados de localização. O local do escritório pode ser impreciso se os Serviços de Localização do Windows estão desabilitados nos computadores. O local de saída de rede pode ser impreciso se as informações do banco de dados de endereço IP reverso não são imprecisas.

Os detalhes desse insight incluem o local do escritório, a porcentagem estimada do total de usuários do locatário no local, o local de saída da rede atual, a relevância do local de saída, a distância entre o local e o ponto de saída atual, a data em que a condição foi detectada pela primeira vez e a data em que a condição foi resolvida.

### <a name="what-should-i-do"></a>O que devo fazer?

Para esse insight, recomendamos que a rede se aproxima do local do escritório para que a conectividade possa ser a melhor rota para a rede global da Microsoft e para a porta de entrada de serviço do Microsoft 365 mais próxima. Ter uma saída de rede próxima aos locais de escritório dos usuários também permite melhorar o desempenho no futuro, à medida que a Microsoft expande os pontos de presença da rede e as portas frontales do serviço do Microsoft 365 no futuro.

Para saber mais sobre como resolver esse problema, confira conexões de rede de Saída [localmente](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) nos Princípios de Conectividade de Rede do [Office 365.](microsoft-365-network-connectivity-principles.md)

## <a name="network-intermediary-device"></a>Dispositivo intermediário de rede

Essa informação será exibida se detectarmos dispositivos entre seus usuários e a rede da Microsoft, o que pode afetar a experiência do usuário do Office 365. É recomendável que eles sejam ignorados para o tráfego de rede específico do Microsoft 365 destinado a datacenters da Microsoft. Essa recomendação também é descrita nos Princípios de Conectividade de Rede do [Microsoft 365](microsoft-365-network-connectivity-principles.md)

### <a name="what-does-this-mean"></a>Cenário

Dispositivos intermediários de rede, como servidores proxy, VPNs e dispositivos de prevenção contra perda de dados, podem afetar o desempenho e a estabilidade dos clientes do Microsoft 365 onde o tráfego está intermediário.

### <a name="what-should-i-do"></a>O que devo fazer?

Configure o dispositivo intermediário de rede detectado para ignorar o processamento do tráfego de rede do Microsoft 365.

## <a name="better-performance-detected-for-customers-near-you"></a>Melhor desempenho detectado para clientes próximos a você

Esse insight será exibido se o serviço de informações de rede detectar que um número significativo de clientes em sua área de transporte tem melhor desempenho do que os usuários em sua organização neste local do escritório.

Esse insight é abreviado como "Pares" em algumas exibições resumidas.

![Desempenho relativo da rede](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Cenário

Este insight examina o desempenho agregado dos clientes do Microsoft 365 na mesma cidade que esse local de escritório. Esse insight será exibido se a latência média de seus usuários for 10% maior do que a latência média de locatários vizinhos.

### <a name="what-should-i-do"></a>O que devo fazer?

Pode haver muitos motivos para essa condição, incluindo latência em sua rede corporativa ou ISP, gargalos ou problemas de design da arquitetura. Examine a latência entre cada salto na rota entre a rede do office e a porta frontal atual do Microsoft 365. Para saber mais, confira Os Princípios de Conectividade de Rede do [Microsoft 365.](microsoft-365-network-connectivity-principles.md)

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Uso de uma porta frontal de serviço do Exchange Online não ideal

Esse insight será exibido se o serviço de informações de rede detectar que os usuários em um local específico não estão se conectando a uma porta frontal de serviço ideal do Exchange Online.

Esse insight é abreviado como "Roteamento" em algumas exibições resumidas.

![Porta frontal EXO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Cenário

Listamos portas frontales de serviço do Exchange Online que são adequadas para uso na cidade do local do escritório com bom desempenho. Se o teste atual mostrar o uso de uma porta frontal de serviço do Exchange Online que não está nessa lista, nós destacamos essa recomendação.

### <a name="what-should-i-do"></a>O que devo fazer?

O uso de uma porta frontal de serviço do Exchange Online que não seja ideal pode ser causado por backhaul de rede antes da saída da rede corporativa. Nesse caso, recomendamos a saída de rede local e direta. Ele também pode ser causado pelo uso de um servidor Resolvedor Recursivo de DNS remoto. Nesse caso, recomendamos alinhar o servidor resolvedor recursivo dns com a saída de rede.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Uso de uma porta frontal de serviço do SharePoint Online não ideal

Esse insight será exibido se o serviço de informações de rede detectar que os usuários em um local específico não estão se conectando à porta de entrada de serviço do SharePoint Online mais próxima.

Esse insight é abreviado como "Afd" em alguns visualizações resumidas.

![Porta frontal do SPO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Cenário

Identificamos a porta de entrada do serviço do SharePoint Online ao qual o cliente de teste está se conectando. Em seguida, para a cidade de localização do escritório, comparamos isso com a porta de frente esperada do serviço do SharePoint Online para essa cidade. Se ele não corresponder, faremos essa recomendação.

### <a name="what-should-i-do"></a>O que devo fazer?

O uso de uma porta frontal de serviço do SharePoint Online que não seja ideal pode ser causado por backhaul de rede antes da saída da rede corporativa. Nesse caso, recomendamos a saída de rede local e direta. Ele também pode ser causado pelo uso de um servidor Resolvedor Recursivo de DNS remoto. Nesse caso, recomendamos alinhar o servidor resolvedor recursivo dns com a saída de rede.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Baixa velocidade de download da porta frontal do SharePoint

Esse insight será exibido se o serviço de informações de rede detectar que a largura de banda entre o local específico do escritório e o SharePoint Online é inferior a 1 MBps.

Esse insight é abreviado como "Produtividade" em algumas exibições resumidas.

### <a name="what-does-this-mean"></a>Cenário

A velocidade de download que um usuário pode obter do SharePoint Online e das portas de serviço do OneDrive for Business é medida em megabytes por segundo (MBps). Se esse valor for menor que 1 MBps, forneceremos esse insight.

### <a name="what-should-i-do"></a>O que devo fazer?

Para melhorar as velocidades de download, a largura de banda pode precisar ser aumentada. Como alternativa, pode haver congestionamento de rede entre os máquinas do usuário no local do escritório e a porta frontal do serviço do SharePoint Online. Isso algumas vezes é chamado de perda congestionada e restringe a velocidade de download disponível para os usuários, mesmo se a largura de banda suficiente estiver disponível.

## <a name="china-user-optimal-network-egress"></a>Saída de rede ideal do usuário da China

Essa informação será exibida se sua organização tiver usuários na China se conectando ao locatário do Microsoft 365 em outras localizações geográficas. 

### <a name="what-does-this-mean"></a>Cenário

Se sua organização tiver conectividade WAN privada, recomendamos configurar um circuito WAN de rede de seus locais de escritório na China que tenha saída de rede para a Internet em qualquer um dos seguintes locais:

- Hong-Kong
- Japão
- Taiwan
- Coreia do Sul
- Cingapura
- Malásia

A saída da Internet mais longe dos usuários do que esses locais reduzirá o desempenho, e a saída na China pode causar problemas de alta latência e conectividade devido ao congestionamento entre fronteiras.

### <a name="what-should-i-do"></a>O que devo fazer?

Para obter mais informações sobre como mitigar problemas de desempenho relacionados a esse insight, consulte a otimização de desempenho do locatário global do [Microsoft 365 para usuários da China.](microsoft-365-networking-china.md)

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Conexões amostradas do Exchange impactadas por problemas de conectividade

Esse insight mostrará quando 50% ou mais das conexões amostradas são impactadas. O impacto é definido pela avaliação do Exchange ser inferior a 60% para cada amostra.

### <a name="what-does-this-mean"></a>Cenário

É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com a conexão do Outlook com o Exchange Online. A porcentagem de amostras provavelmente representa a porcentagem de usuários que aparecem abaixo de 60 pontos.  

### <a name="what-should-i-do"></a>O que devo fazer?

Habilita a visibilidade da conectividade de rede de localização do escritório se você ainda não tiver feito isso. Você deseja identificar quais escritórios são afetados pela conectividade de rede ruim que está afetando o Exchange e encontrar maneiras de melhorar o perímetro de rede em cada um que conecte os usuários à rede da Microsoft.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>Conexões amostradas do SharePoint impactadas por problemas de conectividade

Esse insight mostrará quando 50% ou mais das conexões amostradas são impactadas. O impacto é definido pela avaliação do SharePoint ser inferior a 40% para cada amostra.

### <a name="what-does-this-mean"></a>Cenário

É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com o SharePoint e o OneDrive. A porcentagem de amostras provavelmente representa a porcentagem de usuários que aparecem abaixo de 40 pontos.  

### <a name="what-should-i-do"></a>O que devo fazer?

Habilita a visibilidade da conectividade de rede de localização do escritório se você ainda não tiver feito isso. Você deseja identificar quais escritórios são afetados pela conectividade de rede ruim que está afetando o SharePoint e encontrar maneiras de melhorar o perímetro de rede em cada um que conecte os usuários à rede da Microsoft.

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no Centro de Administração do Microsoft 365 (visualização)](office-365-network-mac-perf-overview.md)

[Avaliação de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-score.md)

[Ferramenta de teste de conectividade de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-onboarding-tool.md)

[Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)](office-365-network-mac-location-services.md)
