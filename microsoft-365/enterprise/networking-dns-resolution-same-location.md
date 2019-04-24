---
title: 'Etapa 2: Configurar conexões locais com a Internet para cada escritório'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar a resolução de DNS para obter um melhor desempenho.
ms.openlocfilehash: 6f276bd1fd90b8dee76a0b0d350f256956ded412
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291126"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>Etapa 2: Configurar conexões locais com a Internet para cada escritório

*Esta etapa é obrigatória e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Na Etapa 2, você verifica se cada um dos escritórios tem conexões de Internet locais e usa servidores DNS locais. Esses dois elementos são necessários para reduzir a latência da conexão e garantir que os computadores clientes locais façam conexões com o ponto de entrada mais próximo dos serviços baseados em nuvem do Microsoft 365.

Em redes tradicionais para grandes organizações, o tráfego da Internet percorre o backbone da rede até uma conexão central com a Internet. Isso não funciona bem para otimizar o desempenho para uma infraestrutura de software como serviço (SaaS) globalmente distribuída, que inclui os produtos Office 365 e Enterprise Mobility + Security (EMS) no Microsoft 365.

A Rede Global da Microsoft inclui servidores de front-end para o conjunto de serviços em nuvem do Microsoft 365 em todo o mundo. Para obter o melhor desempenho, os clientes locais devem acessar um servidor de front-end que esteja geograficamente mais próximo deles, em vez de enviar o tráfego por um backbone de rede e ao servidor de front-end mais próximo da conexão central com a Internet da organização.

Para direcionar uma solicitação de cliente ao servidor de front-end geograficamente mais próximo, os servidores DNS da Microsoft usam as consultas DNS correspondentes à solicitação de conexão inicial do cliente. Portanto, para a menor latência de rede mais baixa:

- Todos os escritórios da organização devem ter conexões de Internet locais para o tráfego de rede da categoria [Otimizar](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).
- Cada conexão de Internet local deve estar usando um servidor DNS local regionalmente para o tráfego de saída da Internet desse local.

Para saber mais, confira [Enviar conexões de rede de saída localmente](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally). 

Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step2) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Evitar hairpins de rede](networking-avoid-network-hairpins.md)|
