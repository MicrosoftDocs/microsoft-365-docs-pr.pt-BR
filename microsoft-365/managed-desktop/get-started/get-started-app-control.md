---
title: Introdução ao controle de aplicativos
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170679"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="18550-103">Introdução ao controle de aplicativos</span><span class="sxs-lookup"><span data-stu-id="18550-103">Get started with app control</span></span>

<span data-ttu-id="18550-104">Antes de habilitar o controle de aplicativos em seu ambiente, leia e entenda [como a área de trabalho gerenciada da Microsoft implementa](../service-description/app-control.md) e suas funções e responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="18550-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="18550-105">O Microsoft Managed desktop simplifica o controle de aplicativos ao cuidar dos aspectos mais desafiadores de obter uma política de base segura.</span><span class="sxs-lookup"><span data-stu-id="18550-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="18550-106">Seus administradores de ti ainda devem testar seus aplicativos no anel de teste e examinar os logs em busca de erros ou avisos.</span><span class="sxs-lookup"><span data-stu-id="18550-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="18550-107">Se um aplicativo precisar de uma isenção, você poderá arquivar uma solicitação, ou a operação de área de trabalho gerenciada da Microsoft poderá, dependendo de quem a detecta primeiro.</span><span class="sxs-lookup"><span data-stu-id="18550-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="18550-108">Implantação inicial de aplicativos</span><span class="sxs-lookup"><span data-stu-id="18550-108">Initial deployment of apps</span></span>

<span data-ttu-id="18550-109">Quando você implanta aplicativos pela primeira vez, o Microsoft Managed desktop precisa avaliar seu comportamento atual.</span><span class="sxs-lookup"><span data-stu-id="18550-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="18550-110">As etapas exatas para habilitar o controle de aplicativos dependem se os dispositivos já foram implantados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="18550-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="18550-111">Dispositivos já em uso</span><span class="sxs-lookup"><span data-stu-id="18550-111">Devices already in use</span></span>

<span data-ttu-id="18550-112">Se já tiver pelo menos um dispositivo de área de trabalho gerenciado da Microsoft em uso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="18550-112">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="18550-113">Abra um tíquete de serviço com operações de área de trabalho gerenciada da Microsoft solicitando que nós ativamos o controle de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="18550-113">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="18550-114">As operações irão implantar uma [política de auditoria](../service-description/app-control.md#audit-policy) para todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="18550-114">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="18550-115">[Teste seus aplicativos](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver se qualquer um será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="18550-115">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="18550-116">Se um aplicativo for bloqueado, abra uma [solicitação de signatário](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="18550-116">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="18550-117">Após concluir o teste (seja qual for o resultado), notifique as operações, observando todas as solicitações de signatário pendentes.</span><span class="sxs-lookup"><span data-stu-id="18550-117">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="18550-118">As operações implantarão progressivamente políticas em grupos de implantação seguindo esta programação:</span><span class="sxs-lookup"><span data-stu-id="18550-118">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="18550-119">Grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="18550-119">Deployment group</span></span>  |<span data-ttu-id="18550-120">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="18550-120">Policy type</span></span>  |<span data-ttu-id="18550-121">Tempo</span><span class="sxs-lookup"><span data-stu-id="18550-121">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="18550-122">Testar</span><span class="sxs-lookup"><span data-stu-id="18550-122">Test</span></span>     |  <span data-ttu-id="18550-123">Auditoria</span><span class="sxs-lookup"><span data-stu-id="18550-123">Audit</span></span>       |  <span data-ttu-id="18550-124">Dia 0</span><span class="sxs-lookup"><span data-stu-id="18550-124">Day 0</span></span>       |
|<span data-ttu-id="18550-125">Primeiro</span><span class="sxs-lookup"><span data-stu-id="18550-125">First</span></span>     | <span data-ttu-id="18550-126">Enforced</span><span class="sxs-lookup"><span data-stu-id="18550-126">Enforced</span></span>        | <span data-ttu-id="18550-127">1º dia</span><span class="sxs-lookup"><span data-stu-id="18550-127">Day 1</span></span>        |
|<span data-ttu-id="18550-128">Rápida</span><span class="sxs-lookup"><span data-stu-id="18550-128">Fast</span></span>     | <span data-ttu-id="18550-129">Enforced</span><span class="sxs-lookup"><span data-stu-id="18550-129">Enforced</span></span>        |  <span data-ttu-id="18550-130">3º dia</span><span class="sxs-lookup"><span data-stu-id="18550-130">Day 3</span></span>       |
|<span data-ttu-id="18550-131">Amplas</span><span class="sxs-lookup"><span data-stu-id="18550-131">Broad</span></span>     | <span data-ttu-id="18550-132">Enforced</span><span class="sxs-lookup"><span data-stu-id="18550-132">Enforced</span></span>        |  <span data-ttu-id="18550-133">Day 7</span><span class="sxs-lookup"><span data-stu-id="18550-133">Day 7</span></span>       |

<span data-ttu-id="18550-134">Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.</span><span class="sxs-lookup"><span data-stu-id="18550-134">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="18550-135">Dispositivos que ainda não estão em uso</span><span class="sxs-lookup"><span data-stu-id="18550-135">Devices not yet in use</span></span>

<span data-ttu-id="18550-136">Se você ainda não tiver dispositivos em uso, abra um tíquete de serviço com operações de área de trabalho gerenciada da Microsoft solicitando que o controle de aplicativos seja ativado.</span><span class="sxs-lookup"><span data-stu-id="18550-136">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="18550-137">As operações implantarão progressivamente políticas em grupos de implantação seguindo esta programação:</span><span class="sxs-lookup"><span data-stu-id="18550-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="18550-138">Grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="18550-138">Deployment group</span></span>  |<span data-ttu-id="18550-139">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="18550-139">Policy type</span></span>  |<span data-ttu-id="18550-140">Tempo</span><span class="sxs-lookup"><span data-stu-id="18550-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="18550-141">Testar</span><span class="sxs-lookup"><span data-stu-id="18550-141">Test</span></span>     |  <span data-ttu-id="18550-142">Auditoria</span><span class="sxs-lookup"><span data-stu-id="18550-142">Audit</span></span>       |  <span data-ttu-id="18550-143">Dia 0</span><span class="sxs-lookup"><span data-stu-id="18550-143">Day 0</span></span>       |
|<span data-ttu-id="18550-144">Primeiro</span><span class="sxs-lookup"><span data-stu-id="18550-144">First</span></span>     | <span data-ttu-id="18550-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="18550-145">Enforced</span></span>        | <span data-ttu-id="18550-146">1º dia</span><span class="sxs-lookup"><span data-stu-id="18550-146">Day 1</span></span>        |
|<span data-ttu-id="18550-147">Rápida</span><span class="sxs-lookup"><span data-stu-id="18550-147">Fast</span></span>     | <span data-ttu-id="18550-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="18550-148">Enforced</span></span>        |  <span data-ttu-id="18550-149">3º dia</span><span class="sxs-lookup"><span data-stu-id="18550-149">Day 3</span></span>       |
|<span data-ttu-id="18550-150">Amplas</span><span class="sxs-lookup"><span data-stu-id="18550-150">Broad</span></span>     | <span data-ttu-id="18550-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="18550-151">Enforced</span></span>        |  <span data-ttu-id="18550-152">Day 7</span><span class="sxs-lookup"><span data-stu-id="18550-152">Day 7</span></span>       |

<span data-ttu-id="18550-153">Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.</span><span class="sxs-lookup"><span data-stu-id="18550-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

