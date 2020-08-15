---
title: Mapa de rede para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: O mapa para implementar a rede Microsoft 365.
ms.openlocfilehash: 93d0f253e098815139b431a826f7e5e7a0410b37
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687212"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Mapa de rede para o Microsoft 365

O Microsoft 365 for Enterprise inclui serviços em nuvem de colaboração e produtividade, Microsoft Intune e muitos serviços de identidade e segurança do Microsoft Azure. Todos esses serviços baseados em nuvem dependem da segurança, desempenho e confiabilidade das conexões de dispositivos clientes pela Internet ou circuitos dedicados. Para hospedar esses serviços e disponibilizá-los para clientes em todo o mundo, a Microsoft desenvolveu uma infraestrutura de rede que enfatiza o desempenho e a integração. 

Uma parte crucial da integração do Microsoft 365 é garantir que as conexões de rede e Internet estejam configuradas para acesso otimizado. Configurar sua rede local para acessar uma nuvem de software (SaaS) distribuída globalmente é diferente de uma rede tradicional que é otimizada para o tráfego para os datacenters locais e uma conexão central com a Internet. 

Use estes artigos para entender as principais diferenças e modificar seus dispositivos de borda, computadores clientes e rede local para obter o melhor desempenho para seus usuários locais.

## <a name="plan"></a>Plano

Na fase de planejamento da implementação de sua rede:

- [Entender como funciona a rede Microsoft 365](microsoft-365-networking-overview.md)
- [Avaliar sua conectividade de rede atual](assessing-network-connectivity.md)
- [Determine se o ExpressRoute é ideal para a sua organização](network-planning-with-expressroute.md)
- [Planejar seus dispositivos de rede](plan-for-network-devices.md)
- [Configurar sua rede para migração](network-and-migration-planning.md)

## <a name="deploy"></a>Implantar

Na fase de implantação de sua implementação de rede:

- [Garantir que sua rede corporativa seja otimizada para conectividade Microsoft 365](set-up-network-for-microsoft-365.md)
- [Adicionar os domínios DNS para sua organização](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [Otimize sua conectividade para os pontos de extremidade do Microsoft 365](microsoft-365-ip-web-service.md)
- [Otimizar a conectividade para funcionários remotos](microsoft-365-vpn-split-tunnel.md)
- Se necessário, [Configure o ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>Gerenciar

Na fase de gerenciamento da implementação de sua rede:

- [Verifique se os dispositivos de rede estão usando os pontos de extremidade mais recentes do Office 365](microsoft-365-endpoints.md)
- [Monitorar e ajustar o desempenho da rede](network-planning-and-performance.md)
- [Monitorar suas conexões ExpressRoute](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>Fornecedores de equipamento de rede

Se você for um fornecedor de equipamento de rede, ingresse no programa de parceria de rede [365 da Microsoft](microsoft-365-networking-partner-program.md). Registre-se no programa para criar os princípios de conectividade de rede do Microsoft 365 em seus produtos e soluções. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Como a contoso realizou a rede para o Microsoft 365

Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [otimizou seus dispositivos de rede e conexões com a internet](contoso-networking.md) para os serviços de nuvem do Microsoft 365.

![A Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

Inicie o planejamento de rede com a [visão geral da conectividade de rede do Microsoft 365](microsoft-365-networking-overview.md).
