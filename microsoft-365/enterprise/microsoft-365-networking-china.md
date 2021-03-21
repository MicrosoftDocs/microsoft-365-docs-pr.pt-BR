---
title: Otimização de desempenho do locatário global do Microsoft 365 para usuários da China
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
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
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923189"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Otimização de desempenho do locatário global do Microsoft 365 para usuários da China

>[!IMPORTANT]
>Essa orientação é específica para cenários de uso nos quais os usuários corporativos do **Microsoft 365** localizados na China se conectam a um locatário global do **Microsoft 365**. Essa orientação não **se aplica** aos locatários no Office 365 operados pela 21Vianet.

Para empresas com locatários globais do Microsoft 365 e uma presença corporativa na China, o desempenho do cliente do Microsoft 365 para usuários baseados na China pode ser complicado por fatores exclusivos da arquitetura da Internet da Telco da China.

Os ISPs da China regulamentaram as conexões no exterior com a Internet pública global que passam por dispositivos de perímetro que são propensos a altos níveis de congestionamento de rede entre fronteiras. Esse congestionamento cria perda de pacotes e latência para todo o tráfego da Internet que entra e sai da China.

![Tráfego do Microsoft 365 - não desenvolvido](../media/O365-networking/China-O365-unoptimized.png)

A perda e a latência de pacotes prejudicam o desempenho dos serviços de rede, especialmente os serviços que exigem grandes trocas de dados (como grandes transferências de arquivos) ou que exigem desempenho quase em tempo real (aplicativos de áudio e vídeo).

O objetivo deste tópico é fornecer práticas recomendadas para reduzir o impacto do congestionamento de rede entre fronteiras da China nos serviços do Microsoft 365. Este tópico não aborda outros problemas comuns de desempenho de última milha, como problemas de alta latência de pacotes devido ao roteamento complexo nas operadoras da China.

## <a name="corporate-network-best-practices"></a>Práticas recomendadas de rede corporativa

Muitas empresas com locatários e usuários globais do Microsoft 365 na China implementaram redes privadas que transportam o tráfego de rede corporativa entre locais de escritório da China e locais no exterior em todo o mundo. Essas empresas podem aproveitar essa infraestrutura de rede para evitar congestionamento de rede entre fronteiras e otimizar o desempenho do serviço do Microsoft 365 na China.

>[!IMPORTANT]
>Assim como em todas as implementações de WAN privadas, você sempre deve consultar os requisitos regulatórios para seu país e/ou região para garantir que sua configuração de rede está em conformidade.

Como primeira etapa, é fundamental que você siga nossas diretrizes de rede de referência em Planejamento de rede e ajuste de [desempenho do Microsoft 365](./network-planning-and-performance.md). O objetivo principal deve ser evitar acessar serviços globais do Microsoft 365 da Internet na China, se possível.

- Aproveite sua rede privada existente para carregar o tráfego de rede do Microsoft 365 entre redes de escritório da China e locais no exterior que egressam na Internet pública fora da China. Quase qualquer local fora da China fornecerá um benefício claro. Os administradores de rede podem otimizar ainda mais a saída em áreas com interconexão de baixa latência com a [rede global da Microsoft.](/azure/networking/microsoft-global-network) Hong Kong, Japão e Coreia do Sul são exemplos.
- Configure os dispositivos de usuário para acessar a rede corporativa por meio de uma conexão VPN para permitir que o tráfego do Microsoft 365 transite pelo link privado da rede corporativa. Verifique se os clientes VPN não estão configurados para usar o túnel dividido ou se os dispositivos de usuário estão configurados para ignorar o túnel dividido para o tráfego do Microsoft 365.
- Configure sua rede para rotear todo o tráfego do Microsoft 365 em seu link privado no exterior. Se você tiver que minimizar o volume de tráfego em seu link  particular, poderá optar  por apenas rotear pontos de extremidade na categoria Otimizar e permitir que solicitações para Permitir e **Padrão** pontos de extremidade transitem pela Internet. Isso melhorará o desempenho e minimizará o consumo de largura de banda limitando o tráfego otimizado a serviços críticos que são mais sensíveis à alta latência e à perda de pacotes.
- Se possível, use UDP em vez de TCP para tráfego de streaming de mídia ao vivo, como para o Teams. O UDP oferece melhor desempenho de streaming de mídia ao vivo do que TCP.

Para obter informações sobre como rotear seletivamente o tráfego do Microsoft 365, consulte [Managing Office 365 endpoints](managing-office-365-endpoints.md). Para ver uma lista de todas as URLs e endereços IP do Office 365 em todo o mundo, consulte [URLs do Office 365 e intervalos de endereços IP.](urls-and-ip-address-ranges.md)

![Tráfego do Microsoft 365 - otimizado](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Práticas recomendadas do usuário

Os usuários na China que se conectam a locatários globais do Microsoft 365 de locais remotos, como casas, cafeterias, hoteis e filiais sem conexão com redes corporativas, podem ter um desempenho de rede ruim, pois o tráfego entre seus dispositivos e o Microsoft 365 deve transitar pelos circuitos de rede entre fronteiras congestionados da China.

Se o acesso entre redes privadas e/ou VPN entre fronteiras à rede corporativa não for uma opção, os problemas de desempenho por usuário ainda poderão ser atenuados por meio do treinamento de seus usuários baseados na China para seguir essas práticas recomendadas.

- Utilize clientes ricos do Office que suportam cache (por exemplo, Outlook, Teams, OneDrive etc.) e evite clientes baseados na Web. Os recursos de cache e acesso offline do cliente do Office podem reduzir drasticamente o impacto do congestionamento e da latência da rede.
- Se o locatário do Microsoft 365 tiver sido configurado com o recurso _audioconferência,_ os usuários do Teams poderão participar de reuniões por meio da PSTN (rede telefônica pública comutado). Para obter mais informações, consulte [Audioconferência no Office 365](/microsoftteams/audio-conferencing-in-office-365).
- Se os usuários apresentarem problemas de desempenho de rede, eles deverão relatar ao departamento de IT para solução de problemas e escalonar para o suporte da Microsoft se for suspeito de problemas com os serviços do Microsoft 365. Nem todos os problemas são causados pelo desempenho da rede entre fronteiras.

A Microsoft está trabalhando continuamente para melhorar a experiência do usuário do Microsoft 365 e o desempenho dos clientes na mais ampla variedade possível de arquiteturas e características de rede. Visite a [Comunidade Técnica do Office 365](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) para iniciar ou participar de uma conversa, encontrar recursos e enviar solicitações e sugestões de recursos.

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de rede e ajuste de desempenho para o Microsoft 365](./network-planning-and-performance.md)

[Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[Rede global da Microsoft](/azure/networking/microsoft-global-network)