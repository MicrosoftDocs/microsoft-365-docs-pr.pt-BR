---
title: Adicionar blocos personalizados ao inicializador de aplicativos
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: fff65c7263e40bf376f53e5f150daea7a24ff55d
ms.sourcegitcommit: 256184cf731c1851b04a07dd7d59ecf020d02635
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131526"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="fcb47-103">Adicionar blocos personalizados ao inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fcb47-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="fcb47-p101">No Office 365, você pode acessar emails, calendários, documentos e aplicativos de forma fácil e rápida, usando o inicializador de aplicativos do Office 365 ([saiba mais](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Esses são os aplicativos que você obtém com o Office 365, bem como os aplicativos personalizados que são adicionados do [Repositório do SharePoint](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) ou do [Microsoft Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span><span class="sxs-lookup"><span data-stu-id="fcb47-p101">In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="fcb47-p102">Você pode adicionar blocos personalizados ao inicializador de aplicativos, que apontem para sites do SharePoint, sites externos, aplicativos herdados, e muito mais. O bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos, mas você pode fixá-lo junto aos aplicativos da guia **Página Inicial** e orientar os usuários a fazerem o mesmo. Isso facilita a localização de sites, aplicativos e recursos importantes para realizar o trabalho. No exemplo a seguir, o bloco personalizado Portal da Contoso serve para acessar o site de intranet do SharePoint da organização.</span><span class="sxs-lookup"><span data-stu-id="fcb47-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Inicializador de aplicativos do Office 365](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="fcb47-111">Adicionar um bloco personalizado ao inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fcb47-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="fcb47-112">No centro de administração, vá para a **guia Configurações e escolha o** > **Settings** **perfil da organização** .</span><span class="sxs-lookup"><span data-stu-id="fcb47-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="fcb47-113">Na guia **perfil da organização** , escolha **blocos personalizados do inicializador de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="fcb47-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="fcb47-114">Selecione **Adicionar um bloco personalizado**.</span><span class="sxs-lookup"><span data-stu-id="fcb47-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="fcb47-115">Insira o **Nome do bloco** para o novo bloco.</span><span class="sxs-lookup"><span data-stu-id="fcb47-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="fcb47-116">O nome será exibido no bloco.</span><span class="sxs-lookup"><span data-stu-id="fcb47-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="fcb47-117">Insira uma **URL do site** para o bloco.</span><span class="sxs-lookup"><span data-stu-id="fcb47-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="fcb47-118">Este é o local onde você deseja que seus usuários sigam quando selecionarem o bloco no inicializador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fcb47-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="fcb47-119">Use HTTPS na URL.</span><span class="sxs-lookup"><span data-stu-id="fcb47-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="fcb47-120">Dica: se você estiver criando um bloco para um site do SharePoint, navegue até esse site, copie a URL e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="fcb47-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="fcb47-121">A URL do site de equipe padrão tem a seguinte aparência:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="fcb47-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="fcb47-122">Insira uma **URL da imagem** para o bloco.</span><span class="sxs-lookup"><span data-stu-id="fcb47-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="fcb47-123">A imagem é exibida na página Meus Aplicativos e no inicializador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fcb47-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="fcb47-124">Dica: a imagem deve ser 60x60 pixels e estar disponível para todos em sua organização sem exigir autenticação.</span><span class="sxs-lookup"><span data-stu-id="fcb47-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="fcb47-125">Insira uma **Descrição** para o bloco.</span><span class="sxs-lookup"><span data-stu-id="fcb47-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="fcb47-126">Você verá isso quando selecionar o bloco na página meus aplicativos e selecionar detalhes do **aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="fcb47-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="fcb47-127">Selecione **salvar alterações** para criar o bloco personalizado.</span><span class="sxs-lookup"><span data-stu-id="fcb47-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="fcb47-128">Agora, o bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos para todas as pessoas.</span><span class="sxs-lookup"><span data-stu-id="fcb47-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="fcb47-129">Promover o bloco para o inicializador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fcb47-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="fcb47-130">Selecione o ícone do inicializador de aplicativos e selecione **todos os aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="fcb47-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="fcb47-131">Localize o novo bloco para o seu aplicativo, selecione as reticências e escolha **fixar no iniciador**.</span><span class="sxs-lookup"><span data-stu-id="fcb47-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="fcb47-p108">Se você não vir o bloco personalizado criado na etapa anterior, verifique se tem uma caixa de correio do Exchange Online atribuída e se você entrou em sua caixa de correio pelo menos uma vez. Estas etapas são necessárias para os blocos personalizados no Office 365.</span><span class="sxs-lookup"><span data-stu-id="fcb47-p108">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fcb47-134">Você e seus usuários devem realizar essas etapas para promover os blocos personalizados na página Meus Aplicativos para o inicializador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fcb47-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="fcb47-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="fcb47-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="fcb47-136">No centro de administração, vá para a guia<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">perfil da organização</a> **configurações** > de **configurações** > .</span><span class="sxs-lookup"><span data-stu-id="fcb47-136">In the admin center, go to the **Settings** > **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> tab.</span></span>
    
2. <span data-ttu-id="fcb47-137">Na página **perfil da organização** , ao lado de **Adicionar blocos personalizados para sua organização**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fcb47-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="fcb47-138">Atualize o **Nome do bloco**, a **URL**, a **Descrição** ou a **URL da imagem** do bloco personalizado (consulte a [Adicionar um bloco personalizado ao inicializador de aplicativos](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="fcb47-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="fcb47-139">Selecione **Atualizar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="fcb47-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="fcb47-140">Para excluir um bloco personalizado, da janela **blocos personalizados** , selecione o bloco, selecione **remover** > **exclusão**de bloco.</span><span class="sxs-lookup"><span data-stu-id="fcb47-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="fcb47-141">E agora?</span><span class="sxs-lookup"><span data-stu-id="fcb47-141">What's next?</span></span>

<span data-ttu-id="fcb47-p109">Além de adicionar blocos ao inicializador de aplicativos, você pode adicionar blocos à barra de navegação do Office 365 ([saiba mais](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Para personalizar a aparência do Office 365 para coincidir com a marca da sua organização, consulte [Personalizar o tema do Office 365](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="fcb47-p109">In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

