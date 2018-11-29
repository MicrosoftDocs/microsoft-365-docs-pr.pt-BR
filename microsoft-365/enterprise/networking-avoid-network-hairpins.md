---
title: 'Etapa 3: Evitar hairpins de rede'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e remova hairpins de rede para melhorar o desempenho.
ms.openlocfilehash: 7277b8f5c07bc156599f946e032c3345da3316e9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865318"
---
# <a name="step-3-avoid-network-hairpins"></a>Etapa 3: Evitar hairpins de rede

*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Um [hairpin de rede](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) ocorre quando o tráfego vinculado a um destino é direcionado primeiro para outro local intermediário, como uma pilha de segurança local, um agente de acesso à nuvem ou um gateway da Web baseado em nuvem. Um hairpin de rede também pode ser causado por mau roteamento na Internet devido a provedores de serviços de rede. O hairpin adiciona latência e pode redirecionar potencialmente o tráfego para um local geograficamente distante.

Para otimizar o desempenho do tráfego para serviços baseados em nuvem do Microsoft 365, verifique se o provedor que fornece a conexão local com a Internet tem um relacionamento de emparelhamento direto com a Rede Global da Microsoft bem próxima a esse local. Essas conexões não possuem hairpins.

Se você usa serviços de rede ou segurança baseados em nuvem para o tráfego do Microsoft 365, certifique-se de que o efeito do hairpin seja avaliado e seu impacto no desempenho seja compreendido. Analise o seguinte:

- O número e a localização dos provedores de serviços através dos quais o tráfego é encaminhado em relação às suas filiais e aos pontos de emparelhamento da Rede Global da Microsoft 
- A qualidade da relação de emparelhamento de rede do provedor de serviços com seu ISP e a Microsoft 
- O impacto no desempenho de backhaul na infraestrutura do provedor de serviços

Sempre que possível, configure seus roteadores de borda para enviar tráfego confiável do Microsoft 365 diretamente, em vez de fazer proxy ou encapsulamento por meio de um fornecedor terceirizado de segurança de rede baseado em nuvem ou na nuvem que processa o tráfego da Internet. 

Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step3) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[Configurar o bypass de tráfego](networking-configure-proxies-firewalls.md)|
