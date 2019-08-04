---
title: Gerenciar aplicativos na área de trabalho gerenciada da Microsoft
description: Informações sobre como atualizar aplicativos de linha de negócios implantados em dispositivos de área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 87968e1238ee5b3dce6e569846e253dada72dd6d
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390728"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="4019c-104">Gerenciar aplicativos de linha de negócios na área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4019c-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="4019c-105">Há algumas maneiras de gerenciar as atualizações de aplicativo para aplicativos que você colocou na área de trabalho gerenciada da Microsoft e implantadas em seus dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4019c-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4019c-106">Você pode fazer atualizações de aplicativos no portal de área de trabalho gerenciada da Microsoft ou no Intune.</span><span class="sxs-lookup"><span data-stu-id="4019c-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="4019c-107">Atualizar aplicativos de linha de negócios na área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4019c-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="4019c-108">**Para atualizar seus aplicativos de linha de negócios no portal de área de trabalho gerenciada da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="4019c-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="4019c-109">Entre no [portal de administração de área de trabalho gerenciada da Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="4019c-109">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="4019c-110">Em **inventário**, selecione **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4019c-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="4019c-111">Selecione o aplicativo que você deseja atualizar e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4019c-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="4019c-112">Em **gerenciar**, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4019c-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="4019c-113">Clique em **arquivo de pacote de aplicativos**e navegue para carregar um novo arquivo de pacote de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4019c-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="4019c-114">Selecione o **arquivo do pacote de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4019c-114">Select **App package file**.</span></span>
7. <span data-ttu-id="4019c-115">Selecione o ícone da pasta e navegue até o local do arquivo do aplicativo atualizado.</span><span class="sxs-lookup"><span data-stu-id="4019c-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="4019c-116">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4019c-116">Select **Open**.</span></span> <span data-ttu-id="4019c-117">As informações do aplicativo são atualizadas com as informações do pacote.</span><span class="sxs-lookup"><span data-stu-id="4019c-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="4019c-118">Verifique se a **versão do aplicativo** reflete o pacote de aplicativos atualizado.</span><span class="sxs-lookup"><span data-stu-id="4019c-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="4019c-119">O aplicativo atualizado será implantado nos dispositivos do usuário.</span><span class="sxs-lookup"><span data-stu-id="4019c-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="4019c-120">Atualizar aplicativos de linha de negócios no Intune</span><span class="sxs-lookup"><span data-stu-id="4019c-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="4019c-121">**Para atualizar seus aplicativos de linha de negócios no Intune**</span><span class="sxs-lookup"><span data-stu-id="4019c-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="4019c-122">Entre no [portal do Azure](https://azure.portal.com).</span><span class="sxs-lookup"><span data-stu-id="4019c-122">Sign in to [Azure portal](https://azure.portal.com).</span></span>
2. <span data-ttu-id="4019c-123">Selecione **todos os serviços** > do**Intune**.</span><span class="sxs-lookup"><span data-stu-id="4019c-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="4019c-124">O Intune está na seção **monitoramento + gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="4019c-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="4019c-125">Selecione **aplicativos cliente > aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4019c-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="4019c-126">Localize e selecione seu aplicativo na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4019c-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="4019c-127">Na folha **visão geral** , selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4019c-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="4019c-128">Selecione o **arquivo do pacote de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4019c-128">Select **App package file**.</span></span>
7. <span data-ttu-id="4019c-129">Selecione o ícone da pasta e navegue até o local do arquivo do aplicativo atualizado.</span><span class="sxs-lookup"><span data-stu-id="4019c-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="4019c-130">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4019c-130">Select **Open**.</span></span> <span data-ttu-id="4019c-131">As informações do aplicativo são atualizadas com as informações do pacote.</span><span class="sxs-lookup"><span data-stu-id="4019c-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="4019c-132">Verifique se a **versão do aplicativo** reflete o pacote de aplicativos atualizado.</span><span class="sxs-lookup"><span data-stu-id="4019c-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="4019c-133">Reverter um aplicativo para uma versão anterior</span><span class="sxs-lookup"><span data-stu-id="4019c-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="4019c-134">Se houver um erro encontrado quando uma nova versão de um aplicativo for implantada, você poderá reverter para uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="4019c-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="4019c-135">O processo descrito aqui é para aplicativos onde tipo está listado como **Windows MSI linha de negócios** ou **aplicativo windows (Win 32)-Preview**</span><span class="sxs-lookup"><span data-stu-id="4019c-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="4019c-136">**Para reverter um aplicativo de linha de negócios para uma versão anterior**</span><span class="sxs-lookup"><span data-stu-id="4019c-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="4019c-137">Entre no [portal de administração de área de trabalho gerenciada da Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="4019c-137">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="4019c-138">Em **inventário**, selecione **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4019c-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="4019c-139">Selecione o aplicativo que você precisa reverter e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4019c-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="4019c-140">Em **gerenciar**, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4019c-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="4019c-141">Para aplicativos de aplicativos **de linha de negócios do Windows MSI** , selecione **informações do aplicativo**e, em **ignorar versão do aplicativo**, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="4019c-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="4019c-142">Para o **aplicativo Windows (Win 32)-Visualizar** aplicativos, selecione **informações do aplicativo**, selecione regras de **detecção**e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4019c-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="4019c-143">Se houver uma regra MSI, verifique se a **verificação de versão do produto MSI** está definida como **não**.</span><span class="sxs-lookup"><span data-stu-id="4019c-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="4019c-144">[Carregar uma versão anterior do arquivo de origem do aplicativo](../get-started/deploy-apps.md) no portal de administração de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4019c-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

