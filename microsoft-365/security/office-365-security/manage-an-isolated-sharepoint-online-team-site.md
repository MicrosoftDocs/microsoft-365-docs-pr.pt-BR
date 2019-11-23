---
title: Gerenciar um site de equipe do SharePoint Online isolado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 'Resumo: Gerencie seu site de equipe do SharePoint Online isolado com estes procedimentos.'
ms.openlocfilehash: fd34a8af35b546266cf5d7cf308dbd387207eb1e
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202442"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="00a6c-103">Gerenciar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="00a6c-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="00a6c-104">**Resumo:** Gerencie seu site de equipe do SharePoint Online isolado com estes procedimentos.</span><span class="sxs-lookup"><span data-stu-id="00a6c-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="00a6c-105">Este artigo descreve as operações de gerenciamento comuns para um site de equipe do SharePoint Online isolado.</span><span class="sxs-lookup"><span data-stu-id="00a6c-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="00a6c-106">Adicionar um novo usuário</span><span class="sxs-lookup"><span data-stu-id="00a6c-106">Add a new user</span></span>

<span data-ttu-id="00a6c-107">Quando alguém novo ingressar no site, você deverá decidir o nível de participação no site:</span><span class="sxs-lookup"><span data-stu-id="00a6c-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="00a6c-108">Administração: adicionar a nova conta de usuário ao grupo de acesso de administradores de site</span><span class="sxs-lookup"><span data-stu-id="00a6c-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="00a6c-109">Colaboração ativa: adicionar a conta de usuário ao grupo de acesso de membros do site</span><span class="sxs-lookup"><span data-stu-id="00a6c-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="00a6c-110">Exibindo: adicionar a conta de usuário ao grupo de acesso de visualizadores de sites</span><span class="sxs-lookup"><span data-stu-id="00a6c-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="00a6c-111">Se você estiver gerenciando contas de usuário e grupos por meio de serviços de domínio do Active Directory (AD DS), adicione os usuários apropriados aos grupos de acesso apropriados usando seus procedimentos normais de gerenciamento de usuários e grupos do AD DS e aguarde a sincronização com o seu Office 365 scriçõe.</span><span class="sxs-lookup"><span data-stu-id="00a6c-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="00a6c-112">Se você estiver gerenciando contas de usuário e grupos através do Office 365, poderá usar o centro de administração do Microsoft 365 ou o Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-112">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="00a6c-113">Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha recebido a função Administrador de conta de usuário ou administrador da empresa e use grupos para adicionar os usuários apropriados aos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="00a6c-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="00a6c-114">Para o PowerShell, primeiro [Conecte-se ao módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="00a6c-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="00a6c-115">Para adicionar uma conta de usuário a um grupo de acesso com seu nome de usuário principal (UPN), use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="00a6c-116">Para adicionar uma conta de usuário a um grupo de acesso com seu nome de exibição, use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="00a6c-117">Adicionar um novo grupo</span><span class="sxs-lookup"><span data-stu-id="00a6c-117">Add a new group</span></span>

