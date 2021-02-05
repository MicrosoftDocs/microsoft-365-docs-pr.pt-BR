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
description: Saiba como usar os complementos centralizados para implantar os complementos para usuários e grupos em sua organização.
ms.openlocfilehash: 5366bd5be80559f23490aeb54f9417a189169e12
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114196"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="a05bf-103">Gerenciar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="a05bf-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a05bf-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="a05bf-104">The admin center is changing.</span></span> <span data-ttu-id="a05bf-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="a05bf-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="a05bf-106">Os complementos do Office ajudam a personalizar seus documentos e simplificar a maneira como você acessa informações na Web (confira Começar a usar o [seu complemento do Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="a05bf-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="a05bf-107">Depois que um administrador implanta os complementos para usuários em uma organização, o administrador pode ativar ou desativar os complementos, editar, excluir e gerenciar o acesso aos complementos.</span><span class="sxs-lookup"><span data-stu-id="a05bf-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="a05bf-108">Para obter mais informações sobre como instalar os complementos do centro de administração, consulte Implantar os [complementos no centro de administração.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="a05bf-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="a05bf-109">Estados de suplementos</span><span class="sxs-lookup"><span data-stu-id="a05bf-109">Add-in states</span></span>

<span data-ttu-id="a05bf-110">Um complemento pode estar no estado **On** ou **Off.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="a05bf-111">**State**</span><span class="sxs-lookup"><span data-stu-id="a05bf-111">**State**</span></span>|<span data-ttu-id="a05bf-112">**Como o estado ocorre**</span><span class="sxs-lookup"><span data-stu-id="a05bf-112">**How the state occurs**</span></span>|<span data-ttu-id="a05bf-113">**Impacto**</span><span class="sxs-lookup"><span data-stu-id="a05bf-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a05bf-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="a05bf-114">**Active**</span></span>  <br/> |<span data-ttu-id="a05bf-115">O administrador carregou o complemento e o atribuiu a usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="a05bf-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="a05bf-116">Os usuários e grupos atribuídos ao complemento o veem nos clientes relevantes.</span><span class="sxs-lookup"><span data-stu-id="a05bf-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="a05bf-117">**Desativado**</span><span class="sxs-lookup"><span data-stu-id="a05bf-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="a05bf-118">O administrador desativou o suplemento.</span><span class="sxs-lookup"><span data-stu-id="a05bf-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="a05bf-119">Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="a05bf-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="a05bf-120">Se o estado do complemento for alterado para Ativo, os usuários e grupos terão acesso a ele novamente.</span><span class="sxs-lookup"><span data-stu-id="a05bf-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="a05bf-121">**Excluído**</span><span class="sxs-lookup"><span data-stu-id="a05bf-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="a05bf-122">O administrador excluiu o suplemento.</span><span class="sxs-lookup"><span data-stu-id="a05bf-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="a05bf-123">Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="a05bf-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="a05bf-124">Considere a exclusão de um complemento se ninguém mais o estiver usando.</span><span class="sxs-lookup"><span data-stu-id="a05bf-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="a05bf-125">Por exemplo, a opção de desligar um complemento pode fazer sentido se um complemento for usado somente durante períodos específicos do ano.</span><span class="sxs-lookup"><span data-stu-id="a05bf-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="a05bf-126">Excluir um complemento</span><span class="sxs-lookup"><span data-stu-id="a05bf-126">Delete an add-in</span></span>

<span data-ttu-id="a05bf-127">Você também pode excluir um complemento que foi implantado.</span><span class="sxs-lookup"><span data-stu-id="a05bf-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="a05bf-128">No centro de administração, vá para a página **Serviços**&  >  **configurações.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="a05bf-129">O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados.</span><span class="sxs-lookup"><span data-stu-id="a05bf-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="a05bf-130">Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para **Configurações**  >  **Integradas de aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a05bf-131">Na parte superior da página **Aplicativos integrados,** escolha **Os Complementos.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="a05bf-132">Selecione o complemento implantado.</span><span class="sxs-lookup"><span data-stu-id="a05bf-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="a05bf-133">Clique em **Excluir Complemento.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="a05bf-134">Remova o botão Desaixar no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="a05bf-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="a05bf-135">Valide suas seleções e escolha **Remover o complemento.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="a05bf-136">Editar o acesso de um complemento</span><span class="sxs-lookup"><span data-stu-id="a05bf-136">Edit add-in access</span></span>

<span data-ttu-id="a05bf-137">Após a implantação, os administradores também podem gerenciar o acesso do usuário aos complementos.</span><span class="sxs-lookup"><span data-stu-id="a05bf-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="a05bf-138">No centro de administração, vá para a página **Serviços**&  >  **configurações.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="a05bf-139">O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados.</span><span class="sxs-lookup"><span data-stu-id="a05bf-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="a05bf-140">Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para **Configurações**  >  **Integradas aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="a05bf-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a05bf-141">Na parte superior da página **Aplicativos integrados,** escolha **Os Complementos.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="a05bf-142">Selecione o complemento implantado.</span><span class="sxs-lookup"><span data-stu-id="a05bf-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="a05bf-143">Clique em **Editar** em **Quem tem Acesso.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="a05bf-144">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="a05bf-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="a05bf-145">Impedir downloads de complementos ao desligar a Office Store em todos os clientes (exceto o Outlook)</span><span class="sxs-lookup"><span data-stu-id="a05bf-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="a05bf-146">A instalação de um complemento do Outlook é gerenciada por [um processo diferente.](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a05bf-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="a05bf-147">Como organização, você pode querer impedir o download de novos complementos do Office da Office Store.</span><span class="sxs-lookup"><span data-stu-id="a05bf-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="a05bf-148">Isso pode ser usado em conjunto com a Implantação Centralizada para garantir que somente os complementos aprovados pela organização sejam implantados para usuários dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a05bf-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="a05bf-149">**Para desativar a aquisição de um complemento**</span><span class="sxs-lookup"><span data-stu-id="a05bf-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="a05bf-150">No centro de administração, vá para a página **Configurações** \> [Serviços&amp; suplementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="a05bf-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="a05bf-151">O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados.</span><span class="sxs-lookup"><span data-stu-id="a05bf-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="a05bf-152">Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para **Configurações**  >  **Integradas aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="a05bf-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a05bf-153">Na parte superior da página **Aplicativos integrados,** escolha **Os Complementos.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="a05bf-154">Selecione **aplicativos e serviços de propriedade do usuário.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="a05bf-155">Limpe a opção para permitir que os usuários acessem a Office Store.</span><span class="sxs-lookup"><span data-stu-id="a05bf-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="a05bf-156">Isso impedirá que todos os usuários adquirem os seguintes complementos da loja.</span><span class="sxs-lookup"><span data-stu-id="a05bf-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="a05bf-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span><span class="sxs-lookup"><span data-stu-id="a05bf-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="a05bf-158">Windows</span><span class="sxs-lookup"><span data-stu-id="a05bf-158">Windows</span></span>
    
  - <span data-ttu-id="a05bf-159">Mac</span><span class="sxs-lookup"><span data-stu-id="a05bf-159">Mac</span></span>
    
  - <span data-ttu-id="a05bf-160">Office</span><span class="sxs-lookup"><span data-stu-id="a05bf-160">Office</span></span>
    
    
- <span data-ttu-id="a05bf-161">Aquisições a partir do **AppSource**</span><span class="sxs-lookup"><span data-stu-id="a05bf-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="a05bf-162">Add-ins within Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a05bf-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="a05bf-163">Um usuário que tentar acessar a loja verá a seguinte mensagem: Desculpe, o **Microsoft 365** foi configurado para impedir a aquisição individual de complementos da Office Store.</span><span class="sxs-lookup"><span data-stu-id="a05bf-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="a05bf-164">O suporte para desligar a Office Store está disponível nas seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="a05bf-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="a05bf-165">Windows: 16.0.9001 - Disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="a05bf-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="a05bf-166">Mac: 16.10.18011401 - Disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="a05bf-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="a05bf-167">iOS: 2.9.18010804 - Disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="a05bf-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="a05bf-168">A Web - Disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="a05bf-168">The web - Currently available.</span></span>
    
<span data-ttu-id="a05bf-169">Isso não impede que um administrador use a Implantação Centralizada para atribuir um complemento da Office Store.</span><span class="sxs-lookup"><span data-stu-id="a05bf-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="a05bf-170">Para impedir que um usuário entre com uma conta da Microsoft, você pode restringir o logon para usar somente a conta organizacional.</span><span class="sxs-lookup"><span data-stu-id="a05bf-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="a05bf-171">Para saber mais, confira [Identidade, autenticação e autorização no Office 2016.](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a05bf-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="a05bf-172">Impedir que os usuários acessem a Office Store também os impedirá de [fazer sideload de complementos](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)do Office para teste.</span><span class="sxs-lookup"><span data-stu-id="a05bf-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="a05bf-173">Mais informações sobre a experiência do usuário final com os complementos</span><span class="sxs-lookup"><span data-stu-id="a05bf-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="a05bf-174">Depois de implantar um add-in, os usuários finais podem começar a [usá-lo](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)em seus aplicativos do Office (confira Começar a usar o seu Complemento do Office).</span><span class="sxs-lookup"><span data-stu-id="a05bf-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="a05bf-175">O complemento aparece em todas as plataformas compatíveis com o add-in.</span><span class="sxs-lookup"><span data-stu-id="a05bf-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="a05bf-176">Se o complemento for compatível com comandos de complemento, os comandos aparecerão na faixa de opções do Office.</span><span class="sxs-lookup"><span data-stu-id="a05bf-176">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="a05bf-177">No exemplo a seguir, o comando **Pesquisar Citação** aparece **para** o complemento Citações.</span><span class="sxs-lookup"><span data-stu-id="a05bf-177">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Faixa de opções do Office com Citações de Pesquisa](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="a05bf-179">Se o complemento implantado não dá suporte a comandos de add-in ou se você quiser exibir todos os complementos implantados, poderá exibi-los por meio de Meus **Complementos.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="a05bf-180">No Word 2016, Excel 2016 ou PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="a05bf-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="a05bf-181">Selecione **Inserir \> Meus Complementos.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="a05bf-182">Selecione a **guia Administração** Gerenciada na janela Desem</span><span class="sxs-lookup"><span data-stu-id="a05bf-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="a05bf-183">Clique duas vezes no complemento implantado anteriormente (neste exemplo, **Citações** ).</span><span class="sxs-lookup"><span data-stu-id="a05bf-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="a05bf-184">![Guia Administração Gerenciada da página Desem que o Office Add-ins](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="a05bf-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="a05bf-185">No Outlook</span><span class="sxs-lookup"><span data-stu-id="a05bf-185">In Outlook</span></span>

1. <span data-ttu-id="a05bf-186">Na faixa **de opções Página** Home, selecione Obter **Complementos.**</span><span class="sxs-lookup"><span data-stu-id="a05bf-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="a05bf-187">![Botão Armazenar no Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="a05bf-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="a05bf-188">Selecione **Admin-managed** na nav esquerda.</span><span class="sxs-lookup"><span data-stu-id="a05bf-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="a05bf-189">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="a05bf-189">Learn more</span></span>

[<span data-ttu-id="a05bf-190">Implantar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="a05bf-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="a05bf-191">Saiba mais sobre como criar e [criar Os Complementos do Office.](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)</span><span class="sxs-lookup"><span data-stu-id="a05bf-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="a05bf-192">[Use cmdlets do PowerShell de implantação centralizada para gerenciar os complementos.](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="a05bf-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="a05bf-193">Solução de problemas: o usuário não está vendo os complementos</span><span class="sxs-lookup"><span data-stu-id="a05bf-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="a05bf-194">Menores e aquisição de complementos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a05bf-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
