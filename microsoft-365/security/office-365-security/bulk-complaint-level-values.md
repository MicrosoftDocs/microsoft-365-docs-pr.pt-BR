---
title: Valores do nível de reclamação em massa
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Saiba mais sobre os valores de nível de conformidade em massa (BCL) no Office 365.
ms.openlocfilehash: 82c006f05ce3d37ff23ca1e522b653bd26efeed8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035563"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="fe17c-103">Nível de reclamação em massa (BCL) no Office 365</span><span class="sxs-lookup"><span data-stu-id="fe17c-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="fe17c-104">Os emails em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de destinatário.</span><span class="sxs-lookup"><span data-stu-id="fe17c-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="fe17c-105">Alguns emails em massa bons que enviam mensagens desejadas com conteúdo relevante para seus assinantes.</span><span class="sxs-lookup"><span data-stu-id="fe17c-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="fe17c-106">Essas mensagens geram poucas reclamações de destinatários.</span><span class="sxs-lookup"><span data-stu-id="fe17c-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="fe17c-107">Outros remetentes em massa enviam mensagens não solicitadas que parecem muito parecidas com spam e geram muitas queixas de destinatários.</span><span class="sxs-lookup"><span data-stu-id="fe17c-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="fe17c-108">As mensagens de um mensageiro em massa são conhecidas como emails em massa ou cinza.</span><span class="sxs-lookup"><span data-stu-id="fe17c-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="fe17c-109">Para distinguir mensagens de diferentes tipos de remetentes em massa, emails de entrada de emails em massa (o Exchange Online ou o Exchange Online Protection (EOP) sem caixas de correio do Exchange Online) recebe um nível de reclamação de massa (BCL) adicionado à mensagem em um cabeçalho X.</span><span class="sxs-lookup"><span data-stu-id="fe17c-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="fe17c-110">A BCL é semelhante ao [nível de confiança de spam (SCL)](spam-confidence-levels.md) usado para identificar mensagens como spam.</span><span class="sxs-lookup"><span data-stu-id="fe17c-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="fe17c-111">Uma BCL maior indica que uma mensagem em massa é mais provável de gerar queixas (e, portanto, é mais provável de spam).</span><span class="sxs-lookup"><span data-stu-id="fe17c-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="fe17c-112">A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar a BCL apropriada.</span><span class="sxs-lookup"><span data-stu-id="fe17c-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="fe17c-113">A filtragem de spam marca mensagens como **email em massa** com base no limite da BCL (o valor padrão ou um valor que você especifica) e executa a ação especificada na mensagem (a ação padrão é entregar a mensagem à pasta lixo eletrônico do destinatário).</span><span class="sxs-lookup"><span data-stu-id="fe17c-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="fe17c-114">Para obter mais informações, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md) e [qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="fe17c-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="fe17c-115">Os limites de BCL são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fe17c-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="fe17c-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="fe17c-116">**BCL**</span></span>|<span data-ttu-id="fe17c-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fe17c-117">**Description**</span></span>|
|<span data-ttu-id="fe17c-118">,0</span><span class="sxs-lookup"><span data-stu-id="fe17c-118">0</span></span>|<span data-ttu-id="fe17c-119">A mensagem não é de um remetente em massa.</span><span class="sxs-lookup"><span data-stu-id="fe17c-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="fe17c-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="fe17c-120">1, 2, 3</span></span>|<span data-ttu-id="fe17c-121">A mensagem é de um remetente em massa que gera algumas reclamações.</span><span class="sxs-lookup"><span data-stu-id="fe17c-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="fe17c-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="fe17c-122">4, 5, 6, 7</span></span>|<span data-ttu-id="fe17c-123">A mensagem é de um remetente em massa que gera um número misto de reclamações.</span><span class="sxs-lookup"><span data-stu-id="fe17c-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="fe17c-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="fe17c-124">8, 9</span></span>|<span data-ttu-id="fe17c-125">A mensagem é de um remetente em massa que gera um grande número de reclamações.</span><span class="sxs-lookup"><span data-stu-id="fe17c-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
