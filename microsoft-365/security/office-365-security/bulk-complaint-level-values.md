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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Os administradores podem saber mais sobre os valores de nível de conformidade em massa (BCL) usados no Exchange Online Protection (EOP).
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827428"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="a9f2e-103">Nível de reclamação em massa (BCL) no EOP</span><span class="sxs-lookup"><span data-stu-id="a9f2e-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="a9f2e-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP atribui um nível de conformidade em massa (BCL) a mensagens de entrada de emails em massa.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="a9f2e-105">A BCL é adicionada à mensagem em um cabeçalho X e é semelhante ao [nível de confiança de spam (SCL)](spam-confidence-levels.md) usado para identificar mensagens como spam.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="a9f2e-106">Uma BCL maior indica que uma mensagem em massa é mais provável de gerar queixas (e, portanto, é mais provável de spam).</span><span class="sxs-lookup"><span data-stu-id="a9f2e-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="a9f2e-107">A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar a BCL apropriada.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="a9f2e-108">Os emails em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de destinatário.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="a9f2e-109">Boa caixa postal envia as mensagens desejadas com conteúdo relevante para seus assinantes.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="a9f2e-110">Essas mensagens geram poucas reclamações de destinatários.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="a9f2e-111">Outros remetentes em massa enviam mensagens não solicitadas que parecem muito parecidas com spam e geram muitas queixas de destinatários.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="a9f2e-112">As mensagens de um mensageiro em massa são conhecidas como emails em massa ou cinza.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="a9f2e-113">A filtragem de spam marca mensagens como **email em massa** com base no limite da BCL (o valor padrão ou um valor que você especifica) e executa a ação especificada na mensagem (a ação padrão é entregar a mensagem à pasta lixo eletrônico do destinatário).</span><span class="sxs-lookup"><span data-stu-id="a9f2e-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="a9f2e-114">Para obter mais informações, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md) e [qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="a9f2e-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="a9f2e-115">Os limites de BCL são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-115">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="a9f2e-116">BCL</span><span class="sxs-lookup"><span data-stu-id="a9f2e-116">BCL</span></span>|<span data-ttu-id="a9f2e-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="a9f2e-117">Description</span></span>|
|:---:|---|
|<span data-ttu-id="a9f2e-118">,0</span><span class="sxs-lookup"><span data-stu-id="a9f2e-118">0</span></span>|<span data-ttu-id="a9f2e-119">A mensagem não é de um remetente em massa.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="a9f2e-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="a9f2e-120">1, 2, 3</span></span>|<span data-ttu-id="a9f2e-121">A mensagem é de um remetente em massa que gera algumas reclamações.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="a9f2e-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="a9f2e-122">4, 5, 6, 7</span></span>|<span data-ttu-id="a9f2e-123">A mensagem é de um remetente em massa que gera um número misto de reclamações.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="a9f2e-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="a9f2e-124">8, 9</span></span>|<span data-ttu-id="a9f2e-125">A mensagem é de um remetente em massa que gera um grande número de reclamações.</span><span class="sxs-lookup"><span data-stu-id="a9f2e-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
