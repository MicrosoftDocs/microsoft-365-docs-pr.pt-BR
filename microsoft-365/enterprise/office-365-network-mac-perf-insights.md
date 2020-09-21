---
title: Microsoft 365 Network insights (versão prévia)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network insights (versão prévia)
ms.openlocfilehash: 682c888fefb9bec9725e470d62019c857fc2de07
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171333"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network insights (versão prévia)

As **informações de rede** são métricas de desempenho coletadas do seu locatário do Microsoft 365 e disponíveis para visualização apenas por usuários administrativos em seu locatário. As ideias são exibidas no centro de administração do Microsoft 365 em <https://portal.microsoft.com/adminportal/home#/networkperformance> .

As ideias destinam-se a ajudar na criação de perímetros de rede para seus locais do Office. Cada informação fornece detalhes ao vivo sobre as características de desempenho para um problema comum específico para cada localização geográfica onde os usuários acessam seu locatário.

Há seis insights de rede específicos que podem ser mostradas para cada local do escritório:

- [Saída de rede de rebocada](#backhauled-network-egress)
- [Melhor desempenho detectado para clientes próximos de você](#better-performance-detected-for-customers-near-you)
- [Uso de uma porta frontal de serviço do Exchange Online não ideal](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Uso de uma porta frontal não ideal do SharePoint Online Service](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Baixa velocidade de download da porta frontal do SharePoint](#low-download-speed-from-sharepoint-front-door)
- [Saída de rede ideal para o usuário da China](#china-user-optimal-network-egress)

Há dois insights de rede de nível de locatário que podem ser mostrados para o locatário. Eles também aparecem nas páginas de Pontuação producvitivy:

- [Conexões de amostra do Exchange impactadas por problemas de conectividade](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Exemplos de conexões do SharePoint impactadas por problemas de conectividade](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Os insights de rede, as recomendações de desempenho e as avaliações no centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para os locatários do Microsoft 365 que foram registrados no programa de visualização de recurso.

## <a name="backhauled-network-egress"></a>Saída de rede de rebocada

Esta percepção será exibida se o serviço de insights de rede detectar que a distância de um determinado local de usuário para a saída da rede é maior que 500 milhas (800 quilômetros), indicando que o tráfego da Microsoft 365 está sendo repassado para um dispositivo ou proxy de borda Internet comum.

Esta percepção é abreviada como "egresso" em alguns modos de exibição de resumo.

![Saída de rede de rebocada](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Cenário

Isso identifica que a distância entre o local do escritório e a egresso da rede é maior que 500 milhas (800 quilômetros). O local do Office é identificado por um local de máquina cliente ofuscado e o local de egresso de rede é identificado usando o endereço IP reverso para os bancos de dados de local. O local do escritório pode ser impreciso se os serviços de localização do Windows estiverem desabilitados nos computadores. O local de egresso de rede pode ser impreciso se as informações do banco de dados de endereço IP reverso não forem precisas.

Os detalhes desta percepção incluem o local do escritório, porcentagem estimada do usuário do locatário total no local, o local de egresso da rede atual, relevância do local de egresso, a distância entre o local e o ponto de saída atual, a data em que a condição foi detectada pela primeira vez e a data em que a condição foi resolvida.

### <a name="what-should-i-do"></a>O que devo fazer?

Para esta percepção, recomendamos que a saída da rede fique mais próxima do local do escritório, para que a conectividade possa ser roteada de maneira ideal para a rede global da Microsoft e para a porta mais próxima do serviço do Microsoft 365. Após o fechamento de egresso da rede para usuários, os locais do Office também permitem um desempenho aprimorado no futuro, já que a Microsoft expande tanto os pontos de presença de rede quanto as portas frontais de serviço do Microsoft 365 no futuro.

Para obter mais informações sobre como resolver esse problema, confira [conexões de rede de saída localmente](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) nos [princípios de conectividade de rede do Office 365](microsoft-365-network-connectivity-principles.md).

## <a name="better-performance-detected-for-customers-near-you"></a>Melhor desempenho detectado para clientes próximos de você

Esta percepção será exibida se o serviço de insights de rede detectar que um número significativo de clientes em sua área de metrô tem melhor desempenho do que os usuários em sua organização nesse local do escritório.

Esta percepção é abreviada como "pares" em alguns modos de exibição de resumo.

![Desempenho de rede relativo](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Cenário

Essa percepção examina o desempenho agregado dos clientes do Microsoft 365 na mesma cidade que este local do escritório. Esta percepção será exibida se a latência média de seus usuários for 10% maior do que a latência média dos locatários vizinhos.

### <a name="what-should-i-do"></a>O que devo fazer?

Pode haver vários motivos para esta condição, incluindo latência na rede corporativa ou no provedor de Internet, afunilamentos ou problemas de design de arquitetura. Examine a latência entre cada salto na rota entre a rede do Office e a porta frontal do Microsoft 365 atual. Para obter mais informações, consulte [princípios de conectividade de rede do Office 365](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Uso de uma porta frontal de serviço do Exchange Online não ideal

Esta percepção será exibida se o serviço de insights de rede detectar que os usuários em um local específico não estão se conectando a uma porta de entrada ideal do Exchange Online Service.

Esta percepção é abreviada como "roteamento" em alguns modos de exibição de resumo.

![Porta frontal EXO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Cenário

Listamos as portas frontais do serviço do Exchange Online que são adequadas para uso da cidade de local do escritório com bom desempenho. Se o teste atual mostrar o uso de uma porta frontal do serviço do Exchange Online que não está nessa lista, chamamos essa recomendação.

### <a name="what-should-i-do"></a>O que devo fazer?

O uso de uma porta de entrada de serviço do Exchange Online não ideal pode ser causado pelo backhaul de rede antes da saída da rede corporativa, caso recomendamos a saída de rede local e direta. Também pode ser causado pelo uso de um servidor de resolvedor de DNS recursivo remoto, caso recomendamos alinhar o servidor do resolvedor de DNS recursivo com a saída da rede.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Uso de uma porta frontal não ideal do SharePoint Online Service

Esta percepção será exibida se o serviço de insights de rede detectar que os usuários em um local específico não estão se conectando à porta frontal mais próxima do SharePoint Online Service.

Esta percepção é abreviada como "AFD" em alguns modos de exibição de resumo.

![Porta frontal SPO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Cenário

Identificamos a porta frontal do serviço do SharePoint Online à qual o cliente de teste está se conectando. Em seguida, para a cidade do local do escritório, comparamos isso à porta frontal do serviço do SharePoint Online esperado para essa cidade. Se não coincidir, fazemos essa recomendação.

### <a name="what-should-i-do"></a>O que devo fazer?

O uso de uma porta de entrada de serviço do SharePoint Online não ideal pode ser causado pelo backhaul de rede antes da saída da rede corporativa, caso recomendamos a saída de rede local e direta. Também pode ser causado pelo uso de um servidor de resolvedor de DNS recursivo remoto, caso recomendamos alinhar o servidor do resolvedor de DNS recursivo com a saída da rede.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Baixa velocidade de download da porta frontal do SharePoint

Esta percepção será exibida se o serviço de insights de rede detectar essa largura de banda entre o local específico do Office e o SharePoint Online for menor que 1 MBps.

Esta percepção é abreviada como "throughput" em alguns modos de exibição de resumo.

### <a name="what-does-this-mean"></a>Cenário

A velocidade de download que um usuário pode obter do SharePoint Online e do OneDrive for Business Service Doors é medida em megabytes por segundo (MBps). Se esse valor for menor que 1 MBps, forneceremos esta percepção.

### <a name="what-should-i-do"></a>O que devo fazer?

Para melhorar as velocidades de download, a largura de banda pode precisar ser aumentada. Como alternativa, pode haver congestionamento de rede entre máquinas de usuário no local do escritório e na porta frontal do serviço do SharePoint Online. Isso às vezes é chamado de perda congestionada e restringe a velocidade de download disponível para os usuários, mesmo se houver largura de banda suficiente disponível.

## <a name="china-user-optimal-network-egress"></a>Saída de rede ideal para o usuário da China

Esta percepção será exibida se sua organização tiver usuários na China se conectarem ao seu locatário do Microsoft 365 em outros locais geográficos. 

### <a name="what-does-this-mean"></a>Cenário

Se sua organização tem conectividade de WAN privada, recomendamos configurar um circuito de WAN de rede de seus locais do Office na China que têm a saída da rede para a Internet em qualquer um dos seguintes locais:

- Hong Kong
- Japão
- Taiwan
- Coreia do Sul
- Cingapura
- Malásia

O egresso de Internet mais distante dos usuários do que esses locais reduzirá o desempenho e o egresso na China pode causar problemas de alta latência e conectividade devido a um congestionamento entre bordas.

### <a name="what-should-i-do"></a>O que devo fazer?

Para obter mais informações sobre como reduzir problemas de desempenho relacionados a essa percepção, consulte [Office 365 global locatário Performance Optimization for China Users](microsoft-365-networking-china.md).

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Conexões de amostra do Exchange impactadas por problemas de conectividade

Esta percepção mostrará quando 50% ou mais das conexões de amostra são impactadas. O impacto é definido pela avaliação do Exchange abaixo de 60% para cada exemplo.

### <a name="what-does-this-mean"></a>Cenário

É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com o Outlook se conectando ao Exchange Online. A porcentagem de amostras provavelmente representa a porcentagem de usuários que mostram abaixo de 60 pontos.  

### <a name="what-should-i-do"></a>O que devo fazer?

Habilitar a visibilidade da conectividade de rede do Office local, se você ainda não tiver feito isso. Você deseja identificar quais escritórios são impactados pela baixa conectividade de rede que está afetando o Exchange e encontre maneiras de melhorar o perímetro de rede em cada um que conecte os usuários à rede da Microsoft.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>Exemplos de conexões do SharePoint impactadas por problemas de conectividade

Esta percepção mostrará quando 50% ou mais das conexões de amostra são impactadas. O impacto é definido pela avaliação do SharePoint que está abaixo de 40% para cada exemplo.

### <a name="what-does-this-mean"></a>Cenário

É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com o SharePoint e o OneDrive. A porcentagem de amostras provavelmente representa a porcentagem de usuários que mostram abaixo de 40 pontos.  

### <a name="what-should-i-do"></a>O que devo fazer?

Habilitar a visibilidade da conectividade de rede do Office local, se você ainda não tiver feito isso. Você deseja identificar quais escritórios são impactados pela baixa conectividade de rede que está afetando o SharePoint e encontre maneiras de melhorar o perímetro de rede em cada um que conecte os usuários à rede da Microsoft.

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no centro de administração do Microsoft 365 (versão prévia)](office-365-network-mac-perf-overview.md)

[Avaliação de rede do Microsoft 365 (versão prévia)](office-365-network-mac-perf-score.md)

[Ferramenta de teste de conectividade de rede 365 da Microsoft (versão prévia)](office-365-network-mac-perf-onboarding-tool.md)

[Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)](office-365-network-mac-location-services.md)
