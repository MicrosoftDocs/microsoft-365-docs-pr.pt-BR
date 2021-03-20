---
title: Perguntas frequentes sobre a proteção antifalsificação
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem exibir perguntas e respostas frequentes sobre a proteção anti-spoofing no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7e7163037029761a53a5461de592e46ab5ea0485
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917553"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="6e6b9-103">Perguntas frequentes sobre a proteção antifalsificação</span><span class="sxs-lookup"><span data-stu-id="6e6b9-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6e6b9-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="6e6b9-104">**Applies to**</span></span>
- [<span data-ttu-id="6e6b9-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6e6b9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6e6b9-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6e6b9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6e6b9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e6b9-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="6e6b9-108">Este artigo fornece perguntas e respostas frequentes sobre a proteção anti-spoofing para organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-108">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="6e6b9-109">Para obter perguntas e respostas sobre a proteção anti-spam, consulte Perguntas frequentes sobre proteção [anti-spam.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="6e6b9-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="6e6b9-110">Para obter perguntas e respostas sobre a proteção anti-malware, consulte Perguntas frequentes sobre proteção [contra malware](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="6e6b9-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="6e6b9-111">Por que a Microsoft escolheu o lixo eletrônico de entrada não autenticado?</span><span class="sxs-lookup"><span data-stu-id="6e6b9-111">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="6e6b9-112">A Microsoft acredita que o risco de continuar a permitir emails de entrada não autenticados é maior do que o risco de perder emails de entrada legítimos.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-112">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="6e6b9-113">O lixo eletrônico não autenticado faz com que o email legítimo seja marcado como spam?</span><span class="sxs-lookup"><span data-stu-id="6e6b9-113">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="6e6b9-114">Quando a Microsoft habilitar esse recurso em 2018, alguns falsos positivos aconteceram (as mensagens boas foram marcadas como ruins).</span><span class="sxs-lookup"><span data-stu-id="6e6b9-114">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="6e6b9-115">No entanto, com o passar do tempo, os envios foram ajustados aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-115">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="6e6b9-116">O número de mensagens que foram identificadas como falsas tornou-se insignificante para a maioria dos caminhos de email.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-116">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="6e6b9-117">A própria Microsoft adotou pela primeira vez os novos requisitos de autenticação de email várias semanas antes de implantá-lo aos clientes.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-117">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="6e6b9-118">Embora tenha havido dificuldades no início, elas diminuíram gradualmente.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-118">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="6e6b9-119">A inteligência de spoof está disponível para clientes do Microsoft 365 sem o Defender para Office 365?</span><span class="sxs-lookup"><span data-stu-id="6e6b9-119">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="6e6b9-120">Sim.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-120">Yes.</span></span> <span data-ttu-id="6e6b9-121">A partir de outubro de 2018, a inteligência de spoof está disponível para todas as organizações com caixas de correio no Exchange Online e organizações EOP autônomas sem caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-121">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="6e6b9-122">Como relatar mensagens de spam ou não spam para a Microsoft?</span><span class="sxs-lookup"><span data-stu-id="6e6b9-122">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="6e6b9-123">Confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="6e6b9-123">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="6e6b9-124">Sou um administrador e não sei todas as fontes para mensagens no meu domínio de email!</span><span class="sxs-lookup"><span data-stu-id="6e6b9-124">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="6e6b9-125">Consulte [Você não sabe todas as fontes para seu email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span><span class="sxs-lookup"><span data-stu-id="6e6b9-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="6e6b9-126">O que acontece se eu desabilitar a proteção anti-spoofing para minha organização?</span><span class="sxs-lookup"><span data-stu-id="6e6b9-126">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="6e6b9-127">Não recomendamos desabilitar a proteção anti-spoofing.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-127">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="6e6b9-128">Desabilitar a proteção permitirá que mais mensagens de phishing e spam sejam entregues em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-128">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="6e6b9-129">Nem todos os phishing são falsas e nem todas as mensagens falsas serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-129">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="6e6b9-130">No entanto, seu risco será maior.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-130">However, your risk will be higher.</span></span>

<span data-ttu-id="6e6b9-131">Agora que [a Filtragem](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Aprimorada para Conectores está disponível, não é mais recomendável desligar a proteção anti-spoofing quando seu email é roteado por outro serviço antes do EOP.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-131">Now that [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="6e6b9-132">A proteção anti-spoofing significa que eu vou ser protegido contra todos os phishing?</span><span class="sxs-lookup"><span data-stu-id="6e6b9-132">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="6e6b9-133">Infelizmente, não.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-133">Unfortunately, no.</span></span> <span data-ttu-id="6e6b9-134">Os invasores se adaptarão para usar outras técnicas (por exemplo, contas comprometidas ou contas em serviços de email gratuitos).</span><span class="sxs-lookup"><span data-stu-id="6e6b9-134">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="6e6b9-135">No entanto, a proteção anti-phishing funciona muito melhor para detectar esses outros tipos de métodos de phishing.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-135">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="6e6b9-136">As camadas de proteção no EOP são projetadas para trabalharem juntas e se desenvolverem umas sobre as outras.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-136">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="6e6b9-137">Outros serviços de email grandes bloqueiam emails de entrada não autenticados?</span><span class="sxs-lookup"><span data-stu-id="6e6b9-137">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="6e6b9-138">Quase todos os grandes serviços de email implementam verificações tradicionais de SPF, DKIM e DMARC.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-138">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="6e6b9-139">Alguns serviços têm outras verificações mais estritas, mas poucos vão até o EOP para bloquear emails não autenticados e tratá-los como mensagens falsas.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-139">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="6e6b9-140">No entanto, o setor está se tornando mais ciente dos problemas com emails não autenticados, especialmente por causa do problema do phishing.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-140">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="6e6b9-141">Ainda preciso habilitar a configuração de Filtro de Spam Avançado "Registro SPF: falha grave" (_MarkAsSpamSpfRecordHardFail_) se eu habilitar anti-spoofing?</span><span class="sxs-lookup"><span data-stu-id="6e6b9-141">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="6e6b9-142">Não.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-142">No.</span></span> <span data-ttu-id="6e6b9-143">Essa configuração ASF não é mais necessária.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-143">This ASF setting is no longer required.</span></span> <span data-ttu-id="6e6b9-144">A proteção anti-spoofing considera a falha dura do SPF e um conjunto muito mais amplo de critérios.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-144">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="6e6b9-145">Se você habilitar a antifalsificação e ativado o **Registro SPF: ocorreu um erro no hardware** (_MarkAsSpamSpfRecordHardFail_), provavelmente obterá mais falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-145">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="6e6b9-146">Recomendamos que você desabilite esse recurso, pois ele não oferece quase nenhum benefício adicional para detectar mensagens de spam ou phishing e, em vez disso, geraria principalmente falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-146">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="6e6b9-147">Para obter mais informações, consulte [AsF (Advanced Spam Filter) settings in EOP](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="6e6b9-147">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="6e6b9-148">O Esquema de Reescrita do Remetente ajuda a corrigir emails encaminhados?</span><span class="sxs-lookup"><span data-stu-id="6e6b9-148">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="6e6b9-149">O SRS corrige apenas parcialmente o problema dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-149">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="6e6b9-150">Ao reescrever o SMTP **MAIL FROM**, o SRS pode garantir que a mensagem encaminhada passe SPF no próximo destino.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-150">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="6e6b9-151">No entanto, como a anti-spoofing é baseada no endereço **From** em combinação com o domínio de assinatura **MAIL FROM** ou DKIM (ou outros sinais), não é suficiente impedir que o email encaminhado pelo SRS seja marcado como spoofed.</span><span class="sxs-lookup"><span data-stu-id="6e6b9-151">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>