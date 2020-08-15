---
title: Estratégia de defesa de negação de serviço da Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Neste artigo, você pode encontrar uma visão geral da estratégia de defesa da Microsoft para ataques de negação de serviço (DoS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f28f7bcb9c6241404c8101bffe7268c5a1917ffa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687394"
---
# <a name="microsoft-365-denial-of-service-defense-strategy"></a>Estratégia de defesa de negação de serviço da Microsoft 365

A estratégia da Microsoft para se defender contra ataques de negação de serviço (DoS) baseado em rede é exclusiva devido à nossa escala e ao espaço global. Essa escala permite que a Microsoft use estratégias e técnicas de que poucas organizações, provedores ou organizações de clientes podem ser compatíveis. A base da estratégia de DoS é nossa presença global. A Microsoft se comunica com provedores de Internet, provedores de emparelhamento (públicos e privados) e corporações privadas em todo o mundo. Isso dá à Microsoft uma presença significativa na Internet e permite que a Microsoft absorver ataques em uma grande área de superfície.

Considerando essa natureza exclusiva, a Microsoft usa processos de detecção e mitigação que diferem dos usados por grandes empresas. A estratégia é baseada em uma separação de detecção e redução global distribuída por várias bordas de rede. Muitas empresas usam soluções de terceiros para detectar e reduzir ataques na borda. À medida que a capacidade de borda da Microsoft aumentou, ficou claro o significado de qualquer ataque em relação a bordas individuais ou específicas era baixo. Por causa dessa configuração exclusiva, a Microsoft separou os componentes de detecção e mitigação. A Microsoft implanta sistemas de detecção de várias camadas para detectar ataques mais próximos de seus pontos de saturação, mantendo a redução global na borda. Essa estratégia garante que possamos lidar com vários ataques simultâneos.

Uma das defesas mais eficazes e de baixo custo empregadas pela Microsoft contra ataques de negação de serviço é reduzir as superfícies de ataque. O tráfego indesejado é Descartado na borda da rede em vez de analisar, processar e depurar os dados embutidos.

Na interface com a rede pública, a Microsoft usa dispositivos de segurança de uso especial para firewall, conversão de endereços de rede e funções de filtragem de IP. A Microsoft também usa roteamento global de vários caminhos de custo igual (ECMP). Global ECMP Routing é uma estrutura de rede para garantir que haja vários caminhos globais para chegar a um serviço. Com esses vários caminhos, os ataques contra serviços são limitados à região da qual o ataque se originou. Outras regiões devem ser não afetadas por esse ataque, já que os usuários finais usariam outros caminhos para acessar o serviço nessas regiões. A Microsoft também desenvolveu sistemas de detecção e correlação de DoS internos que usam dados de fluxo, métricas de desempenho e outras informações. Este é um serviço de nuvem de hiperescalas no Microsoft Azure, que analisa dados coletados de vários pontos em redes e serviços da Microsoft. Uma equipe de resposta a incidentes de um entre cargas de trabalho identifica as funções e responsabilidades entre as equipes, os critérios de escalonamento e os protocolos para envolver várias equipes e tratamento de incidentes. Essas soluções fornecem proteção baseada em rede contra ataques de DoS.

Por fim, as cargas de trabalho baseadas em nuvem são configuradas com limites otimizados com base em seu protocolo e uso de largura de banda precisa proteger exclusivamente essa carga de trabalho.
