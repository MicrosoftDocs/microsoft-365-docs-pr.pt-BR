---
title: Fechar sua conta
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: Quando você fecha sua conta com a Microsoft, todas as informações relacionadas à sua conta são excluídas, incluindo licenças, usuários e dados do usuário.
ms.date: 04/02/2021
ms.openlocfilehash: b212911707b5d6a967ab833a5a06bc76f5ceeb3b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624320"
---
# <a name="close-your-account"></a><span data-ttu-id="2229e-103">Fechar sua conta</span><span class="sxs-lookup"><span data-stu-id="2229e-103">Close your account</span></span>

<span data-ttu-id="2229e-104">Quando você fecha a sua conta do Microsoft, todas as informações relacionadas à sua conta são excluídas.</span><span class="sxs-lookup"><span data-stu-id="2229e-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="2229e-105">Essas informações incluem assinaturas, licenças, métodos de pagamento, usuários e dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="2229e-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2229e-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2229e-106">Before you begin</span></span>

<span data-ttu-id="2229e-107">Antes de iniciar esse processo, faça backup dos dados que queira preservar.</span><span class="sxs-lookup"><span data-stu-id="2229e-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="2229e-108">Você deve ser um administrador Global ou de Cobrança para realizar as etapas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="2229e-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="2229e-109">Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2229e-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="2229e-110">Etapa 1: Excluir usuários</span><span class="sxs-lookup"><span data-stu-id="2229e-110">Step 1: Delete users</span></span>

<span data-ttu-id="2229e-111">Exclua todos os usuários, exceto um administrador global.</span><span class="sxs-lookup"><span data-stu-id="2229e-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="2229e-112">O administrador global conclui as etapas para fechar a conta.</span><span class="sxs-lookup"><span data-stu-id="2229e-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="2229e-113">Antes de poder excluir o diretório no final deste processo, você deve excluir todos os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="2229e-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="2229e-114">Se os usuários estiverem sincronizados no local, primeiro desligue a sincronização e exclua os usuários no diretório de nuvem usando o portal do Azure ou Azure PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="2229e-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="2229e-115">Para excluir usuários, consulte [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span><span class="sxs-lookup"><span data-stu-id="2229e-115">To delete users, see [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span></span>

<span data-ttu-id="2229e-116">Você também pode usar o cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell para excluir usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="2229e-116">You can also use the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="2229e-117">Se sua organização usa o Active Directory que sincroniza com o Microsoft Azure Active Directory (Azure AD), exclua a conta de usuário do Active Directory, em vez disso.</span><span class="sxs-lookup"><span data-stu-id="2229e-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="2229e-118">Para obter instruções, consulte [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span><span class="sxs-lookup"><span data-stu-id="2229e-118">For instructions, see [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="2229e-119">Etapa 2: Cancelar todas as assinaturas ativas</span><span class="sxs-lookup"><span data-stu-id="2229e-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="2229e-120">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="2229e-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="2229e-121">Na guia **Produtos,** encontre uma assinatura ativa.</span><span class="sxs-lookup"><span data-stu-id="2229e-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="2229e-122">Selecione os três pontos (mais ações) e selecione **Cancelar assinatura**.</span><span class="sxs-lookup"><span data-stu-id="2229e-122">Select the three dots (more actions), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="2229e-p106">No painel **Cancelar assinatura**, escolha um motivo pelo qual você está cancelando. Se optar, forneça comentários.</span><span class="sxs-lookup"><span data-stu-id="2229e-p106">In the **Cancel subscription** pane, choose a reason why you're canceling. Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="2229e-125">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2229e-125">Select **Save**.</span></span>
5. <span data-ttu-id="2229e-126">Repita as etapas de 1 a 4 para cancelar todas as assinaturas ativas.</span><span class="sxs-lookup"><span data-stu-id="2229e-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="2229e-127">Etapa 3: Excluir todas as assinaturas desabilitadas</span><span class="sxs-lookup"><span data-stu-id="2229e-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="2229e-128">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="2229e-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="2229e-129">Na guia **Produtos,** selecione uma assinatura desabilitada.</span><span class="sxs-lookup"><span data-stu-id="2229e-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="2229e-130">Na página detalhes da assinatura, na seção **Configurações de assinatura e** pagamento, selecione **Excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="2229e-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="2229e-131">No painel **Excluir assinatura,** selecione **Excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="2229e-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="2229e-132">Na caixa **de diálogo Excluir assinatura,** selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2229e-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="2229e-133">Para cada assinatura desabilitada, repita as etapas de 3 a 5 até que todas as assinaturas sejam excluídas.</span><span class="sxs-lookup"><span data-stu-id="2229e-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="2229e-134">Se você não puder excluir imediatamente uma assinatura desabilitada, [contate o suporte](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="2229e-134">If you're unable to immediately delete a disabled subscription, [contact support](../business-video/get-help-support.md).</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="2229e-135">Etapa 4: Desabilitar a autenticação multifa factor</span><span class="sxs-lookup"><span data-stu-id="2229e-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="2229e-136">Entre no centro de administração com uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="2229e-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="2229e-137">Para verificar quais funções você tem, consulte [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="2229e-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="2229e-138">Vá para a **página Usuários**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">ativos.</a></span><span class="sxs-lookup"><span data-stu-id="2229e-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="2229e-139">Escolha **Autenticação multifa factor**.</span><span class="sxs-lookup"><span data-stu-id="2229e-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="2229e-140">Na página de autenticação multifação, desabilite todas as contas, exceto a conta de administrador global que você está usando no momento.</span><span class="sxs-lookup"><span data-stu-id="2229e-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="2229e-141">Você também pode [usar o PowerShell para desabilitar a autenticação multifa factor para vários usuários](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="2229e-141">You can also [use PowerShell to disable multi-factor authentication for multiple users](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span></span>


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="2229e-142">Etapa 5: Excluir o diretório no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2229e-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="2229e-143">Entre no centro de <a href="https://aad.portal.azure.com/" target="_blank">administração do Azure AD</a> com uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="2229e-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="2229e-144">Selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2229e-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="2229e-145">Alternar para a organização que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="2229e-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="2229e-146">Selecione **Excluir locatário**.</span><span class="sxs-lookup"><span data-stu-id="2229e-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="2229e-147">Se sua organização falhar em uma ou mais verificações, você verá um link para mais informações sobre como passar as verificações.</span><span class="sxs-lookup"><span data-stu-id="2229e-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="2229e-148">Depois de passar todas as verificações, selecione **Excluir** para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="2229e-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="2229e-149">Depois de concluir essa etapa final, sua conta com a Microsoft será fechada e excluída.</span><span class="sxs-lookup"><span data-stu-id="2229e-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>

## <a name="related-content"></a><span data-ttu-id="2229e-150">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="2229e-150">Related content</span></span> 

<span data-ttu-id="2229e-151">[Entenda sua fatura ou fatura para Microsoft 365 para empresas](./billing-and-payments/understand-your-invoice2.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="2229e-151">[Understand your bill or invoice for Microsoft 365 for business](./billing-and-payments/understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="2229e-152">[Cancelar sua assinatura](./subscriptions/cancel-your-subscription.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="2229e-152">[Cancel your subscription](./subscriptions/cancel-your-subscription.md) (article)</span></span>

