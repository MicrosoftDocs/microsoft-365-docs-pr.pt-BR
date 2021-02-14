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
# <a name="get-started-with-app-control"></a><span data-ttu-id="19e54-103">Introdução ao controle de aplicativos</span><span class="sxs-lookup"><span data-stu-id="19e54-103">Get started with app control</span></span>

<span data-ttu-id="19e54-104">Antes de habilitar o controle de aplicativos em seu ambiente, revise e entenda como a Área de Trabalho Gerenciada da [Microsoft](../service-description/app-control.md) o implementa e suas funções e responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="19e54-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="19e54-105">A Área de Trabalho Gerenciada da Microsoft simplifica o controle de aplicativos ao cuidar dos aspectos mais desafiadores de obter uma política de base segura.</span><span class="sxs-lookup"><span data-stu-id="19e54-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="19e54-106">Os administradores de IT ainda devem testar seus aplicativos no anel teste e revisar os logs em busca de avisos ou erros.</span><span class="sxs-lookup"><span data-stu-id="19e54-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="19e54-107">Se um aplicativo precisar de uma isenção, você poderá fazer uma solicitação ou a Operação da Área de Trabalho Gerenciada da Microsoft poderá, dependendo de quem a detectar primeiro.</span><span class="sxs-lookup"><span data-stu-id="19e54-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="19e54-108">Implantação inicial de aplicativos</span><span class="sxs-lookup"><span data-stu-id="19e54-108">Initial deployment of apps</span></span>

<span data-ttu-id="19e54-109">Quando você implanta aplicativos pela primeira vez, a Área de Trabalho Gerenciada da Microsoft precisa avaliar seu comportamento atual.</span><span class="sxs-lookup"><span data-stu-id="19e54-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="19e54-110">As etapas exatas para ativar o controle de aplicativo dependem se os dispositivos já foram implantados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="19e54-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="19e54-111">Dispositivos ainda não em uso</span><span class="sxs-lookup"><span data-stu-id="19e54-111">Devices not yet in use</span></span>

<span data-ttu-id="19e54-112">Se você ainda não tiver dispositivos em uso, abra um tíquete de serviço com as Operações de Área de Trabalho Gerenciada da Microsoft solicitando que a adoção do controle de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="19e54-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="19e54-113">As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:</span><span class="sxs-lookup"><span data-stu-id="19e54-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="19e54-114">Grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="19e54-114">Deployment group</span></span>  |<span data-ttu-id="19e54-115">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="19e54-115">Policy type</span></span>  |<span data-ttu-id="19e54-116">Tempo</span><span class="sxs-lookup"><span data-stu-id="19e54-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="19e54-117">Testar</span><span class="sxs-lookup"><span data-stu-id="19e54-117">Test</span></span>     |  <span data-ttu-id="19e54-118">Auditoria</span><span class="sxs-lookup"><span data-stu-id="19e54-118">Audit</span></span>       |  <span data-ttu-id="19e54-119">Dia 0</span><span class="sxs-lookup"><span data-stu-id="19e54-119">Day 0</span></span>       |
|<span data-ttu-id="19e54-120">Primeiro</span><span class="sxs-lookup"><span data-stu-id="19e54-120">First</span></span>     | <span data-ttu-id="19e54-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="19e54-121">Enforced</span></span>        | <span data-ttu-id="19e54-122">1º dia</span><span class="sxs-lookup"><span data-stu-id="19e54-122">Day 1</span></span>        |
|<span data-ttu-id="19e54-123">Rápida</span><span class="sxs-lookup"><span data-stu-id="19e54-123">Fast</span></span>     | <span data-ttu-id="19e54-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="19e54-124">Enforced</span></span>        |  <span data-ttu-id="19e54-125">2º dia</span><span class="sxs-lookup"><span data-stu-id="19e54-125">Day 2</span></span>       |
|<span data-ttu-id="19e54-126">Amplas</span><span class="sxs-lookup"><span data-stu-id="19e54-126">Broad</span></span>     | <span data-ttu-id="19e54-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="19e54-127">Enforced</span></span>        |  <span data-ttu-id="19e54-128">3º dia</span><span class="sxs-lookup"><span data-stu-id="19e54-128">Day 3</span></span>       |

<span data-ttu-id="19e54-129">Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.</span><span class="sxs-lookup"><span data-stu-id="19e54-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="19e54-130">Dispositivos já em uso</span><span class="sxs-lookup"><span data-stu-id="19e54-130">Devices already in use</span></span>

<span data-ttu-id="19e54-131">Se já tiver pelo menos um dispositivo de Área de Trabalho Gerenciada da Microsoft em uso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="19e54-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="19e54-132">Abra um tíquete de serviço com as Operações de Área de Trabalho Gerenciada da Microsoft solicitando que a adoção do controle do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="19e54-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="19e54-133">As operações implantarão uma [política de auditoria em](../service-description/app-control.md#audit-policy) todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="19e54-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="19e54-134">[Teste seus aplicativos](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver se algum seria bloqueado.</span><span class="sxs-lookup"><span data-stu-id="19e54-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="19e54-135">Se um aplicativo seria bloqueado, abra uma [solicitação de signante.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)</span><span class="sxs-lookup"><span data-stu-id="19e54-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="19e54-136">Depois de concluir o teste (independentemente dos resultados), notifique o Operations, notificando quaisquer solicitações pendentes do signante.</span><span class="sxs-lookup"><span data-stu-id="19e54-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="19e54-137">As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:</span><span class="sxs-lookup"><span data-stu-id="19e54-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="19e54-138">Grupo de implantação</span><span class="sxs-lookup"><span data-stu-id="19e54-138">Deployment group</span></span>  |<span data-ttu-id="19e54-139">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="19e54-139">Policy type</span></span>  |<span data-ttu-id="19e54-140">Tempo</span><span class="sxs-lookup"><span data-stu-id="19e54-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="19e54-141">Testar</span><span class="sxs-lookup"><span data-stu-id="19e54-141">Test</span></span>     |  <span data-ttu-id="19e54-142">Auditoria</span><span class="sxs-lookup"><span data-stu-id="19e54-142">Audit</span></span>       |  <span data-ttu-id="19e54-143">Dia 0</span><span class="sxs-lookup"><span data-stu-id="19e54-143">Day 0</span></span>       |
|<span data-ttu-id="19e54-144">Primeiro</span><span class="sxs-lookup"><span data-stu-id="19e54-144">First</span></span>     | <span data-ttu-id="19e54-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="19e54-145">Enforced</span></span>        | <span data-ttu-id="19e54-146">1º dia</span><span class="sxs-lookup"><span data-stu-id="19e54-146">Day 1</span></span>        |
|<span data-ttu-id="19e54-147">Rápida</span><span class="sxs-lookup"><span data-stu-id="19e54-147">Fast</span></span>     | <span data-ttu-id="19e54-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="19e54-148">Enforced</span></span>        |  <span data-ttu-id="19e54-149">Pausado, lançamento na solicitação</span><span class="sxs-lookup"><span data-stu-id="19e54-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="19e54-150">Amplas</span><span class="sxs-lookup"><span data-stu-id="19e54-150">Broad</span></span>     | <span data-ttu-id="19e54-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="19e54-151">Enforced</span></span>        |  <span data-ttu-id="19e54-152">Pausado, lançamento na solicitação</span><span class="sxs-lookup"><span data-stu-id="19e54-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="19e54-153">Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.</span><span class="sxs-lookup"><span data-stu-id="19e54-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



