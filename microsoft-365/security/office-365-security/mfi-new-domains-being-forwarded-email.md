---
title: Email de visão geral sobre novos domínios encaminhados
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender a usar os novos domínios que estão sendo encaminhados no painel fluxo de emails no Centro de Conformidade e Segurança para investigar quando seus usuários estão encaminhando mensagens para domínio & s externos para os quais nunca foram encaminhados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eb44f5d577d18fc38333cca5e8d2d862f288a2e0
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029853"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="4a935-103">Visão dos novos domínios que estão sendo encaminhados no Centro de Conformidade e Segurança & segurança</span><span class="sxs-lookup"><span data-stu-id="4a935-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4a935-104">Há razões comerciais válidas para encaminhar mensagens de email para destinatários externos em domínios específicos.</span><span class="sxs-lookup"><span data-stu-id="4a935-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="4a935-105">No entanto, é suspeito quando os usuários em sua organização começam a encaminhar mensagens para um domínio para o qual ninguém em sua organização encaminhou mensagens (um novo domínio).</span><span class="sxs-lookup"><span data-stu-id="4a935-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="4a935-106">Essa condição pode indicar que as contas de usuário estão comprometidas.</span><span class="sxs-lookup"><span data-stu-id="4a935-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="4a935-107">Se você suspeitar que as contas foram comprometidas, confira [Responder a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="4a935-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="4a935-108">Os **novos domínios que** estão sendo encaminhados no Centro de Conformidade e Segurança & [notifica](https://protection.office.com) quando os usuários em sua organização estão encaminhando mensagens para novos domínios.</span><span class="sxs-lookup"><span data-stu-id="4a935-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="4a935-109">Esse insight só aparece quando o problema é detectado e aparece na página [de relatório de encaminhamento.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="4a935-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Email de visão geral sobre novos domínios encaminhados](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="4a935-111">Quando você clica no widget, um flyout é exibido, onde você pode encontrar mais detalhes sobre as mensagens encaminhadas, incluindo um link de volta para o relatório [de encaminhamento.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="4a935-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Detalhes do flyout que aparece depois de clicar nos novos domínios que estão sendo encaminhados insight de email](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="4a935-113">Você também pode acessar **essa** página de detalhes  ao selecionar as informações depois de clicar em Exibir tudo na área De informações principais & recomendações (**Painel** de Relatórios \>  ou <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="4a935-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="4a935-114">Para impedir o encaminhamento automático de mensagens para domínios externos, configure um domínio remoto para alguns ou todos os domínios externos.</span><span class="sxs-lookup"><span data-stu-id="4a935-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="4a935-115">Para obter mais informações, [consulte Gerenciar domínios remotos no Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="4a935-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4a935-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4a935-116">Related topics</span></span>

<span data-ttu-id="4a935-117">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="4a935-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
