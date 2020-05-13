---
title: Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP
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
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Encontre respostas para as perguntas mais comuns sobre mensagens que foram enfileiradas, adiadas ou retornadas durante o processo de filtragem do Exchange Online Protection (EOP).
ms.openlocfilehash: 38e72a04e855862c621bd2b170c11407e0d22af3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206587"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP

Este tópico fornece respostas para perguntas frequentes sobre mensagens que foram enfileiradas, adiadas ou retornadas durante o processo de filtragem do Exchange Online Protection (EOP).

## <a name="why-is-mail-queuing"></a>Por que o email é enfileirado?

As mensagens são enfileiradas ou adiadas se o serviço não conseguir criar uma conexão com o servidor do destinatário para entrega. Ele não adiará mensagens se estiver retornando um erro de série 500 a partir da rede do destinatário.

## <a name="how-does-a-message-become-deferred"></a>Como uma mensagem é adiada?

As mensagens serão mantidas quando uma conexão não puder ser feita com o servidor do destinatário e o servidor do destinatário estiver retornando uma "falha temporária" como um tempo limite de conexão, conexão recusada ou um erro de série 400. Se houver uma falha permanente, como um erro de série 500, a mensagem será retornada ao remetente.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Quanto tempo uma mensagem permanece em adiamento e qual é o intervalo de repetição?

As mensagens no adiamento permanecerão nas filas por 1 dia. As tentativas de repetição de mensagens baseiam-se no tipo de erro recebido do sistema de mensagens do destinatário. As primeiras adias são 15 minutos ou menos, com novas tentativas subsequentes (na próxima meia dúzia ou mais), aumentando o intervalo de várias tentativas para um máximo de 60 minutos. A expansão de duração do intervalo é dinâmica, levando em consideração várias variáveis, como tamanhos de fila e prioridade de mensagem interna. Em básico, são 15 minutos (ou menos) para iniciar e, em seguida, expandindo a partir daí as próximas horas para 60 minutos máx.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Após a restauração do servidor de email, como mensagens enfileiradas são distribuídas?

Após a restauração de seu servidor de email, todas as mensagens enfileiradas são automaticamente processadas na ordem em que foram recebidas e enfileiradas quando o servidor ficou indisponível.
