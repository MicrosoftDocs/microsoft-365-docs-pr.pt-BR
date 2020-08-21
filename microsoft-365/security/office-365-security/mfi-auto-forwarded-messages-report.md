---
title: Visão geral sobre mensagens encaminhadas automaticamente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Os administradores podem saber mais sobre o relatório de mensagens de encaminhamento automático no painel de fluxo de emails no centro de conformidade do & de segurança.
ms.openlocfilehash: 8d1a3ffe5ffc16a7793826b98b130121b8e68599
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827022"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="d3c8f-103">Informações de encaminhamento automático de mensagens no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="d3c8f-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="d3c8f-104">As **mensagens de encaminhamento automático** no painel de [fluxo de emails](mail-flow-insights-v2.md) no centro de conformidade de & de segurança exibem informações sobre as mensagens que são automaticamente encaminhadas da sua organização para destinatários em domínios externos.</span><span class="sxs-lookup"><span data-stu-id="d3c8f-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget mensagens automaticamente encaminhadas no centro de conformidade de & de segurança](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="d3c8f-106">Detalhes de mensagens automaticamente encaminhadas</span><span class="sxs-lookup"><span data-stu-id="d3c8f-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="d3c8f-107">Quando você clica no número de mensagens no widget, um painel de submenu aparece mostrando mais informações sobre as mensagens automaticamente encaminhadas:</span><span class="sxs-lookup"><span data-stu-id="d3c8f-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="d3c8f-108">**Encaminhar mensagens automaticamente por métodos de encaminhamento**:</span><span class="sxs-lookup"><span data-stu-id="d3c8f-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="d3c8f-109">**Por regras de fluxo de emails**</span><span class="sxs-lookup"><span data-stu-id="d3c8f-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="d3c8f-110">**Por regras de caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="d3c8f-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="d3c8f-111">**Pelo encaminhamento SMTP**</span><span class="sxs-lookup"><span data-stu-id="d3c8f-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="d3c8f-112">Um link para o [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d3c8f-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="d3c8f-113">**Encaminhar mensagens automaticamente por domínios e usuários**:</span><span class="sxs-lookup"><span data-stu-id="d3c8f-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="d3c8f-114">**Cinco principais domínios encaminhados para**</span><span class="sxs-lookup"><span data-stu-id="d3c8f-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="d3c8f-115">**Novos domínios (semana passada)**</span><span class="sxs-lookup"><span data-stu-id="d3c8f-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="d3c8f-116">**Cinco principais usuários de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="d3c8f-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="d3c8f-117">**Novos usuários (semana passada)**</span><span class="sxs-lookup"><span data-stu-id="d3c8f-117">**New users (last week)**</span></span>
  - <span data-ttu-id="d3c8f-118">Um link para o [relatório de alterações de encaminhamento](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d3c8f-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Submenu de detalhes do relatório de mensagens automaticamente encaminhadas no centro de conformidade & segurança](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="d3c8f-120">Informações</span><span class="sxs-lookup"><span data-stu-id="d3c8f-120">Insights</span></span>

<span data-ttu-id="d3c8f-121">Dois insights são gerados com base nos dados do relatório:</span><span class="sxs-lookup"><span data-stu-id="d3c8f-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="d3c8f-122">Novos usuários encaminhando email</span><span class="sxs-lookup"><span data-stu-id="d3c8f-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="d3c8f-123">Novos domínios sendo encaminhados emails</span><span class="sxs-lookup"><span data-stu-id="d3c8f-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="d3c8f-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="d3c8f-124">See also</span></span>

<span data-ttu-id="d3c8f-125">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="d3c8f-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
