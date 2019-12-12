---
title: Implantar configurações configuráveis na área de trabalho gerenciada da Microsoft
description: Implantar e acompanhar alterações de configurações configuráveis na área de trabalho gerenciada da Microsoft.
keywords: Microsoft Managed desktop, Microsoft 365, serviço, documentação, implantação, implantação em estágios, configurações configuráveis
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 244070c7fd2d5c98f87990bcb4ef6de96ca5a90c
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962238"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="a55d3-104">Implantar e acompanhar configurações configuráveis-Microsoft Managed desktop</span><span class="sxs-lookup"><span data-stu-id="a55d3-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="a55d3-105">Depois de fazer alterações nas categorias de configuração e testar uma implantação, a página status da implantação permite que você comece a implantar suas configurações para grupos.</span><span class="sxs-lookup"><span data-stu-id="a55d3-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="a55d3-106">Esta página mostra um resumo de cada configuração configurável.</span><span class="sxs-lookup"><span data-stu-id="a55d3-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="a55d3-107">Ao abrir uma categoria de configuração, você pode implantar configurações para agrupar e acompanhar o progresso dessas implantações.</span><span class="sxs-lookup"><span data-stu-id="a55d3-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="a55d3-108">Status de implantação</span><span class="sxs-lookup"><span data-stu-id="a55d3-108">Deployment statuses</span></span> 

<span data-ttu-id="a55d3-109">Estes são os status que você verá para cada implantação.</span><span class="sxs-lookup"><span data-stu-id="a55d3-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="a55d3-110">Status</span><span class="sxs-lookup"><span data-stu-id="a55d3-110">Status</span></span>  | <span data-ttu-id="a55d3-111">Explicação</span><span class="sxs-lookup"><span data-stu-id="a55d3-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="a55d3-112">Implantar</span><span class="sxs-lookup"><span data-stu-id="a55d3-112">Deploy</span></span> | <span data-ttu-id="a55d3-113">Sua alteração está aguardando para ser implantada nesse grupo.</span><span class="sxs-lookup"><span data-stu-id="a55d3-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="a55d3-114">Em andamento</span><span class="sxs-lookup"><span data-stu-id="a55d3-114">In progress</span></span> | <span data-ttu-id="a55d3-115">A alteração está sendo aplicada aos dispositivos ativos desse grupo.</span><span class="sxs-lookup"><span data-stu-id="a55d3-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="a55d3-116">Completo</span><span class="sxs-lookup"><span data-stu-id="a55d3-116">Complete</span></span> | <span data-ttu-id="a55d3-117">A alteração foi concluída em todos os dispositivos ativos desse grupo.</span><span class="sxs-lookup"><span data-stu-id="a55d3-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="a55d3-118">Falhou</span><span class="sxs-lookup"><span data-stu-id="a55d3-118">Failed</span></span> | <span data-ttu-id="a55d3-119">A alteração falhou em 10 por cento de dispositivos ativos no grupo, portanto, a implantação foi interrompida.</span><span class="sxs-lookup"><span data-stu-id="a55d3-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="a55d3-120">Uma solicitação de suporte será aberta automaticamente com as operações de área de trabalho gerenciada da Microsoft para solucionar problemas de implantação.</span><span class="sxs-lookup"><span data-stu-id="a55d3-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="a55d3-121">Revertidos</span><span class="sxs-lookup"><span data-stu-id="a55d3-121">Reverted</span></span> | <span data-ttu-id="a55d3-122">A alteração foi revertida para a última alteração implantada com êxito em todos os grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="a55d3-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="a55d3-123">Implantar alterações</span><span class="sxs-lookup"><span data-stu-id="a55d3-123">Deploy changes</span></span>

