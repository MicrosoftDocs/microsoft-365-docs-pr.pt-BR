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
ms.openlocfilehash: 5480916f55fc180a6f08d3c420cb92c730e4065b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167534"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="031fc-103">Pools de entrega de saída</span><span class="sxs-lookup"><span data-stu-id="031fc-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="031fc-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="031fc-104">**Applies to**</span></span>
- [<span data-ttu-id="031fc-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="031fc-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="031fc-106">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="031fc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="031fc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="031fc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="031fc-108">Os servidores de email nos datacenters do Microsoft 365 podem ficar temporariamente sem enviar spam.</span><span class="sxs-lookup"><span data-stu-id="031fc-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="031fc-109">Por exemplo, um ataque de malware ou spam mal-intencionado em uma organização de email local que envia emails de saída por meio do Microsoft 365 ou contas comprometidas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="031fc-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="031fc-110">Os invasores também tentam evitar a detecção retransmitindo mensagens por meio do encaminhamento do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="031fc-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="031fc-111">Esses cenários podem fazer com que o endereço IP dos servidores de datacenter afetados do Microsoft 365 apareça em listas de bloqueio de terceiros.</span><span class="sxs-lookup"><span data-stu-id="031fc-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="031fc-112">As organizações de email de destino que usam essas listas de bloqueio rejeitarão emails dessas fontes de mensagens.</span><span class="sxs-lookup"><span data-stu-id="031fc-112">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="031fc-113">Pool de entrega de alto risco</span><span class="sxs-lookup"><span data-stu-id="031fc-113">High-risk delivery pool</span></span>
<span data-ttu-id="031fc-114">Para evitar isso, todas as mensagens de saída dos servidores de datacenter do Microsoft 365 que são determinadas como spam ou que excedem os limites de envio do serviço ou das políticas de [spam](configure-the-outbound-spam-policy.md) de saída são enviadas através do _pool_ de entrega de alto risco. [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="031fc-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="031fc-115">O pool de entrega de alto risco é um pool de endereços IP separado para emails de saída que é usado apenas para enviar mensagens de "baixa qualidade" (por exemplo, spam e [backscatter](backscatter-messages-and-eop.md)).</span><span class="sxs-lookup"><span data-stu-id="031fc-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="031fc-116">Usar o pool de entrega de alto risco ajuda a impedir que o pool de endereços IP normal para emails de saída envie spam.</span><span class="sxs-lookup"><span data-stu-id="031fc-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="031fc-117">O pool de endereços IP normal para emails de saída mantém a reputação enviando mensagens de "alta qualidade", o que reduz a probabilidade de que esses endereços IP apareçam nas listas de bloqueio de IP.</span><span class="sxs-lookup"><span data-stu-id="031fc-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="031fc-118">A possibilidade muito real de que os endereços IP no pool de entrega de alto risco sejam colocados em listas de bloqueio de IP permanece, mas isso é feito por design.</span><span class="sxs-lookup"><span data-stu-id="031fc-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="031fc-119">A entrega aos destinatários pretendido não é garantida, porque muitas organizações de email não aceitam mensagens do pool de entrega de alto risco.</span><span class="sxs-lookup"><span data-stu-id="031fc-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="031fc-120">Para obter mais informações, consulte [Controle de spam de saída.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="031fc-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="031fc-121">As mensagens em que o domínio de email de origem não tem nenhum registro A e nenhum registro MX definido no DNS público são sempre roteadas através do pool de entrega de alto risco, independentemente de seu spam ou disposição do limite de envio.</span><span class="sxs-lookup"><span data-stu-id="031fc-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="031fc-122">Mensagens de salto</span><span class="sxs-lookup"><span data-stu-id="031fc-122">Bounce messages</span></span>

<span data-ttu-id="031fc-123">O pool de entrega de alto risco de saída gerencia a entrega de todos os relatórios de não entrega (também conhecidos como NDRs, mensagens de rejeição, notificações de status de entrega ou DSNs).</span><span class="sxs-lookup"><span data-stu-id="031fc-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="031fc-124">As possíveis causas para um aumento nas NDRs incluem:</span><span class="sxs-lookup"><span data-stu-id="031fc-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="031fc-125">Uma campanha de spoofing que afeta um dos clientes que usam o serviço.</span><span class="sxs-lookup"><span data-stu-id="031fc-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="031fc-126">Um ataque de colheita de diretório.</span><span class="sxs-lookup"><span data-stu-id="031fc-126">A directory harvest attack.</span></span>
- <span data-ttu-id="031fc-127">Um ataque de spam.</span><span class="sxs-lookup"><span data-stu-id="031fc-127">A spam attack.</span></span>
- <span data-ttu-id="031fc-128">Um servidor de email não..</span><span class="sxs-lookup"><span data-stu-id="031fc-128">A rogue email server.</span></span>

<span data-ttu-id="031fc-129">Todos esses problemas podem resultar em um aumento súbito no número de NDRs sendo processadas pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="031fc-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="031fc-130">Muitas vezes, essas NDRs parecem ser spam para outros servidores e serviços de email (também conhecidos como _[backscatter).](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="031fc-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="031fc-131">Pool de retransmissão</span><span class="sxs-lookup"><span data-stu-id="031fc-131">Relay pool</span></span>

<span data-ttu-id="031fc-132">As mensagens que são encaminhadas ou retransmitida do Microsoft 365 são enviadas usando um pool de retransmissão especial, pois o destino final não deve considerar o Microsoft 365 como o remetente real.</span><span class="sxs-lookup"><span data-stu-id="031fc-132">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="031fc-133">Também é importante isolar esse tráfego, pois existem cenários legítimos e inválidos para o envio automático ou a retransmissão de emails do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="031fc-133">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="031fc-134">Semelhante ao pool de entrega de alto risco, um pool de endereços IP separado é usado para emails repassados.</span><span class="sxs-lookup"><span data-stu-id="031fc-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="031fc-135">Esse pool de endereços não é publicado, pois pode mudar com frequência.</span><span class="sxs-lookup"><span data-stu-id="031fc-135">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="031fc-136">O Microsoft 365 precisa verificar se o remetente original é legítimo para que possamos entregar a mensagem encaminhada com confiança.</span><span class="sxs-lookup"><span data-stu-id="031fc-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="031fc-137">Para fazer isso, a autenticação de email (SPF, DKIM e DMARC) precisa passar quando a mensagem chegar até nós.</span><span class="sxs-lookup"><span data-stu-id="031fc-137">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="031fc-138">Nos casos em que podemos autenticar o remetente, usamos a Reescrita de Remetente para ajudar o receptor a saber que a mensagem encaminhada é de uma fonte confiável.</span><span class="sxs-lookup"><span data-stu-id="031fc-138">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="031fc-139">Você pode ler mais sobre como isso funciona e o que pode fazer para ajudar a garantir que o domínio de envio passe na autenticação no [SRS (Esquema de Reescrita](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)de Remetente).</span><span class="sxs-lookup"><span data-stu-id="031fc-139">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
