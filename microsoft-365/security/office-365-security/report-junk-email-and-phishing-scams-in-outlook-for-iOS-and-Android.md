---
title: Relatar emails de lixo eletrônico e phishing no Outlook para iOS e Android
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre as opções internas de lixo eletrônico, não lixo eletrônico e relatório de email de phishing no Outlook para iOS e Android.
ms.openlocfilehash: 23668a762301ee442bc805e62863079ee7ae6076
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350850"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="0cbf6-103">Relatar emails de lixo eletrônico e phishing no Outlook para iOS e Android no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0cbf6-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0cbf6-104">Nas organizações do Microsoft 365 com caixas de correio em Exchange Online ou caixas de correio locais usando a [autenticação moderna híbrida](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), você pode usar as opções de relatório internas no Outlook para IOS e Android para enviar falsos positivos (emails bons marcados como spam), falsos negativos (email incorreto) e mensagens de phishing para o Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="0cbf6-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0cbf6-105">O que você precisa saber antes de começar</span><span class="sxs-lookup"><span data-stu-id="0cbf6-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="0cbf6-106">Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="0cbf6-107">Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="0cbf6-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="0cbf6-108">Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="0cbf6-109">Para obter mais informações, consulte [políticas de envios de usuários](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="0cbf6-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="0cbf6-110">Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="0cbf6-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="0cbf6-111">Se o relatório de lixo eletrônico estiver desabilitado para o Outlook na política de envio de usuário, as mensagens de lixo eletrônico ou phishing serão movidas para a pasta de lixo eletrônico e não relatadas para seu administrador ou Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="0cbf6-112">Relatar mensagens de spam e phishing no Outlook para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="0cbf6-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="0cbf6-113">Para mensagens na caixa de entrada ou qualquer outra pasta de email, exceto lixo eletrônico, use as etapas a seguir para relatar mensagens de spam e phishing para iOS e Android:</span><span class="sxs-lookup"><span data-stu-id="0cbf6-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="0cbf6-114">Selecione uma ou mais mensagens.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-114">Select one or more messages.</span></span>
2. <span data-ttu-id="0cbf6-115">No canto superior direito, toque nos três pontos verticais.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="0cbf6-116">O menu Ação é aberto.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-116">The action menu opens.</span></span>

   ![Relatar emails de lixo eletrônico ou phishing no menu de ações](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="0cbf6-118">Toque em **relatar lixo eletrônico** e selecione **lixo eletrônico** ou **phishing**.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Relatar emails de lixo eletrônico ou phishing](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="0cbf6-120">Na caixa de diálogo exibida, você pode escolher **relatar** ou **não agradecer**.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="0cbf6-121">Ao selecionar **não graças**, se você tiver tocado **lixo** , a mensagem será movida para a pasta lixo eletrônico, se você **tiver tocado a** mensagem é movida para a pasta itens excluídos.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="0cbf6-122">Selecione **relatório** para também enviar uma cópia da mensagem para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Relatar opções de relatório de email de lixo eletrônico ou phishing](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="0cbf6-124">Se você mudar de ideia, selecione **desfazer** na notificação do sistema que aparece.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="0cbf6-125">A mensagem permanece na pasta caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="0cbf6-126">Relatar mensagens que não são spam da pasta lixo eletrônico no Outlook para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="0cbf6-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="0cbf6-127">Na pasta lixo eletrônico, use as seguintes etapas para relatar falsos positivos de spam:</span><span class="sxs-lookup"><span data-stu-id="0cbf6-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="0cbf6-128">Selecione uma ou mais mensagens.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-128">Select one or more messages.</span></span>
2. <span data-ttu-id="0cbf6-129">No canto superior direito, toque nos três pontos verticais.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="0cbf6-130">O menu Ação é aberto.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-130">The action menu opens.</span></span>

   ![Relatar não é lixo eletrônico no menu Ação](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="0cbf6-132">Toque em **não é lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-132">Tap **Not junk**.</span></span>

<span data-ttu-id="0cbf6-133">Uma notificação de caixa de correio parece que o email foi movido para sua caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="0cbf6-134">Se você mudar de ideia, selecione **desfazer** na notificação do sistema.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="0cbf6-135">O email permanece na pasta lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0cbf6-135">The email remains in the Junk folder.</span></span>
