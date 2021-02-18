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
description: Os administradores podem aprender a usar o insight de regras de correção de fluxo lento de emails no Centro de Conformidade e Segurança & para identificar e corrigir regras de fluxo de emails ineficientes ou desaprinciados (também conhecidas como regras de transporte) em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a50fa0d36cb025f5d0627a2212254b9d08dc5d9c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290688"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="e24a0-103">Visão das regras de fluxo de emails lentas no Centro de Conformidade e & Segurança</span><span class="sxs-lookup"><span data-stu-id="e24a0-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e24a0-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e24a0-104">**Applies to**</span></span>
- [<span data-ttu-id="e24a0-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e24a0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e24a0-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e24a0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e24a0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e24a0-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e24a0-108">Regras de fluxo de emails ineficientes (também conhecidas como regras de transporte) podem levar a atrasos de fluxo de emails para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e24a0-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="e24a0-109">Esse insight relata regras de fluxo de emails que têm um impacto no fluxo de emails da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e24a0-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="e24a0-110">Exemplos desses tipos de regras incluem:</span><span class="sxs-lookup"><span data-stu-id="e24a0-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="e24a0-111">Condições que usam **é membro de grupos** grandes.</span><span class="sxs-lookup"><span data-stu-id="e24a0-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="e24a0-112">Condições que usam correspondência de padrão de expressão regular complexa (regex).</span><span class="sxs-lookup"><span data-stu-id="e24a0-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="e24a0-113">Condições que usam a verificação de conteúdo em anexos.</span><span class="sxs-lookup"><span data-stu-id="e24a0-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="e24a0-114">The **Fix slow mail flow rules** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & [Compliance Center](https://protection.office.com) notifes you when a mail flow rule is taking too long to complete.</span><span class="sxs-lookup"><span data-stu-id="e24a0-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="e24a0-115">Esse insight só aparece depois que a condição é detectada (se você não tiver loops de email, você não verá o insight).</span><span class="sxs-lookup"><span data-stu-id="e24a0-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="e24a0-116">Você pode usar essa notificação para ajudá-lo a identificar e ajustar as regras de fluxo de emails para ajudar a reduzir os atrasos de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="e24a0-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Fix slow mail flow rules insight in the Recommended for you area of the Mail flow dashboard](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="e24a0-118">Quando você clica **em Exibir detalhes** no widget, um flyout é exibido com mais informações:</span><span class="sxs-lookup"><span data-stu-id="e24a0-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="e24a0-119">**Regra:** você pode passar o mouse sobre o resumo para ver todas as condições, exceções e ações da regra.</span><span class="sxs-lookup"><span data-stu-id="e24a0-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="e24a0-120">Você pode clicar no resumo para editar a regra no Centro de administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="e24a0-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="e24a0-121">**Número de mensagens avaliadas:** você pode [](message-trace-scc.md) clicar em Exibir mensagens **de** exemplo para ver os resultados do rastreamento de mensagens para um exemplo das mensagens que foram afetadas pela regra.</span><span class="sxs-lookup"><span data-stu-id="e24a0-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="e24a0-122">**Tempo médio gasto em cada mensagem**</span><span class="sxs-lookup"><span data-stu-id="e24a0-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="e24a0-123">**Tempo médio gasto em uma mensagem:** o valor intermediário que separa a metade superior dos dados da metade inferior do tempo.</span><span class="sxs-lookup"><span data-stu-id="e24a0-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Detalhes do flyout que aparece depois de clicar em Exibir detalhes no insight de regras de fluxo de emails lentos de Correção](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="e24a0-125">Para obter mais informações sobre condições e exceções em regras de fluxo de emails, consulte Condições e exceções de regras de fluxo de email [(predicados) no Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="e24a0-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="e24a0-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="e24a0-126">See also</span></span>

<span data-ttu-id="e24a0-127">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="e24a0-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
