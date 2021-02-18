---
title: Mapa de fluxo de email
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o mapa de fluxo de emails no painel Fluxo de emails no Centro de Conformidade e Segurança para visualizar e controlar como os emails fluem de e para sua organização sobre conectores e sem usar conectores. &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f507f7f01999492d17e168a2a56da906bfcb52d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290580"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mapa de fluxo de emails no Centro de Conformidade & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

O **mapa de fluxo de** emails no painel [Fluxo](mail-flow-insights-v2.md) de emails no Centro de Conformidade e Segurança & [fornece](https://protection.office.com) informações sobre como os emails fluem pela sua organização. Você pode usar essas informações para aprender padrões, identificar anomalias e corrigir problemas à medida que eles ocorrem.

![Widget de mapa de fluxo de emails no painel Fluxo de emails no Centro de Conformidade e & Segurança](../../media/mfi-mail-flow-map-widget.png)

Por padrão, o widget mostra o padrão de fluxo de emails do dia anterior em um gráfico conhecido como *diagrama Sankey.* Você pode usar a seta para a esquerda e a seta para a direita para ![ mostrar informações de dias ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) diferentes. Cada cor diferente representa o fluxo de emails em um conector de entrada ou de saída diferente (ou sem usar conectores). Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.

## <a name="report-view-for-the-mail-flow-map"></a>Exibição de relatório para o mapa de fluxo de emails

Clicar no widget mapa de **fluxo de** emails levará você para o relatório de mapa de **fluxo de** email.

Os gráficos a seguir estão disponíveis na exibição de relatório:

- **Mostrar dados para: Visão geral:** é basicamente uma exibição maior do widget. Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.

  ![Visão geral no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-overview.png)

- **Mostrar dados para: Detalhe:** esta exibição mostra detalhes sobre os conectores e domínios de destino. Os principais domínios de remetentes e destinatários são listados, e o restante é colocado em **Outros.** Se você passar o mouse sobre uma cor e uma seção específicas, o número de mensagens será exibido.

  ![Exibição detalhada no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-detail.png)

Se você clicar em **Filtros** em uma exibição de relatório, poderá especificar um intervalo de datas com data **de** início **e data de término.**

Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download.**

Informações relacionadas são mostradas abaixo do mapa de fluxo de email se elas estão disponíveis (por exemplo, o insight de correção de [possível loop de email).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>Details table view for the Mail flow map

Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:

- **Date**
- **Categoria**
- **Conector/Provedor de serviços de terceiros**
- **Domínio remetente/destinatário**
- **Contagem de mensagem**

Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data de **início** **e data de término.**

Se você selecionar uma linha, detalhes semelhantes serão mostrados em um flyout:

![Detalhes do flyout da tabela de detalhes no mapa de fluxo de emails](../../media/mfi-mail-flow-map-view-details-table-details.png)

Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download.**

Para voltar para a exibição de relatórios, clique em **Exibir relatório.**

## <a name="see-also"></a>Confira também

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