<span data-ttu-id="00a6c-118">Para adicionar acesso a um grupo inteiro, você deve decidir o nível de participação de todos os membros do grupo no site:</span><span class="sxs-lookup"><span data-stu-id="00a6c-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="00a6c-119">Administração: Adicionar o grupo ao grupo de acesso de administradores de site</span><span class="sxs-lookup"><span data-stu-id="00a6c-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="00a6c-120">Colaboração ativa: Adicionar o grupo ao grupo de acesso de membros do site</span><span class="sxs-lookup"><span data-stu-id="00a6c-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="00a6c-121">Exibindo: Adicionar o grupo ao grupo de acesso visualizadores de sites</span><span class="sxs-lookup"><span data-stu-id="00a6c-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="00a6c-122">Se você estiver gerenciando contas de usuário e grupos através do AD DS, adicione os grupos apropriados aos grupos apropriados usando seus procedimentos normais de gerenciamento de usuários e grupos do AD DS e aguarde a sincronização com sua assinatura do Office 365.</span><span class="sxs-lookup"><span data-stu-id="00a6c-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="00a6c-123">Se você estiver gerenciando contas de usuário e grupos através do Office 365, poderá usar o centro de administração do Microsoft 365 ou o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="00a6c-124">Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha recebido o administrador da conta de usuário ou a função de administrador da empresa e use grupos para adicionar os grupos apropriados aos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="00a6c-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="00a6c-125">Para o PowerShell, primeiro [Conecte-se ao módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="00a6c-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="00a6c-126">Em seguida, use os seguintes comandos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-126">Then, use the following PowerShell commands:</span></span>
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="00a6c-127">Remover um usuário</span><span class="sxs-lookup"><span data-stu-id="00a6c-127">Remove a user</span></span>

<span data-ttu-id="00a6c-128">Quando o acesso de alguém precisa ser removido do site, você os remove do grupo de acesso para o qual eles são membros atualmente, com base na sua participação no site:</span><span class="sxs-lookup"><span data-stu-id="00a6c-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="00a6c-129">Administração: Remova a conta de usuário do grupo de acesso de administradores de site</span><span class="sxs-lookup"><span data-stu-id="00a6c-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="00a6c-130">Colaboração ativa: Remova a conta de usuário do grupo de acesso de membros do site</span><span class="sxs-lookup"><span data-stu-id="00a6c-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="00a6c-131">Exibição: remover a conta de usuário do grupo de acesso de visualizadores de sites</span><span class="sxs-lookup"><span data-stu-id="00a6c-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="00a6c-132">Se você estiver gerenciando contas de usuário e grupos por meio do AD DS, remova os usuários apropriados dos grupos de acesso apropriados usando seus procedimentos de gerenciamento de usuário e grupo do AD DS normal e aguarde a sincronização com sua assinatura do Office 365.</span><span class="sxs-lookup"><span data-stu-id="00a6c-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="00a6c-133">Se você estiver gerenciando contas de usuário e grupos através do Office 365, poderá usar o centro de administração do Microsoft 365 ou o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="00a6c-134">Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha recebido a função Administrador de conta de usuário ou administrador da empresa e use grupos para remover os usuários apropriados dos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="00a6c-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="00a6c-135">Para o PowerShell, primeiro [Conecte-se ao módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="00a6c-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="00a6c-136">Para remover uma conta de usuário de um grupo de acesso com seu UPN, use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="00a6c-137">Para remover uma conta de usuário de um grupo de acesso com seu nome de exibição, use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="00a6c-138">Remover um grupo</span><span class="sxs-lookup"><span data-stu-id="00a6c-138">Remove a group</span></span>

<span data-ttu-id="00a6c-139">Para remover o acesso de um grupo inteiro, remova o grupo do grupo de acesso para o qual eles são membros atualmente com base em sua participação no site:</span><span class="sxs-lookup"><span data-stu-id="00a6c-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="00a6c-140">Administração: remover o grupo do grupo de acesso de administradores de site</span><span class="sxs-lookup"><span data-stu-id="00a6c-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="00a6c-141">Colaboração ativa: remover o grupo do grupo de acesso de membros do site</span><span class="sxs-lookup"><span data-stu-id="00a6c-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="00a6c-142">Exibição: remover o grupo do grupo de acesso de visualizadores de sites</span><span class="sxs-lookup"><span data-stu-id="00a6c-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="00a6c-143">Se você estiver gerenciando contas de usuário e grupos por meio do Windows Server Active Directory, remova os grupos apropriados dos grupos de acesso apropriados usando seus procedimentos de gerenciamento de usuário e grupo do AD DS normal e aguarde a sincronização com o seu Office 365 scriçõe.</span><span class="sxs-lookup"><span data-stu-id="00a6c-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="00a6c-144">Se você estiver gerenciando contas de usuário e grupos através do Office 365, poderá usar o centro de administração do Microsoft 365 ou o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="00a6c-145">Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha recebido a função Administrador de conta de usuário ou administrador da empresa e use grupos para remover os grupos apropriados dos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="00a6c-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="00a6c-146">Para o PowerShell, primeiro [Conecte-se ao módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="00a6c-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="00a6c-147">Para remover um grupo de um grupo de acesso usando seus nomes de exibição, use o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a6c-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="00a6c-148">Criar uma subpasta documentos com permissões personalizadas</span><span class="sxs-lookup"><span data-stu-id="00a6c-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="00a6c-149">Em alguns casos, um subconjunto das pessoas que trabalham dentro do site isolado precisa de um local mais privado para colaborar.</span><span class="sxs-lookup"><span data-stu-id="00a6c-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="00a6c-150">Para sites do SharePoint Online, você pode criar uma subpasta na pasta documentos do site e atribuir permissões personalizadas.</span><span class="sxs-lookup"><span data-stu-id="00a6c-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="00a6c-151">Aqueles sem permissões não verão a subpasta.</span><span class="sxs-lookup"><span data-stu-id="00a6c-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="00a6c-152">Para criar uma subpasta documentos com permissões personalizadas, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="00a6c-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="00a6c-153">Entre no Office 365 com uma conta que seja membro do grupo de acesso de administradores para o site.</span><span class="sxs-lookup"><span data-stu-id="00a6c-153">Sign in to Office 365 with an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="00a6c-154">Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="00a6c-154">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="00a6c-155">Vá para o site de equipe isolado e clique em **documentos**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="00a6c-156">Navegue até a pasta na pasta documentos que conterá a subpasta com permissões personalizadas, crie a pasta e, em seguida, abra-a.</span><span class="sxs-lookup"><span data-stu-id="00a6c-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="00a6c-157">Clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="00a6c-158">Clique em **compartilhado com > avançado**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="00a6c-159">Clique em **parar de herdar permissões**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="00a6c-160">Clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="00a6c-161">Clique em **compartilhado com > avançado**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="00a6c-162">Clique em **conceder permissões > compartilhado com > avançado**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="00a6c-163">Na página permissões, clique em \*\* \<nome do site> membros da lista\*\*.</span><span class="sxs-lookup"><span data-stu-id="00a6c-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="00a6c-164">Na página \*\* \<nome do site> Membros\*\* , selecione a marca de seleção ao lado do grupo de acesso de membros do site, clique em **ações**, clique em **remover usuários do grupo**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="00a6c-165">Para adicionar membros específicos a essa subpasta, clique em **novo > adicionar usuários**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="00a6c-166">Na caixa de diálogo **compartilhar** , digite os nomes das contas de usuário que podem colaborar em arquivos na subpasta e, em seguida, clique em **compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="00a6c-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="00a6c-167">Atualize a página da Web para ver os novos resultados.</span><span class="sxs-lookup"><span data-stu-id="00a6c-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="00a6c-168">Em **grupos** na navegação à esquerda, clique no grupo \*\* \<nome do site> visitantes\*\* e use as etapas 11-14 para especificar o conjunto de contas de usuário que podem exibir os arquivos na subpasta (conforme necessário).</span><span class="sxs-lookup"><span data-stu-id="00a6c-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="00a6c-169">Em **grupos** na navegação à esquerda, clique no grupo \*\* \<nome do site> proprietários\*\* e use as etapas 11-14 para especificar o conjunto de contas de usuário que podem administrar as permissões na subpasta (conforme necessário).</span><span class="sxs-lookup"><span data-stu-id="00a6c-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="00a6c-170">Feche a guia **pessoas e grupos** no navegador.</span><span class="sxs-lookup"><span data-stu-id="00a6c-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="00a6c-171">Confira também</span><span class="sxs-lookup"><span data-stu-id="00a6c-171">See Also</span></span>

[<span data-ttu-id="00a6c-172">Sites de equipe do SharePoint Online isolados</span><span class="sxs-lookup"><span data-stu-id="00a6c-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="00a6c-173">Projetar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="00a6c-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="00a6c-174">Implantar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="00a6c-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