<span data-ttu-id="a55d3-124">Mostraremos a imagem de plano de fundo da área de trabalho nessas instruções.</span><span class="sxs-lookup"><span data-stu-id="a55d3-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="a55d3-125">Depois de testar uma implantação, implante as alterações da página status da implantação.</span><span class="sxs-lookup"><span data-stu-id="a55d3-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="a55d3-126">**Para implantar alterações**</span><span class="sxs-lookup"><span data-stu-id="a55d3-126">**To deploy changes**</span></span>

1. <span data-ttu-id="a55d3-127">Entrar no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a55d3-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a55d3-128">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="a55d3-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a55d3-129">Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja implantar e, em seguida, selecione a implantação em estágios a ser implantada.</span><span class="sxs-lookup"><span data-stu-id="a55d3-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="a55d3-130">Selecione **implantar** para implantar a alteração em um dos grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="a55d3-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="a55d3-131">![Espaço de trabalho de status de implantação.</span><span class="sxs-lookup"><span data-stu-id="a55d3-131">![Deployment status workspace.</span></span> <span data-ttu-id="a55d3-132">Painel de sites confiáveis à direita.</span><span class="sxs-lookup"><span data-stu-id="a55d3-132">Trusted sites pane on the right.</span></span> <span data-ttu-id="a55d3-133">Na seção grupos de implantação há três colunas: grupos de implantação, dispositivos e status.</span><span class="sxs-lookup"><span data-stu-id="a55d3-133">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="a55d3-134">Na coluna status, "implantar" é realçado.](images/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="a55d3-134">In the status column, "deploy" is highlighted.](images/1deployedit.png)</span></span>
<span data-ttu-id="a55d3-135">Recomendamos a implantação de grupos de implantação nesta ordem: Test, First, Fast e, em seguida, ampla.</span><span class="sxs-lookup"><span data-stu-id="a55d3-135">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="a55d3-136">Quando as alterações são concluídas em cada grupo, o status é alterado para **concluído**.</span><span class="sxs-lookup"><span data-stu-id="a55d3-136">When changes complete in each group, the status changes to **Complete**.</span></span>

![Espaço de trabalho de status de implantação com colunas para data atualizada, versão, teste, primeiro, rápida e ampla.](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="a55d3-139">Reverter implantação</span><span class="sxs-lookup"><span data-stu-id="a55d3-139">Revert deployment</span></span>

<span data-ttu-id="a55d3-140">Depois de implantar uma alteração, você pode reverter do **status de implantação**.</span><span class="sxs-lookup"><span data-stu-id="a55d3-140">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="a55d3-141">Ao reverter uma alteração **em andamento** ou **concluída**, a implantação atual é interrompida.</span><span class="sxs-lookup"><span data-stu-id="a55d3-141">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="a55d3-142">A configuração será revertida para a última versão implantada em todos os grupos.</span><span class="sxs-lookup"><span data-stu-id="a55d3-142">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="a55d3-143">Mostraremos as etapas para reverter uma alteração usando a imagem de plano de fundo da área de trabalho como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a55d3-143">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="a55d3-144">**Para reverter uma alteração**</span><span class="sxs-lookup"><span data-stu-id="a55d3-144">**To revert a change**</span></span>
1. <span data-ttu-id="a55d3-145">Entrar no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a55d3-145">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a55d3-146">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="a55d3-146">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a55d3-147">Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja reverter e selecione a implantação em estágios a ser revertida.</span><span class="sxs-lookup"><span data-stu-id="a55d3-147">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="a55d3-148">Em **precisa reverter essa alteração?**, selecione **reverter implantação**.</span><span class="sxs-lookup"><span data-stu-id="a55d3-148">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![Espaço de trabalho de status de implantação.](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="a55d3-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a55d3-152">Additional resources</span></span>
- [<span data-ttu-id="a55d3-153">Visão geral das configurações configuráveis</span><span class="sxs-lookup"><span data-stu-id="a55d3-153">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="a55d3-154">Referência de configurações que podem ser alteradas</span><span class="sxs-lookup"><span data-stu-id="a55d3-154">Configurable settings reference</span></span>](config-setting-ref.md) 
