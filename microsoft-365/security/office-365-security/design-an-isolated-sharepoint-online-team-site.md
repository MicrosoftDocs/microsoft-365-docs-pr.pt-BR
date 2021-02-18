---
title: Projetar um site de equipe do SharePoint Online isolado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Projete sites de equipe isolados do SharePoint Online, incluindo determinar níveis de permissão, atribuir permissões a usuários com grupos de acesso e grupos aninhados do Azure AD.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288330"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="2f4e0-103">Projetar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="2f4e0-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2f4e0-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="2f4e0-104">**Applies to**</span></span>
- [<span data-ttu-id="2f4e0-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2f4e0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2f4e0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f4e0-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


 <span data-ttu-id="2f4e0-107">**Resumo:** Passo a passo do processo de design para sites de equipe isolados do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="2f4e0-108">Este artigo o leva pelas principais decisões de design que você deve tomar antes de criar um site de equipe do SharePoint Online isolado.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="2f4e0-109">Fase 1: Determinar seus grupos e níveis de permissão do SharePoint</span><span class="sxs-lookup"><span data-stu-id="2f4e0-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="2f4e0-110">Todos os sites de equipe do SharePoint Online por padrão são criados com os seguintes grupos do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="2f4e0-111">\<site name> Membros</span><span class="sxs-lookup"><span data-stu-id="2f4e0-111">\<site name> Members</span></span>

- <span data-ttu-id="2f4e0-112">\<site name> Visitantes</span><span class="sxs-lookup"><span data-stu-id="2f4e0-112">\<site name> Visitors</span></span>

- <span data-ttu-id="2f4e0-113">\<site name> Proprietários</span><span class="sxs-lookup"><span data-stu-id="2f4e0-113">\<site name> Owners</span></span>

<span data-ttu-id="2f4e0-114">Esses grupos são separados dos grupos do Microsoft 365 e do Azure Active Directory (AD) e são a base para atribuir permissões para os recursos do site.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="2f4e0-115">O conjunto de permissões específicas que determina o que um membro de um grupo do SharePoint pode fazer em um site é um nível de permissão.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-115">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="2f4e0-116">Há três níveis de permissão por padrão para um site de equipe do SharePoint Online: Editar, Ler e Controle total.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-116">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="2f4e0-117">A tabela a seguir mostra a correlação padrão de grupos do SharePoint e níveis de permissão atribuídos:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-117">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="2f4e0-118">Grupo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="2f4e0-118">SharePoint group</span></span>|<span data-ttu-id="2f4e0-119">Nível de permissão</span><span class="sxs-lookup"><span data-stu-id="2f4e0-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="2f4e0-120">\<site name> Membros</span><span class="sxs-lookup"><span data-stu-id="2f4e0-120">\<site name> Members</span></span>|<span data-ttu-id="2f4e0-121">Editar</span><span class="sxs-lookup"><span data-stu-id="2f4e0-121">Edit</span></span>|
|<span data-ttu-id="2f4e0-122">\<site name> Visitantes</span><span class="sxs-lookup"><span data-stu-id="2f4e0-122">\<site name> Visitors</span></span>|<span data-ttu-id="2f4e0-123">Ler</span><span class="sxs-lookup"><span data-stu-id="2f4e0-123">Read</span></span>|
|<span data-ttu-id="2f4e0-124">\<site name> Proprietários</span><span class="sxs-lookup"><span data-stu-id="2f4e0-124">\<site name> Owners</span></span>|<span data-ttu-id="2f4e0-125">Controle total</span><span class="sxs-lookup"><span data-stu-id="2f4e0-125">Full control</span></span>|
|

 <span data-ttu-id="2f4e0-126">**Prática prática:** Você pode criar grupos e níveis de permissão adicionais do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-126">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="2f4e0-127">No entanto, recomendamos usar os grupos padrão do SharePoint e os níveis de permissão para o site isolado do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-127">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="2f4e0-128">Aqui estão os grupos padrão do SharePoint e os níveis de permissão.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-128">Here are the default SharePoint groups and permission levels.</span></span>

![Os grupos padrão do SharePoint e níveis de permissão para um site do SharePoint Online.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="2f4e0-130">Fase 2: Atribuir permissões a usuários com grupos de acesso</span><span class="sxs-lookup"><span data-stu-id="2f4e0-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="2f4e0-131">Você pode atribuir permissões a usuários adicionando sua conta de usuário ou um grupo do Microsoft 365 ou Azure AD do qual a conta de usuário é membro, para os grupos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="2f4e0-132">Depois de adicionadas, as contas de usuário, direta ou indiretamente por meio da associação a um grupo do Microsoft 365 ou Azure AD, são atribuídas ao nível de permissão associado ao grupo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="2f4e0-133">Usando os grupos padrão do SharePoint como exemplo:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="2f4e0-134">Os membros do grupo **\<site name> Membros** do SharePoint, que podem incluir contas de usuário e grupos, são atribuídos ao **nível de** permissão Editar</span><span class="sxs-lookup"><span data-stu-id="2f4e0-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="2f4e0-135">Os membros do grupo **\<site name> Visitantes** do SharePoint, que podem incluir contas de usuário e grupos, são atribuídos ao **nível de** permissão De leitura</span><span class="sxs-lookup"><span data-stu-id="2f4e0-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="2f4e0-136">Os membros do grupo **\<site name> Proprietários** do SharePoint, que podem incluir contas de usuário e grupos, são atribuídos ao **nível de** permissão Controle total</span><span class="sxs-lookup"><span data-stu-id="2f4e0-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="2f4e0-137">**Prática prática:** Embora você possa gerenciar permissões por meio de contas de usuário individuais, recomendamos usar um único grupo do Azure AD, conhecido como grupo de acesso.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-137">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="2f4e0-138">Isso simplifica o gerenciamento de permissões por meio da associação ao grupo de acesso, em vez de gerenciar a lista de contas de usuário para cada grupo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-138">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="2f4e0-139">Os grupos do Azure AD para o Microsoft 365 são grupos diferentes do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="2f4e0-140">Os grupos do Azure AD aparecem no centro  de  administração do Microsoft 365 com o tipo definido como Segurança e não têm um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="2f4e0-141">Os grupos do Azure AD podem ser gerenciados em:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="2f4e0-142">Serviços de Domínio Active Directory (AD DS)</span><span class="sxs-lookup"><span data-stu-id="2f4e0-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="2f4e0-143">Esses são grupos que foram criados em sua infraestrutura do AD DS local e sincronizados com sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="2f4e0-144">No centro de administração do Microsoft 365, esses grupos têm um **Status** de **Sincronizado com o Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="2f4e0-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="2f4e0-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="2f4e0-145">Office 365</span></span>

    <span data-ttu-id="2f4e0-146">Esses são grupos que foram criados usando o Centro de administração do Microsoft 365, o portal do Azure ou o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="2f4e0-147">No centro de administração do Microsoft 365, esses grupos têm um **Status** de **Nuvem.**</span><span class="sxs-lookup"><span data-stu-id="2f4e0-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="2f4e0-148">**Prática prática:** Se você estiver usando o AD DS local e sincronizando com sua assinatura do Microsoft 365, execute o gerenciamento de usuários e grupos com o AD DS.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="2f4e0-149">Para sites de equipe isolados do SharePoint Online, a estrutura de grupo recomendada tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="2f4e0-150">Grupo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="2f4e0-150">SharePoint group</span></span>|<span data-ttu-id="2f4e0-151">Grupo de acesso baseado no Azure AD</span><span class="sxs-lookup"><span data-stu-id="2f4e0-151">Azure AD-based access group</span></span>|<span data-ttu-id="2f4e0-152">Nível da permissão</span><span class="sxs-lookup"><span data-stu-id="2f4e0-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="2f4e0-153">\<site name> Membros</span><span class="sxs-lookup"><span data-stu-id="2f4e0-153">\<site name> Members</span></span>|<span data-ttu-id="2f4e0-154">\<site name> Membros</span><span class="sxs-lookup"><span data-stu-id="2f4e0-154">\<site name> Members</span></span>|<span data-ttu-id="2f4e0-155">Editar</span><span class="sxs-lookup"><span data-stu-id="2f4e0-155">Edit</span></span>|
|<span data-ttu-id="2f4e0-156">\<site name> Visitantes</span><span class="sxs-lookup"><span data-stu-id="2f4e0-156">\<site name> Visitors</span></span>|<span data-ttu-id="2f4e0-157">\<site name> Visualizadores</span><span class="sxs-lookup"><span data-stu-id="2f4e0-157">\<site name> Viewers</span></span>|<span data-ttu-id="2f4e0-158">Ler</span><span class="sxs-lookup"><span data-stu-id="2f4e0-158">Read</span></span>|
|<span data-ttu-id="2f4e0-159">\<site name> Proprietários</span><span class="sxs-lookup"><span data-stu-id="2f4e0-159">\<site name> Owners</span></span>|<span data-ttu-id="2f4e0-160">\<site name> Administradores</span><span class="sxs-lookup"><span data-stu-id="2f4e0-160">\<site name> Admins</span></span>|<span data-ttu-id="2f4e0-161">Controle total</span><span class="sxs-lookup"><span data-stu-id="2f4e0-161">Full control</span></span>|
|

 <span data-ttu-id="2f4e0-162">**Prática prática:** Embora você possa usar grupos do Microsoft 365 ou Azure AD como membros de grupos do SharePoint, recomendamos que você use grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="2f4e0-163">Os grupos do Azure AD, gerenciados por meio do AD DS ou do Microsoft 365, oferecem mais flexibilidade para usar grupos aninhados para atribuir permissões.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="2f4e0-164">Aqui estão os grupos padrão do SharePoint configurados para usar grupos de acesso baseados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Usar grupos de acesso como membros de grupos de sites padrão do SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="2f4e0-166">Ao projetar os três grupos de acesso, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="2f4e0-167">Deve haver apenas alguns membros **\<site name>** no grupo de acesso Administradores, correspondendo a um pequeno número de administradores do SharePoint Online que estão gerenciando o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="2f4e0-168">A maioria dos membros do site está nos grupos **\<site name> de acesso Membros** ou **\<site name> Visualizadores.**</span><span class="sxs-lookup"><span data-stu-id="2f4e0-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="2f4e0-169">Como os membros do site **no \<site name>** grupo de acesso Membros têm a capacidade de excluir ou modificar recursos no site, considere cuidadosamente sua associação.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="2f4e0-170">Quando estiver em dúvida, adicione o membro do site ao grupo **\<site name> de acesso Visualizadores.**</span><span class="sxs-lookup"><span data-stu-id="2f4e0-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="2f4e0-171">Aqui está um exemplo dos grupos do SharePoint e grupos de acesso para um site isolado chamado ProjectX.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![Um exemplo de uso de grupos de acesso para um site do SharePoint Online chamado ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="2f4e0-173">Fase 3: Usar grupos aninhados do Azure AD</span><span class="sxs-lookup"><span data-stu-id="2f4e0-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="2f4e0-174">Para um projeto confinado a um pequeno número de pessoas, um único nível de grupos de acesso baseados no Azure AD adicionados aos grupos do SharePoint do site se ajustará à maioria dos cenários.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-174">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="2f4e0-175">No entanto, se você tiver um grande número de pessoas e essas pessoas já são membros de grupos estabelecidos do Azure AD, você pode atribuir permissões do SharePoint mais facilmente usando grupos aninhados ou grupos que contêm outros grupos como membros.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-175">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="2f4e0-176">Por exemplo, você deseja criar um site de equipe online isolado do SharePoint para colaboração entre os executivos dos departamentos de vendas, marketing, engenharia, jurídico e de suporte, e esses departamentos já têm seus próprios grupos com associação de conta de usuário executiva.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-176">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="2f4e0-177">Em vez de criar um novo grupo para os novos membros do site e colocar todas as contas de usuário executivos individuais nele, coloque os grupos executivos existentes para cada departamento no novo grupo.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-177">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="2f4e0-178">Se você estiver compartilhando uma assinatura do Microsoft 365 entre várias organizações, um único nível de associação de grupo para um site isolado de uma organização pode se tornar difícil de gerenciar devido ao grande número de contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="2f4e0-179">Nesse caso, você pode usar grupos aninhados do Azure AD para cada organização que contenha os grupos em suas organizações para gerenciar as permissões.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="2f4e0-180">Para usar grupos aninhados do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="2f4e0-181">Identifique ou crie os grupos do Azure AD que conterão contas de usuário e adicione as contas de usuário apropriadas como membros.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="2f4e0-182">Crie o grupo de acesso baseado no Azure AD do contêiner que conterá os outros grupos do Azure AD e adicione esses grupos como membros.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="2f4e0-183">Para o nível apropriado de acesso para o grupo de acesso do contêiner, identifique o grupo do SharePoint e o nível de permissão correspondente.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="2f4e0-184">Você não pode usar grupos aninhados do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="2f4e0-185">Aqui está um exemplo de grupos aninhados do Azure AD para o grupo de acesso de membros do ProjectX.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![Um exemplo de como usar grupos de acesso aninhados para o grupo de acesso de membros do site ProjectX.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="2f4e0-187">Como todas as contas de usuário nas equipes de pesquisa, engenharia e projeto são projetadas para ser membros do site, é mais fácil adicionar seus grupos do Azure AD ao grupo de acesso membros do ProjectX.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="2f4e0-188">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2f4e0-188">Next step</span></span>

<span data-ttu-id="2f4e0-189">Quando você estiver pronto para criar e configurar um site isolado em produção, confira Implantar um [site de equipe do SharePoint Online isolado.](deploy-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="2f4e0-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f4e0-190">Confira também</span><span class="sxs-lookup"><span data-stu-id="2f4e0-190">See Also</span></span>

[<span data-ttu-id="2f4e0-191">Sites de equipe do SharePoint Online isolados</span><span class="sxs-lookup"><span data-stu-id="2f4e0-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="2f4e0-192">Gerenciar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="2f4e0-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="2f4e0-193">Implantar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="2f4e0-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
