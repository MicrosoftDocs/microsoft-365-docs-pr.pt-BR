---
title: Alertas de filas e filas
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Os administradores podem aprender sobre alertas de fila e filas no painel de fluxo de emails no centro de conformidade do & de segurança.
ms.openlocfilehash: ef8b4acd4008f3039030049893f83a5e49e1efc2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073671"
---
# <a name="queue-alerts-and-queues"></a>Alertas de filas e filas

## <a name="queue-alerts"></a>Alertas de fila

Quando as mensagens não podem ser enviadas da sua organização do Office 365 para seus servidores de email locais ou parceiros usando conectores, as mensagens são enfileiradas no Office 365. Exemplos comuns que causam essa condição são:

- O conector está configurado incorretamente.

- Houve alterações de rede ou firewall no seu ambiente local.

O Office 365 continuará a tentar a entrega por 48 horas. Após 48 horas, as mensagens expirarão e serão retornadas para os remetentes nas notificações de falha na entrega (também conhecidas como NDRs ou mensagens de devolução).

Se o volume de email em fila exceder o limite predefinido (o valor padrão é 2000), os alertas estarão disponíveis no painel de fluxo de emails em **alertas recentes**, e os administradores receberão uma notificação por email (para o endereço de email alternativo) . Para configurar o limite de alerta, o limite de notificação diária e/ou os destinatários do alerta, consulte a seção **Personalizar alertas de fila** abaixo.

![Enfileirar alertas na área de alertas recentes do painel de fluxo de emails no centro de conformidade & segurança](../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>Personalizar alertas de fila

Informações de fluxo de emails criar uma política de alerta chamada **mensagens atrasadas** (a caixa de seleção **enviar notificações por email** na captura de tela de exemplo abaixo) foi encontrada em **alertas** \> **políticas de alerta**. Você pode modificar os destinatários de limite e alerta clicando na política.

![Navegação de alertas](../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

Você verá uma nova folha de informações de política, agora é possível clicar em **Editar política**.

![Editar Política ](../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

A lâmina de informações será alterada para a **política de edição**. Agora você pode alterar os destinatários para o email de alerta, o limite do número de notificações enviadas por dia e o limite mínimo para acionar o alerta (200 ou mais).

![Editar folha de política](../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>Detalhes de alerta da fila

Quando você clica no alerta, os detalhes de alerta aparecem em um painel de submenu.

![Selecione um alerta de fila na área de alerta recentes do painel de fluxo de emails no centro de conformidade & segurança](../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![O submenu detalhes da fila de alerta no centro de conformidade & segurança](../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

Você pode clicar em **Exibir fila** nos detalhes do alerta para ver os detalhes da fila, os problemas e os links para as correções disponíveis em um novo painel de submenu.

![O submenu detalhes da fila de alerta no centro de conformidade & segurança](../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Exibir fila nos detalhes do alerta](../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>Filas

Mesmo que o volume da mensagem na fila não tenha excedido o limite, você ainda pode usar a área **filas** do painel de fluxo de email para ver as mensagens que foram enfileiradas por mais de uma hora. Você pode usar a área **filas** para monitorar o número de mensagens em fila (o valor 0 indica que o fluxo de emails está ok) e tomar medidas antes que o número de mensagens na fila fique muito grande.

![Filas no painel de fluxo de emails no centro de conformidade de & de segurança](../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

Quando você **clica no número**de mensagens em filas, os detalhes e a orientação da fila para corrigir o problema aparecerão em um painel de submenu (o mesmo submenu exibido depois que você clicar em **Exibir fila** nos detalhes de um alerta de fila).

![Detalhes da fila](../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a>Confira também

Para obter mais informações sobre outros insights de fluxo de email no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
