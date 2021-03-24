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
description: Os administradores podem aprender a usar o mapa de fluxo de email no painel de fluxo de email no Centro de Conformidade de Segurança & para visualizar e rastrear como o email flui de e para sua organização através de conectores e sem usar conectores.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053150"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mapa de fluxo de emails no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

O **mapa de fluxo de** email [](https://protection.office.com) no [painel de](mail-flow-insights-v2.md) fluxo de email no Centro de Conformidade e Segurança & fornece informações sobre como o email flui pela sua organização. Você pode usar essas informações para aprender padrões, identificar anomalias e corrigir problemas à medida que elas ocorrem.

![Widget de mapa de fluxo de email no painel fluxo de email no Centro de Conformidade & Segurança](../../media/mfi-mail-flow-map-widget.png)

Por padrão, o widget mostra o padrão de fluxo de emails do dia anterior em um gráfico conhecido como diagrama *Sankey.* Você pode usar a seta esquerda Seta à esquerda e a ![ ](../../media/scc-left-arrow.png) seta direita ![ para mostrar informações de dias ](../../media/scc-right-arrow.png) diferentes. Cada cor diferente representa o fluxo de emails sobre um conector de entrada ou de saída diferente (ou sem usar conectores). Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.

## <a name="report-view-for-the-mail-flow-map"></a>Exibição de relatório para o mapa de fluxo de emails

Clicar no widget de mapa **de fluxo** de email levará você ao relatório de mapa de **fluxo de** email.

Os gráficos a seguir estão disponíveis na exibição de relatório:

- **Mostrar dados para: Visão geral:** é basicamente uma exibição maior do widget. Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.

  ![Visão geral no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-overview.png)

- **Mostrar dados para: Detalhe**: Este exibição mostra detalhes sobre os conectores e domínios de destino. Os domínios do remetente superior e do destinatário são listados, e o restante é colocado em **Outros**. Se você passar o mouse sobre uma cor e seção específicas, o número de mensagens será exibido.

  ![Exibição detalhada no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-detail.png)

Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**

Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download**.

Informações relacionadas são mostradas abaixo do mapa de fluxo de email se eles estão disponíveis (por exemplo, o [insight corrigir possível loop de email](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>Exibição de tabela de detalhes para o mapa de fluxo de emails

Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:

- **Date**
- **Categoria**
- **Conector / provedor de serviços de terceiros**
- **Domínio remetente/destinatário**
- **Contagem de mensagem**

Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**

Se você selecionar uma linha, detalhes semelhantes serão mostrados em um sobremenu:

![Detalhes do sobremenu da tabela de detalhes no mapa de fluxo de email](../../media/mfi-mail-flow-map-view-details-table-details.png)

Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download**.

Para voltar à exibição de relatórios, clique em **Exibir relatório**.

## <a name="see-also"></a>Confira também

Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)
