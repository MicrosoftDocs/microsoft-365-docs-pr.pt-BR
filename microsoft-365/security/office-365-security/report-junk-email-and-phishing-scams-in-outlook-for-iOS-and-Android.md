---
title: Relatar lixo eletrônico e phishing no Outlook para iOS e Android
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
description: Os administradores podem saber mais sobre as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook para iOS e Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166814"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="c3ac7-103">Relatar lixo eletrônico e phishing no Outlook para iOS e Android no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c3ac7-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c3ac7-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="c3ac7-104">**Applies to**</span></span>
- [<span data-ttu-id="c3ac7-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c3ac7-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="c3ac7-106">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="c3ac7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c3ac7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3ac7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c3ac7-108">Nas organizações do Microsoft 365 com caixas de correio [](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)no Exchange Online ou caixas de correio locais usando a autenticação moderna híbrida, você pode usar as opções internas de relatório no Outlook para iOS e Android para enviar falsos positivos (emails bons marcados como spam), falsos negativos (emails falsos permitidos) e mensagens de phishing para o Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="c3ac7-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3ac7-109">O que você precisa saber antes de começar</span><span class="sxs-lookup"><span data-stu-id="c3ac7-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="c3ac7-110">Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos usar o portal de Envios no Centro de Conformidade e Segurança & Segurança.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c3ac7-111">Para obter mais informações, consulte Usar o Envio de Administrador para [enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c3ac7-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="c3ac7-112">Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c3ac7-113">Para obter mais informações, consulte [Políticas de Envios de Usuário.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c3ac7-113">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c3ac7-114">Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [Mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c3ac7-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c3ac7-115">Se o relatório de lixo eletrônico estiver desabilitado para o Outlook na política de envio de usuário, as mensagens de lixo eletrônico ou phishing serão movidas para a pasta Lixo eletrônico e não relatadas ao administrador ou à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-115">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="c3ac7-116">Relatar mensagens de spam e phishing no Outlook para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="c3ac7-116">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="c3ac7-117">Para mensagens na Caixa de Entrada ou em qualquer outra pasta de email, exceto Lixo Eletrônico, use as etapas a seguir para relatar mensagens de spam e phishing para iOS e Android:</span><span class="sxs-lookup"><span data-stu-id="c3ac7-117">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="c3ac7-118">Selecione uma ou mais mensagens.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-118">Select one or more messages.</span></span>
2. <span data-ttu-id="c3ac7-119">No canto superior direito, toque nos três pontos verticais.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-119">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="c3ac7-120">O menu de ação é aberto.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-120">The action menu opens.</span></span>

   ![Relatar lixo eletrônico ou email de phishing no menu de ações](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="c3ac7-122">Toque **em Relatar lixo** eletrônico e selecione Lixo **Eletrônico** ou **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="c3ac7-122">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Relatar lixo eletrônico ou email de phishing](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="c3ac7-124">Na caixa de diálogo exibida, você pode escolher **Relatório** ou **Não, Obrigado.**</span><span class="sxs-lookup"><span data-stu-id="c3ac7-124">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="c3ac7-125">Ao selecionar **Não** Obrigado ,  se você tiver mapeado Lixo Eletrônico, a mensagem será deslocada para a pasta Lixo Eletrônico, se você tiver mapeado **Phishing,** a mensagem será deslocada para a pasta Itens Excluídos.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-125">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="c3ac7-126">Selecione **Relatório** para também enviar uma cópia da mensagem para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-126">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Relatar opções de relatório de lixo eletrônico ou phishing](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="c3ac7-128">Se você mudar de ideia, selecione **Desfazer** na notificação do notificação do notificação do jogo que aparecer.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-128">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="c3ac7-129">A mensagem permanece na pasta Caixa de Entrada.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-129">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="c3ac7-130">Relatar mensagens não spam da pasta Lixo eletrônico no Outlook para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="c3ac7-130">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="c3ac7-131">Na pasta Lixo eletrônico, use as etapas a seguir para relatar falsos positivos de spam:</span><span class="sxs-lookup"><span data-stu-id="c3ac7-131">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="c3ac7-132">Selecione uma ou mais mensagens.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-132">Select one or more messages.</span></span>
2. <span data-ttu-id="c3ac7-133">No canto superior direito, toque nos três pontos verticais.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-133">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="c3ac7-134">O menu de ação é aberto.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-134">The action menu opens.</span></span>

   ![Relatar que não é lixo eletrônico no menu de ação](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="c3ac7-136">Toque **em Não é lixo eletrônico.**</span><span class="sxs-lookup"><span data-stu-id="c3ac7-136">Tap **Not junk**.</span></span>

<span data-ttu-id="c3ac7-137">Uma notificação do notificação do jogo é exibida de que o email foi movido para sua Caixa de Entrada.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-137">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="c3ac7-138">Se você mudar de ideia, selecione **Desfazer** na notificação do notificação do jogo.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-138">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="c3ac7-139">O email permanece na pasta Lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c3ac7-139">The email remains in the Junk folder.</span></span>
