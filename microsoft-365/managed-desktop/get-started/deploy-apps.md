---
title: Implantar aplicativos em dispositivos
description: Informações para adicionar e implantar aplicativos em dispositivos de área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769101"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="f8dd9-104">Implantar aplicativos em dispositivos</span><span class="sxs-lookup"><span data-stu-id="f8dd9-104">Deploy apps to devices</span></span>
<span data-ttu-id="f8dd9-105">Parte da integração com a área de trabalho gerenciada da Microsoft inclui a adição e implantação de aplicativos aos dispositivos do usuário.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="f8dd9-106">Quando estiver usando o portal de área de trabalho gerenciada da Microsoft, você poderá adicionar e implantar seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="f8dd9-107">O processo geral tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="f8dd9-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="f8dd9-108">[Adicionar aplicativos ao Microsoft Managed desktop portal](#1) – pode ser aplicativos LOB (linha de negócios) existentes ou aplicativos da Microsoft Store para empresas que você sincronizou com o Intune.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="f8dd9-109">[Criar grupos do Azure Active Directory (AD) para a atribuição de aplicativos](#2) -você usará esses grupos para gerenciar a atribuição de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="f8dd9-110">Atribuir aplicativos aos usuários</span><span class="sxs-lookup"><span data-stu-id="f8dd9-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="f8dd9-111">Etapa 1: adicionar aplicativos ao portal de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8dd9-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="f8dd9-112">Você pode adicionar [aplicativos baseados em Win32 ou Windows MSI](#lob-apps), ou [Microsoft Store para aplicativos de negócios](#msfb-apps) à área de trabalho gerenciada da Microsoft e implantá-los em dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="f8dd9-113">Aplicativos baseados em Win32 ou Windows MSI para a área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8dd9-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="f8dd9-114">Você pode adicionar seus aplicativos de linha de negócios (LOB) ao portal de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="f8dd9-115">Para obter informações sobre os requisitos para aplicativos instalados em dispositivos de área de trabalho gerenciada da Microsoft, consulte [requisitos de aplicativos de área de trabalho gerenciado da Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)</span><span class="sxs-lookup"><span data-stu-id="f8dd9-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="f8dd9-116">Neste procedimento, você selecionará o tipo de aplicativo que você deseja adicionar e, em seguida, configurar e carregar a origem do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="f8dd9-117">**Para adicionar seu aplicativo LOB ou aplicativo do Windows ao portal de área de trabalho gerenciada da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="f8dd9-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="f8dd9-118">Você pode entrar no portal de área de trabalho gerenciada da Microsoft ou entrar no Intune e, em seguida, procurar pela área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="f8dd9-119">Mostraremos a entrada no portal de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="f8dd9-120">Entre no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="f8dd9-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="f8dd9-121">Em **inventário** , selecione **aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-121">Under **Inventory** , select **Apps** .</span></span>
3.    <span data-ttu-id="f8dd9-122">Na carga de trabalho aplicativos, selecione **Adicionar** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-122">In the Apps workload, select **Add** .</span></span>
4.    <span data-ttu-id="f8dd9-123">Em **Adicionar aplicativo** , selecione **aplicativo de linha de negócios** ou **Windows app (Win32)** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-123">In **Add app** , select **Line-of-business app** or **Windows app (Win32)** .</span></span>
    - <span data-ttu-id="f8dd9-124">Se você selecionou o **aplicativo de linha de negócios** , consulte [Adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obter instruções sobre como adicionar e configurar aplicativos de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-124">If you selected **Line-of-business app** , see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="f8dd9-125">Se você tiver selecionado o **Windows app (Win32)** , confira o [Win32 app Management](https://docs.microsoft.com/intune/apps-win32-app-management) para instruções sobre como adicionar e configurar aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-125">If you selected **Windows app (Win32)** , see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="f8dd9-126">Aplicativos da Microsoft Store para empresas</span><span class="sxs-lookup"><span data-stu-id="f8dd9-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="f8dd9-127">Se você ainda não se inscreveu na Microsoft Store para empresas, você pode se inscrever ao comprar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="f8dd9-128">Depois de ter seus aplicativos, você pode sincronizá-los com a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="f8dd9-129">**Comprar aplicativos da Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="f8dd9-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="f8dd9-130">Entre na [Microsoft Store para empresas](https://businessstore.microsoft.com) com sua conta de administrador do Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="f8dd9-131">Selecione **comprar para meu grupo** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-131">Select **Shop for my group** .</span></span>
3. <span data-ttu-id="f8dd9-132">Use a pesquisa para encontrar o aplicativo desejado e selecione o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="f8dd9-133">Nos detalhes do produto, selecione **obter o aplicativo** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-133">On the product details, select **Get the App** .</span></span> <span data-ttu-id="f8dd9-134">A Microsoft Store adiciona o aplicativo aos **seus produtos** para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="f8dd9-135">**Para forçar uma sincronização entre o Intune e a Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="f8dd9-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="f8dd9-136">Entre no centro de [Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="f8dd9-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="f8dd9-137">Selecione conectores de **Administração de locatários**  >  **e tokens**  >  **da Microsoft Store para empresas** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business** .</span></span>
3. <span data-ttu-id="f8dd9-138">Selecione **sincronizar** para obter os aplicativos que você comprou da Microsoft Store no Intune.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="f8dd9-139">**Para verificar se uma sincronização entre o Intune e a Microsoft Store para empresas está ativa**</span><span class="sxs-lookup"><span data-stu-id="f8dd9-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="f8dd9-140">Entre na [Microsoft Store para empresas](https://businessstore.microsoft.com) com sua conta de administrador do Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="f8dd9-141">Selecione **gerenciar** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-141">Select **Manage** .</span></span>
3. <span data-ttu-id="f8dd9-142">Selecione **configurações** e, em seguida, **distribuir** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-142">Select **Settings** and then select **Distribute** .</span></span>
4. <span data-ttu-id="f8dd9-143">Em **ferramentas de gerenciamento** , verifique se o Intune está listado e se o status está **ativo** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-143">Under **Management tools** , verify that Intune is listed and that the status is **Active** .</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="f8dd9-144">Etapa 2: criar grupos do Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8dd9-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="f8dd9-145">Crie três grupos do Azure AD para cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="f8dd9-146">Esta tabela descreve os grupos que você precisará (disponível, obrigatório e desinstalação).</span><span class="sxs-lookup"><span data-stu-id="f8dd9-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="f8dd9-147">Tipo de atribuição de aplicativo</span><span class="sxs-lookup"><span data-stu-id="f8dd9-147">App assignment type</span></span> |    <span data-ttu-id="f8dd9-148">Uso de grupo</span><span class="sxs-lookup"><span data-stu-id="f8dd9-148">Group use</span></span>    | <span data-ttu-id="f8dd9-149">Exemplo de nome do Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8dd9-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="f8dd9-150">Disponível</span><span class="sxs-lookup"><span data-stu-id="f8dd9-150">Available</span></span> |  <span data-ttu-id="f8dd9-151">O aplicativo estará disponível no site ou aplicativo do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="f8dd9-152">MMD – *nome do aplicativo* – disponível</span><span class="sxs-lookup"><span data-stu-id="f8dd9-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="f8dd9-153">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="f8dd9-153">Required</span></span> |  <span data-ttu-id="f8dd9-154">O aplicativo é instalado em dispositivos nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="f8dd9-155">MMD – *nome do aplicativo* – obrigatório</span><span class="sxs-lookup"><span data-stu-id="f8dd9-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="f8dd9-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="f8dd9-156">Uninstall</span></span> |  <span data-ttu-id="f8dd9-157">O aplicativo é desinstalado de dispositivos nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="f8dd9-158">MMD – *nome do aplicativo* – desinstalar</span><span class="sxs-lookup"><span data-stu-id="f8dd9-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="f8dd9-159">Adicione seus usuários a esses grupos para disponibilizar o aplicativo, instalar o aplicativo ou remover o aplicativo do dispositivo de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="f8dd9-160">Etapa 3: atribuir aplicativos aos seus usuários</span><span class="sxs-lookup"><span data-stu-id="f8dd9-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="f8dd9-161">**Para atribuir o aplicativo aos seus usuários**</span><span class="sxs-lookup"><span data-stu-id="f8dd9-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="f8dd9-162">Entre no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="f8dd9-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="f8dd9-163">No painel da área de trabalho gerenciada, selecione **aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-163">In Managed Desktop pane, select **Apps** .</span></span>
3. <span data-ttu-id="f8dd9-164">Na carga de trabalho aplicativos, selecione o aplicativo para o qual você deseja atribuir usuários e selecione **atribuir usuários grupos** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups** .</span></span>
4. <span data-ttu-id="f8dd9-165">Para o aplicativo específico, selecione um tipo de atribuição (disponível, obrigatório, desinstalação) e atribua o grupo apropriado.</span><span class="sxs-lookup"><span data-stu-id="f8dd9-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="f8dd9-166">No painel atribuir aplicativos, selecione **OK** .</span><span class="sxs-lookup"><span data-stu-id="f8dd9-166">In the Assign Apps pane, select **OK** .</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="f8dd9-167">Etapas para começar a usar a área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8dd9-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="f8dd9-168">Adicionar e verificar contatos do administrador no portal de Administração</span><span class="sxs-lookup"><span data-stu-id="f8dd9-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="f8dd9-169">Ajustar o acesso condicional</span><span class="sxs-lookup"><span data-stu-id="f8dd9-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="f8dd9-170">Atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="f8dd9-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="f8dd9-171">Implantar o Portal da Empresa do Intune</span><span class="sxs-lookup"><span data-stu-id="f8dd9-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="f8dd9-172">Habilitar Roaming de Estado da Empresa</span><span class="sxs-lookup"><span data-stu-id="f8dd9-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="f8dd9-173">Configurar dispositivos</span><span class="sxs-lookup"><span data-stu-id="f8dd9-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="f8dd9-174">Preparar usuários para o uso dos dispositivos</span><span class="sxs-lookup"><span data-stu-id="f8dd9-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="f8dd9-175">Implantar aplicativos (este tópico)</span><span class="sxs-lookup"><span data-stu-id="f8dd9-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
