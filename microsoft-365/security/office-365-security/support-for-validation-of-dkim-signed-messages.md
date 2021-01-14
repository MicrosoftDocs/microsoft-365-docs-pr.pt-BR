---
title: Suporte para validação de mensagens assinadas por DKIM (Email Identificado por Chaves de Domínio)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Saiba mais sobre a validação de mensagens assinadas pelo DKIM no Exchange Online Protection e no Exchange Online
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845054"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="3727b-103">Suporte para validação de mensagens assinadas por DKIM</span><span class="sxs-lookup"><span data-stu-id="3727b-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3727b-104">O Exchange Online Protection (EOP) e o Exchange Online suportam validação de entrada de mensagens[DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)(Email Identificado por Chaves de Domínio).</span><span class="sxs-lookup"><span data-stu-id="3727b-104">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="3727b-105">O DKIM valida que uma  mensagem de email não foi falsa por outra  pessoa e foi enviada do domínio de onde ela diz ter vindo.</span><span class="sxs-lookup"><span data-stu-id="3727b-105">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="3727b-106">Ele vincula uma mensagem de email à organização que a enviou.</span><span class="sxs-lookup"><span data-stu-id="3727b-106">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="3727b-107">A verificação de DKIM é usada automaticamente para todas as mensagens enviadas com IPv6.</span><span class="sxs-lookup"><span data-stu-id="3727b-107">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="3727b-108">O Microsoft 365 também dá suporte a DKIM quando o email é enviado por IPv4.</span><span class="sxs-lookup"><span data-stu-id="3727b-108">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="3727b-109">(Para saber mais sobre o suporte a IPv6, veja [Suporte para mensagens de email de entrada anônimas por IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).).</span><span class="sxs-lookup"><span data-stu-id="3727b-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="3727b-110">O DKIM valida uma mensagem assinada digitalmente que aparece no DKIM-Signature dos headers da mensagem.</span><span class="sxs-lookup"><span data-stu-id="3727b-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="3727b-111">Os resultados de uma validação DKIM-Signature são carimbados no Authentication-Results de dados.</span><span class="sxs-lookup"><span data-stu-id="3727b-111">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="3727b-112">O texto do cabeçalho de mensagens tem aparência semelhante à seguinte (em que contoso.com é o remetente):</span><span class="sxs-lookup"><span data-stu-id="3727b-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="3727b-113">Para obter mais informações sobre o Authentication-Results de mensagem, consulte RFC 7001 ( Campo de header de mensagem para indicar o status de autenticação[de mensagem.](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="3727b-113">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="3727b-114">A implementação do DKIM da Microsoft está em conformidade com essa RFC.</span><span class="sxs-lookup"><span data-stu-id="3727b-114">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="3727b-115">Os administradores podem criar regras [de fluxo de emails](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) do Exchange (também conhecidas como regras de transporte) nos resultados da validação do DKIM.</span><span class="sxs-lookup"><span data-stu-id="3727b-115">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="3727b-116">Essas regras de fluxo de emails permitirão que os administradores filtrem ou roteiem mensagens conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3727b-116">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
