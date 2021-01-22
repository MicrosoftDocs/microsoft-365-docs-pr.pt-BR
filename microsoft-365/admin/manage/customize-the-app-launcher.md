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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Crie links rápidos para seu email, documentos, aplicativos, sites do SharePoint, sites externos e outros recursos adicionando blocos personalizados ao iniciador de aplicativos. '
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926229"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="fce41-103">Adicionar blocos personalizados ao inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fce41-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="fce41-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="fce41-104">The admin center is changing.</span></span> <span data-ttu-id="fce41-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="fce41-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="fce41-106">No Microsoft 365, você pode obter seus emails, calendários, documentos e aplicativos de forma rápida e fácil usando o iniciador de aplicativos ([saiba mais](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="fce41-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="fce41-107">Esses são os aplicativos que você pode obter com o Microsoft 365, bem como aplicativos personalizados que você adiciona do [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) ou [do Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)</span><span class="sxs-lookup"><span data-stu-id="fce41-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="fce41-p103">Você pode adicionar blocos personalizados ao inicializador de aplicativos, que apontem para sites do SharePoint, sites externos, aplicativos herdados, e muito mais. O bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos, mas você pode fixá-lo junto aos aplicativos da guia **Página Inicial** e orientar os usuários a fazerem o mesmo. Isso facilita a localização de sites, aplicativos e recursos importantes para realizar o trabalho. No exemplo a seguir, o bloco personalizado Portal da Contoso serve para acessar o site de intranet do SharePoint da organização.</span><span class="sxs-lookup"><span data-stu-id="fce41-p103">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Iniciador de aplicativos](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="fce41-113">Adicionar um bloco personalizado ao inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fce41-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="fce41-114">Entre no centro de administração como Administrador Global, acesse Configurações da Organização e escolha a  >  guia Perfil **da** Organização.</span><span class="sxs-lookup"><span data-stu-id="fce41-114">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="fce41-115">Na guia **Perfil da organização,** escolha **blocos personalizados do iniciador de aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="fce41-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="fce41-116">Selecione **Add a custom tile**.</span><span class="sxs-lookup"><span data-stu-id="fce41-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="fce41-117">Insira o **Nome do bloco** para o novo bloco.</span><span class="sxs-lookup"><span data-stu-id="fce41-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="fce41-118">O nome será exibido no bloco.</span><span class="sxs-lookup"><span data-stu-id="fce41-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="fce41-119">Insira uma **URL do site** para o tile.</span><span class="sxs-lookup"><span data-stu-id="fce41-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="fce41-120">Esse é o local para onde você deseja que os usuários acessem quando eles selecionarem o tile no iniciador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fce41-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="fce41-121">Use HTTPS na URL.</span><span class="sxs-lookup"><span data-stu-id="fce41-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="fce41-122">DICA: se você estiver criando um tile para um site do SharePoint, navegue até esse site, copie a URL e copie-a aqui.</span><span class="sxs-lookup"><span data-stu-id="fce41-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="fce41-123">A URL do seu site de equipe padrão tem esta aparência: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="fce41-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="fce41-124">Insira uma **URL da imagem** para o lado.</span><span class="sxs-lookup"><span data-stu-id="fce41-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="fce41-125">A imagem é exibida na página Meus Aplicativos e no inicializador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fce41-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="fce41-126">DICA: a imagem deve ter 60 x 60 pixels e estar disponível para todos em sua organização sem a necessidade de autenticação.</span><span class="sxs-lookup"><span data-stu-id="fce41-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="fce41-127">Insira uma **Descrição** para o bloco.</span><span class="sxs-lookup"><span data-stu-id="fce41-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="fce41-128">Você verá isso quando selecionar o tile na página Meus aplicativos e selecionar **detalhes do aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="fce41-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="fce41-129">Selecione **Salvar alterações** para criar oile personalizado.</span><span class="sxs-lookup"><span data-stu-id="fce41-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="fce41-130">Agora, o bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos para todas as pessoas.</span><span class="sxs-lookup"><span data-stu-id="fce41-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="fce41-131">Promover o tile para o Iniciador de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="fce41-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="fce41-132">Selecione o ícone do iniciador de aplicativos e selecione todos **os aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="fce41-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="fce41-133">Localize o novo tile para seu aplicativo, selecione as recepses e escolha **Fixar no iniciador.**</span><span class="sxs-lookup"><span data-stu-id="fce41-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="fce41-134">Se você não vir o bloco personalizado criado na etapa anterior, verifique se tem uma caixa de correio do Exchange Online atribuída e se você entrou em sua caixa de correio pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="fce41-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="fce41-135">Essas etapas são necessárias para blocos personalizados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fce41-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fce41-136">Você e seus usuários devem realizar essas etapas para promover os blocos personalizados na página Meus Aplicativos para o inicializador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fce41-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="fce41-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="fce41-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="fce41-138">No centro de administração, vá para a **guia Configurações** da Organização  >  **de Configurações**  >  **da** </a> Organização.</span><span class="sxs-lookup"><span data-stu-id="fce41-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="fce41-139">Na página **Perfil da** organização, ao lado de   **Adicionar blocos personalizados para sua organização,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fce41-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="fce41-140">Atualize o **Nome do bloco**, a **URL**, a **Descrição** ou a **URL da imagem** do bloco personalizado (consulte a [Adicionar um bloco personalizado ao inicializador de aplicativos](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="fce41-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="fce41-141">Selecione **Fechar** \> **Atualização.**</span><span class="sxs-lookup"><span data-stu-id="fce41-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="fce41-142">Para excluir um bloco personalizado, na janela **Blocos** personalizados, selecione o bloco, selecione **Remover exclusão de**  >  **bloco.**</span><span class="sxs-lookup"><span data-stu-id="fce41-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="fce41-143">O que vem a seguir?</span><span class="sxs-lookup"><span data-stu-id="fce41-143">What's next?</span></span>

<span data-ttu-id="fce41-144">Além de adicionar blocos ao iniciador de aplicativos, você pode adicionar blocos do iniciador de aplicativos à barra de navegação ([saiba mais](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span><span class="sxs-lookup"><span data-stu-id="fce41-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="fce41-145">Para personalizar a aparência do Microsoft 365 para corresponder à marca da sua organização, confira Personalizar o tema [do Microsoft 365.](../setup/customize-your-organization-theme.md)</span><span class="sxs-lookup"><span data-stu-id="fce41-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  
