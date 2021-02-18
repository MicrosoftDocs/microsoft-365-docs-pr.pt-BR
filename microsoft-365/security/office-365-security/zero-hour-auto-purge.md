---
title: ZAP (Limpeza Automática Zero Hora)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre como a ZAP (limpeza automática zero hora) pode mover retroativamente as mensagens entregues em uma caixa de correio do Exchange Online para a pasta Lixo Eletrônico ou quarentena que são retroativamente encontradas como spam ou phishing.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287300"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="b6b4e-103">ZAP (Limpeza Automática Zero Hora) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b6b4e-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

<span data-ttu-id="b6b4e-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="b6b4e-104">**Applies to**</span></span>
- [<span data-ttu-id="b6b4e-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b6b4e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b6b4e-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b6b4e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b6b4e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6b4e-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="b6b4e-108">Recursos básicos da ZAP</span><span class="sxs-lookup"><span data-stu-id="b6b4e-108">Basic features of ZAP</span></span>

<span data-ttu-id="b6b4e-109">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, a ZAP (Limpeza Automática Zero Hora) é um recurso de proteção de email que detecta e limpa retroativamente mensagens mal-intencionadas de phishing, spam ou malware que já foram entregues às caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-109">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="b6b4e-110">A ZAP não funciona em ambientes autônomos do Exchange Online Protection (EOP) que protegem caixas de correio locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-110">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="b6b4e-111">Como a ZAP funciona</span><span class="sxs-lookup"><span data-stu-id="b6b4e-111">How ZAP works</span></span>

<span data-ttu-id="b6b4e-112">As assinaturas de spam e malware são atualizadas no serviço em tempo real diariamente.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-112">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="b6b4e-113">No entanto, os usuários ainda podem receber mensagens mal-intencionadas por vários motivos, incluindo se o conteúdo é endossado após ser entregue aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-113">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="b6b4e-114">A ZAP resolve esse problema monitorando continuamente as atualizações das assinaturas de spam e malware no serviço.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-114">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="b6b4e-115">A ZAP pode encontrar e remover mensagens que já estão na caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-115">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="b6b4e-116">A ação zap é perfeita para o usuário; eles não serão notificados se uma mensagem for detectada e movida.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-116">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="b6b4e-117">[Listas de remetentes seguros,](create-safe-sender-lists-in-office-365.md)regras de fluxo de emails (também conhecidas como regras de transporte), regras de Caixa de Entrada ou filtros adicionais têm precedência sobre a ZAP.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-117">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="b6b4e-118">Semelhante ao que acontece no fluxo de emails, isso significa que, mesmo que o serviço determine que a mensagem entregue precisa da ZAP, a mensagem não é agida devido à configuração de remententes seguros.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-118">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="b6b4e-119">Esse é outro motivo para ter cuidado com a configuração de mensagens para ignorar a filtragem.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-119">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="b6b4e-120">Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="b6b4e-120">Malware ZAP</span></span>

<span data-ttu-id="b6b4e-121">Para **mensagens lidas ou não lidas** que contêm malware após a entrega, a ZAP coloca em quarentena a mensagem que contém o anexo de malware.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-121">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="b6b4e-122">Somente os administradores podem exibir e gerenciar mensagens de malware da quarentena.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-122">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="b6b4e-123">A ZAP de malware é habilitada por padrão em políticas anti-malware.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-123">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="b6b4e-124">Para obter mais informações, [consulte Configurar políticas anti-malware no EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b6b4e-124">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="b6b4e-125">ZAP de phishing</span><span class="sxs-lookup"><span data-stu-id="b6b4e-125">Phish ZAP</span></span>

<span data-ttu-id="b6b4e-126">Para  mensagens lidas ou não lidas que são identificadas como phishing após a entrega, o resultado da ZAP depende da ação configurada para um veredito de filtragem de email de **phishing** na política anti-spam aplicável.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-126">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="b6b4e-127">As ações de veredito de filtragem disponíveis para phishing e seus possíveis resultados da ZAP são descritas na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="b6b4e-127">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="b6b4e-128">**Adicione X-Header**, **coloque a linha de assunto com texto:** a ZAP não faz nada com a mensagem.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-128">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="b6b4e-129">**Mover mensagem para** Lixo Eletrônico: a ZAP move a mensagem para a pasta Lixo Eletrônico, desde que a regra de lixo eletrônico seja habilitada na caixa de correio (ela é habilitada por padrão).</span><span class="sxs-lookup"><span data-stu-id="b6b4e-129">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b6b4e-130">Para obter mais informações, consulte [Definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="b6b4e-130">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="b6b4e-131">**Redirecionar mensagem para endereço de email**, Excluir **mensagem**, Mensagem **de quarentena:** ZAP coloca a mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-131">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="b6b4e-132">Por padrão, a ZAP de phishing está habilitada em políticas anti-spam, e a ação padrão para o veredito de filtragem de email de phishing é a mensagem de **quarentena,** o que significa que a ZAP de **phishing** coloca a mensagem em quarentena por padrão.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-132">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="b6b4e-133">Para obter mais informações sobre como configurar vereditos de filtragem de spam, consulte Configurar políticas [anti-spam no Microsoft 365.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b6b4e-133">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="b6b4e-134">Spam ZAP</span><span class="sxs-lookup"><span data-stu-id="b6b4e-134">Spam ZAP</span></span>

<span data-ttu-id="b6b4e-135">Para **mensagens não** lidas identificadas como spam após a entrega, o resultado da ZAP depende da ação configurada para o veredito de filtragem de **spam** na política anti-spam aplicável.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-135">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="b6b4e-136">As ações de veredito de filtragem disponíveis para spam e seus possíveis resultados da ZAP são descritas na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="b6b4e-136">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="b6b4e-137">**Adicione X-Header**, **coloque a linha de assunto com texto:** a ZAP não faz nada com a mensagem.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-137">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="b6b4e-138">**Mover mensagem para** Lixo Eletrônico: a ZAP move a mensagem para a pasta Lixo Eletrônico, desde que a regra de lixo eletrônico seja habilitada na caixa de correio (ela é habilitada por padrão).</span><span class="sxs-lookup"><span data-stu-id="b6b4e-138">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b6b4e-139">Para obter mais informações, consulte [Definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="b6b4e-139">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="b6b4e-140">**Redirecionar mensagem para endereço de email**, Excluir **mensagem**, Mensagem **de quarentena:** ZAP coloca a mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-140">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="b6b4e-141">Os usuários finais podem exibir e gerenciar suas próprias mensagens em quarentena de spam.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-141">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="b6b4e-142">Por padrão, a ZAP de spam é habilitada em políticas anti-spam, e a ação padrão  para o veredito de filtragem de **spam** é Mover mensagem para a pasta Lixo **Eletrônico,** o que significa que a ZAP de spam move as mensagens não lidas para a pasta Lixo Eletrônico por padrão.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-142">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="b6b4e-143">Para obter mais informações sobre como configurar vereditos de filtragem de spam, consulte Configurar políticas [anti-spam no Microsoft 365.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b6b4e-143">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="b6b4e-144">Considerações da ZAP para o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b6b4e-144">ZAP considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b6b4e-145">A ZAP não colocará em quarentena [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) qualquer mensagem que está no processo de verificação de Entrega Dinâmica em Anexos Seguros ou em que a filtragem de malware do EOP já substituiu o anexo pelo arquivo de Text.txtalerta **de malware.**</span><span class="sxs-lookup"><span data-stu-id="b6b4e-145">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="b6b4e-146">Se um sinal de phishing ou spam for recebido para esses tipos de mensagens e o veredito de filtragem na política anti-spam estiver definido para tomar alguma providência na mensagem (Mover para Lixo Eletrônico, Redirecionar, Excluir ou Quarentena), a ZAP assumirá como padrão uma ação "Mover para Lixo Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="b6b4e-146">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="b6b4e-147">Como ver se a ZAP moveu sua mensagem</span><span class="sxs-lookup"><span data-stu-id="b6b4e-147">How to see if ZAP moved your message</span></span>

<span data-ttu-id="b6b4e-148">Para determinar se a ZAP moveu sua mensagem, você pode usar o relatório [de Status](view-email-security-reports.md#threat-protection-status-report) de Proteção contra Ameaças ou o Explorador de Ameaças [(e detecções](threat-explorer.md)em tempo real).</span><span class="sxs-lookup"><span data-stu-id="b6b4e-148">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="b6b4e-149">Observe que, como uma ação do sistema, a ZAP não é registrada nos logs de auditoria de caixa de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-149">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="b6b4e-150">Perguntas frequentes sobre a ZAP</span><span class="sxs-lookup"><span data-stu-id="b6b4e-150">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="b6b4e-151">O que acontece se uma mensagem legítima for movida para a pasta Lixo Eletrônico?</span><span class="sxs-lookup"><span data-stu-id="b6b4e-151">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="b6b4e-152">Você deve seguir o processo de relatório normal [para falsos positivos.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="b6b4e-152">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="b6b4e-153">A única razão pela qual a mensagem seria movida da Caixa de Entrada para a pasta Lixo Eletrônico seria porque o serviço determinou que a mensagem era spam ou mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-153">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="b6b4e-154">E se eu usar a pasta Quarentena em vez da pasta Lixo Eletrônico?</span><span class="sxs-lookup"><span data-stu-id="b6b4e-154">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="b6b4e-155">A ZAP tomará medidas em uma mensagem com base na configuração de suas políticas anti-spam, conforme descrito anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-155">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this article.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="b6b4e-156">E se eu estiver usando remetentes seguros, regras de fluxo de emails ou listas de remetentes permitidos/bloqueados?</span><span class="sxs-lookup"><span data-stu-id="b6b4e-156">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="b6b4e-157">Os envios seguros, as regras de fluxo de emails ou o bloqueio e permitem que as configurações organizacionais precedam.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-157">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="b6b4e-158">Essas mensagens são excluídas da ZAP, pois o serviço está fazendo o que você configurou para fazer.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-158">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="b6b4e-159">Esse é outro motivo para ter cuidado com a configuração de mensagens para ignorar a filtragem.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-159">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="b6b4e-160">E se uma mensagem for movida para outra pasta (por exemplo, regras da Caixa de Entrada)?</span><span class="sxs-lookup"><span data-stu-id="b6b4e-160">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="b6b4e-161">A ZAP ainda funciona desde que a mensagem não tenha sido excluída, ou desde que a mesma ação, ou mais forte, ainda não tenha sido aplicada.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-161">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="b6b4e-162">Por exemplo, se a política anti-phishing estiver definida como quarentena e a mensagem já estiver no Lixo Eletrônico, a ZAP tomará medidas para colocar a mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-162">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="b6b4e-163">Como a ZAP afeta as caixas de correio em espera?</span><span class="sxs-lookup"><span data-stu-id="b6b4e-163">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="b6b4e-164">A ZAP não colocará em quarentena as mensagens de caixas de correio em espera.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-164">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="b6b4e-165">A ZAP pode mover mensagens para a pasta Lixo Eletrônico com base na ação configurada para um veredito de spam ou phishing em políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="b6b4e-165">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="b6b4e-166">Para obter mais informações sobre retém no Exchange Online, consulte [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span><span class="sxs-lookup"><span data-stu-id="b6b4e-166">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
