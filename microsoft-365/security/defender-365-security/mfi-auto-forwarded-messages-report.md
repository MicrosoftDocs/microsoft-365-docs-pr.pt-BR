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
description: Os administradores podem aprender sobre o relatório de mensagens encaminhadas automaticamente no painel fluxo de emails no Centro de Conformidade & Segurança.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053153"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="f7a92-103">Visão de mensagens encaminhadas automaticamente no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="f7a92-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f7a92-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="f7a92-104">**Applies to**</span></span>
- [<span data-ttu-id="f7a92-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f7a92-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f7a92-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f7a92-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f7a92-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7a92-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f7a92-108">O & **insight** de mensagens [](mail-flow-insights-v2.md) encaminhadas automaticamente no painel fluxo de emails no Centro de Conformidade e Segurança exibe informações sobre mensagens [que](https://protection.office.com) são encaminhadas automaticamente da sua organização para destinatários em domínios externos.</span><span class="sxs-lookup"><span data-stu-id="f7a92-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget de mensagens encaminhadas automaticamente no Centro de Conformidade & Segurança](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="f7a92-110">Detalhes das mensagens encaminhadas automaticamente</span><span class="sxs-lookup"><span data-stu-id="f7a92-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="f7a92-111">Quando você clica no número de mensagens no widget, um painel de sub-texto é exibido que mostra mais informações sobre as mensagens encaminhadas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="f7a92-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="f7a92-112">**Mensagens encaminhadas automaticamente por meio de métodos de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="f7a92-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="f7a92-113">**Por regras de fluxo de emails**</span><span class="sxs-lookup"><span data-stu-id="f7a92-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="f7a92-114">**Por regras de caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="f7a92-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="f7a92-115">**Por encaminhamento SMTP**: Este método indica o encaminhamento automático que os administradores podem configurar em uma caixa de correio, conforme descrito em [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="f7a92-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="f7a92-116">Um link para o [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="f7a92-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="f7a92-117">**Mensagens encaminhadas automaticamente por domínios e usuários:**</span><span class="sxs-lookup"><span data-stu-id="f7a92-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="f7a92-118">**Top 5 domínios encaminhados para**</span><span class="sxs-lookup"><span data-stu-id="f7a92-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="f7a92-119">**Novos domínios (semana passada)**</span><span class="sxs-lookup"><span data-stu-id="f7a92-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="f7a92-120">**Principais 5 usuários de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="f7a92-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="f7a92-121">**Novos usuários (semana passada)**</span><span class="sxs-lookup"><span data-stu-id="f7a92-121">**New users (last week)**</span></span>
  - <span data-ttu-id="f7a92-122">Um link para o [relatório de modificações de encaminhamento](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="f7a92-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Submenu de detalhes para o relatório de mensagens encaminhadas automaticamente no Centro de Conformidade & Segurança](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="f7a92-124">Percepções</span><span class="sxs-lookup"><span data-stu-id="f7a92-124">Insights</span></span>

<span data-ttu-id="f7a92-125">Duas percepções são geradas com base nos dados do relatório:</span><span class="sxs-lookup"><span data-stu-id="f7a92-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="f7a92-126">Novos usuários encaminhando emails</span><span class="sxs-lookup"><span data-stu-id="f7a92-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="f7a92-127">Novos domínios sendo encaminhados por email</span><span class="sxs-lookup"><span data-stu-id="f7a92-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="f7a92-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="f7a92-128">See also</span></span>

<span data-ttu-id="f7a92-129">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="f7a92-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>