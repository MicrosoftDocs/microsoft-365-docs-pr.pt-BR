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
ms.openlocfilehash: b6ae4deed1566492574e30cf8cb66a750c9858c8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470626"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="1ce5a-103">Adicionar blocos personalizados ao inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1ce5a-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="1ce5a-104">No Microsoft 365, você pode chegar rapidamente e facilmente aos seus emails, calendários, documentos e aplicativos usando o iniciador de aplicativos ([saiba mais](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="1ce5a-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="1ce5a-105">Esses são os aplicativos que você tem com o Microsoft 365, bem como aplicativos personalizados que você adiciona da Loja do [SharePoint](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) ou [do Azure AD](/previous-versions/office/office-365-api/).</span><span class="sxs-lookup"><span data-stu-id="1ce5a-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="1ce5a-p102">Você pode adicionar blocos personalizados ao inicializador de aplicativos, que apontem para sites do SharePoint, sites externos, aplicativos herdados, e muito mais. O bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos, mas você pode fixá-lo junto aos aplicativos da guia **Página Inicial** e orientar os usuários a fazerem o mesmo. Isso facilita a localização de sites, aplicativos e recursos importantes para realizar o trabalho. No exemplo a seguir, o bloco personalizado Portal da Contoso serve para acessar o site de intranet do SharePoint da organização.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Launcher de aplicativos](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="1ce5a-111">Adicionar um bloco personalizado ao inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1ce5a-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="1ce5a-112">Entre no centro de administração como Administrador Global, acesse **Configurações** da Organização Configurações e escolha a  >  guia **Perfil da** Organização.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="1ce5a-113">Na guia **Perfil da** Organização, escolha **Blocos personalizados do iniciador de aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="1ce5a-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="1ce5a-114">Selecione **Adicionar um azulejo personalizado.**</span><span class="sxs-lookup"><span data-stu-id="1ce5a-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="1ce5a-115">Insira o **Nome do bloco** para o novo bloco.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="1ce5a-116">O nome será exibido no bloco.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="1ce5a-117">Insira uma **URL do site** para o azulejo.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="1ce5a-118">Este é o local onde você deseja que seus usuários acessem quando eles selecionam o telha no launcher do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="1ce5a-119">Use HTTPS na URL.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="1ce5a-120">DICA: Se você estiver criando um azulejo para um site do SharePoint, navegue até esse site, copie a URL e a colará aqui.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="1ce5a-121">A URL do site de equipe padrão tem esta aparência: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="1ce5a-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="1ce5a-122">Insira uma **URL da imagem** do azulejo.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="1ce5a-123">A imagem é exibida na página Meus Aplicativos e no inicializador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="1ce5a-124">DICA: a imagem deve ter 60 x 60 pixels e estar disponível para todos na sua organização sem a necessidade de autenticação.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="1ce5a-125">Insira uma **Descrição** para o bloco.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="1ce5a-126">Você vê isso quando seleciona o azulejo na página Meus aplicativos e seleciona **Detalhes do aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="1ce5a-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="1ce5a-127">Selecione **Salvar alterações** para criar o azulejo personalizado.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="1ce5a-128">Agora, o bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos para todas as pessoas.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="1ce5a-129">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="1ce5a-129">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="1ce5a-130">No centro de administração, vá para a guia **Configurações** da Organização  >  **Configurações**  >  **Perfil da** </a> organização.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-130">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="1ce5a-131">Na página **Perfil da** Organização, ao lado de   **Adicionar blocos personalizados para sua** organização, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-131">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="1ce5a-132">Atualize o **Nome do bloco**, a **URL**, a **Descrição** ou a **URL da imagem** do bloco personalizado (consulte a [Adicionar um bloco personalizado ao inicializador de aplicativos](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="1ce5a-132">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="1ce5a-133">Selecione **Atualizar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1ce5a-133">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="1ce5a-134">Para excluir um bloco personalizado, na janela **Blocos** personalizados, selecione o bloco, selecione **Remover excluir bloco**  >  .</span><span class="sxs-lookup"><span data-stu-id="1ce5a-134">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="1ce5a-135">O que vem a seguir?</span><span class="sxs-lookup"><span data-stu-id="1ce5a-135">What's next?</span></span>

<span data-ttu-id="1ce5a-136">Além de adicionar blocos ao launcher de aplicativos, você pode adicionar blocos do launcher de aplicativo à barra de navegação ([saiba mais](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span><span class="sxs-lookup"><span data-stu-id="1ce5a-136">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="1ce5a-137">Para personalizar a aparência do Microsoft 365 para corresponder à marca da sua organização, consulte Personalizar o [tema do Microsoft 365](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="1ce5a-137">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
