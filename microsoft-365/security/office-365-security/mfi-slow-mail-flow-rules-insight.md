---
title: Visão geral sobre regras de correção de fluxo reduzido de email
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender como usar a correção de regras de fluxo de emails lentos no centro de conformidade de & de segurança para identificar e corrigir regras de fluxo de emails ineficientes ou desfeitas (também conhecidas como regras de transporte) em sua organização.
ms.openlocfilehash: 6a2a3c42eadf3c621b34d2a21344eafd2618e669
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877532"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="8e1e5-103">Correção de regras de fluxo de email lentos no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="8e1e5-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8e1e5-104">Regras de fluxo de emails ineficientes (também conhecidas como regras de transporte) podem levar a atrasos de fluxo de emails para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="8e1e5-105">Esta percepção relata regras de fluxo de emails que afetam o fluxo de email da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="8e1e5-106">Exemplos desses tipos de regras incluem:</span><span class="sxs-lookup"><span data-stu-id="8e1e5-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="8e1e5-107">Condições que o uso **é membro de** grupos grandes.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="8e1e5-108">Condições que usam a correspondência de padrão de expressão regular (Regex) complexa.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="8e1e5-109">Condições que usam a verificação de conteúdo em anexos.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="8e1e5-110">A **correção de regras de fluxo de emails lentos** na área **recomendada para você** do [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de segurança & conformidade](https://protection.office.com) avisa quando uma regra de fluxo de emails demora muito para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="8e1e5-111">Essa percepção aparece apenas após a condição ser detectada (se você não tiver loops de email, não verá a percepção).</span><span class="sxs-lookup"><span data-stu-id="8e1e5-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="8e1e5-112">Você pode usar essa notificação para ajudá-lo a identificar e ajustar as regras de fluxo de emails para ajudar a reduzir os atrasos de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Corrigir recomendações de regras de fluxo de email lentos na área recomendada para você do painel de fluxo de emails](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="8e1e5-114">Quando você clica em **Exibir detalhes** no widget, um submenu aparece com mais informações:</span><span class="sxs-lookup"><span data-stu-id="8e1e5-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="8e1e5-115">**Regra** : você pode passar o mouse sobre o resumo para ver todas as condições, exceções e ações da regra.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-115">**Rule** : You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="8e1e5-116">Você pode clicar no resumo para editar a regra no centro de administração do Exchange (Eat).</span><span class="sxs-lookup"><span data-stu-id="8e1e5-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="8e1e5-117">**Número de mensagens avaliadas** : você pode clicar em **Exibir exemplos de mensagens** para ver os resultados do [rastreamento](message-trace-scc.md) de mensagens para um exemplo das mensagens que foram afetadas pela regra.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-117">**Number of messages evaluated** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="8e1e5-118">**Tempo médio gasto em cada mensagem**</span><span class="sxs-lookup"><span data-stu-id="8e1e5-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="8e1e5-119">**Tempo médio gasto em uma mensagem** : o valor intermediário que separa a metade superior da metade inferior dos dados de tempo.</span><span class="sxs-lookup"><span data-stu-id="8e1e5-119">**Median time spent on a message** : The middle value that separates the upper half from the lower half of time data.</span></span>

![Submenu de detalhes que aparece depois de clicar em Exibir detalhes na visão de regras de fluxo de emails de correção lenta](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="8e1e5-121">Para obter mais informações sobre condições e exceções nas regras de fluxo de email no Exchange Online, consulte [Mail Flow Rules and exceptions (predicates) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="8e1e5-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e1e5-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8e1e5-122">Related topics</span></span>

<span data-ttu-id="8e1e5-123">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="8e1e5-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
