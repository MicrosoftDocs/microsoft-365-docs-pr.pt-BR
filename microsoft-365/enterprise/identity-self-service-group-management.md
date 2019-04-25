---
title: 'Etapa 6: Usar grupos para facilitar o gerenciamento'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar o gerenciamento de grupos de autoatendimento do Azure AD.
ms.openlocfilehash: 9400e99ced45370600d1d5dcee4388ddef4250fe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283515"
---
# <a name="step-6-use-groups-for-easier-management"></a><span data-ttu-id="bcf5a-103">Etapa 6: Usar grupos para facilitar o gerenciamento</span><span class="sxs-lookup"><span data-stu-id="bcf5a-103">Step 6: Use groups for easier management</span></span>

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="bcf5a-104">Permitir que usuários criem e gerenciem os próprios grupos</span><span class="sxs-lookup"><span data-stu-id="bcf5a-104">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="bcf5a-105">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="bcf5a-105">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="bcf5a-106">Nesta seção, você identificará grupos do Azure Active Directory (Azure AD) que podem ser gerenciados por proprietários de grupos em vez de administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-106">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="bcf5a-107">Conhecido como *gerenciamento de grupos de autoatendimento*, este recurso permite que proprietários de grupos que não foram atribuídos a uma função administrativa para criar e gerenciar grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-107">In this step, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="bcf5a-p102">Os usuários podem solicitar a associação a um grupo de segurança, e essa solicitação vai para o proprietário do grupo e não para o administrador da TI. Isso permite que o controle diário da associação ao grupo seja delegado a equipes, projetos ou aos proprietários da empresa, os quais entendem o uso comercial do grupo e podem gerenciar as suas associações.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="bcf5a-110">O gerenciamento de grupos de autoatendimento está disponível apenas para os grupos de segurança do Azure AD e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-110">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span> <span data-ttu-id="bcf5a-111">Ele não está disponível para grupos habilitados para email, listas de distribuição ou qualquer grupo que tenha sido sincronizado de serviços locais de domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="bcf5a-111">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="bcf5a-112">Para saber mais, consulte as [instruções para configurar um grupo do Azure AD para o gerenciamento de autoatendimento](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="bcf5a-112">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="bcf5a-113">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-self-service-groups) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="bcf5a-114">Configurar associações de grupo dinâmico</span><span class="sxs-lookup"><span data-stu-id="bcf5a-114">Set up dynamic group membership</span></span>

<span data-ttu-id="bcf5a-115">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="bcf5a-115">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="bcf5a-116">Nesta seção, você criará uma série de regras que vão adicionar ou remover automaticamente contas de usuários como membros do um grupo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-116">In this step, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as dynamic group membership. The rules are based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="bcf5a-117">Isso é conhecido como *associação de grupo dinâmico*.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-117">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="bcf5a-118">As regras se baseiam em atributos das contas de usuário, como Departamento ou País.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-118">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="bcf5a-119">Veja aqui como as regras são aplicadas:</span><span class="sxs-lookup"><span data-stu-id="bcf5a-119">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="bcf5a-120">Se uma nova conta de usuário atende a todas as regras do grupo, ela se tornará membro.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-120">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="bcf5a-121">Se a conta de usuário não for um membro do grupo, mas seus atributos forem alterados de modo que ela passa a atender a todas as regras do grupo, ela se tornará membro desse grupo.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-121">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="bcf5a-122">Se a conta de usuário não atender a toda as regras do grupo, ela não será incluída no grupo.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-122">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="bcf5a-123">Se a conta de usuário for membro do grupo, mas seus atributos forem alterados de modo que ela passe a não atender mais a todas as regras do grupo, ela será removida do grupo.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-123">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="bcf5a-p105">Para usar a associação dinâmica, primeiro você precisa determinar os conjuntos de grupos que possuem um conjunto comum de atributos de conta de usuário. Por exemplo, todos os membros do departamento de vendas devem estar no grupo de vendas no Azure AD, com base em no atributo de conta de usuário por departamento definido como "Vendas".</span><span class="sxs-lookup"><span data-stu-id="bcf5a-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="bcf5a-126">Consulte as [instruções para criar e configurar regras para um grupo dinâmico no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="bcf5a-126">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="bcf5a-127">Os resultados desta seção são:</span><span class="sxs-lookup"><span data-stu-id="bcf5a-127">The results of this step are:</span></span>

- <span data-ttu-id="bcf5a-128">um conjunto de grupos do Azure AD que pode ser configurado quanto à associação dinâmica;</span><span class="sxs-lookup"><span data-stu-id="bcf5a-128">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="bcf5a-129">um conjunto de regras em cada grupo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-129">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="bcf5a-131">Guia do Laboratório de Teste: automatizar licenças e associação a grupos</span><span class="sxs-lookup"><span data-stu-id="bcf5a-131">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="bcf5a-132">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-dyn-groups) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="bcf5a-133">Configurar licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="bcf5a-133">Set up automatic licensing</span></span>

<span data-ttu-id="bcf5a-134">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="bcf5a-134">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="bcf5a-135">Nesta seção, você vai configurar grupos de segurança no Azure AD para atribuir licenças automaticamente de um conjunto de assinaturas para todos os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-135">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="bcf5a-136">Isso é conhecido como *licenciamento baseado em grupo*.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-136">This is known as *group-based licensing*.</span></span> <span data-ttu-id="bcf5a-137">Se uma conta de usuário for adicionada ou removida do grupo, as licenças para as assinaturas do grupo serão atribuídas ou removidas automaticamente da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-137">In this step, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as group-based licensing. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="bcf5a-138">No Microsoft 365 Enterprise, você configura grupos de segurança do Azure AD para atribuir estas duas licenças:</span><span class="sxs-lookup"><span data-stu-id="bcf5a-138">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="bcf5a-139">Office 365 Enterprise E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="bcf5a-139">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="bcf5a-140">Enterprise Mobility + Security (EMS) E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="bcf5a-140">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="bcf5a-p107">Usando os grupos que foram identificados na Etapa 2, procure aqueles com uma lista de contas em que todos os usuários precisem ter as licenças do Office 365 e do EMS. Verifique se você tem licenças suficientes para todos os membros do grupo. Se não houver licenças para todos, os novos usuários não receberão licenças até que estas estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-p107">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="bcf5a-144">Você não deve configurar o *licenciamento baseado em grupo* para grupos que contenham contas do Azure para empresas (B2B).</span><span class="sxs-lookup"><span data-stu-id="bcf5a-144">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="bcf5a-145">Consulte as [noções básicas sobre o licenciamento baseado em grupo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="bcf5a-145">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="bcf5a-146">Consulte as [etapas para configurar o licenciamento baseado em grupo para um grupo de segurança do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="bcf5a-146">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="bcf5a-147">Os resultados desta seção são:</span><span class="sxs-lookup"><span data-stu-id="bcf5a-147">The results of this step are:</span></span>

- <span data-ttu-id="bcf5a-148">Você identificou quais grupos de segurança são adequados para o licenciamento baseado em grupo.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-148">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="bcf5a-149">Você configurou esses grupos para o licenciamento baseado em grupo.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-149">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="bcf5a-151">Guia do Laboratório de Teste: automatizar licenças e associação a grupos</span><span class="sxs-lookup"><span data-stu-id="bcf5a-151">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="bcf5a-152">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-group-license) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="bcf5a-153">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="bcf5a-153">Next step</span></span>

[<span data-ttu-id="bcf5a-154">Critérios de saída da infraestrutura de identidade</span><span class="sxs-lookup"><span data-stu-id="bcf5a-154">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)
