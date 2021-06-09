---
title: Microsoft 365 otimização de desempenho global do locatário para usuários da China
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
description: Este artigo fornece orientações para otimizar o desempenho da rede para usuários da China de locatários de Microsoft 365 globais.
ms.openlocfilehash: f48b552dec72d78e2429aedf6a3834dba6c7590a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844497"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 otimização de desempenho global do locatário para usuários da China

> [!IMPORTANT]
> Essa orientação é específica para cenários de uso nos quais os usuários corporativos Microsoft 365 **localizados** na China se conectam a um **locatário global** Microsoft 365 local. Essa orientação não **se aplica** aos locatários em Office 365 operados pela 21Vianet.

Para empresas com locatários de Microsoft 365 globais e uma presença corporativa na China, o desempenho do cliente Microsoft 365 para usuários baseados na China pode ser complicado por fatores exclusivos da arquitetura da Internet da Telco da China.

Os ISPs da China regulamentaram as conexões no exterior com a Internet pública global que passam por dispositivos de perímetro propensos a altos níveis de congestionamento de rede entre fronteiras. Esse congestionamento cria perda de pacotes e latência para todo o tráfego da Internet que entra e sai da China.

![Microsoft 365 tráfego - não desenvolvido](../media/O365-networking/China-O365-unoptimized.png)

A perda e a latência de pacotes são prejudiciais para o desempenho dos serviços de rede, especialmente os serviços que exigem grandes trocas de dados (como grandes transferências de arquivos) ou que exigem desempenho quase em tempo real (aplicativos de áudio e vídeo).

O objetivo deste tópico é fornecer práticas recomendadas para reduzir o impacto do congestionamento de rede entre fronteiras da China nos serviços Microsoft 365 serviços. Este tópico não aborda outros problemas comuns de desempenho de última milha, como problemas de alta latência de pacotes devido ao roteamento complexo nas operadoras da China.

## <a name="corporate-network-best-practices"></a>Práticas recomendadas de rede corporativa

Muitas empresas com locatários e usuários globais Microsoft 365 na China implementaram redes privadas que transportam o tráfego de rede corporativa entre locais de escritório da China e locais em todo o mundo. Essas empresas podem aproveitar essa infraestrutura de rede para evitar congestionamento de rede entre fronteiras e otimizar o Microsoft 365 de serviço na China.

> [!IMPORTANT]
> Assim como em todas as implementações de WAN privadas, você sempre deve consultar os requisitos regulatórios para seu país e/ou região para garantir que sua configuração de rede está em conformidade.

Como primeira etapa, é fundamental que você siga nossas diretrizes de rede de referência em Planejamento de rede e ajuste [de desempenho para](./network-planning-and-performance.md)Microsoft 365 . O objetivo principal deve ser evitar acessar serviços de Microsoft 365 globais da Internet na China, se possível.

- Aproveite sua rede privada existente para realizar Microsoft 365 de rede entre redes de escritório da China e locais no exterior que egressam na Internet pública fora da China. Quase qualquer local fora da China fornecerá um benefício claro. Os administradores de rede podem otimizar ainda mais a saída em áreas com interconexão de baixa latência com a [rede global da Microsoft.](/azure/networking/microsoft-global-network) Hong Kong, Japão e Coreia do Sul são exemplos.
- Configure os dispositivos de usuário para acessar a rede corporativa por meio de uma conexão VPN para permitir que o tráfego Microsoft 365 transite pelo link privado da rede corporativa. Verifique se os clientes VPN não estão configurados para usar o túnel dividido ou se os dispositivos de usuário estão configurados para ignorar o túnel dividido para Microsoft 365 tráfego. Para obter informações adicionais sobre como otimizar a conectividade VPN para Teams e tráfego de mídia em tempo real, consulte [esta seção](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china).
- Configure sua rede para rotear todo o tráfego Microsoft 365 seu link privado no exterior. Se você tiver que minimizar o volume de tráfego em seu link  particular, poderá optar  por apenas rotear pontos de extremidade na categoria Otimizar e permitir que solicitações para Permitir e **Padrão** pontos de extremidade transitem pela Internet. Isso melhorará o desempenho e minimizará o consumo de largura de banda limitando o tráfego otimizado a serviços críticos que são mais sensíveis à alta latência e à perda de pacotes.
- Se possível, use UDP em vez de TCP para tráfego de streaming de mídia ao vivo, como para Teams. O UDP oferece melhor desempenho de streaming de mídia ao vivo do que TCP.

