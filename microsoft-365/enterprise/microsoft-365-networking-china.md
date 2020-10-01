---
title: Otimização de desempenho de locatário global do Microsoft 365 para usuários da China
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
- M365initiative-CoreDeploy
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artigo fornece orientações para otimizar o desempenho da rede para usuários da China de locatários do Microsoft 365 global.
ms.openlocfilehash: 1f5f51991c5950d46c9d835a98bea86bcb354366
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327504"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Otimização de desempenho de locatário global do Microsoft 365 para usuários da China

>[!IMPORTANT]
>Esta orientação é específica dos cenários de uso nos quais **os usuários do microsoft 365 Enterprise localizados na China** se conectam a um **locatário global do Microsoft 365**. Este guia não **se aplica** a locatários no Office 365 operado pela 21vianet.

Para empresas com locatários do Microsoft 365 globais e uma presença corporativa na China, o desempenho do cliente da Microsoft 365 para usuários baseados em China pode ser complicado por fatores exclusivos da arquitetura de Internet da Telco da China.

Os ISPs da China têm regulamentados as conexões do exterior à Internet pública global que passam por dispositivos de perímetro que estão sujeitos a altos níveis de congestionamento de rede entre bordas. Esse congestionamento cria perda de pacotes e latência para todo o tráfego da Internet entrando e saindo da China.

![Tráfego Microsoft 365-não otimizado](../media/O365-networking/China-O365-unoptimized.png)

A perda de pacotes e a latência são prejudiciais ao desempenho de serviços de rede, especialmente serviços que exigem grandes trocas de dados (como grandes transferências de arquivos) ou que exigem desempenho quase em tempo real (aplicativos de áudio e vídeo).

O objetivo deste tópico é fornecer práticas recomendadas para reduzir o impacto do congestionamento da rede entre bordas da China nos serviços 365 da Microsoft. Este tópico não aborda outros problemas comuns de desempenho da última vista, como problemas de alta latência de pacote devido ao roteamento complexo dentro de operadoras da China.

## <a name="corporate-network-best-practices"></a>Práticas recomendadas de rede corporativa

Muitas empresas com locatários e usuários globais da Microsoft 365 na China implementaram redes privadas que carregam tráfego de rede corporativa entre escritórios da China e locais do exterior no mundo todo. Essas empresas podem aproveitar essa infraestrutura de rede para evitar o congestionamento de rede entre bordas e otimizar o desempenho do serviço Microsoft 365 na China.

>[!IMPORTANT]
>Assim como ocorre com todas as implementações de WAN privadas, você deve sempre consultar requisitos normativos para o seu país e/ou região para garantir que sua configuração de rede esteja em conformidade.

Como primeira etapa, é crucial que você siga as orientações da nossa rede de benchmark em [planejamento de rede e ajuste de desempenho para o Microsoft 365](https://aka.ms/tune). O objetivo principal deve ser evitar acessar serviços globais da Microsoft 365 da Internet na China, se possível.

- Aproveite a rede privada existente para transportar o tráfego de rede do Microsoft 365 entre as redes do Office da China e locais do exterior que egressom na Internet pública fora da China. Praticamente qualquer local fora da China oferecerá um benefício claro. Os administradores de rede podem otimizar ainda mais por egresso em áreas com interconexão de baixa latência com a [rede global da Microsoft](https://docs.microsoft.com/azure/networking/microsoft-global-network). Hong Kong, Japão e Coréia do Sul são exemplos.
- Configure os dispositivos de usuário para acessar a rede corporativa através de uma conexão VPN para permitir que o tráfego da Microsoft 365 seja transmitido ao link exterior privado da rede corporativa. Verifique se os clientes VPN não estão configurados para usar o túnel de divisão ou se os dispositivos de usuário estão configurados para ignorar o túnel de divisão para o tráfego do Microsoft 365.
- Configure sua rede para rotear todo o tráfego do Microsoft 365 em seu link exterior privado. Se for necessário minimizar o volume de tráfego no seu link privado, você poderá optar por direcionar somente os pontos de extremidade na categoria **otimizar** e permitir que as solicitações para **permitir** e os pontos de extremidade **padrão** sejam de trânsito à Internet. Isso melhorará o desempenho e minimizará o consumo de largura de banda, limitando o tráfego otimizado aos serviços críticos que são mais confidenciais à alta latência e perda de pacotes.
- Se possível, use UDP em vez do TCP para tráfego de fluxo de mídias do Live, como o para Teams. O UDP oferece melhor desempenho de fluxo contínuo de mídia do Live do que o TCP.

Para obter informações sobre como encaminhar seletivamente o tráfego do Microsoft 365, consulte [Managing Office 365 Endpoints](managing-office-365-endpoints.md). Para obter uma lista de todos os endereços IP e URLs do Office 365 em todo o mundo, confira [URLs e intervalos de endereços IP do office 365](urls-and-ip-address-ranges.md).

![Microsoft 365 com otimização de tráfego](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Práticas recomendadas do usuário

Os usuários na China que se conectam aos locatários globais do Microsoft 365 de locais remotos, como residências, lanchonetes, hotéis e filiais sem conexão com redes corporativas podem experimentar um desempenho de rede ruim, pois o tráfego entre seus dispositivos e a Microsoft 365 devem ter circuitos de rede entre bordas congestionadas da China.

Se as redes privadas e/ou o acesso VPN na rede corporativa não forem uma opção, os problemas de desempenho por usuário ainda poderão ser atenuados ao treinar os usuários baseados na China para seguir estas práticas recomendadas.

- Use clientes do Office avançados que oferecem suporte a cache (por exemplo, Outlook, Teams, OneDrive, etc.) e evite clientes baseados na Web. Os recursos de cache de cliente do Office e acesso offline podem reduzir drasticamente o impacto do congestionamento da rede e da latência.
- Se o seu locatário do Microsoft 365 tiver sido configurado com o recurso de _audioconferência_ , os usuários do teams poderão ingressar em reuniões através da rede telefônica pública comutada (PSTN). Para obter mais informações, consulte [audioconferência no Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).
- Se os usuários experimentarem problemas de desempenho de rede, eles deverão relatar ao seu departamento de ti para solução de problemas e escalonar para o suporte da Microsoft se houver suspeita de problemas com os serviços 365 da Microsoft. Nem todos os problemas são causados pelo desempenho da rede entre bordas.

A Microsoft está sempre trabalhando para melhorar a experiência do usuário da Microsoft 365 e o desempenho de clientes sobre a maior variedade possível de arquiteturas e características de rede. Visite a [comunidade de tecnologia do Office 365](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) para iniciar ou ingressar em uma conversa, localizar recursos e enviar solicitações de recurso e sugestões.

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de rede e ajuste de desempenho para o Microsoft 365](https://aka.ms/tune)

[Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[Rede global da Microsoft](https://docs.microsoft.com/azure/networking/microsoft-global-network)
