---
title: Inspersão no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre a inspersão e o Microsoft Exchange Online Protection (EOP)
ms.openlocfilehash: e30fa27ac359ad28e042b2d4bd446d34a2e4f1e9
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209626"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="3643f-103">Inspersão no EOP</span><span class="sxs-lookup"><span data-stu-id="3643f-103">Backscatter in EOP</span></span>

<span data-ttu-id="3643f-104">A *dispersão* é uma notificação de falha na entrega (também conhecida como NDRs ou mensagens de devolução) que você recebe para mensagens que não enviou.</span><span class="sxs-lookup"><span data-stu-id="3643f-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="3643f-105">Os spammers forjam (falsificam) o endereço de: de suas mensagens e freqüentemente usam endereços de email reais para dar credibilidade às suas mensagens.</span><span class="sxs-lookup"><span data-stu-id="3643f-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="3643f-106">Portanto, quando os spammers inevitavelmente enviam mensagens para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino é essencialmente induzido a retornar a mensagem não entregue em um NDR para o remetente forjado no endereço de:.</span><span class="sxs-lookup"><span data-stu-id="3643f-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="3643f-107">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP faz todos os esforços para identificar e cancelar silenciosamente mensagens de fontes do dubious sem gerar uma notificação de falha na entrega.</span><span class="sxs-lookup"><span data-stu-id="3643f-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="3643f-108">Mas, com base nos emails de volume simples que fluem pelo serviço, há sempre a possibilidade de que o EOP envie involuntariamente a dispersão.</span><span class="sxs-lookup"><span data-stu-id="3643f-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="3643f-109">O Backscatterer.org mantém uma lista de bloqueios (também conhecida como lista de bloqueio de DNS ou DNSBL) dos servidores de email que foram responsáveis por enviar a dispersão, e os servidores do EOP podem aparecer nessa lista.</span><span class="sxs-lookup"><span data-stu-id="3643f-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="3643f-110">No entanto, não tentamos removê-lo da lista de bloqueios do Backscatterer.org porque não é uma lista de remetentes de spam (por sua própria admissão).</span><span class="sxs-lookup"><span data-stu-id="3643f-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="3643f-111">O site do Backscatter.org ( <http://www.backscatterer.org/?target=usage> ) recomenda o uso de seus serviços para verificar emails de entrada no modo de segurança, em vez de rejeitar modo (grandes serviços de email quase sempre enviam algumas dispersão).</span><span class="sxs-lookup"><span data-stu-id="3643f-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
