---
title: Gerenciar aplicativos na Área de Trabalho Gerenciada da Microsoft
description: Informações sobre como atualizar aplicativos de linha de negócios implantados em dispositivos da Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600678"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="9fa82-104">Gerenciar aplicativos da linha empresarial na Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9fa82-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="9fa82-105">Há algumas maneiras de gerenciar atualizações de aplicativos para aplicativos que você tenha integrado à Área de Trabalho Gerenciada da Microsoft e implantado em seus dispositivos da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9fa82-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9fa82-106">Você pode fazer atualizações de aplicativos no portal da Área de Trabalho Gerenciada da Microsoft ou no Intune.</span><span class="sxs-lookup"><span data-stu-id="9fa82-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="9fa82-107">Atualizar aplicativos de linha de negócios na Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9fa82-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="9fa82-108">**Para atualizar seus aplicativos de linha de negócios no portal da Área de Trabalho Gerenciada da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="9fa82-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="9fa82-109">Entre no Portal [de Administração da Área de Trabalho Gerenciada da Microsoft.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="9fa82-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="9fa82-110">Em **Inventário,** selecione **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="9fa82-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="9fa82-111">Selecione o aplicativo que você deseja atualizar e, em seguida, selecione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="9fa82-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="9fa82-112">Em **Gerenciar,** selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9fa82-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="9fa82-113">Clique **no arquivo do pacote do** aplicativo e navegue para carregar um novo arquivo de pacote do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9fa82-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="9fa82-114">Selecione **o arquivo do pacote do aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="9fa82-114">Select **App package file**.</span></span>
7. <span data-ttu-id="9fa82-115">Selecione o ícone da pasta e navegue até o local do arquivo de aplicativo atualizado.</span><span class="sxs-lookup"><span data-stu-id="9fa82-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="9fa82-116">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="9fa82-116">Select **Open**.</span></span> <span data-ttu-id="9fa82-117">As informações do aplicativo são atualizadas com as informações do pacote.</span><span class="sxs-lookup"><span data-stu-id="9fa82-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="9fa82-118">Verifique se **a versão do aplicativo** reflete o pacote do aplicativo atualizado.</span><span class="sxs-lookup"><span data-stu-id="9fa82-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="9fa82-119">O aplicativo atualizado será implantado nos dispositivos do usuário.</span><span class="sxs-lookup"><span data-stu-id="9fa82-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="9fa82-120">Atualizar aplicativos de linha de negócios no Intune</span><span class="sxs-lookup"><span data-stu-id="9fa82-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="9fa82-121">**Para atualizar seus aplicativos de linha de negócios no Intune**</span><span class="sxs-lookup"><span data-stu-id="9fa82-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="9fa82-122">Entre no [portal do Azure.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="9fa82-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="9fa82-123">Selecione **Todos os Serviços** do  >  **Intune.**</span><span class="sxs-lookup"><span data-stu-id="9fa82-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="9fa82-124">O Intune está na **seção Monitoramento + Gerenciamento.**</span><span class="sxs-lookup"><span data-stu-id="9fa82-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="9fa82-125">Selecione **Aplicativos cliente > aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="9fa82-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="9fa82-126">Encontre e selecione seu aplicativo na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="9fa82-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="9fa82-127">Na folha **Visão geral,** selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9fa82-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="9fa82-128">Selecione **o arquivo do pacote do aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="9fa82-128">Select **App package file**.</span></span>
7. <span data-ttu-id="9fa82-129">Selecione o ícone da pasta e navegue até o local do arquivo de aplicativo atualizado.</span><span class="sxs-lookup"><span data-stu-id="9fa82-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="9fa82-130">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="9fa82-130">Select **Open**.</span></span> <span data-ttu-id="9fa82-131">As informações do aplicativo são atualizadas com as informações do pacote.</span><span class="sxs-lookup"><span data-stu-id="9fa82-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="9fa82-132">Verifique se **a versão do aplicativo** reflete o pacote do aplicativo atualizado.</span><span class="sxs-lookup"><span data-stu-id="9fa82-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="9fa82-133">Reverter um aplicativo para uma versão anterior</span><span class="sxs-lookup"><span data-stu-id="9fa82-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="9fa82-134">Se houver um erro encontrado quando uma nova versão de um aplicativo for implantada, você poderá reverter para uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="9fa82-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="9fa82-135">O processo descrito aqui é para aplicativos em que o tipo está listado como aplicativo de linha de **negócios MSI** do Windows ou aplicativo **do Windows (Win 32) - visualização**</span><span class="sxs-lookup"><span data-stu-id="9fa82-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="9fa82-136">**Para reverter um aplicativo de linha de negócios para uma versão anterior**</span><span class="sxs-lookup"><span data-stu-id="9fa82-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="9fa82-137">Entre no Portal [de Administração da Área de Trabalho Gerenciada da Microsoft.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="9fa82-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="9fa82-138">Em **Inventário,** selecione **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="9fa82-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="9fa82-139">Selecione o aplicativo que você precisa reverter e selecione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="9fa82-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="9fa82-140">Em **Gerenciar,** selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9fa82-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="9fa82-141">Para aplicativos de linha de negócios **MSI** do Windows, selecione Informações do aplicativo e, em  **Ignorar** versão do aplicativo, selecione **Sim.**</span><span class="sxs-lookup"><span data-stu-id="9fa82-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="9fa82-142">Para **o aplicativo do Windows (Win 32) -** aplicativos de visualização, selecione **Informações** do aplicativo, selecione regras de **detecção** e, em seguida, **selecione Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9fa82-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="9fa82-143">Se houver uma regra MSI, verifique se a verificação da versão do produto **MSI** está definida como **Não.**</span><span class="sxs-lookup"><span data-stu-id="9fa82-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="9fa82-144">[Carregue uma versão anterior do arquivo de origem do aplicativo no](../get-started/deploy-apps.md) portal do Administrador da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9fa82-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

