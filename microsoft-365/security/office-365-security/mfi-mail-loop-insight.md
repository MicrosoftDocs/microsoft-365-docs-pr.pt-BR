---
title: Visão geral sobre correção de possíveis loop de email
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar a correção de possíveis loops de email no painel de fluxo de emails no centro de conformidade de & de segurança para identificar e corrigir loops de email em sua organização.
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920555"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="5ff7b-103">Correção de possíveis informações de loop de email no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="5ff7b-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5ff7b-104">Os loops de email são ruins porque:</span><span class="sxs-lookup"><span data-stu-id="5ff7b-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="5ff7b-105">Eles desperdiçam recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="5ff7b-105">They waste system resources.</span></span>
- <span data-ttu-id="5ff7b-106">Eles consomem a cota de volume de email da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5ff7b-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="5ff7b-107">Eles enviam notificações confusas de não entrega (também conhecidas como NDRs ou mensagens de devolução) para os remetentes de mensagens originais.</span><span class="sxs-lookup"><span data-stu-id="5ff7b-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="5ff7b-108">A **correção de possíveis loops de email** na área **recomendada para você** do [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de segurança & conformidade](https://protection.office.com) avisa quando um loop de email é detectado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5ff7b-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="5ff7b-109">Essa percepção aparece apenas após a condição ser detectada (se você não tiver loops de email, não verá a percepção).</span><span class="sxs-lookup"><span data-stu-id="5ff7b-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Corrigir recomendações de regras de fluxo de email lentos na área recomendada para você do painel de fluxo de emails](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="5ff7b-111">Quando você clica em **Exibir detalhes** no widget, um submenu aparece com mais informações:</span><span class="sxs-lookup"><span data-stu-id="5ff7b-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="5ff7b-112">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ff7b-112">**Domain**</span></span>
- <span data-ttu-id="5ff7b-113">**Número de mensagens** : você pode clicar em **Exibir exemplos de mensagens** para ver os resultados do [rastreamento](message-trace-scc.md) de mensagens para um exemplo das mensagens que foram afetadas pelo loop.</span><span class="sxs-lookup"><span data-stu-id="5ff7b-113">**Number of messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="5ff7b-114">**Tipo de domínio** "por exemplo, autoritativo ou não autoritativo.</span><span class="sxs-lookup"><span data-stu-id="5ff7b-114">**Domain type** " For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="5ff7b-115">**Registro MX** : o host ( **servidor de email** ) e os valores de **prioridade** do registro MX do domínio.</span><span class="sxs-lookup"><span data-stu-id="5ff7b-115">**MX record** : The host ( **Mail server** ) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="5ff7b-116">**Motivo do loop** e **como corrigir** : identificaremos os cenários de loop de email mais comuns e fornecerão as ações recomendadas para corrigir o loop.</span><span class="sxs-lookup"><span data-stu-id="5ff7b-116">**Loop reason** and **How to fix** : We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Submenu de detalhes que aparece depois de clicar em Exibir detalhes na correção de possíveis loops de emails](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="5ff7b-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="5ff7b-118">See also</span></span>

<span data-ttu-id="5ff7b-119">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="5ff7b-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
