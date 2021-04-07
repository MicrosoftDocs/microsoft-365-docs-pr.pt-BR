---
title: Otimização de desempenho do locatário global do Microsoft 365 para usuários da China
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artigo fornece orientações para otimizar o desempenho da rede para usuários da China de locatários globais do Microsoft 365.
ms.openlocfilehash: e330e892b584c805bded2228381e74e6a4fa615a
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615190"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Otimização de desempenho do locatário global do Microsoft 365 para usuários da China

>[!IMPORTANT]
>Essa orientação é específica para cenários de uso nos quais os usuários corporativos do **Microsoft 365** localizados na China se conectam a um locatário global do **Microsoft 365**. Essa orientação não **se aplica** aos locatários no Office 365 operados pela 21Vianet.

Para empresas com locatários globais do Microsoft 365 e uma presença corporativa na China, o desempenho do cliente do Microsoft 365 para usuários baseados na China pode ser complicado por fatores exclusivos da arquitetura da Internet da Telco da China.

Os ISPs da China regulamentaram as conexões no exterior com a Internet pública global que passam por dispositivos de perímetro propensos a altos níveis de congestionamento de rede entre fronteiras. Esse congestionamento cria perda de pacotes e latência para todo o tráfego da Internet que entra e sai da China.

![Tráfego do Microsoft 365 - não desenvolvido](../media/O365-networking/China-O365-unoptimized.png)

A perda e a latência de pacotes são prejudiciais para o desempenho dos serviços de rede, especialmente os serviços que exigem grandes trocas de dados (como grandes transferências de arquivos) ou que exigem desempenho quase em tempo real (aplicativos de áudio e vídeo).

O objetivo deste tópico é fornecer práticas recomendadas para reduzir o impacto do congestionamento de rede entre fronteiras da China nos serviços do Microsoft 365. Este tópico não aborda outros problemas comuns de desempenho de última milha, como problemas de alta latência de pacotes devido ao roteamento complexo nas operadoras da China.

## <a name="corporate-network-best-practices"></a>Práticas recomendadas de rede corporativa

Muitas empresas com locatários e usuários globais do Microsoft 365 na China implementaram redes privadas que transportam o tráfego de rede corporativa entre locais de escritório da China e locais no exterior em todo o mundo. Essas empresas podem aproveitar essa infraestrutura de rede para evitar congestionamento de rede entre fronteiras e otimizar o desempenho do serviço do Microsoft 365 na China.

>[!IMPORTANT]
>Assim como em todas as implementações de WAN privadas, você sempre deve consultar os requisitos regulatórios para seu país e/ou região para garantir que sua configuração de rede está em conformidade.

Como primeira etapa, é fundamental que você siga nossas diretrizes de rede de referência em Planejamento de rede e ajuste de [desempenho do Microsoft 365](./network-planning-and-performance.md). O objetivo principal deve ser evitar acessar serviços globais do Microsoft 365 da Internet na China, se possível.

