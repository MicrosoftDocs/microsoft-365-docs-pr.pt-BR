---
title: Valores de nível de reclamação em massa
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre valores de nível de conformidade em massa (BCL) usados no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c68314cf992d39a105293955b6fade7b1a2bec56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289885"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="90d0d-103">Nível de reclamação em massa (BCL) no EOP</span><span class="sxs-lookup"><span data-stu-id="90d0d-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90d0d-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="90d0d-104">**Applies to**</span></span>
- [<span data-ttu-id="90d0d-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="90d0d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="90d0d-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="90d0d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="90d0d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90d0d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="90d0d-108">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP atribui um nível de conformidade em massa (BCL) a mensagens de entrada de mailers em massa.</span><span class="sxs-lookup"><span data-stu-id="90d0d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="90d0d-109">O BCL é adicionado à mensagem em um X-header e é semelhante ao nível de confiança de [spam (SCL)](spam-confidence-levels.md) usado para identificar mensagens como spam.</span><span class="sxs-lookup"><span data-stu-id="90d0d-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="90d0d-110">Uma BCL mais alta indica que uma mensagem em massa tem mais probabilidade de gerar reclamações (e, portanto, é mais provável que seja spam).</span><span class="sxs-lookup"><span data-stu-id="90d0d-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="90d0d-111">A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar o BCL apropriado.</span><span class="sxs-lookup"><span data-stu-id="90d0d-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="90d0d-112">Os mailers em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de destinatários.</span><span class="sxs-lookup"><span data-stu-id="90d0d-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="90d0d-113">Os bons mailers em massa enviam mensagens desejadas com conteúdo relevante para seus assinantes.</span><span class="sxs-lookup"><span data-stu-id="90d0d-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="90d0d-114">Essas mensagens geram poucas reclamações dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="90d0d-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="90d0d-115">Outros remetentes de email em massa enviam mensagens não solicitadas que se parecem muito com spam e geram muitas reclamações dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="90d0d-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="90d0d-116">As mensagens de um mailer em massa são conhecidas como email em massa ou cinza.</span><span class="sxs-lookup"><span data-stu-id="90d0d-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="90d0d-117">A filtragem de  spam marca as mensagens como email em massa com base no limite de BCL (o valor padrão ou um valor que você especificar) e realiza a ação especificada na mensagem (a ação padrão é entregar a mensagem para a pasta Lixo Eletrônico do destinatário).</span><span class="sxs-lookup"><span data-stu-id="90d0d-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="90d0d-118">Para obter mais informações, [consulte Configurar políticas anti-spam](configure-your-spam-filter-policies.md) [e Qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="90d0d-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="90d0d-119">Os limites de BCL são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="90d0d-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="90d0d-120">BCL</span><span class="sxs-lookup"><span data-stu-id="90d0d-120">BCL</span></span>|<span data-ttu-id="90d0d-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="90d0d-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="90d0d-122">0</span><span class="sxs-lookup"><span data-stu-id="90d0d-122">0</span></span>|<span data-ttu-id="90d0d-123">A mensagem não é de um remetente em massa.</span><span class="sxs-lookup"><span data-stu-id="90d0d-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="90d0d-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="90d0d-124">1, 2, 3</span></span>|<span data-ttu-id="90d0d-125">A mensagem é de um remetente em massa que gera poucas reclamações.</span><span class="sxs-lookup"><span data-stu-id="90d0d-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="90d0d-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="90d0d-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="90d0d-127">A mensagem é de um remetente em massa que gera um número misto de reclamações.</span><span class="sxs-lookup"><span data-stu-id="90d0d-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="90d0d-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="90d0d-128">8, 9</span></span>|<span data-ttu-id="90d0d-129">A mensagem é de um remetente em massa que gera um grande número de reclamações.</span><span class="sxs-lookup"><span data-stu-id="90d0d-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="90d0d-130"><sup>\*</sup> Esse é o valor limite padrão usado em políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="90d0d-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
