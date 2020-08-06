---
title: Correção de possíveis informações de loop de email
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar a correção de possíveis loops de email no painel de fluxo de emails no centro de conformidade de & de segurança para identificar e corrigir loops de email em sua organização.
ms.openlocfilehash: 54240cffc534b4be708492b37b827636edab280e
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577613"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="b2249-103">Correção de possíveis informações de loop de email no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="b2249-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="b2249-104">Um loop de email é ruim porque ele desperdiça recursos do sistema, consome a cota de volume de emails da sua organização e envia notificações confusas de falha na entrega (também conhecidas como NDRs ou mensagens de devolução) para os remetentes originais.</span><span class="sxs-lookup"><span data-stu-id="b2249-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="b2249-105">A **correção de possíveis loops de email** na área **recomendada para você** do [painel de fluxo de emails](mail-flow-insights-v2.md) no centro de segurança & conformidade avisa quando um loop de email é detectado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b2249-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="b2249-106">Essa percepção aparece apenas após a condição ser detectada (se você não tiver loops de email, não verá a percepção).</span><span class="sxs-lookup"><span data-stu-id="b2249-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Corrigir recomendações de regras de fluxo de email lentos na área recomendada para você do painel de fluxo de emails](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="b2249-108">Quando você clica em **Exibir detalhes** no widget, um submenu aparece com mais informações:</span><span class="sxs-lookup"><span data-stu-id="b2249-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="b2249-109">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b2249-109">**Domain**</span></span>
- <span data-ttu-id="b2249-110">**Número de mensagens**: você pode clicar em **Exibir exemplos de mensagens** para ver os resultados do [rastreamento](message-trace-scc.md) de mensagens para um exemplo das mensagens que foram afetadas pelo loop.</span><span class="sxs-lookup"><span data-stu-id="b2249-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="b2249-111">**Tipo de domínio**"por exemplo, autoritativo ou não autoritativo.</span><span class="sxs-lookup"><span data-stu-id="b2249-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="b2249-112">**Registro MX**: o host (**servidor de email**) e os valores de **prioridade** do registro MX do domínio.</span><span class="sxs-lookup"><span data-stu-id="b2249-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="b2249-113">**Motivo do loop** e **como corrigir**: tentaremos identificar os cenários de loop de email mais comuns e fornecer as ações recomendadas (se disponível) para corrigir o loop.</span><span class="sxs-lookup"><span data-stu-id="b2249-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![Submenu de detalhes que aparece depois de clicar em Exibir detalhes na correção de possíveis loops de emails](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="b2249-115">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b2249-115">Related topics</span></span>

<span data-ttu-id="b2249-116">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="b2249-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
