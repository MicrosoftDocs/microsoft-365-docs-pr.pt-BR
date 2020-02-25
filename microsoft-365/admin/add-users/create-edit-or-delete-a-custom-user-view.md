---
title: Criar, editar ou excluir uma exibição de usuário personalizada no Office 365
f1.keywords:
- NOCSH
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
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Saiba como usar filtros para criar, editar ou excluir o modo de exibição do usuário personalizado no Office 365.
ms.openlocfilehash: ba03d3da3e8bfdc4f2a661d1dc59845a8a22609f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237143"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="29ab7-103">Criar, editar ou excluir uma exibição de usuário personalizada no Office 365</span><span class="sxs-lookup"><span data-stu-id="29ab7-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="29ab7-104">Se você for um administrador de gerenciamento global ou de usuário do Office 365, poderá criar modos de exibição de usuário personalizados para exibir um subconjunto específico de usuários.</span><span class="sxs-lookup"><span data-stu-id="29ab7-104">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="29ab7-105">Esses modos de exibição são adicionais ao conjunto padrão de modos de exibição que acompanham o Office 365.</span><span class="sxs-lookup"><span data-stu-id="29ab7-105">These views are in addition to the standard set of views that come with Office 365.</span></span> <span data-ttu-id="29ab7-106">Você pode criar, editar ou excluir modos de exibição de usuário personalizados, e os modos de exibição personalizados que você cria estão disponíveis para todos os administradores.</span><span class="sxs-lookup"><span data-stu-id="29ab7-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="29ab7-107">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="29ab7-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="29ab7-108">Exibições de usuário personalizadas no centro de administração</span><span class="sxs-lookup"><span data-stu-id="29ab7-108">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="29ab7-109">Ao criar, editar ou excluir um modo de exibição de usuário personalizado, as alterações serão mostradas na lista de **filtros** que todos os administradores da sua empresa veem quando acessam a página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="29ab7-109">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="29ab7-110">Você pode criar até 50 modos de exibição personalizados.</span><span class="sxs-lookup"><span data-stu-id="29ab7-110">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="29ab7-111">Quando você cria, edita ou exclui um modo de exibição de usuário personalizado, as alterações serão mostradas na lista de **exibições** que todos os administradores da sua empresa veem quando acessam a página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="29ab7-111">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="29ab7-112">Você pode criar até 50 modos de exibição personalizados.</span><span class="sxs-lookup"><span data-stu-id="29ab7-112">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="29ab7-113">Quando você cria, edita ou exclui um modo de exibição de usuário personalizado, as alterações serão mostradas na lista de **exibições** que todos os administradores da sua empresa veem quando acessam a página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="29ab7-113">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="29ab7-114">Você pode criar até 50 modos de exibição personalizados.</span><span class="sxs-lookup"><span data-stu-id="29ab7-114">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="29ab7-115">Os modos de exibição de usuário padrão são exibidos por padrão na lista suspensa **filtros** .</span><span class="sxs-lookup"><span data-stu-id="29ab7-115">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="29ab7-116">Os filtros padrão incluem **todos os usuários**, **usuários licenciados**, **usuários convidados**, **logon permitido**, **logon bloqueado**, usuários não **licenciados**, **usuários com erros**, administradores de **cobrança**, **administradores globais**, **Administradores de assistência técnica**, administradores de **Serviços**e administradores de **Gerenciamento de usuários**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-116">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="29ab7-117">Não é possível editar ou excluir modos de exibição padrão.</span><span class="sxs-lookup"><span data-stu-id="29ab7-117">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="29ab7-118">Algumas coisas a serem observadas sobre os modos de exibição padrão:</span><span class="sxs-lookup"><span data-stu-id="29ab7-118">A few things to note about standard views:</span></span> 

