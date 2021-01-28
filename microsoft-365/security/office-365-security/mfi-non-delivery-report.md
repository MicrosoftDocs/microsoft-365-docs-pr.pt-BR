---
title: Relatório de não entrega no painel fluxo de emails
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
description: Os administradores podem aprender a usar o relatório de detalhes de falha na entrega no painel de fluxo de emails no Centro de Conformidade de & de Segurança para monitorar os códigos de erro encontrados com mais frequência em notificações de falha na entrega (também conhecidas como NDRs ou mensagens de rejeição) dos envios em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd27fc818a46a983874a04f0e313c622e047ea5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029829"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Relatório de falha na entrega no Centro de Conformidade & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


O  relatório de falha [](mail-flow-insights-v2.md) na entrega no painel fluxo de emails no Centro de Conformidade e Segurança mostra os códigos de erro mais encontrados em notificações de falha na entrega (também conhecidas como NDRs ou mensagens de rejeição) para usuários em sua organização. [&](https://protection.office.com) Este relatório mostra os detalhes das NDRs para que você possa solucionar problemas de entrega de email.

![Widget de relatório de falha na entrega no painel fluxo de emails no Centro de Conformidade e Segurança &](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Exibição de relatório para o relatório de não entrega

Clicar no widget de **relatório de não** entrega levará você ao relatório de não **entrega.**

Por padrão, a atividade de todos os códigos de erro é mostrada. Se você clicar **em Mostrar dados** para , você pode selecionar um código de erro específico na lista suspenso.

Se você passar o mouse sobre uma cor específica (código de erro) em um dia específico no gráfico, verá o número total de mensagens do erro.

![Exibição de relatório no relatório de domínio não aceito](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Details table view for the Non-delivery report

Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:

- **Date**
- **Código do relatório de não entrega**
- **Count**
- **Mensagens de** exemplo: as IDs de mensagem de uma amostra de mensagens afetadas.

Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data **de** início **e data de término.**

Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download.**

Quando você seleciona uma linha na tabela, um flyout é exibido com as seguintes informações:

- **Date**
- **Código do relatório de falha** na entrega: você pode clicar no link para encontrar mais informações sobre as causas e soluções para o código de erro específico.
- **Count**
- **Exemplos de** mensagens: você pode clicar **em Exibir mensagens de exemplo** para ver os resultados [do](message-trace-scc.md) rastreamento de mensagens para uma amostra das mensagens afetadas.

![Submenu de detalhes após selecionar uma linha no exibição de tabela Detalhes no relatório de não entrega](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
