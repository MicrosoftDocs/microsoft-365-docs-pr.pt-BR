---
title: Implantar aplicativos para dispositivos Microsoft Desktop gerenciados
description: Informações de adição e implantar aplicativos Microsoft Desktop gerenciados dispositivos.
keywords: Microsoft Desktop gerenciados, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341594"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="d0c15-104">Implantar aplicativos em dispositivos Microsoft Desktop gerenciados</span><span class="sxs-lookup"><span data-stu-id="d0c15-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d0c15-p101">Parte da inclusão à área de trabalho gerenciada do Microsoft inclui adicionando e implantar aplicativos dispositivos do seu usuário. Depois que você estiver usando o portal do Microsoft Desktop gerenciados, você pode adicionar e implantar seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d0c15-p101">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices. Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="d0c15-107">O processo geral tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="d0c15-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="d0c15-108">[Adicionar aplicativos ao portal do Microsoft Desktop gerenciados](#1) - isso pode ser existentes aplicativos da Microsoft Store for Business que você tiver sincronizados com Intune ou aplicativos de linha de negócios (LOB).</span><span class="sxs-lookup"><span data-stu-id="d0c15-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="d0c15-109">[Grupos de criar Azure AD (Active Directory) para atribuição de app](#2) - você utilizará esses grupos para gerenciar a atribuição de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d0c15-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="d0c15-110">Atribuir aplicativos para seus usuários</span><span class="sxs-lookup"><span data-stu-id="d0c15-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="d0c15-111">Etapa 1: Adicionar aplicativos ao portal do Microsoft Desktop gerenciados</span><span class="sxs-lookup"><span data-stu-id="d0c15-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="d0c15-112">Você pode adicionar [Win32, aplicativos baseados no Windows MSI](#lob-apps)ou [Armazenamento da Microsoft para aplicativos de negócios](#msfb-apps) para o Microsoft Desktop gerenciados e, em seguida, implantá-los nos dispositivos de área de trabalho gerenciada do Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0c15-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="d0c15-113">Win32 ou Windows aplicativos baseados em MSI à Microsoft gerenciados da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="d0c15-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="d0c15-p102">Você pode adicionar seus aplicativos de linha de negócios (LOB) ao portal do Microsoft Desktop gerenciados. Para obter informações sobre requisitos de aplicativos, instalados nos dispositivos de área de trabalho gerenciada do Microsoft, consulte [requisitos de aplicativo do Microsoft Desktop gerenciados](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="d0c15-p102">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal. For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="d0c15-116">Neste procedimento, você selecionará o tipo de aplicativo que deseja adicionar e, em seguida, configurar e carregar a fonte do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d0c15-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="d0c15-117">**Para adicionar seu aplicativo LOB ou aplicativo do Windows ao portal do Microsoft Desktop gerenciados**</span><span class="sxs-lookup"><span data-stu-id="d0c15-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="d0c15-p103">Você pode entre no portal do Microsoft Desktop gerenciados, ou entrar em Intune e procure Microsoft Desktop gerenciados. Mostraremos entrando no portal do Microsoft Desktop gerenciados.</span><span class="sxs-lookup"><span data-stu-id="d0c15-p103">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop. We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="d0c15-120">Faça logon no [portal de administração de área de trabalho gerenciada da Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="d0c15-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="d0c15-121">Em **inventário**, selecione **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="d0c15-122">Em que a carga de trabalho de aplicativos, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="d0c15-123">No **aplicativo de adicionar**, selecione **o aplicativo de linha de negócios** ou **a visualização do aplicativo do Windows (Win32)**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="d0c15-124">Se você selecionou um **aplicativo de linha de negócios**, consulte [Adicionar um aplicativo de linha de negócios do Windows para Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obter instruções sobre como adicionar e configurar aplicativos de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="d0c15-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="d0c15-125">Se você selecionou **a visualização do aplicativo do Windows (Win32 -)**, consulte o [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) para obter instruções sobre como adicionar e configurar aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="d0c15-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="d0c15-126">Armazenamento da Microsoft para aplicativos de negócios</span><span class="sxs-lookup"><span data-stu-id="d0c15-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="d0c15-p104">Se você ainda não se inscreveu com Microsoft Store for Business, você pode inscrever-se quando você faz compras para aplicativos. Depois de ter seus aplicativos, eles podem ser sincronizados com Microsoft Desktop gerenciados.</span><span class="sxs-lookup"><span data-stu-id="d0c15-p104">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps. After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="d0c15-129">**Comprar aplicativos a partir do Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="d0c15-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="d0c15-130">Entrar no [Microsoft Store for Business](https://businessstore.microsoft.com) com seu Store Microsoft para a conta de administrador de negócios.</span><span class="sxs-lookup"><span data-stu-id="d0c15-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="d0c15-131">Selecione a **loja para o meu grupo**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="d0c15-132">Usar a pesquisa para localizar a que o aplicativo desejado e selecione o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d0c15-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="d0c15-p105">Os detalhes do produto, selecione **obter o aplicativo**. Microsoft Store adiciona o aplicativo para **produtos e serviços &** para sua organização.</span><span class="sxs-lookup"><span data-stu-id="d0c15-p105">On the product details, select **Get the App**. Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="d0c15-135">**Para forçar uma sincronização entre Intune e Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="d0c15-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="d0c15-136">Entre no [Portal do Windows Azure](https://portal.azure.com/) como Intune Admin ou Administrador Global para seu locatário</span><span class="sxs-lookup"><span data-stu-id="d0c15-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="d0c15-p106">Selecione **todos os serviços gt _ Intune**. Intune estiver no monitoramento + gerenciamento seção.</span><span class="sxs-lookup"><span data-stu-id="d0c15-p106">Select **All services > Intune**. Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="d0c15-139">No painel Intune, selecione **Os aplicativos cliente**e selecione **Microsoft Store for Business**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="d0c15-140">Selecione **Habilitar** para sincronizar seu Store Microsoft para aplicativos de negócios com Intune.</span><span class="sxs-lookup"><span data-stu-id="d0c15-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="d0c15-141">Se você ainda não estiver, sign up e associe o Microsoft armazenar para a conta de negócios com Intune</span><span class="sxs-lookup"><span data-stu-id="d0c15-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="d0c15-142">Selecione o idioma no qual os aplicativos a partir do Microsoft Store for Business serão exibidos no seu console Intune</span><span class="sxs-lookup"><span data-stu-id="d0c15-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="d0c15-143">Selecione **sincronização** para sincronizar seu Store Microsoft para aplicativos de negócios com Intune.</span><span class="sxs-lookup"><span data-stu-id="d0c15-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="d0c15-144">Verifique se a sincronização entre o Microsoft Store for Business e Intune é ativa (próxima etapa).</span><span class="sxs-lookup"><span data-stu-id="d0c15-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="d0c15-145">**Para verificar se uma sincronização entre Intune e Microsoft Store for Business está ativa**</span><span class="sxs-lookup"><span data-stu-id="d0c15-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="d0c15-146">Entrar no [Microsoft Store for Business](https://businessstore.microsoft.com) com seu Store Microsoft para a conta de administrador de negócios.</span><span class="sxs-lookup"><span data-stu-id="d0c15-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="d0c15-147">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-147">Select **Manage**.</span></span>
3. <span data-ttu-id="d0c15-148">Selecione **configurações** e selecione **Distribute**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="d0c15-149">Em **Ferramentas de gerenciamento**, verifique se que Intune está listado e se o status está **ativa**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="d0c15-150">Etapa 2: Criar grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d0c15-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="d0c15-p107">Crie três grupos do Azure AD para cada aplicativo. Esta tabela descreve os grupos que você precisará (disponível, necessário e desinstalação).</span><span class="sxs-lookup"><span data-stu-id="d0c15-p107">Create three Azure AD groups for each app. This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="d0c15-153">Tipo de atribuição de aplicativo</span><span class="sxs-lookup"><span data-stu-id="d0c15-153">App assignment type</span></span> |   <span data-ttu-id="d0c15-154">Uso de grupo</span><span class="sxs-lookup"><span data-stu-id="d0c15-154">Group use</span></span>   | <span data-ttu-id="d0c15-155">Nome do exemplo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d0c15-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="d0c15-156">Disponível</span><span class="sxs-lookup"><span data-stu-id="d0c15-156">Available</span></span> |  <span data-ttu-id="d0c15-157">O aplicativo estará disponível no aplicativo do Portal da empresa ou site.</span><span class="sxs-lookup"><span data-stu-id="d0c15-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="d0c15-158">MMD – *nome do aplicativo* – disponível</span><span class="sxs-lookup"><span data-stu-id="d0c15-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="d0c15-159">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d0c15-159">Required</span></span> |  <span data-ttu-id="d0c15-160">O aplicativo está instalado nos dispositivos nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="d0c15-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="d0c15-161">MMD – *nome do aplicativo* – necessário</span><span class="sxs-lookup"><span data-stu-id="d0c15-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="d0c15-162">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="d0c15-162">Uninstall</span></span> |  <span data-ttu-id="d0c15-163">TThe app é desinstalado de dispositivos nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="d0c15-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="d0c15-164">MMD – *nome do aplicativo* – desinstalação</span><span class="sxs-lookup"><span data-stu-id="d0c15-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="d0c15-165">Adicione os usuários a esses grupos para tornar o app vem incluído, instale o aplicativo ou remover o aplicativo do seu dispositivo Microsoft Desktop gerenciados.</span><span class="sxs-lookup"><span data-stu-id="d0c15-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="d0c15-166">Etapa 3: Atribuir aplicativos para seus usuários</span><span class="sxs-lookup"><span data-stu-id="d0c15-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="d0c15-167">**Para atribuir o aplicativo para seus usuários**</span><span class="sxs-lookup"><span data-stu-id="d0c15-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="d0c15-168">Faça logon no [portal de administração de área de trabalho gerenciada da Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="d0c15-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="d0c15-169">No painel de área de trabalho gerenciado, selecione **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="d0c15-170">Em que a carga de trabalho de aplicativos, selecione o aplicativo que você deseja atribuir aos usuários e selecione **atribuir grupos de usuários**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="d0c15-171">Para o aplicativo específico, selecione um tipo de atribuição (disponível, necessário, desinstalar) e atribuir o grupo apropriado.</span><span class="sxs-lookup"><span data-stu-id="d0c15-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="d0c15-172">No painel de atribuir aplicativos, selecione **Okey**.</span><span class="sxs-lookup"><span data-stu-id="d0c15-172">In the Assign Apps pane, select **OK**.</span></span>

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