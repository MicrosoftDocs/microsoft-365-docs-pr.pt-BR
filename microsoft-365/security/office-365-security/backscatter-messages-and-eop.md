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
ms.openlocfilehash: 3cdc556a8cc193466d150fc82298796779841cca
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165950"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="b3f1f-103">Dispersão inversa no EOP</span><span class="sxs-lookup"><span data-stu-id="b3f1f-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b3f1f-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="b3f1f-104">**Applies to**</span></span>
- [<span data-ttu-id="b3f1f-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b3f1f-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="b3f1f-106">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="b3f1f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="b3f1f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3f1f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b3f1f-108">*Backscatter* são relatórios de não entrega (também conhecidos como NDRs ou mensagens de rejeição) que você recebe para mensagens que você não enviou.</span><span class="sxs-lookup"><span data-stu-id="b3f1f-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="b3f1f-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lendity to their messages.</span><span class="sxs-lookup"><span data-stu-id="b3f1f-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="b3f1f-110">Portanto, quando remetentes de spam inevitavelmente enviam mensagens para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino é essencialmente complicado para retornar a mensagem não entregue em uma NDR para o remetente forjado no endereço De:.</span><span class="sxs-lookup"><span data-stu-id="b3f1f-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="b3f1f-111">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP se esforça para identificar e soltar silenciosamente mensagens de fontes mal-confiáveis sem gerar uma NDR.</span><span class="sxs-lookup"><span data-stu-id="b3f1f-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="b3f1f-112">Porém, com base no volume total de emails que fluem pelo serviço, sempre existe a possibilidade de que o EOP enviará backscatter sem querer.</span><span class="sxs-lookup"><span data-stu-id="b3f1f-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="b3f1f-113">Backscatterer.org mantém uma lista de bloqueios (também conhecida como uma lista de bloqueios de DNS ou DNSBL) de servidores de email que foram responsáveis por enviar backscatter, e os servidores EOP podem aparecer nessa lista.</span><span class="sxs-lookup"><span data-stu-id="b3f1f-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="b3f1f-114">Porém, não tentamos remover a si mesmo da lista de Backscatterer.org, pois ela não é uma lista de remetentes de spam (por sua própria admissão).</span><span class="sxs-lookup"><span data-stu-id="b3f1f-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="b3f1f-115">O Backscatter.org site ( ) recomenda usar seu serviço para verificar o email de entrada no modo de segurança em vez do modo rejeitar (serviços de email grandes quase sempre enviam <http://www.backscatterer.org/?target=usage> algum backscatter).</span><span class="sxs-lookup"><span data-stu-id="b3f1f-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
