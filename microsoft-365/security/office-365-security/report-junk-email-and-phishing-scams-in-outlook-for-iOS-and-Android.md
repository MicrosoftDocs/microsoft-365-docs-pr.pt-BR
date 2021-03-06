---
title: Relatar lixo eletrônico e email de phishing no Outlook para iOS e Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook para iOS e Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6e63f534a9f9516c6e1a87ff82d5b0916d25778
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509321"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Relatar lixo eletrônico e email de phishing no Outlook para iOS e Android no Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com caixas de correio [](../../enterprise/hybrid-modern-auth-overview.md)no Exchange Online ou caixas de correio locais usando autenticação moderna híbrida, você pode enviar falsos positivos (emails bons marcados como spam), falsos negativos (email ruim permitido) e mensagens de phishing para a Proteção do Exchange Online (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar

- Para a melhor experiência de envio de usuário, recomendamos usar a Mensagem de Relatório e os complementos de Phishing de Relatório. Consulte [Habilitar](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) o complemento Mensagem de Relatório e [Habilitar o add-in de Phishing de Relatório](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) para obter mais informações.

- Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança. Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [User Submissions policies](user-submission.md).

- Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

  > [!NOTE]
  > Se o relatório de lixo eletrônico estiver desabilitado para o Outlook na política de envio do usuário, as mensagens de lixo eletrônico ou phishing serão movidas para a pasta Lixo Eletrônico e não relatadas ao administrador ou à Microsoft.
