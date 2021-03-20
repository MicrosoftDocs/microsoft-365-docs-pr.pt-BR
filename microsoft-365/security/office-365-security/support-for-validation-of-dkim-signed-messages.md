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
# <a name="support-for-validation-of-dkim-signed-messages"></a>Suporte para validação de mensagens assinadas por DKIM

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

A Proteção do Exchange Online (EOP) e o Exchange Online suportam a validação de entrada de mensagens[DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).

O DKIM valida que uma  mensagem de email não foi falsa por outra pessoa e foi enviada do domínio de onde diz *ter* vindo. Ele vincula uma mensagem de email à organização que a enviou. A verificação de DKIM é usada automaticamente para todas as mensagens enviadas com IPv6. O Microsoft 365 também dá suporte a DKIM quando o email é enviado por IPv4. (Para saber mais sobre o suporte a IPv6, veja [Suporte para mensagens de email de entrada anônimas por IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).).

O DKIM valida uma mensagem assinada digitalmente que aparece no DKIM-Signature dos headers da mensagem. Os resultados de uma validação DKIM-Signature são marcados no Authentication-Results de dados. O texto do cabeçalho de mensagens tem aparência semelhante à seguinte (em que contoso.com é o remetente):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Para obter mais informações sobre o Authentication-Results de Authentication-Results, consulte RFC 7001 ( Campo do[Header](https://www.rfc-editor.org/rfc/rfc7001.txt)de Mensagens para Indicar o Status da Autenticação de Mensagem . A implementação DKIM da Microsoft está em conformidade com essa RFC.

Os administradores podem criar regras de fluxo de [emails](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) do Exchange (também conhecidas como regras de transporte) nos resultados da validação DKIM. Essas regras de fluxo de emails permitirão que os administradores filtrem ou roteiem mensagens conforme necessário.