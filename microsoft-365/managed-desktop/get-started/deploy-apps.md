---
title: Implantar aplicativos para dispositivos de área de trabalho gerenciada da Microsoft
description: Informações para adicionar e implantar aplicativos em dispositivos de área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: febb3198c434e638f83c412a3f8a3b688d9f5bd1
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414159"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="b1609-104">Implantar aplicativos em dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1609-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="b1609-105">Parte da integração com a área de trabalho gerenciada da Microsoft inclui a adição e implantação de aplicativos aos dispositivos do usuário.</span><span class="sxs-lookup"><span data-stu-id="b1609-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="b1609-106">Quando estiver usando o portal de área de trabalho gerenciada da Microsoft, você poderá adicionar e implantar seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b1609-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="b1609-107">O processo geral tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="b1609-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="b1609-108">[Adicionar aplicativos ao Microsoft Managed desktop portal](#1) – pode ser aplicativos LOB (linha de negócios) existentes ou aplicativos da Microsoft Store para empresas que você sincronizou com o Intune.</span><span class="sxs-lookup"><span data-stu-id="b1609-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="b1609-109">[Criar grupos do Azure Active Directory (AD) para a atribuição de aplicativos](#2) -você usará esses grupos para gerenciar a atribuição de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b1609-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="b1609-110">Atribuir aplicativos aos usuários</span><span class="sxs-lookup"><span data-stu-id="b1609-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="b1609-111">Etapa 1: adicionar aplicativos ao portal de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1609-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="b1609-112">Você pode adicionar [aplicativos baseados em Win32 ou Windows MSI](#lob-apps), ou [Microsoft Store para aplicativos de negócios](#msfb-apps) à área de trabalho gerenciada da Microsoft e implantá-los em dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1609-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="b1609-113">Aplicativos baseados em Win32 ou Windows MSI para a área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1609-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="b1609-114">Você pode adicionar seus aplicativos de linha de negócios (LOB) ao portal de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1609-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="b1609-115">Para obter informações sobre os requisitos para aplicativos instalados em dispositivos de área de trabalho gerenciada da Microsoft, consulte [requisitos de aplicativos de área de trabalho gerenciado da Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)</span><span class="sxs-lookup"><span data-stu-id="b1609-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="b1609-116">Neste procedimento, você selecionará o tipo de aplicativo que você deseja adicionar e, em seguida, configurar e carregar a origem do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b1609-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="b1609-117">**Para adicionar seu aplicativo LOB ou aplicativo do Windows ao portal de área de trabalho gerenciada da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="b1609-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="b1609-118">Você pode entrar no portal de área de trabalho gerenciada da Microsoft ou entrar no Intune e, em seguida, procurar pela área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1609-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="b1609-119">Mostraremos a entrada no portal de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1609-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="b1609-120">Entre no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="b1609-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="b1609-121">Em **inventário**, selecione **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b1609-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="b1609-122">Na carga de trabalho aplicativos, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b1609-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="b1609-123">Em **Adicionar aplicativo**, selecione **aplicativo de linha de negócios** ou **aplicativo Windows (Win32)-visualização**.</span><span class="sxs-lookup"><span data-stu-id="b1609-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="b1609-124">Se você selecionou o **aplicativo de linha de negócios**, consulte [Adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obter instruções sobre como adicionar e configurar aplicativos de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="b1609-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="b1609-125">Se você selecionou **Windows app (Win32) – Preview**, conFira o [Win32 app Management](https://docs.microsoft.com/intune/apps-win32-app-management) para instruções sobre como adicionar e configurar aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="b1609-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="b1609-126">Aplicativos da Microsoft Store para empresas</span><span class="sxs-lookup"><span data-stu-id="b1609-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="b1609-127">Se você ainda não se inscreveu na Microsoft Store para empresas, você pode se inscrever ao comprar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b1609-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="b1609-128">Depois de ter seus aplicativos, você pode sincronizá-los com a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1609-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="b1609-129">**Comprar aplicativos da Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="b1609-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="b1609-130">Entre na [Microsoft Store para empresas](https://businessstore.microsoft.com) com sua conta de administrador do Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="b1609-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="b1609-131">Selecione **comprar para meu grupo**.</span><span class="sxs-lookup"><span data-stu-id="b1609-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="b1609-132">Use a pesquisa para encontrar o aplicativo desejado e selecione o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b1609-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="b1609-133">Nos detalhes do produto, selecione **obter o aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="b1609-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="b1609-134">A Microsoft Store adiciona o aplicativo aos **Serviços do & de produtos** para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b1609-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="b1609-135">**Para forçar uma sincronização entre o Intune e a Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="b1609-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="b1609-136">Entrar no [portal do Azure](https://portal.azure.com/) como administrador do Intune ou administrador global para o locatário</span><span class="sxs-lookup"><span data-stu-id="b1609-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="b1609-137">Selecione **todos os serviços _GT_ Intune**.</span><span class="sxs-lookup"><span data-stu-id="b1609-137">Select **All services > Intune**.</span></span> <span data-ttu-id="b1609-138">O Intune está na seção monitoramento + gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b1609-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="b1609-139">No painel do Intune, selecione **aplicativos cliente**e, em seguida, selecione **Microsoft Store para empresas**.</span><span class="sxs-lookup"><span data-stu-id="b1609-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="b1609-140">Selecione **habilitar** para sincronizar seus aplicativos da Microsoft Store para empresas com o Intune.</span><span class="sxs-lookup"><span data-stu-id="b1609-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="b1609-141">Se você ainda não tiver feito isso, Inscreva-se e associe sua conta da Microsoft Store para empresas com o Intune</span><span class="sxs-lookup"><span data-stu-id="b1609-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="b1609-142">Selecione o idioma no qual os aplicativos da Microsoft Store para empresas serão exibidos no seu console do Intune</span><span class="sxs-lookup"><span data-stu-id="b1609-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="b1609-143">Selecione **sincronizar** para sincronizar seus aplicativos da Microsoft Store para empresas com o Intune.</span><span class="sxs-lookup"><span data-stu-id="b1609-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="b1609-144">Verifique se a sincronização entre a Microsoft Store para empresas e o Intune está ativa (próxima etapa).</span><span class="sxs-lookup"><span data-stu-id="b1609-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="b1609-145">**Para verificar se uma sincronização entre o Intune e a Microsoft Store para empresas está ativa**</span><span class="sxs-lookup"><span data-stu-id="b1609-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="b1609-146">Entre na [Microsoft Store para empresas](https://businessstore.microsoft.com) com sua conta de administrador do Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="b1609-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="b1609-147">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="b1609-147">Select **Manage**.</span></span>
3. <span data-ttu-id="b1609-148">Selecione **configurações** e, em seguida, **distribuir**.</span><span class="sxs-lookup"><span data-stu-id="b1609-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="b1609-149">Em **ferramentas de gerenciamento**, verifique se o Intune está listado e se o status está **ativo**.</span><span class="sxs-lookup"><span data-stu-id="b1609-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="b1609-150">Etapa 2: criar grupos do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b1609-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="b1609-151">Crie três grupos do Azure AD para cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b1609-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="b1609-152">Esta tabela descreve os grupos que você precisará (disponível, obrigatório e desInstalação).</span><span class="sxs-lookup"><span data-stu-id="b1609-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="b1609-153">Tipo de atribuição de aplicativo</span><span class="sxs-lookup"><span data-stu-id="b1609-153">App assignment type</span></span> |   <span data-ttu-id="b1609-154">Uso de grupo</span><span class="sxs-lookup"><span data-stu-id="b1609-154">Group use</span></span>   | <span data-ttu-id="b1609-155">Exemplo de nome do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b1609-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="b1609-156">Disponível</span><span class="sxs-lookup"><span data-stu-id="b1609-156">Available</span></span> |  <span data-ttu-id="b1609-157">O aplicativo estará disponível no site ou aplicativo do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b1609-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="b1609-158">MMD – *nome do aplicativo* – disponível</span><span class="sxs-lookup"><span data-stu-id="b1609-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="b1609-159">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b1609-159">Required</span></span> |  <span data-ttu-id="b1609-160">O aplicativo é instalado em dispositivos nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="b1609-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="b1609-161">MMD – *nome do aplicativo* – obrigatório</span><span class="sxs-lookup"><span data-stu-id="b1609-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="b1609-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="b1609-162">Uninstall</span></span> |  <span data-ttu-id="b1609-163">O aplicativo especifica é desinstalado dos dispositivos nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="b1609-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="b1609-164">MMD – *nome do aplicativo* – desinstalar</span><span class="sxs-lookup"><span data-stu-id="b1609-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="b1609-165">Adicione seus usuários a esses grupos para fazer com que o aplicativo disponibilize, instalar o aplicativo ou remover o aplicativo do dispositivo de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1609-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="b1609-166">Etapa 3: atribuir aplicativos aos seus usuários</span><span class="sxs-lookup"><span data-stu-id="b1609-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="b1609-167">**Para atribuir o aplicativo aos seus usuários**</span><span class="sxs-lookup"><span data-stu-id="b1609-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="b1609-168">Entre no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="b1609-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="b1609-169">No painel da área de trabalho gerenciada, selecione **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b1609-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="b1609-170">Na carga de trabalho aplicativos, selecione o aplicativo para o qual você deseja atribuir usuários e selecione **atribuir usuários grupos**.</span><span class="sxs-lookup"><span data-stu-id="b1609-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="b1609-171">Para o aplicativo específico, selecione um tipo de atribuição (disponível, obrigatório, desInstalação) e atribua o grupo apropriado.</span><span class="sxs-lookup"><span data-stu-id="b1609-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="b1609-172">No painel atribuir aplicativos, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1609-172">In the Assign Apps pane, select **OK**.</span></span>

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->