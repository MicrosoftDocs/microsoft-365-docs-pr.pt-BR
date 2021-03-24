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
description: Os administradores podem aprender a usar o relatório de detalhes de não entrega no painel de fluxo de emails no Centro de Conformidade do & de Segurança para monitorar os códigos de erro encontrados com mais frequência em relatórios de falha na entrega (também conhecidos como NDRs ou mensagens de rejeição) de envios em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053133"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Relatório de falha na entrega no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

O  relatório de não [](mail-flow-insights-v2.md) entrega no painel de fluxo de emails no Centro de Conformidade e Segurança mostra os códigos de erro mais encontrados em relatórios de não entrega (também conhecidos como NDRs ou mensagens de rejeição) para usuários em sua organização. [&](https://protection.office.com) Este relatório mostra os detalhes das NDRs para que você possa solucionar problemas de entrega de email.

![Widget de relatório de não entrega no painel fluxo de emails no Centro de Conformidade & Segurança](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Exibição de relatório para o relatório de não entrega

Clicar no widget de relatório **de** não entrega levará você ao relatório **de não entrega.**

Por padrão, a atividade de todos os códigos de erro é mostrada. Se você clicar **em Mostrar dados** para , você pode selecionar um código de erro específico no menu suspenso.

Se você passar o mouse sobre uma cor específica (código de erro) em um dia específico no gráfico, você verá o número total de mensagens para o erro.

![Exibir relatório no relatório de domínio não aceito](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Exibição de tabela de detalhes para o relatório de não entrega

Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:

- **Date**
- **Código do relatório de não entrega**
- **Count**
- **Exemplo de mensagens**: As IDs de mensagem de uma amostra de mensagens afetadas.

Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**

Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download**.

Quando você seleciona uma linha na tabela, um sobrevoo aparece com as seguintes informações:

- **Date**
- **Código do relatório** de não entrega : você pode clicar no link para encontrar mais informações sobre as causas e soluções para o código de erro específico.
- **Count**
- **Exemplo de mensagens**: você pode clicar em **Exibir mensagens de exemplo** para ver os resultados do rastreamento de mensagens para um exemplo das mensagens afetadas. [](message-trace-scc.md)

![Submenu de detalhes após selecionar uma linha no exibição de tabela Detalhes no relatório De não entrega](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)
