---
title: Pool de entrega de alto risco para mensagens de saída
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Quando o sistema de email de um cliente é comprometido por malware ou um ataque de spam mal-intencionado e está enviando spam de saída por meio do serviço de filtragem hospedado, isso pode resultar em endereços IP dos servidores de data center do Office 365 listados no bloco de terceiros contém.
ms.openlocfilehash: 5b9241dead5b40e9f216ecd3023d6f8b86fb0205
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072449"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="6fddd-103">Pool de entrega de alto risco para mensagens de saída</span><span class="sxs-lookup"><span data-stu-id="6fddd-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="6fddd-104">Quando o sistema de email de um cliente é comprometido por malware ou um ataque de spam mal-intencionado e está enviando spam de saída por meio do serviço de filtragem hospedado, isso pode resultar em endereços IP dos servidores de data center do Office 365 listados no bloco de terceiros contém.</span><span class="sxs-lookup"><span data-stu-id="6fddd-104">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists.</span></span> <span data-ttu-id="6fddd-105">Servidores de destino que não usam o serviço de filtragem hospedado, mas usam essas listas de bloqueio, rejeitam todos os emails enviados de qualquer um dos endereços IP de filtragem hospedado que foram adicionados a essas listas.</span><span class="sxs-lookup"><span data-stu-id="6fddd-105">Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists.</span></span> <span data-ttu-id="6fddd-106">Para evitar isso, todas as mensagens de saída que excedem o limite de spam são enviadas por meio de um pool de entrega de alto risco.</span><span class="sxs-lookup"><span data-stu-id="6fddd-106">To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool.</span></span> <span data-ttu-id="6fddd-107">Esse pool de emails de saída secundário só é usado para enviar mensagens que podem ter baixa qualidade.</span><span class="sxs-lookup"><span data-stu-id="6fddd-107">This secondary outbound email pool is only used to send messages that may be of low quality.</span></span> <span data-ttu-id="6fddd-108">Isso ajuda a proteger o restante da rede de enviar mensagens que são mais prováveis no bloqueio do endereço IP de envio.</span><span class="sxs-lookup"><span data-stu-id="6fddd-108">This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="6fddd-109">O uso de um pool de entrega de alto risco dedicado ajuda a garantir que o pool de saída normal só esteja enviando mensagens conhecidas por uma alta qualidade.</span><span class="sxs-lookup"><span data-stu-id="6fddd-109">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality.</span></span> <span data-ttu-id="6fddd-110">O uso desse pool IP secundário ajuda a reduzir a probabilidade de o pool de saída de IP normal ser adicionado a uma lista de bloqueados.</span><span class="sxs-lookup"><span data-stu-id="6fddd-110">Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list.</span></span> <span data-ttu-id="6fddd-111">A possibilidade de um pool de entrega de alto risco ser colocado em uma lista bloqueada continua a ser um risco.</span><span class="sxs-lookup"><span data-stu-id="6fddd-111">The possibility of the high-risk delivery pool being placed on a blocked list remains a risk.</span></span> <span data-ttu-id="6fddd-112">Isso é esperado.</span><span class="sxs-lookup"><span data-stu-id="6fddd-112">This is by design.</span></span>
  
<span data-ttu-id="6fddd-113">Mensagens em que o domínio de envio não tem registro de endereço (um registro), que fornece o endereço IP do domínio, e nenhum registro MX, que ajuda a direcionar o email aos servidores que devem receber o email de um domínio específico no DNS, são sempre roteados através do pool de entrega de alto risco independentemente da disposição de spam.</span><span class="sxs-lookup"><span data-stu-id="6fddd-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="6fddd-114">Noções básicas sobre mensagens de notificação de status de entrega (DSN)</span><span class="sxs-lookup"><span data-stu-id="6fddd-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="6fddd-115">O pool de entrega de alto risco de saída gerencia a entrega de todas as mensagens "devolvidas" ou "com falha" (DSN).</span><span class="sxs-lookup"><span data-stu-id="6fddd-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="6fddd-116">As possíveis causas para um surto nas mensagens DSN incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6fddd-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="6fddd-117">Uma campanha de falsificação que afete um dos clientes que utilizam o serviço</span><span class="sxs-lookup"><span data-stu-id="6fddd-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="6fddd-118">Um ataque de coleta de diretório</span><span class="sxs-lookup"><span data-stu-id="6fddd-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="6fddd-119">Um ataque de spam</span><span class="sxs-lookup"><span data-stu-id="6fddd-119">A spam attack</span></span>
    
- <span data-ttu-id="6fddd-120">Um servidor SMTP invasor</span><span class="sxs-lookup"><span data-stu-id="6fddd-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="6fddd-121">Todos esses problemas podem resultar em um aumento repentino no número de mensagens DSN processadas pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="6fddd-121">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service.</span></span> <span data-ttu-id="6fddd-122">Muitas vezes, essas mensagens DSN parecem ser spam para outros serviços e servidores de email.</span><span class="sxs-lookup"><span data-stu-id="6fddd-122">Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="6fddd-123">Para saber mais</span><span class="sxs-lookup"><span data-stu-id="6fddd-123">For more information</span></span>

[<span data-ttu-id="6fddd-124">Configurar a política de spam de saída</span><span class="sxs-lookup"><span data-stu-id="6fddd-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="6fddd-125">Perguntas frequentes sobre proteção antispam</span><span class="sxs-lookup"><span data-stu-id="6fddd-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

