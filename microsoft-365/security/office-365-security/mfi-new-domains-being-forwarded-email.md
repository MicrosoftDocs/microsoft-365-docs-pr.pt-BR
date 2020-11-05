---
title: Email de visão geral sobre novos domínios encaminhados
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender a usar os novos domínios que estão sendo encaminhados para a percepção de email no painel de fluxo de emails no centro de conformidade de & de segurança para investigar quando seus usuários estão encaminhando mensagens para domínios externos que nunca foram encaminhadas para o.
ms.openlocfilehash: f2d8c9229062cbef0ad90b3d0fd843d6588a08dc
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920556"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="e9cd2-103">Novos domínios que estão sendo encaminhados informações de email no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="e9cd2-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e9cd2-104">Há motivos comerciais válidos para encaminhar mensagens de email para destinatários externos em domínios específicos.</span><span class="sxs-lookup"><span data-stu-id="e9cd2-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="e9cd2-105">No entanto, é suspeito quando os usuários em sua organização começam a encaminhar mensagens para um domínio em que ninguém em sua organização tenha encaminhado mensagens para (um novo domínio).</span><span class="sxs-lookup"><span data-stu-id="e9cd2-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="e9cd2-106">Essa condição pode indicar que as contas de usuário estão comprometidas.</span><span class="sxs-lookup"><span data-stu-id="e9cd2-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="e9cd2-107">Se você suspeitar que as contas foram comprometidas, confira [responder a uma conta de email comprometida](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="e9cd2-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="e9cd2-108">Os **novos domínios que estão sendo encaminhados** informações de email no [centro de conformidade e segurança &](https://protection.office.com) o notifica quando os usuários de sua organização estão encaminhando mensagens para novos domínios.</span><span class="sxs-lookup"><span data-stu-id="e9cd2-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="e9cd2-109">Essa percepção aparece somente quando o problema é detectado e aparece na página de [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="e9cd2-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Email de visão geral sobre novos domínios encaminhados](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="e9cd2-111">Quando você clica no widget, um submenu aparece onde você pode encontrar mais detalhes sobre as mensagens encaminhadas, incluindo um link de volta para o [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="e9cd2-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Submenu de detalhes que aparece depois de clicar nos novos domínios que estão sendo encaminhados informações de email](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="e9cd2-113">Você também pode acessar essa página de detalhes ao selecionar a percepção depois de clicar em **Exibir tudo** na área de **recomendações de & principais** em (painel de **relatórios** \> **Dashboard** ou <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="e9cd2-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on ( **Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="e9cd2-114">Para impedir o encaminhamento automático de mensagens para domínios externos, configure um domínio remoto para alguns ou todos os domínios externos.</span><span class="sxs-lookup"><span data-stu-id="e9cd2-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="e9cd2-115">Para obter mais informações, consulte [gerenciar domínios remotos no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="e9cd2-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e9cd2-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e9cd2-116">Related topics</span></span>

<span data-ttu-id="e9cd2-117">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="e9cd2-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