Para obter informações sobre como rotear seletivamente Microsoft 365 tráfego, consulte [Managing Office 365 endpoints](managing-office-365-endpoints.md). Para ver uma lista de todas as URLs Office 365 e endereços IP em todo o mundo, consulte [Office 365 URLs e intervalos de endereços IP.](urls-and-ip-address-ranges.md)

![Microsoft 365 tráfego - otimizado](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Práticas recomendadas do usuário

Os usuários na China que se conectam a locatários globais de Microsoft 365 de locais remotos, como casas, cafeterias, hoteis e filiais sem conexão com redes corporativas, podem ter um desempenho de rede ruim porque o tráfego entre seus dispositivos e o Microsoft 365 deve transitar pelos circuitos de rede entre fronteiras congestionados da China.

Se o acesso entre redes privadas e/ou VPN entre fronteiras à rede corporativa não for uma opção, os problemas de desempenho por usuário ainda poderão ser atenuados por meio do treinamento de seus usuários baseados na China para seguir essas práticas recomendadas.

- Utilize clientes Office que suportam cache (por exemplo, Outlook, Teams, OneDrive etc.) e evite clientes baseados na Web. Office recursos de cache de cliente e acesso offline podem reduzir drasticamente o impacto do congestionamento e latência da rede.
- Se seu Microsoft 365 locatário tiver sido configurado com o recurso _audioconferência,_ Teams os usuários poderão participar de reuniões por meio da PSTN (rede telefônica pública comutado). Para obter mais informações, consulte [Audioconferência em Office 365](/microsoftteams/audio-conferencing-in-office-365).
- Se os usuários apresentarem problemas de desempenho de rede, eles deverão relatar ao departamento de IT para solução de problemas e escaloná-los para o suporte da Microsoft, caso seja suspeito Microsoft 365 problemas com os serviços de Microsoft 365. Nem todos os problemas são causados pelo desempenho da rede entre fronteiras.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Otimizando o Microsoft Teams de rede de reuniões para usuários na China

Para organizações com locatários globais Microsoft 365 presença na China, Microsoft 365 desempenho do cliente para usuários baseados na China pode ser complicado por fatores exclusivos da arquitetura da Internet da China. Muitas empresas e escolas relataram bons resultados seguindo esta orientação. No entanto, o escopo é limitado a locais de rede do usuário que estão sob controle da configuração de rede de IT, por exemplo, locais do office ou pontos de extremidade home/mobile com conectividade VPN. Microsoft Teams chamadas e reuniões geralmente são usadas de locais externos, como home offices, locais móveis, na estrada e cafeterias. Como as chamadas e reuniões dependem do tráfego de mídia em tempo real, essas Teams experiências são particularmente sensíveis ao congestionamento de rede.

Como resultado, a Microsoft fez uma parceria com provedores de telecomunicações para transportar o tráfego de mídia em tempo real do Teams e do Skype for Business Online usando um caminho de rede preferencial e de alta qualidade entre conexões de internet públicas e domésticas na China e os serviços Teams e Skype na nuvem global Microsoft 365. Essa funcionalidade resultou em uma melhoria de mais de dez vezes na perda de pacotes e em outras métricas importantes que impactam a experiência do usuário.

>[!IMPORTANT]
>Atualmente, essas melhorias não abordam as reuniões do Microsoft Live Events, como grandes reuniões de estilo de transmissão ou "prefeitura" usando Teams ou Microsoft Stream. Para exibir uma reunião de Eventos Ao Vivo, os usuários na China precisam usar uma rede privada ou uma solução SDWAN/VPN. No entanto, as melhorias na rede beneficiarão os usuários que estão apresentando ou produzindo uma reunião do Live Events, pois essa experiência atua como uma reunião Teams regular para o produtor ou apresentador.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Práticas recomendadas de rede da organização para Teams reuniões

Você precisa considerar como aproveitar essas melhorias de rede, já que as diretrizes anteriores para considerar uma extensão de rede privada para evitar congestionamento de rede entre fronteiras. Há duas opções gerais para redes de office da organização:

1. Não faça nada de novo. Continue a seguir as diretrizes anteriores em torno do bypass de rede privada para evitar congestionamento entre fronteiras. Teams tráfego de mídia em tempo real aproveitará essa configuração, como antes.
2. Implemente um padrão dividido/híbrido.
   - Use as diretrizes anteriores para todo o tráfego sinalizado para otimização, exceto Teams reuniões e chamar tráfego de mídia em tempo real.
   - Roteie Teams reunião e chamando tráfego de mídia em tempo real pela Internet pública. Consulte as informações a seguir para obter detalhes sobre como identificar o tráfego de rede de mídia em tempo real.

O envio Teams tráfego de áudio e vídeo de mídia em tempo real pela internet pública, que usa a conectividade de maior qualidade, pode resultar em uma economia considerável de custos, pois é gratuito em vez de pagar para enviar esse tráfego por uma rede privada. Pode haver benefícios adicionais semelhantes se os usuários também estão usando clientes SDWAN ou VPN. Algumas organizações também podem preferir ter mais de seus dados percorrendo conexões públicas da Internet como uma prática geral.

As mesmas opções podem ser aplicadas às configurações do SDWAN ou VPN. Por exemplo, um usuário está usando um SDWAN ou VPN para rotear o tráfego Microsoft 365 para a rede corporativa e, em seguida, aproveitar a extensão privada dessa rede para evitar congestionamento entre fronteiras. O SDWAN ou VPN do usuário agora pode ser configurado para excluir Teams reunião e chamar tráfego em tempo real do roteamento vpn. Essa configuração VPN é chamada de túnel dividido. Consulte [Túnel dividido vpn para obter Office 365](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) para obter mais informações.

Você também pode continuar a usar seu SDWAN ou VPN para todo o tráfego Microsoft 365, incluindo para Microsoft Teams tráfego em tempo real. A Microsoft não tem recomendações sobre o uso de soluções SDWAN ou VPN.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Práticas recomendadas de rede de usuários, móveis e móveis para Teams reuniões

Os usuários na China podem aproveitar essas melhorias simplesmente conectando-se ao serviço público de Internet na China com uma conexão fixa ou móvel. Teams tráfego de áudio e vídeo de mídia em tempo real na internet pública beneficia diretamente da conectividade e da qualidade aprimoradas.

No entanto, os dados de outros serviços Microsoft 365 e outros tráfegos no Teams, como chat ou arquivos, não se beneficiarão diretamente dessas melhorias. Os usuários fora da rede da organização ainda podem ter um desempenho de rede ruim para esse tráfego. Conforme discutido neste artigo, você pode atenuar esses efeitos usando uma VPN ou SDWAN. Você também pode fazer com que seus usuários usem clientes de área de trabalho ricos por meio de clientes Web, que suportam cache no aplicativo para atenuar problemas de rede.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Identificar o Teams de rede de mídia em tempo real

Para configurar um dispositivo de rede ou uma instalação VPN/SDWAN Teams, você precisa excluir apenas o tráfego de áudio e vídeo de mídia em tempo real. Os detalhes do tráfego podem ser encontrados para a ID 11 na lista oficial de URLs Office 365 e [intervalos de endereços IP.](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams) Todas as outras configurações de rede devem permanecer como estão.

A Microsoft está trabalhando continuamente para melhorar Microsoft 365 experiência do usuário e o desempenho dos clientes na mais ampla variedade possível de arquiteturas e características de rede. Visite o [Office 365 do Networking Tech Community](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) iniciar ou participar de uma conversa, encontrar recursos e enviar solicitações e sugestões de recursos

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de rede e ajuste de desempenho para o Microsoft 365](./network-planning-and-performance.md)

[Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[Rede global da Microsoft](/azure/networking/microsoft-global-network)
