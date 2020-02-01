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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Resumo: Percorra o processo de design para sites de equipe isolados do SharePoint Online.'
ms.openlocfilehash: 345a5fa5dcdcf2a3e61fdd6f1f346d46afe3fd5f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599468"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="573c7-103">Projetar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="573c7-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="573c7-104">**Resumo:** Percorra o processo de design para sites de equipe isolados do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="573c7-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="573c7-105">Este artigo orienta as principais decisões de design que você deve fazer antes de criar um site de equipe do SharePoint Online isolado.</span><span class="sxs-lookup"><span data-stu-id="573c7-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="573c7-106">Fase 1: determinar seus grupos e níveis de permissão do SharePoint</span><span class="sxs-lookup"><span data-stu-id="573c7-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="573c7-107">Todos os sites de equipe do SharePoint Online por padrão são criados com os seguintes grupos do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="573c7-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="573c7-108">\<Membros do nome do site></span><span class="sxs-lookup"><span data-stu-id="573c7-108">\<site name> Members</span></span>
    
- <span data-ttu-id="573c7-109">\<nome do site> visitantes</span><span class="sxs-lookup"><span data-stu-id="573c7-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="573c7-110">\<nome do site> proprietários</span><span class="sxs-lookup"><span data-stu-id="573c7-110">\<site name> Owners</span></span>
    