- <span data-ttu-id="29ab7-119">Alguns modos de exibição padrão exibem uma lista não classificada se houver mais de 2.000 usuários na lista.</span><span class="sxs-lookup"><span data-stu-id="29ab7-119">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="29ab7-120">Para localizar usuários específicos nesta lista, use a caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="29ab7-120">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="29ab7-121">Se você não comprou o Office 365 da Microsoft, os **Administradores de cobrança** não aparecerão na lista de modos de exibição padrão.</span><span class="sxs-lookup"><span data-stu-id="29ab7-121">If you didn't purchase Office 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="29ab7-122">Para saber mais, veja [Atribuindo funções de administrador](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="29ab7-122">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="29ab7-123">Escolha os filtros para o modo de exibição de usuário personalizado</span><span class="sxs-lookup"><span data-stu-id="29ab7-123">Choose the filters for your custom user view</span></span>

<span data-ttu-id="29ab7-124">Você pode criar e editar seus modos de exibição personalizados no painel de **filtro personalizado** .</span><span class="sxs-lookup"><span data-stu-id="29ab7-124">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="29ab7-125">Se você selecionar várias opções de filtro, receberá resultados que contenham usuários que correspondam a todos os critérios selecionados.</span><span class="sxs-lookup"><span data-stu-id="29ab7-125">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="29ab7-126">O exemplo a seguir mostra como criar um modo de exibição personalizado chamado "usuários canadenses" que mostra todos os usuários em um domínio específico que estão no Canadá.</span><span class="sxs-lookup"><span data-stu-id="29ab7-126">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="29ab7-127">**A-Domain** Se você tiver vários domínios para sua organização, poderá escolher em uma lista suspensa de domínios disponíveis.</span><span class="sxs-lookup"><span data-stu-id="29ab7-127">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="29ab7-128">**Status de entrada B** Escolha usuários que são permitidos ou bloqueados.</span><span class="sxs-lookup"><span data-stu-id="29ab7-128">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="29ab7-129">**C-local** Escolha um local em uma lista suspensa de países.</span><span class="sxs-lookup"><span data-stu-id="29ab7-129">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="29ab7-130">**Licença de produto atribuída D** Escolha em uma lista suspensa de licenças disponíveis em sua organização.</span><span class="sxs-lookup"><span data-stu-id="29ab7-130">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="29ab7-131">Use este filtro para mostrar os usuários que têm a licença selecionada atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="29ab7-131">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="29ab7-132">Os usuários também podem ter licenças adicionais.</span><span class="sxs-lookup"><span data-stu-id="29ab7-132">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="29ab7-133">Você também pode filtrar por detalhes adicionais de perfil de usuário usados na organização, como departamento, cidade, estado ou província, país ou região, ou cargo.</span><span class="sxs-lookup"><span data-stu-id="29ab7-133">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="29ab7-134">**Outras condições:**</span><span class="sxs-lookup"><span data-stu-id="29ab7-134">**Other conditions:**</span></span>
  
- <span data-ttu-id="29ab7-135">**Somente usuários sincronizados** Selecione esta caixa para mostrar todos os usuários que foram sincronizados com o Active Directory local, independentemente se os usuários foram ativados ou não.</span><span class="sxs-lookup"><span data-stu-id="29ab7-135">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="29ab7-136">**Usuários com erros** Selecione esta caixa para mostrar aos usuários que podem ter o provisionamento de erros.</span><span class="sxs-lookup"><span data-stu-id="29ab7-136">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="29ab7-137">**Usuários não licenciados** Selecione esta caixa para localizar todos os usuários que não receberam uma licença.</span><span class="sxs-lookup"><span data-stu-id="29ab7-137">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="29ab7-138">Os resultados desse modo de exibição também podem incluir usuários que tenham uma caixa de correio do Exchange, mas não tenham uma licença.</span><span class="sxs-lookup"><span data-stu-id="29ab7-138">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="29ab7-139">Para controlar esses usuários especificamente, use o filtro **usuários não licenciados com caixas de correio do Exchange ou arquivos mortos**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-139">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="29ab7-140">Os resultados desse modo de exibição também podem incluir usuários que têm um arquivo morto do Exchange, mas não têm uma licença.</span><span class="sxs-lookup"><span data-stu-id="29ab7-140">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="29ab7-141">**Usuários não licenciados com caixas de correio ou arquivos mortos do Exchange** Selecione esta caixa para mostrar as contas de usuário que foram criadas no Exchange Online e ter uma caixa de correio do Exchange, mas não foi atribuída uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="29ab7-141">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Office 365 license.</span></span> <span data-ttu-id="29ab7-142">Os resultados desse filtro incluem usuários que tenham ou quem foram atribuídos a um arquivo morto do Exchange.</span><span class="sxs-lookup"><span data-stu-id="29ab7-142">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 
    
