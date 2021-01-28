---
title: Informações sobre filas no painel fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Os administradores podem aprender a usar o & widget Filas no painel Fluxo de emails no Centro de Conformidade e Segurança para monitorar o fluxo de emails malsucedido para suas organizações locais ou parceiras em conectores de saída.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73e97cbbd05e298013e9e686053a969d587ad5cf
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029145"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Informações sobre filas no Centro de Conformidade & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Quando as mensagens não puderem ser enviadas de sua organização para seus servidores de email locais ou parceiros usando conectores, as mensagens serão en filas no Microsoft 365. Exemplos comuns que causam essa condição são:

- O conector está configurado incorretamente.
- Houve alterações de rede ou firewall em seu ambiente local.

O Microsoft 365 continuará tentando fazer a entrega por 24 horas. Após 24 horas, as mensagens expiram e serão devolvidas aos rementes em notificações de não entrega (também conhecidas como NDRs ou mensagens de rejeição).

Se o volume de email na fila exceder o limite predefinido (o valor padrão é 200 mensagens), as informações estarão disponíveis nos seguintes locais:

- O **insight de filas** no [painel de fluxo de](mail-flow-insights-v2.md) emails no Centro de conformidade & [segurança.](https://protection.office.com) Para obter mais informações, consulte o [insight filas na seção painel](#queues-insight-in-the-mail-flow-dashboard) de fluxo de email neste artigo.

- Um alerta é exibido em **Alertas** recentes do painel Alertas no Centro de Conformidade e Segurança [&](https://protection.office.com) ( Painel de **Alertas** \>  ou <https://protection.office.com/alertsdashboard> ).

  ![Alertas recentes no painel Alertas no Centro de Conformidade e Segurança & segurança](../../media/mfi-queued-messages-alert.png)

- Os administradores receberão uma notificação por email com base na configuração da política de alerta padrão chamada **Mensagens que foram adiadas.** Para definir as configurações de notificação para esse alerta, consulte a próxima seção.

  Para obter mais informações sobre políticas de alerta, consulte [Políticas de alerta no Centro de Conformidade e & Segurança.](../../compliance/alert-policies.md)

## <a name="customize-queue-alerts"></a>Personalizar alertas de fila

1. No Centro [de Conformidade & Segurança,](https://protection.office.com)vá para Políticas **de** \> **Alertas ou** <https://protection.office.com/alertpolicies> abra.

2. Na página **Políticas de alerta,** encontre e selecione a política chamada **Mensagens que foram atrasadas.**

3. Na mensagem **que foi adiada, você** pode ativar ou desativar o alerta e definir as configurações de notificação.

   ![As mensagens atrasaram detalhes da política de alerta no Centro de Conformidade e & Segurança](../../media/mfi-queued-messages-alert-policy.png)

   - **Status**: Você pode alternar ou desligar o alerta.

   - **Destinatários de email** e **limite de notificação diária:** clique **em Editar** para definir as seguintes configurações:

4. Para definir as configurações de notificação, clique em **Editar.** No menu **Editar política** exibido, de configure as seguintes configurações:

   - **Enviar notificações por email:** o valor padrão está on.
   - **Destinatários de email:** o valor padrão é **TenantAdmins**.
   - **Limite de notificação** diária: o valor padrão é **Sem limite.**
   - **Limite:** o valor padrão é 200.

   ![As configurações de notificação nas Mensagens atrasaram os detalhes da política de alerta no Centro de Conformidade & Segurança](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Quando terminar, clique em **Salvar** e **Fechar.**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Informações sobre filas no painel fluxo de emails

Mesmo que o volume de mensagens na fila não tenha excedido o limite e [](mail-flow-insights-v2.md) gerado um alerta, você ainda poderá usar o insight de **Filas** no painel fluxo de emails para ver as mensagens que foram enfileiradas por mais de uma hora e tomar medidas antes que o número de mensagens na fila se torne muito grande.

![Widget Filas no painel fluxo de emails no Centro de Conformidade e Segurança &](../../media/mfi-queues-widget.png)

Se você clicar no número de mensagens no widget, um flyout Mensagens **em** fila aparecerá com as seguintes informações:

- **Número de mensagens na fila**
- **Nome do** conector: clique no nome do conector para gerenciar o conector no Centro de administração do Exchange (EAC).
- **Hora de início da fila**
- **Mensagens mais antigas expiradas**
- **Servidor de destino**
- **Último endereço IP**
- **Último erro**
- **Como corrigir:** Problemas comuns e soluções estão disponíveis. Se for um **link Corrigir agora** está disponível, clique nele para corrigir o problema. Caso contrário, clique em qualquer link disponível para obter mais informações sobre o erro e possíveis soluções.

![Detalhes depois de clicar no insight Filas no painel Fluxo de emails](../../media/mfi-queues-details.png)

O mesmo flyout é exibido depois que você **clica** em Exibir fila nos detalhes de um alerta de **atraso de** mensagens.

![Mensagens atrasaram detalhes de alerta no Centro de Conformidade e Segurança & segurança](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Confira também

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
