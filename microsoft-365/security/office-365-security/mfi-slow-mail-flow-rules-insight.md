---
title: Visão geral sobre regras de correção de fluxo reduzido de email
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o insight Corrigir regras de fluxo de emails lentos no Centro de Conformidade & Segurança para identificar e corrigir regras de fluxo de emails ineficientes ou quebrados (também conhecidas como regras de transporte) em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 51ffa92402fd3e7c9e76115642426d3cce0a9e19
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202976"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="b609e-103">Correção do insight das regras de fluxo de emails lentos no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="b609e-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b609e-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="b609e-104">**Applies to**</span></span>
- [<span data-ttu-id="b609e-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b609e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b609e-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b609e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b609e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b609e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b609e-108">Regras ineficientes de fluxo de emails (também conhecidas como regras de transporte) podem levar a atrasos de fluxo de emails para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b609e-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="b609e-109">Esse insight relata regras de fluxo de emails que têm um impacto no fluxo de emails da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b609e-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="b609e-110">Exemplos desses tipos de regras incluem:</span><span class="sxs-lookup"><span data-stu-id="b609e-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="b609e-111">Condições que usam **é membro de** grupos grandes.</span><span class="sxs-lookup"><span data-stu-id="b609e-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="b609e-112">Condições que usam correspondência de padrão de expressão regular complexa (regex).</span><span class="sxs-lookup"><span data-stu-id="b609e-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="b609e-113">Condições que usam a verificação de conteúdo em anexos.</span><span class="sxs-lookup"><span data-stu-id="b609e-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="b609e-114">O insight Corrigir & **regras** de fluxo de [](mail-flow-insights-v2.md) emails lentos na área Recomendada para você do painel de fluxo de email no Centro de Conformidade e Segurança notifica quando [uma](https://protection.office.com) regra de fluxo de emails está demorando muito para ser concluída. </span><span class="sxs-lookup"><span data-stu-id="b609e-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="b609e-115">Esse insight aparece somente depois que a condição é detectada (se você não tiver nenhum loop de email, você não verá o insight).</span><span class="sxs-lookup"><span data-stu-id="b609e-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="b609e-116">Você pode usar essa notificação para ajudá-lo a identificar e ajustar as regras de fluxo de emails para ajudar a reduzir os atrasos no fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="b609e-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Correção do insight das regras de fluxo de emails lentos na área Recomendada para você do painel de fluxo de emails](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="b609e-118">Quando você clica **em Exibir detalhes** no widget, um sobremenu aparece com mais informações:</span><span class="sxs-lookup"><span data-stu-id="b609e-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="b609e-119">**Regra:** você pode passar o mouse sobre o resumo para ver todas as condições, exceções e ações da regra.</span><span class="sxs-lookup"><span data-stu-id="b609e-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="b609e-120">Você pode clicar no resumo para editar a regra no centro de administração Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="b609e-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="b609e-121">**Número de mensagens avaliadas:** você pode [](message-trace-scc.md) clicar em Exibir mensagens **de** exemplo para ver os resultados do rastreamento de mensagens para um exemplo das mensagens que foram afetadas pela regra.</span><span class="sxs-lookup"><span data-stu-id="b609e-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="b609e-122">**Tempo médio gasto em cada mensagem**</span><span class="sxs-lookup"><span data-stu-id="b609e-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="b609e-123">**Tempo médio gasto em uma mensagem**: o valor intermediário que separa a metade superior dos dados de metade inferior do tempo.</span><span class="sxs-lookup"><span data-stu-id="b609e-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Detalhes do sobrevoo que aparecem depois de clicar em Exibir detalhes no insight Corrigir regras de fluxo de emails lentos](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="b609e-125">Para obter mais informações sobre condições e exceções em regras de fluxo de emails, consulte Condições de regra de fluxo de email e exceções [(predicados) em Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="b609e-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="b609e-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="b609e-126">See also</span></span>

<span data-ttu-id="b609e-127">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="b609e-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>