> [!TIP]
> <span data-ttu-id="29ab7-143">Se você criar um modo de exibição personalizado que retorna mais de 2.000 usuários, a lista de usuários resultante não será classificada.</span><span class="sxs-lookup"><span data-stu-id="29ab7-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="29ab7-144">Nesse caso, use a caixa Pesquisar para localizar usuários ou editar o modo de exibição personalizado para refinar sua pesquisa.</span><span class="sxs-lookup"><span data-stu-id="29ab7-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="29ab7-145">Criar um modo de exibição de usuário personalizado</span><span class="sxs-lookup"><span data-stu-id="29ab7-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="29ab7-146">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="29ab7-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="29ab7-147">Na página **usuários ativos** , selecione **filtros** e selecione **novo filtro**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="29ab7-148">Na página **filtro personalizado** , digite o nome do filtro, escolha as condições para o filtro personalizado e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="29ab7-149">O modo de exibição personalizado agora está incluído na lista suspensa de filtros.</span><span class="sxs-lookup"><span data-stu-id="29ab7-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="29ab7-150">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="29ab7-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="29ab7-151">Na página **usuários ativos** , selecione **modos** de exibição e selecione **Adicionar modo de exibição personalizado**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="29ab7-152">Na página **modo de exibição personalizado** , digite o nome para o filtro, escolha as condições para o filtro personalizado e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="29ab7-153">O modo de exibição personalizado agora está incluído na lista suspensa de filtros.</span><span class="sxs-lookup"><span data-stu-id="29ab7-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="29ab7-154">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="29ab7-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="29ab7-155">Na página **usuários ativos** , selecione **modos** de exibição e selecione **Adicionar modo de exibição personalizado**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="29ab7-156">Na página **modo de exibição personalizado** , digite o nome para o filtro, escolha as condições para o filtro personalizado e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="29ab7-157">O modo de exibição personalizado agora está incluído na lista suspensa de filtros.</span><span class="sxs-lookup"><span data-stu-id="29ab7-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="29ab7-158">Editar ou excluir um modo de exibição de usuário personalizado</span><span class="sxs-lookup"><span data-stu-id="29ab7-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="29ab7-159">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="29ab7-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="29ab7-160">Na página **usuários ativos** , selecione **filtro**, selecione o filtro que você deseja alterar e, em seguida, selecione **Editar Filtro**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="29ab7-161">Você pode editar somente modos de exibição personalizados.</span><span class="sxs-lookup"><span data-stu-id="29ab7-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="29ab7-162">Na página **filtro personalizado** , edite as informações conforme necessário e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="29ab7-163">Ou, para excluir o filtro, na parte inferior da página, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="29ab7-164">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="29ab7-164">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="29ab7-165">Na página **usuários ativos** , selecione **modos**de exibição, selecione o filtro que você deseja alterar e, em seguida, selecione **Editar este modo de exibição**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="29ab7-166">Você pode editar somente modos de exibição personalizados.</span><span class="sxs-lookup"><span data-stu-id="29ab7-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="29ab7-167">Na página **modo de exibição personalizado** , edite as informações conforme o necessário e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="29ab7-168">Ou, para excluir o filtro, na parte inferior da página, selecione **excluir modo de exibição personalizado**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="29ab7-169">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="29ab7-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="29ab7-170">Na página **usuários ativos** , selecione **modos**de exibição, selecione o filtro que você deseja alterar e, em seguida, selecione **Editar este modo de exibição**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="29ab7-171">Você pode editar somente modos de exibição personalizados.</span><span class="sxs-lookup"><span data-stu-id="29ab7-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="29ab7-172">Na página **modo de exibição personalizado** , edite as informações conforme o necessário e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="29ab7-173">Ou, para excluir o filtro, na parte inferior da página, selecione **excluir modo de exibição personalizado**.</span><span class="sxs-lookup"><span data-stu-id="29ab7-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     

