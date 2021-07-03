---
title: Implantar configurações configuráveis no Área de Trabalho Gerenciada da Microsoft
description: Implante e acompanhe as alterações de configurações configuráveis no Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação, implantação, implantação em estágios, configurações configuráveis
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287790"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="9552e-104">Implantar e rastrear configurações configuráveis - Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9552e-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="9552e-105">Depois de fazer alterações em suas categorias de configuração e preparar uma implantação, a página de status de implantação permite que você comece a implantar suas configurações em grupos.</span><span class="sxs-lookup"><span data-stu-id="9552e-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="9552e-106">Esta página mostra um resumo de cada configuração configurável.</span><span class="sxs-lookup"><span data-stu-id="9552e-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="9552e-107">Ao abrir uma categoria de configuração, você pode implantar configurações em grupos e acompanhar o andamento dessas implantações.</span><span class="sxs-lookup"><span data-stu-id="9552e-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="9552e-108">Status da implantação</span><span class="sxs-lookup"><span data-stu-id="9552e-108">Deployment statuses</span></span>

<span data-ttu-id="9552e-109">Esses são os status que você verá para cada implantação.</span><span class="sxs-lookup"><span data-stu-id="9552e-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="9552e-110">Status</span><span class="sxs-lookup"><span data-stu-id="9552e-110">Status</span></span> | <span data-ttu-id="9552e-111">Explicação</span><span class="sxs-lookup"><span data-stu-id="9552e-111">Explanation</span></span>
--- | ---
<span data-ttu-id="9552e-112">Implantar</span><span class="sxs-lookup"><span data-stu-id="9552e-112">Deploy</span></span> | <span data-ttu-id="9552e-113">Sua alteração está esperando para ser implantada nesse grupo.</span><span class="sxs-lookup"><span data-stu-id="9552e-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="9552e-114">Em andamento</span><span class="sxs-lookup"><span data-stu-id="9552e-114">In progress</span></span> | <span data-ttu-id="9552e-115">A alteração está sendo aplicada a dispositivos ativos neste grupo.</span><span class="sxs-lookup"><span data-stu-id="9552e-115">The change is being applied to active devices in this group.</span></span>
<span data-ttu-id="9552e-116">Concluído</span><span class="sxs-lookup"><span data-stu-id="9552e-116">Complete</span></span> | <span data-ttu-id="9552e-117">A alteração concluída em todos os dispositivos ativos neste grupo.</span><span class="sxs-lookup"><span data-stu-id="9552e-117">The change completed on all active devices in this group.</span></span>
<span data-ttu-id="9552e-118">Falhou</span><span class="sxs-lookup"><span data-stu-id="9552e-118">Failed</span></span> | <span data-ttu-id="9552e-119">A alteração falhou em 10% dos dispositivos ativos no grupo, portanto, a implantação foi interrompida.</span><span class="sxs-lookup"><span data-stu-id="9552e-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="9552e-120">Uma solicitação de suporte será aberta automaticamente com Área de Trabalho Gerenciada da Microsoft para solucionar problemas da implantação.</span><span class="sxs-lookup"><span data-stu-id="9552e-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span>
<span data-ttu-id="9552e-121">Revertido</span><span class="sxs-lookup"><span data-stu-id="9552e-121">Reverted</span></span> | <span data-ttu-id="9552e-122">A alteração foi revertida para a última alteração implantada com êxito em todos os grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="9552e-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="9552e-123">Implantar alterações</span><span class="sxs-lookup"><span data-stu-id="9552e-123">Deploy changes</span></span>

<span data-ttu-id="9552e-124">Mostraremos a imagem de plano de fundo da área de trabalho nestas instruções.</span><span class="sxs-lookup"><span data-stu-id="9552e-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="9552e-125">Depois de preparar uma implantação, você implanta alterações da página de status de implantação.</span><span class="sxs-lookup"><span data-stu-id="9552e-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span>

<span data-ttu-id="9552e-126">**Para implantar alterações**</span><span class="sxs-lookup"><span data-stu-id="9552e-126">**To deploy changes**</span></span>

1. <span data-ttu-id="9552e-127">Entre [no](https://endpoint.microsoft.com/) Microsoft Endpoint Manager e navegue até o menu **Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="9552e-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="9552e-128">Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="9552e-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="9552e-129">No espaço de trabalho **de status** de implantação, selecione a configuração que você deseja implantar e selecione a implantação em estágios a ser implantada.</span><span class="sxs-lookup"><span data-stu-id="9552e-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="9552e-130">Selecione **Implantar** para implantar a alteração em um dos grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="9552e-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE]
> <span data-ttu-id="9552e-131">O ícone de cuidado laranja indica que há um grupo anterior disponível para implantação, pois é recomendável a distribuição em ordem.</span><span class="sxs-lookup"><span data-stu-id="9552e-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="9552e-132">Recomendamos a implantação em grupos de implantação nesta ordem: Test, First, Fast e, em seguida, Broad.</span><span class="sxs-lookup"><span data-stu-id="9552e-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="9552e-133">Quando as alterações são concluídas em cada grupo, o status muda para **Complete**.</span><span class="sxs-lookup"><span data-stu-id="9552e-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="9552e-134">Reverter implantação</span><span class="sxs-lookup"><span data-stu-id="9552e-134">Revert deployment</span></span>

<span data-ttu-id="9552e-135">Depois de ter implantado uma alteração, você pode reverter do **status de implantação.**</span><span class="sxs-lookup"><span data-stu-id="9552e-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="9552e-136">Quando você reverter uma  alteração em andamento ou **Concluída,** a implantação atual será interrompida.</span><span class="sxs-lookup"><span data-stu-id="9552e-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="9552e-137">A configuração será revertida para a última versão que foi implantada em todos os grupos.</span><span class="sxs-lookup"><span data-stu-id="9552e-137">The setting will revert to the last version that was deployed to all groups.</span></span>

<span data-ttu-id="9552e-138">Mostraremos as etapas para reverter uma alteração usando a imagem em segundo plano da Área de Trabalho como exemplo.</span><span class="sxs-lookup"><span data-stu-id="9552e-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="9552e-139">**Para reverter uma alteração**</span><span class="sxs-lookup"><span data-stu-id="9552e-139">**To revert a change**</span></span>

1. <span data-ttu-id="9552e-140">Entre [no](https://endpoint.microsoft.com/) Microsoft Endpoint Manager e navegue até o menu **Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="9552e-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="9552e-141">Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="9552e-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="9552e-142">No espaço de trabalho **de status** de implantação, selecione a configuração que você deseja reverter e selecione a implantação em estágios para reverter.</span><span class="sxs-lookup"><span data-stu-id="9552e-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="9552e-143">Em **Necessidade de reverter essa alteração?**, selecione Reverter **implantação**.</span><span class="sxs-lookup"><span data-stu-id="9552e-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="9552e-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9552e-144">Additional resources</span></span>

- [<span data-ttu-id="9552e-145">Visão geral das configurações configuráveis</span><span class="sxs-lookup"><span data-stu-id="9552e-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="9552e-146">Referência de configurações que podem ser alteradas</span><span class="sxs-lookup"><span data-stu-id="9552e-146">Configurable settings reference</span></span>](config-setting-ref.md) 
