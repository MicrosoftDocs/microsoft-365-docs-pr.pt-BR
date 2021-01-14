---
title: Enviar mensagens manualmente à Microsoft para análise
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Administradores e usuários finais podem aprender a enviar mensagens de email (emails bons marcados como emails ruins ou ruins permitidos) para análise da Microsoft.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94747b1d0a1aef746a63abada977aa47270ae4e2
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865075"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="26769-103">Enviar mensagens manualmente à Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="26769-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="26769-104">Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos usar o portal de Envios no Centro de Conformidade e Segurança & Segurança.</span><span class="sxs-lookup"><span data-stu-id="26769-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="26769-105">Para obter mais informações, consulte Usar o Envio de Administrador [para enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="26769-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="26769-106">Pode ser frustrante quando os usuários em sua organização recebem mensagens de lixo eletrônico (spam) ou phishing em sua Caixa de Entrada, ou se eles não recebem uma mensagem de email legítima porque ela está marcada como lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="26769-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="26769-107">Estamos constantemente ajustando nossos filtros de spam para ser mais preciso.</span><span class="sxs-lookup"><span data-stu-id="26769-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="26769-108">Você e seus usuários podem ajudar nesse processo enviando falsos positivos (emails bons marcados como ruins), falsos negativos (emails falsos permitidos) e mensagens de phishing para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="26769-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="26769-109">Devido ao alto volume de envios que recebemos, talvez não seja possível responder a todas as solicitações de análise.</span><span class="sxs-lookup"><span data-stu-id="26769-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="26769-110">Enviar falsos negativos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="26769-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="26769-111">Em vez de usar os procedimentos a seguir para relatar falsos negativos, os usuários no Outlook e no Outlook na Web (anteriormente conhecido como Outlook Web App) podem usar o complemento Mensagem de Relatório ou o complemento Phishing de Relatório.</span><span class="sxs-lookup"><span data-stu-id="26769-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="26769-112">Para obter informações sobre como instalar [](enable-the-report-message-add-in.md) e usar essas ferramentas, consulte Habilitar o complemento Mensagem de Relatório e Habilitar o complemento [Phishing de Relatório.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="26769-112">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="26769-113">Se você receber uma mensagem que passou pela filtragem de spam que deveria ter sido identificada como spam ou phishing, você pode enviar a mensagem para as equipes de Análise de Spam da Microsoft e Análise de Phishing da Microsoft, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="26769-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="26769-114">Os analistas analisarão a mensagem e a adicionarão aos filtros de todo o serviço se atenderem aos critérios de classificação.</span><span class="sxs-lookup"><span data-stu-id="26769-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="26769-115">Crie uma nova mensagem de email em branco com um dos seguintes destinatários:</span><span class="sxs-lookup"><span data-stu-id="26769-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="26769-116">**Lixo eletrônico**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="26769-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="26769-117">**Phishing**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="26769-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="26769-118">Arraste e solte a mensagem de lixo eletrônico ou phishing na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="26769-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="26769-119">Isso salvará a mensagem de lixo eletrônico ou phishing como um anexo na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="26769-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="26769-120">Não copie e copie e copie o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para podermos inspecionar os títulos da mensagem).</span><span class="sxs-lookup"><span data-stu-id="26769-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="26769-121">Você pode anexar várias mensagens na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="26769-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="26769-122">Certifique-se de que todas as mensagens sejam do mesmo tipo: mensagens de phishing ou lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="26769-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="26769-123">Deixe o corpo da nova mensagem vazio.</span><span class="sxs-lookup"><span data-stu-id="26769-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="26769-124">Use os formatos .msg (formato padrão do Outlook) ou .eml (formato padrão do Outlook na Web) para as mensagens anexadas.</span><span class="sxs-lookup"><span data-stu-id="26769-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="26769-125">Quando terminar, clique em **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="26769-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="26769-126">Os administradores têm várias maneiras diferentes de bloquear mensagens específicas que estão sendo identificadas injustificadas como spam.</span><span class="sxs-lookup"><span data-stu-id="26769-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="26769-127">Para obter detalhes, [consulte Criar listas de remetentes bloqueados no EOP.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="26769-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="26769-128">Enviar falsos positivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="26769-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="26769-129">Em vez de usar os procedimentos a seguir para relatar falsos positivos, os usuários no Outlook e no Outlook na Web (anteriormente conhecido como Outlook Web App) podem usar o complemento Mensagem de Relatório ou o complemento Phishing de Relatório.</span><span class="sxs-lookup"><span data-stu-id="26769-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="26769-130">Para obter informações sobre como instalar [](enable-the-report-message-add-in.md) e usar essas ferramentas, consulte Habilitar o complemento Mensagem de Relatório e Habilitar o complemento [Phishing de Relatório.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="26769-130">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="26769-131">Se uma mensagem foi identificada incorretamente como spam, você pode enviar a mensagem para a Equipe de Análise de Spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26769-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="26769-132">Os analistas avaliarão a mensagem e (dependendo dos resultados da análise) os filtros de todo o serviço podem ser ajustados para permitir a passagem da mensagem.</span><span class="sxs-lookup"><span data-stu-id="26769-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="26769-133">Crie uma nova mensagem de email em `not_junk@office365.microsoft.com` branco com o destinatário:</span><span class="sxs-lookup"><span data-stu-id="26769-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="26769-134">Arraste e solte a mensagem identificada incompatibilidade na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="26769-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="26769-135">Isso salvará a mensagem identificada incompatibilidade como um anexo na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="26769-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="26769-136">Não copie e copie e copie o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para podermos inspecionar os títulos da mensagem).</span><span class="sxs-lookup"><span data-stu-id="26769-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="26769-137">Você pode anexar várias mensagens na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="26769-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="26769-138">Certifique-se de que todas as mensagens sejam do mesmo tipo: mensagens de phishing ou lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="26769-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="26769-139">Deixe o corpo da nova mensagem vazio.</span><span class="sxs-lookup"><span data-stu-id="26769-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="26769-140">Use os formatos .msg (formato padrão do Outlook) ou .eml (formato padrão do Outlook na Web) para as mensagens anexadas.</span><span class="sxs-lookup"><span data-stu-id="26769-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="26769-141">Quando terminar, clique em **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="26769-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="26769-142">Os administradores têm várias maneiras diferentes de permitir que mensagens específicas ignorem a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="26769-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="26769-143">Para obter detalhes, [consulte Criar listas de remetentes seguros no EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="26769-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="26769-144">Onde os dados dos envios para a Microsoft são armazenados?</span><span class="sxs-lookup"><span data-stu-id="26769-144">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="26769-145">Os dados residem no limite de conformidade do Office 365 nos data centers da América do Norte.</span><span class="sxs-lookup"><span data-stu-id="26769-145">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="26769-146">Os dados são revisados por analistas da equipe de engenharia para ajudar a melhorar a eficácia dos filtros.</span><span class="sxs-lookup"><span data-stu-id="26769-146">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="26769-147">Criar uma regra de fluxo de emails para receber cópias de mensagens que são relatadas à Microsoft</span><span class="sxs-lookup"><span data-stu-id="26769-147">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="26769-148">Para obter instruções, [confira Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="26769-148">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
