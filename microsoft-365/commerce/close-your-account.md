---
title: Fechar sua conta
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Saiba como fechar sua conta com a Microsoft.
ms.openlocfilehash: 905b3d1dfef44a6b1f78c5afe5f7673aec6b8894
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809204"
---
# <a name="close-your-account"></a><span data-ttu-id="3afad-103">Fechar sua conta</span><span class="sxs-lookup"><span data-stu-id="3afad-103">Close your account</span></span>

<span data-ttu-id="3afad-104">Quando você fecha sua conta com a Microsoft, todas as informações relacionadas à sua conta são excluídas.</span><span class="sxs-lookup"><span data-stu-id="3afad-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="3afad-105">Essas informações incluem assinaturas, licenças, métodos de pagamento, usuários e dados de usuário.</span><span class="sxs-lookup"><span data-stu-id="3afad-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="3afad-106">Antes de iniciar esse processo, certifique-se de fazer o backup de todos os dados que deseja preservar.</span><span class="sxs-lookup"><span data-stu-id="3afad-106">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="3afad-107">Etapa 1: excluir usuários</span><span class="sxs-lookup"><span data-stu-id="3afad-107">Step 1: Delete users</span></span>

<span data-ttu-id="3afad-108">Exclua todos os usuários, exceto um administrador global, que conclua as etapas para fechar a conta.</span><span class="sxs-lookup"><span data-stu-id="3afad-108">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="3afad-109">Para poder excluir o diretório no final desse processo, você deve excluir todos os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="3afad-109">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="3afad-110">Se os usuários forem sincronizados no local, primeiro desative a sincronização e exclua os usuários no diretório de nuvem usando o portal do Azure ou cmdlets do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3afad-110">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="3afad-111">Para excluir usuários, consulte <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">administrador de gerenciamento de usuário: excluir um ou mais usuários</a>.</span><span class="sxs-lookup"><span data-stu-id="3afad-111">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="3afad-112">Você também pode usar o cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> do PowerShell para excluir usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="3afad-112">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="3afad-113">Se sua organização usa o Active Directory que sincroniza com o Azure AD, exclua a conta de usuário do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3afad-113">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="3afad-114">Para obter instruções, consulte <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">exclusão em massa de usuários no Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="3afad-114">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="3afad-115">Etapa 2: cancelar todas as assinaturas ativas</span><span class="sxs-lookup"><span data-stu-id="3afad-115">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="3afad-116">No centro de administração, vá para a página de serviços de **cobrança** > de<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">produtos &</a> .</span><span class="sxs-lookup"><span data-stu-id="3afad-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="3afad-117">Se a lista de assinaturas estiver no modo de exibição de **tabela** , no lado direito, selecione **cartões**.</span><span class="sxs-lookup"><span data-stu-id="3afad-117">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="3afad-118">Encontre uma assinatura ativa e, na seção **configurações & ações** , selecione **cancelar assinatura**.</span><span class="sxs-lookup"><span data-stu-id="3afad-118">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="3afad-119">Siga as instruções para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="3afad-119">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="3afad-120">Repita as etapas 1 a 4 para cancelar todas as assinaturas ativas.</span><span class="sxs-lookup"><span data-stu-id="3afad-120">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="3afad-121">Etapa 3: excluir todas as assinaturas desabilitadas</span><span class="sxs-lookup"><span data-stu-id="3afad-121">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="3afad-122">No centro de administração, vá para a página de serviços de **cobrança** > de<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">produtos &</a> .</span><span class="sxs-lookup"><span data-stu-id="3afad-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="3afad-123">Se a lista de assinaturas estiver no modo de exibição de **tabela** , no lado direito, selecione **cartões**.</span><span class="sxs-lookup"><span data-stu-id="3afad-123">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="3afad-124">Ao lado de **status da assinatura**, selecione **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="3afad-124">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="3afad-125">Encontre uma assinatura desabilitada e, na seção **configurações & ações** , selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="3afad-125">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="3afad-126">Na caixa de diálogo **excluir inscrição** , marque a caixa **de seleção eu entendo o impacto** e, em seguida, selecione **excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="3afad-126">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="3afad-127">Para cada assinatura desabilitada, repita as etapas 4 e 5 até que todas as assinaturas tenham sido excluídas.</span><span class="sxs-lookup"><span data-stu-id="3afad-127">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="3afad-128">Etapa 4: desabilitar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="3afad-128">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="3afad-129">No centro de administração, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">usuários ativos</a> do **usuário** > .</span><span class="sxs-lookup"><span data-stu-id="3afad-129">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="3afad-130">Escolha a **autenticação multifator**.</span><span class="sxs-lookup"><span data-stu-id="3afad-130">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="3afad-131">Na página autenticação multifator, desabilite todas as contas, exceto para a conta de administrador global que você está usando no momento.</span><span class="sxs-lookup"><span data-stu-id="3afad-131">On the multi-factor authentication page, disable all accounts except for the global admin account that you’re currently using.</span></span>

<span data-ttu-id="3afad-132">Você também pode <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">usar o PowerShell para desabilitar a autenticação multifator para vários usuários</a>.</span><span class="sxs-lookup"><span data-stu-id="3afad-132">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="3afad-133">Etapa 5: excluir o diretório no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3afad-133">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="3afad-134">Entre no centro de <a href="https://aad.portal.azure.com/" target="_blank">Administração do Azure ad</a> com uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="3afad-134">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="3afad-135">Selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3afad-135">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="3afad-136">Alterne para o diretório que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="3afad-136">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="3afad-137">Selecione **excluir diretório**.</span><span class="sxs-lookup"><span data-stu-id="3afad-137">Select **Delete directory**.</span></span>

5. <span data-ttu-id="3afad-138">Se o diretório falhar em uma ou mais verificações, você verá um link para obter mais informações sobre como passar as verificações.</span><span class="sxs-lookup"><span data-stu-id="3afad-138">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="3afad-139">Depois de passar em todas as verificações, selecione **excluir** para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="3afad-139">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="3afad-140">Após concluir esta etapa final, sua conta com a Microsoft será fechada e excluída.</span><span class="sxs-lookup"><span data-stu-id="3afad-140">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>