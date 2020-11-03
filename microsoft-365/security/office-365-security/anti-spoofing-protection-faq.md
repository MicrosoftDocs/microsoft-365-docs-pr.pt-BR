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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem exibir perguntas frequentes e respostas sobre a proteção contra falsificação no Exchange Online Protection (EOP).
ms.openlocfilehash: a5b0484e41e3df7a7b6ad16e69a4f7062b19b554
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844387"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="5c369-103">Perguntas frequentes sobre a proteção antifalsificação</span><span class="sxs-lookup"><span data-stu-id="5c369-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5c369-104">Este artigo fornece perguntas frequentes e respostas sobre a proteção contra falsificação para organizações do Microsoft 365 com caixas de correio no Exchange Online, ou organizações autônomas do Exchange Online Protection (EOP), sem caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5c369-104">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="5c369-105">Para perguntas e respostas sobre a proteção contra spam, confira [perguntas frequentes sobre proteção](anti-spam-protection-faq.md)contra spam.</span><span class="sxs-lookup"><span data-stu-id="5c369-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="5c369-106">Para perguntas e respostas sobre a proteção contra malware, consulte [Anti-Malware Protection FAQ](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="5c369-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="5c369-107">Por que a Microsoft optou por emails de entrada não autenticados de lixo eletrônico?</span><span class="sxs-lookup"><span data-stu-id="5c369-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="5c369-108">A Microsoft acredita que o risco de continuar a permitir emails de entrada não autenticados é maior do que o risco de perder emails de entrada legítimos.</span><span class="sxs-lookup"><span data-stu-id="5c369-108">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="5c369-109">O lixo eletrônico de entrada não autenticado faz com que emails legítimos sejam marcados como spam?</span><span class="sxs-lookup"><span data-stu-id="5c369-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="5c369-110">Quando a Microsoft habilitou este recurso no 2018, ocorreram alguns falsos positivos (mensagens boas foram marcadas como ruins).</span><span class="sxs-lookup"><span data-stu-id="5c369-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="5c369-111">No entanto, ao longo do tempo, os remetentes ajustados para os requisitos.</span><span class="sxs-lookup"><span data-stu-id="5c369-111">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="5c369-112">O número de mensagens que foram identificadas indevidos como falsificadas se tornaram insignificantes para a maioria dos caminhos de email.</span><span class="sxs-lookup"><span data-stu-id="5c369-112">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="5c369-113">A própria Microsoft primeiro adotou os novos requisitos de autenticação de email várias semanas antes de implantá-lo para os clientes.</span><span class="sxs-lookup"><span data-stu-id="5c369-113">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="5c369-114">Embora tenha havido dificuldades no início, elas diminuíram gradualmente.</span><span class="sxs-lookup"><span data-stu-id="5c369-114">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="5c369-115">A inteligência de falsificação está disponível para clientes da Microsoft 365 sem o defender para Office 365?</span><span class="sxs-lookup"><span data-stu-id="5c369-115">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="5c369-116">Sim.</span><span class="sxs-lookup"><span data-stu-id="5c369-116">Yes.</span></span> <span data-ttu-id="5c369-117">A partir de outubro de 2018, a inteligência de falsificação está disponível para todas as organizações com caixas de correio no Exchange Online e organizações EOP autônomas sem caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5c369-117">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="5c369-118">Como relatar mensagens de spam ou não spam para a Microsoft?</span><span class="sxs-lookup"><span data-stu-id="5c369-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="5c369-119">Confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="5c369-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="5c369-120">Sou um administrador e não sei todas as fontes de mensagens em meu domínio de email!</span><span class="sxs-lookup"><span data-stu-id="5c369-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="5c369-121">Confira [se você não conhece todas as fontes de email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span><span class="sxs-lookup"><span data-stu-id="5c369-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="5c369-122">O que acontece se eu desabilitar a proteção contra falsificação para minha organização?</span><span class="sxs-lookup"><span data-stu-id="5c369-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="5c369-123">Não recomendamos desabilitar a proteção contra falsificação.</span><span class="sxs-lookup"><span data-stu-id="5c369-123">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="5c369-124">Desabilitar a proteção permitirá que mais mensagens de phishing e spam sejam entregues na sua organização.</span><span class="sxs-lookup"><span data-stu-id="5c369-124">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="5c369-125">Nem todos os phishing são falsificações, e nem todas as mensagens falsificadas serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="5c369-125">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="5c369-126">No entanto, seu risco será maior.</span><span class="sxs-lookup"><span data-stu-id="5c369-126">However, your risk will be higher.</span></span>

