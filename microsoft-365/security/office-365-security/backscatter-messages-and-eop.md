---
title: Mnsagens backscatter e EOP
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
ms.openlocfilehash: f6e8398565837f7a380c8a6a5c4cd8de422cc215
ms.sourcegitcommit: ca4ce9e8c7e4b433608cd059857740ffd5a472c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2019
ms.locfileid: "40840160"
---
# <a name="backscatter-messages-and-eop"></a>Mensagens backscatter e EOP

*Mensagens de dispersão* são notificações de falha na entrega (também conhecidas como NDRs ou mensagens de devolução) que você recebe para mensagens que não enviou. Os spammers forjam (falsificam) o endereço de: de suas mensagens e freqüentemente usam endereços de email reais para dar credibilidade às suas mensagens. Portanto, quando eles enviam mensagens inevitavelmente para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino pode dutifully responder com uma notificação de falha na entrega, que é enviada para o remetente forjado no endereço de:.

O proteção do Exchange Online (EOP) faz todos os esforços para identificar e soltar silenciosamente mensagens de fontes do dubious sem gerar uma notificação de falha na entrega. Mas, com base no volume de email simples que flui pelo serviço, sempre há a possibilidade de que o EOP envie mensagens de inspersão involuntariamente.

O Backscatterer.org mantém uma lista de bloqueios (também conhecida como lista de bloqueio de DNS ou DNSBL) dos servidores de email que foram responsáveis por enviar mensagens de dispersão, e os servidores do EOP podem aparecer na lista. No entanto, não tentamos removê-lo da lista de bloqueios do Backscatterer.org porque não é uma lista de remetentes de spam (por sua própria admissão).

> [!TIP]
> De acordo com o dispersa. ou`http://www.backscatterer.org/?target=usage`site (), eles recomendam o uso de seus serviços para verificar emails de entrada no modo de segurança, em vez de rejeitar modo (grandes serviços de email quase sempre enviam algumas mensagens de inspersão).
