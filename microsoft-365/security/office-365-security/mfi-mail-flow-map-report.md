---
title: Mapa de fluxo de email
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o mapa de fluxo de emails no painel de fluxo de emails no centro de conformidade de & de segurança para visualizar e controlar como o email flui para e de sua organização sobre os conectores e sem usar conectores.
ms.openlocfilehash: 74cabb7f7b34be6248d18d71565c8a9729d7e38b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199366"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mapa de fluxo de emails no centro de conformidade de & de segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


O **mapa de fluxo de emails** no [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de conformidade do & de segurança](https://protection.office.com) fornece informações sobre como os emails fluem pela sua organização. Você pode usar essas informações para aprender padrões, identificar anomalias e corrigir problemas conforme eles ocorrem.

![Widget mapa de fluxo de emails no painel de fluxo de emails no centro de conformidade de & de segurança](../../media/mfi-mail-flow-map-widget.png)

Por padrão, o widget mostra o padrão de fluxo de emails do dia anterior em um gráfico conhecido como diagrama *Sankey* . Você pode usar a seta para a esquerda seta para a ![ esquerda e seta para ](../../media/scc-left-arrow.png) a direita ![ ](../../media/scc-right-arrow.png) para mostrar informações de diferentes dias. Cada cor diferente representa o fluxo de mensagens por um conector de entrada ou saída diferente (ou sem usar conectores). Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.

## <a name="report-view-for-the-mail-flow-map"></a>Exibição de relatório para o mapa de fluxo de emails

Clicar no widget **mapa de fluxo de emails** o levará para o relatório de **mapa de fluxo de emails** .

Os gráficos a seguir estão disponíveis no modo de exibição de relatório:

- **Show data for: Overview**: Este é basicamente uma visão maior do widget. Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.

  ![Exibição de visão geral no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-overview.png)

- **Mostrar dados de: Detail**: este modo de exibição mostra detalhes sobre os conectores e domínios de destino. Os principais remetentes e domínios de destinatário são listados e o restante é colocado em **outros**. Se você passar o mouse sobre uma cor e seção específica, o número de mensagens será exibido.

  ![Exibição de detalhes no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-detail.png)

Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.

Para enviar por email o relatório para um intervalo de datas específico para um ou mais destinatários, clique em **solicitar download**.

Os insights relacionados são mostrados abaixo do mapa de fluxo de emails, se estiverem disponíveis (por exemplo, a [correção de possíveis informações de loop de email](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>Exibição da tabela de detalhes para o mapa de fluxo de emails

Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:

- **Date**
- **Category**
- **Conector/provedor de serviços terceirizado**
- **Domínio do remetente/destinatário**
- **Contagem de mensagem**

Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.

Se você selecionar uma linha, os detalhes semelhantes serão mostrados em um submenu:

![Submenu de detalhes da tabela detalhes no mapa de fluxo de emails](../../media/mfi-mail-flow-map-view-details-table-details.png)

Para enviar por email o relatório para um intervalo de datas específico para um ou mais destinatários, clique em **solicitar download**.

Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.

## <a name="see-also"></a>Confira também

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
