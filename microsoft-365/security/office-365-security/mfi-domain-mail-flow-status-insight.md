---
title: Visão geral do status do fluxo de email de domínio superior no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar a visão superior do status do fluxo de emails do domínio no painel de fluxo de emails no centro de conformidade de & de segurança para solucionar problemas de fluxo de emails relacionados a seus registros MX.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920579"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="b348c-103">Visão geral do status do fluxo de email de domínio superior no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="b348c-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b348c-104">A **parte superior do status do fluxo de emails do domínio** no [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de conformidade do & de segurança](https://protection.office.com) oferece o status atual do fluxo de emails da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b348c-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="b348c-105">Essa percepção ajuda a identificar e solucionar problemas de domínios que estão experimentando \* problemas de *_fluxo de emails_*.</span><span class="sxs-lookup"><span data-stu-id="b348c-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow_* _ issues.</span></span> <span data-ttu-id="b348c-106">Por exemplo, o domínio não pode receber emails externos porque o domínio expirou ou o domínio tem um registro MX incorreto.</span><span class="sxs-lookup"><span data-stu-id="b348c-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget status de fluxo de domínio superior no painel de fluxo de emails no centro de conformidade & segurança](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="b348c-108">Quando você clica em _ *Exibir detalhes* \* no widget, um submenu de **status de domínio** aparece mostrando mais detalhes para o status de cada domínio:</span><span class="sxs-lookup"><span data-stu-id="b348c-108">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="b348c-109">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b348c-109">**Domain**</span></span>
- <span data-ttu-id="b348c-110">**Registro MX anterior**</span><span class="sxs-lookup"><span data-stu-id="b348c-110">**Previous MX record**</span></span>
- <span data-ttu-id="b348c-111">**Registro MX atual**</span><span class="sxs-lookup"><span data-stu-id="b348c-111">**Current MX record**</span></span>
- <span data-ttu-id="b348c-112">**Status de recebimento de email**</span><span class="sxs-lookup"><span data-stu-id="b348c-112">**Email receiving status**</span></span>
- <span data-ttu-id="b348c-113">**Status do domínio** : uma marca de seleção verde indica o registro MX atual (no momento em que você clicou no widget) corresponde ao valor que temos no registro e o domínio recebeu emails nas últimas duas horas.</span><span class="sxs-lookup"><span data-stu-id="b348c-113">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="b348c-114">Um X vermelho indica que o registro MX foi alterado e o domínio não recebeu nenhum email durante as últimas 6 horas.</span><span class="sxs-lookup"><span data-stu-id="b348c-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="b348c-115">Isso provavelmente indica que o domínio expirou ou que o registro MX foi atualizado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="b348c-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="b348c-116">Verifique com o seu registrador de domínio ou serviço de hospedagem DNS para ver se o domínio expirou ou se o registro MX do domínio está incorreto.</span><span class="sxs-lookup"><span data-stu-id="b348c-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="b348c-117">Você pode clicar em **Exibir mais** para ver as mesmas informações para mais domínios.</span><span class="sxs-lookup"><span data-stu-id="b348c-117">You can click **View more** to see the same information for more domains.</span></span>

![Submenu de detalhes da visão superior do status do fluxo de emails do domínio](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="b348c-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="b348c-119">See also</span></span>

<span data-ttu-id="b348c-120">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="b348c-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
