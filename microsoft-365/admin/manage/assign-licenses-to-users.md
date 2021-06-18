---
title: Atribuir licenças aos usuários
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Atribua licenças dependendo se você deseja atribuir licenças de produto a usuários específicos ou atribuir licenças de usuários a um produto específico.
ms.date: 04/26/2021
ms.openlocfilehash: c8e5c6a648f08aaba97fe05e19a5cfa0cada2174
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007004"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="b92cd-103">Atribuir licenças aos usuários</span><span class="sxs-lookup"><span data-stu-id="b92cd-103">Assign licenses to users</span></span>

<span data-ttu-id="b92cd-104">Você pode atribuir licenças a usuários na página **Usuários ativos** ou na página **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="b92cd-105">O método usado depende de você querer atribuir licenças do produto a usuários específicos ou atribuir licenças de usuários a um produto específico.</span><span class="sxs-lookup"><span data-stu-id="b92cd-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="b92cd-106">Como administrador, você não pode atribuir ou cancelar a atribuição de licenças para uma assinatura de compra de autoatendimento comprada por um usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b92cd-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="b92cd-107">Você pode [assumir uma assinatura de compra de autoatendimento](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), e, em seguida, atribuir ou cancelar a atribuição de licenças.</span><span class="sxs-lookup"><span data-stu-id="b92cd-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="b92cd-108">[Aprenda como adicionar um usuário e atribuir uma licença ao mesmo tempo](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="b92cd-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b92cd-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b92cd-109">Before you begin</span></span>

- <span data-ttu-id="b92cd-110">Você deve ser um administrador global, de licença ou de usuário para atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="b92cd-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="b92cd-111">Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b92cd-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="b92cd-112">Você pode [atribuir licenças às contas de usuários do Microsoft 365 com o PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b92cd-112">You can [assign Microsoft 365 licenses to user accounts with PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="b92cd-113">Para obter mais instruções do licenciamento baseado em grupo, consulte [Atribuir licenças a usuários por membro de grupo no Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="b92cd-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="b92cd-114">Alguns serviços, como o Sway, são atribuídos automaticamente aos usuários e não precisam ser atribuídos individualmente.</span><span class="sxs-lookup"><span data-stu-id="b92cd-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="b92cd-115">Use a página Licenças para atribuir licenças aos usuários</span><span class="sxs-lookup"><span data-stu-id="b92cd-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="b92cd-116">Ao usar a página **Licenças** para atribuir licenças, você atribui licenças de um produto específico para até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="b92cd-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="b92cd-117">Na página **Licenças**, você verá uma lista de todos os produtos que você possui assinaturas.</span><span class="sxs-lookup"><span data-stu-id="b92cd-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="b92cd-118">Você também verá o número total de licenças de cada produto, quantas licenças são atribuídas e quantas estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b92cd-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b92cd-119">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="b92cd-120">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b92cd-121">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="b92cd-122">Selecione um produto.</span><span class="sxs-lookup"><span data-stu-id="b92cd-122">Select a product.</span></span>
3. <span data-ttu-id="b92cd-123">Na página de detalhes do produto, selecione **Atribuir licenças**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="b92cd-124">No painel **Atribuir licenças a usuários**, comece a digitar um nome e, em seguida, selecione-o nos resultados para adicioná-lo à lista.</span><span class="sxs-lookup"><span data-stu-id="b92cd-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="b92cd-125">É possível selecionar até 20 usuários de cada vez.</span><span class="sxs-lookup"><span data-stu-id="b92cd-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="b92cd-126">Selecione **Ativar ou desativar os aplicativos e serviços** para atribuir ou remover o acesso a itens específicos.</span><span class="sxs-lookup"><span data-stu-id="b92cd-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="b92cd-127">Quando tiver terminado, clique em **Atribuir** e depois em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="b92cd-128">Se houver um conflito, será exibida uma mensagem informando qual é o problema e como corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="b92cd-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="b92cd-129">Por exemplo, se você selecionou licenças que contêm serviços conflitantes, a mensagem de erro indicará revisar os serviços incluídos em cada licença e tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="b92cd-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="b92cd-130">Para alterar os aplicativos e serviços que o usuário tem acesso:</span><span class="sxs-lookup"><span data-stu-id="b92cd-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b92cd-131">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-131">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="b92cd-132">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b92cd-133">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="b92cd-134">Na página **Licenças**, selecione a linha de um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="b92cd-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="b92cd-135">No painel direito, marque ou desmarque os aplicativos e serviços aos quais você deseja conceder acesso ou remover o acesso.</span><span class="sxs-lookup"><span data-stu-id="b92cd-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="b92cd-136">Quando tiver terminado, selecione **Salvar**, e então selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="b92cd-137">Use a página Usuários ativos para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="b92cd-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="b92cd-138">Ao usar a página **Usuários ativos** para atribuir licenças, você atribui licenças de usuários a produtos.</span><span class="sxs-lookup"><span data-stu-id="b92cd-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="b92cd-139">Atribuir licenças a vários usuários</span><span class="sxs-lookup"><span data-stu-id="b92cd-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b92cd-140">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="b92cd-141">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b92cd-142">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="b92cd-143">Selecione os círculos ao lado dos nomes dos usuários aos quais você quer atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="b92cd-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="b92cd-144">Na parte superior, selecione **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-144">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="b92cd-145">No painel **Gerenciar licenças de produtos**, selecione **Atribuir mais: manter as licenças existentes e atribuir mais** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-145">In the **Manage product licenses** pane, select **Assign more: Keep the existing licenses and assign more** \> **Next**.</span></span>
5. <span data-ttu-id="b92cd-146">Em **Licenças**, selecione a caixa para as licenças que você deseja que os usuários selecionados tenham.</span><span class="sxs-lookup"><span data-stu-id="b92cd-146">Under **Licenses**, select the box for the license(s) that you want the selected users to have.</span></span>\
    <span data-ttu-id="b92cd-147">Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b92cd-147">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="b92cd-148">Você pode limitar quais serviços estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="b92cd-148">You can limit which services are available to the users.</span></span> <span data-ttu-id="b92cd-149">Desmarque as caixas para os serviços que você não deseja que os usuários tenham.</span><span class="sxs-lookup"><span data-stu-id="b92cd-149">Deselect the boxes for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="b92cd-150">Na parte inferior do painel, selecione **Salvar mudanças**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-150">At the bottom of the pane, select **Save changes**.</span></span>  
    <span data-ttu-id="b92cd-151">Talvez seja necessário comprar licenças adicionais se você não tiver licenças suficientes para todos.</span><span class="sxs-lookup"><span data-stu-id="b92cd-151">You might have to buy additional licneses if you don't have enough licenses for everyone.</span></span>


> [!NOTE]
> <span data-ttu-id="b92cd-152">Se você deseja atribuir licenças a um grande número de usuários, use o [Atribuir licenças a usuários por associação a um grupo no Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="b92cd-152">If you want to assign licenses for a large number of users, use [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span></span>

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="b92cd-153">Atribuir licenças a um usuário</span><span class="sxs-lookup"><span data-stu-id="b92cd-153">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b92cd-154">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="b92cd-155">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b92cd-156">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="b92cd-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="b92cd-157">Selecione a linha do usuário ao qual você quer atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="b92cd-157">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="b92cd-158">No painel direito, selecione **Licenças e Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-158">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="b92cd-159">Expanda a seção **Licenças**, marque as caixas das licenças que você deseja atribuir e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-159">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="b92cd-160">Atribuir uma licença a um usuário convidado</span><span class="sxs-lookup"><span data-stu-id="b92cd-160">Assign a license to a guest user</span></span>

<span data-ttu-id="b92cd-161">É possível convidar usuários convidados para colaborar com sua organização no centro de administração do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b92cd-161">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="b92cd-162">Para saber mais sobre os usuários convidados, confira [O que é acesso de usuário convidado no Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="b92cd-162">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="b92cd-163">Se você não tiver nenhum usuário convidado, confira [Início Rápido: Adicionar usuários convidados ao seu diretório no portal do Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="b92cd-163">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b92cd-164">Você terá de ser um administrador global para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="b92cd-164">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="b92cd-165">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">centro de administração do Azure Active Directory</a></span><span class="sxs-lookup"><span data-stu-id="b92cd-165">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="b92cd-166">No painel de navegação, selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-166">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="b92cd-167">Na página **Usuários | Todos os Usuários (Visualização)**, selecione **Adicionar filtros**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-167">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="b92cd-168">No menu **Escolher um campo**, escolha o **Tipo de usuário** e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-168">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="b92cd-169">No menu seguinte, selecione **Convidado**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-169">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="b92cd-170">Na lista de resultados, selecione o usuário que precisa de uma licença.</span><span class="sxs-lookup"><span data-stu-id="b92cd-170">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="b92cd-171">Em **Gerenciar**, selecione **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-171">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="b92cd-172">Selecione **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-172">Select **Assignments**.</span></span>
9. <span data-ttu-id="b92cd-173">Na página **Atualizar atribuições de licença**, selecione o produto para o qual deseja atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="b92cd-173">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="b92cd-174">À direita, desmarque as caixas de seleção dos serviços às quais você não deseja que o usuário convidado tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="b92cd-174">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="b92cd-175">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b92cd-175">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b92cd-176">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b92cd-176">Next steps</span></span>

<span data-ttu-id="b92cd-177">Se os usuários ainda não tiverem os aplicativos do Office instalados, você poderá compartilhar a [Guia de início rápido dos funcionários](../../business-video/employee-quick-setup.md) com os usuários para configurar coisas, do tipo [como baixar e instalar o Microsoft 365 ou o Office 2019 em um computador ou Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e [como configurar aplicativos do Office e e-mails em um dispositivo móvel](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="b92cd-177">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](../../business-video/employee-quick-setup.md) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="b92cd-178">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="b92cd-178">Related content</span></span>

<span data-ttu-id="b92cd-179">[Compreender assinaturas e licenças](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="b92cd-179">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="b92cd-180">[Cancelar a atribuição de licenças de usuários](remove-licenses-from-users.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="b92cd-180">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="b92cd-181">[Compre ou remova licenças da sua assinatura](../../commerce/licenses/buy-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="b92cd-181">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
