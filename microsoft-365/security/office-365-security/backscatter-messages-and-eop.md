---
title: Dispersão inversa no EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre Backscatter e Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202940"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="59ef8-103">Dispersão inversa no EOP</span><span class="sxs-lookup"><span data-stu-id="59ef8-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="59ef8-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="59ef8-104">**Applies to**</span></span>
- [<span data-ttu-id="59ef8-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="59ef8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="59ef8-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="59ef8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="59ef8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59ef8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="59ef8-108">*Backscatter* é relatórios de não entrega (também conhecidos como NDRs ou mensagens de rejeição) que você recebe para mensagens que você não enviou.</span><span class="sxs-lookup"><span data-stu-id="59ef8-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="59ef8-109">Os remetentes de spam forjam (falsificam) o De: endereço de suas mensagens e costumam usar endereços de email reais para dar credibilidade às suas mensagens.</span><span class="sxs-lookup"><span data-stu-id="59ef8-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="59ef8-110">Portanto, quando os remetentes de spam inevitavelmente enviam mensagens para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino é essencialmente enganoso para retornar a mensagem não entregue em uma NDR para o remetente forjado no endereço From:.</span><span class="sxs-lookup"><span data-stu-id="59ef8-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="59ef8-111">Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas Proteção do Exchange Online (EOP) sem caixas de correio Exchange Online, o EOP faz todo o esforço para identificar e soltar silenciosamente mensagens de fontes dúbias sem gerar uma NDR.</span><span class="sxs-lookup"><span data-stu-id="59ef8-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="59ef8-112">Mas, com base no volume total de emails que flui pelo serviço, sempre há a possibilidade de que o EOP envie backscatter sem querer.</span><span class="sxs-lookup"><span data-stu-id="59ef8-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="59ef8-113">Backscatterer.org mantém uma lista de bloqueios (também conhecida como uma lista de bloqueios DNS ou DNSBL) de servidores de email responsáveis pelo envio de backscatter, e os servidores EOP podem aparecer nesta lista.</span><span class="sxs-lookup"><span data-stu-id="59ef8-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="59ef8-114">Porém, não tentamos nos remover da lista de bloqueios Backscatterer.org porque não é uma lista de spammers (por sua própria admissão).</span><span class="sxs-lookup"><span data-stu-id="59ef8-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="59ef8-115">O Backscatter.org site ( ) recomenda usar seu serviço para verificar emails de entrada no modo Cofre em vez do modo Rejeitar (grandes serviços de email quase sempre enviam algum <http://www.backscatterer.org/?target=usage> backscatter).</span><span class="sxs-lookup"><span data-stu-id="59ef8-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
