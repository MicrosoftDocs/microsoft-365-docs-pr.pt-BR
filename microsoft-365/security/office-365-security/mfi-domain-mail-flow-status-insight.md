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
description: Os administradores podem aprender a usar a visão superior do status do fluxo de emails do domínio no painel de fluxo de emails no centro de conformidade de & de segurança para solucionar problemas de fluxo de emails relacionados a registros MX em seus domínios de email.
ms.openlocfilehash: d4abc311e96df87894d5f059328f1a16a00190b8
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877498"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="32812-103">Visão geral do status do fluxo de email de domínio superior no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="32812-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="32812-104">A **parte superior do status do fluxo de emails do domínio** no [painel de fluxo de emails](mail-flow-insights-v2.md) do centro de [conformidade & segurança](https://protection.office.com) oferece o status atual dos domínios da sua organização em termos de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="32812-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="32812-105">Essa percepção ajuda a identificar e solucionar problemas de domínios que estão experimentando o *_fluxo de emails com impacto_* de problemas (por exemplo, não é possível receber emails externos), especialmente expirações de domínios ou domínios com registros MX incorretos.</span><span class="sxs-lookup"><span data-stu-id="32812-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow impacting_* _ issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Widget status de fluxo de domínio superior no painel de fluxo de emails no centro de conformidade & segurança](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="32812-107">Quando você clica em _ *Exibir detalhes* \* no widget, um submenu de **status de domínio** aparece mostrando mais detalhes para o status de cada domínio:</span><span class="sxs-lookup"><span data-stu-id="32812-107">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="32812-108">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="32812-108">**Domain**</span></span>
- <span data-ttu-id="32812-109">**Registro MX anterior**</span><span class="sxs-lookup"><span data-stu-id="32812-109">**Previous MX record**</span></span>
- <span data-ttu-id="32812-110">**Registro MX atual**</span><span class="sxs-lookup"><span data-stu-id="32812-110">**Current MX record**</span></span>
- <span data-ttu-id="32812-111">**Status de recebimento de email**</span><span class="sxs-lookup"><span data-stu-id="32812-111">**Email receiving status**</span></span>
- <span data-ttu-id="32812-112">**Status do domínio** : uma marca de seleção verde indica o registro MX atual (no momento em que você clicou no widget) corresponde ao valor que temos no registro e que o domínio recebeu emails nas últimas duas horas.</span><span class="sxs-lookup"><span data-stu-id="32812-112">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="32812-113">Um X vermelho indica que o registro MX foi alterado e que o domínio não recebeu nenhum email durante as últimas 6 horas.</span><span class="sxs-lookup"><span data-stu-id="32812-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="32812-114">Isso provavelmente indica que o domínio expirou ou que o registro MX foi atualizado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="32812-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="32812-115">Verifique com o seu registrador de domínio ou serviço de hospedagem DNS para ver se o domínio expirou ou se o registro MX do domínio está incorreto.</span><span class="sxs-lookup"><span data-stu-id="32812-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="32812-116">Você pode clicar em **Exibir mais** para ver as mesmas informações para mais domínios.</span><span class="sxs-lookup"><span data-stu-id="32812-116">You can click **View more** to see the same information for more domains.</span></span>

![Submenu de detalhes da visão superior do status do fluxo de emails do domínio](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="32812-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="32812-118">Related topics</span></span>

<span data-ttu-id="32812-119">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="32812-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
