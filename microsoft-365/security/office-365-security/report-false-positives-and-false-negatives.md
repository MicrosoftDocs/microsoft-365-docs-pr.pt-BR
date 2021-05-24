---
title: Relatar falsos positivos e falsos negativos no Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Saiba como relatar falsos positivos e falsos negativos no Outlook usando o recurso Mensagem de Relatório.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f8c4fc327bfd467cdd1d0043c454e222e84125c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625108"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="0699b-103">Relatar falsos positivos e falsos negativos no Outlook</span><span class="sxs-lookup"><span data-stu-id="0699b-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0699b-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="0699b-104">**Applies to**</span></span>
- [<span data-ttu-id="0699b-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0699b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0699b-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0699b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0699b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0699b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="0699b-108">Se você for um administrador em uma organização Microsoft 365 com caixas de correio Exchange Online, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="0699b-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="0699b-109">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="0699b-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="0699b-110">Em organizações com caixas de correio em Exchange Online ou caixas de correio locais usando autenticação moderna híbrida, você pode enviar falsos positivos (bons emails bloqueados ou enviados para a pasta de lixo eletrônico) e falsos negativos (email indesejado ou phishing que foi entregue à caixa de entrada) para Proteção do Exchange Online (EOP). Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0699b-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0699b-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="0699b-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0699b-112">Para a melhor experiência de envio do usuário, use o complemento Mensagem de Relatório ou o complemento Relatar Phishing.</span><span class="sxs-lookup"><span data-stu-id="0699b-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="0699b-113">Observe que esse complemento funciona para Outlook em todas as plataformas— na Web, iOS, Android e Área de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="0699b-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="0699b-114">Se você for um administrador em uma organização com Exchange Online caixas de correio, use o portal Envios no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="0699b-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="0699b-115">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="0699b-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="0699b-116">Você pode configurar para enviar mensagens diretamente para a Microsoft, uma caixa de correio especificada ou ambas.</span><span class="sxs-lookup"><span data-stu-id="0699b-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="0699b-117">Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="0699b-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="0699b-118">Para obter mais informações sobre como obter e habilitar a Mensagem de Relatório ou os complementos de Phishing de Relatório, consulte [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="0699b-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="0699b-119">Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="0699b-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="0699b-120">Usar o recurso Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="0699b-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="0699b-121">Relatar mensagens de lixo eletrônico e phishing</span><span class="sxs-lookup"><span data-stu-id="0699b-121">Report junk and phishing messages</span></span>

<span data-ttu-id="0699b-122">Para mensagens na Caixa de Entrada ou em qualquer outra pasta de email, exceto Lixo Eletrônico, use o seguinte método para relatar mensagens de spam e phishing:</span><span class="sxs-lookup"><span data-stu-id="0699b-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="0699b-123">Clique nas **releições** Mais ações no canto superior direito  da mensagem selecionada, clique em Relatar mensagem no menu suspenso e selecione **Lixo** Eletrônico ou **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="0699b-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0699b-124">![Mensagem de Relatório - Mais ações](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="0699b-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0699b-125">![Mensagem de Relatório - Lixo Eletrônico e Phishing](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="0699b-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="0699b-126">As mensagens selecionadas serão enviadas à Microsoft para análise e:</span><span class="sxs-lookup"><span data-stu-id="0699b-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="0699b-127">Movido para a pasta Lixo Eletrônico se tiver sido relatado como spam.</span><span class="sxs-lookup"><span data-stu-id="0699b-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="0699b-128">Excluído se tiver sido relatado como phishing.</span><span class="sxs-lookup"><span data-stu-id="0699b-128">Deleted if it was reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="0699b-129">Relatar mensagens que não são lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="0699b-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="0699b-130">Clique nas **releições** Mais ações no canto superior direito  da mensagem selecionada, clique em Relatar mensagem no menu suspenso e clique em **Não Lixo Eletrônico.**</span><span class="sxs-lookup"><span data-stu-id="0699b-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0699b-131">![Mensagem de Relatório - Mais ações](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="0699b-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0699b-132">![Mensagem de relatório - Não lixo eletrônico](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="0699b-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="0699b-133">A mensagem selecionada será enviada à Microsoft para análise e movida para a Caixa de Entrada ou qualquer outra pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="0699b-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="0699b-134">Exibir e revisar mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="0699b-134">View and review reported messages</span></span>

<span data-ttu-id="0699b-135">Para revisar as mensagens relatadas pelos usuários à Microsoft, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="0699b-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="0699b-136">Use o portal Envios de Administrador.</span><span class="sxs-lookup"><span data-stu-id="0699b-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="0699b-137">Para obter mais informações, consulte [Exibir envios de usuários para a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="0699b-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="0699b-138">Crie uma regra de fluxo de emails (também conhecida como regra de transporte) para enviar cópias de mensagens relatadas.</span><span class="sxs-lookup"><span data-stu-id="0699b-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="0699b-139">Para obter instruções, [consulte Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="0699b-139">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
