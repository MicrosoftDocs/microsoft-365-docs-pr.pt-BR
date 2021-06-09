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
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104529"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="846bd-104">Implantar e rastrear configurações configuráveis - Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="846bd-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="846bd-105">Depois de fazer alterações em suas categorias de configuração e preparar uma implantação, a página de status de implantação permite que você comece a implantar suas configurações em grupos.</span><span class="sxs-lookup"><span data-stu-id="846bd-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="846bd-106">Esta página mostra um resumo de cada configuração configurável.</span><span class="sxs-lookup"><span data-stu-id="846bd-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="846bd-107">Ao abrir uma categoria de configuração, você pode implantar configurações em grupos e acompanhar o andamento dessas implantações.</span><span class="sxs-lookup"><span data-stu-id="846bd-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="846bd-108">Status da implantação</span><span class="sxs-lookup"><span data-stu-id="846bd-108">Deployment statuses</span></span> 

<span data-ttu-id="846bd-109">Esses são os status que você verá para cada implantação.</span><span class="sxs-lookup"><span data-stu-id="846bd-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="846bd-110">Status</span><span class="sxs-lookup"><span data-stu-id="846bd-110">Status</span></span>  | <span data-ttu-id="846bd-111">Explicação</span><span class="sxs-lookup"><span data-stu-id="846bd-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="846bd-112">Implantar</span><span class="sxs-lookup"><span data-stu-id="846bd-112">Deploy</span></span> | <span data-ttu-id="846bd-113">Sua alteração está esperando para ser implantada nesse grupo.</span><span class="sxs-lookup"><span data-stu-id="846bd-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="846bd-114">Em andamento</span><span class="sxs-lookup"><span data-stu-id="846bd-114">In progress</span></span> | <span data-ttu-id="846bd-115">A alteração está sendo aplicada a dispositivos ativos neste grupo.</span><span class="sxs-lookup"><span data-stu-id="846bd-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="846bd-116">Concluído</span><span class="sxs-lookup"><span data-stu-id="846bd-116">Complete</span></span> | <span data-ttu-id="846bd-117">A alteração concluída em todos os dispositivos ativos neste grupo.</span><span class="sxs-lookup"><span data-stu-id="846bd-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="846bd-118">Falhou</span><span class="sxs-lookup"><span data-stu-id="846bd-118">Failed</span></span> | <span data-ttu-id="846bd-119">A alteração falhou em 10% dos dispositivos ativos no grupo, portanto, a implantação foi interrompida.</span><span class="sxs-lookup"><span data-stu-id="846bd-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="846bd-120">Uma solicitação de suporte será aberta automaticamente com Área de Trabalho Gerenciada da Microsoft para solucionar problemas da implantação.</span><span class="sxs-lookup"><span data-stu-id="846bd-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="846bd-121">Revertido</span><span class="sxs-lookup"><span data-stu-id="846bd-121">Reverted</span></span> | <span data-ttu-id="846bd-122">A alteração foi revertida para a última alteração implantada com êxito em todos os grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="846bd-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="846bd-123">Implantar alterações</span><span class="sxs-lookup"><span data-stu-id="846bd-123">Deploy changes</span></span>

<span data-ttu-id="846bd-124">Mostraremos a imagem de plano de fundo da área de trabalho nestas instruções.</span><span class="sxs-lookup"><span data-stu-id="846bd-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="846bd-125">Depois de preparar uma implantação, você implanta alterações da página de status de implantação.</span><span class="sxs-lookup"><span data-stu-id="846bd-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="846bd-126">**Para implantar alterações**</span><span class="sxs-lookup"><span data-stu-id="846bd-126">**To deploy changes**</span></span>

1. <span data-ttu-id="846bd-127">Entre [no](https://endpoint.microsoft.com/) Microsoft Endpoint Manager e navegue até o menu **Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="846bd-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="846bd-128">Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="846bd-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="846bd-129">No espaço de trabalho **de status** de implantação, selecione a configuração que você deseja implantar e selecione a implantação em estágios a ser implantada.</span><span class="sxs-lookup"><span data-stu-id="846bd-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="846bd-130">Selecione **Implantar** para implantar a alteração em um dos grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="846bd-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="846bd-131">O ícone de cuidado laranja indica que há um grupo anterior disponível para implantação, pois é recomendável a distribuição em ordem.</span><span class="sxs-lookup"><span data-stu-id="846bd-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="846bd-132">Recomendamos a implantação em grupos de implantação nesta ordem: Test, First, Fast e, em seguida, Broad.</span><span class="sxs-lookup"><span data-stu-id="846bd-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="846bd-133">Quando as alterações são concluídas em cada grupo, o status muda para **Complete**.</span><span class="sxs-lookup"><span data-stu-id="846bd-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="846bd-134">Reverter implantação</span><span class="sxs-lookup"><span data-stu-id="846bd-134">Revert deployment</span></span>

<span data-ttu-id="846bd-135">Depois de ter implantado uma alteração, você pode reverter do **status de implantação.**</span><span class="sxs-lookup"><span data-stu-id="846bd-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="846bd-136">Quando você reverter uma  alteração em andamento ou **Concluída,** a implantação atual será interrompida.</span><span class="sxs-lookup"><span data-stu-id="846bd-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="846bd-137">A configuração será revertida para a última versão que foi implantada em todos os grupos.</span><span class="sxs-lookup"><span data-stu-id="846bd-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="846bd-138">Mostraremos as etapas para reverter uma alteração usando a imagem em segundo plano da Área de Trabalho como exemplo.</span><span class="sxs-lookup"><span data-stu-id="846bd-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="846bd-139">**Para reverter uma alteração**</span><span class="sxs-lookup"><span data-stu-id="846bd-139">**To revert a change**</span></span>
1. <span data-ttu-id="846bd-140">Entre [no](https://endpoint.microsoft.com/) Microsoft Endpoint Manager e navegue até o menu **Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="846bd-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="846bd-141">Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="846bd-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="846bd-142">No espaço de trabalho **de status** de implantação, selecione a configuração que você deseja reverter e selecione a implantação em estágios para reverter.</span><span class="sxs-lookup"><span data-stu-id="846bd-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="846bd-143">Em **Necessidade de reverter essa alteração?**, selecione Reverter **implantação**.</span><span class="sxs-lookup"><span data-stu-id="846bd-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="846bd-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="846bd-144">Additional resources</span></span>
- [<span data-ttu-id="846bd-145">Visão geral das configurações configuráveis</span><span class="sxs-lookup"><span data-stu-id="846bd-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="846bd-146">Referência de configurações que podem ser alteradas</span><span class="sxs-lookup"><span data-stu-id="846bd-146">Configurable settings reference</span></span>](config-setting-ref.md) 
