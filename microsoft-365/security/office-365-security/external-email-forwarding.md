---
title: Configurando e controlando o encaminhamento de emails externos, encaminhamento automático, acesso de 5.7.520 negado, desabilitar o encaminhamento externo, o administrador desabilitou o encaminhamento externo, política antispam de saída
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: c1a7cd4d8f00c9e2433601903efd1fba7bb587f9
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681727"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="55867-103">Controlar o encaminhamento de email externo automático no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="55867-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="55867-104">Como administrador, você pode ter requisitos da empresa para restringir ou controlar mensagens encaminhadas automaticamente para destinatários externos (destinatários fora da sua organização).</span><span class="sxs-lookup"><span data-stu-id="55867-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="55867-105">O encaminhamento de emails pode ser útil, mas também pode representar um risco de segurança devido à possível divulgação de informações.</span><span class="sxs-lookup"><span data-stu-id="55867-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="55867-106">Os invasores podem usar essas informações para atacar sua organização ou seus parceiros.</span><span class="sxs-lookup"><span data-stu-id="55867-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="55867-107">Os seguintes tipos de encaminhamento automático estão disponíveis no Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="55867-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="55867-108">Os usuários podem configurar [regras de caixa de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) para encaminhar mensagens automaticamente para remetentes externos (deliberadamente ou como resultado de uma conta comprometida).</span><span class="sxs-lookup"><span data-stu-id="55867-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="55867-109">Os administradores podem configurar o [encaminhamento de caixa de correio](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (também conhecido como encaminhamento SMTP) para encaminhar mensagens automaticamente para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="55867-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as SMTP forwarding) to automatically forward messages to external recipients.</span></span>

<span data-ttu-id="55867-110">Você pode usar as políticas de filtro de spam de saída para controlar o encaminhamento automático para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="55867-110">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="55867-111">Três configurações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="55867-111">Three settings are available:</span></span>

- <span data-ttu-id="55867-112">**Automático**: o encaminhamento externo automático está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="55867-112">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="55867-113">O encaminhamento automático de mensagens interno continuará funcionando.</span><span class="sxs-lookup"><span data-stu-id="55867-113">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="55867-114">Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="55867-114">This is the default setting.</span></span>
- <span data-ttu-id="55867-115">**Ativado**: o encaminhamento externo automático é permitido e não é restrito.</span><span class="sxs-lookup"><span data-stu-id="55867-115">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="55867-116">**Off**: o encaminhamento externo automático está desabilitado e resultará em uma notificação de falha na entrega (também conhecida como NDR ou mensagem de devolução) para o remetente.</span><span class="sxs-lookup"><span data-stu-id="55867-116">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="55867-117">Para obter instruções sobre como definir essas configurações, consulte [Configure Outbound spam Filtering in EOP](configure-the-outbound-spam-policy.md).</span><span class="sxs-lookup"><span data-stu-id="55867-117">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

<span data-ttu-id="55867-118">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="55867-118">**Notes**:</span></span>

- <span data-ttu-id="55867-119">Desabilitar o encaminhamento automático também desabilitará as regras de caixa de entrada que redirecionam mensagens para endereços externos.</span><span class="sxs-lookup"><span data-stu-id="55867-119">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>

- <span data-ttu-id="55867-120">O encaminhamento automático de mensagens entre usuários internos não é afetado pelas configurações em políticas de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="55867-120">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>

- <span data-ttu-id="55867-121">Você pode ver informações sobre os usuários que estão encaminhando mensagens automaticamente para destinatários externos no [relatório de mensagens de encaminhamento automático](mfi-auto-forwarded-messages-report.md).</span><span class="sxs-lookup"><span data-stu-id="55867-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="55867-122">Como as configurações da política de filtro de spam de saída funcionam com outros controles de encaminhamento automáticos de email</span><span class="sxs-lookup"><span data-stu-id="55867-122">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="55867-123">Como administrador, você já deve ter configurado outros controles para permitir ou bloquear o encaminhamento automático de emails.</span><span class="sxs-lookup"><span data-stu-id="55867-123">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="55867-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="55867-124">For example:</span></span>

- <span data-ttu-id="55867-125">[Domínios remotos](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) para permitir ou bloquear o encaminhamento automático de emails para alguns ou todos os domínios externos.</span><span class="sxs-lookup"><span data-stu-id="55867-125">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>
- <span data-ttu-id="55867-126">Condições e ações nas [regras de fluxo de emails](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) do Exchange (também conhecidas como regras de transporte) para detectar e bloquear automaticamente mensagens encaminhadas para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="55867-126">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="55867-127">As regras de domínio remoto e de fluxo de emails são independentes das configurações nas políticas de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="55867-127">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="55867-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="55867-128">For example:</span></span>

- <span data-ttu-id="55867-129">Você permite o encaminhamento automático para um domínio remoto, mas bloqueia o encaminhamento automático em políticas de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="55867-129">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="55867-130">Neste exemplo, as mensagens encaminhadas automaticamente são bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="55867-130">In this example, automatically forwarded messages are blocked.</span></span>
- <span data-ttu-id="55867-131">Você permite o encaminhamento automático em políticas de filtro de spam de saída, mas usa regras de fluxo de emails ou configurações de domínio remoto para bloquear emails encaminhados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="55867-131">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="55867-132">Neste exemplo, as regras de fluxo de email ou as configurações de domínio remoto bloquearão mensagens automaticamente encaminhadas.</span><span class="sxs-lookup"><span data-stu-id="55867-132">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="55867-133">Essa independência de recurso permite que você (por exemplo) permita o encaminhamento automático em políticas de filtro de spam de saída, mas use domínios remotos para controlar os domínios externos aos quais os usuários podem encaminhar mensagens.</span><span class="sxs-lookup"><span data-stu-id="55867-133">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="55867-134">A mensagem de encaminhamento de email bloqueado</span><span class="sxs-lookup"><span data-stu-id="55867-134">The blocked email forwarding message</span></span>

<span data-ttu-id="55867-135">Quando uma mensagem é detectada como encaminhada automaticamente e a política organizacional *bloqueia* essa atividade, a mensagem é retornada ao remetente em uma notificação de falha na entrega que contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="55867-135">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
