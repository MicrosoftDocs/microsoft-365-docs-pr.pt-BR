---
title: Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Encontre respostas para as perguntas mais comuns sobre mensagens que foram en filas, adiadas ou recuperadas durante o processo de filtragem do Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e54a260a70a9c68a94412243308bffe60d989e99
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289694"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Este tópico fornece respostas para perguntas frequentes sobre mensagens que foram en filas, adiadas ou recuperadas durante o processo de filtragem do Exchange Online Protection (EOP).

## <a name="why-is-mail-queuing"></a>Por que o email é enfileirado?

As mensagens são enfileiradas ou adiadas se o serviço não conseguir criar uma conexão com o servidor do destinatário para entrega. Ele não adiará mensagens se estiver retornando um erro de série 500 a partir da rede do destinatário.

## <a name="how-does-a-message-become-deferred"></a>Como uma mensagem é adiada?

As mensagens serão mantidas quando uma conexão não puder ser feita com o servidor do destinatário e o servidor do destinatário estiver retornando uma "falha temporária" como um tempo limite de conexão, conexão recusada ou um erro de série 400. Se houver uma falha permanente, como um erro de série 500, a mensagem será retornada ao remetente.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Quanto tempo uma mensagem permanece em adiamento e qual é o intervalo de repetição?

As mensagens em adiamento permanecerão em nossas filas por 1 dia. As tentativas de repetição de mensagens baseiam-se no tipo de erro recebido do sistema de mensagens do destinatário. Os primeiros adiamentos são de 15 minutos ou menos, com as próximas setas (nas próximas meia dezenas ou mais) aumentando o intervalo em várias setas para um máximo de 60 minutos. A expansão da duração do intervalo é dinâmica, levando em consideração várias variáveis, como tamanhos de fila e prioridade interna de mensagens. No básico, são 15 minutos (ou menos) para começar e, em seguida, expandindo de lá nas próximas horas para 60 minutos no máximo.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Após a restauração do servidor de email, como mensagens enfileiradas são distribuídas?

Após a restauração de seu servidor de email, todas as mensagens enfileiradas são automaticamente processadas na ordem em que foram recebidas e enfileiradas quando o servidor ficou indisponível.
