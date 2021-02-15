---
title: Otimização de desempenho global do locatário do Microsoft 365 para usuários da China
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
- m365initiative-coredeploy
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artigo fornece orientações para otimizar o desempenho de rede para usuários da China de locatários globais do Microsoft 365.
ms.openlocfilehash: 9b397e60b4a3b80563ed31731a6f7aa8e0bdab7f
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456358"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Otimização de desempenho global do locatário do Microsoft 365 para usuários da China

>[!IMPORTANT]
>Essa orientação é específica para cenários de uso em que os usuários corporativos do **Microsoft 365** localizados na China se conectam a um locatário global do **Microsoft 365.** Essas diretrizes não **se aplicam** a locatários no Office 365 operado pela 21Vianet.

Para empresas com locatários globais do Microsoft 365 e uma presença corporativa na China, o desempenho do cliente do Microsoft 365 para usuários baseados na China pode ser complicado por fatores exclusivos da arquitetura de Internet da Telco da China.

Os ISPs da China têm conexões regulares com a Internet pública global que passam por dispositivos de perímetro sujeitos a altos níveis de congestionamento de rede entre fronteiras. Esse congestionamento cria perda de pacotes e latência para todo o tráfego de Internet que entra e sai da China.

![Tráfego do Microsoft 365 - não personalizado](../media/O365-networking/China-O365-unoptimized.png)

A perda de pacotes e a latência são prejudiciais ao desempenho dos serviços de rede, especialmente serviços que exigem grandes trocas de dados (como transferências de arquivos grandes) ou que exigem desempenho quase em tempo real (aplicativos de áudio e vídeo).

O objetivo deste tópico é fornecer práticas recomendadas para reduzir o impacto do congestionamento de rede entre fronteiras da China nos serviços do Microsoft 365. Este tópico não aborda outros problemas comuns de desempenho de última milha, como problemas de alta latência de pacotes devido ao roteamento complexo nas operadoras da China.

## <a name="corporate-network-best-practices"></a>Práticas recomendadas de rede corporativa

Muitas empresas com locatários globais do Microsoft 365 e usuários na China implementaram redes privadas que transportam o tráfego de rede corporativa entre locais de escritório da China e locais diferentes em todo o mundo. Essas empresas podem aproveitar essa infraestrutura de rede para evitar congestionamento de rede entre borda e otimizar o desempenho do serviço do Microsoft 365 na China.

>[!IMPORTANT]
>Assim como em todas as implementações de WAN privadas, você deve sempre consultar os requisitos regulatórios do seu país e/ou região para garantir que sua configuração de rede está em conformidade.

Como primeira etapa, é fundamental que você siga nossas diretrizes de rede de parâmetros de comparação no planejamento de rede e ajuste de desempenho do [Microsoft 365.](https://aka.ms/tune) O objetivo principal deve ser evitar o acesso a serviços globais do Microsoft 365 da Internet na China, se possível.

- Aproveite sua rede privada existente para transportar o tráfego de rede do Microsoft 365 entre redes de escritório da China e locais de saída na Internet pública fora da China. Quase qualquer local fora da China fornecerá um benefício claro. Os administradores de rede podem otimizar ainda mais egressando em áreas com interconexão de baixa latência com a [rede global da Microsoft.](https://docs.microsoft.com/azure/networking/microsoft-global-network) Hong Kong, Japão e Coreia do Sul são exemplos.
- Configure os dispositivos do usuário para acessar a rede corporativa por meio de uma conexão VPN para permitir que o tráfego do Microsoft 365 transite pelo link privado da rede corporativa. Verifique se os clientes VPN não estão configurados para usar o túnel dividido ou se os dispositivos do usuário estão configurados para ignorar o túnel dividido para o tráfego do Microsoft 365.
- Configure sua rede para rotear todo o tráfego do Microsoft 365 através do link privado do seu site. Se for necessário minimizar o volume de tráfego no link privado, você poderá optar por  encaminhar  apenas os pontos de extremidade na categoria Otimizar e permitir que as solicitações para os pontos de extremidade Permitir e Padrão transitem pela Internet.  Isso melhorará o desempenho e minimizará o consumo de largura de banda limitando o tráfego otimizado a serviços críticos mais sensíveis à alta latência e à perda de pacotes.
- Se possível, use UDP em vez de TCP para tráfego de streaming de mídia ao vivo, como para o Teams. O UDP oferece melhor desempenho de streaming de mídia ao vivo do que o TCP.

Para saber mais sobre como rotear seletivamente o tráfego do Microsoft 365, confira Gerenciar pontos de extremidade do [Office 365.](managing-office-365-endpoints.md) Para ver uma lista de todas as URLs e endereços IP do Office 365 em todo o mundo, confira URLs e intervalos de [endereços IP do Office 365.](urls-and-ip-address-ranges.md)

![Tráfego do Microsoft 365 - otimizado](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Práticas recomendadas para o usuário

Os usuários na China que se conectam a locatários globais do Microsoft 365 de locais remotos, como casas, cafeterias, cafeterias e filiais sem conexão com redes corporativas, podem ter um desempenho de rede ruim porque o tráfego entre seus dispositivos e o Microsoft 365 deve transitar pelos circuitos de rede entre borda congestionados da China.

Se redes privadas entre borda e/ou acesso VPN na rede corporativa não for uma opção, os problemas de desempenho por usuário ainda poderão ser atenuados com o treinamento dos usuários baseados na China para seguir estas práticas recomendadas.

- Utilize clientes do Office ricos que suportam cache (por exemplo, Outlook, Teams, OneDrive etc.) e evite clientes baseados na Web. O cache do cliente do Office e os recursos de acesso offline podem reduzir drasticamente o impacto do congestionamento e da latência da rede.
- Se o locatário do Microsoft 365 tiver sido configurado com o recurso de Audioconferência, os usuários do Teams poderão participar de reuniões por meio da PSTN (rede telefônica pública comutado).  Para saber mais, confira [Audioconferência no Office 365.](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)
- Se os usuários têm problemas de desempenho de rede, eles devem relatar ao departamento de IT para solução de problemas e escalonar para o suporte da Microsoft se há problemas com os serviços do Microsoft 365. Nem todos os problemas são causados pelo desempenho de rede entre borda.

A Microsoft está trabalhando continuamente para melhorar a experiência do usuário do Microsoft 365 e o desempenho dos clientes na mais ampla variedade possível de arquiteturas e características de rede. Visite a [Comunidade Técnica do Office 365](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) para iniciar ou participar de uma conversa, encontrar recursos e enviar sugestões e solicitações de recursos.

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de rede e ajuste de desempenho para o Microsoft 365](https://aka.ms/tune)

[Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[Rede global da Microsoft](https://docs.microsoft.com/azure/networking/microsoft-global-network)
