---
title: Suporte para mensagens de email de entrada anônimas por IPv6
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Saiba como configurar o suporte para mensagens anônimas de fontes IPv6 para o Exchange Online Protection e o Exchange Online.
ms.openlocfilehash: 1cd38798aa644b79c8f1d6362edd17a515b5c98d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598228"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="4a5b3-103">Suporte para mensagens de email de entrada anônimas por IPv6</span><span class="sxs-lookup"><span data-stu-id="4a5b3-103">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="4a5b3-104">Exchange Online Protection (EOP) e Exchange Online suportam o recebimento de mensagens de email de entrada anônimas sobre comunicações IPv6 de remetentes que não enviam mensagens sobre Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="4a5b3-104">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS).</span></span> <span data-ttu-id="4a5b3-105">Você pode optar por receber mensagens por IPv6 solicitando essa funcionalidade do suporte da Microsoft abrindo o centro de administração do Microsoft 365 em [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), clicando em **suporte**e, em seguida, clicando em **nova solicitação de serviço**.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-105">You can opt-in to receive messages over IPv6 by requesting this functionality from Microsoft Support by opening the Microsoft 365 admin center at [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), clicking **Support**, and then clicking **New service request**).</span></span> <span data-ttu-id="4a5b3-106">Se você não optar por IPv6, continuará recebendo mensagens sobre IPv4.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-106">If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="4a5b3-107">Remetentes que transmitem mensagens para serviço sobre IPv6 devem cumprir com os dois requisitos a seguir:</span><span class="sxs-lookup"><span data-stu-id="4a5b3-107">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="4a5b3-108">O endereço de IPv6 remetente deve ter um registro PTR válido ([registro DNS inverso](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) do endereço IPv6 remetente).</span><span class="sxs-lookup"><span data-stu-id="4a5b3-108">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="4a5b3-109">O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](https://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="4a5b3-109">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="4a5b3-110">É obrigatório cumprir com esses requisitos, independentemente da configuração anterior à escolha do IPv6.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-110">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6.</span></span> <span data-ttu-id="4a5b3-111">Se ambos os requisitos forem satisfeitos, a mensagem passará pelo filtro de mensagens de email normal fornecido pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-111">If both requirements are met, the message will go through normal email message filtering provided by the service.</span></span> <span data-ttu-id="4a5b3-112">Se uma ou outra não for atendida, a mensagem será rejeitada com uma das seguintes respostas 450:</span><span class="sxs-lookup"><span data-stu-id="4a5b3-112">If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="4a5b3-113">Se você não tiver a opção de receber mensagens sobre IPv6 e o remetente tentar forçar uma mensagem sobre IPv6 manualmente conectando-se ao servidor de email, a mensagem será rejeitada com uma resposta 550 parecida com a seguinte:</span><span class="sxs-lookup"><span data-stu-id="4a5b3-113">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="4a5b3-114">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="4a5b3-114">For more information</span></span>

[<span data-ttu-id="4a5b3-115">Suporte para validação de mensagens assinadas por DKIM</span><span class="sxs-lookup"><span data-stu-id="4a5b3-115">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

