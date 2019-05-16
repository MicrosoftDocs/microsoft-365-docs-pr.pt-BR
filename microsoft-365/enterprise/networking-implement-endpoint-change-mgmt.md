---
title: 'Etapa 4: Planejar alterações de endereço IP e URL'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: dacd2ad83bdeb106ae398e8223f457c66a12b598
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073221"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a>Etapa 4: Planejar alterações de endereço IP e URL

*Esta etapa é opcional e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
>Esta etapa requer a [Etapa 3](networking-configure-proxies-firewalls.md). Se você não realizou a etapa 3, prossiga para a [Etapa 5](networking-optimize-tcp-performance.md).
>

As URLs e endereços IP usados pela rede global do Microsoft 365 mudam com o passar do tempo, portanto, é importante planejar as atualizações desses pontos de extremidade. Por exemplo, talvez seja necessário reconfigurar os dispositivos de perímetro de segurança com:

- novas URLs para novos serviços que precisarão de um processamento livre;
- URLs removidas para serviços que não estão mais em uso;
- novos intervalos de endereços IP para novos locais e servidores da rede Microsoft na Internet; 
- alterações nos intervalos de endereços IP para diferentes serviços.

Para saber mais sobre a criação de um plano de implementação para alterações nos pontos de extremidade, que inclui o recebimento de notificações de alterações, consulte as informações sobre como [ gerenciar a integração de pontos de extremidade do Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) e [gerenciar os proxies de ponto de extremidade do Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).

Como ponto de verificação provisório, você pode consultar os [critérios de saída](networking-exit-criteria.md#crit-networking-step4) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Otimizar o desempenho do serviço entre o cliente e o Office 365](networking-optimize-tcp-performance.md)|
