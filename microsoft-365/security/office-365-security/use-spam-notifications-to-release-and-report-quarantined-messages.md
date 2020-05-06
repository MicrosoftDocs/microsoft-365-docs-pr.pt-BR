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
description: Neste artigo, você aprenderá sobre as notificações de spam do usuário final para mensagens em quarentena.
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034993"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena

A quarentena contém mensagens potencialmente perigosas ou indesejadas nas organizações que utilizam Microsoft 365 com caixas de correio do Exchange Online ou Exchange Online Protection (EOP) de organizações autônomas, sem as caixas de correio do Exchange Online. Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).

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
