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
description: Os administradores podem saber mais sobre a quarentena no Exchange Online Protection (EOP) que contém mensagens potencialmente perigosas ou indesejadas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4b111ea0d07453ef4280ec9e57247c8215420074
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167402"
---
# <a name="quarantined-email-messages-in-eop"></a>Mensagens de email em quarentena no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
-   [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
-   [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena está disponível para ressalvar mensagens potencialmente perigosas ou indesejadas.

As políticas anti-malware colocarão automaticamente uma mensagem em quarentena *se* qualquer anexo for encontrado contendo malware. Para obter mais informações, consulte [Configurar políticas anti-malware no EOP.](configure-anti-malware-policies.md)

Por padrão, a política anti-spam coloca as mensagens de phishing em quarentena e envia mensagens de spam e emails em massa para a pasta Lixo Eletrônico do usuário. Porém, você também pode criar e personalizar políticas anti-spam para colocar mensagens de spam e emails em massa em quarentena. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

Tanto os usuários quanto os administradores podem trabalhar com mensagens em quarentena:

- Os administradores podem trabalhar com todos os tipos de mensagens em quarentena para todos os usuários. Somente administradores podem trabalhar com mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte). Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).

- Os usuários podem trabalhar com mensagens em quarentena nas quais são destinatários se a mensagem foi colocada em quarentena como spam, email em massa ou (a partir de abril de 2020) phishing. Para obter mais informações, [consulte Encontrar e liberar mensagens em quarentena como um usuário no EOP](find-and-release-quarantined-messages-as-a-user.md).

  Para impedir que os usuários gerementem suas próprias mensagens de phishing em quarentena, os administradores podem configurar uma ação diferente para o veredito de filtragem de email de **phishing** nas políticas anti-spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

- Os administradores e usuários podem relatar falsos positivos à Microsoft em quarentena.

Para obter mais informações sobre a quarentena, consulte [Perguntas frequentes sobre a quarentena.](quarantine-faq.md)
