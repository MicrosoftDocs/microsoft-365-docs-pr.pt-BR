---
title: Limpeza automática zero hora – proteção contra spam e malware
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
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
description: A limpeza automática de zero horas (ZAP) é um recurso de proteção de email que detecta mensagens com spam ou malware que já foram entregues às caixas de entrada dos seus usuários e renderiza o conteúdo mal-intencionado inofensivo. Como o ZAP faz isso depende do tipo de conteúdo mal-intencionado detectado.
ms.openlocfilehash: f43826614def99f8807d8777f128d5bc66f7b46a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073346"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="15b67-104">Limpeza automática zero hora – proteção contra spam e malware</span><span class="sxs-lookup"><span data-stu-id="15b67-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="15b67-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="15b67-105">Overview</span></span>

<span data-ttu-id="15b67-106">A limpeza automática de zero horas (ZAP) é um recurso de proteção de email que detecta mensagens com phishing, spam ou malware que já foram entregues às caixas de entrada dos seus usuários e renderiza o conteúdo mal-intencionado inofensivo.</span><span class="sxs-lookup"><span data-stu-id="15b67-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="15b67-107">Como o ZAP depende do tipo de conteúdo mal-intencionado detectado; os emails podem ser zapped devido a conteúdo, URLs ou anexos de email.</span><span class="sxs-lookup"><span data-stu-id="15b67-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="15b67-108">O ZAP está disponível com a proteção do Exchange Online padrão incluída em qualquer assinatura do Office 365 que contenha caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="15b67-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="15b67-109">O ZAP é ativado por padrão, mas as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="15b67-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="15b67-110">A **ação de spam** é definida para **mover a mensagem para a pasta lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="15b67-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="15b67-111">Você também pode criar uma nova política de filtro de spam que se aplique somente a um conjunto de usuários se não quiser que todas as caixas de correio sejam filtradas por ZAP.</span><span class="sxs-lookup"><span data-stu-id="15b67-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="15b67-112">Os usuários mantiveram suas configurações de lixo eletrônico padrão e não desativaram a proteção de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="15b67-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="15b67-113">(Consulte [alterar o nível de proteção no filtro de lixo eletrônico](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) para obter detalhes sobre as opções do usuário no Outlook.)</span><span class="sxs-lookup"><span data-stu-id="15b67-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>
  
## <a name="how-zap-works"></a><span data-ttu-id="15b67-114">Como o ZAP funciona</span><span class="sxs-lookup"><span data-stu-id="15b67-114">How ZAP works</span></span>

