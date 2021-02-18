---
title: Perguntas frequentes sobre mensagens em quarentena
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
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem exibir perguntas frequentes e respostas sobre mensagens em quarentena no Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8496ae4f1702bb63328be0c494d8829c9ddd8cf2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289396"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="a6a1b-103">Perguntas frequentes sobre mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="a6a1b-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a6a1b-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a6a1b-104">**Applies to**</span></span>
- [<span data-ttu-id="a6a1b-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a6a1b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a6a1b-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a6a1b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a6a1b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6a1b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a6a1b-108">Este tópico fornece perguntas frequentes e respostas sobre mensagens de email em quarentena para organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-108">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="a6a1b-109">Para perguntas e respostas sobre a proteção anti-spam, consulte Perguntas frequentes sobre [a proteção anti-spam.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="a6a1b-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="a6a1b-110">Para perguntas e respostas sobre a proteção anti-malware, consulte Perguntas frequentes sobre [a proteção anti-malware.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a6a1b-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="a6a1b-111">Para perguntas e respostas sobre a proteção anti-spoofing, consulte Perguntas frequentes sobre a proteção [anti-spoofing.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="a6a1b-111">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="a6a1b-112">Como faço para gerenciar mensagens que foram colocadas em quarentena para malware?</span><span class="sxs-lookup"><span data-stu-id="a6a1b-112">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="a6a1b-113">Somente administradores podem gerenciar mensagens que foram colocadas em quarentena para malware.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-113">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="a6a1b-114">Para obter mais informações, [consulte Gerenciar mensagens e arquivos em quarentena como administrador.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="a6a1b-114">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="a6a1b-115">Como colocar o spam em quarentena?</span><span class="sxs-lookup"><span data-stu-id="a6a1b-115">How do I quarantine spam?</span></span>

<span data-ttu-id="a6a1b-116">Por padrão, as mensagens classificadas como spam ou email em massa pela filtragem de spam são entregues na caixa de correio do usuário e movidas para a pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-116">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="a6a1b-117">Mas você pode criar e configurar políticas anti-spam para colocar mensagens de spam ou emails em massa em quarentena.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-117">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="a6a1b-118">Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a6a1b-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="a6a1b-119">Como posso dar aos usuários acesso à quarentena?</span><span class="sxs-lookup"><span data-stu-id="a6a1b-119">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="a6a1b-120">Um usuário deve ter uma conta válida para acessar suas próprias mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-120">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="a6a1b-121">O EOP autônomo exige que os usuários sejam representados como usuários de email no EOP (criado manualmente ou criado por meio da sincronização de diretórios).</span><span class="sxs-lookup"><span data-stu-id="a6a1b-121">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="a6a1b-122">Para obter mais informações sobre como gerenciar usuários em ambientes EOP autônomos, consulte [Gerenciar usuários de email no EOP.](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a6a1b-122">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="a6a1b-123">Quais mensagens os usuários finais podem acessar em quarentena?</span><span class="sxs-lookup"><span data-stu-id="a6a1b-123">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="a6a1b-124">Os usuários podem acessar spam, email em massa e (a partir de abril de 2020) mensagens de phishing em que são destinatários.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-124">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="a6a1b-125">Os usuários finais não podem acessar malware em quarentena, phishing de  alta confiança ou mensagens que foram colocadas em quarentena devido à ação Entregar a mensagem para a quarentena hospedada em regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="a6a1b-125">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a6a1b-126">Para obter mais informações sobre os usuários que acessam mensagens em quarentena, consulte Encontrar e liberar mensagens [em quarentena como um usuário.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="a6a1b-126">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="a6a1b-127">Por quanto tempo as mensagens são mantidas em quarentena?</span><span class="sxs-lookup"><span data-stu-id="a6a1b-127">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="a6a1b-128">Você configura por quanto tempo as mensagens de spam, phishing e email em massa são mantidas em quarentena usando políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-128">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="a6a1b-129">O padrão é 30 dias, que também é o máximo.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-129">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="a6a1b-130">Para obter mais informações, [consulte Configurar políticas anti-spam no EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a6a1b-130">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="a6a1b-131">Para mensagens que foram colocadas em quarentena pela ação de regra de fluxo de emails Entregar a mensagem para a quarentena hospedada, as mensagens são mantidas em quarentena por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-131">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="a6a1b-132">Não é possível configurar essa duração.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-132">You can't configure this duration.</span></span>

<span data-ttu-id="a6a1b-133">Depois que o período expirar, as mensagens serão excluídas e não serão recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-133">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="a6a1b-134">Posso liberar ou relatar mais de uma mensagem em quarentena por vez?</span><span class="sxs-lookup"><span data-stu-id="a6a1b-134">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="a6a1b-135">No Centro de Conformidade & segurança, você pode selecionar e liberar até 100 mensagens por vez.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-135">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="a6a1b-136">Os administradores podem usar os cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) no PowerShell do Exchange Online ou no PowerShell do EOP autônomo para encontrar e liberar mensagens em quarentena em massa e para relatar falsos positivos em massa.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-136">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="a6a1b-137">Há suporte para curingas ao procurar mensagens em quarentena?</span><span class="sxs-lookup"><span data-stu-id="a6a1b-137">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="a6a1b-138">Posso procurar mensagens em quarentena para um domínio específico?</span><span class="sxs-lookup"><span data-stu-id="a6a1b-138">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="a6a1b-139">Caracteres curinga não são suportados no Centro de Conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-139">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="a6a1b-140">Por exemplo, ao pesquisar um remetente, você precisa especificar o endereço de email completo.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-140">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="a6a1b-141">Porém, você pode usar curingas no PowerShell do Exchange Online ou no EOP PowerShell autônomo.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-141">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="a6a1b-142">Por exemplo, copie o seguinte código do PowerShell para o Bloco de Notas e salve o arquivo como .ps1 em um local fácil de encontrar (por exemplo, C:\Data\QuarantineRelease.ps1).</span><span class="sxs-lookup"><span data-stu-id="a6a1b-142">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="a6a1b-143">Em seguida, depois de se conectar [ao PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online ou ao PowerShell da Proteção do [Exchange Online,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)execute o seguinte comando para executar o script:</span><span class="sxs-lookup"><span data-stu-id="a6a1b-143">Then, after you connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="a6a1b-144">O script faz as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="a6a1b-144">The script does the following actions:</span></span>

- <span data-ttu-id="a6a1b-145">Encontre mensagens não enviadas que foram colocadas em quarentena como spam de todos os remetentes no domínio fabrikam.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-145">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="a6a1b-146">O número máximo de resultados é 50.000 (50 páginas de 1.000 resultados).</span><span class="sxs-lookup"><span data-stu-id="a6a1b-146">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="a6a1b-147">Salve os resultados em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-147">Save the results to a CSV file.</span></span>
- <span data-ttu-id="a6a1b-148">Liberar as mensagens em quarentena correspondentes para todos os destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-148">Release the matching quarantined messages to all original recipients.</span></span>

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

<span data-ttu-id="a6a1b-149">Depois de liberar uma mensagem, você não poderá liberá-la novamente.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-149">After you release a message, you can't release it again.</span></span>
