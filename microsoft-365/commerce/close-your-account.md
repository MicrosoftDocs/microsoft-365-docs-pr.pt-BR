---
title: Fechar sua conta
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Saiba como fechar sua conta com a Microsoft.
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376312"
---
# <a name="close-your-account"></a><span data-ttu-id="5bb8d-103">Fechar sua conta</span><span class="sxs-lookup"><span data-stu-id="5bb8d-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5bb8d-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-104">The admin center is changing.</span></span> <span data-ttu-id="5bb8d-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="5bb8d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="5bb8d-106">Quando você fecha a sua conta do Microsoft, todas as informações relacionadas à sua conta são excluídas.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="5bb8d-107">Essas informações incluem assinaturas, licenças, métodos de pagamento, usuários e dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5bb8d-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5bb8d-108">Before you begin</span></span>

<span data-ttu-id="5bb8d-109">Antes de iniciar esse processo, faça backup dos dados que queira preservar.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="5bb8d-110">Você deve ser um administrador global ou de cobrança para realizar as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="5bb8d-111">Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5bb8d-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="5bb8d-112">Etapa 1: excluir usuários</span><span class="sxs-lookup"><span data-stu-id="5bb8d-112">Step 1: Delete users</span></span>

<span data-ttu-id="5bb8d-113">Exclua todos os usuários, exceto um administrador global.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="5bb8d-114">O administrador global conclui as etapas para fechar a conta.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="5bb8d-115">Para poder excluir o diretório no final desse processo, você deve excluir todos os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="5bb8d-116">Se os usuários forem sincronizados no local, primeiro desative a sincronização e exclua os usuários no diretório de nuvem usando o portal do Azure ou cmdlets do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="5bb8d-117">Para excluir usuários, consulte <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">administrador de gerenciamento de usuário: excluir um ou mais usuários</a>.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-117">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="5bb8d-118">Você também pode usar o cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> do PowerShell para excluir usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="5bb8d-119">Se sua organização usa o Active Directory que sincroniza com o Active Directory do Microsoft Azure (Azure AD), exclua a conta de usuário do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="5bb8d-120">Para obter instruções, consulte <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">exclusão em massa de usuários no Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-120">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="5bb8d-121">Etapa 2: cancelar todas as assinaturas ativas</span><span class="sxs-lookup"><span data-stu-id="5bb8d-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="5bb8d-122">No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="5bb8d-123">Na guia **produtos** , encontre uma assinatura ativa.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="5bb8d-124">Selecione **Mais ações** (três pontos) e, em seguida, selecione **Cancelar assinatura**.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="5bb8d-125">No painel **Cancelar assinatura**, escolha um motivo pelo qual você está cancelando.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="5bb8d-126">Opcionalmente, forneça qualquer comentário.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="5bb8d-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-127">Select **Save**.</span></span>
5. <span data-ttu-id="5bb8d-128">Repita as etapas 1 a 4 para cancelar todas as assinaturas ativas.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="5bb8d-129">Etapa 3: excluir todas as assinaturas desabilitadas</span><span class="sxs-lookup"><span data-stu-id="5bb8d-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="5bb8d-130">No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="5bb8d-131">Na guia **produtos** , selecione uma assinatura desabilitada.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="5bb8d-132">Na página detalhes da assinatura, na seção **configurações de assinatura e pagamento** , selecione **excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="5bb8d-133">No painel **excluir assinatura** , selecione **excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="5bb8d-134">Na caixa de diálogo **excluir inscrição** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="5bb8d-135">Para cada assinatura desabilitada, repita as etapas de 3 a 5 até que todas as assinaturas sejam excluídas.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="5bb8d-136">Se não for possível excluir imediatamente uma assinatura desabilitada, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contate o suporte</a></span><span class="sxs-lookup"><span data-stu-id="5bb8d-136">If you're unable to immediately delete a disabled subscription, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="5bb8d-137">Etapa 4: desabilitar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="5bb8d-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="5bb8d-138">Entre no centro de administração com uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="5bb8d-139">Para verificar quais funções você tem, confira [verificar funções de administrador em sua organização](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="5bb8d-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="5bb8d-140">Vá para a **Users**  >  página <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">usuários ativos</a> do usuário.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="5bb8d-141">Escolha a **autenticação multifator**.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="5bb8d-142">Na página autenticação multifator, desabilite todas as contas, exceto para a conta de administrador global que você está usando no momento.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="5bb8d-143">Você também pode <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">usar o PowerShell para desabilitar a autenticação multifator para vários usuários</a>.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-143">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="5bb8d-144">Etapa 5: excluir o diretório no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5bb8d-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="5bb8d-145">Entre no centro de <a href="https://aad.portal.azure.com/" target="_blank">Administração do Azure ad</a> com uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="5bb8d-146">Selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="5bb8d-147">Alterne para a organização que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="5bb8d-148">Selecione **excluir locatário**.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="5bb8d-149">Se sua organização falhar em uma ou mais verificações, você verá um link para obter mais informações sobre como passar as verificações.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="5bb8d-150">Depois de passar em todas as verificações, selecione **excluir** para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="5bb8d-151">Após concluir esta etapa final, sua conta com a Microsoft será fechada e excluída.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>