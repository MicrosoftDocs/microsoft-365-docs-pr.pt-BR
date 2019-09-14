---
title: 'Etapa 6: Usar grupos para facilitar o gerenciamento'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar o gerenciamento de grupos de autoatendimento do Azure AD.
ms.openlocfilehash: 97077f5e047f55ea6bf6e532d25d25f4682ff179
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981772"
---
# <a name="step-6-use-groups-for-easier-management"></a><span data-ttu-id="5ddba-103">Etapa 6: Usar grupos para facilitar o gerenciamento</span><span class="sxs-lookup"><span data-stu-id="5ddba-103">Step 6: Use groups for easier management</span></span>

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="5ddba-104">Permitir que usuários criem e gerenciem os próprios grupos</span><span class="sxs-lookup"><span data-stu-id="5ddba-104">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="5ddba-105">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5ddba-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5ddba-106">Nesta seção, você identificará grupos do Azure Active Directory (Azure AD) que podem ser gerenciados por proprietários de grupos em vez de administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="5ddba-106">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="5ddba-107">Conhecido como *gerenciamento de grupos de autoatendimento*, este recurso permite que proprietários de grupos que não foram atribuídos a uma função administrativa para criar e gerenciar grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="5ddba-107">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="5ddba-p102">Os usuários podem solicitar a associação a um grupo de segurança, e essa solicitação vai para o proprietário do grupo e não para o administrador da TI. Isso permite que o controle diário da associação ao grupo seja delegado a equipes, projetos ou aos proprietários da empresa, os quais entendem o uso comercial do grupo e podem gerenciar as suas associações.</span><span class="sxs-lookup"><span data-stu-id="5ddba-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="5ddba-110">O gerenciamento de grupos de autoatendimento está disponível apenas para os grupos de segurança do Azure AD e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ddba-110">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="5ddba-111">Ele não está disponível para grupos habilitados para email, listas de distribuição ou qualquer grupo que tenha sido sincronizado de serviços locais de domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5ddba-111">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="5ddba-112">Para saber mais, consulte as [instruções para configurar um grupo do Azure AD para o gerenciamento de autoatendimento](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="5ddba-112">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="5ddba-113">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-self-service-groups) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="5ddba-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="5ddba-114">Configurar associações de grupo dinâmico</span><span class="sxs-lookup"><span data-stu-id="5ddba-114">Set up dynamic group membership</span></span>

<span data-ttu-id="5ddba-115">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5ddba-115">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5ddba-116">Nesta seção, você criará uma série de regras que vão adicionar ou remover automaticamente contas de usuários como membros do um grupo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ddba-116">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="5ddba-117">Isso é conhecido como *associação de grupo dinâmico*.</span><span class="sxs-lookup"><span data-stu-id="5ddba-117">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="5ddba-118">As regras se baseiam em atributos das contas de usuário, como Departamento ou País.</span><span class="sxs-lookup"><span data-stu-id="5ddba-118">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="5ddba-119">Veja aqui como as regras são aplicadas:</span><span class="sxs-lookup"><span data-stu-id="5ddba-119">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="5ddba-120">Se uma nova conta de usuário atende a todas as regras do grupo, ela se tornará membro.</span><span class="sxs-lookup"><span data-stu-id="5ddba-120">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="5ddba-121">Se a conta de usuário não for um membro do grupo, mas seus atributos forem alterados de modo que ela passa a atender a todas as regras do grupo, ela se tornará membro desse grupo.</span><span class="sxs-lookup"><span data-stu-id="5ddba-121">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="5ddba-122">Se a conta de usuário não atender a toda as regras do grupo, ela não será incluída no grupo.</span><span class="sxs-lookup"><span data-stu-id="5ddba-122">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="5ddba-123">Se a conta de usuário for membro do grupo, mas seus atributos forem alterados de modo que ela passe a não atender mais a todas as regras do grupo, ela será removida do grupo.</span><span class="sxs-lookup"><span data-stu-id="5ddba-123">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="5ddba-p105">Para usar a associação dinâmica, primeiro você precisa determinar os conjuntos de grupos que possuem um conjunto comum de atributos de conta de usuário. Por exemplo, todos os membros do departamento de vendas devem estar no grupo de vendas no Azure AD, com base em no atributo de conta de usuário por departamento definido como "Vendas".</span><span class="sxs-lookup"><span data-stu-id="5ddba-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="5ddba-126">Consulte as [instruções para criar e configurar regras para um grupo dinâmico no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="5ddba-126">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="5ddba-127">Os resultados desta seção são:</span><span class="sxs-lookup"><span data-stu-id="5ddba-127">The results of this section are:</span></span>

- <span data-ttu-id="5ddba-128">um conjunto de grupos do Azure AD que pode ser configurado quanto à associação dinâmica;</span><span class="sxs-lookup"><span data-stu-id="5ddba-128">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="5ddba-129">um conjunto de regras em cada grupo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="5ddba-129">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5ddba-131">Guia do Laboratório de Teste: automatizar licenças e associação a grupos</span><span class="sxs-lookup"><span data-stu-id="5ddba-131">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="5ddba-132">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-dyn-groups) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="5ddba-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="5ddba-133">Configurar licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="5ddba-133">Set up automatic licensing</span></span>

<span data-ttu-id="5ddba-134">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5ddba-134">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5ddba-135">Nesta seção, você vai configurar grupos de segurança no Azure AD para atribuir licenças automaticamente de um conjunto de assinaturas para todos os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="5ddba-135">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="5ddba-136">Isso é conhecido como *licenciamento baseado em grupo*.</span><span class="sxs-lookup"><span data-stu-id="5ddba-136">This is known as *group-based licensing*.</span></span> <span data-ttu-id="5ddba-137">Se uma conta de usuário for adicionada ou removida do grupo, as licenças das assinaturas do grupo serão atribuídas ou terão a atribuição cancelada automaticamente da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="5ddba-137">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="5ddba-138">No Microsoft 365 Enterprise, você configurará grupos de segurança do Azure AD para atribuir as licenças apropriadas do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5ddba-138">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="5ddba-139">Verifique se você tem licenças suficientes para todos os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="5ddba-139">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="5ddba-140">Caso as licenças acabem, os novos usuários não receberão licenças até que elas fiquem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5ddba-140">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="5ddba-141">Você não deve configurar o *licenciamento baseado em grupo* para grupos que contenham contas do Azure para empresas (B2B).</span><span class="sxs-lookup"><span data-stu-id="5ddba-141">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="5ddba-142">Consulte as [noções básicas sobre o licenciamento baseado em grupo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="5ddba-142">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="5ddba-143">Consulte as [etapas para configurar o licenciamento baseado em grupo para um grupo de segurança do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="5ddba-143">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="5ddba-144">Os resultados desta seção são:</span><span class="sxs-lookup"><span data-stu-id="5ddba-144">The results of this section are:</span></span>

- <span data-ttu-id="5ddba-145">Você identificou quais grupos de segurança são adequados para o licenciamento baseado em grupo.</span><span class="sxs-lookup"><span data-stu-id="5ddba-145">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="5ddba-146">Você configurou esses grupos para o licenciamento baseado em grupo.</span><span class="sxs-lookup"><span data-stu-id="5ddba-146">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5ddba-148">Guia do Laboratório de Teste: automatizar licenças e associação a grupos</span><span class="sxs-lookup"><span data-stu-id="5ddba-148">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="5ddba-149">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-group-license) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="5ddba-149">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="5ddba-150">Configurar a governança de identidade</span><span class="sxs-lookup"><span data-stu-id="5ddba-150">Configure identity governance</span></span>](identity-governance.md) |