<span data-ttu-id="573c7-111">Esses grupos são separados dos grupos do Office 365 e do Azure Active Directory (AD) e são a base para atribuir permissões para os recursos do site.</span><span class="sxs-lookup"><span data-stu-id="573c7-111">These groups are separate from Office 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="573c7-112">O conjunto de permissões específicas que determina o que um membro de um grupo do SharePoint pode fazer em um site é um nível de permissão.</span><span class="sxs-lookup"><span data-stu-id="573c7-112">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="573c7-113">Há três níveis de permissão por padrão para um site de equipe do SharePoint Online: editar, ler e controle total.</span><span class="sxs-lookup"><span data-stu-id="573c7-113">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="573c7-114">A tabela a seguir mostra a correlação padrão de grupos do SharePoint e níveis de permissão atribuídos:</span><span class="sxs-lookup"><span data-stu-id="573c7-114">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="573c7-115">**Grupo do SharePoint**</span><span class="sxs-lookup"><span data-stu-id="573c7-115">**SharePoint group**</span></span>|<span data-ttu-id="573c7-116">**Nível de permissão**</span><span class="sxs-lookup"><span data-stu-id="573c7-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="573c7-117">\<Membros do nome do site></span><span class="sxs-lookup"><span data-stu-id="573c7-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="573c7-118">Edit</span><span class="sxs-lookup"><span data-stu-id="573c7-118">Edit</span></span>  <br/> |
|<span data-ttu-id="573c7-119">\<nome do site> visitantes</span><span class="sxs-lookup"><span data-stu-id="573c7-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="573c7-120">Ler</span><span class="sxs-lookup"><span data-stu-id="573c7-120">Read</span></span>  <br/> |
|<span data-ttu-id="573c7-121">\<nome do site> proprietários</span><span class="sxs-lookup"><span data-stu-id="573c7-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="573c7-122">Controle total</span><span class="sxs-lookup"><span data-stu-id="573c7-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="573c7-123">Práticas **recomendadas:** Você pode criar grupos adicionais do SharePoint e níveis de permissão.</span><span class="sxs-lookup"><span data-stu-id="573c7-123">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="573c7-124">No entanto, recomendamos o uso dos grupos e níveis de permissão padrão do SharePoint para seu site isolado do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="573c7-124">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="573c7-125">Estes são os grupos e os níveis de permissão padrão do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="573c7-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![Os grupos e níveis de permissão padrão do SharePoint para um site do SharePoint Online.](../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="573c7-127">Fase 2: atribuir permissões a usuários com grupos de acesso</span><span class="sxs-lookup"><span data-stu-id="573c7-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="573c7-128">Você pode atribuir permissões aos usuários adicionando sua conta de usuário ou um grupo do Office 365 ou do Azure AD do qual a conta de usuário é membro, para os grupos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="573c7-128">You can assign permissions to users by adding their user account, or an Office 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="573c7-129">Depois de adicionada, as contas de usuário do Office 365, direta ou indiretamente, via Associação a um grupo do Office 365 ou do Azure AD, recebem o nível de permissão associado ao grupo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="573c7-129">Once added, the Office 365 user accounts, either directly or indirectly via membership in an Office 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="573c7-130">Usando os grupos padrão do SharePoint como exemplo:</span><span class="sxs-lookup"><span data-stu-id="573c7-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="573c7-131">Os membros do grupo \*\* \<nome do site> Membros\*\* do SharePoint, que podem incluir contas de usuário e grupos, recebem o nível de permissão **Editar**</span><span class="sxs-lookup"><span data-stu-id="573c7-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="573c7-132">Os membros do grupo \*\* \<nome do site> visitantes\*\* do SharePoint, que podem incluir contas de usuário e grupos, recebem o nível de permissão de **leitura**</span><span class="sxs-lookup"><span data-stu-id="573c7-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="573c7-133">Os membros do grupo \*\* \<nome do site> proprietários\*\* do SharePoint, que podem incluir contas de usuário e grupos, recebem o nível de permissão **controle total**</span><span class="sxs-lookup"><span data-stu-id="573c7-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="573c7-134">Práticas **recomendadas:** Embora você possa gerenciar permissões por meio de contas de usuário individuais, recomendamos usar um único grupo do Azure AD, conhecido como grupo de acesso, em vez disso.</span><span class="sxs-lookup"><span data-stu-id="573c7-134">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="573c7-135">Isso simplifica o gerenciamento de permissões por meio da associação no grupo de acesso, em vez de gerenciar a lista de contas de usuário para cada grupo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="573c7-135">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="573c7-136">Os grupos do Azure AD para Office 365 são diferentes dos grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="573c7-136">Azure AD groups for Office 365 are different than Office 365 groups.</span></span> <span data-ttu-id="573c7-137">Os grupos do Azure AD aparecem no centro de administração do Microsoft 365 com o **tipo** definido como **segurança** e não têm um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="573c7-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="573c7-138">Os grupos do Azure AD podem ser gerenciados em:</span><span class="sxs-lookup"><span data-stu-id="573c7-138">Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="573c7-139">Serviços de Domínio Active Directory (AD DS)</span><span class="sxs-lookup"><span data-stu-id="573c7-139">Active Directory Domain Services (AD DS)</span></span>
    
    <span data-ttu-id="573c7-140">Estes são grupos que foram criados em sua infraestrutura do AD DS local e sincronizados com a sua assinatura do Office 365.</span><span class="sxs-lookup"><span data-stu-id="573c7-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Office 365 subscription.</span></span> <span data-ttu-id="573c7-141">No centro de administração do Microsoft 365, esses grupos têm \*\*\*\* um status **sincronizado com o Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="573c7-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="573c7-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="573c7-142">Office 365</span></span>
    
    <span data-ttu-id="573c7-143">Estes são os grupos que foram criados usando o centro de administração do Microsoft 365, o portal do Azure ou o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="573c7-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="573c7-144">No centro de administração do Microsoft 365, esses grupos têm um **status** de **nuvem**.</span><span class="sxs-lookup"><span data-stu-id="573c7-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="573c7-145">Práticas **recomendadas:** Se você estiver usando o AD DS no local e estiver sincronizando com sua assinatura do Office 365, realize o gerenciamento de usuário e de grupo com o AD DS.</span><span class="sxs-lookup"><span data-stu-id="573c7-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Office 365 subscription, perform your user and group management with AD DS.</span></span>
  
