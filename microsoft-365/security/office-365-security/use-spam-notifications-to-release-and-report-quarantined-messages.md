---
title: Notificações de spam do usuário final no Office 36
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
description: Quando um administrador habilita as notificações de spam para o usuário final em políticas antispam, os destinatários da mensagem receberão notificações periódicas sobre suas mensagens em quarentena.
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895054"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Notificações de spam do usuário final no Office 365

A quarentena mantém mensagens potencialmente perigosas ou indesejadas nas organizações do Office 365 com caixas de correio do Exchange Online ou de organizações autônomas do Exchange Online Protection (EOP) sem as caixas de correio do Exchange Online. Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).

Por padrão, as notificações de spam do usuário final estão desabilitadas em políticas antispam. Quando um administrador [habilita as notificações de spam para o usuário final](configure-your-spam-filter-policies.md), os destinatários das mensagens receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, emails em massa ou (em abril de 2020) phishing.

> [!NOTE]
> Em outubro de 2019, removemos a capacidade de liberar mensagens em quarentena diretamente de notificações de spam do usuário final. Em vez disso, os usuários agora podem ir para o centro de conformidade & segurança do Office 365 para liberar as mensagens em quarentena (seja diretamente ou clicando em **revisar** na notificação). Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no Office 365](find-and-release-quarantined-messages-as-a-user.md). <br/><br/> As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) só estão disponíveis para administradores. Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no Office 365](manage-quarantined-messages-and-files.md).

Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:

- **Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.

- **Assunto**: o texto da linha de assunto da mensagem em quarentena.

- **Date**: a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.

- **Remetente do bloco**: clique neste link para adicionar o remetente à sua lista de remetentes bloqueados.

- **Revisão**: clique neste link para ir para a quarentena no centro de conformidade & segurança, onde você pode liberar, excluir ou relatar suas mensagens em quarentena.

![Exemplo de notificação de spam do usuário final](../../media/end-user-spam-notification.png)
