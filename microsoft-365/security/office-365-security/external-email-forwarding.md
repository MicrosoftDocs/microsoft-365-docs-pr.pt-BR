---
title: Configurando e controlando o encaminhamento de email externo, encaminhamento automático, Acesso Negado 5.7.520, desabilitação do encaminhamento externo, Seu administrador desabilitou o encaminhamento externo, a política anti-spam de saída
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6b96d3d656a89e7102550d09a2f5052fdb5ae818
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52792951"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="0d832-103">Controlar o encaminhamento automático de email externo em Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d832-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0d832-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="0d832-104">**Applies to**</span></span>
- [<span data-ttu-id="0d832-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0d832-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0d832-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0d832-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0d832-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d832-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0d832-108">Como administrador, você pode ter requisitos da empresa para restringir ou controlar mensagens encaminhadas automaticamente para destinatários externos (destinatários fora da sua organização).</span><span class="sxs-lookup"><span data-stu-id="0d832-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="0d832-109">O encaminhamento de email pode ser útil, mas também pode representar um risco de segurança devido à divulgação potencial de informações.</span><span class="sxs-lookup"><span data-stu-id="0d832-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="0d832-110">Os invasores podem usar essas informações para atacar sua organização ou parceiros.</span><span class="sxs-lookup"><span data-stu-id="0d832-110">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="0d832-111">Os seguintes tipos de encaminhamento automático estão disponíveis em Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="0d832-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="0d832-112">Os usuários podem configurar [regras de Caixa de](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) Entrada para encaminhar automaticamente mensagens para os envios externos (deliberadamente ou como resultado de uma conta comprometida).</span><span class="sxs-lookup"><span data-stu-id="0d832-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>
- <span data-ttu-id="0d832-113">Os administradores podem configurar o [encaminhamento de caixa](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) de correio (também conhecido como encaminhamento _SMTP_) para encaminhar automaticamente mensagens para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="0d832-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="0d832-114">O administrador pode escolher se deve simplesmente encaminhar mensagens ou manter cópias de mensagens encaminhadas na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="0d832-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="0d832-115">Você pode usar políticas de filtro de spam de saída para controlar o encaminhamento automático para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="0d832-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="0d832-116">Três configurações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="0d832-116">Three settings are available:</span></span>

- <span data-ttu-id="0d832-117">**Automático - Controlado pelo sistema:** o encaminhamento externo automático está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="0d832-117">**Automatic - System-controlled**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="0d832-118">O encaminhamento automático interno das mensagens continuará a funcionar.</span><span class="sxs-lookup"><span data-stu-id="0d832-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="0d832-119">Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="0d832-119">This is the default setting.</span></span>
- <span data-ttu-id="0d832-120">**On**: O encaminhamento externo automático é permitido e não restrito.</span><span class="sxs-lookup"><span data-stu-id="0d832-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="0d832-121">**Desativado**: o encaminhamento externo automático está desabilitado e resultará em um relatório de não entrega (também conhecido como NDR ou mensagem de rejeição) para o remetente.</span><span class="sxs-lookup"><span data-stu-id="0d832-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="0d832-122">Para obter instruções sobre como configurar essas configurações, consulte [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span><span class="sxs-lookup"><span data-stu-id="0d832-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="0d832-123">Desabilitar o encaminhamento automático desabilita quaisquer regras de Caixa de Entrada (usuários) ou encaminhamento de caixa de correio (administradores) que redirecionam mensagens para endereços externos.</span><span class="sxs-lookup"><span data-stu-id="0d832-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="0d832-124">O encaminhamento automático de mensagens entre usuários internos não é afetado pelas configurações nas políticas de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="0d832-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="0d832-125">Você pode ver informações sobre usuários que estão encaminhando mensagens automaticamente para destinatários externos no relatório mensagens [encaminhadas automaticamente.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="0d832-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="0d832-126">Como as configurações de política de filtro de spam de saída funcionam com outros controles automáticos de encaminhamento de email</span><span class="sxs-lookup"><span data-stu-id="0d832-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="0d832-127">Como administrador, você pode já ter configurado outros controles para permitir ou bloquear o encaminhamento automático de email.</span><span class="sxs-lookup"><span data-stu-id="0d832-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="0d832-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0d832-128">For example:</span></span>

- <span data-ttu-id="0d832-129">[Domínios remotos](/exchange/mail-flow-best-practices/remote-domains/remote-domains) para permitir ou bloquear o encaminhamento automático de email para alguns ou todos os domínios externos.</span><span class="sxs-lookup"><span data-stu-id="0d832-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>
- <span data-ttu-id="0d832-130">Condições e ações em Exchange de fluxo de emails [(também](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) conhecidas como regras de transporte) para detectar e bloquear automaticamente as mensagens encaminhadas para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="0d832-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="0d832-131">As configurações de domínio remoto e as regras de fluxo de email são independentes das configurações nas políticas de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="0d832-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="0d832-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0d832-132">For example:</span></span>

- <span data-ttu-id="0d832-133">Você permite o encaminhamento automático para um domínio remoto, mas bloqueia o encaminhamento automático em políticas de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="0d832-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="0d832-134">Neste exemplo, as mensagens encaminhadas automaticamente são bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="0d832-134">In this example, automatically forwarded messages are blocked.</span></span>
- <span data-ttu-id="0d832-135">Você permite o encaminhamento automático em políticas de filtro de spam de saída, mas usa regras de fluxo de emails ou configurações de domínio remoto para bloquear emails encaminhados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0d832-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="0d832-136">Neste exemplo, as regras de fluxo de emails ou as configurações de domínio remoto bloquearão automaticamente as mensagens encaminhadas.</span><span class="sxs-lookup"><span data-stu-id="0d832-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="0d832-137">Essa independência de recursos permite que você (por exemplo) permita o encaminhamento automático em políticas de filtro de spam de saída, mas use domínios remotos para controlar os domínios externos para os que os usuários podem encaminhar mensagens.</span><span class="sxs-lookup"><span data-stu-id="0d832-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="0d832-138">Mensagens de encaminhamento de email bloqueadas</span><span class="sxs-lookup"><span data-stu-id="0d832-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="0d832-139">Quando uma mensagem é detectada como encaminhada automaticamente  e a política de filtro de [spam](configure-the-outbound-spam-policy.md) de saída bloqueia essa atividade, a mensagem é retornada ao remetente em uma NDR que contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="0d832-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