<span data-ttu-id="573c7-146">Para sites de equipe isolados do SharePoint Online, a estrutura de grupo recomendada é semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="573c7-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="573c7-147">**Grupo do SharePoint**</span><span class="sxs-lookup"><span data-stu-id="573c7-147">**SharePoint group**</span></span>|<span data-ttu-id="573c7-148">**Grupo de acesso baseado no AD do Azure**</span><span class="sxs-lookup"><span data-stu-id="573c7-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="573c7-149">**Nível de permissão**</span><span class="sxs-lookup"><span data-stu-id="573c7-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="573c7-150">\<Membros do nome do site></span><span class="sxs-lookup"><span data-stu-id="573c7-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="573c7-151">\<Membros do nome do site></span><span class="sxs-lookup"><span data-stu-id="573c7-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="573c7-152">Edit</span><span class="sxs-lookup"><span data-stu-id="573c7-152">Edit</span></span>  <br/> |
|<span data-ttu-id="573c7-153">\<nome do site> visitantes</span><span class="sxs-lookup"><span data-stu-id="573c7-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="573c7-154">\<Visualizadores de nome de site></span><span class="sxs-lookup"><span data-stu-id="573c7-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="573c7-155">Ler</span><span class="sxs-lookup"><span data-stu-id="573c7-155">Read</span></span>  <br/> |
|<span data-ttu-id="573c7-156">\<nome do site> proprietários</span><span class="sxs-lookup"><span data-stu-id="573c7-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="573c7-157">\<nome do site> administradores</span><span class="sxs-lookup"><span data-stu-id="573c7-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="573c7-158">Controle total</span><span class="sxs-lookup"><span data-stu-id="573c7-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="573c7-159">Práticas **recomendadas:** Embora você possa usar os grupos do Office 365 ou do Azure AD como membros de grupos do SharePoint, recomendamos usar os grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="573c7-159">**Best practice:** Although you can use either Office 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="573c7-160">Os grupos do Azure AD, gerenciados pelo AD DS ou pelo Office 365, oferecem mais flexibilidade para usar grupos aninhados para atribuir permissões.</span><span class="sxs-lookup"><span data-stu-id="573c7-160">Azure AD groups, managed either through AD DS or Office 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="573c7-161">Estes são os grupos padrão do SharePoint configurados para usar grupos de acesso baseados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="573c7-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![Usando grupos do Access como membros de grupos de sites padrão do SharePoint Online.](../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="573c7-163">Ao projetar os três grupos de acesso, tenha em mente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="573c7-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="573c7-164">Deve haver apenas alguns membros no grupo nome do \*\* \<site> administradores\*\* de acesso, correspondendo a um pequeno número de administradores do SharePoint Online que estão gerenciando o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="573c7-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="573c7-165">A maioria dos membros do site estão no \*\* \<nome do site> Membros\*\* ou \*\* \<nome do site>\*\* os grupos de acesso do visualizador.</span><span class="sxs-lookup"><span data-stu-id="573c7-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="573c7-166">Como os membros do site no grupo \*\* \<nome do site> Members\*\* Access têm a capacidade de excluir ou modificar recursos no site, considere cuidadosamente sua associação.</span><span class="sxs-lookup"><span data-stu-id="573c7-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="573c7-167">Quando estiver em dúvida, adicione o membro do site ao grupo de acesso de \*\* \<nome do site> visualizadores\*\* .</span><span class="sxs-lookup"><span data-stu-id="573c7-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="573c7-168">Veja um exemplo de grupos do SharePoint e grupos de acesso para um site isolado chamado projeto x.</span><span class="sxs-lookup"><span data-stu-id="573c7-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![Um exemplo de uso de grupos de acesso para um site do SharePoint Online chamado projeto x.](../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="573c7-170">Fase 3: usar grupos aninhados do Azure AD</span><span class="sxs-lookup"><span data-stu-id="573c7-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="573c7-171">Para um projeto confinado a um pequeno número de pessoas, um único nível de grupos de acesso baseado no AD do Azure adicionado aos grupos do SharePoint do site se ajustará à maioria dos cenários.</span><span class="sxs-lookup"><span data-stu-id="573c7-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="573c7-172">No entanto, se você tiver um grande número de pessoas e essas pessoas já forem membros dos grupos do Azure AD estabelecidos, poderá atribuir permissões do SharePoint com mais facilidade usando grupos aninhados ou grupos que contenham outros grupos como membros.</span><span class="sxs-lookup"><span data-stu-id="573c7-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="573c7-173">Por exemplo, você deseja criar um site de equipe isolado do SharePoint Online para colaboração entre os executivos dos departamentos de vendas, marketing, engenharia, legal e de suporte e esses departamentos que já têm seus próprios grupos com conta de usuário executivo Academy.</span><span class="sxs-lookup"><span data-stu-id="573c7-173">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="573c7-174">Em vez de criar um novo grupo para os novos membros do site e colocar todas as contas de usuário executivo individuais, coloque os grupos executivos existentes para cada departamento do novo grupo.</span><span class="sxs-lookup"><span data-stu-id="573c7-174">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="573c7-175">Se você estiver compartilhando uma assinatura do Office 365 entre várias organizações, pode ser difícil gerenciar um único nível de associação de grupo para um site isolado para uma organização devido ao número enorme de contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="573c7-175">If you are sharing an Office 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="573c7-176">Nesse caso, você pode usar grupos aninhados do Azure AD para cada organização que contenha os grupos dentro de suas organizações para gerenciar as permissões.</span><span class="sxs-lookup"><span data-stu-id="573c7-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="573c7-177">Para usar grupos aninhados do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="573c7-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="573c7-178">Identifique ou crie os grupos do Azure AD que conterá as contas de usuário e adicione as contas de usuário apropriadas como membros.</span><span class="sxs-lookup"><span data-stu-id="573c7-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="573c7-179">Crie o grupo de acesso baseado em AD do Azure de contêiner que conterá os outros grupos do Azure AD e adicione esses grupos como membros.</span><span class="sxs-lookup"><span data-stu-id="573c7-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="573c7-180">Para o nível de acesso apropriado para o grupo de acesso de contêiner, identifique o grupo do SharePoint e o nível de permissão correspondente.</span><span class="sxs-lookup"><span data-stu-id="573c7-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="573c7-181">Não é possível usar grupos aninhados do Office 365.</span><span class="sxs-lookup"><span data-stu-id="573c7-181">You cannot use nested Office 365 groups.</span></span> 
  
<span data-ttu-id="573c7-182">Veja um exemplo de grupos aninhados do Azure AD para o grupo de acesso de membros do projeto x.</span><span class="sxs-lookup"><span data-stu-id="573c7-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![Um exemplo de uso de grupos de acesso aninhados para o grupo de acesso de membros do site do projeto x.](../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="573c7-184">Como todas as contas de usuário nas equipes de pesquisa, engenharia e projetos líderes do projeto devem ser membros do site, é mais fácil adicionar seus grupos do Azure AD ao grupo de acesso de membros do projeto x.</span><span class="sxs-lookup"><span data-stu-id="573c7-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="573c7-185">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="573c7-185">Next step</span></span>

<span data-ttu-id="573c7-186">Quando estiver pronto para criar e configurar um site isolado em produção, consulte [implantar um site de equipe isolado do SharePoint Online](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="573c7-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="573c7-187">Confira também</span><span class="sxs-lookup"><span data-stu-id="573c7-187">See Also</span></span>

[<span data-ttu-id="573c7-188">Sites de equipe do SharePoint Online isolados</span><span class="sxs-lookup"><span data-stu-id="573c7-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="573c7-189">Gerenciar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="573c7-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="573c7-190">Implantar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="573c7-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



