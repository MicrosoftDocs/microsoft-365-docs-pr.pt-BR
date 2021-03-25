---
title: Nível de confiança de spam
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre o nível de confiança de spam (SCL) aplicado a mensagens no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 951bbcb5fcbcc7b7916ee1c34c4ab489d54b6667
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202950"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="cdd7c-103">Nível de confiança de spam (SCL) no EOP</span><span class="sxs-lookup"><span data-stu-id="cdd7c-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="cdd7c-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="cdd7c-104">**Applies to**</span></span>
- [<span data-ttu-id="cdd7c-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cdd7c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cdd7c-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="cdd7c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cdd7c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdd7c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cdd7c-108">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, as mensagens de entrada passam pela filtragem de spam no EOP e são atribuídas a uma pontuação de spam.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="cdd7c-109">Essa pontuação é mapeada para um SCL (nível de confiança de spam) individual adicionado à mensagem em um header X.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="cdd7c-110">Uma SCL mais alta indica que uma mensagem tem mais probabilidade de ser spam.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="cdd7c-111">O EOP toma medidas na mensagem com base na SCL.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="cdd7c-112">O que significa a SCL e as ações padrão que são tomadas em mensagens são descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="cdd7c-113">Para obter mais informações sobre ações que você pode tomar em mensagens com base no veredito de filtragem de spam, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cdd7c-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="cdd7c-114">SCL</span><span class="sxs-lookup"><span data-stu-id="cdd7c-114">SCL</span></span>|<span data-ttu-id="cdd7c-115">Definição</span><span class="sxs-lookup"><span data-stu-id="cdd7c-115">Definition</span></span>|<span data-ttu-id="cdd7c-116">Ação padrão</span><span class="sxs-lookup"><span data-stu-id="cdd7c-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="cdd7c-117">-1</span><span class="sxs-lookup"><span data-stu-id="cdd7c-117">-1</span></span>|<span data-ttu-id="cdd7c-118">A mensagem ignorou a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-118">The message skipped spam filtering.</span></span> <span data-ttu-id="cdd7c-119">Por exemplo, a mensagem é de um remetente seguro, foi enviada para um destinatário seguro ou é de um servidor de origem de email na Lista de IDS.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="cdd7c-120">Para obter mais informações, consulte [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="cdd7c-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="cdd7c-121">Entregar a mensagem para a caixa de entrada do destinatário.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="cdd7c-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="cdd7c-122">0, 1</span></span>|<span data-ttu-id="cdd7c-123">A filtragem de spam determinou que a mensagem não era spam.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="cdd7c-124">Entregar a mensagem para a caixa de entrada do destinatário.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="cdd7c-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="cdd7c-125">5, 6</span></span>|<span data-ttu-id="cdd7c-126">A filtragem de spam marcou a mensagem como **Spam**</span><span class="sxs-lookup"><span data-stu-id="cdd7c-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="cdd7c-127">Entregar a mensagem na pasta Lixo Eletrônico do destinatário.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="cdd7c-128">9 </span><span class="sxs-lookup"><span data-stu-id="cdd7c-128">9</span></span>|<span data-ttu-id="cdd7c-129">A filtragem de spam marcou a mensagem como **spam de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="cdd7c-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="cdd7c-130">Entregar a mensagem na pasta Lixo Eletrônico do destinatário.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="cdd7c-131">Você notará que os SCL 2, 3, 4, 7 e 8 não são usados pela filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="cdd7c-132">Você pode usar regras de fluxo de emails (também conhecidas como regras de transporte) para carimbar a SCL em mensagens.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="cdd7c-133">Se você usar uma regra de fluxo de emails para definir a SCL, os valores 5 ou 6 acionam a ação de filtragem de spam para **Spam** e os valores 7, 8 ou 9 acionam a ação de filtragem de **spam** para spam de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="cdd7c-134">Para obter mais informações, [consulte Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="cdd7c-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="cdd7c-135">Semelhante à SCL, o nível de reclamação em massa (BCL) identifica email em massa ruim (também conhecido como _email cinza)._</span><span class="sxs-lookup"><span data-stu-id="cdd7c-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="cdd7c-136">Um BCL mais alto indica que uma mensagem de email em massa tem mais chances de gerar reclamações (e, portanto, mais chances que seja spam).</span><span class="sxs-lookup"><span data-stu-id="cdd7c-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="cdd7c-137">Você configura o limite BCL em políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="cdd7c-138">Para obter mais informações, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the](what-s-the-difference-between-junk-email-and-bulk-email.md)difference between junk email and bulk email? .</span><span class="sxs-lookup"><span data-stu-id="cdd7c-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="cdd7c-139">![O ícone curto do LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New para o Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="cdd7c-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="cdd7c-140">Descubra cursos de vídeo **gratuitos para administradores do Microsoft 365** e profissionais de TI , trazidos para você pelo LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="cdd7c-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
