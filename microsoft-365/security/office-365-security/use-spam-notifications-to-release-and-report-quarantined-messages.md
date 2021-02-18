---
title: Notificações de spam para o usuário final no Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem saber mais sobre as notificações de spam do usuário final para mensagens em quarentena no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287540"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas. Para obter mais informações, consulte [Mensagens em quarentena no EOP.](quarantine-email-messages.md)

Por padrão, as notificações de spam do usuário final são desabilitadas nas políticas anti-spam. Quando um administrador habilita as notificações de spam para o usuário final, os [destinatários](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)(incluindo caixas de correio compartilhadas com o autopping habilitado) receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, email em massa ou (a partir de abril de 2020) phishing.

Para caixas de correio compartilhadas, as notificações de spam do usuário final só são suportadas para usuários que têm permissão FullAccess para a caixa de correio compartilhada. Para obter mais informações, [consulte Usar o EAC para editar a delegação de caixa de correio compartilhada.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

A notificação de spam do usuário final não é suportada para grupos.

> [!NOTE]
> As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) estão disponíveis apenas para administradores. Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).

Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:

- **Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.

- **Assunto**: o texto da linha de assunto da mensagem em quarentena.

- **Data:** a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.

- **Bloquear Remetente:** clique neste link para adicionar o remetente à sua lista de Remetentes Bloqueados. Para obter mais informações, [consulte Bloquear um remetente de email.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Versão:** para mensagens de spam (não phishing), você pode liberar a mensagem aqui sem entrar em quarentena no Centro de Conformidade e & Segurança.

- **Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages. Para obter mais informações, [consulte Encontrar e liberar mensagens em quarentena como um usuário no EOP](find-and-release-quarantined-messages-as-a-user.md).

![Exemplo de notificação de spam para o usuário final](../../media/end-user-spam-notification.png)

> [!NOTE]
> Um remetente bloqueado ainda pode enviar emails para você. Todas as mensagens desse remetente que a fizerem para sua caixa de correio serão movidas imediatamente para a pasta Lixo Eletrônico. As mensagens futuras desse remetente irão para sua pasta Lixo Eletrônico ou para a quarentena do usuário final. Se você quiser excluir essas mensagens na chegada, em vez de deixar em quarentena, [use](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) as Regras de fluxo de emails (também conhecidas como regras de transporte) para excluir as mensagens na chegada.
