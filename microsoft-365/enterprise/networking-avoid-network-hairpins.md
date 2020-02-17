---
title: 'Etapa 3: Evitar hairpins de rede'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e remova hairpins de rede para melhorar o desempenho.
ms.openlocfilehash: f9499fdb8e8c3f7b77e3349d6cc99f6dbf465870
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066698"
---
# <a name="step-3-avoid-network-hairpins"></a>Etapa 3: Evitar hairpins de rede

*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*

![Fase 1 – Rede](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Um [hairpin de rede](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) acontece quando o tráfego vinculado a um destino é direcionado primeiro para outro local intermediário, como uma pilha de segurança local, um agente de acesso à nuvem ou um gateway Web baseado em nuvem. Veja um exemplo.

![Exemplo de um hairpin de rede](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

Um hairpin de rede também pode ser causado por um roteamento insatisfatório na Internet, devido aos provedores de serviços de rede. 

Um hairpin adiciona latência e pode redirecionar o tráfego para um local distante geograficamente.

Para otimizar o desempenho do tráfego para serviços baseados em nuvem do Microsoft 365, verifique se o provedor que fornece a conexão local com a Internet tem um relacionamento de emparelhamento direto com a Rede Global da Microsoft bem próxima a esse local. Essas conexões não possuem hairpins.

Se você usa serviços de rede ou segurança baseados em nuvem para o tráfego do Microsoft 365, certifique-se de que o efeito do hairpin seja avaliado e seu impacto no desempenho seja compreendido. Analise o seguinte:

- O número e a localização dos provedores de serviços através dos quais o tráfego é encaminhado em relação às suas filiais e aos pontos de emparelhamento da Rede Global da Microsoft 
- A qualidade da relação de emparelhamento de rede do provedor de serviços com seu ISP e a Microsoft 
- O impacto no desempenho de backhaul na infraestrutura do provedor de serviços

Sempre que possível, configure seus roteadores de borda para enviar tráfego confiável do Microsoft 365 diretamente, em vez de fazer proxy ou encapsulamento por meio de um fornecedor terceirizado de segurança de rede baseado em nuvem ou na nuvem que processa o tráfego da Internet. 

![Exemplo de um hairpin de rede sendo ignorado](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step3) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![Etapa 4](../media/stepnumbers/Step4.png)|[Configurar o bypass de tráfego](networking-configure-proxies-firewalls.md)|
