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
ms.openlocfilehash: 2a752c89e2430f24441d14178942b89362736322
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203582"
---
# <a name="backscatter-in-eop"></a>Dispersão inversa no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


A *dispersão* é uma notificação de falha na entrega (também conhecida como NDRs ou mensagens de devolução) que você recebe para mensagens que não enviou. Os spammers forjam (falsificam) o endereço de: de suas mensagens e freqüentemente usam endereços de email reais para dar credibilidade às suas mensagens. Portanto, quando os spammers inevitavelmente enviam mensagens para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino é essencialmente induzido a retornar a mensagem não entregue em um NDR para o remetente forjado no endereço de:.

Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP faz todos os esforços para identificar e cancelar silenciosamente mensagens de fontes do dubious sem gerar uma notificação de falha na entrega. Mas, com base nos emails de volume simples que fluem pelo serviço, há sempre a possibilidade de que o EOP envie involuntariamente a dispersão.

O Backscatterer.org mantém uma lista de bloqueios (também conhecida como lista de bloqueio de DNS ou DNSBL) dos servidores de email que foram responsáveis por enviar a dispersão, e os servidores do EOP podem aparecer nessa lista. No entanto, não tentamos removê-lo da lista de bloqueios do Backscatterer.org porque não é uma lista de remetentes de spam (por sua própria admissão).

> [!TIP]
> O site do Backscatter.org ( <http://www.backscatterer.org/?target=usage> ) recomenda o uso de seus serviços para verificar emails de entrada no modo de segurança, em vez de rejeitar modo (grandes serviços de email quase sempre enviam algumas dispersão).
