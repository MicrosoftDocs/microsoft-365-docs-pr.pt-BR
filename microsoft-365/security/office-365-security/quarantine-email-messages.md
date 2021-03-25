---
title: Mensagens de email em quarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre a quarentena no Exchange Online Protection (EOP) que contém mensagens potencialmente perigosas ou indesejadas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203064"
---
# <a name="quarantined-email-messages-in-eop"></a>Mensagens de email em quarentena no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena está disponível para manter mensagens potencialmente perigosas ou indesejadas.

As políticas anti-malware colocarão automaticamente uma mensagem em quarentena se *algum* anexo for encontrado com malware. Para obter mais informações, consulte [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

Por padrão, a política anti-spam coloca mensagens de phishing em quarentena e entrega mensagens de spam e email em massa para a pasta Lixo Eletrônico do usuário. Porém, você também pode criar e personalizar políticas anti-spam para colocar em quarentena mensagens de spam e email em massa. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

Os usuários e administradores podem trabalhar com mensagens em quarentena:

- Os administradores podem trabalhar com todos os tipos de mensagens em quarentena para todos os usuários. Somente os administradores podem trabalhar com mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte). Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).

- Os usuários podem trabalhar com mensagens em quarentena em que são destinatários se a mensagem foi colocada em quarentena como spam, email em massa ou phishing (a partir de abril de 2020). Para obter mais informações, [consulte Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).

  Para impedir que os usuários gere o gerenciamento de suas próprias mensagens de phishing em quarentena, os administradores podem configurar uma ação diferente para o veredito de filtragem de email de **phishing** em políticas anti-spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

- Os administradores e usuários podem relatar falsos positivos à Microsoft em quarentena.

Para obter mais informações sobre a quarentena, consulte [Perguntas frequentes sobre quarentena.](quarantine-faq.md)
