---
title: Quarentena no Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: A quarentena no Microsoft 365 contém mensagens potencialmente perigosas ou indesejadas. Administradores e usuários finais podem acessar a quarentena.
ms.openlocfilehash: 2e2a83bc2ff2d57cf3310e2cb17a656683dbed47
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634431"
---
# <a name="quarantine-email-messages"></a>Mensagens de email em quarentena

Se você for um cliente Microsoft 365 com caixas de correio no Exchange Online ou um cliente autônomo do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena estará disponível para manter mensagens potencialmente perigosas ou indesejadas.

As políticas Antimalware automaticamente colocarão uma mensagem em quarentena se *qualquer* anexo tiver malware. Para obter mais informações, consulte [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).

Por padrão, o anti-spam policia as mensagens de phishing e entrega mensagens de email em massa e spam para a pasta lixo eletrônico do usuário. No entanto, você também pode criar e personalizar políticas antispam para colocar em quarentena spam e mensagens de email em massa. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

Tanto usuários quanto administradores podem trabalhar com mensagens em quarentena:

- Os administradores podem trabalhar com todos os tipos de mensagens em quarentena para todos os usuários. Somente os administradores podem trabalhar com mensagens colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte). Para obter mais informações, consulte [Gerenciar arquivos e mensagens em quarentena como administrador no Office 365](manage-quarantined-messages-and-files.md).

- Os usuários podem trabalhar com mensagens em quarentena onde eles são um destinatário se a mensagem foi colocada em quarentena como spam, email em massa ou (a partir de abril de 2020). Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no Office 365](find-and-release-quarantined-messages-as-a-user.md).

  Para impedir que os usuários gerenciem suas próprias mensagens de phishing em quarentena, os administradores podem configurar uma ação diferente para a veredicto de filtragem de **email de phishing** em políticas antispam. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

- Administradores e usuários podem relatar falsos positivos para a Microsoft em quarentena.

Para obter mais informações sobre, quarentena, consulte [perguntas frequentes sobre quarentena](quarantine-faq.md).
