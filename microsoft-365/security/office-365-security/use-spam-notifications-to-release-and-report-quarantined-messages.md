---
title: Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena
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
ms.openlocfilehash: 641efc024a2842f30f7754c52f624a9f668851de
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636411"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena

A quarentena contém mensagens potencialmente perigosas ou indesejadas nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) independentes sem caixas de correio do Exchange Online. Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).

Por padrão, as notificações de spam do usuário final estão desabilitadas em políticas antispam. Quando um administrador [habilita notificações de spam para o usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), os destinatários receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, email em massa ou (em abril de 2020) phishing.

> [!NOTE]
> As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) só estão disponíveis para administradores. Para obter mais informações, consulte [Gerenciar arquivos e mensagens em quarentena como administrador no Office 365](manage-quarantined-messages-and-files.md).

Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:

- **Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.

- **Assunto**: o texto da linha de assunto da mensagem em quarentena.

- **Date**: a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.

- **Remetente do bloco**: clique neste link para adicionar o remetente à sua lista de remetentes bloqueados. Para obter mais informações, consulte [bloquear um remetente de email no Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Release**: para mensagens de spam (não Phish), você pode liberar a mensagem aqui sem ir para a quarentena do centro de conformidade de & de segurança.

- **Revisão**: clique neste link para ir para quarentena no centro de conformidade & segurança, onde você pode liberar, excluir ou relatar suas mensagens em quarentena. Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no Office 365](find-and-release-quarantined-messages-as-a-user.md).

![Exemplo de notificação de spam do usuário final](../../media/end-user-spam-notification.png)
