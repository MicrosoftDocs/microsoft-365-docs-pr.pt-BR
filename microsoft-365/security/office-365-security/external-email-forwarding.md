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
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080108"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="a951d-103">Configurando o encaminhamento de email externo no Office 365</span><span class="sxs-lookup"><span data-stu-id="a951d-103">Configuring external email forwarding in Office 365</span></span>

<span data-ttu-id="a951d-104">O encaminhamento externo é controlado pela *política antispam de saída* e com escopo para os usuários com base na configuração configurada.</span><span class="sxs-lookup"><span data-stu-id="a951d-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="a951d-105">As 3 configurações atualmente são suportadas:</span><span class="sxs-lookup"><span data-stu-id="a951d-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="a951d-106">**Automático** – nesse modo, o sistema é responsável por decidir se uma mensagem encaminhada é permitida ou não.</span><span class="sxs-lookup"><span data-stu-id="a951d-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="a951d-107">Este é o modo padrão e, nesse modo, o sistema bloqueará o encaminhamento externo automático.</span><span class="sxs-lookup"><span data-stu-id="a951d-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="a951d-108">**Ativado** – o encaminhamento externo automático é permitido e não é restrito.</span><span class="sxs-lookup"><span data-stu-id="a951d-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="a951d-109">**Off** – o encaminhamento externo automático está desabilitado e resultará em um relatório de falha na entrega (NDR) para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="a951d-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="a951d-110">Consulte [Configure Outbound spam Filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) para obter mais informações sobre como definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="a951d-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) for more information on how to configure these settings.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="a951d-111">Controle de encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="a951d-111">Controlling external email forwarding</span></span>

<span data-ttu-id="a951d-112">Como administrador de uma organização, você pode ter requisitos de empresa para restringir ou controlar quem poderá encaminhar emails automaticamente usando regras de caixa de entrada ou encaminhamento SMTP, fora da organização.</span><span class="sxs-lookup"><span data-stu-id="a951d-112">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="a951d-113">O encaminhamento de emails pode ser um recurso útil, mas também pode representar um risco por meio da possível divulgação de informações, mesmo fornecendo informações a invasores que podem ser aproveitados para atacar a organização ou seus parceiros.</span><span class="sxs-lookup"><span data-stu-id="a951d-113">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="a951d-114">O Office 365 não permite o encaminhamento externo automático por regras de caixa de entrada ou configuração de caixa de correio, que fornece uma política padrão segura.</span><span class="sxs-lookup"><span data-stu-id="a951d-114">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="a951d-115">No entanto, o administrador pode modificar essas configurações para todos ou alguns usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="a951d-115">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="a951d-116">O encaminhamento de mensagens entre usuários internos não é afetado por tal modificação.</span><span class="sxs-lookup"><span data-stu-id="a951d-116">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="a951d-117">Desabilitar o encaminhamento automático para endereços externos no Office 365 está sendo lançado em fases com detalhes comunicados por meio de postagens do [centro de mensagens](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="a951d-117">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="a951d-118">Para ajudar os administradores a se preparar para essas alterações, eles modificam as políticas antecipadamente para garantir que não haja interrupção nos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a951d-118">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="a951d-119">Mais informações sobre os usuários que usam o encaminhamento automático (regras de caixa de entrada ou encaminhamento SMTP) em sua organização podem ser encontradas no [relatório de mensagens de encaminhamento automático](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="a951d-119">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="a951d-120">A mensagem de encaminhamento de email bloqueado</span><span class="sxs-lookup"><span data-stu-id="a951d-120">The blocked email forwarding message</span></span>

<span data-ttu-id="a951d-121">Quando uma mensagem é detectada como encaminhada automaticamente e a política organizacional *bloqueia* que a atividade de um relatório de falha na **entrega (NDR)** será gerada de volta para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="a951d-121">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="a951d-122">O relatório indicará que a mensagem não foi entregue.</span><span class="sxs-lookup"><span data-stu-id="a951d-122">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="a951d-123">O NDR terá o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="a951d-123">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
