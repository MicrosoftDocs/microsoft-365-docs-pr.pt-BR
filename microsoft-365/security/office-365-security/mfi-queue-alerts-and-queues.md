---
title: Ideias de filas no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Os administradores podem aprender a usar o widget filas no painel de fluxo de emails no centro de conformidade do & de segurança para monitorar o fluxo de emails sem êxito em suas organizações locais ou de parceiros em relação a conectores de saída.
ms.openlocfilehash: 3291a21828215d0a2a99c2226147bb1b748b8469
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199284"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Informações sobre filas no centro de conformidade & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Quando as mensagens não podem ser enviadas da sua organização para seus servidores de email locais ou parceiros usando conectores, as mensagens são enfileiradas no Microsoft 365. Exemplos comuns que causam essa condição são:

- O conector está configurado incorretamente.
- Houve alterações de rede ou firewall no seu ambiente local.

A Microsoft 365 continuará a tentar a entrega por 24 horas. Após 24 horas, as mensagens expirarão e serão retornadas aos remetentes nas notificações de falha na entrega (também conhecidas como NDRs ou mensagens de devolução).

Se o volume de email em fila exceder o limite predefinido (o valor padrão é 200), as informações estarão disponíveis nos seguintes locais:

- As **filas** insights no [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de conformidade de & de segurança](https://protection.office.com). Para obter mais informações, consulte a [visão de filas no painel de fluxo de emails](#queues-insight-in-the-mail-flow-dashboard) deste tópico.
  
- Um alerta é exibido em **alertas recentes** no painel de alertas no [centro de conformidade & segurança](https://protection.office.com) (painel de**alertas** \> **Dashboard** ou <https://protection.office.com/alertsdashboard> ).

  ![Alertas recentes no painel de alertas no centro de conformidade & segurança](../../media/mfi-queued-messages-alert.png)

- Os administradores receberão uma notificação por email com base na configuração da política de alerta padrão chamada **as mensagens foram atrasadas**. Para definir as configurações de notificação para este alerta, consulte a próxima seção.

  Para obter mais informações sobre políticas de alerta, consulte [políticas de alerta no centro de conformidade de & de segurança](../../compliance/alert-policies.md).

## <a name="customize-queue-alerts"></a>Personalizar alertas de fila

1. No [centro de conformidade & segurança](https://protection.office.com), vá para **Alerts** \> **políticas de alerta** de alertas ou abrir <https://protection.office.com/alertpolicies> .

2. Na página **políticas de alerta** , localize e selecione a política denominada **mensagens foram atrasadas**.

3. Na **mensagem com submenu com atraso** que é aberto, você pode ativar ou desativar o alerta e definir as configurações de notificação.

   ![Detalhes da política de alerta de mensagens atrasadas o centro de conformidade & segurança](../../media/mfi-queued-messages-alert-policy.png)

   - **Status**: você pode ativar ou desativar o alerta.

   - **Destinatários de email** e **limite de notificação diária**: clique em **Editar** para definir as seguintes configurações:

4. Para definir as configurações de notificação, clique em **Editar**. No submenu **Editar política** que aparece, defina as seguintes configurações:

   - **Enviar notificações por email**: o valor padrão é ativado.
   - **Destinatários de email**: o valor padrão é **TenantAdmins**.
   - **Limite diário de notificação**: o valor padrão é **sem limite**.
   - **Limite**: o valor padrão é 200.

   ![As configurações de notificação nas mensagens foram atrasadas detalhes da política de alerta o centro de conformidade & segurança](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Quando tiver terminado, clique em **salvar** e **fechar**.

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Ideias de filas no painel de fluxo de emails

Mesmo que o volume da mensagem na fila não tenha excedido o limite e gerado um alerta, você ainda pode usar a percepção de **filas** no [painel de fluxo de emails](mail-flow-insights-v2.md) para ver as mensagens que foram enfileiradas por mais de uma hora e tomar medidas antes que o número de mensagens em fila fique muito grande.

![Widget filas no painel de fluxo de emails no centro de conformidade de & de segurança](../../media/mfi-queues-widget.png)

Se você clicar no número de mensagens no widget, um submenu de **mensagens em fila** aparecerá com as seguintes informações:

- **Número de mensagens em fila**
- **Nome do conector**: clique no nome do conector para gerenciar o conector no centro de administração do Exchange (Eat).
- **Hora da fila de início**
- **As mensagens mais antigas expiraram**
- **Servidor de destino**
- **Último endereço IP**
- **Último erro**
- **Como corrigir**: problemas comuns e soluções estão disponíveis. Se houver um link **corrigir agora** disponível, clique nele para corrigir o problema. Caso contrário, clique em qualquer link disponível para obter mais informações sobre o erro e as soluções possíveis.

![Detalhes depois de clicar na visão filas no painel de fluxo de emails](../../media/mfi-queues-details.png)

O mesmo submenu é exibido depois que você clica em **Exibir fila** nos detalhes de um alerta de **mensagens foram atrasadas** .

![Os detalhes de alerta de mensagens foram atrasadas no centro de conformidade de & de segurança](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Confira também

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
