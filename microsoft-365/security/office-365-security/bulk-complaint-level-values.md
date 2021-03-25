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
description: Os administradores podem aprender sobre valores de nível de conformidade em massa (BCL) usados na Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202934"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="13bb8-103">Nível de reclamação em massa (BCL) no EOP</span><span class="sxs-lookup"><span data-stu-id="13bb8-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="13bb8-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="13bb8-104">**Applies to**</span></span>
- [<span data-ttu-id="13bb8-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="13bb8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="13bb8-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="13bb8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="13bb8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13bb8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="13bb8-108">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações do Exchange Online Protection (EOP) autônomas sem caixas de correio do Exchange Online, o EOP atribui um nível de conformidade em massa (BCL) a mensagens de entrada de mailers em massa.</span><span class="sxs-lookup"><span data-stu-id="13bb8-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="13bb8-109">O BCL é adicionado à mensagem em um header X e é semelhante ao nível de confiança de [spam (SCL)](spam-confidence-levels.md) usado para identificar mensagens como spam.</span><span class="sxs-lookup"><span data-stu-id="13bb8-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="13bb8-110">Uma BCL mais alta indica que uma mensagem em massa tem mais probabilidade de gerar reclamações (e, portanto, é mais provável que seja spam).</span><span class="sxs-lookup"><span data-stu-id="13bb8-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="13bb8-111">A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar o BCL apropriado.</span><span class="sxs-lookup"><span data-stu-id="13bb8-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="13bb8-112">Os mailers em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de destinatários.</span><span class="sxs-lookup"><span data-stu-id="13bb8-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="13bb8-113">Os bons mailers em massa enviam mensagens desejadas com conteúdo relevante para seus assinantes.</span><span class="sxs-lookup"><span data-stu-id="13bb8-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="13bb8-114">Essas mensagens geram poucas reclamações de destinatários.</span><span class="sxs-lookup"><span data-stu-id="13bb8-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="13bb8-115">Outros remetentes de email em massa enviam mensagens não solicitadas que se parecem muito com spam e geram muitas reclamações de destinatários.</span><span class="sxs-lookup"><span data-stu-id="13bb8-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="13bb8-116">As mensagens de um mailer em massa são conhecidas como email em massa ou email cinza.</span><span class="sxs-lookup"><span data-stu-id="13bb8-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="13bb8-117">A filtragem de  spam marca mensagens como email em massa com base no limite de BCL (o valor padrão ou um valor especificado) e realiza a ação especificada na mensagem (a ação padrão é entregar a mensagem para a pasta Lixo Eletrônico do destinatário).</span><span class="sxs-lookup"><span data-stu-id="13bb8-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="13bb8-118">Para obter mais informações, consulte [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="13bb8-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="13bb8-119">Os limites BCL são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="13bb8-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="13bb8-120">BCL</span><span class="sxs-lookup"><span data-stu-id="13bb8-120">BCL</span></span>|<span data-ttu-id="13bb8-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="13bb8-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="13bb8-122">0</span><span class="sxs-lookup"><span data-stu-id="13bb8-122">0</span></span>|<span data-ttu-id="13bb8-123">A mensagem não é de um remetente em massa.</span><span class="sxs-lookup"><span data-stu-id="13bb8-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="13bb8-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="13bb8-124">1, 2, 3</span></span>|<span data-ttu-id="13bb8-125">A mensagem é de um remetente em massa que gera poucas reclamações.</span><span class="sxs-lookup"><span data-stu-id="13bb8-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="13bb8-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="13bb8-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="13bb8-127">A mensagem é de um remetente em massa que gera um número misto de reclamações.</span><span class="sxs-lookup"><span data-stu-id="13bb8-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="13bb8-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="13bb8-128">8, 9</span></span>|<span data-ttu-id="13bb8-129">A mensagem é de um remetente em massa que gera um alto número de reclamações.</span><span class="sxs-lookup"><span data-stu-id="13bb8-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="13bb8-130"><sup>\*</sup> Esse é o valor de limite padrão usado em políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="13bb8-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
