---
title: Atribuir licenças aos usuários
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Aprenda a atribuir licenças aos usuários.
ms.date: 08/14/2020
ms.openlocfilehash: 9f044f29cabf4976d5fbf17b22777da62e4414c5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915489"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="3510e-103">Atribuir licenças aos usuários</span><span class="sxs-lookup"><span data-stu-id="3510e-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3510e-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="3510e-104">The admin center is changing.</span></span> <span data-ttu-id="3510e-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3510e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="3510e-106">Você pode atribuir licenças a usuários na página **Usuários ativos** ou na página **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="3510e-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="3510e-107">O método usado depende de você querer atribuir licenças do produto a usuários específicos ou atribuir licenças de usuários a um produto específico.</span><span class="sxs-lookup"><span data-stu-id="3510e-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="3510e-108">[Aprenda como adicionar um usuário e atribuir uma licença ao mesmo tempo](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="3510e-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3510e-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3510e-109">Before you begin</span></span>

- <span data-ttu-id="3510e-110">Você deve ser um administrador global, de licença ou de usuário para atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="3510e-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="3510e-111">Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3510e-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="3510e-112">Você pode [atribuir licenças às contas de usuários com o Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3510e-112">You can [assign licenses to user accounts with Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="3510e-113">Para obter mais instruções do licenciamento baseado em grupo, consulte [Atribuir licenças a usuários por membro de grupo no Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="3510e-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="3510e-114">Alguns serviços, como o Sway, são atribuídos automaticamente aos usuários e não precisam ser atribuídos individualmente.</span><span class="sxs-lookup"><span data-stu-id="3510e-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="3510e-115">Use a página Licenças para atribuir licenças aos usuários</span><span class="sxs-lookup"><span data-stu-id="3510e-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="3510e-116">Ao usar a página **Licenças** para atribuir licenças, você atribui licenças de um produto específico para até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="3510e-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="3510e-117">Na página **Licenças**, você verá uma lista de todos os produtos que você possui assinaturas.</span><span class="sxs-lookup"><span data-stu-id="3510e-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="3510e-118">Você também verá o número total de licenças de cada produto, quantas licenças são atribuídas e quantas estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3510e-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="3510e-119">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="3510e-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="3510e-120">Selecione um produto.</span><span class="sxs-lookup"><span data-stu-id="3510e-120">Select a product.</span></span>
3. <span data-ttu-id="3510e-121">Na página de detalhes do produto, selecione **Atribuir licenças**.</span><span class="sxs-lookup"><span data-stu-id="3510e-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="3510e-122">No painel **Atribuir licenças a usuários**, comece a digitar um nome e, em seguida, selecione-o nos resultados para adicioná-lo à lista.</span><span class="sxs-lookup"><span data-stu-id="3510e-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="3510e-123">É possível selecionar até 20 usuários de cada vez.</span><span class="sxs-lookup"><span data-stu-id="3510e-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="3510e-124">Selecione **Ativar ou desativar os aplicativos e serviços** para atribuir ou remover o acesso a itens específicos.</span><span class="sxs-lookup"><span data-stu-id="3510e-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="3510e-125">Quando tiver terminado, clique em **Atribuir** e depois em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="3510e-126">Se houver um conflito, será exibida uma mensagem informando qual é o problema e como corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="3510e-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="3510e-127">Por exemplo, se você selecionou licenças que contêm serviços conflitantes, a mensagem de erro indicará revisar os serviços incluídos em cada licença e tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="3510e-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="3510e-128">Para alterar os aplicativos e serviços que o usuário tem acesso:</span><span class="sxs-lookup"><span data-stu-id="3510e-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="3510e-129">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="3510e-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="3510e-130">Na página **Licenças**, selecione a linha de um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="3510e-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="3510e-131">No painel direito, marque ou desmarque os aplicativos e serviços aos quais você deseja conceder acesso ou remover o acesso.</span><span class="sxs-lookup"><span data-stu-id="3510e-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="3510e-132">Quando tiver terminado, selecione **Salvar**, e então selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="3510e-133">Use a página Usuários ativos para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="3510e-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="3510e-134">Ao usar a página **Usuários ativos** para atribuir licenças, você atribui licenças de usuários a produtos.</span><span class="sxs-lookup"><span data-stu-id="3510e-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="3510e-135">Atribuir licenças a vários usuários</span><span class="sxs-lookup"><span data-stu-id="3510e-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="3510e-136">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="3510e-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3510e-137">Selecione os círculos ao lado dos nomes dos usuários aos quais você quer atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="3510e-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="3510e-138">Na parte superior, selecione **mais opções (...)**, em seguida, selecione **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="3510e-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="3510e-139">No painel **Gerenciar licenças de produtos**, selecione **Adicionar a atribuições de licença de produto existentes** \> **.Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="3510e-140">No painel **Adicionar a produtos existentes**, alterne o botão para a posição **Ativado** nas licenças que você quer que os usuários selecionados tenham.</span><span class="sxs-lookup"><span data-stu-id="3510e-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="3510e-141">Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3510e-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="3510e-142">Você pode limitar quais serviços estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="3510e-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="3510e-143">Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.</span><span class="sxs-lookup"><span data-stu-id="3510e-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="3510e-144">Na parte inferior do painel, selecione **Adicionar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="3510e-145">Atribuir licenças a vários usuários</span><span class="sxs-lookup"><span data-stu-id="3510e-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="3510e-146">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="3510e-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3510e-147">Selecione as caixas ao lado dos nomes dos usuários aos quais você quer atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="3510e-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="3510e-148">No painel **Ações em massa**, escolha **Editar licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="3510e-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="3510e-149">No painel **Atribuir produtos**, selecione **Adicionar a atribuições de licença de produto existentes** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="3510e-150">Alterne para a posição **Ativado** das licenças que você quer que os usuários selecionados tenham.</span><span class="sxs-lookup"><span data-stu-id="3510e-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="3510e-151">Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3510e-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="3510e-152">Você pode limitar quais serviços estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="3510e-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="3510e-153">Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.</span><span class="sxs-lookup"><span data-stu-id="3510e-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="3510e-154">Na parte inferior do painel **Adicionar a produtos existentes**, selecione **Adicionar** \> **Fechar**\> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="3510e-155">Atribuir licenças a vários usuários</span><span class="sxs-lookup"><span data-stu-id="3510e-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="3510e-156">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="3510e-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3510e-157">Selecione as caixas ao lado dos nomes dos usuários aos quais você quer atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="3510e-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="3510e-158">No painel **Ações em massa**, escolha **Editar licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="3510e-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="3510e-159">No painel **Atribuir produtos**, selecione **Adicionar a atribuições de licença de produto existentes** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="3510e-160">Alterne para a posição **Ativado** das licenças que você quer que os usuários selecionados tenham.</span><span class="sxs-lookup"><span data-stu-id="3510e-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="3510e-161">Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3510e-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="3510e-162">Você pode limitar quais serviços estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="3510e-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="3510e-163">Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.</span><span class="sxs-lookup"><span data-stu-id="3510e-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="3510e-164">Na parte inferior do painel **Adicionar a produtos existentes**, selecione **Adicionar** \> **Fechar**\> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="3510e-165">Atribuir licenças a um usuário</span><span class="sxs-lookup"><span data-stu-id="3510e-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="3510e-166">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="3510e-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3510e-167">Selecione a linha do usuário ao qual você quer atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="3510e-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="3510e-168">No painel direito, selecione **Licenças e Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="3510e-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="3510e-169">Expanda a seção **Licenças**, marque as caixas das licenças que você deseja atribuir e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="3510e-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="3510e-170">Atribuir licenças a um usuário</span><span class="sxs-lookup"><span data-stu-id="3510e-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="3510e-171">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="3510e-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3510e-172">Selecione a caixa ao lado do nome do usuário ao qual você quer atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="3510e-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="3510e-173">No painel direito, na linha **Licenças do produto**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="3510e-174">No painel **Licenças do produto**, alterne o botão para a posição **Ativado** na licença que você quer atribuir ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3510e-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.\</span></span>
    <span data-ttu-id="3510e-175">Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3510e-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="3510e-176">Você pode limitar quais serviços estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="3510e-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="3510e-177">Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.</span><span class="sxs-lookup"><span data-stu-id="3510e-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="3510e-178">Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="3510e-179">Atribuir licenças a um usuário</span><span class="sxs-lookup"><span data-stu-id="3510e-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="3510e-180">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="3510e-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3510e-181">Selecione a caixa ao lado do nome do usuário ao qual você quer atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="3510e-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="3510e-182">No painel direito, na linha **Licenças do produto**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="3510e-183">No painel **Licenças do produto**, alterne o botão para a posição **Ativado** na licença que você quer atribuir ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3510e-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.\</span></span>
    <span data-ttu-id="3510e-184">Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3510e-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="3510e-185">Você pode limitar quais serviços estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="3510e-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="3510e-186">Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.</span><span class="sxs-lookup"><span data-stu-id="3510e-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="3510e-187">Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="3510e-188">Atribuir uma licença a um usuário convidado</span><span class="sxs-lookup"><span data-stu-id="3510e-188">Assign a license to a guest user</span></span>

<span data-ttu-id="3510e-189">É possível convidar usuários convidados para colaborar com sua organização no centro de administração do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3510e-189">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="3510e-190">Para saber mais sobre os usuários convidados, confira [O que é acesso de usuário convidado no Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="3510e-190">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="3510e-191">Se você não tiver nenhum usuário convidado, confira [Início Rápido: Adicionar usuários convidados ao seu diretório no portal do Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="3510e-191">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3510e-192">Você terá de ser um administrador global para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="3510e-192">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="3510e-193">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">centro de administração do Azure Active Directory</a></span><span class="sxs-lookup"><span data-stu-id="3510e-193">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="3510e-194">No painel de navegação, selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="3510e-194">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="3510e-195">Na página **Usuários | Todos os Usuários (Visualização)**, selecione **Adicionar filtros**.</span><span class="sxs-lookup"><span data-stu-id="3510e-195">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="3510e-196">No menu **Escolher um campo**, escolha o **Tipo de usuário** e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-196">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="3510e-197">No menu seguinte, selecione **Convidado**.</span><span class="sxs-lookup"><span data-stu-id="3510e-197">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="3510e-198">Na lista de resultados, selecione o usuário que precisa de uma licença.</span><span class="sxs-lookup"><span data-stu-id="3510e-198">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="3510e-199">Em **Gerenciar**, selecione **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="3510e-199">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="3510e-200">Selecione **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="3510e-200">Select **Assignments**.</span></span>
9. <span data-ttu-id="3510e-201">Na página **Atualizar atribuições de licença**, selecione o produto para o qual deseja atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="3510e-201">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="3510e-202">À direita, desmarque as caixas de seleção dos serviços às quais você não deseja que o usuário convidado tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="3510e-202">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="3510e-203">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3510e-203">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3510e-204">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3510e-204">Next steps</span></span>

<span data-ttu-id="3510e-205">Se os usuários ainda não tiverem os aplicativos do Office instalados, você poderá compartilhar a [Guia de início rápido dos funcionários](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) com os usuários para configurar coisas, do tipo [como baixar e instalar o Microsoft 365 ou o Office 2019 em um computador ou Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e [como configurar aplicativos do Office e e-mails em um dispositivo móvel](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="3510e-205">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="3510e-206">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="3510e-206">Related content</span></span>

<span data-ttu-id="3510e-207">[Compreender assinaturas e licenças](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="3510e-207">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="3510e-208">[Cancelar a atribuição de licenças de usuários](remove-licenses-from-users.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="3510e-208">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="3510e-209">[Compre ou remova licenças da sua assinatura](../../commerce/licenses/buy-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="3510e-209">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>