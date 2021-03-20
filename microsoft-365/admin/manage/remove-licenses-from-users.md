---
title: Cancelar a atribuição de licenças de usuários
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Saiba como desaignar licenças de contas de usuário.
ms.date: 07/01/2020
ms.openlocfilehash: 858daaf0069ecba3e6ff65ce957462764b45c22c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915189"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="e94cf-103">Cancelar a atribuição de licenças de usuários</span><span class="sxs-lookup"><span data-stu-id="e94cf-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e94cf-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="e94cf-104">The admin center is changing.</span></span> <span data-ttu-id="e94cf-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e94cf-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="e94cf-106">Você pode desasignar licenças  de usuários na página Usuários ativos ou na página **Licenças.**</span><span class="sxs-lookup"><span data-stu-id="e94cf-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="e94cf-107">O método usado depende se você deseja desasincar licenças de produtos de usuários específicos ou desasincar licenças de usuários de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="e94cf-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="e94cf-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e94cf-108">Before you begin</span></span>

- <span data-ttu-id="e94cf-109">Você deve ser um administrador global, licença, usuário para desasincar licenças.</span><span class="sxs-lookup"><span data-stu-id="e94cf-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="e94cf-110">Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e94cf-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="e94cf-111">Você pode [remover licenças a contas de usuário com o Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e94cf-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="e94cf-112">Você também pode [excluir contas de usuário](../add-users/delete-a-user.md) que foram atribuídas a uma licença para disponibilizar sua licença para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="e94cf-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="e94cf-113">Quando você exclui uma conta de usuário, sua licença está disponível imediatamente para atribuir a outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="e94cf-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="e94cf-114">Usar a página Licenças para desasincar licenças</span><span class="sxs-lookup"><span data-stu-id="e94cf-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="e94cf-115">Quando você usa a página **Licenças** para desasincar licenças, desaigna licenças para um produto específico para até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="e94cf-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="e94cf-116">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="e94cf-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="e94cf-117">Selecione o produto para o qual você deseja desasincar licenças.</span><span class="sxs-lookup"><span data-stu-id="e94cf-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="e94cf-118">Selecione os usuários para os quais você deseja desasincar licenças.</span><span class="sxs-lookup"><span data-stu-id="e94cf-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="e94cf-119">Selecione **Unassign licenses**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="e94cf-120">Na caixa **Licenças não assinadas,** selecione **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="e94cf-121">Usar a página Usuários ativos para desasinalhar licenças</span><span class="sxs-lookup"><span data-stu-id="e94cf-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="e94cf-122">Quando você usa a **página Usuários ativos** para desaignar licenças, você desaigna licenças de produtos de usuários.</span><span class="sxs-lookup"><span data-stu-id="e94cf-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="e94cf-123">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="e94cf-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="e94cf-124">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="e94cf-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="e94cf-125">Selecione a linha do usuário para o que você deseja desaignar uma licença.</span><span class="sxs-lookup"><span data-stu-id="e94cf-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="e94cf-126">No painel direito, selecione **Licenças e Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="e94cf-127">Expanda **a seção Licenças,** limpe as caixas das licenças que você deseja desasinalhar e selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="e94cf-128">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="e94cf-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="e94cf-129">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="e94cf-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="e94cf-130">Escolha o usuário para o que você deseja desaignar a licença.</span><span class="sxs-lookup"><span data-stu-id="e94cf-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="e94cf-131">À direita, na linha **Licenças do** produto, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="e94cf-132">No painel **Licenças de** produto, alterne  a alternância para a posição Off da licença que você deseja desasinchar para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e94cf-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="e94cf-133">Por exemplo, se você desligar a licença do Office 365 Enterprise E3, ela desaigna essa licença e todos os serviços sob essa licença para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="e94cf-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="e94cf-134">Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="e94cf-135">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="e94cf-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="e94cf-136">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="e94cf-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="e94cf-137">Escolha o usuário para o que você deseja desaignar a licença.</span><span class="sxs-lookup"><span data-stu-id="e94cf-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="e94cf-138">À direita, na linha **Licenças do** produto, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="e94cf-139">No painel **Licenças de** produto, alterne  a alternância para a posição Off da licença que você deseja desasinchar para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e94cf-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="e94cf-140">Por exemplo, se você desligar a licença do Office 365 Enterprise E3, ela desaigna essa licença e todos os serviços sob essa licença para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="e94cf-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="e94cf-141">Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="e94cf-142">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="e94cf-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="e94cf-143">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="e94cf-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="e94cf-144">Selecione os círculos ao lado dos nomes dos usuários para os que você deseja desasinalhar licenças.</span><span class="sxs-lookup"><span data-stu-id="e94cf-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="e94cf-145">Na parte superior, selecione **mais opções (...)**, em seguida, selecione **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="e94cf-146">No painel **Gerenciar licenças de produtos**, selecione **Substituir atribuições de licença de produto existentes** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="e94cf-147">Na parte inferior do painel **Substituir produtos** existentes, marque a caixa de seleção Remover todas **as licenças** de produto da caixa de seleção Usuários e, em seguida, selecione **Substituir** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="e94cf-148">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="e94cf-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="e94cf-149">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="e94cf-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="e94cf-150">Selecione as caixas ao lado dos nomes dos usuários para os que você deseja desaignar todas as licenças.</span><span class="sxs-lookup"><span data-stu-id="e94cf-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="e94cf-151">No painel **Ações em massa**, escolha **Editar licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="e94cf-152">No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="e94cf-153">Na parte inferior do painel Substituir **produtos** existentes, marque a caixa de seleção Remover todas as **licenças** de produto da caixa de seleção usuários e, em seguida, selecione **Substituir** \> **Fechar** \> **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="e94cf-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="e94cf-154">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="e94cf-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="e94cf-155">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="e94cf-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="e94cf-156">Selecione as caixas ao lado dos nomes dos usuários para os que você deseja desaignar todas as licenças.</span><span class="sxs-lookup"><span data-stu-id="e94cf-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="e94cf-157">No painel **Ações em massa**, escolha **Editar licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="e94cf-158">No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e94cf-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="e94cf-159">Na parte inferior do painel Substituir **produtos** existentes, marque a caixa de seleção Remover todas as **licenças** de produto da caixa de seleção usuários e, em seguida, selecione **Substituir** \> **Fechar** \> **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="e94cf-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="e94cf-160">O que acontece com os dados de um usuário ao remover a licença?</span><span class="sxs-lookup"><span data-stu-id="e94cf-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="e94cf-161">Quando uma licença é removida de um usuário, os dados associados a essa conta são mantidos por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="e94cf-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="e94cf-162">Após o período de carência de 30 dias, os dados são excluídos e não podem ser recuperados.</span><span class="sxs-lookup"><span data-stu-id="e94cf-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="e94cf-163">Os arquivos salvos no OneDrive for Business não são excluídos, a menos que o usuário seja excluído do centro de administração do Microsoft 365 ou seja removido por meio da sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e94cf-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="e94cf-164">Para obter mais informações, consulte Retenção e exclusão do [OneDrive.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="e94cf-164">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="e94cf-165">Quando a licença é removida, a caixa de correio do usuário não é mais pesquisável usando uma ferramenta de Descoberta Eletrônico, como Pesquisa de Conteúdo ou Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="e94cf-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="e94cf-166">Para obter mais informações, consulte "Pesquisar caixas de correio desconectadas ou des licenciadas" na Pesquisa de [Conteúdo no Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="e94cf-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="e94cf-167">Se você tiver uma assinatura enterprise, como o Office 365 Enterprise E3, o Exchange Online permitirá que você preserve os dados de caixa de correio de uma conta de usuário excluída usando caixas de correio [inativas](../../compliance/inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e94cf-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="e94cf-168">Para obter mais informações, [consulte Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="e94cf-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="e94cf-169">Para saber como bloquear o acesso de um usuário aos dados do Microsoft 365 após a remoção da licença e como obter acesso aos dados posteriormente, consulte [Remove a former employee](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="e94cf-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="e94cf-170">Se você remover a licença de um usuário e eles ainda têm aplicativos do Office [instalados,](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) eles verão Erros de ativação e produto não licenciado no Office quando eles usam aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="e94cf-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e94cf-171">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e94cf-171">Next steps</span></span>

<span data-ttu-id="e94cf-172">Se você não vai reatribuir as [licenças](../../managed-desktop/get-started/assign-licenses.md)nãousadas para outros usuários , considere remover as [licenças](../../commerce/licenses/buy-licenses.md) da sua assinatura para que você não esteja pagando por mais licenças do que precisa.</span><span class="sxs-lookup"><span data-stu-id="e94cf-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="e94cf-173">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="e94cf-173">Related content</span></span>

<span data-ttu-id="e94cf-174">[Remover licenças de sua assinatura](../../commerce/licenses/buy-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="e94cf-174">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="e94cf-175">[Atribuir licenças aos usuários](assign-licenses-to-users.md) (artigo) </span><span class="sxs-lookup"><span data-stu-id="e94cf-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="e94cf-176">[Compreender assinaturas e licenças no Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="e94cf-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>