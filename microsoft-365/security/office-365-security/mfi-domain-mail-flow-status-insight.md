---
title: Visão geral do status do fluxo de email de domínio superior no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar a visão superior do status do fluxo de emails do domínio no painel de fluxo de emails no centro de conformidade de & de segurança para solucionar problemas de fluxo de emails relacionados a registros MX em seus domínios de email.
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827010"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="6edb1-103">Visão geral do status do fluxo de email de domínio superior no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="6edb1-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="6edb1-104">A **parte superior do status do fluxo de emails do domínio** no [painel de fluxo de emails](mail-flow-insights-v2.md) do centro de conformidade & segurança oferece o status atual dos domínios da sua organização em termos de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="6edb1-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="6edb1-105">Essa percepção ajuda a identificar e solucionar problemas de domínios que estão enfrentando problemas de ***impacto de fluxo de emails*** (por exemplo, não é possível receber emails externos), especialmente expirações de domínio ou domínios com registros MX incorretos.</span><span class="sxs-lookup"><span data-stu-id="6edb1-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Widget status de fluxo de domínio superior no painel de fluxo de emails no centro de conformidade & segurança](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="6edb1-107">Quando você clica em **Exibir detalhes** no widget, um submenu de **status de domínio** aparece mostrando mais detalhes para o status de cada domínio:</span><span class="sxs-lookup"><span data-stu-id="6edb1-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="6edb1-108">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="6edb1-108">**Domain**</span></span>
- <span data-ttu-id="6edb1-109">**Registro MX anterior**</span><span class="sxs-lookup"><span data-stu-id="6edb1-109">**Previous MX record**</span></span>
- <span data-ttu-id="6edb1-110">**Registro MX atual**</span><span class="sxs-lookup"><span data-stu-id="6edb1-110">**Current MX record**</span></span>
- <span data-ttu-id="6edb1-111">**Status de recebimento de email**</span><span class="sxs-lookup"><span data-stu-id="6edb1-111">**Email receiving status**</span></span>
- <span data-ttu-id="6edb1-112">**Status do domínio**: uma marca de seleção verde indica o registro MX atual (no momento em que você clicou no widget) corresponde ao valor que temos no registro e que o domínio recebeu emails nas últimas duas horas.</span><span class="sxs-lookup"><span data-stu-id="6edb1-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="6edb1-113">Um X vermelho indica que o registro MX foi alterado e que o domínio não recebeu nenhum email durante as últimas 6 horas.</span><span class="sxs-lookup"><span data-stu-id="6edb1-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="6edb1-114">Isso provavelmente indica que o domínio expirou ou que o registro MX foi atualizado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="6edb1-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="6edb1-115">Verifique com o seu registrador de domínio ou serviço de hospedagem DNS para ver se o domínio expirou ou se o registro MX do domínio está incorreto.</span><span class="sxs-lookup"><span data-stu-id="6edb1-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="6edb1-116">Você pode clicar em **Exibir mais** para ver as mesmas informações para mais domínios.</span><span class="sxs-lookup"><span data-stu-id="6edb1-116">You can click **View more** to see the same information for more domains.</span></span>

![Submenu de detalhes da visão superior do status do fluxo de emails do domínio](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="6edb1-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6edb1-118">Related topics</span></span>

<span data-ttu-id="6edb1-119">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="6edb1-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
