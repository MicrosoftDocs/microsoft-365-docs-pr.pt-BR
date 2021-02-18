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
# <a name="backscatter-in-eop"></a>Dispersão inversa no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*Backscatter* são relatórios de não entrega (também conhecidos como NDRs ou mensagens de rejeição) que você recebe para mensagens que você não enviou. Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lendity to their messages. Portanto, quando remetentes de spam inevitavelmente enviam mensagens para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino é essencialmente complicado para retornar a mensagem não entregue em uma NDR para o remetente forjado no endereço De:.

Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP se esforça para identificar e soltar silenciosamente mensagens de fontes mal-confiáveis sem gerar uma NDR. Porém, com base no volume total de emails que fluem pelo serviço, sempre existe a possibilidade de que o EOP enviará backscatter sem querer.

Backscatterer.org mantém uma lista de bloqueios (também conhecida como uma lista de bloqueios de DNS ou DNSBL) de servidores de email que foram responsáveis por enviar backscatter, e os servidores EOP podem aparecer nessa lista. Porém, não tentamos remover a si mesmo da lista de Backscatterer.org porque ela não é uma lista de remetentes de spam (por sua própria admissão).

> [!TIP]
> O Backscatter.org site ( ) recomenda usar seu serviço para verificar o email de entrada no modo de segurança em vez do modo rejeitar (serviços de email grandes quase sempre enviam <http://www.backscatterer.org/?target=usage> algum backscatter).
