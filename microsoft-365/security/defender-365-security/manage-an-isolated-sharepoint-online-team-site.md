---
title: Gerenciar um site de equipe do SharePoint Online isolado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Gerencie um site de equipe isolado do SharePoint Online, adicione novos usuários e grupos, remova usuários e grupos e crie uma subpasta de documentos com permissões personalizadas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 99b773547fa67068d75a79260af14010e456cb01
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054147"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="144cc-103">Gerenciar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="144cc-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="144cc-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="144cc-104">**Applies to**</span></span>
- [<span data-ttu-id="144cc-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="144cc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="144cc-106">Microsoft Defender para Office 365 Plano 1</span><span class="sxs-lookup"><span data-stu-id="144cc-106">Microsoft Defender for Office 365 plan 1</span></span>](defender-for-office-365.md)
- <span data-ttu-id="144cc-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="144cc-107">SharePoint Online</span></span> 

 <span data-ttu-id="144cc-108">**Resumo:** Gerencie seu site de equipe isolado do SharePoint Online com esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="144cc-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="144cc-109">Este artigo descreve operações de gerenciamento comuns para um site de equipe isolado do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="144cc-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="144cc-110">Adicionar um novo usuário</span><span class="sxs-lookup"><span data-stu-id="144cc-110">Add a new user</span></span>

