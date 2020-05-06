---
title: Limpeza automática de zero horas (ZAP)-recurso de proteção de email
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
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
description: Saiba mais sobre exclusão automática de zero horas (ZAP), um recurso de proteção de email no Microsoft 365 que detecta spam, malware ou mensagens de phishing que já foram entregues ao Exchange Online.
ms.openlocfilehash: a6f21147e7beaadb3aa6430b299dea8b248561c1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034921"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-microsoft-365"></a><span data-ttu-id="64a7d-103">Limpeza automática de zero horas (ZAP)-proteção contra spam e malware no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="64a7d-103">Zero-hour auto purge (ZAP) - protection against spam and malware in Microsoft 365</span></span>

## <a name="overview"></a><span data-ttu-id="64a7d-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="64a7d-104">Overview</span></span>

<span data-ttu-id="64a7d-105">A limpeza automática de zero horas (ZAP) é um recurso de proteção de email no Microsoft 365 que detecta retroativamente e neutralizes mensagens de malware, spam ou malware mal-intencionadas que já foram entregues às caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="64a7d-105">Zero-hour auto purge (ZAP) is an email protection feature in Microsoft 365 that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="64a7d-106">O ZAP está disponível com a proteção do Exchange Online (EOP) padrão que está incluída em qualquer assinatura do Microsoft 365 que contenha caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="64a7d-106">ZAP is available with the default Exchange Online Protection (EOP) that's included with any Microsoft 365 subscription that contains Exchange Online mailboxes.</span></span> <span data-ttu-id="64a7d-107">ZAP não funciona em ambientes autônomos do EOP que protegem caixas de correio locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="64a7d-107">ZAP doesn't work in standalone EOP environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="64a7d-108">Como o ZAP funciona</span><span class="sxs-lookup"><span data-stu-id="64a7d-108">How ZAP works</span></span>

<span data-ttu-id="64a7d-109">A Microsoft 365 atualiza as assinaturas de spam e malware em tempo real diariamente.</span><span class="sxs-lookup"><span data-stu-id="64a7d-109">Microsoft 365 updates spam and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="64a7d-110">No entanto, os usuários ainda podem receber mensagens mal-intencionadas por vários motivos, incluindo se o conteúdo é enarmado depois de ser entregue aos usuários.</span><span class="sxs-lookup"><span data-stu-id="64a7d-110">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="64a7d-111">O ZAP aborda esse problema, monitorando continuamente as atualizações para as assinaturas de malware e spam do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="64a7d-111">ZAP addresses this issue by continually monitoring updates to the Microsoft 365 spam and malware signatures.</span></span> <span data-ttu-id="64a7d-112">ZAP pode localizar e remover mensagens que já estão na caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="64a7d-112">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="64a7d-113">A ação ZAP é direta para o usuário; Eles não são notificados quando uma mensagem é detectada e movida.</span><span class="sxs-lookup"><span data-stu-id="64a7d-113">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="64a7d-114">[Listas de remetentes seguros](create-safe-sender-lists-in-office-365.md), regras de fluxo de emails (também conhecidas como regras de transporte), regras de caixa de entrada ou filtros adicionais têm precedência sobre o zap.</span><span class="sxs-lookup"><span data-stu-id="64a7d-114">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="64a7d-115">ZAP de malware</span><span class="sxs-lookup"><span data-stu-id="64a7d-115">Malware ZAP</span></span>

