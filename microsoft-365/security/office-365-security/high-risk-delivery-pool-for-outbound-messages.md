---
title: Pool de entrega de alto risco para mensagens de saída
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Saiba como o pool de entrega de alto risco é usado para proteger a reputação de servidores de email nos datacenters do Microsoft 365.
ms.openlocfilehash: 7fb4788361534335be1e07bae44ed7511bebe434
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638029"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="0cc80-103">Pool de entrega de alto risco para mensagens de saída</span><span class="sxs-lookup"><span data-stu-id="0cc80-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="0cc80-104">Os servidores de email nos datacenters do Microsoft 365 podem ser temporariamente culpados no envio de spam.</span><span class="sxs-lookup"><span data-stu-id="0cc80-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="0cc80-105">Por exemplo, um ataque de malware ou spam mal-intencionado em uma organização de email local que envia emails de saída pelo Microsoft 365 ou contas do Microsoft 365 comprometidas.</span><span class="sxs-lookup"><span data-stu-id="0cc80-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="0cc80-106">Esses cenários podem resultar no endereço IP dos servidores de datacenters do Microsoft 365 afetados que aparecem nas listas de bloqueios de terceiros.</span><span class="sxs-lookup"><span data-stu-id="0cc80-106">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="0cc80-107">As organizações de email de destino que usam essas listas de bloqueio rejeitarão emails dessas fontes de mensagens.</span><span class="sxs-lookup"><span data-stu-id="0cc80-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="0cc80-108">Para evitar isso, todas as mensagens de saída dos servidores de datacenter da Microsoft 365 que são determinados como spam ou que excedem os limites de envio do [serviço](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ou [as políticas de spam de saída](configure-the-outbound-spam-policy.md) são enviadas através do pool de _entrega de alto risco_.</span><span class="sxs-lookup"><span data-stu-id="0cc80-108">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="0cc80-109">O pool de entrega de alto risco é um pool de endereços IP secundário para email de saída que só é usado para enviar mensagens de "baixa qualidade" (por exemplo, spam e [dispersão](backscatter-messages-and-eop.md)).</span><span class="sxs-lookup"><span data-stu-id="0cc80-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="0cc80-110">O uso do pool de entrega de alto risco ajuda a evitar que o pool de endereços IP normal para email de saída envie spam.</span><span class="sxs-lookup"><span data-stu-id="0cc80-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="0cc80-111">O pool de endereços IP normal para email de saída mantém a reputação de enviar mensagens de "alta qualidade", o que reduz a probabilidade de que esse endereço IP apareça em listas de bloqueios de IP.</span><span class="sxs-lookup"><span data-stu-id="0cc80-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="0cc80-112">A possibilidade real de que os endereços IP no pool de entrega de alto risco sejam colocados em listas de bloqueios de IP permaneça, mas isso ocorre por design.</span><span class="sxs-lookup"><span data-stu-id="0cc80-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="0cc80-113">A entrega aos destinatários pretendidos não é garantida, pois muitas organizações de email não aceitarão mensagens do pool de entrega de alto risco.</span><span class="sxs-lookup"><span data-stu-id="0cc80-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="0cc80-114">Para obter mais informações, consulte [controlar spam de saída](outbound-spam-controls.md).</span><span class="sxs-lookup"><span data-stu-id="0cc80-114">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0cc80-115">Mensagens em que o domínio de email de origem não tem um registro A e nenhum registro MX definido no DNS público sempre é roteado através do pool de entrega de alto risco, independentemente da disposição de spam ou de limite de envio.</span><span class="sxs-lookup"><span data-stu-id="0cc80-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="0cc80-116">Mensagens de devolução</span><span class="sxs-lookup"><span data-stu-id="0cc80-116">Bounce messages</span></span>

<span data-ttu-id="0cc80-117">O pool de entrega de alto risco de saída gerencia a entrega de todas as notificações de falha na entrega (também conhecidas como NDRs, mensagens de devolução, notificações de status de entrega ou DSNs).</span><span class="sxs-lookup"><span data-stu-id="0cc80-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="0cc80-118">As possíveis causas para uma sobrecarga nos NDRs incluem:</span><span class="sxs-lookup"><span data-stu-id="0cc80-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="0cc80-119">Uma campanha de falsificação que afeta um dos clientes que usam o serviço.</span><span class="sxs-lookup"><span data-stu-id="0cc80-119">A spoofing campaign that affects one of the customers using the service.</span></span>

- <span data-ttu-id="0cc80-120">Um ataque de coleta de diretório.</span><span class="sxs-lookup"><span data-stu-id="0cc80-120">A directory harvest attack.</span></span>

- <span data-ttu-id="0cc80-121">Um ataque de spam.</span><span class="sxs-lookup"><span data-stu-id="0cc80-121">A spam attack.</span></span>

- <span data-ttu-id="0cc80-122">Um servidor de emails não autorizados.</span><span class="sxs-lookup"><span data-stu-id="0cc80-122">A rogue email server.</span></span>

<span data-ttu-id="0cc80-123">Todos esses problemas podem resultar em um aumento repentino no número de NDRs que estão sendo processados pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="0cc80-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="0cc80-124">Muitas vezes, esses NDRs parecem ser spam para outros servidores de email e serviços (também conhecidos como _[dispersão](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="0cc80-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
