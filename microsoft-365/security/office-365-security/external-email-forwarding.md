---
title: Configurando e controlando o encaminhamento de emails externos, encaminhamento automático, acesso de 5.7.520 negado, desabilitar o encaminhamento externo, o administrador desabilitou o encaminhamento externo, política antispam de saída
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 78ba5183667f4e5c6f713182969338f3ef2e7262
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600524"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="b8098-103">Configurando o encaminhamento de email externo no Office 365</span><span class="sxs-lookup"><span data-stu-id="b8098-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b8098-104">O encaminhamento externo é controlado pela *política antispam de saída* e com escopo para os usuários com base na configuração configurada.</span><span class="sxs-lookup"><span data-stu-id="b8098-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="b8098-105">As 3 configurações atualmente são suportadas:</span><span class="sxs-lookup"><span data-stu-id="b8098-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="b8098-106">**Automático** – o encaminhamento externo automático é bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b8098-106">**Automatic** – Automatic external forwarding is blocked.</span></span> <span data-ttu-id="b8098-107">O encaminhamento automático de mensagens interno continuará funcionando.</span><span class="sxs-lookup"><span data-stu-id="b8098-107">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="b8098-108">Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="b8098-108">This is the default setting.</span></span>

- <span data-ttu-id="b8098-109">**Ativado** – o encaminhamento externo automático é permitido e não é restrito.</span><span class="sxs-lookup"><span data-stu-id="b8098-109">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="b8098-110">**Off** – o encaminhamento externo automático está desabilitado e resultará em um relatório de falha na entrega (NDR) para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="b8098-110">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="b8098-111">Consulte [Configure Outbound spam Filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) para obter mais informações sobre como definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="b8098-111">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="b8098-112">Desabilitar o encaminhamento automático também desabilitará as regras de caixa de entrada que redirecionam mensagens para endereços externos.</span><span class="sxs-lookup"><span data-stu-id="b8098-112">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="b8098-113">Controle de encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="b8098-113">Controlling external email forwarding</span></span>

<span data-ttu-id="b8098-114">Como administrador de uma organização, você pode ter requisitos de empresa para restringir ou controlar quem poderá encaminhar emails automaticamente usando regras de caixa de entrada ou encaminhamento SMTP, fora da organização.</span><span class="sxs-lookup"><span data-stu-id="b8098-114">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="b8098-115">O encaminhamento de emails pode ser um recurso útil, mas também pode representar um risco por meio da possível divulgação de informações, mesmo fornecendo informações a invasores que podem ser aproveitados para atacar a organização ou seus parceiros.</span><span class="sxs-lookup"><span data-stu-id="b8098-115">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="b8098-116">O Office 365 não permite o encaminhamento externo automático por regras de caixa de entrada ou configuração de caixa de correio, que fornece uma política padrão segura.</span><span class="sxs-lookup"><span data-stu-id="b8098-116">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="b8098-117">No entanto, o administrador pode modificar essas configurações para todos ou alguns usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="b8098-117">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="b8098-118">O encaminhamento de mensagens entre usuários internos não é afetado por tal modificação.</span><span class="sxs-lookup"><span data-stu-id="b8098-118">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="b8098-119">Desabilitar o encaminhamento automático para endereços externos no Office 365 está sendo lançado em fases com detalhes comunicados por meio de postagens do [centro de mensagens](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="b8098-119">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="b8098-120">Para ajudar os administradores a se preparar para essas alterações, eles modificam as políticas antecipadamente para garantir que não haja interrupção nos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="b8098-120">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="b8098-121">Mais informações sobre os usuários que usam o encaminhamento automático (regras de caixa de entrada ou encaminhamento SMTP) em sua organização podem ser encontradas no [relatório de mensagens de encaminhamento automático](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="b8098-121">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="b8098-122">Como essa política funciona com outros controles de encaminhamento automáticos</span><span class="sxs-lookup"><span data-stu-id="b8098-122">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="b8098-123">Como administrador, você pode já ter outros tipos de controles em vigor, bloqueando o encaminhamento automático em [domínios remotos](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) e o uso de uma regra de transporte do Exchange (ETR).</span><span class="sxs-lookup"><span data-stu-id="b8098-123">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="b8098-124">Esses dois controles são independentes desse recurso específico, por exemplo, se você permitir o encaminhamento automático para um domínio remoto, mas bloquear o encaminhamento automático por meio da política de spam de saída, o resultado será que a mensagem encaminhada automaticamente é bloqueada.</span><span class="sxs-lookup"><span data-stu-id="b8098-124">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="b8098-125">Da mesma forma, se você permitir o encaminhamento automático na política de spam de saída, mas bloqueá-lo em um ETR ou domínio remoto, a mensagem será bloqueada por qualquer um desses controles.</span><span class="sxs-lookup"><span data-stu-id="b8098-125">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="b8098-126">Isso permite que você, por exemplo, permita o encaminhamento automático na política de spam de saída e utilize domínios remotos para controlar os domínios para os quais os usuários podem encaminhar mensagens automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b8098-126">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="b8098-127">A mensagem de encaminhamento de email bloqueado</span><span class="sxs-lookup"><span data-stu-id="b8098-127">The blocked email forwarding message</span></span>

<span data-ttu-id="b8098-128">Quando uma mensagem é detectada como encaminhada automaticamente e a política organizacional *bloqueia* que a atividade de um relatório de falha na **entrega (NDR)** será gerada de volta para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="b8098-128">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="b8098-129">O relatório indicará que a mensagem não foi entregue.</span><span class="sxs-lookup"><span data-stu-id="b8098-129">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="b8098-130">O NDR terá o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="b8098-130">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