<span data-ttu-id="64a7d-116">Para **mensagens de leitura ou não lidas** que são encontradas para conter malware após a entrega, zap coloca em quarentena a mensagem que contém o anexo de malware.</span><span class="sxs-lookup"><span data-stu-id="64a7d-116">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="64a7d-117">Somente os administradores podem exibir e gerenciar mensagens de malware da quarentena.</span><span class="sxs-lookup"><span data-stu-id="64a7d-117">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="64a7d-118">O malware ZAP é habilitado por padrão em políticas antimalware.</span><span class="sxs-lookup"><span data-stu-id="64a7d-118">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="64a7d-119">Para obter mais informações, consulte [Configure anti-malware Policies in Microsoft 365](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="64a7d-119">For more information, see [Configure anti-malware policies in Microsoft 365](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="64a7d-120">Phish de phishing</span><span class="sxs-lookup"><span data-stu-id="64a7d-120">Phish ZAP</span></span>

<span data-ttu-id="64a7d-121">Para **mensagens de leitura ou não lidas** que são identificadas como Phish após a entrega, o resultado de zap depende da ação que é configurada para um veredicto de filtragem de **email de phishing** na política antispam aplicável.</span><span class="sxs-lookup"><span data-stu-id="64a7d-121">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="64a7d-122">As ações de filtragem de veredicto disponíveis para o Phish e seus possíveis resultados de ZAP são descritos na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="64a7d-122">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="64a7d-123">**Adicionar cabeçalho X**, **preceder a linha de assunto com o texto**: zap não realiza nenhuma ação na mensagem.</span><span class="sxs-lookup"><span data-stu-id="64a7d-123">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="64a7d-124">**Mover mensagem para o lixo eletrônico**: zap move a mensagem para a pasta lixo eletrônico, contanto que a regra de lixo eletrônico esteja habilitada na caixa de correio (habilitada por padrão).</span><span class="sxs-lookup"><span data-stu-id="64a7d-124">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="64a7d-125">Para obter mais informações, consulte [Configurar definições de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="64a7d-125">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="64a7d-126">**Redirecionar mensagem para endereço de email**, **Excluir mensagem**, **mensagem de quarentena**: zap coloca a mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="64a7d-126">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="64a7d-127">Somente os administradores podem exibir e gerenciar mensagens em quarentena de phishing.</span><span class="sxs-lookup"><span data-stu-id="64a7d-127">Only admins can view and manage phish quarantined messages.</span></span>

<span data-ttu-id="64a7d-128">Por padrão, o phishing ZAP está habilitado em políticas antispam, e a ação padrão para o filtro de filtragem de **email de phishing** veredicto é uma **mensagem em quarentena**, o que significa que o Phish zap coloca a mensagem por padrão.</span><span class="sxs-lookup"><span data-stu-id="64a7d-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="64a7d-129">Para obter mais informações sobre a configuração do filtro de spam verdicts, consulte [Configure anti-spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="64a7d-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="64a7d-130">ZAP de spam</span><span class="sxs-lookup"><span data-stu-id="64a7d-130">Spam ZAP</span></span>

<span data-ttu-id="64a7d-131">Para **mensagens não lidas** identificadas como spam após a entrega, o resultado de zap depende da ação configurada para o veredicto de filtragem de **spam** na política antispam aplicável.</span><span class="sxs-lookup"><span data-stu-id="64a7d-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="64a7d-132">As ações de filtragem de veredicto para spam e seus possíveis resultados de ZAP são descritas na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="64a7d-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="64a7d-133">**Adicionar cabeçalho X**, **preceder a linha de assunto com o texto**: zap não realiza nenhuma ação na mensagem.</span><span class="sxs-lookup"><span data-stu-id="64a7d-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="64a7d-134">**Mover mensagem para o lixo eletrônico**: zap move a mensagem para a pasta lixo eletrônico, contanto que a regra de lixo eletrônico esteja habilitada na caixa de correio (habilitada por padrão).</span><span class="sxs-lookup"><span data-stu-id="64a7d-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="64a7d-135">Para obter mais informações, consulte [Configurar definições de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="64a7d-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="64a7d-136">**Redirecionar mensagem para endereço de email**, **Excluir mensagem**, **mensagem de quarentena**: zap coloca a mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="64a7d-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="64a7d-137">Os usuários finais podem exibir e gerenciar suas próprias mensagens em quarentena de spam.</span><span class="sxs-lookup"><span data-stu-id="64a7d-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="64a7d-138">Por padrão, o lixo de spam está habilitado em políticas antispam, e a ação padrão para o veredicto de filtragem de **spam** é **mover a mensagem para a pasta lixo eletrônico**, o que significa que o lixo de spam move as mensagens **não lidas** para a pasta lixo eletrônico por padrão.</span><span class="sxs-lookup"><span data-stu-id="64a7d-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="64a7d-139">Para obter mais informações sobre a configuração do filtro de spam verdicts, consulte [Configure anti-spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="64a7d-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a><span data-ttu-id="64a7d-140">Considerações de ZAP para a proteção avançada contra ameaças do Office 365 (ATP)</span><span class="sxs-lookup"><span data-stu-id="64a7d-140">ZAP considerations for Office 365 Advanced Threat Protection (ATP)</span></span>

<span data-ttu-id="64a7d-141">ZAP não colocará em quarentena qualquer mensagem que esteja no processo de varredura [dinâmica da entrega](dynamic-delivery-and-previewing.md) , ou em que a filtragem de malware já tenha substituído o anexo com o arquivo **Text. txt de alerta de malware** .</span><span class="sxs-lookup"><span data-stu-id="64a7d-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="64a7d-142">Se um sinal de phishing ou spam for recebido para esses tipos de mensagens, e a veredicto de filtragem na política antispam estiver definida para executar alguma ação na mensagem (mover para lixo eletrônico, redirecionar, excluir, quarentena), ZAP será o padrão para uma ação mover para lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="64a7d-142">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="64a7d-143">Como ver se ZAP moveu a mensagem</span><span class="sxs-lookup"><span data-stu-id="64a7d-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="64a7d-144">Para determinar se o ZAP moveu a mensagem, você pode usar o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report) ou o [Explorador de ameaças (e detecções em tempo real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="64a7d-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="64a7d-145">Observe que, como uma ação do sistema, ZAP não é registrado nos logs de auditoria de caixa de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="64a7d-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="64a7d-146">FAQ DE ZAP</span><span class="sxs-lookup"><span data-stu-id="64a7d-146">ZAP FAQ</span></span>

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="64a7d-147">P: o que acontece quando uma mensagem legítima é movida para a pasta lixo eletrônico?</span><span class="sxs-lookup"><span data-stu-id="64a7d-147">Q: What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="64a7d-148">A: você deve seguir o processo de relatório normal para [falsos positivos](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="64a7d-148">A: You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="64a7d-149">A única razão pela qual a mensagem seria movida da caixa de entrada para a pasta lixo eletrônico seria porque o serviço determinou que a mensagem era spam ou mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="64a7d-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="q-what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="64a7d-150">P: e se eu usar a pasta quarentena em vez da pasta lixo eletrônico?</span><span class="sxs-lookup"><span data-stu-id="64a7d-150">Q: What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="64a7d-151">Um: ZAP executará uma ação em uma mensagem com base na configuração de suas políticas antispam, conforme descrito anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="64a7d-151">A: ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="64a7d-152">P: e se eu estiver usando regras de fluxo de email ou listas de remetentes permitidos/bloqueados?</span><span class="sxs-lookup"><span data-stu-id="64a7d-152">Q: What if I'm using mail flow rules or allowed/blocked sender lists?</span></span>

<span data-ttu-id="64a7d-153">A: regras de fluxo de emails ou bloqueio e permitir configurações organizacionais têm precedência.</span><span class="sxs-lookup"><span data-stu-id="64a7d-153">A: Mail flow rules or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="64a7d-154">Essas mensagens são excluídas de ZAP.</span><span class="sxs-lookup"><span data-stu-id="64a7d-154">These messages are excluded from ZAP.</span></span>

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="64a7d-155">P: e se uma mensagem for movida para outra pasta (por exemplo, regras de caixa de entrada)?</span><span class="sxs-lookup"><span data-stu-id="64a7d-155">Q: What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="64a7d-156">A: ZAP ainda funciona desde que a mensagem não tenha sido excluída, ou desde que a mesma ação, ou mais forte, ainda não tenha sido aplicada.</span><span class="sxs-lookup"><span data-stu-id="64a7d-156">A:  ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="64a7d-157">Por exemplo, se a política de phishing estiver definida como quarentena e o usuário ou administrador já tiver desenviado o email, a quarentena executará uma ação para colocar em quarentena o arquivo.</span><span class="sxs-lookup"><span data-stu-id="64a7d-157">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="q-does-zap-change-the-message-header"></a><span data-ttu-id="64a7d-158">P: a ZAP altera o cabeçalho da mensagem?</span><span class="sxs-lookup"><span data-stu-id="64a7d-158">Q: Does ZAP change the message header?</span></span>

<span data-ttu-id="64a7d-159">A: uma ação ZAP não faz qualquer alteração no cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="64a7d-159">A: A ZAP action does not make any changes to the message header.</span></span>

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="64a7d-160">P: como o ZAP afeta caixas de correio em espera?</span><span class="sxs-lookup"><span data-stu-id="64a7d-160">Q: How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="64a7d-161">A: ZAP não colocará em quarentena as mensagens de caixas de correio em espera.</span><span class="sxs-lookup"><span data-stu-id="64a7d-161">A: ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="64a7d-162">ZAP pode mover mensagens para a pasta lixo eletrônico com base na ação configurada para um spam ou veredicto de phishing em políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="64a7d-162">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="64a7d-163">Para obter mais informações sobre isenções no Exchange Online, consulte [bloqueio in-loco e retenção de litígio no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span><span class="sxs-lookup"><span data-stu-id="64a7d-163">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