<span data-ttu-id="144cc-111">Quando alguém novo ingressar no site, você deve decidir seu nível de participação no site:</span><span class="sxs-lookup"><span data-stu-id="144cc-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="144cc-112">Administração: adicionar a nova conta de usuário ao grupo de acesso de administradores de site</span><span class="sxs-lookup"><span data-stu-id="144cc-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="144cc-113">Colaboração ativa: adicionar a conta de usuário ao grupo de acesso de membros do site</span><span class="sxs-lookup"><span data-stu-id="144cc-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="144cc-114">Exibição: adicionar a conta de usuário ao grupo de acesso de visualizadores de site</span><span class="sxs-lookup"><span data-stu-id="144cc-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="144cc-115">Se você estiver gerenciando contas e grupos de usuários por meio dos Serviços de Domínio do Active Directory (AD DS), adicione os usuários apropriados aos grupos de acesso apropriados usando seus procedimentos normais de gerenciamento de grupo e usuário do AD DS e aguarde a sincronização com sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="144cc-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="144cc-116">Se você estiver gerenciando contas e grupos de usuários por meio do Microsoft 365, poderá usar o Centro de administração do Microsoft 365 ou o Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="144cc-117">Para o Centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para adicionar os usuários apropriados aos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="144cc-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="144cc-118">Para o PowerShell, primeiro [Conecte-se ao módulo PowerShell do Azure Active Directory para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="144cc-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="144cc-119">Para adicionar uma conta de usuário a um grupo de acesso com seu nome principal de usuário (UPN), use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="144cc-120">Para adicionar uma conta de usuário a um grupo de acesso com seu nome de exibição, use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="144cc-121">Adicionar um novo grupo</span><span class="sxs-lookup"><span data-stu-id="144cc-121">Add a new group</span></span>

<span data-ttu-id="144cc-122">Para adicionar acesso a um grupo inteiro, você deve decidir o nível de participação de todos os membros do grupo no site:</span><span class="sxs-lookup"><span data-stu-id="144cc-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="144cc-123">Administração: adicionar o grupo ao grupo de acesso de administradores de site</span><span class="sxs-lookup"><span data-stu-id="144cc-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="144cc-124">Colaboração ativa: adicionar o grupo ao grupo de acesso de membros do site</span><span class="sxs-lookup"><span data-stu-id="144cc-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="144cc-125">Exibição: adicionar o grupo ao grupo de acesso de visualizadores de site</span><span class="sxs-lookup"><span data-stu-id="144cc-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="144cc-126">Se você estiver gerenciando contas de usuário e grupos por meio do AD DS, adicione os grupos apropriados aos grupos apropriados usando seus procedimentos normais de gerenciamento de grupo e usuário do AD DS e aguarde a sincronização com sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="144cc-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="144cc-127">Se você estiver gerenciando contas e grupos de usuários por meio do Office 365, poderá usar o Centro de administração do Microsoft 365 ou o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="144cc-128">Para o Centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para adicionar os grupos apropriados aos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="144cc-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="144cc-129">Para o PowerShell, primeiro [Conecte-se ao módulo PowerShell do Azure Active Directory para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="144cc-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="144cc-130">Em seguida, use os seguintes comandos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="144cc-131">Remover um usuário</span><span class="sxs-lookup"><span data-stu-id="144cc-131">Remove a user</span></span>

<span data-ttu-id="144cc-132">Quando o acesso de alguém deve ser removido do site, você os remove do grupo de acesso para o qual ele é membro no momento com base em sua participação no site:</span><span class="sxs-lookup"><span data-stu-id="144cc-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="144cc-133">Administração: Remover a conta de usuário do grupo de acesso de administradores de site</span><span class="sxs-lookup"><span data-stu-id="144cc-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="144cc-134">Colaboração ativa: remover a conta de usuário do grupo de acesso de membros do site</span><span class="sxs-lookup"><span data-stu-id="144cc-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="144cc-135">Exibição: Remover a conta de usuário do grupo de acesso de visualizadores de site</span><span class="sxs-lookup"><span data-stu-id="144cc-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="144cc-136">Se você estiver gerenciando contas e grupos de usuários por meio do AD DS, remova os usuários apropriados dos grupos de acesso apropriados usando seus procedimentos normais de gerenciamento de grupo e usuário do AD DS e aguarde a sincronização com sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="144cc-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="144cc-137">Se você estiver gerenciando contas e grupos de usuários por meio do Office 365, poderá usar o Centro de administração do Microsoft 365 ou o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="144cc-138">Para o Centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para remover os usuários apropriados dos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="144cc-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="144cc-139">Para o PowerShell, primeiro [Conecte-se ao módulo PowerShell do Azure Active Directory para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="144cc-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="144cc-140">Para remover uma conta de usuário de um grupo de acesso com seu UPN, use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="144cc-141">Para remover uma conta de usuário de um grupo de acesso com seu nome de exibição, use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="144cc-142">Remover um grupo</span><span class="sxs-lookup"><span data-stu-id="144cc-142">Remove a group</span></span>

<span data-ttu-id="144cc-143">Para remover o acesso de um grupo inteiro, remova o grupo do grupo de acesso para o qual ele é membro no momento com base em sua participação no site:</span><span class="sxs-lookup"><span data-stu-id="144cc-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="144cc-144">Administração: Remover o grupo do grupo de acesso de administradores de site</span><span class="sxs-lookup"><span data-stu-id="144cc-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="144cc-145">Colaboração ativa: Remover o grupo do grupo de acesso de membros do site</span><span class="sxs-lookup"><span data-stu-id="144cc-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="144cc-146">Exibição: Remover o grupo do grupo de acesso de visualizadores de site</span><span class="sxs-lookup"><span data-stu-id="144cc-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="144cc-147">Se você estiver gerenciando contas e grupos de usuários por meio do Windows Server Active Directory, remova os grupos apropriados dos grupos de acesso apropriados usando seus procedimentos normais de gerenciamento de grupo e usuário do AD DS e aguarde a sincronização com sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="144cc-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="144cc-148">Se você estiver gerenciando contas e grupos de usuários por meio do Office 365, poderá usar o Centro de administração do Microsoft 365 ou o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="144cc-149">Para o Centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para remover os grupos apropriados dos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="144cc-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="144cc-150">Para o PowerShell, primeiro [Conecte-se ao módulo PowerShell do Azure Active Directory para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="144cc-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="144cc-151">Para remover um grupo de um grupo de acesso usando seus nomes de exibição, use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="144cc-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="144cc-152">Criar uma subpasta de documentos com permissões personalizadas</span><span class="sxs-lookup"><span data-stu-id="144cc-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="144cc-153">Em alguns casos, um subconjunto das pessoas que trabalham no site isolado precisa de um local mais privado para colaborar.</span><span class="sxs-lookup"><span data-stu-id="144cc-153">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="144cc-154">Para sites do SharePoint Online, você pode criar uma subpasta na pasta Documentos do site e atribuir permissões personalizadas.</span><span class="sxs-lookup"><span data-stu-id="144cc-154">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="144cc-155">Aqueles sem permissões não verão a subpasta.</span><span class="sxs-lookup"><span data-stu-id="144cc-155">Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="144cc-156">Para criar uma subpasta de documentos com permissões personalizadas, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="144cc-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="144cc-157">Entre em uma conta que seja membro do grupo de acesso de administradores do site.</span><span class="sxs-lookup"><span data-stu-id="144cc-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="144cc-158">Para obter ajuda, consulte [Como entrar no Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="144cc-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="144cc-159">Vá para o site de equipe isolado e clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="144cc-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="144cc-160">Navegue até a pasta na pasta documentos que conterá a subpasta com permissões personalizadas, crie a pasta e abra-a.</span><span class="sxs-lookup"><span data-stu-id="144cc-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="144cc-161">Clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="144cc-161">Click **Share**.</span></span>

5. <span data-ttu-id="144cc-162">Clique **em Compartilhado com > Avançado**.</span><span class="sxs-lookup"><span data-stu-id="144cc-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="144cc-163">Clique **em Parar de herdar permissões** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="144cc-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="144cc-164">Clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="144cc-164">Click **Share**.</span></span>

8. <span data-ttu-id="144cc-165">Clique **em Compartilhado com > Avançado**.</span><span class="sxs-lookup"><span data-stu-id="144cc-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="144cc-166">Clique **em Conceder Permissões > Compartilhado com > Avançado**.</span><span class="sxs-lookup"><span data-stu-id="144cc-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="144cc-167">Na página permissões, clique em **\<site name> Membros na lista**.</span><span class="sxs-lookup"><span data-stu-id="144cc-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="144cc-168">Na página **\<site name> Membros,** selecione a marca de seleção ao lado do grupo de acesso de membros do site, clique em **Ações,** clique em **Remover** usuários do grupo e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="144cc-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="144cc-169">Para adicionar membros específicos a essa subpasta, clique em **Novo > Adicionar usuários**.</span><span class="sxs-lookup"><span data-stu-id="144cc-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="144cc-170">Na caixa **de diálogo** Compartilhar, digite os nomes das contas de usuário que podem colaborar em arquivos na subpasta e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="144cc-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="144cc-171">Atualize a página da Web para ver os novos resultados.</span><span class="sxs-lookup"><span data-stu-id="144cc-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="144cc-172">Em **Grupos** na navegação à **\<site name>** esquerda, clique no grupo Visitantes e use as etapas 11-14 para especificar o conjunto de contas de usuário que podem exibir os arquivos na subpasta (conforme necessário).</span><span class="sxs-lookup"><span data-stu-id="144cc-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="144cc-173">Em **Grupos** na navegação à **\<site name>** esquerda, clique no grupo Proprietários e use as etapas 11-14 para especificar o conjunto de contas de usuário que podem administrar as permissões na subpasta (conforme necessário).</span><span class="sxs-lookup"><span data-stu-id="144cc-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="144cc-174">Feche a **guia Pessoas e Grupos** no navegador.</span><span class="sxs-lookup"><span data-stu-id="144cc-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="144cc-175">Confira também</span><span class="sxs-lookup"><span data-stu-id="144cc-175">See Also</span></span>

[<span data-ttu-id="144cc-176">Sites de equipe do SharePoint Online isolados</span><span class="sxs-lookup"><span data-stu-id="144cc-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="144cc-177">Configurar uma equipe com isolamento de segurança</span><span class="sxs-lookup"><span data-stu-id="144cc-177">Configure a team with security isolation</span></span>](/microsoft-365/solutions/secure-teams-security-isolation)
