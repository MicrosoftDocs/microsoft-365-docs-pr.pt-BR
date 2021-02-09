---
title: Visão geral sobre mensagens encaminhadas automaticamente
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Os administradores podem saber mais sobre o relatório de mensagens encaminhadas automaticamente no painel Fluxo de emails no Centro de Conformidade e & Segurança.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c95c403e0b342bf0466c45804ba3975c492b8e1b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150589"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="c179d-103">Insight de mensagens encaminhadas automaticamente no Centro de Conformidade e Segurança & segurança</span><span class="sxs-lookup"><span data-stu-id="c179d-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c179d-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="c179d-104">**Applies to**</span></span>
- [<span data-ttu-id="c179d-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c179d-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="c179d-106">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="c179d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c179d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c179d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c179d-108">O & **insight** de mensagens [](mail-flow-insights-v2.md) encaminhadas automaticamente no painel fluxo de emails no Centro de Conformidade e Segurança exibe informações sobre mensagens [que](https://protection.office.com) são encaminhadas automaticamente da sua organização para destinatários em domínios externos.</span><span class="sxs-lookup"><span data-stu-id="c179d-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget mensagens encaminhadas automaticamente no Centro de Conformidade e Segurança & Segurança](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="c179d-110">Detalhes das mensagens encaminhadas automaticamente</span><span class="sxs-lookup"><span data-stu-id="c179d-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="c179d-111">Quando você clica no número de mensagens no widget, um painel de sub-texto é exibido, que mostra mais informações sobre as mensagens encaminhadas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="c179d-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="c179d-112">**Mensagens encaminhadas automaticamente por meio de métodos de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="c179d-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="c179d-113">**Por regras de fluxo de emails**</span><span class="sxs-lookup"><span data-stu-id="c179d-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="c179d-114">**Por regras da Caixa de Entrada**</span><span class="sxs-lookup"><span data-stu-id="c179d-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="c179d-115">**Por encaminhamento SMTP:** esse método indica o encaminhamento automático que os administradores podem configurar em uma caixa de correio, conforme descrito em Configurar o encaminhamento de [email para uma caixa de correio.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="c179d-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="c179d-116">Um link para o [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="c179d-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="c179d-117">**Mensagens encaminhadas automaticamente por domínios e usuários:**</span><span class="sxs-lookup"><span data-stu-id="c179d-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="c179d-118">**Os 5 principais domínios encaminhados para**</span><span class="sxs-lookup"><span data-stu-id="c179d-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="c179d-119">**Novos domínios (última semana)**</span><span class="sxs-lookup"><span data-stu-id="c179d-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="c179d-120">**Cinco principais usuários de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="c179d-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="c179d-121">**Novos usuários (última semana)**</span><span class="sxs-lookup"><span data-stu-id="c179d-121">**New users (last week)**</span></span>
  - <span data-ttu-id="c179d-122">Um link para o [relatório de modificações de encaminhamento](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="c179d-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Submenu de detalhes do relatório de mensagens encaminhadas automaticamente no Centro de Conformidade & Segurança](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="c179d-124">Insights</span><span class="sxs-lookup"><span data-stu-id="c179d-124">Insights</span></span>

<span data-ttu-id="c179d-125">Duas informações são geradas com base nos dados do relatório:</span><span class="sxs-lookup"><span data-stu-id="c179d-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="c179d-126">Novos usuários encaminhando emails</span><span class="sxs-lookup"><span data-stu-id="c179d-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="c179d-127">Novos domínios sendo encaminhados por email</span><span class="sxs-lookup"><span data-stu-id="c179d-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="c179d-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="c179d-128">See also</span></span>

<span data-ttu-id="c179d-129">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="c179d-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
