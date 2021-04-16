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
ms.openlocfilehash: 44428654946d31ad249bfd3e7a3609da3e3634a6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860542"
---
# <a name="close-your-account"></a><span data-ttu-id="1cda5-103">Fechar sua conta</span><span class="sxs-lookup"><span data-stu-id="1cda5-103">Close your account</span></span>

<span data-ttu-id="1cda5-104">Quando você fecha a sua conta do Microsoft, todas as informações relacionadas à sua conta são excluídas.</span><span class="sxs-lookup"><span data-stu-id="1cda5-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="1cda5-105">Essas informações incluem assinaturas, licenças, métodos de pagamento, usuários e dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="1cda5-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1cda5-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1cda5-106">Before you begin</span></span>

<span data-ttu-id="1cda5-107">Antes de iniciar esse processo, faça backup dos dados que queira preservar.</span><span class="sxs-lookup"><span data-stu-id="1cda5-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="1cda5-108">Você deve ser um administrador Global ou de Cobrança para realizar as etapas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="1cda5-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="1cda5-109">Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1cda5-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="1cda5-110">Etapa 1: Excluir usuários</span><span class="sxs-lookup"><span data-stu-id="1cda5-110">Step 1: Delete users</span></span>

<span data-ttu-id="1cda5-111">Exclua todos os usuários, exceto um administrador global.</span><span class="sxs-lookup"><span data-stu-id="1cda5-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="1cda5-112">O administrador global conclui as etapas para fechar a conta.</span><span class="sxs-lookup"><span data-stu-id="1cda5-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="1cda5-113">Antes de poder excluir o diretório no final deste processo, você deve excluir todos os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="1cda5-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="1cda5-114">Se os usuários estiverem sincronizados no local, primeiro desligue a sincronização e exclua os usuários no diretório de nuvem usando o portal do Azure ou os cmdlets do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1cda5-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="1cda5-115">Para excluir usuários, consulte <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span><span class="sxs-lookup"><span data-stu-id="1cda5-115">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="1cda5-116">Você também pode usar o cmdlet <a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">Remove-MsolUser</a> PowerShell para excluir usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="1cda5-116">You can also use the <a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="1cda5-117">Se sua organização usa o Active Directory que se sincroniza com o Microsoft Azure Active Directory (Azure AD), exclua a conta de usuário do Active Directory, em vez disso.</span><span class="sxs-lookup"><span data-stu-id="1cda5-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="1cda5-118">Para obter instruções, consulte <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="1cda5-118">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="1cda5-119">Etapa 2: Cancelar todas as assinaturas ativas</span><span class="sxs-lookup"><span data-stu-id="1cda5-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="1cda5-120">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="1cda5-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="1cda5-121">Na guia **Produtos,** encontre uma assinatura ativa.</span><span class="sxs-lookup"><span data-stu-id="1cda5-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="1cda5-122">Selecione **Mais ações** (três pontos) e, em seguida, selecione **Cancelar assinatura**.</span><span class="sxs-lookup"><span data-stu-id="1cda5-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="1cda5-123">No painel **Cancelar assinatura**, escolha um motivo pelo qual você está cancelando.</span><span class="sxs-lookup"><span data-stu-id="1cda5-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="1cda5-124">Opcionalmente, forneça qualquer comentário.</span><span class="sxs-lookup"><span data-stu-id="1cda5-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="1cda5-125">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1cda5-125">Select **Save**.</span></span>
5. <span data-ttu-id="1cda5-126">Repita as etapas de 1 a 4 para cancelar todas as assinaturas ativas.</span><span class="sxs-lookup"><span data-stu-id="1cda5-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="1cda5-127">Etapa 3: Excluir todas as assinaturas desabilitadas</span><span class="sxs-lookup"><span data-stu-id="1cda5-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="1cda5-128">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="1cda5-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="1cda5-129">Na guia **Produtos,** selecione uma assinatura desabilitada.</span><span class="sxs-lookup"><span data-stu-id="1cda5-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="1cda5-130">Na página detalhes da assinatura, na seção **Configurações de assinatura e** pagamento, selecione **Excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="1cda5-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="1cda5-131">No painel **Excluir assinatura,** selecione **Excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="1cda5-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="1cda5-132">Na caixa **de diálogo Excluir assinatura,** selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="1cda5-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="1cda5-133">Para cada assinatura desabilitada, repita as etapas de 3 a 5 até que todas as assinaturas sejam excluídas.</span><span class="sxs-lookup"><span data-stu-id="1cda5-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="1cda5-134">Se você não puder excluir imediatamente uma assinatura desabilitada, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contate o suporte</a></span><span class="sxs-lookup"><span data-stu-id="1cda5-134">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="1cda5-135">Etapa 4: Desabilitar a autenticação multifa factor</span><span class="sxs-lookup"><span data-stu-id="1cda5-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="1cda5-136">Entre no centro de administração com uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1cda5-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="1cda5-137">Para verificar quais funções você tem, consulte [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="1cda5-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="1cda5-138">Vá para a **página Usuários**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">ativos.</a></span><span class="sxs-lookup"><span data-stu-id="1cda5-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="1cda5-139">Escolha **Autenticação multifa factor**.</span><span class="sxs-lookup"><span data-stu-id="1cda5-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="1cda5-140">Na página de autenticação multifação, desabilite todas as contas, exceto a conta de administrador global que você está usando no momento.</span><span class="sxs-lookup"><span data-stu-id="1cda5-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="1cda5-141">Você também pode <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">usar o PowerShell para desabilitar a autenticação multifa factor para vários usuários</a>.</span><span class="sxs-lookup"><span data-stu-id="1cda5-141">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="1cda5-142">Etapa 5: Excluir o diretório no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1cda5-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="1cda5-143">Entre no centro de <a href="https://aad.portal.azure.com/" target="_blank">administração do Azure AD</a> com uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1cda5-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="1cda5-144">Selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="1cda5-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="1cda5-145">Alternar para a organização que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="1cda5-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="1cda5-146">Selecione **Excluir locatário**.</span><span class="sxs-lookup"><span data-stu-id="1cda5-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="1cda5-147">Se sua organização falhar em uma ou mais verificações, você verá um link para mais informações sobre como passar as verificações.</span><span class="sxs-lookup"><span data-stu-id="1cda5-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="1cda5-148">Depois de passar todas as verificações, selecione **Excluir** para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="1cda5-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="1cda5-149">Depois de concluir essa etapa final, sua conta com a Microsoft será fechada e excluída.</span><span class="sxs-lookup"><span data-stu-id="1cda5-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>