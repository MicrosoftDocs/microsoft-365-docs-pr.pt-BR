---
title: 'Etapa 5: Otimizar o desempenho do serviço do Office 365 com o cliente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Definir as configurações de TCP e os serviços do Office 365 para melhorar o desempenho.
ms.openlocfilehash: 9e786b36d7a2afccc3b9112b815cd42a40317c15
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073181"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Etapa 5: Otimizar o desempenho do serviço do Office 365 com o cliente

*Esta etapa é opcional e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Você pode aumentar o desempenho ao ajustar a forma como o Protocolo de Controle de Transmissão (TCP) funciona entre dispositivos-cliente e os serviços do Office 365.

Para dispositivos-cliente, você pode alterar as seguintes configurações do TCP em dispositivos-cliente para otimizar o desempenho do TCP:

- [Dimensionamento de janelas TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), para que seu dispositivo-cliente possa enviar mais dados antes de solicitar uma confirmação.
- [Tempo ocioso do TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), para que seu dispositivo-cliente possa lidar com conexões abertas com mais eficiência.
- [Tamanho máximo de segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), para que seu dispositivo-cliente possa enviar os maiores blocos de dados em um pacote.
- [Confirmações seletivas do TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), para que seu dispositivo-cliente possa confirmar os dados recebidos com mais eficiência.

Com relação aos serviços do Office 365, consulte estes recursos adicionais para otimizar o desempenho:

- [Exchange Online](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [Skype for Business Online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [SharePoint Online](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [Project Online](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

Como ponto de verificação provisório, você pode consultar os [critérios de saída](networking-exit-criteria.md#crit-networking-step5) para esta etapa.

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura de rede](networking-exit-criteria.md)
