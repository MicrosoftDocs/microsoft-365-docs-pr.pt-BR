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
description: Encontre respostas para as perguntas mais comuns sobre mensagens que foram enluadas, adiadas ou recuperadas durante o processo de filtragem do Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054387"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="44271-103">Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP</span><span class="sxs-lookup"><span data-stu-id="44271-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="44271-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="44271-104">**Applies to**</span></span>
- [<span data-ttu-id="44271-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="44271-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="44271-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="44271-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="44271-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44271-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="44271-108">Este tópico fornece respostas para perguntas frequentes sobre mensagens que foram enluadas, adiadas ou recuperadas durante o processo de filtragem do Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="44271-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="44271-109">Por que o email é enfileirado?</span><span class="sxs-lookup"><span data-stu-id="44271-109">Why is mail queuing?</span></span>

<span data-ttu-id="44271-110">As mensagens são enfileiradas ou adiadas se o serviço não conseguir criar uma conexão com o servidor do destinatário para entrega.</span><span class="sxs-lookup"><span data-stu-id="44271-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="44271-111">Ele não adiará mensagens se estiver retornando um erro de série 500 a partir da rede do destinatário.</span><span class="sxs-lookup"><span data-stu-id="44271-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="44271-112">Como uma mensagem é adiada?</span><span class="sxs-lookup"><span data-stu-id="44271-112">How does a message become deferred?</span></span>

<span data-ttu-id="44271-113">As mensagens serão mantidas quando uma conexão não puder ser feita com o servidor do destinatário e o servidor do destinatário estiver retornando uma "falha temporária" como um tempo limite de conexão, conexão recusada ou um erro de série 400.</span><span class="sxs-lookup"><span data-stu-id="44271-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="44271-114">Se houver uma falha permanente, como um erro de série 500, a mensagem será retornada ao remetente.</span><span class="sxs-lookup"><span data-stu-id="44271-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="44271-115">Quanto tempo uma mensagem permanece em adiamento e qual é o intervalo de repetição?</span><span class="sxs-lookup"><span data-stu-id="44271-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="44271-116">As mensagens em adiamento permanecerão em nossas filas por 1 dia.</span><span class="sxs-lookup"><span data-stu-id="44271-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="44271-117">As tentativas de repetição de mensagens baseiam-se no tipo de erro recebido do sistema de mensagens do destinatário.</span><span class="sxs-lookup"><span data-stu-id="44271-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="44271-118">Os primeiros adiamentos são de 15 minutos ou menos, com recuperações subsequentes (durante a próxima meia dúzia ou mais) aumentando o intervalo sobre várias recuperações para um máximo de 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="44271-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="44271-119">A expansão da duração do intervalo é dinâmica, levando em consideração várias variáveis, como tamanhos de fila e prioridade interna da mensagem.</span><span class="sxs-lookup"><span data-stu-id="44271-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="44271-120">No básico, são 15 minutos (ou menos) para começar e, em seguida, expandindo-se de lá nas próximas horas para 60 minutos no máximo.</span><span class="sxs-lookup"><span data-stu-id="44271-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="44271-121">Após a restauração do servidor de email, como mensagens enfileiradas são distribuídas?</span><span class="sxs-lookup"><span data-stu-id="44271-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="44271-122">Após a restauração de seu servidor de email, todas as mensagens enfileiradas são automaticamente processadas na ordem em que foram recebidas e enfileiradas quando o servidor ficou indisponível.</span><span class="sxs-lookup"><span data-stu-id="44271-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
