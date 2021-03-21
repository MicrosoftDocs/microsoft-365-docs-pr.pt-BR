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
description: Os administradores podem aprender a usar os novos domínios que estão sendo encaminhados no painel de fluxo de emails no Centro de Conformidade do & de Segurança para investigar quando seus usuários estão encaminhando mensagens para domínios externos que nunca foram encaminhados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1310350bd4ff6b43d321f5888c9436ac71debb82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929343"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="c0705-103">Novos domínios que estão sendo encaminhados no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="c0705-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c0705-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="c0705-104">**Applies to**</span></span>
- [<span data-ttu-id="c0705-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c0705-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c0705-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c0705-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c0705-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0705-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c0705-108">Há motivos comerciais válidos para encaminhar mensagens de email para destinatários externos em domínios específicos.</span><span class="sxs-lookup"><span data-stu-id="c0705-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="c0705-109">No entanto, é suspeito quando os usuários em sua organização começam a encaminhar mensagens para um domínio para o qual ninguém em sua organização encaminhou mensagens (um novo domínio).</span><span class="sxs-lookup"><span data-stu-id="c0705-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="c0705-110">Essa condição pode indicar que as contas de usuário estão comprometidas.</span><span class="sxs-lookup"><span data-stu-id="c0705-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="c0705-111">Se você suspeitar que as contas foram comprometidas, consulte [Respondendo a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="c0705-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="c0705-112">Os **Novos domínios** [&](https://protection.office.com) que estão sendo encaminhados no Centro de Conformidade e Segurança notificam você quando os usuários em sua organização estão encaminhando mensagens para novos domínios.</span><span class="sxs-lookup"><span data-stu-id="c0705-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="c0705-113">Esse insight aparece somente quando o problema é detectado e aparece na página [Relatório de](view-mail-flow-reports.md#forwarding-report) Encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="c0705-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Email de visão geral sobre novos domínios encaminhados](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="c0705-115">Quando você clica no widget, um sobrevoo aparece onde você pode encontrar mais detalhes sobre as mensagens encaminhadas, incluindo um link de volta para o relatório [de encaminhamento](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="c0705-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Detalhes sobre o sobremenu que aparecem depois de clicar no insight de email novos domínios que estão sendo encaminhados](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="c0705-117">Você também pode acessar **essa** página de detalhes  quando selecionar o insight depois de clicar em Exibir tudo na área Principais & recomendações em (**Painel** de Relatórios \>  ou <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="c0705-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="c0705-118">Para impedir o encaminhamento automático de mensagens para domínios externos, configure um domínio remoto para alguns ou todos os domínios externos.</span><span class="sxs-lookup"><span data-stu-id="c0705-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="c0705-119">Para obter mais informações, consulte [Gerenciar domínios remotos no Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="c0705-119">For more information, see [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0705-120">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c0705-120">Related topics</span></span>

<span data-ttu-id="c0705-121">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="c0705-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>