- Aproveite sua rede privada existente para carregar o tráfego de rede do Microsoft 365 entre redes de escritório da China e locais no exterior que egressam na Internet pública fora da China. Quase qualquer local fora da China fornecerá um benefício claro. Os administradores de rede podem otimizar ainda mais a saída em áreas com interconexão de baixa latência com a [rede global da Microsoft.](https://docs.microsoft.com/azure/networking/microsoft-global-network) Hong Kong, Japão e Coreia do Sul são exemplos.
- Configure os dispositivos de usuário para acessar a rede corporativa por meio de uma conexão VPN para permitir que o tráfego do Microsoft 365 transite pelo link privado da rede corporativa. Verifique se os clientes VPN não estão configurados para usar o túnel dividido ou se os dispositivos de usuário estão configurados para ignorar o túnel dividido para o tráfego do Microsoft 365. Para obter informações adicionais sobre como otimizar a conectividade VPN para o Teams e o tráfego de mídia em tempo real, [consulte esta seção](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china).
- Configure sua rede para rotear todo o tráfego do Microsoft 365 em seu link privado no exterior. Se você tiver que minimizar o volume de tráfego em seu link  particular, poderá optar  por apenas rotear pontos de extremidade na categoria Otimizar e permitir que solicitações para Permitir e **Padrão** pontos de extremidade transitem pela Internet. Isso melhorará o desempenho e minimizará o consumo de largura de banda limitando o tráfego otimizado a serviços críticos que são mais sensíveis à alta latência e à perda de pacotes.
- Se possível, use UDP em vez de TCP para tráfego de streaming de mídia ao vivo, como para o Teams. O UDP oferece melhor desempenho de streaming de mídia ao vivo do que TCP.

Para obter informações sobre como rotear seletivamente o tráfego do Microsoft 365, consulte [Managing Office 365 endpoints](managing-office-365-endpoints.md). Para ver uma lista de todas as URLs e endereços IP do Office 365 em todo o mundo, consulte [URLs do Office 365 e intervalos de endereços IP.](urls-and-ip-address-ranges.md)

![Tráfego do Microsoft 365 - otimizado](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Práticas recomendadas do usuário

Os usuários na China que se conectam a locatários globais do Microsoft 365 de locais remotos, como casas, cafeterias, hoteis e filiais sem conexão com redes corporativas, podem ter um desempenho de rede ruim porque o tráfego entre seus dispositivos e o Microsoft 365 deve transitar pelos circuitos de rede entre fronteiras congestionados da China.

Se o acesso entre redes privadas e/ou VPN entre fronteiras à rede corporativa não for uma opção, os problemas de desempenho por usuário ainda poderão ser atenuados por meio do treinamento de seus usuários baseados na China para seguir essas práticas recomendadas.

- Utilize clientes ricos do Office que suportam cache (por exemplo, Outlook, Teams, OneDrive etc.) e evite clientes baseados na Web. Os recursos de cache e acesso offline do cliente do Office podem reduzir drasticamente o impacto do congestionamento e da latência da rede.
- Se o locatário do Microsoft 365 tiver sido configurado com o recurso _audioconferência,_ os usuários do Teams poderão participar de reuniões por meio da PSTN (rede telefônica pública comutado). Para obter mais informações, consulte [Audioconferência no Office 365](/microsoftteams/audio-conferencing-in-office-365).
- Se os usuários apresentarem problemas de desempenho de rede, eles deverão relatar ao departamento de IT para solução de problemas e escalonar para o suporte da Microsoft se for suspeito de problemas com os serviços do Microsoft 365. Nem todos os problemas são causados pelo desempenho da rede entre fronteiras.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Otimizando o desempenho da rede de reuniões do Microsoft Teams para usuários na China  

Para organizações com locatários globais do Microsoft 365 e presença na China, o desempenho do cliente do Microsoft 365 para usuários baseados na China pode ser complicado por fatores exclusivos da arquitetura da Internet da China. Muitas empresas e escolas relataram bons resultados seguindo esta orientação. No entanto, o escopo é limitado a locais de rede do usuário que estão sob controle da configuração de rede de IT, por exemplo, locais do office ou pontos de extremidade home/mobile com conectividade VPN. Chamadas e reuniões do Microsoft Teams geralmente são usadas de locais externos, como home offices, locais móveis, na estrada e cafeterias. Como as chamadas e reuniões dependem do tráfego de mídia em tempo real, essas experiências do Teams são particularmente sensíveis ao congestionamento de rede.

Como resultado, a Microsoft fez uma parceria com provedores de telecomunicações para transportar o tráfego de mídia em tempo real do Teams e do Skype for Business Online usando um caminho de rede preferencial e de alta qualidade entre conexões de internet domésticas e públicas na China e os serviços do Teams e do Skype na nuvem global do Microsoft 365. Essa funcionalidade resultou em uma melhoria de mais de dez vezes na perda de pacotes e em outras métricas importantes que impactam a experiência do usuário.

>[!IMPORTANT]
>Atualmente, essas melhorias não abordam as reuniões do Microsoft Live Events, como grandes reuniões de estilo de transmissão ou "cidade", usando o Teams ou o Microsoft Stream. Para exibir uma reunião de Eventos Ao Vivo, os usuários na China precisam usar uma rede privada ou uma solução SDWAN/VPN. No entanto, as melhorias na rede beneficiarão os usuários que estão apresentando ou produzindo uma reunião do Live Events, pois essa experiência atua como uma reunião regular do Teams para o produtor ou apresentador.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Práticas recomendadas de rede da organização para reuniões do Teams

Você precisa considerar como aproveitar essas melhorias de rede, já que as diretrizes anteriores para considerar uma extensão de rede privada para evitar congestionamento de rede entre fronteiras. Há duas opções gerais para redes de office da organização:

1.  Não faça nada de novo. Continue a seguir as diretrizes anteriores em torno do bypass de rede privada para evitar congestionamento entre fronteiras. O tráfego de mídia em tempo real do Teams aproveitará essa configuração, como antes.
2.  Implemente um padrão dividido/híbrido. 

  - Use as diretrizes anteriores para todo o tráfego sinalizado para otimização, exceto reuniões do Teams e chamada de tráfego de mídia em tempo real.

  - Roteie a reunião do Teams e chamando o tráfego de mídia em tempo real pela Internet pública. Consulte as informações a seguir para obter detalhes sobre como identificar o tráfego de rede de mídia em tempo real.

O envio do tráfego de áudio e vídeo de mídia em tempo real do Teams pela internet pública, que usa a conectividade de maior qualidade, pode resultar em uma economia considerável de custos, pois é gratuito em vez de pagar para enviar esse tráfego por uma rede privada. Pode haver benefícios adicionais semelhantes se os usuários também estão usando clientes SDWAN ou VPN. Algumas organizações também podem preferir ter mais de seus dados percorrendo conexões públicas da Internet como uma prática geral.

As mesmas opções podem ser aplicadas às configurações do SDWAN ou VPN. Por exemplo, um usuário está usando um SDWAN ou VPN para rotear o tráfego do Microsoft 365 para a rede corporativa e, em seguida, aproveitar a extensão privada dessa rede para evitar congestionamento entre fronteiras. O SDWAN ou VPN do usuário agora pode ser configurado para excluir a reunião do Teams e chamar o tráfego em tempo real do roteamento de VPN. Essa configuração VPN é chamada de túnel dividido. Confira [o túnel dividido de VPN para o Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) para obter mais informações.

Você também pode continuar a usar seu SDWAN ou VPN para todo o tráfego do Microsoft 365, inclusive para o tráfego em tempo real do Microsoft Teams. A Microsoft não tem recomendações sobre o uso de soluções SDWAN ou VPN.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Práticas recomendadas de rede de usuários, móveis e móveis para reuniões do Teams

Os usuários na China podem aproveitar essas melhorias simplesmente conectando-se ao serviço público de Internet na China com uma conexão fixa ou móvel. O tráfego de áudio e vídeo de mídia em tempo real do Teams na internet pública beneficia diretamente da conectividade e da qualidade aprimoradas.

No entanto, os dados de outros serviços do Microsoft 365 e outros tráfegos no Teams, como chat ou arquivos, não se beneficiarão diretamente dessas melhorias. Os usuários fora da rede da organização ainda podem ter um desempenho de rede ruim para esse tráfego. Conforme discutido neste artigo, você pode atenuar esses efeitos usando uma VPN ou SDWAN. Você também pode fazer com que seus usuários usem clientes de área de trabalho ricos por meio de clientes Web, que suportam cache no aplicativo para atenuar problemas de rede.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Identificando o tráfego de rede de mídia em tempo real do Teams

Para configurar um dispositivo de rede ou uma configuração VPN/SDWAN, você precisa excluir apenas o tráfego de áudio e vídeo de mídia em tempo real do Teams. Os detalhes do tráfego podem ser encontrados para a ID 11 na lista oficial de [URLs do Office 365 e intervalos de endereços IP.](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) Todas as outras configurações de rede devem permanecer como estão.

A Microsoft está trabalhando continuamente para melhorar a experiência do usuário do Microsoft 365 e o desempenho dos clientes na mais ampla variedade possível de arquiteturas e características de rede. Visite a Comunidade de Tecnologia de Rede do [Office 365]( https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) para iniciar ou participar de uma conversa, encontrar recursos e enviar solicitações e sugestões de recursos

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de rede e ajuste de desempenho para o Microsoft 365](./network-planning-and-performance.md)

[Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[Rede global da Microsoft](/azure/networking/microsoft-global-network)