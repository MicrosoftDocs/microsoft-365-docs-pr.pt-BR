---
title: Visão de status de fluxo de email de domínio superior no painel fluxo de emails
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
description: Os administrador & es podem aprender a usar a visão de status de fluxo de email de domínio superior no painel de fluxo de emails no Centro de Conformidade e segurança para solucionar problemas de fluxo de emails relacionados aos registros MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203412"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="94901-103">Principais informações sobre o status do fluxo de emails de domínio no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="94901-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="94901-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="94901-104">**Applies to**</span></span>
- [<span data-ttu-id="94901-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="94901-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="94901-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="94901-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="94901-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94901-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="94901-108">A **visão de status** de [](mail-flow-insights-v2.md) fluxo de [&](https://protection.office.com) email de domínio superior no painel fluxo de email no Centro de Conformidade e Segurança fornece o status atual de fluxo de emails para sua organização.</span><span class="sxs-lookup"><span data-stu-id="94901-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="94901-109">Esse insight ajuda você a identificar e solucionar problemas de domínios que estão enfrentando problemas ***de fluxo de*** emails.</span><span class="sxs-lookup"><span data-stu-id="94901-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="94901-110">Por exemplo, o domínio não pode receber emails externos porque o domínio expirou ou o domínio tem um registro MX incorreto.</span><span class="sxs-lookup"><span data-stu-id="94901-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget de status de fluxo de domínio superior no painel fluxo de email no Centro de Conformidade & Segurança](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="94901-112">Quando você clica **em Exibir detalhes** no widget, um **flyout de status** de domínio é exibido que mostra mais detalhes sobre o status de cada domínio:</span><span class="sxs-lookup"><span data-stu-id="94901-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="94901-113">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="94901-113">**Domain**</span></span>
- <span data-ttu-id="94901-114">**Registro MX anterior**</span><span class="sxs-lookup"><span data-stu-id="94901-114">**Previous MX record**</span></span>
- <span data-ttu-id="94901-115">**Registro MX atual**</span><span class="sxs-lookup"><span data-stu-id="94901-115">**Current MX record**</span></span>
- <span data-ttu-id="94901-116">**Status de recebimento de email**</span><span class="sxs-lookup"><span data-stu-id="94901-116">**Email receiving status**</span></span>
- <span data-ttu-id="94901-117">**Status do** domínio : uma marca de verificação verde indica que o registro MX atual (no momento em que você clicou no widget) corresponde ao valor que temos no registro e o domínio recebeu emails durante as últimas duas horas.</span><span class="sxs-lookup"><span data-stu-id="94901-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="94901-118">Um X vermelho indica que o registro MX foi alterado e o domínio não recebeu nenhum email durante as últimas 6 horas.</span><span class="sxs-lookup"><span data-stu-id="94901-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="94901-119">Isso provavelmente indica que seu domínio expirou ou que o registro MX foi atualizado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="94901-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="94901-120">Verifique com seu registrador de domínio ou serviço de hospedagem DNS para ver se o domínio expirou ou se o registro MX do domínio está incorreto.</span><span class="sxs-lookup"><span data-stu-id="94901-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="94901-121">Você pode clicar **em Exibir mais** para ver as mesmas informações para mais domínios.</span><span class="sxs-lookup"><span data-stu-id="94901-121">You can click **View more** to see the same information for more domains.</span></span>

![Detalhes do flyout na visão de status de fluxo de email de domínio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="94901-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="94901-123">See also</span></span>

<span data-ttu-id="94901-124">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="94901-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
