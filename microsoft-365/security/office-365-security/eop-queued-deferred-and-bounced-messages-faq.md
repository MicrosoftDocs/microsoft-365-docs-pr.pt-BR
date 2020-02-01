---
title: Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: Este tópico fornece respostas para perguntas frequentes sobre mensagens que foram enfileiradas, adiadas ou retornadas durante o processo de filtragem do Microsoft Proteção do Exchange Online (EOP).
ms.openlocfilehash: 05993e8d0e9af69dd1ac35b588c4e8ec731642f7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599348"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="a9e30-103">Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP</span><span class="sxs-lookup"><span data-stu-id="a9e30-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="a9e30-104">Este tópico fornece respostas para perguntas frequentes sobre mensagens que foram enfileiradas, adiadas ou retornadas durante o processo de filtragem do Microsoft Proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="a9e30-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>

<span data-ttu-id="a9e30-105">**P. Por que o email é enfileirado?**</span><span class="sxs-lookup"><span data-stu-id="a9e30-105">**Q. Why is mail queuing?**</span></span>

<span data-ttu-id="a9e30-p101">R. As mensagens são enfileiradas ou adiadas se o serviço não conseguir criar uma conexão com o servidor do destinatário para entrega. Ele não adiará mensagens se estiver retornando um erro de série 500 a partir da rede do destinatário.</span><span class="sxs-lookup"><span data-stu-id="a9e30-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

<span data-ttu-id="a9e30-109">**P. Como uma mensagem é adiada?**</span><span class="sxs-lookup"><span data-stu-id="a9e30-109">**Q. How does a message become deferred?**</span></span>

<span data-ttu-id="a9e30-p102">R. As mensagens serão mantidas quando uma conexão não puder ser feita com o servidor do destinatário e o servidor do destinatário estiver retornando uma "falha temporária" como um tempo limite de conexão, conexão recusada ou um erro de série 400. Se houver uma falha permanente, como um erro de série 500, a mensagem será retornada ao remetente.</span><span class="sxs-lookup"><span data-stu-id="a9e30-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

<span data-ttu-id="a9e30-113">**P. Quanto tempo uma mensagem permanece em adiamento e qual é o intervalo de repetição?**</span><span class="sxs-lookup"><span data-stu-id="a9e30-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>

<span data-ttu-id="a9e30-114">R.</span><span class="sxs-lookup"><span data-stu-id="a9e30-114">A.</span></span> <span data-ttu-id="a9e30-115">As mensagens no adiamento permanecerão nas filas por 1 dia.</span><span class="sxs-lookup"><span data-stu-id="a9e30-115">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="a9e30-116">As tentativas de repetição de mensagens baseiam-se no tipo de erro recebido do sistema de mensagens do destinatário.</span><span class="sxs-lookup"><span data-stu-id="a9e30-116">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="a9e30-117">As primeiras adias são 15 minutos ou menos, com novas tentativas subsequentes (na próxima meia dúzia ou mais), aumentando o intervalo de várias tentativas para um máximo de 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="a9e30-117">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="a9e30-118">A expansão de duração do intervalo é dinâmica, levando em consideração várias variáveis, como tamanhos de fila e prioridade de mensagem interna.</span><span class="sxs-lookup"><span data-stu-id="a9e30-118">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="a9e30-119">Em básico, são 15 minutos (ou menos) para iniciar e, em seguida, expandindo a partir daí as próximas horas para 60 minutos máx.</span><span class="sxs-lookup"><span data-stu-id="a9e30-119">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

<span data-ttu-id="a9e30-120">**P. Após a restauração do servidor de email, como mensagens enfileiradas são distribuídas?**</span><span class="sxs-lookup"><span data-stu-id="a9e30-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>

<span data-ttu-id="a9e30-p104">R. Após a restauração de seu servidor de email, todas as mensagens enfileiradas são automaticamente processadas na ordem em que foram recebidas e enfileiradas quando o servidor ficou indisponível.</span><span class="sxs-lookup"><span data-stu-id="a9e30-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
