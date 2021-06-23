---
title: Relatar mensagens de spam, não spam e phishing para a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre as diferentes maneiras de relatar mensagens e arquivos bons e ruins à Microsoft para análise.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082811"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="d6346-103">Relatar mensagens e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6346-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d6346-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="d6346-104">**Applies to**</span></span>
- [<span data-ttu-id="d6346-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d6346-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d6346-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d6346-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d6346-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6346-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d6346-108">Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas do Proteção do Exchange Online (EOP) sem caixas de correio Exchange Online, usuários e administradores têm vários métodos diferentes para relatar mensagens de email e arquivos à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6346-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="d6346-109">Método</span><span class="sxs-lookup"><span data-stu-id="d6346-109">Method</span></span>|<span data-ttu-id="d6346-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="d6346-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="d6346-111">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6346-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="d6346-112">O método de relatório recomendado para administradores em organizações com Exchange Online caixas de correio (não disponíveis no EOP autônomo).</span><span class="sxs-lookup"><span data-stu-id="d6346-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="d6346-113">Habilitar a Mensagem de Relatório ou os complementos de Phishing de Relatório</span><span class="sxs-lookup"><span data-stu-id="d6346-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="d6346-114">Funciona com Outlook e Outlook na Web (anteriormente conhecido como Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="d6346-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="d6346-115">Dependendo da sua assinatura, as mensagens relatadas pelos usuários com os complementos estão disponíveis no [portal Envios](admin-submission.md)de Administrador, resultados de investigação e resposta [automatizadas (AIR),](air-view-investigation-results.md)no relatório de mensagens relatadas pelo usuário [e](view-email-security-reports.md#user-reported-messages-report)no [Explorer](threat-explorer-views.md#email--submissions).</span><span class="sxs-lookup"><span data-stu-id="d6346-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="d6346-116">Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada.</span><span class="sxs-lookup"><span data-stu-id="d6346-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="d6346-117">Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="d6346-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="d6346-118">Relatar falsos positivos e falsos negativos no Outlook</span><span class="sxs-lookup"><span data-stu-id="d6346-118">Report false positives and false negatives in Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="d6346-119">Envie falsos positivos (bons emails bloqueados ou enviados para a pasta lixo eletrônico) e falsos negativos (emails indesejados ou phishing que foram entregues à caixa de entrada) para Proteção do Exchange Online (EOP) usando o recurso Mensagem de Relatório.</span><span class="sxs-lookup"><span data-stu-id="d6346-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="d6346-120">Enviar mensagens manualmente à Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="d6346-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="d6346-121">Envie mensagens anexadas manualmente para endereços de email específicos da Microsoft para spam, não spam e phishing.</span><span class="sxs-lookup"><span data-stu-id="d6346-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="d6346-122">Usar as regras de fluxo de correio para ver o que os usuários estão relatando à Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6346-122">Use mail flow rules to see what users are reporting to Microsoft</span></span>](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|<span data-ttu-id="d6346-123">Saiba como criar uma regra de fluxo de emails (também conhecida como regra de transporte) que o notifica quando os usuários relatam mensagens à Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="d6346-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="d6346-124">Enviar malware e não malware à Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="d6346-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="d6346-125">Use o Inteligência de Segurança da Microsoft site para enviar anexos e outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="d6346-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="d6346-126">Se as mensagens de spam ou phishing foram colocadas em quarentena em vez de entregues, os usuários poderão relatar as mensagens à Microsoft de Quarentena no portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d6346-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from Quarantine in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="d6346-127">Para obter detalhes, [consulte Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="d6346-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d6346-128">Os dados de envios para a Microsoft residem no limite Office 365 conformidade nos data centers norte-americanos.</span><span class="sxs-lookup"><span data-stu-id="d6346-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="d6346-129">Os dados são revisados por analistas na equipe de engenharia para ajudar a melhorar a eficácia dos filtros.</span><span class="sxs-lookup"><span data-stu-id="d6346-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
