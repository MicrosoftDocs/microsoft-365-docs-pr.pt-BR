---
title: Implantar configurações configuráveis na área de trabalho gerenciada da Microsoft
description: Implantar e acompanhar alterações de configurações configuráveis na área de trabalho gerenciada da Microsoft.
keywords: Microsoft Managed desktop, Microsoft 365, serviço, documentação, implantação, implantação em estágios, configurações configuráveis
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4662373b926d07558ecedd05c9dfcf472ceb6357
ms.sourcegitcommit: d38c0ce846bac19e876a03a59ed4f268c7bae389
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900280"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="3a91d-104">Implantar e acompanhar configurações configuráveis-Microsoft Managed desktop</span><span class="sxs-lookup"><span data-stu-id="3a91d-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="3a91d-105">Depois de fazer alterações nas categorias de configuração e testar uma implantação, a página status da implantação permite que você comece a implantar suas configurações para grupos.</span><span class="sxs-lookup"><span data-stu-id="3a91d-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="3a91d-106">Esta página mostra um resumo de cada configuração configurável.</span><span class="sxs-lookup"><span data-stu-id="3a91d-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="3a91d-107">Ao abrir uma categoria de configuração, você pode implantar configurações para agrupar e acompanhar o progresso dessas implantações.</span><span class="sxs-lookup"><span data-stu-id="3a91d-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="3a91d-108">Status de implantação</span><span class="sxs-lookup"><span data-stu-id="3a91d-108">Deployment statuses</span></span> 

<span data-ttu-id="3a91d-109">Estes são os Statues que você verá para cada implantação.</span><span class="sxs-lookup"><span data-stu-id="3a91d-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="3a91d-110">Status</span><span class="sxs-lookup"><span data-stu-id="3a91d-110">Status</span></span>  | <span data-ttu-id="3a91d-111">Explicação</span><span class="sxs-lookup"><span data-stu-id="3a91d-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="3a91d-112">Implantar</span><span class="sxs-lookup"><span data-stu-id="3a91d-112">Deploy</span></span> | <span data-ttu-id="3a91d-113">Sua alteração está aguardando para ser implantada nesse grupo.</span><span class="sxs-lookup"><span data-stu-id="3a91d-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="3a91d-114">Em andamento</span><span class="sxs-lookup"><span data-stu-id="3a91d-114">In progress</span></span> | <span data-ttu-id="3a91d-115">A alteração está sendo aplicada aos dispositivos ativos desse grupo.</span><span class="sxs-lookup"><span data-stu-id="3a91d-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="3a91d-116">Completo</span><span class="sxs-lookup"><span data-stu-id="3a91d-116">Complete</span></span> | <span data-ttu-id="3a91d-117">A alteração foi concluída em todos os dispositivos ativos desse grupo.</span><span class="sxs-lookup"><span data-stu-id="3a91d-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="3a91d-118">Failed</span><span class="sxs-lookup"><span data-stu-id="3a91d-118">Failed</span></span> | <span data-ttu-id="3a91d-119">A alteração falhou em 10 por cento de dispositivos ativos no grupo, portanto, a implantação foi interrompida.</span><span class="sxs-lookup"><span data-stu-id="3a91d-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="3a91d-120">Uma solicitação de suporte será aberta automaticamente com as operações de área de trabalho gerenciada da Microsoft para solucionar problemas de implantação.</span><span class="sxs-lookup"><span data-stu-id="3a91d-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="3a91d-121">Revertidos</span><span class="sxs-lookup"><span data-stu-id="3a91d-121">Reverted</span></span> | <span data-ttu-id="3a91d-122">A alteração foi revertida para a última alteração implantada com êxito em todos os grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="3a91d-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="3a91d-123">Implantar alterações</span><span class="sxs-lookup"><span data-stu-id="3a91d-123">Deploy changes</span></span>

<span data-ttu-id="3a91d-124">Mostraremos a imagem de plano de fundo da área de trabalho nessas instruções.</span><span class="sxs-lookup"><span data-stu-id="3a91d-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="3a91d-125">Depois de testar uma implantação, implante as alterações da página status da implantação.</span><span class="sxs-lookup"><span data-stu-id="3a91d-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="3a91d-126">**Para implantar alterações**</span><span class="sxs-lookup"><span data-stu-id="3a91d-126">**To deploy changes**</span></span>

1. <span data-ttu-id="3a91d-127">Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="3a91d-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="3a91d-128">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="3a91d-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="3a91d-129">Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja implantar e, em seguida, selecione a implantação em estágios a ser implantada.</span><span class="sxs-lookup"><span data-stu-id="3a91d-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="3a91d-130">Selecione **implantar** para implantar a alteração em um dos grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="3a91d-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

![Visão geral do status de implantação de configurações configuráveis](images/deploy-cs-overview.png)

<span data-ttu-id="3a91d-132">A área de trabalho gerenciada da Microsoft recomenda a implantação de grupos de implantação nesta ordem: Test, First, Fast e, em seguida, ampla.</span><span class="sxs-lookup"><span data-stu-id="3a91d-132">Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="3a91d-133">Quando as alterações são concluídas em cada grupo, o status é alterado para **concluído**.</span><span class="sxs-lookup"><span data-stu-id="3a91d-133">When changes complete in each group, the status changes to **Complete**.</span></span>

![Implantação de configurações configuráveis concluída](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="3a91d-135">Reverter implantação</span><span class="sxs-lookup"><span data-stu-id="3a91d-135">Revert deployment</span></span>

<span data-ttu-id="3a91d-136">Depois de implantar uma alteração, você pode reverter do **status de implantação**.</span><span class="sxs-lookup"><span data-stu-id="3a91d-136">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="3a91d-137">Ao reverter uma alteração **em andamento** ou **concluída**, a implantação atual é interrompida.</span><span class="sxs-lookup"><span data-stu-id="3a91d-137">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="3a91d-138">A configuração será revertida para a última versão implantada em todos os grupos.</span><span class="sxs-lookup"><span data-stu-id="3a91d-138">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="3a91d-139">Mostraremos as etapas para reverter uma alteração usando a imagem de plano de fundo da área de trabalho como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="3a91d-139">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="3a91d-140">**Para reverter uma alteração**</span><span class="sxs-lookup"><span data-stu-id="3a91d-140">**To revert a change**</span></span>
1. <span data-ttu-id="3a91d-141">Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="3a91d-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="3a91d-142">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="3a91d-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="3a91d-143">Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja reverter e selecione a implantação em estágios a ser revertida.</span><span class="sxs-lookup"><span data-stu-id="3a91d-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="3a91d-144">Em **precisa reverter essa alteração**, selecione **reverter implantação**.</span><span class="sxs-lookup"><span data-stu-id="3a91d-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Reversão de implantação de configurações configurável](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="3a91d-146">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3a91d-146">Additional resources</span></span>
- [<span data-ttu-id="3a91d-147">Visão geral das configurações configuráveis</span><span class="sxs-lookup"><span data-stu-id="3a91d-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="3a91d-148">Referência de configurações configuráveis</span><span class="sxs-lookup"><span data-stu-id="3a91d-148">Configurable settings reference</span></span>](config-setting-ref.md) 
