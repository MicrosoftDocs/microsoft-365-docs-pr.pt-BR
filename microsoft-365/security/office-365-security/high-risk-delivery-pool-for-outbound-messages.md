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
description: Saiba como os pools de entrega são usados para proteger a reputação dos servidores de email nos Microsoft 365 datacenters.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137710"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="f02b1-103">Pools de entrega de saída</span><span class="sxs-lookup"><span data-stu-id="f02b1-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f02b1-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="f02b1-104">**Applies to**</span></span>
- [<span data-ttu-id="f02b1-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f02b1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f02b1-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f02b1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f02b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f02b1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f02b1-108">Os servidores de email Microsoft 365 datacenters podem ser temporariamente considerados como os que enviam spam.</span><span class="sxs-lookup"><span data-stu-id="f02b1-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="f02b1-109">Por exemplo, um ataque de malware ou spam mal-intencionado em uma organização de email local que envia emails de saída por meio de Microsoft 365 ou contas Microsoft 365 comprometidas.</span><span class="sxs-lookup"><span data-stu-id="f02b1-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="f02b1-110">Os invasores também tentam evitar a detecção retransmitindo mensagens Microsoft 365 encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="f02b1-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="f02b1-111">Esses cenários podem resultar no endereço IP dos servidores Microsoft 365 datacenter afetados que aparecem em listas de bloqueio de terceiros.</span><span class="sxs-lookup"><span data-stu-id="f02b1-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="f02b1-112">As organizações de email de destino que usam essas listas de bloqueio rejeitarão emails dessas fontes de mensagens.</span><span class="sxs-lookup"><span data-stu-id="f02b1-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="f02b1-113">Pool de entrega de alto risco</span><span class="sxs-lookup"><span data-stu-id="f02b1-113">High-risk delivery pool</span></span>
<span data-ttu-id="f02b1-114">Para evitar isso, todas as mensagens de saída de servidores de datacenter Microsoft 365 que são [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) determinadas como spam ou que excedem os limites de envio do serviço ou das políticas de [spam](configure-the-outbound-spam-policy.md) de saída são enviadas por meio do _pool_ de entrega de alto risco.</span><span class="sxs-lookup"><span data-stu-id="f02b1-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="f02b1-115">O pool de entrega de alto risco é um pool de endereços IP separado para email de saída que é usado apenas para enviar mensagens de "baixa qualidade" (por exemplo, spam e [backscatter](backscatter-messages-and-eop.md)).</span><span class="sxs-lookup"><span data-stu-id="f02b1-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="f02b1-116">O uso do pool de entrega de alto risco ajuda a impedir que o pool de endereços IP normal para email de saída envie spam.</span><span class="sxs-lookup"><span data-stu-id="f02b1-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="f02b1-117">O pool de endereços IP normal para email de saída mantém a reputação de envio de mensagens de "alta qualidade", o que reduz a probabilidade de que esses endereços IP apareçam em listas de bloqueios de IP.</span><span class="sxs-lookup"><span data-stu-id="f02b1-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="f02b1-118">A possibilidade muito real de que os endereços IP no pool de entrega de alto risco sejam colocados em listas de bloqueios de IP permanece, mas isso é por design.</span><span class="sxs-lookup"><span data-stu-id="f02b1-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="f02b1-119">A entrega aos destinatários pretendido não é garantida, pois muitas organizações de email não aceitarão mensagens do pool de entrega de alto risco.</span><span class="sxs-lookup"><span data-stu-id="f02b1-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="f02b1-120">Para obter mais informações, consulte [Control outbound spam](outbound-spam-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f02b1-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f02b1-121">As mensagens em que o domínio de email de origem não tem registro A e nenhum registro MX definido no DNS público são sempre roteadas pelo pool de entrega de alto risco, independentemente de seu spam ou disposição de limite de envio.</span><span class="sxs-lookup"><span data-stu-id="f02b1-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="f02b1-122">Mensagens de rejeição</span><span class="sxs-lookup"><span data-stu-id="f02b1-122">Bounce messages</span></span>

<span data-ttu-id="f02b1-123">O pool de entrega de alto risco de saída gerencia a entrega de todos os relatórios de não entrega (também conhecidos como NDRs, mensagens de rejeição, notificações de status de entrega ou DSNs).</span><span class="sxs-lookup"><span data-stu-id="f02b1-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="f02b1-124">As possíveis causas para uma sobrecarga em NDRs incluem:</span><span class="sxs-lookup"><span data-stu-id="f02b1-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="f02b1-125">Uma campanha de spoofing que afeta um dos clientes que usam o serviço.</span><span class="sxs-lookup"><span data-stu-id="f02b1-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="f02b1-126">Um ataque de coleta de diretório.</span><span class="sxs-lookup"><span data-stu-id="f02b1-126">A directory harvest attack.</span></span>
- <span data-ttu-id="f02b1-127">Um ataque de spam.</span><span class="sxs-lookup"><span data-stu-id="f02b1-127">A spam attack.</span></span>
- <span data-ttu-id="f02b1-128">Um servidor de email desonesto.</span><span class="sxs-lookup"><span data-stu-id="f02b1-128">A rogue email server.</span></span>

<span data-ttu-id="f02b1-129">Todos esses problemas podem resultar em um aumento repentino no número de NDRs sendo processados pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="f02b1-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="f02b1-130">Muitas vezes, essas NDRs parecem ser spam para outros servidores de email e serviços (também conhecidos como _[backscatter](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="f02b1-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>


### <a name="relay-pool"></a><span data-ttu-id="f02b1-131">Pool de retransmissão</span><span class="sxs-lookup"><span data-stu-id="f02b1-131">Relay pool</span></span>

<span data-ttu-id="f02b1-132">As mensagens encaminhadas ou retransmitida por Microsoft 365 em determinados cenários serão enviadas usando um pool de retransmissão especial, pois o destino não deve considerar Microsoft 365 como o remetente real.</span><span class="sxs-lookup"><span data-stu-id="f02b1-132">Messages that are forwarded or relayed via Microsoft 365 in certain scenarios will be sent using a special relay pool, because the destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="f02b1-133">É importante isolar esse tráfego de email, pois existem cenários legítimos e inválidos para encaminhamento automático ou retransmissão de emails fora de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f02b1-133">It's important for us to isolate this email traffic, because there are legitimate and invalid scenarios for auto forwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="f02b1-134">Semelhante ao pool de entrega de alto risco, um pool de endereços IP separado é usado para emails reenvados.</span><span class="sxs-lookup"><span data-stu-id="f02b1-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="f02b1-135">Esse pool de endereços não é publicado porque pode mudar com frequência e não faz parte do registro SPF publicado para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f02b1-135">This address pool is not published because it can change often, and it's not part of published SPF record for Microsoft 365.</span></span>

<span data-ttu-id="f02b1-136">Microsoft 365 precisa verificar se o remetente original é legítimo para que possamos entregar com confiança a mensagem encaminhada.</span><span class="sxs-lookup"><span data-stu-id="f02b1-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span>

<span data-ttu-id="f02b1-137">A mensagem encaminhada/retransmitida deve atender a um dos seguintes critérios para evitar o uso do pool de retransmissão:</span><span class="sxs-lookup"><span data-stu-id="f02b1-137">The forwarded/relayed message should meet one of the following criteria to avoid using the relay pool:</span></span>

- <span data-ttu-id="f02b1-138">O remetente de saída está em [um domínio aceito.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="f02b1-138">The outbound sender is in an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
- <span data-ttu-id="f02b1-139">SPF passa quando a mensagem é Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f02b1-139">SPF passes when the message comes to Microsoft 365.</span></span>
- <span data-ttu-id="f02b1-140">O DKIM no domínio do remetente passa quando a mensagem é Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f02b1-140">DKIM on the sender domain passes when the message comes to Microsoft 365.</span></span>
 
<span data-ttu-id="f02b1-141">Você pode dizer que uma mensagem foi enviada por meio do pool de retransmissão olhando para o IP do servidor de saída (o pool de retransmissão estará no intervalo 40.95.0.0/16) ou olhando para o nome do servidor de saída (terá "rly" no nome).</span><span class="sxs-lookup"><span data-stu-id="f02b1-141">You can tell that a message was sent via the relay pool by looking at the outbound server IP (the relay pool will be in the 40.95.0.0/16 range), or by looking at the outbound server name (will have "rly" in the name).</span></span>

<span data-ttu-id="f02b1-142">Nos casos em que podemos autenticar o remetente, usamos o Esquema de Reescrita de Remetente (SRS) para ajudar o sistema de email do destinatário a saber que a mensagem encaminhada é de uma fonte confiável.</span><span class="sxs-lookup"><span data-stu-id="f02b1-142">In cases where we can authenticate the sender, we use Sender Rewriting Scheme (SRS) to help the recipient email system know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="f02b1-143">Você pode ler mais sobre como isso funciona e o que pode fazer para ajudar a garantir que o domínio de envio passe autenticação no [SrS (Esquema](/office365/troubleshoot/antispam/sender-rewriting-scheme)de Reescrita do Remetente) em Office 365 .</span><span class="sxs-lookup"><span data-stu-id="f02b1-143">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>

<span data-ttu-id="f02b1-144">Para que o DKIM funcione, certifique-se de habilitar o DKIM para envio de domínio.</span><span class="sxs-lookup"><span data-stu-id="f02b1-144">For DKIM to work, make sure you enable DKIM for sending domain.</span></span> <span data-ttu-id="f02b1-145">Por exemplo, fabrikam.com faz parte do contoso.com e é definido nos domínios aceitos da organização.</span><span class="sxs-lookup"><span data-stu-id="f02b1-145">For example, fabrikam.com is part of contoso.com and is defined in the accepted domains of the organization.</span></span> <span data-ttu-id="f02b1-146">Se o remetente da mensagem sender@fabrikam.com, o DKIM precisará ser habilitado para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f02b1-146">If the message sender is sender@fabrikam.com, DKIM needs to be enabled for fabrikam.com.</span></span> <span data-ttu-id="f02b1-147">você pode ler sobre como habilitar em [Usar DKIM para validar emails](use-dkim-to-validate-outbound-email.md)de saída enviados do seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="f02b1-147">you can read on how to enable at [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="f02b1-148">Para adicionar domínios personalizados, siga as etapas em [Adicionar um domínio a Microsoft 365](../../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="f02b1-148">To add a custom domains follow the steps in [Add a domain to Microsoft 365](../../admin/setup/add-domain.md).</span></span>
