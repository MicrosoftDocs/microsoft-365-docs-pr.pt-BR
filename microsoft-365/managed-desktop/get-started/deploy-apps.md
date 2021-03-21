---
title: Implantar aplicativos em dispositivos
description: Informações para adicionar e implantar aplicativos em dispositivos da Área de Trabalho Gerenciada da Microsoft.
keywords: Microsoft Managed Desktop, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922021"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="3d377-104">Implantar aplicativos em dispositivos</span><span class="sxs-lookup"><span data-stu-id="3d377-104">Deploy apps to devices</span></span>
<span data-ttu-id="3d377-105">Parte da integração à Área de Trabalho Gerenciada da Microsoft inclui adicionar e implantar aplicativos aos dispositivos do usuário.</span><span class="sxs-lookup"><span data-stu-id="3d377-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="3d377-106">Depois de usar o portal da Área de Trabalho Gerenciada da Microsoft, você pode adicionar e implantar seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3d377-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="3d377-107">O processo geral tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="3d377-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="3d377-108">[Adicionar aplicativos](#1) ao portal da Área de Trabalho Gerenciada da Microsoft - Podem ser aplicativos de linha de negócios (LOB) existentes ou aplicativos da Microsoft Store para Empresas sincronizados com o Intune.</span><span class="sxs-lookup"><span data-stu-id="3d377-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="3d377-109">[Criar grupos do Azure Active Directory (AD)](#2) para atribuição de aplicativos - Você usará esses grupos para gerenciar a atribuição do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d377-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="3d377-110">Atribuir aplicativos aos seus usuários</span><span class="sxs-lookup"><span data-stu-id="3d377-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="3d377-111">Etapa 1: Adicionar aplicativos ao portal da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d377-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="3d377-112">Você pode adicionar [aplicativos baseados em Win32 ou Windows MSI](#lob-apps)ou [Microsoft Store para Empresas](#msfb-apps) à Área de Trabalho Gerenciada da Microsoft e implantá-los em dispositivos da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d377-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="3d377-113">Aplicativos baseados em Win32 ou Windows MSI para Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d377-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="3d377-114">Você pode adicionar seus aplicativos de linha de negócios (LOB) ao portal da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d377-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="3d377-115">Para obter informações sobre os requisitos para aplicativos instalados em dispositivos da Área de Trabalho Gerenciada da Microsoft, consulte [Requisitos de aplicativos da Área de Trabalho Gerenciada da Microsoft](../service-description/mmd-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d377-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="3d377-116">Neste procedimento, você selecionará qual tipo de aplicativo deseja adicionar e configurará e carregará a fonte do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d377-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="3d377-117">**Para adicionar seu aplicativo LOB ou aplicativo do Windows ao portal da Área de Trabalho Gerenciada da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="3d377-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="3d377-118">Você pode entrar no portal da Área de Trabalho Gerenciada da Microsoft ou entrar no Intune e procurar área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d377-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="3d377-119">Mostraremos como entrar no portal da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d377-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="3d377-120">Entre no [portal de Administração da Área de Trabalho Gerenciada da Microsoft](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="3d377-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="3d377-121">Em **Inventário,** selecione **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="3d377-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="3d377-122">Na carga de trabalho aplicativos, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3d377-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="3d377-123">Em **Adicionar aplicativo,** selecione **Aplicativo linha de negócios** ou aplicativo do Windows **(Win32)**.</span><span class="sxs-lookup"><span data-stu-id="3d377-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="3d377-124">Se você **selecionou** o aplicativo linha de negócios , consulte Adicionar um aplicativo de linha de negócios do Windows ao [Microsoft Intune](/intune/lob-apps-windows) para instruções sobre como adicionar e configurar aplicativos de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="3d377-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="3d377-125">Se você **selecionou o aplicativo do Windows (Win32),** confira Gerenciamento de [aplicativos Win32](/intune/apps-win32-app-management) para instruções sobre como adicionar e configurar aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="3d377-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="3d377-126">Aplicativos da Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="3d377-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="3d377-127">Se você ainda não se inscreveu na Microsoft Store para Empresas, poderá se inscrever ao comprar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3d377-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="3d377-128">Depois de ter seus aplicativos, você pode sincroná-los com a Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d377-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="3d377-129">**Para comprar aplicativos da Microsoft Store para Empresas**</span><span class="sxs-lookup"><span data-stu-id="3d377-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="3d377-130">Entre na [Microsoft Store para Empresas com](https://businessstore.microsoft.com) sua conta de Administrador da Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="3d377-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="3d377-131">Selecione **Comprar para o meu grupo**.</span><span class="sxs-lookup"><span data-stu-id="3d377-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="3d377-132">Use a Pesquisa para descobrir se o aplicativo que você deseja e selecione o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d377-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="3d377-133">Nos detalhes do produto, selecione **Obter o aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3d377-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="3d377-134">A Microsoft Store adiciona o aplicativo **aos Seus produtos** para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d377-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="3d377-135">**Para forçar uma sincronização entre o Intune e a Microsoft Store para Empresas**</span><span class="sxs-lookup"><span data-stu-id="3d377-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="3d377-136">Entre no Centro de [administração do Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="3d377-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="3d377-137">Selecione **Conectores de administração** de  >  **locatários e tokens** da Microsoft Store para  >  **Empresas.**</span><span class="sxs-lookup"><span data-stu-id="3d377-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="3d377-138">Selecione **Sincronizar** para obter os aplicativos que você comprou da Microsoft Store para o Intune.</span><span class="sxs-lookup"><span data-stu-id="3d377-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="3d377-139">**Para verificar se uma sincronização entre o Intune e a Microsoft Store para Empresas está ativa**</span><span class="sxs-lookup"><span data-stu-id="3d377-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="3d377-140">Entre na [Microsoft Store para Empresas com](https://businessstore.microsoft.com) sua conta de Administrador da Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="3d377-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="3d377-141">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="3d377-141">Select **Manage**.</span></span>
3. <span data-ttu-id="3d377-142">Selecione **Configurações** e selecione **Distribuir**.</span><span class="sxs-lookup"><span data-stu-id="3d377-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="3d377-143">Em **Ferramentas de Gerenciamento,** verifique se o Intune está listado e se o status é **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="3d377-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="3d377-144">Etapa 2: Criar grupos do Azure AD</span><span class="sxs-lookup"><span data-stu-id="3d377-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="3d377-145">Crie três grupos do Azure AD para cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d377-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="3d377-146">Esta tabela descreve os grupos de que você precisará (Disponível, Obrigatório e Desinstalar).</span><span class="sxs-lookup"><span data-stu-id="3d377-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="3d377-147">Tipo de atribuição de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3d377-147">App assignment type</span></span> |    <span data-ttu-id="3d377-148">Uso de grupo</span><span class="sxs-lookup"><span data-stu-id="3d377-148">Group use</span></span>    | <span data-ttu-id="3d377-149">Nome do Azure AD de exemplo</span><span class="sxs-lookup"><span data-stu-id="3d377-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="3d377-150">Disponível</span><span class="sxs-lookup"><span data-stu-id="3d377-150">Available</span></span> |  <span data-ttu-id="3d377-151">O aplicativo estará disponível no aplicativo ou site do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="3d377-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="3d377-152">MMD – *nome do aplicativo* – Disponível</span><span class="sxs-lookup"><span data-stu-id="3d377-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="3d377-153">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="3d377-153">Required</span></span> |  <span data-ttu-id="3d377-154">O aplicativo é instalado em dispositivos nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="3d377-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="3d377-155">MMD – *nome do aplicativo* – Obrigatório</span><span class="sxs-lookup"><span data-stu-id="3d377-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="3d377-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="3d377-156">Uninstall</span></span> |  <span data-ttu-id="3d377-157">O aplicativo é desinstalado de dispositivos nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="3d377-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="3d377-158">MMD – *nome do aplicativo* – Desinstalar</span><span class="sxs-lookup"><span data-stu-id="3d377-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="3d377-159">Adicione seus usuários a esses grupos para disponibilizar o aplicativo, instalar o aplicativo ou remover o aplicativo do dispositivo da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d377-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="3d377-160">Etapa 3: Atribuir aplicativos aos seus usuários</span><span class="sxs-lookup"><span data-stu-id="3d377-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="3d377-161">**Para atribuir o aplicativo aos seus usuários**</span><span class="sxs-lookup"><span data-stu-id="3d377-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="3d377-162">Entre no [portal de Administração da Área de Trabalho Gerenciada da Microsoft](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="3d377-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="3d377-163">No painel Área de Trabalho Gerenciada, selecione **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="3d377-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="3d377-164">Na carga de trabalho aplicativos, selecione o aplicativo ao que você deseja atribuir usuários e selecione **Atribuir grupos de usuários**.</span><span class="sxs-lookup"><span data-stu-id="3d377-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="3d377-165">Para o aplicativo específico, selecione um tipo de atribuição (Disponível, Obrigatório, Desinstalar) e atribua o grupo apropriado.</span><span class="sxs-lookup"><span data-stu-id="3d377-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="3d377-166">No painel Atribuir Aplicativos, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d377-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="3d377-167">Etapas para começar com a Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d377-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="3d377-168">Adicionar e verificar contatos do administrador no portal de Administração</span><span class="sxs-lookup"><span data-stu-id="3d377-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="3d377-169">Ajustar o acesso condicional</span><span class="sxs-lookup"><span data-stu-id="3d377-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="3d377-170">Atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="3d377-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="3d377-171">Implantar o Portal da Empresa do Intune</span><span class="sxs-lookup"><span data-stu-id="3d377-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="3d377-172">Habilitar Roaming de Estado da Empresa</span><span class="sxs-lookup"><span data-stu-id="3d377-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="3d377-173">Configurar dispositivos</span><span class="sxs-lookup"><span data-stu-id="3d377-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="3d377-174">Preparar usuários para o uso dos dispositivos</span><span class="sxs-lookup"><span data-stu-id="3d377-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="3d377-175">Implantar aplicativos (este tópico)</span><span class="sxs-lookup"><span data-stu-id="3d377-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->