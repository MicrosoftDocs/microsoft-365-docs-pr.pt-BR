---
title: Perguntas Frequentes sobre a Quarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Respostas para perguntas frequentes sobre a quarentena no Office 365.
ms.openlocfilehash: 58800d5645241c2115356bc9899ce53302d1e37e
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856900"
---
# <a name="quarantine-faq-in-office-365"></a><span data-ttu-id="a81eb-103">Perguntas frequentes sobre quarentena no Office 365</span><span class="sxs-lookup"><span data-stu-id="a81eb-103">Quarantine FAQ in Office 365</span></span>

<span data-ttu-id="a81eb-104">Este tópico fornece perguntas frequentes e respostas sobre a quarentena para clientes do Office 365 com caixas de correio em Exchange Online ou clientes autônomos do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a81eb-104">This topic provides frequently asked questions and answers about quarantine for Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="a81eb-105">P: como gerenciar mensagens em quarentena para malware?</span><span class="sxs-lookup"><span data-stu-id="a81eb-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="a81eb-106">Somente os administradores podem gerenciar mensagens em quarentena para malware.</span><span class="sxs-lookup"><span data-stu-id="a81eb-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="a81eb-107">Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="a81eb-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="a81eb-108">P: como colocar em quarentena spam?</span><span class="sxs-lookup"><span data-stu-id="a81eb-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="a81eb-109">R.</span><span class="sxs-lookup"><span data-stu-id="a81eb-109">A.</span></span> <span data-ttu-id="a81eb-110">Por padrão, as mensagens classificadas como spam ou email em massa por filtragem de spam são entregues na caixa de correio do usuário e são movidas para a pasta lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="a81eb-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="a81eb-111">Mas você pode criar e configurar políticas antispam para colocar em quarentena mensagens de email em massa ou spam.</span><span class="sxs-lookup"><span data-stu-id="a81eb-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="a81eb-112">Para obter mais informações, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a81eb-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="a81eb-113">P: como permitir que os usuários acessem a quarentena?</span><span class="sxs-lookup"><span data-stu-id="a81eb-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="a81eb-114">R.</span><span class="sxs-lookup"><span data-stu-id="a81eb-114">A.</span></span> <span data-ttu-id="a81eb-115">Um usuário deve ter uma conta válida para acessar suas próprias mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="a81eb-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="a81eb-116">O EOP autônomo exige que os usuários sejam representados como usuários de email no EOP (criado manualmente ou criado via sincronização de diretório).</span><span class="sxs-lookup"><span data-stu-id="a81eb-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="a81eb-117">Para obter mais informações sobre como gerenciar usuários em ambientes autônomos do EOP, consulte [Manage mail users in EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="a81eb-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="a81eb-118">P: quais mensagens podem acessar usuários finais em quarentena?</span><span class="sxs-lookup"><span data-stu-id="a81eb-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="a81eb-119">R.</span><span class="sxs-lookup"><span data-stu-id="a81eb-119">A.</span></span> <span data-ttu-id="a81eb-120">Os usuários podem acessar spam, emails em massa e (a partir de abril de 2020) mensagens de phishing em que são destinatários.</span><span class="sxs-lookup"><span data-stu-id="a81eb-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="a81eb-121">Os usuários finais não podem acessar malware em quarentena, phishing de alta confiança ou mensagens que foram colocadas em quarentena devido à ação de **entrega da mensagem para a quarentena hospedada** em regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="a81eb-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a81eb-122">Para obter mais informações sobre os usuários que acessam mensagens em quarentena, consulte [Localizar e liberar mensagens em quarentena como um usuário no Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="a81eb-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="a81eb-123">P: quanto tempo as mensagens são mantidas na quarentena?</span><span class="sxs-lookup"><span data-stu-id="a81eb-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="a81eb-124">R.</span><span class="sxs-lookup"><span data-stu-id="a81eb-124">A.</span></span> <span data-ttu-id="a81eb-125">Você configura por quanto tempo spam, phishing e mensagens de email em massa são mantidos na quarentena usando políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="a81eb-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="a81eb-126">O padrão é 30 dias, que também é o máximo.</span><span class="sxs-lookup"><span data-stu-id="a81eb-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="a81eb-127">Para obter mais informações, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a81eb-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="a81eb-128">Para mensagens que foram colocadas em quarentena pela ação de regra de fluxo de emails **entregar a mensagem para a quarentena hospedada**, as mensagens são mantidas em quarentena por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="a81eb-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="a81eb-129">Você não pode configurar esta duração.</span><span class="sxs-lookup"><span data-stu-id="a81eb-129">You can't configure this duration.</span></span>

<span data-ttu-id="a81eb-130">Depois que o período de tempo expira, as mensagens são excluídas e não são recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="a81eb-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="a81eb-131">P: posso liberar ou relatar mais de uma mensagem em quarentena por vez?</span><span class="sxs-lookup"><span data-stu-id="a81eb-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="a81eb-132">R.</span><span class="sxs-lookup"><span data-stu-id="a81eb-132">A.</span></span> <span data-ttu-id="a81eb-133">No centro de conformidade & segurança, você pode selecionar e liberar até 100 mensagens de cada vez.</span><span class="sxs-lookup"><span data-stu-id="a81eb-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="a81eb-134">Os administradores podem usar os cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) no PowerShell do Exchange Online ou do Exchange Online Protection PowerShell para localizar e liberar mensagens em quarentena em massa e para relatar falsos positivos em massa.</span><span class="sxs-lookup"><span data-stu-id="a81eb-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="a81eb-135">P: há suporte para curingas durante a pesquisa de mensagens em quarentena?</span><span class="sxs-lookup"><span data-stu-id="a81eb-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="a81eb-136">Posso pesquisar mensagens em quarentena para um domínio específico?</span><span class="sxs-lookup"><span data-stu-id="a81eb-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="a81eb-137">R.</span><span class="sxs-lookup"><span data-stu-id="a81eb-137">A.</span></span> <span data-ttu-id="a81eb-138">Não há suporte para curingas no centro de conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="a81eb-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="a81eb-139">Por exemplo, ao pesquisar um remetente, você precisa especificar o endereço de email completo.</span><span class="sxs-lookup"><span data-stu-id="a81eb-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="a81eb-140">No entanto, você pode usar caracteres curinga no PowerShell do Exchange Online ou do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="a81eb-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="a81eb-141">Por exemplo, execute o seguinte comando para localizar mensagens de spam em quarentena de todos os remetentes no domínio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="a81eb-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="a81eb-142">Em seguida, execute o seguinte comando para liberar essas mensagens a todos os destinatários originais:</span><span class="sxs-lookup"><span data-stu-id="a81eb-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $CQ.Identity -ReleaseToAll}
```

<span data-ttu-id="a81eb-143">Após liberar uma mensagem, você não poderá liberá-la novamente.</span><span class="sxs-lookup"><span data-stu-id="a81eb-143">After you release a message, you can't release it again.</span></span>