<span data-ttu-id="15b67-115">O Office 365 atualiza as assinaturas de malware e mecanismo antispam em tempo real diariamente.</span><span class="sxs-lookup"><span data-stu-id="15b67-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="15b67-116">No entanto, os usuários ainda podem obter mensagens mal-intencionadas entregues às suas caixas de entrada por vários motivos, incluindo se o conteúdo é enarmado depois de ser entregue aos usuários.</span><span class="sxs-lookup"><span data-stu-id="15b67-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="15b67-117">O ZAP aborda isso ao monitorar atualizações continuamente nas assinaturas de spam e malware do Office 365.</span><span class="sxs-lookup"><span data-stu-id="15b67-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="15b67-118">ZAP pode localizar e remover mensagens entregues anteriormente que já estão nas caixas de entrada dos usuários.</span><span class="sxs-lookup"><span data-stu-id="15b67-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="15b67-119">A ação ZAP é transparente para o usuário da caixa de correio; Eles não são notificados quando uma mensagem de email é movida.</span><span class="sxs-lookup"><span data-stu-id="15b67-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="15b67-120">A mensagem não deve ser mais antiga que 2 dias.</span><span class="sxs-lookup"><span data-stu-id="15b67-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="15b67-121">As listas de permissões, [as regras de fluxo de emails](https://go.microsoft.com/fwlink/p/?LinkId=722755) (também conhecidas como regras de transporte) e as regras de usuário final ou filtros adicionais têm precedência sobre o zap.</span><span class="sxs-lookup"><span data-stu-id="15b67-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="15b67-122">ZAP de malware</span><span class="sxs-lookup"><span data-stu-id="15b67-122">Malware ZAP</span></span>

<span data-ttu-id="15b67-123">Para malware recém detectado, o ZAP remove anexos de mensagens de email, deixando o corpo da mensagem na caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="15b67-123">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="15b67-124">Os anexos são removidos independentemente do status de leitura do email.</span><span class="sxs-lookup"><span data-stu-id="15b67-124">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="15b67-125">O malware ZAP é habilitado por padrão na política de malware.</span><span class="sxs-lookup"><span data-stu-id="15b67-125">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="15b67-126">Você pode desabilitar o ZAP de malware usando o parâmetro *ZapEnabled* no cmdlet [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) no PowerShell do Exchange Online ou do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="15b67-126">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="15b67-127">Phish de phishing</span><span class="sxs-lookup"><span data-stu-id="15b67-127">Phish ZAP</span></span>

<span data-ttu-id="15b67-128">Para email que é identificado como Phish após a entrega, o ZAP realiza a ação de acordo com a política de spam pela qual o usuário é coberto.</span><span class="sxs-lookup"><span data-stu-id="15b67-128">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="15b67-129">Se a ação de phishing de política estiver definida para executar uma ação em um email (redirecionar, excluir, quarentena, mover para lixo eletrônico), ZAP moverá a mensagem para a pasta lixo eletrônico da caixa de entrada do usuário, independentemente do status de leitura do email.</span><span class="sxs-lookup"><span data-stu-id="15b67-129">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="15b67-130">Se a ação de phishing de política não estiver definida como executar ação (Adicionar cabeçalho X, modificar assunto, sem ação), ZAP não executará ações no email.</span><span class="sxs-lookup"><span data-stu-id="15b67-130">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="15b67-131">Saiba mais sobre como [configurar suas políticas de filtro de spam](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) aqui.</span><span class="sxs-lookup"><span data-stu-id="15b67-131">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="15b67-132">O phishing ZAP está habilitado por padrão na política de spam.</span><span class="sxs-lookup"><span data-stu-id="15b67-132">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="15b67-133">Você pode desabilitar o Phish ZAP usando o parâmetro *ZapEnabled* no cmdlet [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) no PowerShell do Exchange Online ou do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="15b67-133">You can disable Phish ZAP by using the *ZapEnabled* parameter on the [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="15b67-134">ZAP de spam</span><span class="sxs-lookup"><span data-stu-id="15b67-134">Spam ZAP</span></span>

<span data-ttu-id="15b67-135">Para email que é identificado como spam após a entrega, o ZAP realiza a ação de acordo com a política de spam pela qual o usuário é coberto.</span><span class="sxs-lookup"><span data-stu-id="15b67-135">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="15b67-136">Se a ação de spam de política estiver definida como executar uma ação em um email (redirecionar, excluir, quarentena, mover para lixo eletrônico), ZAP moverá a mensagem para a pasta lixo eletrônico da caixa de entrada do usuário, se a mensagem for não lida.</span><span class="sxs-lookup"><span data-stu-id="15b67-136">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="15b67-137">Se a ação de spam de política não estiver definida como executar ação (Adicionar cabeçalho X, modificar assunto, sem ação), ZAP não executará ações no email.</span><span class="sxs-lookup"><span data-stu-id="15b67-137">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="15b67-138">Saiba mais sobre como [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md) aqui.</span><span class="sxs-lookup"><span data-stu-id="15b67-138">Learn more about how to [Configure your spam filter policies](configure-your-spam-filter-policies.md) here.</span></span>

<span data-ttu-id="15b67-139">O ZAP de spam está habilitado por padrão na política de spam.</span><span class="sxs-lookup"><span data-stu-id="15b67-139">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="15b67-140">Você pode desabilitar o ZAP de spam usando o parâmetro *ZapEnabled* do cmdlet [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) no PowerShell do Exchange Online ou do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="15b67-140">You can disable Spam ZAP by using the *ZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="15b67-141">O parâmetro *ZapEnabled* no cmdlet **set-HostedContentFilterPolicy** desabilita ou habilita a impressão ZAP e o spam zap para a política.</span><span class="sxs-lookup"><span data-stu-id="15b67-141">The *ZapEnabled* parameter on the **Set-HostedContentFilterPolicy** cmdlet disables or enables both Phish ZAP and Spam ZAP for the policy.</span></span> <span data-ttu-id="15b67-142">Você não pode habilitar ou desabilitar o zap de phishing e o spam ZAP dentro da mesma política.</span><span class="sxs-lookup"><span data-stu-id="15b67-142">You can't independently enable or disable Phish ZAP and Spam ZAP within the same policy.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="15b67-143">Como ver se ZAP moveu a mensagem</span><span class="sxs-lookup"><span data-stu-id="15b67-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="15b67-144">Para determinar se o ZAP moveu a mensagem, você pode usar o [relatório de status de proteção contra ameaças](../../compliance/view-email-security-reports.md#threat-protection-status-report) ou o [Explorador de ameaças (e detecções em tempo real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="15b67-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](../../compliance/view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="15b67-145">Desabilitar ZAP</span><span class="sxs-lookup"><span data-stu-id="15b67-145">Disable ZAP</span></span>

<span data-ttu-id="15b67-146">Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="15b67-146">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="15b67-147">Para se conectar ao PowerShell do Exchange Online Protection, confira [conectar-se ao PowerShell do Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290).</span><span class="sxs-lookup"><span data-stu-id="15b67-147">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="15b67-148">Desabilitar o malware ZAP \* \*</span><span class="sxs-lookup"><span data-stu-id="15b67-148">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="15b67-149">Este exemplo desabilita o ZAP na política de filtro de malware chamada "Test".</span><span class="sxs-lookup"><span data-stu-id="15b67-149">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="15b67-150">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="15b67-150">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="15b67-151">Desabilitar o phishing ZAP e o spam ZAP</span><span class="sxs-lookup"><span data-stu-id="15b67-151">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="15b67-152">Este exemplo desabilita o phishing ZAP e o spam ZAP na política de filtro de conteúdo chamada "Test".</span><span class="sxs-lookup"><span data-stu-id="15b67-152">This example disables Phish ZAP and Spam ZAP in the content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="15b67-153">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span><span class="sxs-lookup"><span data-stu-id="15b67-153">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="15b67-154">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="15b67-154">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="15b67-155">O que acontece se uma mensagem legítima for movida para a pasta lixo eletrônico?</span><span class="sxs-lookup"><span data-stu-id="15b67-155">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="15b67-156">Você deve seguir o processo de relatório normal para [falsos positivos](../../compliance/prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="15b67-156">You should follow the normal reporting process for [false-positives](../../compliance/prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="15b67-157">A única razão pela qual a mensagem seria movida da caixa de entrada para a pasta lixo eletrônico seria porque o serviço determinou que a mensagem era spam ou mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="15b67-157">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="15b67-158">E se eu usar a quarentena do Office 365 em vez da pasta lixo eletrônico?</span><span class="sxs-lookup"><span data-stu-id="15b67-158">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="15b67-159">ZAP não move mensagens para a quarentena da caixa de entrada neste momento.</span><span class="sxs-lookup"><span data-stu-id="15b67-159">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="15b67-160">E se eu tiver uma regra de fluxo de emails personalizada (regra bloquear/permitir)?</span><span class="sxs-lookup"><span data-stu-id="15b67-160">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="15b67-161">Regras criadas por administradores (regras de fluxo de emails) ou regras de bloqueio e permissão têm precedência.</span><span class="sxs-lookup"><span data-stu-id="15b67-161">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="15b67-162">Essas mensagens são excluídas dos critérios de recurso para que o fluxo de email siga a ação de regra (regra bloquear/permitir).</span><span class="sxs-lookup"><span data-stu-id="15b67-162">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="15b67-163">E se uma mensagem for movida para outra pasta (por exemplo, regra de caixa de entrada)?</span><span class="sxs-lookup"><span data-stu-id="15b67-163">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="15b67-164">ZAP ainda funciona nesse caso, a menos que a mensagem tenha sido excluída ou esteja em lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="15b67-164">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="15b67-165">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="15b67-165">Related Topics</span></span>

[<span data-ttu-id="15b67-166">Proteção anti-spam de emails do Office 365</span><span class="sxs-lookup"><span data-stu-id="15b67-166">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="15b67-167">Bloquear spam de email com o filtro de spam do Office 365 para evitar problemas de falsos negativos</span><span class="sxs-lookup"><span data-stu-id="15b67-167">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
