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
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2020
ms.locfileid: "42313806"
---
# <a name="backscatter-messages-and-eop"></a>Mnsagens backscatter e EOP

*Mensagens de dispersão* são notificações de falha na entrega (também conhecidas como NDRs ou mensagens de devolução) que você recebe para mensagens que não enviou. Os spammers forjam (falsificam) o endereço de: de suas mensagens e freqüentemente usam endereços de email reais para dar credibilidade às suas mensagens. Portanto, quando um remetente de spam envia mensagens inevitavelmente para destinatários não existentes (spam é uma operação de alto volume), o servidor de email de destino provavelmente retornará a mensagem não entregue em uma notificação de falha na entrega, que é enviada ao remetente forjado no endereço de:.

O proteção do Exchange Online (EOP) faz todos os esforços para identificar e soltar silenciosamente mensagens de fontes do dubious sem gerar uma notificação de falha na entrega. Mas, com base no volume de email simples que flui pelo serviço, sempre há a possibilidade de que o EOP envie mensagens de inspersão involuntariamente.

O Backscatterer.org mantém uma lista de bloqueios (também conhecida como lista de bloqueio de DNS ou DNSBL) dos servidores de email que foram responsáveis por enviar mensagens de dispersão, e os servidores do EOP podem aparecer na lista. No entanto, não tentamos removê-lo da lista de bloqueios do Backscatterer.org porque não é uma lista de remetentes de spam (por sua própria admissão).

> [!TIP]
> O site do Backscatter.org<http://www.backscatterer.org/?target=usage>() recomenda usar o serviço para verificar emails de entrada no modo de segurança, em vez de rejeitar modo (grandes serviços de email quase sempre enviam algumas mensagens de inspersão).
