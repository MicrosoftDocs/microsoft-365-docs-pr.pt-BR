---
title: Cancelar a atribuição de licenças de usuários
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: O método que você usa para desasignar licenças de produto depende se você desa desa desemarcar licenças de usuários específicos ou de um produto específico.
ms.date: 07/01/2020
ms.openlocfilehash: f79ffecc22fe4531076ccacd83c25e44b81052a6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53006968"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="d5885-103">Cancelar a atribuição de licenças de usuários</span><span class="sxs-lookup"><span data-stu-id="d5885-103">Unassign licenses from users</span></span>

<span data-ttu-id="d5885-104">Você pode desasignar licenças  de usuários na página Usuários ativos ou na página **Licenças.**</span><span class="sxs-lookup"><span data-stu-id="d5885-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="d5885-105">O método usado depende se você deseja desasincar licenças de produtos de usuários específicos ou desasincar licenças de usuários de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="d5885-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="d5885-106">Como administrador, você não pode atribuir ou cancelar a atribuição de licenças para uma assinatura de compra de autoatendimento comprada por um usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d5885-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="d5885-107">Você pode [assumir uma assinatura de compra de autoatendimento](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), e, em seguida, atribuir ou cancelar a atribuição de licenças.</span><span class="sxs-lookup"><span data-stu-id="d5885-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d5885-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d5885-108">Before you begin</span></span>

- <span data-ttu-id="d5885-109">Você deve ser um administrador global, licença, usuário para desasincar licenças.</span><span class="sxs-lookup"><span data-stu-id="d5885-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="d5885-110">Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d5885-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="d5885-111">Você pode [remover licenças a contas de usuário com o Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d5885-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="d5885-112">Você também pode [excluir contas de usuário](../add-users/delete-a-user.md) que foram atribuídas a uma licença para disponibilizar sua licença para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="d5885-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="d5885-113">Quando você exclui uma conta de usuário, sua licença está disponível imediatamente para atribuir a outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="d5885-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="d5885-114">Usar a página Licenças para desasincar licenças</span><span class="sxs-lookup"><span data-stu-id="d5885-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="d5885-115">Quando você usa a página **Licenças** para desasincar licenças, desaigna licenças para um produto específico para até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="d5885-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d5885-116">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="d5885-116">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="d5885-117">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="d5885-117">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="d5885-118">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="d5885-118">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="d5885-119">Selecione o produto para o qual você deseja desasincar licenças.</span><span class="sxs-lookup"><span data-stu-id="d5885-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="d5885-120">Selecione os usuários para os quais você deseja desasincar licenças.</span><span class="sxs-lookup"><span data-stu-id="d5885-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="d5885-121">Selecione **Unassign licenses**.</span><span class="sxs-lookup"><span data-stu-id="d5885-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="d5885-122">Na caixa **Licenças não assinadas,** selecione **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="d5885-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="d5885-123">Usar a página Usuários ativos para desasinalhar licenças</span><span class="sxs-lookup"><span data-stu-id="d5885-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="d5885-124">Quando você usa a **página Usuários ativos** para desaignar licenças, você desaigna licenças de produtos de usuários.</span><span class="sxs-lookup"><span data-stu-id="d5885-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="d5885-125">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="d5885-125">Unassign licenses from one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d5885-126">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="d5885-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="d5885-127">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="d5885-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="d5885-128">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="d5885-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="d5885-129">Selecione a linha do usuário para o que você deseja desaignar uma licença.</span><span class="sxs-lookup"><span data-stu-id="d5885-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="d5885-130">No painel direito, selecione **Licenças e Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="d5885-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="d5885-131">Expanda **a seção Licenças,** limpe as caixas das licenças que você deseja desasinalhar e selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="d5885-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="d5885-132">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="d5885-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d5885-133">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="d5885-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="d5885-134">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="d5885-134">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="d5885-135">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="d5885-135">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="d5885-136">Selecione os círculos ao lado dos nomes dos usuários para os que você deseja desasinalhar licenças.</span><span class="sxs-lookup"><span data-stu-id="d5885-136">Select the circles next to the names of the users who you want to unassign licenses for.</span></span>
3. <span data-ttu-id="d5885-137">Na parte superior, selecione **Gerenciar licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="d5885-137">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="d5885-138">No painel **Gerenciar licenças de** produto, selecione **Unassign all** Save  >  **changes**.</span><span class="sxs-lookup"><span data-stu-id="d5885-138">In the **Manage product licenses** pane, select **Unassign all** > **Save changes**.</span></span>
5. <span data-ttu-id="d5885-139">Na parte inferior do painel, selecione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="d5885-139">At the bottom of the pane, select **Done**.</span></span>  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="d5885-140">O que acontece com os dados de um usuário ao remover a licença?</span><span class="sxs-lookup"><span data-stu-id="d5885-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="d5885-141">Quando uma licença é removida de um usuário, Exchange dados online associados a essa conta são mantidos por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="d5885-141">When a license is removed from a user, Exchange online data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="d5885-142">Após o período de carência de 30 dias, os dados são excluídos e não podem ser recuperados.</span><span class="sxs-lookup"><span data-stu-id="d5885-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="d5885-143">Os arquivos salvos OneDrive for Business não são excluídos, a menos que o usuário seja excluído do Centro de administração do Microsoft 365 ou seja removido por meio da sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d5885-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="d5885-144">Para obter mais informações, [consulte OneDrive retenção e exclusão.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="d5885-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="d5885-145">Quando a licença é removida, a caixa de correio do usuário não é mais pesquisável usando uma ferramenta de Descoberta Eletrônico, como Pesquisa de Conteúdo ou Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="d5885-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="d5885-146">Para obter mais informações, consulte "Pesquisar caixas de correio desconectadas ou des licenciadas" em Pesquisa de [Conteúdo em Microsoft 365](../../compliance/content-search.md).</span><span class="sxs-lookup"><span data-stu-id="d5885-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="d5885-147">Se você tiver uma assinatura Enterprise, como Office 365 Enterprise E3, Exchange Online permite preservar os dados de caixa de correio de uma conta de usuário excluída usando caixas de correio [inativas](../../compliance/inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d5885-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="d5885-148">Para obter mais informações, [consulte Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="d5885-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="d5885-149">Para saber como bloquear o acesso de um usuário a Microsoft 365 dados após a remoção da licença e como obter acesso aos dados posteriormente, consulte [Remove a former employee](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="d5885-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="d5885-150">Se você remover a licença de um usuário e eles ainda Office [aplicativos instalados,](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) eles verão erros de ativação e produto não licenciado no Office quando eles usam Office aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d5885-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d5885-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d5885-151">Next steps</span></span>

<span data-ttu-id="d5885-152">Se você não vai reatribuir as [licenças](../../managed-desktop/get-started/assign-licenses.md)nãousadas para outros usuários , considere remover as [licenças](../../commerce/licenses/buy-licenses.md) da sua assinatura para que você não esteja pagando por mais licenças do que precisa.</span><span class="sxs-lookup"><span data-stu-id="d5885-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="d5885-153">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="d5885-153">Related content</span></span>

<span data-ttu-id="d5885-154">[Remover licenças de sua assinatura](../../commerce/licenses/buy-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="d5885-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="d5885-155">[Atribuir licenças aos usuários](assign-licenses-to-users.md) (artigo) </span><span class="sxs-lookup"><span data-stu-id="d5885-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="d5885-156">[Compreender assinaturas e licenças no Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="d5885-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
