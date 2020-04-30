---
title: Enviar mensagens manualmente para a Microsoft para análise
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Você e seus usuários podem enviar mensagens de spam falsas negativas e falsos positivos para a Microsoft para análise. '
ms.openlocfilehash: 928809a8d00e082bf3150abb27dc493c2b82c070
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939422"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="fcc10-103">Enviar mensagens manualmente para a Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="fcc10-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="fcc10-104">Se você for um administrador em uma organização do Microsoft 365 com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="fcc10-104">If you're an admin in an Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="fcc10-105">Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="fcc10-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="fcc10-106">Pode ser frustrante quando os usuários da sua organização recebem mensagens de lixo eletrônico (spam) ou mensagens de phishing em sua caixa de entrada ou se não recebem uma mensagem de email legítima porque estão marcados como lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="fcc10-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="fcc10-107">Estamos constantemente ajustando os nossos filtros de spam para serem mais precisos.</span><span class="sxs-lookup"><span data-stu-id="fcc10-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="fcc10-108">Você e seus usuários podem ajudar nesse processo enviando falsos positivos (emails satisfatórios marcados como defeituosos), falsos negativos (email incorreto) e mensagens de phishing para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="fcc10-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc10-109">Devido ao alto volume de envios que recebemos, talvez não seja possível atender a todas as solicitações para análise.</span><span class="sxs-lookup"><span data-stu-id="fcc10-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="fcc10-110">Enviar falsos negativos para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fcc10-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="fcc10-111">Em vez de usar os procedimentos a seguir para relatar falsos negativos, os usuários do Outlook e do Outlook na Web (anteriormente conhecido como Outlook Web App) podem usar o suplemento de mensagem de relatório para o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="fcc10-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="fcc10-112">Para obter informações sobre como instalar e usar essa ferramenta, consulte [habilitar o suplemento de mensagem de relatório](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="fcc10-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="fcc10-113">Se você receber uma mensagem que passa pelo filtro de spam que deve ter sido identificada como spam ou phishing, você pode enviar a mensagem para a análise de spam da Microsoft e para as equipes de análise de phishing da Microsoft, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="fcc10-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="fcc10-114">Os analistas revisarão a mensagem e a adicionarão aos filtros de todo o serviço se atenderem aos critérios de classificação.</span><span class="sxs-lookup"><span data-stu-id="fcc10-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="fcc10-115">Crie uma nova mensagem de email em branco com um dos seguintes destinatários:</span><span class="sxs-lookup"><span data-stu-id="fcc10-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="fcc10-116">**Lixo eletrônico**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="fcc10-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="fcc10-117">**Phishing**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="fcc10-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="fcc10-118">Arraste e solte a mensagem de lixo eletrônico ou phishing na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="fcc10-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="fcc10-119">Isso salvará o lixo eletrônico ou a mensagem de phishing como um anexo na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="fcc10-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="fcc10-120">Não copie e cole o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os cabeçalhos da mensagem).</span><span class="sxs-lookup"><span data-stu-id="fcc10-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="fcc10-121">Você pode anexar várias mensagens na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="fcc10-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="fcc10-122">Certifique-se de que todas as mensagens são do mesmo tipo: mensagens golpes de phishing ou mensagens de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="fcc10-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="fcc10-123">Deixe o corpo da nova mensagem vazio.</span><span class="sxs-lookup"><span data-stu-id="fcc10-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="fcc10-124">Use formatos. msg (formato padrão do Outlook) ou. eml (padrão Outlook no formato da Web) para as mensagens anexadas.</span><span class="sxs-lookup"><span data-stu-id="fcc10-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="fcc10-125">Quando tiver terminado, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="fcc10-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="fcc10-126">Os administradores têm várias maneiras diferentes de bloquear mensagens específicas que estão sendo inalgumas identificadas como spam.</span><span class="sxs-lookup"><span data-stu-id="fcc10-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="fcc10-127">Para obter detalhes, consulte [criar listas de remetentes bloqueados no Office 365](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="fcc10-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="fcc10-128">Enviar falsos positivos para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fcc10-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="fcc10-129">Em vez de usar os procedimentos a seguir para relatar falsos positivos, os usuários do Outlook e do Outlook na Web podem usar o suplemento de mensagem de relatório para o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="fcc10-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="fcc10-130">Para obter informações sobre como instalar e usar essa ferramenta, consulte [habilitar o suplemento de mensagem de relatório](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="fcc10-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="fcc10-131">Se uma mensagem foi identificada incorretamente como spam, você pode enviar a mensagem para a equipe de análise de spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fcc10-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="fcc10-132">Os analistas avaliarão a mensagem e (dependendo dos resultados da análise) os filtros de todo o serviço podem ser ajustados para permitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="fcc10-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="fcc10-133">Crie uma nova mensagem de email em branco `not_junk@office365.microsoft.com` com o destinatário:</span><span class="sxs-lookup"><span data-stu-id="fcc10-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="fcc10-134">Arraste e solte a mensagem inidentificada na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="fcc10-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="fcc10-135">Isso salvará a mensagem inidentificada como um anexo na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="fcc10-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="fcc10-136">Não copie e cole o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os cabeçalhos da mensagem).</span><span class="sxs-lookup"><span data-stu-id="fcc10-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="fcc10-137">Você pode anexar várias mensagens na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="fcc10-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="fcc10-138">Certifique-se de que todas as mensagens são do mesmo tipo: mensagens de phishing ou mensagens de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="fcc10-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="fcc10-139">Deixe o corpo da nova mensagem vazio.</span><span class="sxs-lookup"><span data-stu-id="fcc10-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="fcc10-140">Use formatos. msg (formato padrão do Outlook) ou. eml (padrão Outlook no formato da Web) para as mensagens anexadas.</span><span class="sxs-lookup"><span data-stu-id="fcc10-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="fcc10-141">Quando tiver terminado, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="fcc10-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="fcc10-142">Os administradores têm várias maneiras diferentes de permitir que mensagens específicas ignorem a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="fcc10-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="fcc10-143">Para obter detalhes, consulte [criar listas de remetentes seguros no Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="fcc10-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="fcc10-144">Criar uma regra de fluxo de email para receber cópias de mensagens relatadas para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fcc10-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="fcc10-145">Para obter instruções, consulte [usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="fcc10-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
