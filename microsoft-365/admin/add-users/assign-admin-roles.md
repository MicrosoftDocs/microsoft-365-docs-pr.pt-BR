---
title: Atribuir funções de administrador ao Microsoft 365 de administração
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
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Saiba como atribuir funções de administrador a um usuário ou vários usuários em sua empresa para que eles possam executar tarefas específicas no centro de administração.
ms.openlocfilehash: f23a30cfd1be53982572d745d476558c3be615e6
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571860"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="1e185-103">Atribuir funções de administrador</span><span class="sxs-lookup"><span data-stu-id="1e185-103">Assign admin roles</span></span>

<span data-ttu-id="1e185-104">Se você for a pessoa que comprou sua assinatura de negócios da Microsoft, será o administrador global. Isso significa que você tem controle ilimitado sobre os produtos em suas assinaturas e pode acessar a maioria dos dados.</span><span class="sxs-lookup"><span data-stu-id="1e185-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="1e185-105">Para obter mais informações, confira o artigo [Sobre funções de administrador](about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1e185-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="1e185-106">Quando você adiciona novos usuários, se você não atribuir a  eles uma função de administrador, eles estão na função de usuário e não têm privilégios de administrador em nenhum dos centros de administração da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1e185-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="1e185-107">Mas se você precisar de ajuda para fazer as coisas, poderá atribuir uma função de administrador a um usuário.</span><span class="sxs-lookup"><span data-stu-id="1e185-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="1e185-108">Por exemplo, se você precisar de alguém para ajudar a redefinir senhas, não deve atribuir a elas a função de administrador global, você deve atribuí-las a função de administrador de senha.</span><span class="sxs-lookup"><span data-stu-id="1e185-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="1e185-109">Ter muitos administradores globais, com acesso ilimitado aos seus dados e negócios online, é um risco de segurança.</span><span class="sxs-lookup"><span data-stu-id="1e185-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="1e185-110">Assista: Adicionar um administrador.</span><span class="sxs-lookup"><span data-stu-id="1e185-110">Watch: Add an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="1e185-111">Se você achou esse vídeo útil, confira as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="1e185-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="1e185-112">Atribuir funções de administrador</span><span class="sxs-lookup"><span data-stu-id="1e185-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="1e185-113">Você pode atribuir usuários a uma função de duas maneiras diferentes:</span><span class="sxs-lookup"><span data-stu-id="1e185-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="1e185-114">Você pode ir até os detalhes do usuário e **Gerenciar funções** para atribuir uma função ao usuário.</span><span class="sxs-lookup"><span data-stu-id="1e185-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="1e185-115">Ou você pode ir para **Funções** e selecionar a função e adicionar vários usuários a ela.</span><span class="sxs-lookup"><span data-stu-id="1e185-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="1e185-116">Atribuir funções de administrador a usuários usando funções</span><span class="sxs-lookup"><span data-stu-id="1e185-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="1e185-117">No centro de administração, vá para **Funções**.</span><span class="sxs-lookup"><span data-stu-id="1e185-117">In the admin center, go to **Roles**.</span></span> <span data-ttu-id="1e185-118">Escolha as **guias Azure AD** ou **Intune** para exibir as funções de administrador disponíveis para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1e185-118">Choose the **Azure AD** or **Intune** tabs to view the admin roles available for your organization.</span></span>
2. <span data-ttu-id="1e185-119">Selecione a função de administrador à que você deseja atribuir o usuário.</span><span class="sxs-lookup"><span data-stu-id="1e185-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="1e185-120">Selecione **Administradores atribuídos** > **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1e185-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="1e185-121">Digite o nome de **exibição ou** o nome de usuário **do** usuário e selecione o usuário na lista de sugestões.</span><span class="sxs-lookup"><span data-stu-id="1e185-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="1e185-122">Adicione vários usuários até terminar.</span><span class="sxs-lookup"><span data-stu-id="1e185-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="1e185-123">Selecione **Salvar** e, em seguida, o usuário será adicionado à lista de administradores atribuídos.</span><span class="sxs-lookup"><span data-stu-id="1e185-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="1e185-124">Atribuir um usuário a uma função de administrador a partir de Usuários ativos</span><span class="sxs-lookup"><span data-stu-id="1e185-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="1e185-125">No centro de administração, vá para a **página Usuários** > [Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=834822)</span><span class="sxs-lookup"><span data-stu-id="1e185-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="1e185-126">Na página **Usuários ativos,** selecione o usuário cuja função de administrador você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="1e185-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="1e185-127">No painel sublevado, em **Funções**, selecione **Gerenciar funções**.</span><span class="sxs-lookup"><span data-stu-id="1e185-127">In the flyout pane, under **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="1e185-128">Selecione a função de administrador que deseja atribuir ao usuário.</span><span class="sxs-lookup"><span data-stu-id="1e185-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="1e185-129">Se você não vir a função que está procurando, selecione **Mostrar tudo** na parte inferior da lista.</span><span class="sxs-lookup"><span data-stu-id="1e185-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1e185-130">No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="1e185-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="1e185-131">Na página **Usuários ativos,** selecione o usuário cuja função de administrador você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="1e185-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="1e185-132">No painel de sobrevoos, ao lado de **Funções,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1e185-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="1e185-133">Se você não vir a opção **Editar,** não terá permissão para editar e não poderá atribuir funções de administrador a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="1e185-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="1e185-134">Peça a um administrador global em sua empresa para atribuir funções para você.</span><span class="sxs-lookup"><span data-stu-id="1e185-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="1e185-135">Em uma pequena empresa, o proprietário da empresa (a pessoa que comprou sua assinatura) é um administrador global. Em uma grande empresa, as pessoas-chave no departamento de IT são administradores globais.</span><span class="sxs-lookup"><span data-stu-id="1e185-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="1e185-136">Selecione **Administrador personalizado** para ver uma lista de funções personalizadas para você.</span><span class="sxs-lookup"><span data-stu-id="1e185-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="1e185-137">Para uma descrição de cada função, consulte [Sobre funções de administrador.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="1e185-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1e185-138">No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="1e185-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="1e185-139">Na página **Usuários ativos,** selecione o usuário cuja função de administrador você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="1e185-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="1e185-140">No painel de sobrevoos, ao lado de **Funções,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1e185-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="1e185-141">Se você não vir a opção **Editar,** não terá permissão para editar e não poderá atribuir funções de administrador a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="1e185-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="1e185-142">Peça a um administrador global em sua empresa para atribuir funções para você.</span><span class="sxs-lookup"><span data-stu-id="1e185-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="1e185-143">Em uma pequena empresa, o proprietário da empresa (a pessoa que comprou sua assinatura) é um administrador global. Em uma grande empresa, as pessoas-chave no departamento de IT são administradores globais.</span><span class="sxs-lookup"><span data-stu-id="1e185-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="1e185-144">Selecione **Administrador personalizado** para ver uma lista de funções personalizadas para você.</span><span class="sxs-lookup"><span data-stu-id="1e185-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="1e185-145">Para uma descrição de cada função, consulte [Sobre funções de administrador.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="1e185-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="1e185-146">Atribuir funções de administrador para vários usuários</span><span class="sxs-lookup"><span data-stu-id="1e185-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="1e185-147">Se você conhece o PowerShell, consulte [Atribuir funções a contas de usuário com o PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1e185-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="1e185-148">Ele é ideal para atribuir funções a centenas de usuários.</span><span class="sxs-lookup"><span data-stu-id="1e185-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="1e185-149">Use as instruções a seguir para atribuir funções a dezenas de usuários.</span><span class="sxs-lookup"><span data-stu-id="1e185-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="1e185-150">Verificar funções de administrador em sua organização</span><span class="sxs-lookup"><span data-stu-id="1e185-150">Check admin roles in your organization</span></span>

<span data-ttu-id="1e185-151">Talvez você não tenha as permissões corretas para atribuir funções de administrador a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="1e185-151">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="1e185-152">Verifique se você tem as permissões corretas ou peça a outro administrador para atribuir funções para você.</span><span class="sxs-lookup"><span data-stu-id="1e185-152">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="1e185-153">Você pode verificar permissões de função de administrador de duas maneiras diferentes:</span><span class="sxs-lookup"><span data-stu-id="1e185-153">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="1e185-154">Você pode ir até os detalhes do usuário e procurar em **Funções** na **página Conta.**</span><span class="sxs-lookup"><span data-stu-id="1e185-154">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="1e185-155">Ou você pode ir para **Funções** e selecionar a função de administrador e selecionar administradores atribuídos para ver quais usuários são atribuídos.</span><span class="sxs-lookup"><span data-stu-id="1e185-155">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="1e185-156">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="1e185-156">Related content</span></span>

<span data-ttu-id="1e185-157">[Sobre Microsoft 365 de administrador](about-admin-roles.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="1e185-157">[About Microsoft 365 admin roles](about-admin-roles.md) (article)</span></span>

<span data-ttu-id="1e185-158">[Permissões de função de administrador Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (artigo)</span><span class="sxs-lookup"><span data-stu-id="1e185-158">[Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (article)</span></span>

<span data-ttu-id="1e185-159">[Atribuir funções a contas de usuário com o PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="1e185-159">[Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (article)</span></span>

<span data-ttu-id="1e185-160">[Autorizar ou remover relacionamentos de parceiros](../misc/add-partner.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="1e185-160">[Authorize or remove partner relationships](../misc/add-partner.md) (article)</span></span>