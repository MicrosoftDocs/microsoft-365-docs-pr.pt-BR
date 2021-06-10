---
title: Gerenciar suplementos no centro de administração
f1.keywords:
- NOCSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Saiba mais sobre como usar os complementos centralizados para implantar os complementos para usuários e grupos em sua organização.
ms.openlocfilehash: d678755b28daea1578ce2a5d2e387492cf32d368
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636053"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="1b7a7-103">Gerenciar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="1b7a7-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="1b7a7-104">Office os complementos ajudam você a personalizar seus documentos e a simplificar a maneira como você acessa informações na Web (consulte [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="1b7a7-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="1b7a7-105">Depois que um administrador implanta os complementos para usuários em uma organização, o administrador pode desativar ou ativar os complementos, editar, excluir e gerenciar o acesso aos complementos.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="1b7a7-106">Para obter mais informações sobre como instalar os complementos do centro de administração, consulte [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="1b7a7-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="1b7a7-107">Estados de complementos</span><span class="sxs-lookup"><span data-stu-id="1b7a7-107">Add-in states</span></span>

<span data-ttu-id="1b7a7-108">Um complemento pode estar no estado **On** ou **Off.**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
| <span data-ttu-id="1b7a7-109">Estado</span><span class="sxs-lookup"><span data-stu-id="1b7a7-109">State</span></span> | <span data-ttu-id="1b7a7-110">Como o estado ocorre</span><span class="sxs-lookup"><span data-stu-id="1b7a7-110">How the state occurs</span></span> | <span data-ttu-id="1b7a7-111">Impacto</span><span class="sxs-lookup"><span data-stu-id="1b7a7-111">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="1b7a7-112">**Ativo**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-112">**Active**</span></span>  <br/> |<span data-ttu-id="1b7a7-113">O administrador carregou o complemento e o atribuiu a usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="1b7a7-114">Os usuários e grupos atribuídos ao complemento o veem nos clientes relevantes.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="1b7a7-115">**Desativado**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="1b7a7-116">O administrador desativou o suplemento.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="1b7a7-117">Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="1b7a7-118">Se o estado do add-in for alterado para Ativo, os usuários e grupos terão acesso a ele novamente.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="1b7a7-119">**Excluído**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="1b7a7-120">O administrador excluiu o suplemento.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="1b7a7-121">Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="1b7a7-122">Considere a exclusão de um complemento se ninguém o estiver usando mais.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="1b7a7-123">Por exemplo, desligar um complemento pode fazer sentido se um add-in for usado somente durante períodos específicos do ano.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="1b7a7-124">Excluir um complemento</span><span class="sxs-lookup"><span data-stu-id="1b7a7-124">Delete an add-in</span></span>

<span data-ttu-id="1b7a7-125">Você também pode excluir um complemento que foi implantado.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="1b7a7-126">No centro de administração, vá para **a** página Configurações  >  **Serviços & de complementos.**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1b7a7-127">O centro de administração está sendo atualizado para a experiência de implantação com Aplicativos Integrados.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="1b7a7-128">Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para Configurações  >  **aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="1b7a7-129">Na parte superior da página **Aplicativos integrados,** escolha **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="1b7a7-130">Selecione o complemento implantado.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="1b7a7-131">Clique em **Excluir Add-In**.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="1b7a7-132">Remova o botão Adicionar no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-132">Remove the Add-in button on the bottom-right corner.</span></span>

4. <span data-ttu-id="1b7a7-133">Valide suas seleções e escolha **Remover complemento**.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="1b7a7-134">Editar acesso ao complemento</span><span class="sxs-lookup"><span data-stu-id="1b7a7-134">Edit add-in access</span></span>

<span data-ttu-id="1b7a7-135">Após a implantação, os administradores também podem gerenciar o acesso do usuário aos complementos.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="1b7a7-136">No centro de administração, vá para **a** página Configurações  >  **Serviços & de complementos.**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1b7a7-137">O centro de administração está sendo atualizado para a experiência de implantação com Aplicativos Integrados.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="1b7a7-138">Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para Configurações  >  **aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="1b7a7-139">Na parte superior da página **Aplicativos integrados,** escolha **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="1b7a7-140">Selecione o complemento implantado.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="1b7a7-141">Clique em **Editar** em **Who tem Access**.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="1b7a7-142">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="1b7a7-143">Impedir downloads de complementos ao desligar o Office Store em todos os clientes (exceto Outlook)</span><span class="sxs-lookup"><span data-stu-id="1b7a7-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="1b7a7-144">Outlook instalação do add-in é gerenciada por um [processo diferente.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="1b7a7-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="1b7a7-145">Como uma organização, você pode querer impedir o download de novos Office de Office Store.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="1b7a7-146">Isso pode ser usado em conjunto com a Implantação Centralizada para garantir que apenas os complementos aprovados pela organização sejam implantados para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="1b7a7-147">**Para desativar a aquisição de um complemento**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="1b7a7-148">No centro de administração, vá para a página **Configurações** \> [Serviços&amp; suplementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="1b7a7-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1b7a7-149">O centro de administração está sendo atualizado para a experiência de implantação com Aplicativos Integrados.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-149">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="1b7a7-150">Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para Configurações  >  **aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="1b7a7-151">Na parte superior da página **Aplicativos integrados,** escolha **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="1b7a7-152">Selecione **Aplicativos e serviços de propriedade do usuário**.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="1b7a7-153">Desmarque a opção de permitir que os usuários acessem a Office Store.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-153">Clear the option to let users access the Office store.</span></span>

    <span data-ttu-id="1b7a7-154">Isso impedirá que todos os usuários adquiram os seguintes complementos da loja.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
      
    - <span data-ttu-id="1b7a7-155">Os complementos para Word, Excel e PowerPoint 2016 de:</span><span class="sxs-lookup"><span data-stu-id="1b7a7-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
        
      - <span data-ttu-id="1b7a7-156">Windows</span><span class="sxs-lookup"><span data-stu-id="1b7a7-156">Windows</span></span>
      - <span data-ttu-id="1b7a7-157">Mac</span><span class="sxs-lookup"><span data-stu-id="1b7a7-157">Mac</span></span>
      - <span data-ttu-id="1b7a7-158">Office</span><span class="sxs-lookup"><span data-stu-id="1b7a7-158">Office</span></span>
        
        
    - <span data-ttu-id="1b7a7-159">Aquisições começando no **AppSource**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-159">Acquisitions starting within **AppSource**</span></span>
        
    - <span data-ttu-id="1b7a7-160">Os complementos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1b7a7-160">Add-ins within Microsoft 365</span></span>
        
    <span data-ttu-id="1b7a7-161">Um usuário que tentar acessar o armazenamento verá a seguinte mensagem: Desculpe, Microsoft 365 foi configurada para impedir a aquisição individual de Office **Desempregos da Loja.**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="1b7a7-162">O suporte para desligar o Office Store está disponível nas seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="1b7a7-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="1b7a7-163">Windows: 16.0.9001 - Disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="1b7a7-164">Mac: 16.10.18011401 - Disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="1b7a7-165">iOS: 2.9.18010804 - Disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="1b7a7-166">A Web - Disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-166">The web - Currently available.</span></span>
    
<span data-ttu-id="1b7a7-167">Isso não impede que um administrador use a Implantação Centralizada para atribuir um Office Store.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="1b7a7-168">Para impedir que um usuário entre com uma conta da Microsoft, você pode restringir o logon para usar apenas a conta organizacional.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="1b7a7-169">Para obter mais informações, [consulte Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span><span class="sxs-lookup"><span data-stu-id="1b7a7-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE] 
> <span data-ttu-id="1b7a7-170">Impedir que os usuários acessem o office store também os impedirá de fazer sideload Office de complementos para testes de um [compartilhamento de rede.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="1b7a7-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing from a network share](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="1b7a7-171">Mais sobre a experiência do usuário final com os complementos</span><span class="sxs-lookup"><span data-stu-id="1b7a7-171">More about the end-user experience with add-ins</span></span>

<span data-ttu-id="1b7a7-172">Depois de implantar um add-in, os usuários finais podem começar a usá-lo em seus aplicativos Office de Office (consulte [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="1b7a7-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="1b7a7-173">O complemento aparece em todas as plataformas que o complemento oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="1b7a7-174">Se o complemento for compatível com comandos de complemento, os comandos aparecerão na faixa Office faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-174">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="1b7a7-175">No exemplo a seguir, o comando **Search Citation** é exibido para o complemento **Citações.**</span><span class="sxs-lookup"><span data-stu-id="1b7a7-175">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office faixa de opções com citações de pesquisa](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="1b7a7-177">Se o complemento implantado não dá suporte a comandos de add-in ou se você quiser exibir todos os complementos implantados, poderá **exibi-los** por meio de Meus Complementos .</span><span class="sxs-lookup"><span data-stu-id="1b7a7-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="1b7a7-178">Nos aplicativos Word 2016, Excel 2016 ou PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="1b7a7-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="1b7a7-179">Selecione **Inserir \> Meus Complementos**.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="1b7a7-180">Selecione a **guia Admin Managed** na janela Office Desem seguida.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="1b7a7-181">Clique duas vezes no complemento implantado anteriormente (neste exemplo, **Citações**).</span><span class="sxs-lookup"><span data-stu-id="1b7a7-181">Double-click the add-in you deployed earlier (in this example, **Citations**).</span></span>

    ![Guia Administrador Gerenciado da página de Office Desa somar](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a><span data-ttu-id="1b7a7-183">No Outlook</span><span class="sxs-lookup"><span data-stu-id="1b7a7-183">In Outlook</span></span>

1. <span data-ttu-id="1b7a7-184">Na faixa **de opções** Home, selecione **Obter Complementos**.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-184">On the **Home** ribbon, select **Get Add-ins**.</span></span>

    ![Botão Armazenar no Outlook](../../media/getaddinsicon.png)
  
2. <span data-ttu-id="1b7a7-186">Selecione **Gerenciados pelo Administrador** no painel de administração à esquerda.</span><span class="sxs-lookup"><span data-stu-id="1b7a7-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="related-content"></a><span data-ttu-id="1b7a7-187">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="1b7a7-187">Related content</span></span>

<span data-ttu-id="1b7a7-188">[Implantar os complementos no centro de administração](./manage-deployment-of-add-ins.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="1b7a7-188">[Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="1b7a7-189">Saiba mais sobre como criar e [criar Office -ins](/office/dev/add-ins/overview/office-add-ins) (artigo)</span><span class="sxs-lookup"><span data-stu-id="1b7a7-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins) (article)</span></span>\
<span data-ttu-id="1b7a7-190">[Usar cmdlets do PowerShell de](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) Implantação Centralizada para gerenciar os complementos (artigo)</span><span class="sxs-lookup"><span data-stu-id="1b7a7-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\
<span data-ttu-id="1b7a7-191">[Solução de problemas: o usuário não está vendo os complementos](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artigo)</span><span class="sxs-lookup"><span data-stu-id="1b7a7-191">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>\
<span data-ttu-id="1b7a7-192">[Secundárias e aquisição de complementos do Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="1b7a7-192">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span></span>