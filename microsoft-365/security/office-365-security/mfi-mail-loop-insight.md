---
title: Visão geral sobre correção de possíveis loop de email
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o insight correção de loop de email possível no painel de fluxo de email no Centro de Conformidade e Segurança & para identificar e corrigir loops de email em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203287"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="64d8d-103">Corrigir informações de loop de email possíveis no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="64d8d-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="64d8d-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="64d8d-104">**Applies to**</span></span>
- [<span data-ttu-id="64d8d-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="64d8d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="64d8d-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="64d8d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="64d8d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64d8d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="64d8d-108">Os loops de email são ruins porque:</span><span class="sxs-lookup"><span data-stu-id="64d8d-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="64d8d-109">Eles desperdiçam recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="64d8d-109">They waste system resources.</span></span>
- <span data-ttu-id="64d8d-110">Eles consomem a cota de volume de email da sua organização.</span><span class="sxs-lookup"><span data-stu-id="64d8d-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="64d8d-111">Eles enviam relatórios confusos de não entrega (também conhecidos como NDRs ou mensagens de rejeição) para os envios de mensagens originais.</span><span class="sxs-lookup"><span data-stu-id="64d8d-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="64d8d-112">A **visão de** loop  de email correção [](mail-flow-insights-v2.md) possível na [](https://protection.office.com) área Recomendada para você do painel de fluxo de email no Centro de Conformidade e Segurança & notifica quando um loop de email é detectado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="64d8d-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="64d8d-113">Esse insight aparece somente depois que a condição é detectada (se você não tiver nenhum loop de email, você não verá o insight).</span><span class="sxs-lookup"><span data-stu-id="64d8d-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Correção do insight das regras de fluxo de emails lentos na área Recomendada para você do painel de fluxo de emails](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="64d8d-115">Quando você clica **em Exibir detalhes** no widget, um sobremenu aparece com mais informações:</span><span class="sxs-lookup"><span data-stu-id="64d8d-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="64d8d-116">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="64d8d-116">**Domain**</span></span>
- <span data-ttu-id="64d8d-117">**Número de mensagens**: você pode clicar [](message-trace-scc.md) em Exibir **mensagens de** exemplo para ver os resultados do rastreamento de mensagens para um exemplo das mensagens que foram afetadas pelo loop.</span><span class="sxs-lookup"><span data-stu-id="64d8d-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="64d8d-118">**Tipo de** domínio " Por exemplo, autoritativo ou não autoritativo.</span><span class="sxs-lookup"><span data-stu-id="64d8d-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="64d8d-119">**Registro MX**: o host (**servidor de email**) e valores **priority** do registro MX para o domínio.</span><span class="sxs-lookup"><span data-stu-id="64d8d-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="64d8d-120">**Motivo do** loop **e Como corrigir:** identificaremos os cenários de loop de email mais comuns e forneceremos ações recomendadas para corrigir o loop.</span><span class="sxs-lookup"><span data-stu-id="64d8d-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Detalhes sobre o sobrevoo que aparecem depois de clicar em Exibir detalhes no insight de loop de email correção possível](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="64d8d-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="64d8d-122">See also</span></span>

<span data-ttu-id="64d8d-123">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="64d8d-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
