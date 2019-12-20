---
title: Usar notificações de spam do usuário para liberar e reportar mensagens em quarentena no Office 365spam
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Se seu administrador habilitar as notificações para usuários, você receberá uma mensagem de notificação que lista as mensagens enviadas para sua caixa de correio que foram identificadas como spam, massa ou mensagens de phishing. Você pode liberar ou relatar mensagens depois de ser notificado.
ms.openlocfilehash: c8253ba7002ac88932cbef07508215a3d9a65f75
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806704"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Usar notificações de spam do usuário para liberar e reportar mensagens em quarentena no Office 365spam

Se seu administrador habilitar notificações de spam para usuários, você receberá uma mensagem de notificação que lista as mensagens endereçadas à sua caixa de correio que foram identificadas como spam e colocadas em quarentena.

> [!TIP]
> Se você é um administrador e deseja habilitar esse recurso, você pode escolher a opção ao [modificar uma política antispam padrão](configure-your-spam-filter-policies.md).

A mensagem recebida inclui o número de mensagens de spam em quarentena que você tem e a data e a hora (no UTC ou horário coordenado universal) da última mensagem na lista. A lista inclui o seguinte para cada mensagem:

- **Remetente** O nome de envio e o endereço de email da mensagem em quarentena.

- **Assunto** O texto da linha do assunto da mensagem em quarentena.

- **Data** A data e a hora (em UTC) em que a mensagem foi colocada em quarentena.

Estas são as ações que você pode realizar com uma mensagem em quarentena:

- **Bloquear remetente** se quiser que o Office 365 adicione o remetente à sua lista de remetentes bloqueados.

- **Versão** se a mensagem não for spam e se você quiser que o Office 365 envie a mensagem para sua caixa de correio.

- **Revise** para navegar até o portal de quarentena no centro de segurança e conformidade se você quiser realizar outras ações, como visualizar ou liberar.

Esteja ciente do seguinte:

- As mensagens colocadas em quarentena porque corresponderam a uma regra de fluxo de emails não estão incluídas nas mensagens em quarentena do usuário. Somente as mensagens em quarentena por spam estão listadas.

- Você só pode liberar uma mensagem e relatá-la como falso positivo (e não como lixo eletrônico) uma vez.
