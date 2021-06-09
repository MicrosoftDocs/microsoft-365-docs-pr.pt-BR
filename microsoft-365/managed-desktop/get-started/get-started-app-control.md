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
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430454"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="27331-103">Introdução ao controle de aplicativos</span><span class="sxs-lookup"><span data-stu-id="27331-103">Get started with app control</span></span>

<span data-ttu-id="27331-104">Antes de habilitar o controle de aplicativos em seu ambiente, não deixe de analisar e entender como Área de Trabalho Gerenciada da Microsoft o implementa e suas funções e responsabilidades. [](../service-description/app-control.md)</span><span class="sxs-lookup"><span data-stu-id="27331-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="27331-105">Área de Trabalho Gerenciada da Microsoft simplifica o controle de aplicativos, tomando conta dos aspectos mais desafiadores da obtenção de uma política de base segura.</span><span class="sxs-lookup"><span data-stu-id="27331-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="27331-106">Os administradores de IT ainda devem testar seus aplicativos no anel de teste e revisar os logs em busca de avisos ou erros.</span><span class="sxs-lookup"><span data-stu-id="27331-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="27331-107">Se um aplicativo precisar de uma isenção, você poderá arquivar uma solicitação, ou Área de Trabalho Gerenciada da Microsoft operação pode, dependendo de quem detectá-la primeiro.</span><span class="sxs-lookup"><span data-stu-id="27331-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="27331-108">Implantação inicial de aplicativos</span><span class="sxs-lookup"><span data-stu-id="27331-108">Initial deployment of apps</span></span>

<span data-ttu-id="27331-109">Quando você implanta aplicativos pela primeira vez, Área de Trabalho Gerenciada da Microsoft precisa avaliar seu comportamento atual.</span><span class="sxs-lookup"><span data-stu-id="27331-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="27331-110">As etapas exatas para habilenciar o controle de aplicativo dependem se os dispositivos já foram implantados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="27331-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="27331-111">Dispositivos ainda não em uso</span><span class="sxs-lookup"><span data-stu-id="27331-111">Devices not yet in use</span></span>

<span data-ttu-id="27331-112">Se você ainda não tiver dispositivos em uso, abra um tíquete de serviço com Área de Trabalho Gerenciada da Microsoft Operações solicitando que abrimos o controle do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="27331-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="27331-113">As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:</span><span class="sxs-lookup"><span data-stu-id="27331-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="27331-114">Grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="27331-114">Deployment group</span></span>  |<span data-ttu-id="27331-115">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="27331-115">Policy type</span></span>  |<span data-ttu-id="27331-116">Tempo</span><span class="sxs-lookup"><span data-stu-id="27331-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="27331-117">Testar</span><span class="sxs-lookup"><span data-stu-id="27331-117">Test</span></span>     |  <span data-ttu-id="27331-118">Auditoria</span><span class="sxs-lookup"><span data-stu-id="27331-118">Audit</span></span>       |  <span data-ttu-id="27331-119">Dia 0</span><span class="sxs-lookup"><span data-stu-id="27331-119">Day 0</span></span>       |
|<span data-ttu-id="27331-120">Primeiro</span><span class="sxs-lookup"><span data-stu-id="27331-120">First</span></span>     | <span data-ttu-id="27331-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="27331-121">Enforced</span></span>        | <span data-ttu-id="27331-122">1º dia</span><span class="sxs-lookup"><span data-stu-id="27331-122">Day 1</span></span>        |
|<span data-ttu-id="27331-123">Rápida</span><span class="sxs-lookup"><span data-stu-id="27331-123">Fast</span></span>     | <span data-ttu-id="27331-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="27331-124">Enforced</span></span>        |  <span data-ttu-id="27331-125">2º dia</span><span class="sxs-lookup"><span data-stu-id="27331-125">Day 2</span></span>       |
|<span data-ttu-id="27331-126">Amplas</span><span class="sxs-lookup"><span data-stu-id="27331-126">Broad</span></span>     | <span data-ttu-id="27331-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="27331-127">Enforced</span></span>        |  <span data-ttu-id="27331-128">3º dia</span><span class="sxs-lookup"><span data-stu-id="27331-128">Day 3</span></span>       |

<span data-ttu-id="27331-129">Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.</span><span class="sxs-lookup"><span data-stu-id="27331-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="27331-130">Dispositivos já em uso</span><span class="sxs-lookup"><span data-stu-id="27331-130">Devices already in use</span></span>

<span data-ttu-id="27331-131">Se já tiver pelo menos um Área de Trabalho Gerenciada da Microsoft em uso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="27331-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="27331-132">Abra um tíquete de serviço com Área de Trabalho Gerenciada da Microsoft Operações solicitando que abrimos o controle do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="27331-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="27331-133">As operações implantarão uma [política de Auditoria](../service-description/app-control.md#audit-policy) em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="27331-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="27331-134">[Teste seus aplicativos](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver se algum seria bloqueado.</span><span class="sxs-lookup"><span data-stu-id="27331-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="27331-135">Se um aplicativo for bloqueado, abra uma [solicitação de signante](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="27331-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="27331-136">Depois de concluir o teste (independentemente dos resultados), notifique Operações, notificando quaisquer solicitações pendentes do signator.</span><span class="sxs-lookup"><span data-stu-id="27331-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="27331-137">As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:</span><span class="sxs-lookup"><span data-stu-id="27331-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="27331-138">Grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="27331-138">Deployment group</span></span>  |<span data-ttu-id="27331-139">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="27331-139">Policy type</span></span>  |<span data-ttu-id="27331-140">Tempo</span><span class="sxs-lookup"><span data-stu-id="27331-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="27331-141">Testar</span><span class="sxs-lookup"><span data-stu-id="27331-141">Test</span></span>     |  <span data-ttu-id="27331-142">Auditoria</span><span class="sxs-lookup"><span data-stu-id="27331-142">Audit</span></span>       |  <span data-ttu-id="27331-143">Dia 0</span><span class="sxs-lookup"><span data-stu-id="27331-143">Day 0</span></span>       |
|<span data-ttu-id="27331-144">Primeiro</span><span class="sxs-lookup"><span data-stu-id="27331-144">First</span></span>     | <span data-ttu-id="27331-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="27331-145">Enforced</span></span>        | <span data-ttu-id="27331-146">1º dia</span><span class="sxs-lookup"><span data-stu-id="27331-146">Day 1</span></span>        |
|<span data-ttu-id="27331-147">Rápida</span><span class="sxs-lookup"><span data-stu-id="27331-147">Fast</span></span>     | <span data-ttu-id="27331-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="27331-148">Enforced</span></span>        |  <span data-ttu-id="27331-149">Pausado, lançamento na solicitação</span><span class="sxs-lookup"><span data-stu-id="27331-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="27331-150">Amplas</span><span class="sxs-lookup"><span data-stu-id="27331-150">Broad</span></span>     | <span data-ttu-id="27331-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="27331-151">Enforced</span></span>        |  <span data-ttu-id="27331-152">Pausado, lançamento na solicitação</span><span class="sxs-lookup"><span data-stu-id="27331-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="27331-153">Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.</span><span class="sxs-lookup"><span data-stu-id="27331-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



