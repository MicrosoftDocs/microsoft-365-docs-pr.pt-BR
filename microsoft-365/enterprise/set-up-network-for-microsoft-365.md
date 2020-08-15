---
title: Configurar sua rede para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Encontre links para artigos com informações para ajudá-lo a configurar sua rede para o Microsoft 365, incluindo uma visão geral da conectividade de rede e uma lista de pontos de extremidade.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686976"
---
# <a name="set-up-your-network-for-microsoft-365"></a>Configurar sua rede para o Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Uma parte importante da integração com o Microsoft 365 é garantir que as conexões de rede e Internet sejam configuradas para acesso otimizado. Configurar sua rede local para acessar uma nuvem de software (SaaS) distribuída globalmente é diferente de uma rede tradicional que é otimizada para o tráfego para os datacenters locais e uma conexão central com a Internet. 

Use estes artigos para entender as principais diferenças e modificar seus dispositivos de borda, computadores clientes e rede local para obter o melhor desempenho para seus usuários locais.

## <a name="how-microsoft-365-networking-works"></a>Como funciona a rede Microsoft 365

Consulte estes artigos para obter uma visão geral da conectividade do Microsoft 365:

- [Visão geral da conectividade de rede do Microsoft 365](microsoft-365-networking-overview.md)
- [Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md)
- [Avaliando a conectividade de rede do Microsoft 365](assessing-network-connectivity.md)

Para obter conselhos sobre como melhorar o desempenho, consulte [planejamento de rede e ajuste de desempenho para o Microsoft 365](network-planning-and-performance.md).

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a>Suporte para redes Microsoft 365 como um fornecedor de equipamento de rede

Se você é um fornecedor de equipamentos de rede, junte-se ao [Programa de Parceiros de Rede do Office 365](microsoft-365-networking-partner-program.md). Inscreva-se no programa para integrar princípios de conectividade de rede do Office 365 aos seus produtos e soluções. 

## <a name="office-365-endpoints"></a>Pontos de extremidade do Office 365

Pontos de extremidade são o conjunto de endereços IP de destino, nomes de domínio do DNS e URLs do tráfego do Office 365 na Internet. 

Para otimizar o desempenho dos serviços baseados em nuvem do Office 365, alguns pontos de extremidade precisam de tratamento especial pelos navegadores clientes e pelos dispositivos da rede de borda. Esses dispositivos incluem firewalls, SSL Break and Inspect e dispositivos de inspeção de pacotes e sistemas de prevenção de perda de dados.

Confira [Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md) para saber mais.

Atualmente, há cinco nuvens diferentes do Office 365. Esta tabela leva você à lista de pontos de extremidade de cada um deles.

| Pontos de extremidade | Descrição |
|:-------|:-----|
| [Pontos de extremidade mundiais](urls-and-ip-address-ranges.md) | Os pontos de extremidade das assinaturas do Office 365 em todo o mundo, que incluem a United States Government Community Cloud (GCC). |
| [Pontos de extremidade do US Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | Os pontos de extremidade das assinaturas do Departamento de Defesa dos Estados Unidos (DoD). |
| [Pontos de extremidade do US Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) | Os pontos de extremidade das assinaturas da United States Government Community Cloud High (GCC alto). |
| [Pontos de extremidade do Office 365 operado pela 21Vianet](urls-and-ip-address-ranges-21vianet.md) | Os pontos de extremidade do Office 365 operado pela 21Vianet, que são projetados para atender às necessidades do Office 365 na China. |
| [Pontos de extremidade do Office 365 Germany](microsoft-365-germany-endpoints.md) | Os pontos de extremidade uma nuvem separada na Europa para a maioria dos clientes regulamentados na Alemanha, União Europeia (UE) e Associação Europeia de Livre Comércio (EFTA). |
|||

Para obter automaticamente a lista mais recente de pontos de extremidade de sua nuvem do Office 365, confira o [Serviços de Endereços IP e URLs da Web do Office 365](microsoft-365-ip-web-service.md).

Para pontos de extremidade adicionais, confira estes artigos:

- [Pontos de extremidade adicionais não incluídos nos serviços Web](additional-office365-ip-addresses-and-urls.md)
- [Solicitações de rede do Office 2016 para Mac](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a>Tópicos adicionais para a rede 365 da Microsoft

Consulte estes artigos sobre tópicos especializados na rede Microsoft 365:

- [Redes de distribuição de conteúdo](content-delivery-networks.md)
- [Suporte a IPv6 nos serviços do Office 365](ipv6-support.md)
- [Suporte a NAT com o Office 365](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a>ExpressRoute para o Microsoft 365

Confira estes artigos para obter informações sobre o uso do ExpressRoute para tráfego do Office 365:

- [Microsoft Azure ExpressRoute para Office 365](azure-expressroute.md)
- [Como implementar o ExpressRoute para Office 365](implementing-expressroute.md)
- [Planejamento de rede com o ExpressRoute para Office 365](network-planning-with-expressroute.md)
- [Como rotear com o ExpressRoute para Office 365](routing-with-expressroute.md)
