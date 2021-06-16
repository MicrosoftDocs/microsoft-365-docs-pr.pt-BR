---
title: Enviar mensagens manualmente à Microsoft para análise
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Os administradores e usuários finais podem aprender como enviar mensagens de email (emails bons marcados como emails ruins ou ruins permitidos) para análise da Microsoft.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d277df764ce2fb135f11c6320bc990e4d4142d6
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929762"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="8fd84-103">Enviar mensagens manualmente à Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="8fd84-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8fd84-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="8fd84-104">**Applies to**</span></span>
- [<span data-ttu-id="8fd84-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8fd84-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8fd84-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8fd84-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8fd84-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fd84-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="8fd84-108">Se você for um administrador em uma organização com Exchange Online caixas de correio, recomendamos que você use o portal Envios no portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8fd84-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="8fd84-109">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="8fd84-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="8fd84-110">Pode ser frustrante quando os usuários em sua organização recebem mensagens de lixo eletrônico (spam) ou mensagens de phishing em sua Caixa de Entrada ou se eles não recebem uma mensagem de email legítima porque ela é marcada como lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8fd84-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="8fd84-111">Estamos constantemente ajustando nossos filtros de spam para ser mais preciso.</span><span class="sxs-lookup"><span data-stu-id="8fd84-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="8fd84-112">Você e seus usuários podem ajudar nesse processo enviando falsos positivos (emails bons marcados como ruins), falsos negativos (emails ruins permitidos) e mensagens de phishing para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="8fd84-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="8fd84-113">Devido ao alto volume de envios que recebemos, talvez não seja possível responder a todas as solicitações de análise.</span><span class="sxs-lookup"><span data-stu-id="8fd84-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="8fd84-114">Enviar falsos negativos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="8fd84-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="8fd84-115">Em vez de usar os procedimentos a seguir para relatar falsos negativos, os usuários do Outlook e do Outlook na Web (anteriormente conhecidos como Outlook Web App) podem usar o complemento Mensagem de Relatório ou o complemento Relatar Phishing.</span><span class="sxs-lookup"><span data-stu-id="8fd84-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="8fd84-116">Para obter informações sobre como instalar e usar essas ferramentas, consulte [Enable the Report Message add-in](enable-the-report-message-add-in.md) and Enable the Report [Phishing add-in](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="8fd84-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="8fd84-117">Se você receber uma mensagem que passou pela filtragem de spam que deveria ter sido identificada como spam ou phishing, poderá enviar a mensagem para as equipes de Análise de Spam da Microsoft e análise de phishing da Microsoft, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="8fd84-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="8fd84-118">Os analistas revisarão a mensagem e a adicionarão aos filtros de todo o serviço se atenderem aos critérios de classificação.</span><span class="sxs-lookup"><span data-stu-id="8fd84-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="8fd84-119">Crie uma nova mensagem de email em branco com um dos seguintes destinatários:</span><span class="sxs-lookup"><span data-stu-id="8fd84-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="8fd84-120">**Lixo** eletrônico : `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="8fd84-120">**Junk**: `junk@office365.microsoft.com`</span></span>
   - <span data-ttu-id="8fd84-121">**Phishing**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="8fd84-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="8fd84-122">Arraste e solte o lixo eletrônico ou a mensagem de phishing na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="8fd84-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="8fd84-123">Isso salvará o lixo eletrônico ou a mensagem de phishing como um anexo na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="8fd84-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="8fd84-124">Não copie e colar o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os headers da mensagem).</span><span class="sxs-lookup"><span data-stu-id="8fd84-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="8fd84-125">Você pode anexar várias mensagens na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="8fd84-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="8fd84-126">Certifique-se de que todas as mensagens sejam do mesmo tipo: mensagens de phishing ou mensagens de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8fd84-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="8fd84-127">Deixe o corpo da nova mensagem vazio.</span><span class="sxs-lookup"><span data-stu-id="8fd84-127">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="8fd84-128">Use os formatos .msg (formato padrão Outlook) ou .eml (padrão Outlook no formato Web) para as mensagens anexadas.</span><span class="sxs-lookup"><span data-stu-id="8fd84-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="8fd84-129">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8fd84-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="8fd84-130">Os administradores têm várias maneiras diferentes de bloquear mensagens específicas que estão sendo identificadas como spam.</span><span class="sxs-lookup"><span data-stu-id="8fd84-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="8fd84-131">Para obter detalhes, consulte [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="8fd84-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="8fd84-132">Enviar falsos positivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="8fd84-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="8fd84-133">Em vez de usar os procedimentos a seguir para relatar falsos positivos, os usuários do Outlook e do Outlook na Web (anteriormente conhecidos como Outlook Web App) podem usar o complemento Mensagem de Relatório ou o complemento Relatar Phishing.</span><span class="sxs-lookup"><span data-stu-id="8fd84-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="8fd84-134">Para obter informações sobre como instalar e usar essas ferramentas, consulte [Enable the Report Message add-in](enable-the-report-message-add-in.md) and Enable the Report [Phishing add-in](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="8fd84-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="8fd84-135">Se uma mensagem foi identificada incorretamente como spam, você pode enviar a mensagem para a Equipe de Análise de Spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8fd84-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="8fd84-136">Os analistas avaliarão a mensagem e (dependendo dos resultados da análise) os filtros de todo o serviço podem ser ajustados para permitir a passagem da mensagem.</span><span class="sxs-lookup"><span data-stu-id="8fd84-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="8fd84-137">Crie uma nova mensagem de email em `not_junk@office365.microsoft.com` branco com como destinatário.</span><span class="sxs-lookup"><span data-stu-id="8fd84-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient.</span></span>

2. <span data-ttu-id="8fd84-138">Arraste e solte a mensagem não identificada na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="8fd84-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="8fd84-139">Isso salvará a mensagem identificada como um anexo na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="8fd84-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="8fd84-140">Não copie e colar o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os headers da mensagem).</span><span class="sxs-lookup"><span data-stu-id="8fd84-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="8fd84-141">Você pode anexar várias mensagens na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="8fd84-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="8fd84-142">Certifique-se de que todas as mensagens sejam do mesmo tipo: mensagens de phishing ou mensagens de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8fd84-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="8fd84-143">Deixe o corpo da nova mensagem vazio.</span><span class="sxs-lookup"><span data-stu-id="8fd84-143">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="8fd84-144">Use os formatos .msg (formato padrão Outlook) ou .eml (padrão Outlook no formato Web) para as mensagens anexadas.</span><span class="sxs-lookup"><span data-stu-id="8fd84-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="8fd84-145">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8fd84-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="8fd84-146">Os administradores têm várias maneiras diferentes de permitir que mensagens específicas ignorem a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="8fd84-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="8fd84-147">Para obter detalhes, consulte [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="8fd84-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="8fd84-148">Onde os dados de envios para a Microsoft são armazenados?</span><span class="sxs-lookup"><span data-stu-id="8fd84-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="8fd84-149">Os dados residem no limite Office 365 conformidade nos data centers norte-americanos.</span><span class="sxs-lookup"><span data-stu-id="8fd84-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="8fd84-150">Os dados são revisados por analistas na equipe de engenharia para ajudar a melhorar a eficácia dos filtros.</span><span class="sxs-lookup"><span data-stu-id="8fd84-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="8fd84-151">Criar uma regra de fluxo de emails para receber cópias de mensagens relatadas à Microsoft</span><span class="sxs-lookup"><span data-stu-id="8fd84-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="8fd84-152">Para obter instruções, [consulte Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="8fd84-152">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
