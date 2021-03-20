---
title: Suporte para validação de mensagens assinadas por DKIM (Domain Keys Identified Mail)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Saiba mais sobre a validação de mensagens assinadas pelo DKIM no Exchange Online Protection e no Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 111bf169d60e386dc48ef086bbe631b8760201a6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916521"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="e4215-103">Suporte para validação de mensagens assinadas por DKIM</span><span class="sxs-lookup"><span data-stu-id="e4215-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e4215-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e4215-104">**Applies to**</span></span>
- [<span data-ttu-id="e4215-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e4215-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e4215-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e4215-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e4215-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4215-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e4215-108">A Proteção do Exchange Online (EOP) e o Exchange Online suportam a validação de entrada de mensagens[DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="e4215-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="e4215-109">O DKIM valida que uma  mensagem de email não foi falsa por outra pessoa e foi enviada do domínio de onde diz *ter* vindo.</span><span class="sxs-lookup"><span data-stu-id="e4215-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="e4215-110">Ele vincula uma mensagem de email à organização que a enviou.</span><span class="sxs-lookup"><span data-stu-id="e4215-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="e4215-111">A verificação de DKIM é usada automaticamente para todas as mensagens enviadas com IPv6.</span><span class="sxs-lookup"><span data-stu-id="e4215-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="e4215-112">O Microsoft 365 também dá suporte a DKIM quando o email é enviado por IPv4.</span><span class="sxs-lookup"><span data-stu-id="e4215-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="e4215-113">(Para saber mais sobre o suporte a IPv6, veja [Suporte para mensagens de email de entrada anônimas por IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).).</span><span class="sxs-lookup"><span data-stu-id="e4215-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="e4215-114">O DKIM valida uma mensagem assinada digitalmente que aparece no DKIM-Signature dos headers da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e4215-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="e4215-115">Os resultados de uma validação DKIM-Signature são marcados no Authentication-Results de dados.</span><span class="sxs-lookup"><span data-stu-id="e4215-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="e4215-116">O texto do cabeçalho de mensagens tem aparência semelhante à seguinte (em que contoso.com é o remetente):</span><span class="sxs-lookup"><span data-stu-id="e4215-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="e4215-117">Para obter mais informações sobre o Authentication-Results de Authentication-Results, consulte RFC 7001 ( Campo do[Header](https://www.rfc-editor.org/rfc/rfc7001.txt)de Mensagens para Indicar o Status da Autenticação de Mensagem .</span><span class="sxs-lookup"><span data-stu-id="e4215-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="e4215-118">A implementação DKIM da Microsoft está em conformidade com essa RFC.</span><span class="sxs-lookup"><span data-stu-id="e4215-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="e4215-119">Os administradores podem criar regras de fluxo de [emails](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) do Exchange (também conhecidas como regras de transporte) nos resultados da validação DKIM.</span><span class="sxs-lookup"><span data-stu-id="e4215-119">Admins can create Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="e4215-120">Essas regras de fluxo de emails permitirão que os administradores filtrem ou roteiem mensagens conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e4215-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>