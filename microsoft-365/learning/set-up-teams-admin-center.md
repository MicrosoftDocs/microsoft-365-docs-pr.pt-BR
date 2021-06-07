---
title: Configurar o Microsoft Viva Learning (Visualização) no Teams de administração
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Saiba como configurar o Microsoft Viva Learning (Visualização) no Teams de administração.
ms.openlocfilehash: 860f16bee7d93f2212072c5d738263402704272f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789226"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="b6242-103">Configurar o Microsoft Viva Learning (Visualização) no Teams de administração</span><span class="sxs-lookup"><span data-stu-id="b6242-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="b6242-104">As informações neste artigo se relacionam a um produto de visualização que pode ser substancialmente modificado antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="b6242-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="b6242-105">O Teams administrador precisa executar determinadas etapas para habilitar o Viva Learning (Visualização) para seus usuários no locatário.</span><span class="sxs-lookup"><span data-stu-id="b6242-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="b6242-106">Essas etapas variam de acordo com a forma como o locatário está habilitado: [*Visualização Pública*](set-up-teams-admin-center.md#public-preview-tenants) ou [ *Visualização Privada* (ou Beta).](set-up-teams-admin-center.md#private-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="b6242-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="b6242-107">Locatários de Visualização Pública</span><span class="sxs-lookup"><span data-stu-id="b6242-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="b6242-108">Etapas de administrador para locatários de Visualização Pública</span><span class="sxs-lookup"><span data-stu-id="b6242-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="b6242-109">Como o Viva Learning (Visualização) ainda não está disponível geralmente, determinadas etapas são necessárias para habilitar os recursos e definir permissões para usuários ou grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="b6242-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="b6242-110">Habilitar recursos de Visualização Pública para usuários do Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b6242-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="b6242-111">a.</span><span class="sxs-lookup"><span data-stu-id="b6242-111">a.</span></span> <span data-ttu-id="b6242-112">Modifique Teams política de atualização para habilitar recursos de Visualização Pública.</span><span class="sxs-lookup"><span data-stu-id="b6242-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="b6242-113">Consulte [Microsoft Teams Visualização Pública](/microsoftteams/public-preview-doc-updates).</span><span class="sxs-lookup"><span data-stu-id="b6242-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="b6242-114">b.</span><span class="sxs-lookup"><span data-stu-id="b6242-114">b.</span></span> <span data-ttu-id="b6242-115">Habilita a política de atualização para usuários ou grupos que realizarão testes do Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b6242-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="b6242-116">Consulte [Atribuir políticas a usuários e grupos](/microsoftteams/assign-policies-users-and-groups).</span><span class="sxs-lookup"><span data-stu-id="b6242-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="b6242-117">Modifique a política de permissão do aplicativo para usuários do Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b6242-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="b6242-118">a.</span><span class="sxs-lookup"><span data-stu-id="b6242-118">a.</span></span> <span data-ttu-id="b6242-119">A menos que ele faça parte da política global, permita que todos os aplicativos da Microsoft na política de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b6242-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="b6242-120">Consulte [Gerenciar políticas de permissão do aplicativo em Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="b6242-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="b6242-121">b.</span><span class="sxs-lookup"><span data-stu-id="b6242-121">b.</span></span> <span data-ttu-id="b6242-122">Habilita a política de permissão do aplicativo para usuários ou grupos que realizarão testes do Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b6242-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="b6242-123">Consulte [Atribuir políticas a usuários e grupos](/microsoftteams/assign-policies-users-and-groups).</span><span class="sxs-lookup"><span data-stu-id="b6242-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3.  <span data-ttu-id="b6242-124">Notifique os usuários que testarão o Viva Learning (Visualização) para alternar seu cliente de com build para [Visualização Pública para Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span><span class="sxs-lookup"><span data-stu-id="b6242-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6242-125">Para locatários de Visualização Pública, o Viva  Learning (Visualização) não será exibido em aplicativos gerenciados no Teams de administração até o lançamento final do produto.</span><span class="sxs-lookup"><span data-stu-id="b6242-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="b6242-126">No entanto, os usuários habilitados para Visualização Pública podem encontrar o Viva Learning (Visualização) no Teams de aplicativos e usá-lo, depois que as políticas e permissões corretas foram configuradas.</span><span class="sxs-lookup"><span data-stu-id="b6242-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="b6242-127">Etapas do usuário para locatários de Visualização Pública</span><span class="sxs-lookup"><span data-stu-id="b6242-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="b6242-128">Os usuários que foram habilitados para testes de Visualização Pública [](/microsoftteams/public-preview-doc-updates#enable-public-preview) — habilitando as políticas descritas anteriormente [—](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) precisam alternar para Visualização Pública em seu cliente Teams público.</span><span class="sxs-lookup"><span data-stu-id="b6242-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="b6242-129">Os usuários devem selecionar suas imagens de perfil > **Sobre**  >  **Visualização Pública.**</span><span class="sxs-lookup"><span data-stu-id="b6242-129">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
    ![Navegação superior no aplicativo Teams mostrando o perfil do usuário](../media/learning/learning-app-select-profile-teams.png)
    
2. <span data-ttu-id="b6242-131">Os usuários devem aceitar os termos e condições de Visualização Pública.</span><span class="sxs-lookup"><span data-stu-id="b6242-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![Alternar para a com build de visualização pública](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="b6242-133">Os usuários agora podem encontrar o Viva Learning (Visualização) no Teams app store e começar a usá-lo.</span><span class="sxs-lookup"><span data-stu-id="b6242-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="b6242-134">Locatários de Visualização Privada</span><span class="sxs-lookup"><span data-stu-id="b6242-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="b6242-135">Etapas de administrador para locatários de Visualização Privada (ou Beta)</span><span class="sxs-lookup"><span data-stu-id="b6242-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="b6242-136">Para locatários de Visualização Privada, não há políticas adicionais que precisam ser habilitadas.</span><span class="sxs-lookup"><span data-stu-id="b6242-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="b6242-137">No entanto, o Viva Learning (Visualização) deve ser disponibilizado para os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b6242-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="b6242-138">Na navegação à esquerda do centro de administração Teams, acesse **Teams**  >  **aplicativos Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b6242-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navegação à esquerda no centro de Teams de administração mostrando Teams aplicativos e Gerenciar aplicativos.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="b6242-140">Na página **Gerenciar aplicativos,** na caixa de pesquisa, digite *Viva Learning* e selecione Viva **Learning (Visualização).**</span><span class="sxs-lookup"><span data-stu-id="b6242-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Gerenciar a página aplicativos no Teams de administração mostrando a caixa de pesquisa.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="b6242-142">Na página **Viva Aprendizagem (Visualização),** em **Status,** selecione **Permitido** ativar o Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b6242-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   ![Página de aprendizado no centro Teams de administração mostrando configurações de Status e Aplicativo.](../media/learning/learning-app-teams-learning-page.png)


<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a><span data-ttu-id="b6242-144">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b6242-144">Next step</span></span>

[<span data-ttu-id="b6242-145">Configurar fontes de conteúdo de aprendizagem para o Viva Learning (Visualização) no Microsoft 365 de administração</span><span class="sxs-lookup"><span data-stu-id="b6242-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
