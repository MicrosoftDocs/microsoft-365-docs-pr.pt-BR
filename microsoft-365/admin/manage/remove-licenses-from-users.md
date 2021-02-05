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
description: Saiba como desa designar licenças de contas de usuário.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114472"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="c27ae-103">Cancelar a atribuição de licenças de usuários</span><span class="sxs-lookup"><span data-stu-id="c27ae-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c27ae-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="c27ae-104">The admin center is changing.</span></span> <span data-ttu-id="c27ae-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="c27ae-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="c27ae-106">Você pode desa designar licenças de usuários na página Usuários **ativos** ou **na página Licenças.**</span><span class="sxs-lookup"><span data-stu-id="c27ae-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="c27ae-107">O método usado depende se você deseja desa designar licenças de produto de usuários específicos ou desa designar licenças de usuários de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="c27ae-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="c27ae-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c27ae-108">Before you begin</span></span>

- <span data-ttu-id="c27ae-109">Você deve ser um administrador global, de licença, de usuário para desa designar licenças.</span><span class="sxs-lookup"><span data-stu-id="c27ae-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="c27ae-110">Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c27ae-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="c27ae-111">Você pode [remover licenças a contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c27ae-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span></span>
- <span data-ttu-id="c27ae-112">Você também pode [excluir contas de usuário](../add-users/delete-a-user.md) que foram atribuídas a uma licença para disponibilizar sua licença para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="c27ae-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="c27ae-113">Quando você exclui uma conta de usuário, a licença fica imediatamente disponível para ser atribuído a outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="c27ae-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="c27ae-114">Usar a página Licenças para desa designar licenças</span><span class="sxs-lookup"><span data-stu-id="c27ae-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="c27ae-115">Ao usar a **página Licenças** para desa designar licenças, você desafere licenças para um produto específico para até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="c27ae-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="c27ae-116">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="c27ae-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="c27ae-117">Selecione o produto para o qual você deseja desaignar licenças.</span><span class="sxs-lookup"><span data-stu-id="c27ae-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="c27ae-118">Selecione os usuários para os quais você deseja desaignar licenças.</span><span class="sxs-lookup"><span data-stu-id="c27ae-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="c27ae-119">Selecione **Unassign licenses**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="c27ae-120">In the **Unassign licenses** box, select **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="c27ae-121">Usar a página Usuários ativos para desa designar licenças</span><span class="sxs-lookup"><span data-stu-id="c27ae-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="c27ae-122">Ao usar a página **Usuários ativos** para desa designar licenças, você desafere licenças de produto dos usuários.</span><span class="sxs-lookup"><span data-stu-id="c27ae-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="c27ae-123">Desa designar licenças de um usuário</span><span class="sxs-lookup"><span data-stu-id="c27ae-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="c27ae-124">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="c27ae-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c27ae-125">Selecione a linha do usuário para o que você deseja desa designar uma licença.</span><span class="sxs-lookup"><span data-stu-id="c27ae-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="c27ae-126">No painel direito, selecione **Licenças e Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="c27ae-127">Expanda **a seção Licenças,** des clear the boxes for the licenses that you want to unasign, then select **Save changes**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="c27ae-128">Desa designar licenças de um usuário</span><span class="sxs-lookup"><span data-stu-id="c27ae-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="c27ae-129">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="c27ae-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c27ae-130">Escolha o usuário para o que você deseja retirar a licença.</span><span class="sxs-lookup"><span data-stu-id="c27ae-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="c27ae-131">À direita, na linha **Licenças de** produto, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="c27ae-132">No painel **Licenças de** produto, alterne  o botão para a posição Desligado para a licença que você deseja desa designar para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c27ae-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="c27ae-133">Por exemplo, se você desligar a licença do Office 365 Enterprise E3, ela desa designa essa licença e todos os serviços sob essa licença para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="c27ae-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="c27ae-134">Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="c27ae-135">Desa designar licenças de um usuário</span><span class="sxs-lookup"><span data-stu-id="c27ae-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="c27ae-136">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="c27ae-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c27ae-137">Escolha o usuário para o que você deseja retirar a licença.</span><span class="sxs-lookup"><span data-stu-id="c27ae-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="c27ae-138">À direita, na linha **Licenças de** produto, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="c27ae-139">No painel **Licenças de** produto, alterne  o botão para a posição Desligado para a licença que você deseja desa designar para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c27ae-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="c27ae-140">Por exemplo, se você desligar a licença do Office 365 Enterprise E3, ela desa designa essa licença e todos os serviços sob essa licença para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="c27ae-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="c27ae-141">Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="c27ae-142">Desa designar licenças de vários usuários</span><span class="sxs-lookup"><span data-stu-id="c27ae-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="c27ae-143">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="c27ae-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c27ae-144">Selecione os círculos ao lado dos nomes dos usuários para os quem você deseja rea designar licenças.</span><span class="sxs-lookup"><span data-stu-id="c27ae-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="c27ae-145">Na parte superior, selecione **mais opções (...)**, em seguida, selecione **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="c27ae-146">No painel **Gerenciar licenças de produtos**, selecione **Substituir atribuições de licença de produto existentes** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c27ae-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="c27ae-148">Desa designar licenças de vários usuários</span><span class="sxs-lookup"><span data-stu-id="c27ae-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="c27ae-149">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="c27ae-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c27ae-150">Selecione as caixas ao lado dos nomes dos usuários para os que você deseja desa designar todas as licenças.</span><span class="sxs-lookup"><span data-stu-id="c27ae-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="c27ae-151">No painel **Ações em massa**, escolha **Editar licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="c27ae-152">No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c27ae-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="c27ae-154">Desa designar licenças de vários usuários</span><span class="sxs-lookup"><span data-stu-id="c27ae-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="c27ae-155">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="c27ae-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c27ae-156">Selecione as caixas ao lado dos nomes dos usuários para os que você deseja desa designar todas as licenças.</span><span class="sxs-lookup"><span data-stu-id="c27ae-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="c27ae-157">No painel **Ações em massa**, escolha **Editar licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="c27ae-158">No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c27ae-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="c27ae-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="c27ae-160">O que acontece com os dados de um usuário quando você remove a licença dele?</span><span class="sxs-lookup"><span data-stu-id="c27ae-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="c27ae-161">Quando uma licença é removida de um usuário, os dados associados a essa conta são mantidos por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c27ae-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="c27ae-162">Após o período de carência de 30 dias, os dados são excluídos e não podem ser recuperados.</span><span class="sxs-lookup"><span data-stu-id="c27ae-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="c27ae-163">Os arquivos salvos no OneDrive for Business não são excluídos, a menos que o usuário seja excluído do centro de administração do Microsoft 365 ou seja removido por meio da sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c27ae-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="c27ae-164">Para saber mais, confira a retenção e [a exclusão do OneDrive.](https://docs.microsoft.com/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="c27ae-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="c27ae-165">Quando a licença é removida, a caixa de correio do usuário não é mais pesquisável usando uma ferramenta de Descoberta Eletrônico, como Pesquisa de Conteúdo ou Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="c27ae-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="c27ae-166">Para obter mais informações, consulte "Pesquisar caixas de correio desconectadas ou sem licença" na Pesquisa de [Conteúdo no Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="c27ae-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="c27ae-167">Se você tiver uma assinatura Enterprise, como o Office 365 Enterprise E3, o Exchange Online permite preservar os dados da caixa de correio de uma conta de usuário excluída usando caixas de correio [inativas.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="c27ae-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="c27ae-168">Para obter mais informações, consulte Criar e gerenciar caixas de correio [inativas no Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="c27ae-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="c27ae-169">Para saber como bloquear o acesso de um usuário aos dados do Microsoft 365 após a remoção da licença e como obter acesso aos dados posteriormente, confira Remover um [ex-funcionário.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="c27ae-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="c27ae-170">Se você remover a licença de um usuário e ele ainda tiver aplicativos do Office [instalados,](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) ele verá erros de ativação e produto não licenciamento no Office ao usar os aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="c27ae-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c27ae-171">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c27ae-171">Next steps</span></span>

<span data-ttu-id="c27ae-172">Se você não for reatribuir as [licenças](../../managed-desktop/get-started/assign-licenses.md)nãoutiladas a outros usuários, considere remover as [licenças](../../commerce/licenses/buy-licenses.md) da sua assinatura para que você não esteja pagando por mais licenças do que precisa.</span><span class="sxs-lookup"><span data-stu-id="c27ae-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="c27ae-173">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="c27ae-173">Related content</span></span>

<span data-ttu-id="c27ae-174">[Remover licenças da sua assinatura](../../commerce/licenses/remove-licenses-from-subscription.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="c27ae-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="c27ae-175">[Atribuir licenças a usuários](assign-licenses-to-users.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="c27ae-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="c27ae-176">[Compreender assinaturas e licenças no Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="c27ae-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>