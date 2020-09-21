---
title: Implantar configurações configuráveis na área de trabalho gerenciada da Microsoft
description: Implantar e acompanhar alterações de configurações configuráveis na área de trabalho gerenciada da Microsoft.
keywords: Microsoft Managed desktop, Microsoft 365, serviço, documentação, implantação, implantação em estágios, configurações configuráveis
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
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="a399b-104">Implantar e acompanhar configurações configuráveis-Microsoft Managed desktop</span><span class="sxs-lookup"><span data-stu-id="a399b-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="a399b-105">Depois de fazer alterações nas categorias de configuração e testar uma implantação, a página status da implantação permite que você comece a implantar suas configurações para grupos.</span><span class="sxs-lookup"><span data-stu-id="a399b-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="a399b-106">Esta página mostra um resumo de cada configuração configurável.</span><span class="sxs-lookup"><span data-stu-id="a399b-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="a399b-107">Ao abrir uma categoria de configuração, você pode implantar configurações para agrupar e acompanhar o progresso dessas implantações.</span><span class="sxs-lookup"><span data-stu-id="a399b-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="a399b-108">Status de implantação</span><span class="sxs-lookup"><span data-stu-id="a399b-108">Deployment statuses</span></span> 

<span data-ttu-id="a399b-109">Estes são os status que você verá para cada implantação.</span><span class="sxs-lookup"><span data-stu-id="a399b-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="a399b-110">Status</span><span class="sxs-lookup"><span data-stu-id="a399b-110">Status</span></span>  | <span data-ttu-id="a399b-111">Explicação</span><span class="sxs-lookup"><span data-stu-id="a399b-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="a399b-112">Implantar</span><span class="sxs-lookup"><span data-stu-id="a399b-112">Deploy</span></span> | <span data-ttu-id="a399b-113">Sua alteração está aguardando para ser implantada nesse grupo.</span><span class="sxs-lookup"><span data-stu-id="a399b-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="a399b-114">Em andamento</span><span class="sxs-lookup"><span data-stu-id="a399b-114">In progress</span></span> | <span data-ttu-id="a399b-115">A alteração está sendo aplicada aos dispositivos ativos desse grupo.</span><span class="sxs-lookup"><span data-stu-id="a399b-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="a399b-116">Completo</span><span class="sxs-lookup"><span data-stu-id="a399b-116">Complete</span></span> | <span data-ttu-id="a399b-117">A alteração foi concluída em todos os dispositivos ativos desse grupo.</span><span class="sxs-lookup"><span data-stu-id="a399b-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="a399b-118">Falhou</span><span class="sxs-lookup"><span data-stu-id="a399b-118">Failed</span></span> | <span data-ttu-id="a399b-119">A alteração falhou em 10 por cento de dispositivos ativos no grupo, portanto, a implantação foi interrompida.</span><span class="sxs-lookup"><span data-stu-id="a399b-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="a399b-120">Uma solicitação de suporte será aberta automaticamente com as operações de área de trabalho gerenciada da Microsoft para solucionar problemas de implantação.</span><span class="sxs-lookup"><span data-stu-id="a399b-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="a399b-121">Revertidos</span><span class="sxs-lookup"><span data-stu-id="a399b-121">Reverted</span></span> | <span data-ttu-id="a399b-122">A alteração foi revertida para a última alteração implantada com êxito em todos os grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="a399b-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="a399b-123">Implantar alterações</span><span class="sxs-lookup"><span data-stu-id="a399b-123">Deploy changes</span></span>

<span data-ttu-id="a399b-124">Mostraremos a imagem de plano de fundo da área de trabalho nessas instruções.</span><span class="sxs-lookup"><span data-stu-id="a399b-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="a399b-125">Depois de testar uma implantação, implante as alterações da página status da implantação.</span><span class="sxs-lookup"><span data-stu-id="a399b-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="a399b-126">**Para implantar alterações**</span><span class="sxs-lookup"><span data-stu-id="a399b-126">**To deploy changes**</span></span>

1. <span data-ttu-id="a399b-127">Entre no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e navegue até o menu **dispositivos**</span><span class="sxs-lookup"><span data-stu-id="a399b-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a399b-128">Procure a seção área de trabalho gerenciada da Microsoft, selecione **configurações**.</span><span class="sxs-lookup"><span data-stu-id="a399b-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a399b-129">Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja implantar e, em seguida, selecione a implantação em estágios a ser implantada.</span><span class="sxs-lookup"><span data-stu-id="a399b-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="a399b-130">Selecione **implantar** para implantar a alteração em um dos grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="a399b-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="a399b-131">O ícone de cuidado laranja indica que há um grupo anterior disponível para implantação conforme recomendado para distribuição na ordem.</span><span class="sxs-lookup"><span data-stu-id="a399b-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="a399b-132">Recomendamos a implantação de grupos de implantação nesta ordem: Test, First, Fast e, em seguida, ampla.</span><span class="sxs-lookup"><span data-stu-id="a399b-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="a399b-133">Quando as alterações são concluídas em cada grupo, o status é alterado para **concluído**.</span><span class="sxs-lookup"><span data-stu-id="a399b-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="a399b-134">Reverter implantação</span><span class="sxs-lookup"><span data-stu-id="a399b-134">Revert deployment</span></span>

<span data-ttu-id="a399b-135">Depois de implantar uma alteração, você pode reverter do **status de implantação**.</span><span class="sxs-lookup"><span data-stu-id="a399b-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="a399b-136">Ao reverter uma alteração **em andamento** ou **concluída**, a implantação atual é interrompida.</span><span class="sxs-lookup"><span data-stu-id="a399b-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="a399b-137">A configuração será revertida para a última versão implantada em todos os grupos.</span><span class="sxs-lookup"><span data-stu-id="a399b-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="a399b-138">Mostraremos as etapas para reverter uma alteração usando a imagem de plano de fundo da área de trabalho como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a399b-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="a399b-139">**Para reverter uma alteração**</span><span class="sxs-lookup"><span data-stu-id="a399b-139">**To revert a change**</span></span>
1. <span data-ttu-id="a399b-140">Entre no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e navegue até o menu **dispositivos**</span><span class="sxs-lookup"><span data-stu-id="a399b-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a399b-141">Procure a seção área de trabalho gerenciada da Microsoft, selecione **configurações**.</span><span class="sxs-lookup"><span data-stu-id="a399b-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a399b-142">Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja reverter e selecione a implantação em estágios a ser revertida.</span><span class="sxs-lookup"><span data-stu-id="a399b-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="a399b-143">Em **precisa reverter essa alteração?**, selecione **reverter implantação**.</span><span class="sxs-lookup"><span data-stu-id="a399b-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="a399b-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a399b-144">Additional resources</span></span>
- [<span data-ttu-id="a399b-145">Visão geral das configurações configuráveis</span><span class="sxs-lookup"><span data-stu-id="a399b-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="a399b-146">Referência de configurações que podem ser alteradas</span><span class="sxs-lookup"><span data-stu-id="a399b-146">Configurable settings reference</span></span>](config-setting-ref.md) 
