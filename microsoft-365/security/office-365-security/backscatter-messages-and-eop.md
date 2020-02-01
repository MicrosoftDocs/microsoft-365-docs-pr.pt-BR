---
title: Mnsagens backscatter e EOP
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
description: As mensagens de dispersão são mensagens de retorno automatizadas que são enviadas para endereços de email falsificados. O DNSBL dispersão identifica servidores que enviam mensagens de dispersão (que podem incluir muitas fontes de email legítimas). Como não se trata de uma lista de remetentes de spam, não tentamos remover-se da DNSBL dispersão.
ms.openlocfilehash: 3dc83c303e861c8762f2276de521e1b550ae2e59
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599728"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="c9932-105">Mensagens backscatter e EOP</span><span class="sxs-lookup"><span data-stu-id="c9932-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="c9932-106">*Mensagens de dispersão* são notificações de falha na entrega (também conhecidas como NDRs ou mensagens de devolução) que você recebe para mensagens que não enviou.</span><span class="sxs-lookup"><span data-stu-id="c9932-106">*Backscatter messages* are non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="c9932-107">Os spammers forjam (falsificam) o endereço de: de suas mensagens e freqüentemente usam endereços de email reais para dar credibilidade às suas mensagens.</span><span class="sxs-lookup"><span data-stu-id="c9932-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="c9932-108">Portanto, quando eles enviam mensagens inevitavelmente para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino pode dutifully responder com uma notificação de falha na entrega, que é enviada para o remetente forjado no endereço de:.</span><span class="sxs-lookup"><span data-stu-id="c9932-108">So, when they inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server might dutifully respond with an NDR, which is sent to the forged sender in the From: address.</span></span>

<span data-ttu-id="c9932-109">O proteção do Exchange Online (EOP) faz todos os esforços para identificar e soltar silenciosamente mensagens de fontes do dubious sem gerar uma notificação de falha na entrega.</span><span class="sxs-lookup"><span data-stu-id="c9932-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="c9932-110">Mas, com base no volume de email simples que flui pelo serviço, sempre há a possibilidade de que o EOP envie mensagens de inspersão involuntariamente.</span><span class="sxs-lookup"><span data-stu-id="c9932-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter messages.</span></span>

<span data-ttu-id="c9932-111">O Backscatterer.org mantém uma lista de bloqueios (também conhecida como lista de bloqueio de DNS ou DNSBL) dos servidores de email que foram responsáveis por enviar mensagens de dispersão, e os servidores do EOP podem aparecer na lista.</span><span class="sxs-lookup"><span data-stu-id="c9932-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter messages, and EOP servers might appear on this list.</span></span> <span data-ttu-id="c9932-112">No entanto, não tentamos removê-lo da lista de bloqueios do Backscatterer.org porque não é uma lista de remetentes de spam (por sua própria admissão).</span><span class="sxs-lookup"><span data-stu-id="c9932-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="c9932-113">De acordo com o dispersa. ou`http://www.backscatterer.org/?target=usage`site (), eles recomendam o uso de seus serviços para verificar emails de entrada no modo de segurança, em vez de rejeitar modo (grandes serviços de email quase sempre enviam algumas mensagens de inspersão).</span><span class="sxs-lookup"><span data-stu-id="c9932-113">According to the Backscatter.or website (`http://www.backscatterer.org/?target=usage`), they recommend using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter messages).</span></span>
