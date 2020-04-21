---
title: Adicionar blocos personalizados ao inicializador de aplicativos
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Crie links rápidos para seus emails, documentos, aplicativos, sites do SharePoint, sites externos e outros recursos adicionando blocos personalizados ao inicializador de aplicativos. '
ms.openlocfilehash: 705d45a2c26d3bd5e2d45d6d8f5a7c998c449f8d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628191"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="13697-103">Adicionar blocos personalizados ao inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="13697-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="13697-104">No Microsoft 365, você pode acessar seus emails, calendários, documentos e aplicativos com rapidez e facilidade usando o inicializador de aplicativos ([saiba mais](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)).</span><span class="sxs-lookup"><span data-stu-id="13697-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)).</span></span> <span data-ttu-id="13697-105">Estes são os aplicativos que você obtém com o Microsoft 365, bem como aplicativos personalizados que você adiciona do [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) ou [do Azure ad](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span><span class="sxs-lookup"><span data-stu-id="13697-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="13697-p102">Você pode adicionar blocos personalizados ao inicializador de aplicativos, que apontem para sites do SharePoint, sites externos, aplicativos herdados, e muito mais. O bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos, mas você pode fixá-lo junto aos aplicativos da guia **Página Inicial** e orientar os usuários a fazerem o mesmo. Isso facilita a localização de sites, aplicativos e recursos importantes para realizar o trabalho. No exemplo a seguir, o bloco personalizado Portal da Contoso serve para acessar o site de intranet do SharePoint da organização.</span><span class="sxs-lookup"><span data-stu-id="13697-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Inicializador de aplicativos](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="13697-111">Adicionar um bloco personalizado ao inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="13697-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="13697-112">No centro de administração, vá para a **guia Configurações e escolha o** > **Settings** **perfil da organização** .</span><span class="sxs-lookup"><span data-stu-id="13697-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="13697-113">Na guia **perfil da organização** , escolha **blocos personalizados do inicializador de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="13697-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="13697-114">Selecione **Adicionar um bloco personalizado**.</span><span class="sxs-lookup"><span data-stu-id="13697-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="13697-115">Insira o **Nome do bloco** para o novo bloco.</span><span class="sxs-lookup"><span data-stu-id="13697-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="13697-116">O nome será exibido no bloco.</span><span class="sxs-lookup"><span data-stu-id="13697-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="13697-117">Insira uma **URL do site** para o bloco.</span><span class="sxs-lookup"><span data-stu-id="13697-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="13697-118">Este é o local onde você deseja que seus usuários sigam quando selecionarem o bloco no inicializador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="13697-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="13697-119">Use HTTPS na URL.</span><span class="sxs-lookup"><span data-stu-id="13697-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="13697-120">Dica: se você estiver criando um bloco para um site do SharePoint, navegue até esse site, copie a URL e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="13697-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="13697-121">A URL do site de equipe padrão tem a seguinte aparência:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="13697-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="13697-122">Insira uma **URL da imagem** para o bloco.</span><span class="sxs-lookup"><span data-stu-id="13697-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="13697-123">A imagem é exibida na página Meus Aplicativos e no inicializador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="13697-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="13697-124">Dica: a imagem deve ser 60x60 pixels e estar disponível para todos em sua organização sem exigir autenticação.</span><span class="sxs-lookup"><span data-stu-id="13697-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="13697-125">Insira uma **Descrição** para o bloco.</span><span class="sxs-lookup"><span data-stu-id="13697-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="13697-126">Você verá isso quando selecionar o bloco na página meus aplicativos e selecionar detalhes do **aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="13697-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="13697-127">Selecione **salvar alterações** para criar o bloco personalizado.</span><span class="sxs-lookup"><span data-stu-id="13697-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="13697-128">Agora, o bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos para todas as pessoas.</span><span class="sxs-lookup"><span data-stu-id="13697-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="13697-129">Promover o bloco para o inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="13697-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="13697-130">Selecione o ícone do inicializador de aplicativos e selecione **todos os aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="13697-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="13697-131">Localize o novo bloco para o seu aplicativo, selecione as reticências e escolha **fixar no iniciador**.</span><span class="sxs-lookup"><span data-stu-id="13697-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="13697-132">Se você não vir o bloco personalizado criado na etapa anterior, verifique se tem uma caixa de correio do Exchange Online atribuída e se você entrou em sua caixa de correio pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="13697-132">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="13697-133">Estas etapas são necessárias para blocos personalizados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13697-133">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="13697-134">Você e seus usuários devem realizar essas etapas para promover os blocos personalizados na página Meus Aplicativos para o inicializador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="13697-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="13697-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="13697-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="13697-136">No centro de administração, vá para a guia<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">perfil da organização</a> **configurações** > de **configurações** > .</span><span class="sxs-lookup"><span data-stu-id="13697-136">In the admin center, go to the **Settings** > **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> tab.</span></span>
    
2. <span data-ttu-id="13697-137">Na página **perfil da organização** , ao lado de **Adicionar blocos personalizados para sua organização**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="13697-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="13697-138">Atualize o **Nome do bloco**, a **URL**, a **Descrição** ou a **URL da imagem** do bloco personalizado (consulte a [Adicionar um bloco personalizado ao inicializador de aplicativos](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="13697-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="13697-139">Selecione **Atualizar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="13697-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="13697-140">Para excluir um bloco personalizado, da janela **blocos personalizados** , selecione o bloco, selecione **remover** > **exclusão**de bloco.</span><span class="sxs-lookup"><span data-stu-id="13697-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="13697-141">E agora?</span><span class="sxs-lookup"><span data-stu-id="13697-141">What's next?</span></span>

<span data-ttu-id="13697-142">Além de adicionar blocos ao inicializador de aplicativos, você pode adicionar blocos de inicializador de aplicativos à barra de navegação ([saiba mais](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)).</span><span class="sxs-lookup"><span data-stu-id="13697-142">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)).</span></span> <span data-ttu-id="13697-143">Para personalizar a aparência do Microsoft 365 para corresponder à marca da sua organização, consulte [Customize The Microsoft 365 Theme](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="13697-143">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

