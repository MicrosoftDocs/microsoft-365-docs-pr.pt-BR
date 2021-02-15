---
title: Gerenciar grupos do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Saiba mais sobre como gerenciar grupos do Microsoft 365.
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328481"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="87dd2-103">Gerenciar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87dd2-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="87dd2-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="87dd2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="87dd2-105">Você pode gerenciar grupos do Microsoft 365 de várias maneiras diferentes, dependendo da sua configuração.</span><span class="sxs-lookup"><span data-stu-id="87dd2-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="87dd2-106">Você pode gerenciar contas de usuário no centro de administração do [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/add-users/)PowerShell, nos Serviços de Domínio do Active Directory (AD DS) ou no centro de administração do [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="87dd2-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="87dd2-107">Planejar onde e como você gerenciará seus grupos</span><span class="sxs-lookup"><span data-stu-id="87dd2-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="87dd2-108">Onde e como você pode gerenciar suas contas de usuário depende do modelo de identidade que você deseja usar para seu Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87dd2-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="87dd2-109">Os dois modelos gerais são somente na nuvem e híbridos.</span><span class="sxs-lookup"><span data-stu-id="87dd2-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="87dd2-110">Apenas Nuvem</span><span class="sxs-lookup"><span data-stu-id="87dd2-110">Cloud-only</span></span>

<span data-ttu-id="87dd2-111">Você cria e gerencia grupos com:</span><span class="sxs-lookup"><span data-stu-id="87dd2-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="87dd2-112">O Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87dd2-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="87dd2-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="87dd2-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="87dd2-114">Centro de Administração do Microsoft Azure AD</span><span class="sxs-lookup"><span data-stu-id="87dd2-114">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="87dd2-115">Híbrido</span><span class="sxs-lookup"><span data-stu-id="87dd2-115">Hybrid</span></span>

<span data-ttu-id="87dd2-116">Os grupos do AD DS são sincronizados com o Microsoft 365 a partir do AD DS, portanto, você deve usar ferramentas locais do AD DS para gerenciar esses grupos.</span><span class="sxs-lookup"><span data-stu-id="87dd2-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="87dd2-117">Você também pode criar e gerenciar grupos do Azure AD separados dos grupos do AD DS, mas que podem conter usuários e grupos do AD DS.</span><span class="sxs-lookup"><span data-stu-id="87dd2-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="87dd2-118">Nesse caso, você pode usar:</span><span class="sxs-lookup"><span data-stu-id="87dd2-118">In this case, you can use:</span></span>

- [<span data-ttu-id="87dd2-119">O Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87dd2-119">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="87dd2-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="87dd2-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="87dd2-121">Centro de Administração do Microsoft Azure AD</span><span class="sxs-lookup"><span data-stu-id="87dd2-121">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="87dd2-122">Permitir que usuários criem e gerenciem os próprios grupos</span><span class="sxs-lookup"><span data-stu-id="87dd2-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="87dd2-123">O Azure AD permite grupos que podem ser gerenciados por proprietários de grupos em vez de administradores de IT.</span><span class="sxs-lookup"><span data-stu-id="87dd2-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="87dd2-124">Conhecido como *gerenciamento de grupos de autoatendimento*, este recurso permite que proprietários de grupos que não foram atribuídos a uma função administrativa para criar e gerenciar grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="87dd2-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="87dd2-p105">Os usuários podem solicitar a associação a um grupo de segurança, e essa solicitação vai para o proprietário do grupo e não para o administrador da TI. Isso permite que o controle diário da associação ao grupo seja delegado a equipes, projetos ou aos proprietários da empresa, os quais entendem o uso comercial do grupo e podem gerenciar as suas associações.</span><span class="sxs-lookup"><span data-stu-id="87dd2-p105">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="87dd2-127">O gerenciamento de grupo de autoatendimento está disponível apenas aos grupos de segurança do Azure AD e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87dd2-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="87dd2-128">Ele não está disponível para grupos habilitados para email, listas de distribuição ou qualquer grupo que tenha sido sincronizado do AD DS.</span><span class="sxs-lookup"><span data-stu-id="87dd2-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="87dd2-129">Para saber mais, consulte as [instruções para configurar um grupo do Azure AD para o gerenciamento de autoatendimento](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="87dd2-129">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="87dd2-130">Configurar associações de grupo dinâmico</span><span class="sxs-lookup"><span data-stu-id="87dd2-130">Set up dynamic group membership</span></span>

<span data-ttu-id="87dd2-131">O Azure AD oferece suporte à configuração de uma série de regras que adicionam ou removem automaticamente contas de usuário como membros de um grupo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="87dd2-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="87dd2-132">Isso é conhecido como *associação de grupo dinâmico*.</span><span class="sxs-lookup"><span data-stu-id="87dd2-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="87dd2-133">As regras se baseiam em atributos das contas de usuário, como Departamento ou País.</span><span class="sxs-lookup"><span data-stu-id="87dd2-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="87dd2-134">Veja como as regras são aplicadas:</span><span class="sxs-lookup"><span data-stu-id="87dd2-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="87dd2-135">Se uma nova conta de usuário atende a todas as regras do grupo, ela se tornará membro.</span><span class="sxs-lookup"><span data-stu-id="87dd2-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="87dd2-136">Se uma conta de usuário não for um membro do grupo, mas seus atributos forem alterados para corresponder a todas as regras do grupo, ela se tornará um membro desse grupo.</span><span class="sxs-lookup"><span data-stu-id="87dd2-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="87dd2-137">Se uma conta de usuário não corresponder a todas as regras do grupo, ela não será adicionada ao grupo.</span><span class="sxs-lookup"><span data-stu-id="87dd2-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="87dd2-138">Se a conta de usuário for membro do grupo, mas seus atributos forem alterados de modo que ela passe a não atender mais a todas as regras do grupo, ela será removida do grupo.</span><span class="sxs-lookup"><span data-stu-id="87dd2-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="87dd2-p108">Para usar a associação dinâmica, você deve primeiro determinar os conjuntos de grupos que possuem um conjunto comum de atributos de conta do usuário. Por exemplo, todos os membros do Departamento de vendas devem estar no grupo Sales Azure AD, com base no atributo de conta de usuário Departamento definido como "Vendas".</span><span class="sxs-lookup"><span data-stu-id="87dd2-p108">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="87dd2-141">Consulte as [instruções para criar e configurar regras para um grupo dinâmico no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="87dd2-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="87dd2-142">Configurar licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="87dd2-142">Set up automatic licensing</span></span>

<span data-ttu-id="87dd2-143">Você pode configurar grupos de segurança no Azure AD para atribuir automaticamente licenças de um conjunto de assinaturas a todos os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="87dd2-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="87dd2-144">Isso é conhecido como *licenciamento baseado em grupo*.</span><span class="sxs-lookup"><span data-stu-id="87dd2-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="87dd2-145">Se uma conta de usuário for adicionada ou removida do grupo, as licenças das assinaturas do grupo serão automaticamente atribuídas ou não atribuídas à conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="87dd2-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="87dd2-146">No Microsoft 365 Enterprise, você configurará grupos de segurança do Azure AD para atribuir as licenças apropriadas do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="87dd2-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="87dd2-147">Verifique se você tem licenças suficientes para todos os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="87dd2-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="87dd2-148">Se você ficar sem licenças, os novos usuários não receberão licenças até que as licenças estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="87dd2-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="87dd2-149">Você não deve configurar o licenciamento baseado em grupo para grupos que contenham contas do Azure para empresas (B2B).</span><span class="sxs-lookup"><span data-stu-id="87dd2-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="87dd2-150">Para saber mais, confira [Noções básicas de licenciamento baseado em grupo no Azure AD.](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="87dd2-150">For more information, see [Group-based licensing basics in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="87dd2-151">Confira as [instruções para configurar o licenciamento baseado em grupo para um grupo de segurança do Azure.](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="87dd2-151">See the [instructions to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>