<span data-ttu-id="5c369-127">Agora que a [filtragem avançada para conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) está disponível, não recomendamos mais desativar a proteção contra falsificação quando o email é roteado por outro serviço antes do EOP.</span><span class="sxs-lookup"><span data-stu-id="5c369-127">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="5c369-128">A proteção contra falsificação significa que eu será protegido contra todos os phishing?</span><span class="sxs-lookup"><span data-stu-id="5c369-128">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="5c369-129">Infelizmente, não.</span><span class="sxs-lookup"><span data-stu-id="5c369-129">Unfortunately, no.</span></span> <span data-ttu-id="5c369-130">Os invasores se adaptarão ao uso de outras técnicas (por exemplo, contas comprometidas ou contas em serviços de email gratuitos).</span><span class="sxs-lookup"><span data-stu-id="5c369-130">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="5c369-131">No entanto, a proteção anti-phishing funciona muito melhor para detectar esses outros tipos de métodos de phishing.</span><span class="sxs-lookup"><span data-stu-id="5c369-131">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="5c369-132">As camadas de proteção no EOP são projetadas juntas e compiladas umas sobre as outras.</span><span class="sxs-lookup"><span data-stu-id="5c369-132">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="5c369-133">Outros grandes serviços de email bloqueiam emails de entrada não autenticados?</span><span class="sxs-lookup"><span data-stu-id="5c369-133">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="5c369-134">Quase todos os grandes serviços de email implementam verificações tradicionais de SPF, DKIM e DMARC.</span><span class="sxs-lookup"><span data-stu-id="5c369-134">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="5c369-135">Alguns serviços têm outras verificações mais estritas, mas poucos vão até o EOP para bloquear emails não autenticados e tratá-los como mensagens falsificadas.</span><span class="sxs-lookup"><span data-stu-id="5c369-135">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="5c369-136">No entanto, o setor está se tornando mais atento a problemas com emails não autenticados, especialmente devido ao problema de phishing.</span><span class="sxs-lookup"><span data-stu-id="5c369-136">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="5c369-137">Ainda precisa habilitar a configuração avançada de filtro de spam "registro SPF: falha de hardware" ( _MarkAsSpamSpfRecordHardFail_ ) se eu habilitar a antifalsificação?</span><span class="sxs-lookup"><span data-stu-id="5c369-137">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" ( _MarkAsSpamSpfRecordHardFail_ ) if I enable anti-spoofing?</span></span>

<span data-ttu-id="5c369-138">Não.</span><span class="sxs-lookup"><span data-stu-id="5c369-138">No.</span></span> <span data-ttu-id="5c369-139">Essa configuração de ASF não é mais necessária.</span><span class="sxs-lookup"><span data-stu-id="5c369-139">This ASF setting is no longer required.</span></span> <span data-ttu-id="5c369-140">A proteção antifalsificação considera a falha de hardware SPF e um conjunto muito mais amplo de critérios.</span><span class="sxs-lookup"><span data-stu-id="5c369-140">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="5c369-141">Se você habilitar a antifalsificação e ativado o **Registro SPF: ocorreu um erro no hardware** ( _MarkAsSpamSpfRecordHardFail_ ), provavelmente obterá mais falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="5c369-141">If you have anti-spoofing enabled and the **SPF record: hard fail** ( _MarkAsSpamSpfRecordHardFail_ ) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="5c369-142">Recomendamos que você desabilite esse recurso, pois ele não fornecerá praticamente nenhum benefício adicional para detectar spam ou mensagens de phishing e, em vez disso, geraria quase todos os falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="5c369-142">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="5c369-143">Para obter mais informações, consulte [Configurações avançadas de filtro de spam (ASF) no EOP](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="5c369-143">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="5c369-144">A ajuda do esquema de reconfiguração do remetente corrige emails encaminhados?</span><span class="sxs-lookup"><span data-stu-id="5c369-144">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="5c369-145">O SRS corrige apenas parcialmente o problema dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="5c369-145">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="5c369-146">Ao reescrever o **email SMTP de** , o SRS pode garantir que a mensagem encaminhada passe SPF no próximo destino.</span><span class="sxs-lookup"><span data-stu-id="5c369-146">By rewriting the SMTP **MAIL FROM** , SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="5c369-147">No entanto, como a antifalsificação baseia-se no endereço **de** em combinação com o domínio de assinatura ou **email de** DKIM (ou outros sinais), não é suficiente impedir que emails enviados do SRS sejam marcados como falsificados.</span><span class="sxs-lookup"><span data-stu-id="5c369-147">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
