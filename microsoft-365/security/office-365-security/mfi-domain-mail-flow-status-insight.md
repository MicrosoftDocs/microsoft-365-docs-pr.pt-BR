---
title: Visão geral do status do fluxo de emails do domínio no painel Fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o insight de & status de fluxo de emails de domínio superior no painel Fluxo de emails no Centro de Conformidade e Segurança para solucionar problemas de fluxo de emails relacionados a seus registros MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 457675e7f32cd513f5593ede53a64aaef9d54904
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029901"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="d9825-103">Principais informações sobre o status do fluxo de emails do domínio no Centro de Conformidade e & Segurança</span><span class="sxs-lookup"><span data-stu-id="d9825-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d9825-104">Os principais insights de status [](mail-flow-insights-v2.md) **do** fluxo de emails do domínio no painel Fluxo de emails [no](https://protection.office.com) Centro de Conformidade e Segurança & o status atual do fluxo de emails da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d9825-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="d9825-105">Esse insight ajuda a identificar e solucionar problemas de domínios que estão enfrentando \**_problemas de fluxo de_* emails.</span><span class="sxs-lookup"><span data-stu-id="d9825-105">This insight helps you identify and troubleshoot domains that are experiencing \**_mail flow_* _ issues.</span></span> <span data-ttu-id="d9825-106">Por exemplo, o domínio não pode receber emails externos porque o domínio expirou ou o domínio tem um registro MX incorreto.</span><span class="sxs-lookup"><span data-stu-id="d9825-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Principal widget de status de fluxo de domínio no painel Fluxo de emails no Centro de Conformidade e Segurança & Segurança](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="d9825-108">Quando você clica em _ *Exibir detalhes*\* no widget, um **flyout de status** do domínio é exibido, que mostra mais detalhes sobre o status de cada domínio:</span><span class="sxs-lookup"><span data-stu-id="d9825-108">When you click _ *View details*\* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="d9825-109">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="d9825-109">**Domain**</span></span>
- <span data-ttu-id="d9825-110">**Registro MX anterior**</span><span class="sxs-lookup"><span data-stu-id="d9825-110">**Previous MX record**</span></span>
- <span data-ttu-id="d9825-111">**Registro MX atual**</span><span class="sxs-lookup"><span data-stu-id="d9825-111">**Current MX record**</span></span>
- <span data-ttu-id="d9825-112">**Status de recebimento de email**</span><span class="sxs-lookup"><span data-stu-id="d9825-112">**Email receiving status**</span></span>
- <span data-ttu-id="d9825-113">**Status** do domínio: uma marca de seleção verde indica que o registro MX atual (no momento em que você clicou no widget) corresponde ao valor que temos no registro, e o domínio recebeu emails durante as últimas duas horas.</span><span class="sxs-lookup"><span data-stu-id="d9825-113">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="d9825-114">Um X vermelho indica que o registro MX foi alterado e que o domínio não recebeu emails durante as últimas seis horas.</span><span class="sxs-lookup"><span data-stu-id="d9825-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="d9825-115">Isso provavelmente indica que seu domínio expirou ou que o registro MX foi atualizado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="d9825-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="d9825-116">Verifique com seu registrador de domínio ou serviço de hospedagem DNS para ver se o domínio expirou ou se o registro MX do domínio está incorreto.</span><span class="sxs-lookup"><span data-stu-id="d9825-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="d9825-117">Você pode clicar **em Exibir mais** para ver as mesmas informações para mais domínios.</span><span class="sxs-lookup"><span data-stu-id="d9825-117">You can click **View more** to see the same information for more domains.</span></span>

![Detalhes do flyout no insight de status de fluxo de emails do domínio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="d9825-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="d9825-119">See also</span></span>

<span data-ttu-id="d9825-120">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="d9825-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
