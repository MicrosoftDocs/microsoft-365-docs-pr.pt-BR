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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Encontre respostas para as perguntas mais comuns sobre mensagens que foram enfileiradas, adiadas ou retornadas durante o processo de filtragem do Exchange Online Protection (EOP).
ms.openlocfilehash: 76fe08f3a83321b6c0549dae5f1382ead5f0b3ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827744"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="5ed63-103">Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP</span><span class="sxs-lookup"><span data-stu-id="5ed63-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="5ed63-104">Este tópico fornece respostas para perguntas frequentes sobre mensagens que foram enfileiradas, adiadas ou retornadas durante o processo de filtragem do Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="5ed63-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="5ed63-105">Por que o email é enfileirado?</span><span class="sxs-lookup"><span data-stu-id="5ed63-105">Why is mail queuing?</span></span>

<span data-ttu-id="5ed63-106">As mensagens são enfileiradas ou adiadas se o serviço não conseguir criar uma conexão com o servidor do destinatário para entrega.</span><span class="sxs-lookup"><span data-stu-id="5ed63-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="5ed63-107">Ele não adiará mensagens se estiver retornando um erro de série 500 a partir da rede do destinatário.</span><span class="sxs-lookup"><span data-stu-id="5ed63-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="5ed63-108">Como uma mensagem é adiada?</span><span class="sxs-lookup"><span data-stu-id="5ed63-108">How does a message become deferred?</span></span>

<span data-ttu-id="5ed63-109">As mensagens serão mantidas quando uma conexão não puder ser feita com o servidor do destinatário e o servidor do destinatário estiver retornando uma "falha temporária" como um tempo limite de conexão, conexão recusada ou um erro de série 400.</span><span class="sxs-lookup"><span data-stu-id="5ed63-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="5ed63-110">Se houver uma falha permanente, como um erro de série 500, a mensagem será retornada ao remetente.</span><span class="sxs-lookup"><span data-stu-id="5ed63-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="5ed63-111">Quanto tempo uma mensagem permanece em adiamento e qual é o intervalo de repetição?</span><span class="sxs-lookup"><span data-stu-id="5ed63-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="5ed63-112">As mensagens no adiamento permanecerão nas filas por 1 dia.</span><span class="sxs-lookup"><span data-stu-id="5ed63-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="5ed63-113">As tentativas de repetição de mensagens baseiam-se no tipo de erro recebido do sistema de mensagens do destinatário.</span><span class="sxs-lookup"><span data-stu-id="5ed63-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="5ed63-114">As primeiras adias são 15 minutos ou menos, com novas tentativas subsequentes (na próxima meia dúzia ou mais), aumentando o intervalo de várias tentativas para um máximo de 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="5ed63-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="5ed63-115">A expansão de duração do intervalo é dinâmica, levando em consideração várias variáveis, como tamanhos de fila e prioridade de mensagem interna.</span><span class="sxs-lookup"><span data-stu-id="5ed63-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="5ed63-116">Em básico, são 15 minutos (ou menos) para iniciar e, em seguida, expandindo a partir daí as próximas horas para 60 minutos máx.</span><span class="sxs-lookup"><span data-stu-id="5ed63-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="5ed63-117">Após a restauração do servidor de email, como mensagens enfileiradas são distribuídas?</span><span class="sxs-lookup"><span data-stu-id="5ed63-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="5ed63-118">Após a restauração de seu servidor de email, todas as mensagens enfileiradas são automaticamente processadas na ordem em que foram recebidas e enfileiradas quando o servidor ficou indisponível.</span><span class="sxs-lookup"><span data-stu-id="5ed63-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
