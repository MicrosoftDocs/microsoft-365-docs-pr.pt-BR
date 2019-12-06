---
title: Suporte para validação de mensagens assinadas por DKIM
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
description: Saiba mais sobre a validação de mensagens assinadas do DKIM no Exchange Online Protection e no Exchange Online
ms.openlocfilehash: bb02e558c7aaf07a7b13ec0bdb237a9ab84220f4
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871227"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="d654d-103">Suporte para validação de mensagens assinadas por DKIM</span><span class="sxs-lookup"><span data-stu-id="d654d-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="d654d-104">O Exchange Online Protection (EOP) e o Exchange Online suportam validação de entrada de mensagens de Email Identificado por Chaves de Domínio ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="d654d-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="d654d-105">DKIM é um método para validar que uma mensagem foi enviada do domínio que ela diz ter originado e que não foi falsificada por qualquer outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="d654d-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="d654d-106">Ele liga uma mensagem de email ao responsável da organização por enviá-la.</span><span class="sxs-lookup"><span data-stu-id="d654d-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="d654d-107">A verificação DKIM é usada automaticamente para todas as mensagens enviadas em comunicações IPv6.</span><span class="sxs-lookup"><span data-stu-id="d654d-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="d654d-108">Agora, o Office 365 também oferece suporte ao DKIM quando o email é enviado por IPv4.</span><span class="sxs-lookup"><span data-stu-id="d654d-108">Office 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="d654d-109">(Para saber mais sobre o suporte a IPv6, veja [Suporte para mensagens de email de entrada anônimas por IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).).</span><span class="sxs-lookup"><span data-stu-id="d654d-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="d654d-p102">DKIM valida uma mensagem assinada digitalmente que aparece no cabeçalho DKIM-Assinatura nos cabeçalhos de mensagens. Os resultados de uma validação DKIM-Assinatura ficam carimbados no cabeçalho Resultados-de-Autenticação que está de acordo com RFC 7001 ([Campo do cabeçalho de mensagens para indicar status de autenticação de mensagens](https://www.rfc-editor.org/rfc/rfc7001.txt)). O texto do cabeçalho de mensagens tem aparência semelhante à seguinte (em que contoso.com é o remetente):</span><span class="sxs-lookup"><span data-stu-id="d654d-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

<span data-ttu-id="d654d-113">Os administradores podem criar [regras de fluxo de emails](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) do Exchange (também conhecidas como regras de transporte) nos resultados de uma validação de DKIM para filtrar ou rotear mensagens, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="d654d-113">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span>
