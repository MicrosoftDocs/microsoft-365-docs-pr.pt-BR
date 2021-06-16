---
title: Notificações de spam do usuário final no Microsoft 365
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
description: Os administradores podem aprender sobre notificações de spam do usuário final para mensagens em quarentena Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 30f82abc245a2f6022bd1a75b57e9d20e3e32a32
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929882"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas. Para obter mais informações, consulte [Mensagens em quarentena no EOP](quarantine-email-messages.md).

Por padrão, as notificações de spam do usuário final são desabilitadas em políticas anti-spam. Quando um administrador habilita notificações de spam do usuário final, os [destinatários](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)(incluindo caixas de correio compartilhadas com automação habilitada) receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, email em massa ou phishing (a partir de abril de 2020).

Para caixas de correio compartilhadas, as notificações de spam do usuário final só são suportadas para usuários que têm permissão FullAccess para a caixa de correio compartilhada. Para obter mais informações, [consulte Usar o EAC para editar a delegação de caixa de correio compartilhada.](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

A notificação de Spam do Usuário Final não é suportada para grupos.

> [!NOTE]
> As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) estão disponíveis apenas para administradores. Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).

Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:

- **Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.

- **Assunto**: O texto da linha de assunto da mensagem em quarentena.

- **Data**: a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.

- **Bloquear Remetente**: clique neste link para adicionar o remetente à lista Remetentes Bloqueados em sua caixa de correio. Para obter mais informações, consulte [Bloquear um remetente](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Versão**: para mensagens de spam (não phishing), você pode liberar a mensagem aqui sem ir para Quarentena do portal Microsoft 365 Defender.

- **Revisão**: clique neste link para ir para Quarentena no portal Microsoft 365 Defender, onde você pode (dependendo do motivo pelo qual a mensagem foi colocada em quarentena), liberar, excluir ou relatar suas mensagens em quarentena. Para obter mais informações, [consulte Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).

![Exemplo de notificação de spam do usuário final](../../media/end-user-spam-notification.png)

> [!NOTE]
> Um remetente bloqueado ainda pode enviar emails. Todas as mensagens desse remetente que o fizerem para sua caixa de correio serão movidas imediatamente para a pasta Lixo Eletrônico. Mensagens futuras desse remetente irão para sua pasta Lixo Eletrônico ou para a quarentena do usuário final. Se você quiser excluir essas mensagens na chegada, em vez de quarantir-las, [use](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) As Regras de fluxo de emails (também conhecidas como regras de transporte) para excluir as mensagens na chegada.