---
title: 'Etapa 5: Otimizar o desempenho do serviço do Office 365 com o cliente'
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
description: Definir as configurações de TCP e os serviços do Office 365 para melhorar o desempenho.
ms.openlocfilehash: f89ae816780101c31971c8e3e60df803f82f1e55
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370068"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Etapa 5: Otimizar o desempenho do serviço do Office 365 com o cliente

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![Fase 1 – Rede](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Você pode aumentar o desempenho ao ajustar a forma como o Protocolo de Controle de Transmissão (TCP) funciona entre dispositivos-cliente e os serviços do Office 365.

Para dispositivos-cliente, você pode alterar as seguintes configurações do TCP em dispositivos-cliente para otimizar o desempenho do TCP:

- [Dimensionamento de janelas TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), para que seu dispositivo-cliente possa enviar mais dados antes de solicitar uma confirmação.
- [Tempo ocioso do TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), para que seu dispositivo-cliente possa lidar com conexões abertas com mais eficiência.
- [Tamanho máximo de segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), para que seu dispositivo-cliente possa enviar os maiores blocos de dados em um pacote.
- [Confirmações seletivas do TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), para que seu dispositivo-cliente possa confirmar os dados recebidos com mais eficiência.

Com relação aos serviços do Office 365, consulte estes recursos adicionais para otimizar o desempenho:

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [Skype for Business Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Web App no Project Online](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step5) para esta etapa.

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura de rede](networking-exit-criteria.md)
