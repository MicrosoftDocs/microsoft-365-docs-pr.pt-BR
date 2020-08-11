---
title: Notificações de spam do usuário final no Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem saber mais sobre as notificações de spam do usuário final para mensagens em quarentena na proteção do Exchange Online (EOP).
ms.openlocfilehash: b196a9e11d54d9d86acc991ba877279f1fa3d115
ms.sourcegitcommit: 51f040a4edb8dd52521a5d7b0f7a975986a1af10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46608294"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas. Para obter mais informações, consulte [mensagens em quarentena no EOP](quarantine-email-messages.md).

Por padrão, as notificações de spam do usuário final estão desabilitadas em políticas antispam. Quando um administrador [habilita as notificações de spam do usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), os destinatários (incluindo caixas de correio compartilhadas com mapeamento automático habilitado) receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, email em massa ou (em abril de 2020) phishing.

> [!NOTE]
> As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) só estão disponíveis para administradores. Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).

Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:

- **Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.

- **Assunto**: o texto da linha de assunto da mensagem em quarentena.

- **Date**: a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.

- **Remetente do bloco**: clique neste link para adicionar o remetente à sua lista de remetentes bloqueados. Para obter mais informações, consulte [bloquear um remetente de email](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Release**: para mensagens de spam (não phishing), você pode liberar a mensagem aqui sem entrar em quarentena no centro de conformidade do & de segurança.

- **Revisão**: clique neste link para ir para quarentena no centro de conformidade do & de segurança, onde você pode (dependendo de por que a mensagem foi colocada em quarentena) exibir, liberar, excluir ou relatar suas mensagens em quarentena. Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no EOP](find-and-release-quarantined-messages-as-a-user.md).

![Exemplo de notificação de spam do usuário final](../../media/end-user-spam-notification.png)
