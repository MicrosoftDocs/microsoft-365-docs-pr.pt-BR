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
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286964"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="67944-103">Dispersão inversa no EOP</span><span class="sxs-lookup"><span data-stu-id="67944-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="67944-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="67944-104">**Applies to**</span></span>
- [<span data-ttu-id="67944-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="67944-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="67944-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="67944-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="67944-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67944-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="67944-108">*Backscatter* são relatórios de não entrega (também conhecidos como NDRs ou mensagens de rejeição) que você recebe para mensagens que você não enviou.</span><span class="sxs-lookup"><span data-stu-id="67944-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="67944-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lendity to their messages.</span><span class="sxs-lookup"><span data-stu-id="67944-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="67944-110">Portanto, quando remetentes de spam inevitavelmente enviam mensagens para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino é essencialmente complicado para retornar a mensagem não entregue em uma NDR para o remetente forjado no endereço De:.</span><span class="sxs-lookup"><span data-stu-id="67944-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="67944-111">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP se esforça para identificar e soltar silenciosamente mensagens de fontes mal-confiáveis sem gerar uma NDR.</span><span class="sxs-lookup"><span data-stu-id="67944-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="67944-112">Porém, com base no volume total de emails que fluem pelo serviço, sempre existe a possibilidade de que o EOP enviará backscatter sem querer.</span><span class="sxs-lookup"><span data-stu-id="67944-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="67944-113">Backscatterer.org mantém uma lista de bloqueios (também conhecida como uma lista de bloqueios de DNS ou DNSBL) de servidores de email que foram responsáveis por enviar backscatter, e os servidores EOP podem aparecer nessa lista.</span><span class="sxs-lookup"><span data-stu-id="67944-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="67944-114">Porém, não tentamos remover a si mesmo da lista de Backscatterer.org porque ela não é uma lista de remetentes de spam (por sua própria admissão).</span><span class="sxs-lookup"><span data-stu-id="67944-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="67944-115">O Backscatter.org site ( ) recomenda usar seu serviço para verificar o email de entrada no modo de segurança em vez do modo rejeitar (serviços de email grandes quase sempre enviam <http://www.backscatterer.org/?target=usage> algum backscatter).</span><span class="sxs-lookup"><span data-stu-id="67944-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
