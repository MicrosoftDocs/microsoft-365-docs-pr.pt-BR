---
title: Pools de entrega de saída
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Saiba como os pools de entrega são usados para proteger a reputação dos servidores de email nos datacenters do Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599906"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="e5d80-103">Pools de entrega de saída</span><span class="sxs-lookup"><span data-stu-id="e5d80-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e5d80-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e5d80-104">**Applies to**</span></span>
- [<span data-ttu-id="e5d80-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e5d80-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e5d80-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e5d80-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e5d80-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5d80-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e5d80-108">Os servidores de email nos datacenters do Microsoft 365 podem ser temporariamente considerados como os que enviam spam.</span><span class="sxs-lookup"><span data-stu-id="e5d80-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="e5d80-109">Por exemplo, um ataque de malware ou spam mal-intencionado em uma organização de email local que envia emails de saída por meio do Microsoft 365 ou contas comprometidas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5d80-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="e5d80-110">Os invasores também tentam evitar a detecção retransmitindo mensagens por meio do encaminhamento do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5d80-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="e5d80-111">Esses cenários podem resultar no endereço IP dos servidores de datacenter do Microsoft 365 afetados que aparecem em listas de bloqueios de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e5d80-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="e5d80-112">As organizações de email de destino que usam essas listas de bloqueio rejeitarão emails dessas fontes de mensagens.</span><span class="sxs-lookup"><span data-stu-id="e5d80-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="e5d80-113">Pool de entrega de alto risco</span><span class="sxs-lookup"><span data-stu-id="e5d80-113">High-risk delivery pool</span></span>
<span data-ttu-id="e5d80-114">Para evitar isso, todas as mensagens de saída dos servidores de datacenter do Microsoft 365 que são determinadas como spam ou que excedem os limites de envio do serviço ou das políticas de [spam](configure-the-outbound-spam-policy.md) de saída são enviadas por meio do _pool_ de entrega de alto risco. [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="e5d80-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="e5d80-115">O pool de entrega de alto risco é um pool de endereços IP separado para email de saída que é usado apenas para enviar mensagens de "baixa qualidade" (por exemplo, spam e [backscatter](backscatter-messages-and-eop.md)).</span><span class="sxs-lookup"><span data-stu-id="e5d80-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="e5d80-116">O uso do pool de entrega de alto risco ajuda a impedir que o pool de endereços IP normal para email de saída envie spam.</span><span class="sxs-lookup"><span data-stu-id="e5d80-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="e5d80-117">O pool de endereços IP normal para email de saída mantém a reputação de envio de mensagens de "alta qualidade", o que reduz a probabilidade de que esses endereços IP apareçam em listas de bloqueios de IP.</span><span class="sxs-lookup"><span data-stu-id="e5d80-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="e5d80-118">A possibilidade muito real de que os endereços IP no pool de entrega de alto risco sejam colocados em listas de bloqueios de IP permanece, mas isso é por design.</span><span class="sxs-lookup"><span data-stu-id="e5d80-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="e5d80-119">A entrega aos destinatários pretendido não é garantida, pois muitas organizações de email não aceitarão mensagens do pool de entrega de alto risco.</span><span class="sxs-lookup"><span data-stu-id="e5d80-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="e5d80-120">Para obter mais informações, consulte [Control outbound spam](outbound-spam-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e5d80-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e5d80-121">As mensagens em que o domínio de email de origem não tem registro A e nenhum registro MX definido no DNS público são sempre roteadas pelo pool de entrega de alto risco, independentemente de seu spam ou disposição de limite de envio.</span><span class="sxs-lookup"><span data-stu-id="e5d80-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="e5d80-122">Mensagens de rejeição</span><span class="sxs-lookup"><span data-stu-id="e5d80-122">Bounce messages</span></span>

<span data-ttu-id="e5d80-123">O pool de entrega de alto risco de saída gerencia a entrega de todos os relatórios de não entrega (também conhecidos como NDRs, mensagens de rejeição, notificações de status de entrega ou DSNs).</span><span class="sxs-lookup"><span data-stu-id="e5d80-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="e5d80-124">As possíveis causas para uma sobrecarga em NDRs incluem:</span><span class="sxs-lookup"><span data-stu-id="e5d80-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="e5d80-125">Uma campanha de spoofing que afeta um dos clientes que usam o serviço.</span><span class="sxs-lookup"><span data-stu-id="e5d80-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="e5d80-126">Um ataque de coleta de diretório.</span><span class="sxs-lookup"><span data-stu-id="e5d80-126">A directory harvest attack.</span></span>
- <span data-ttu-id="e5d80-127">Um ataque de spam.</span><span class="sxs-lookup"><span data-stu-id="e5d80-127">A spam attack.</span></span>
- <span data-ttu-id="e5d80-128">Um servidor de email desonesto.</span><span class="sxs-lookup"><span data-stu-id="e5d80-128">A rogue email server.</span></span>

<span data-ttu-id="e5d80-129">Todos esses problemas podem resultar em um aumento repentino no número de NDRs sendo processados pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="e5d80-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="e5d80-130">Muitas vezes, essas NDRs parecem ser spam para outros servidores de email e serviços (também conhecidos como _[backscatter](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="e5d80-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
