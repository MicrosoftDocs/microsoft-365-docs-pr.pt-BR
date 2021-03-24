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
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053708"
---
# <a name="backscatter-in-eop"></a>Dispersão inversa no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* é relatórios de não entrega (também conhecidos como NDRs ou mensagens de rejeição) que você recebe para mensagens que você não enviou. Os remetentes de spam forjam (falsificam) o De: endereço de suas mensagens e costumam usar endereços de email reais para dar credibilidade às suas mensagens. Portanto, quando os remetentes de spam inevitavelmente enviam mensagens para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino é essencialmente enganoso para retornar a mensagem não entregue em uma NDR para o remetente forjado no endereço From:.

Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP faz todos os esforços para identificar e soltar silenciosamente mensagens de fontes dúbias sem gerar uma NDR. Mas, com base no volume total de emails que flui pelo serviço, sempre há a possibilidade de que o EOP envie backscatter sem querer.

Backscatterer.org mantém uma lista de bloqueios (também conhecida como uma lista de bloqueios DNS ou DNSBL) de servidores de email responsáveis pelo envio de backscatter, e os servidores EOP podem aparecer nesta lista. Porém, não tentamos nos remover da lista de bloqueios Backscatterer.org porque não é uma lista de spammers (por sua própria admissão).

> [!TIP]
> O Backscatter.org site ( ) recomenda usar seu serviço para verificar emails de entrada no modo seguro em vez do modo Rejeitar (grandes serviços de email quase sempre enviam algum <http://www.backscatterer.org/?target=usage> backscatter).
