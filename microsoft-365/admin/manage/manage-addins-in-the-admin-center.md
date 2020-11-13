---
title: Gerenciar suplementos no centro de administração
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Saiba como usar suplementos centralizados para implantar suplementos para usuários e grupos em sua organização.
ms.openlocfilehash: 5521b01e059ca8ae4a97ecb094f9aa1198263701
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071472"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="1e5e9-103">Gerenciar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="1e5e9-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1e5e9-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-104">The admin center is changing.</span></span> <span data-ttu-id="1e5e9-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="1e5e9-106">Os suplementos do Office ajudam você a personalizar seus documentos e simplificar a forma como você acessa as informações na Web (Confira [começar a usar o suplemento do Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="1e5e9-107">Depois que um administrador implanta suplementos para usuários em uma organização, o administrador pode ativar ou desativar os suplementos, editar, excluir e gerenciar o acesso aos suplementos.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="1e5e9-108">Para obter mais informações sobre como instalar suplementos no centro de administração, consulte [implantar suplementos no centro de administração](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="1e5e9-109">Estados de suplementos</span><span class="sxs-lookup"><span data-stu-id="1e5e9-109">Add-in states</span></span>

<span data-ttu-id="1e5e9-110">Um suplemento pode estar no estado **ativado** ou **desativado** .</span><span class="sxs-lookup"><span data-stu-id="1e5e9-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="1e5e9-111">**State**</span><span class="sxs-lookup"><span data-stu-id="1e5e9-111">**State**</span></span>|<span data-ttu-id="1e5e9-112">**Como o estado ocorre**</span><span class="sxs-lookup"><span data-stu-id="1e5e9-112">**How the state occurs**</span></span>|<span data-ttu-id="1e5e9-113">**Impacto**</span><span class="sxs-lookup"><span data-stu-id="1e5e9-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1e5e9-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="1e5e9-114">**Active**</span></span>  <br/> |<span data-ttu-id="1e5e9-115">O administrador carregou o suplemento e o atribuiu a usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="1e5e9-116">Os usuários e grupos atribuídos ao suplemento o vêem nos clientes relevantes.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="1e5e9-117">**Desativado**</span><span class="sxs-lookup"><span data-stu-id="1e5e9-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="1e5e9-118">O administrador desativou o suplemento.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="1e5e9-119">Os usuários e grupos atribuídos ao suplemento não têm mais acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="1e5e9-120">Se o estado do suplemento for alterado para ativo, os usuários e grupos terão acesso a ele novamente.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="1e5e9-121">**Excluído**</span><span class="sxs-lookup"><span data-stu-id="1e5e9-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="1e5e9-122">O administrador excluiu o suplemento.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="1e5e9-123">Os usuários e grupos atribuídos ao suplemento não têm mais acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="1e5e9-124">Considere a possibilidade de excluir um suplemento se ninguém estiver usando mais um.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="1e5e9-125">Por exemplo, a desativação de um suplemento pode fazer sentido se um suplemento é usado somente durante horários específicos do ano.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="1e5e9-126">Excluir um suplemento</span><span class="sxs-lookup"><span data-stu-id="1e5e9-126">Delete an add-in</span></span>

<span data-ttu-id="1e5e9-127">Você também pode excluir um suplemento implantado.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="1e5e9-128">No centro de administração, vá para a página **configurações** de  >  **&** de suplementos.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="1e5e9-129">O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="1e5e9-130">Se você não vir as etapas acima, vá para seção implantação centralizada em aplicativos de **configurações**  >  **integradas**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="1e5e9-131">Na parte superior da página **aplicativos integrados** , escolha **suplementos**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="1e5e9-132">Selecione o suplemento implantado.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="1e5e9-133">Clique em **excluir suplemento**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="1e5e9-134">Remova o botão do suplemento no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="1e5e9-135">Valide suas seleções e escolha **remover suplemento**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="1e5e9-136">Editar acesso de suplemento</span><span class="sxs-lookup"><span data-stu-id="1e5e9-136">Edit add-in access</span></span>

<span data-ttu-id="1e5e9-137">Pós-implantação, os administradores também podem gerenciar o acesso do usuário a suplementos.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="1e5e9-138">No centro de administração, vá para a página **configurações** de  >  **&** de suplementos.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="1e5e9-139">O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="1e5e9-140">Se você não vir as etapas acima, vá para seção implantação centralizada em aplicativos de **configurações**  >  **integradas**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="1e5e9-141">Na parte superior da página **aplicativos integrados** , escolha **suplementos**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="1e5e9-142">Selecione o suplemento implantado.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="1e5e9-143">Clique em **Editar** em **quem tem acesso**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="1e5e9-144">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="1e5e9-145">Impedir downloads de suplementos desativando a Office Store em todos os clientes (exceto Outlook)</span><span class="sxs-lookup"><span data-stu-id="1e5e9-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="1e5e9-146">A instalação do suplemento do Outlook é gerenciada por um [processo diferente](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="1e5e9-147">Como uma organização, talvez você queira impedir o download de novos suplementos do Office da Office Store.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="1e5e9-148">Isso pode ser usado em conjunto com a implantação centralizada para garantir que apenas os suplementos aprovados pela organização sejam implantados para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="1e5e9-149">**Para desativar a aquisição de suplementos**</span><span class="sxs-lookup"><span data-stu-id="1e5e9-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="1e5e9-150">No centro de administração, vá para a página **Configurações** \> [Serviços&amp; suplementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="1e5e9-151">O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="1e5e9-152">Se você não vir as etapas acima, vá para seção implantação centralizada em aplicativos de **configurações**  >  **integradas**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="1e5e9-153">Na parte superior da página **aplicativos integrados** , escolha **suplementos**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="1e5e9-154">Selecione **aplicativos e serviços de Propriedade do usuário**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="1e5e9-155">Desmarque a opção para permitir que os usuários acessem a Office Store.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="1e5e9-156">Isso impedirá que todos os usuários adquiram os seguintes suplementos do repositório.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="1e5e9-157">Suplementos para Word, Excel e PowerPoint 2016 de:</span><span class="sxs-lookup"><span data-stu-id="1e5e9-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="1e5e9-158">Windows</span><span class="sxs-lookup"><span data-stu-id="1e5e9-158">Windows</span></span>
    
  - <span data-ttu-id="1e5e9-159">Mac</span><span class="sxs-lookup"><span data-stu-id="1e5e9-159">Mac</span></span>
    
  - <span data-ttu-id="1e5e9-160">Office</span><span class="sxs-lookup"><span data-stu-id="1e5e9-160">Office</span></span>
    
    
- <span data-ttu-id="1e5e9-161">Aquisições começando no **AppSource**</span><span class="sxs-lookup"><span data-stu-id="1e5e9-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="1e5e9-162">Suplementos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e5e9-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="1e5e9-163">Um usuário que tentar acessar o repositório verá a seguinte mensagem: o **Microsoft 365 foi configurado para impedir a aquisição individual de suplementos da Office Store.**</span><span class="sxs-lookup"><span data-stu-id="1e5e9-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="1e5e9-164">O suporte à desativação da Office Store está disponível nas seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="1e5e9-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="1e5e9-165">Windows: 16.0.9001-disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="1e5e9-166">Mac: 16.10.18011401-disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="1e5e9-167">iOS: 2.9.18010804-disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="1e5e9-168">A Web-disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-168">The web - Currently available.</span></span>
    
<span data-ttu-id="1e5e9-169">Isso não impede que um administrador use a implantação centralizada para atribuir um suplemento da Office Store.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="1e5e9-170">Para impedir que um usuário entre com uma conta da Microsoft, você pode restringir o logon para usar apenas a conta organizacional.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="1e5e9-171">Para obter mais informações, consulte [identidade, autenticação e autorização no Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="1e5e9-172">Impedir que os usuários acessem a Office Store também os impedirá de [Sideload dos suplementos do Office para teste](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="1e5e9-173">Saiba mais sobre a experiência do usuário final com suplementos</span><span class="sxs-lookup"><span data-stu-id="1e5e9-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="1e5e9-174">Depois de implantar um suplemento, os usuários finais podem começar a usá-lo em seus aplicativos do Office (Confira [começar a usar o suplemento do Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="1e5e9-175">O suplemento aparece em todas as plataformas compatíveis com o suplemento.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="1e5e9-176">Se o suplemento suportar comandos de suplemento, os comandos serão exibidos na faixa de opções do Office.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-176">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="1e5e9-177">No exemplo a seguir, a **citação de pesquisa** de comando aparece para o suplemento de **citações** .</span><span class="sxs-lookup"><span data-stu-id="1e5e9-177">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Faixa de opções do Office com citações de pesquisa](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="1e5e9-179">Se o suplemento implantado não oferecer suporte a comandos de suplemento ou se você quiser exibir todos os suplementos implantados, poderá exibi-los por meio **de meus** suplementos.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="1e5e9-180">No Word 2016, no Excel 2016 ou no PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="1e5e9-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="1e5e9-181">Selecione **Inserir \> meus** suplementos.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="1e5e9-182">Selecione a guia **Administração gerenciada** na janela suplementos do Office.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="1e5e9-183">Clique duas vezes no suplemento que você implantou anteriormente (neste exemplo, **citações** ).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="1e5e9-184">![Guia Administração gerenciada da página de suplementos do Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="1e5e9-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="1e5e9-185">No Outlook</span><span class="sxs-lookup"><span data-stu-id="1e5e9-185">In Outlook</span></span>

1. <span data-ttu-id="1e5e9-186">Na faixa de opções **página inicial** , selecione **obter suplementos**.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="1e5e9-187">![Botão armazenar no Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="1e5e9-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="1e5e9-188">Selecione **Administração gerenciada** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="1e5e9-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="1e5e9-189">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="1e5e9-189">Learn more</span></span>

[<span data-ttu-id="1e5e9-190">Implantar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="1e5e9-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="1e5e9-191">Saiba mais sobre a criação e [a criação de suplementos do Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="1e5e9-192">[Use cmdlets do PowerShell de implantação centralizada para gerenciar suplementos](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span><span class="sxs-lookup"><span data-stu-id="1e5e9-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="1e5e9-193">Solução de problemas: o usuário não está vendo suplementos</span><span class="sxs-lookup"><span data-stu-id="1e5e9-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="1e5e9-194">Menores e adquirir suplementos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="1e5e9-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
