---
title: Relatar emails de lixo eletrônico e phishing no Outlook para iOS e Android
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre as opções internas de lixo eletrônico, não lixo eletrônico e relatório de email de phishing no Outlook para iOS e Android.
ms.openlocfilehash: fef519f3fdd5cf46d383c41ad227ab0cd3ed4390
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201528"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Relatar emails de lixo eletrônico e phishing no Outlook para iOS e Android no Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio em Exchange Online ou caixas de correio locais usando a [autenticação moderna híbrida](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview?view=o365-worldwide), você pode usar as opções de relatório internas no Outlook para IOS e Android para enviar falsos positivos (emails bons marcados como spam), falsos negativos (email incorreto) e mensagens de phishing para o Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar

- Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade do & de segurança. Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).

- Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar. Para obter mais informações, consulte [especificar uma caixa de correio para envios de emails de spam e mensagens de phishing no Exchange Online](user-submission.md).

- Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).

  > [!NOTE]
  > Se o relatório de lixo eletrônico estiver desabilitado para o Outlook na política de envio de usuário, as mensagens de lixo eletrônico ou phishing serão movidas para a pasta de lixo eletrônico e não relatadas para seu administrador ou Microsoft.

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>Relatar mensagens de spam e phishing no Outlook para iOS e Android

Para mensagens na caixa de entrada ou qualquer outra pasta de email, exceto lixo eletrônico, use as etapas a seguir para relatar mensagens de spam e phishing para iOS e Android:

1. Selecione uma ou mais mensagens.
2. No canto superior direito, toque nos três pontos verticais. O menu Ação é aberto.

   ![Relatar emails de lixo eletrônico ou phishing no menu de ações](../../media/Android-report-as-junk-dialog.png)

3. Toque em **relatar lixo eletrônico** e selecione **lixo eletrônico** ou **phishing**.

   ![Relatar emails de lixo eletrônico ou phishing](../../media/Android-report-junk-or-phishing.png)

4. Na caixa de diálogo exibida, você pode escolher **relatar** ou **não agradecer**. Ao selecionar **não graças**, se você tiver tocado **lixo** , a mensagem será movida para a pasta lixo eletrônico, se você **tiver tocado a** mensagem é movida para a pasta itens excluídos. Selecione **relatório** para também enviar uma cópia da mensagem para a Microsoft.

   ![Relatar opções de relatório de email de lixo eletrônico ou phishing](../../media/Android-junk-email-reporting-options.png)

Se você mudar de ideia, selecione **desfazer** na notificação do sistema que aparece. A mensagem permanece na pasta caixa de entrada.

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>Relatar mensagens que não são spam da pasta lixo eletrônico no Outlook para iOS e Android

Na pasta lixo eletrônico, use as seguintes etapas para relatar falsos positivos de spam:

1. Selecione uma ou mais mensagens.
2. No canto superior direito, toque nos três pontos verticais. O menu Ação é aberto.

   ![Relatar não é lixo eletrônico no menu Ação](../../media/Android-not-junk-email.png)

3. Toque em **não é lixo eletrônico**.

Uma notificação de caixa de correio parece que o email foi movido para sua caixa de entrada. Se você mudar de ideia, selecione **desfazer** na notificação do sistema. O email permanece na pasta lixo eletrônico.
