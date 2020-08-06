---
title: Novos domínios sendo encaminhados informações sobre email
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender a usar os novos domínios que estão sendo encaminhados para o centro de administração do Exchange para investigar quando os usuários de sua organização estão encaminhando mensagens para domínios externos que nunca foram encaminhadas para o.
ms.openlocfilehash: 81a596d48696f28d62d68594f27081435487d17f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578353"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="149cb-103">Novos domínios que estão sendo encaminhados informações de email no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="149cb-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="149cb-104">Embora você possa ter motivos comerciais válidos para encaminhar mensagens de email para destinatários externos em domínios específicos, é suspeito quando os usuários em sua organização começam a encaminhar mensagens para domínios externos, e ninguém já encaminharia mensagens para esses domínios antes (novos domínios).</span><span class="sxs-lookup"><span data-stu-id="149cb-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="149cb-105">Essa condição pode indicar que as contas de usuário estão comprometidas.</span><span class="sxs-lookup"><span data-stu-id="149cb-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="149cb-106">Se você suspeitar que as contas foram comprometidas, confira [responder a uma conta de email comprometida](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="149cb-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="149cb-107">Os **novos domínios que estão sendo encaminhados** informações de email notifica você quando os usuários da sua organização estão encaminhando mensagens para novos domínios.</span><span class="sxs-lookup"><span data-stu-id="149cb-107">The **New domains being forwarded email** insight notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="149cb-108">Essa percepção aparece somente quando o problema é detectado e aparece na página de [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="149cb-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Novos domínios sendo encaminhados informações sobre email](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="149cb-110">Quando você clica no widget, um submenu aparece onde você pode encontrar mais detalhes sobre as mensagens encaminhadas, incluindo um link de volta para o [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="149cb-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Submenu de detalhes que aparece depois de clicar nos novos domínios que estão sendo encaminhados informações de email](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="149cb-112">Você também pode acessar essa página de detalhes ao selecionar a percepção depois de clicar em **Exibir tudo** na área de **recomendações de & principais** em (painel de**relatórios** \> **Dashboard** ou <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="149cb-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="149cb-113">Para impedir o encaminhamento automático de mensagens para domínios externos, configure um domínio remoto para alguns ou todos os domínios externos.</span><span class="sxs-lookup"><span data-stu-id="149cb-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="149cb-114">Para obter mais informações, consulte [gerenciar domínios remotos no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="149cb-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="149cb-115">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="149cb-115">Related topics</span></span>

<span data-ttu-id="149cb-116">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="149cb-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>