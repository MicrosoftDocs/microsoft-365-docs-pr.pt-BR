---
title: Implantar um site de equipe do SharePoint Online isolado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 'Resumo: implante um novo site de equipe do SharePoint Online isolado com as instruções passo a passo.'
ms.openlocfilehash: 67c6a5304e067ac847c9f8158d48a588ca118220
ms.sourcegitcommit: 550ea6f093ec35182e7c65a2811e9bfb07ec7d01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38039110"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="3f6bb-103">Implantar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="3f6bb-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="3f6bb-104">**Resumo:** Implante um novo site de equipe do SharePoint Online isolado com as instruções passo a passo.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="3f6bb-105">Este artigo é um guia de implantação passo a passo para criar e configurar um site de equipe do SharePoint Online isolado no Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="3f6bb-106">Essas etapas pressupõem o uso dos três grupos padrão do SharePoint e níveis de permissão correspondentes, com um único grupo de acesso baseado em AD (Active Directory) do Azure para cada nível de acesso.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="3f6bb-107">Fase 1: criar e preencher os grupos de acesso ao site de equipe</span><span class="sxs-lookup"><span data-stu-id="3f6bb-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="3f6bb-108">Nesta fase, você cria os três grupos de acesso baseados no AD do Azure para os três grupos padrão do SharePoint e os preenche com as contas de usuário apropriadas.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3f6bb-109">As etapas a seguir pressupõem que todas as contas de usuário necessárias já existam e que recebem as licenças apropriadas.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="3f6bb-110">Caso contrário, adicione-os e atribua licenças antes de prosseguir para a etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="3f6bb-111">Etapa 1: listar os administradores do SharePoint Online para o site</span><span class="sxs-lookup"><span data-stu-id="3f6bb-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="3f6bb-112">Determine o conjunto de contas de usuário correspondentes aos administradores do SharePoint Online para o site de equipe isolado.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="3f6bb-113">Se você estiver gerenciando contas de usuário e grupos através do Office 365 e quiser usar o Windows PowerShell, faça uma lista de seus nomes principais de usuário (UPNs) (exemplo de UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3f6bb-113">If you are managing user accounts and groups through Office 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="3f6bb-114">Etapa 2: listar os membros do site</span><span class="sxs-lookup"><span data-stu-id="3f6bb-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="3f6bb-115">Determine o conjunto de contas de usuário correspondentes aos membros do site de equipe isolado, aqueles que serão colaborativos nos recursos armazenados no site.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="3f6bb-116">Se você estiver gerenciando contas de usuário e grupos através do Office 365 e quiser usar o PowerShell, faça uma lista de seus UPNs.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-116">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="3f6bb-117">Se houver muitos membros do site, você poderá armazenar a lista de UPNs em um arquivo de texto e adicioná-los todos com um único comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="3f6bb-118">Etapa 3: listar os visualizadores para o site</span><span class="sxs-lookup"><span data-stu-id="3f6bb-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="3f6bb-119">Determinar o conjunto de contas de usuário correspondentes aos visualizadores do site de equipe isolado, aqueles que podem exibir os recursos armazenados no site, mas não modificá-los ou colaborar diretamente em seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="3f6bb-120">Se você estiver gerenciando contas de usuário e grupos através do Office 365 e quiser usar o PowerShell, faça uma lista de seus UPNs.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-120">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="3f6bb-121">Se houver muitos membros do site, você poderá armazenar a lista de UPNs em um arquivo de texto e adicioná-los todos com um único comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="3f6bb-122">Os visualizadores do site podem incluir gerência executiva, assessoria jurídica ou participantes entre departamentos.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="3f6bb-123">Etapa 4: criar os três grupos de acesso para o site no Azure AD</span><span class="sxs-lookup"><span data-stu-id="3f6bb-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="3f6bb-124">Você precisa criar os seguintes grupos de acesso no Azure AD:</span><span class="sxs-lookup"><span data-stu-id="3f6bb-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="3f6bb-125">Administradores de site (que conterá a lista da etapa 1)</span><span class="sxs-lookup"><span data-stu-id="3f6bb-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="3f6bb-126">Membros do site (que conterá a lista da etapa 2)</span><span class="sxs-lookup"><span data-stu-id="3f6bb-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="3f6bb-127">Visualizadores de site (que conterá a lista da etapa 3)</span><span class="sxs-lookup"><span data-stu-id="3f6bb-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="3f6bb-128">No navegador, vá para o portal do Azure em [https://portal.azure.com](https://portal.azure.com) e entre com as credenciais de uma conta que tenha sido atribuída com o administrador de gerenciamento de usuário ou a função de administrador da empresa.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="3f6bb-129">No Portal do Azure, clique em **Azure Active Directory > Grupos**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="3f6bb-130">Na folha **Grupos – Todos os grupos**, clique em **+ Novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="3f6bb-131">Na folha **novo grupo** :</span><span class="sxs-lookup"><span data-stu-id="3f6bb-131">On the **New Group** blade:</span></span>
    
  - <span data-ttu-id="3f6bb-132">Selecione **Segurança** em **Tipo de grupo**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-132">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="3f6bb-133">Digite o nome do grupo em **nome**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-133">Type the group name in **Name**.</span></span>
    
  - <span data-ttu-id="3f6bb-134">Digite uma descrição do grupo em **Descrição do grupo**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-134">Type a description of the group in **Group description**.</span></span>
    
  - <span data-ttu-id="3f6bb-135">Escolha **Atribuído** em **Tipo de Associação**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="3f6bb-136">Clique em **Criar** e, em seguida, feche a folha **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="3f6bb-137">Repita as etapas 3-5 para seus grupos adicionais.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3f6bb-138">Você precisa usar o portal do Azure para criar os grupos de modo que eles tenham recursos do Office habilitados.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="3f6bb-139">Se um site isolado do SharePoint Online for configurado posteriormente como um site altamente confidencial com um rótulo de proteção de informações do Azure para criptografar arquivos e atribuir permissão a grupos específicos, os grupos permitidos deverão ter sido criados com recursos do Office habilitados.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="3f6bb-140">Você não pode alterar a configuração de recursos do Office de um grupo do Azure AD após ele ter sido criado.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="3f6bb-141">Aqui está a configuração resultante com os três grupos de acesso de site.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![Os três grupos de acesso para sua implantação de um site isolado do SharePoint Online.](../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="3f6bb-143">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-143">Step 5.</span></span> <span data-ttu-id="3f6bb-144">Adicionar as contas de usuário aos grupos de acesso</span><span class="sxs-lookup"><span data-stu-id="3f6bb-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="3f6bb-145">Nesta etapa, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3f6bb-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="3f6bb-146">Adicionar a lista de usuários da etapa 1 ao grupo de acesso de administradores de site</span><span class="sxs-lookup"><span data-stu-id="3f6bb-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="3f6bb-147">Adicionar a lista de usuários da etapa 2 ao grupo de acesso de membros do site</span><span class="sxs-lookup"><span data-stu-id="3f6bb-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="3f6bb-148">Adicionar a lista de usuários da etapa 3 ao grupo de acesso de visualizadores de sites</span><span class="sxs-lookup"><span data-stu-id="3f6bb-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="3f6bb-149">Se você estiver gerenciando contas de usuário e grupos por meio de serviços de domínio do Active Directory (AD DS), adicione usuários aos grupos de acesso apropriados usando seus procedimentos normais de gerenciamento de usuários e grupos do AD DS e aguarde a sincronização com sua assinatura do Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="3f6bb-150">Se você estiver gerenciando contas de usuário e grupos através do Office 365, poderá usar o centro de administração do Microsoft 365 ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="3f6bb-151">Se você tiver nomes de grupo duplicados para qualquer um dos grupos de acesso, deverá usar o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="3f6bb-152">Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha atribuído a função Administrador de conta de usuário ou administrador da empresa e use grupos para adicionar as contas de usuário e grupos apropriados aos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="3f6bb-153">Para o PowerShell, primeiro [Conecte-se ao módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="3f6bb-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="3f6bb-154">Em seguida, use o seguinte bloco de comando para adicionar uma conta de usuário individual a um grupo de acesso:</span><span class="sxs-lookup"><span data-stu-id="3f6bb-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="3f6bb-155">Para um arquivo de texto que contém todos os comandos do PowerShell e uma planilha de configuração do Excel que gera comandos do PowerShell com base em seus nomes de conta de usuário e de grupo, baixe o [Kit de implantação de site de equipe do SharePoint Online isolado](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span><span class="sxs-lookup"><span data-stu-id="3f6bb-155">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 
  
<span data-ttu-id="3f6bb-156">Se você armazenou os UPNs de contas de usuário para qualquer um dos grupos de acesso em um arquivo de texto, você pode usar o seguinte bloco de comando do PowerShell para adicionar todos ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="3f6bb-156">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="3f6bb-157">Para o PowerShell, use o seguinte bloco de comando para adicionar um grupo individual a um grupo de acesso:</span><span class="sxs-lookup"><span data-stu-id="3f6bb-157">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="3f6bb-158">Os resultados devem ser os seguintes:</span><span class="sxs-lookup"><span data-stu-id="3f6bb-158">The results should be the following:</span></span>
  
- <span data-ttu-id="3f6bb-159">O grupo Administradores do site do Azure AD contém as contas de usuário ou grupos de administrador do site</span><span class="sxs-lookup"><span data-stu-id="3f6bb-159">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="3f6bb-160">O grupo membros do site do Azure AD contém as contas de usuário ou grupos do site membro</span><span class="sxs-lookup"><span data-stu-id="3f6bb-160">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="3f6bb-161">O grupo Visualizador do site do Azure AD contém as contas de usuário ou grupos que só podem exibir o conteúdo do site</span><span class="sxs-lookup"><span data-stu-id="3f6bb-161">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="3f6bb-162">Valide a lista de membros do grupo para cada grupo de acesso com o centro de administração do Microsoft 365 ou com o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3f6bb-162">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="3f6bb-163">Aqui está a configuração resultante com os três grupos de acesso de site preenchidos com contas de usuário ou grupos.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-163">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![Os três grupos de acesso preenchidos com contas de usuário.](../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="3f6bb-165">Fase 2: criar e configurar o site de equipe isolado</span><span class="sxs-lookup"><span data-stu-id="3f6bb-165">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="3f6bb-166">Nesta fase, você cria o site do SharePoint Online isolado e configura as permissões para os níveis de permissão padrão do SharePoint Online para usar seus novos grupos de acesso baseados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-166">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span>
  
<span data-ttu-id="3f6bb-167">Primeiro, crie o site de equipe do SharePoint Online com estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-167">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="3f6bb-168">Entre no centro de administração com uma conta que também será usada para administrar o site de equipe do SharePoint Online (um administrador do SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="3f6bb-168">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="3f6bb-169">Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="3f6bb-169">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="3f6bb-170">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-170">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="3f6bb-171">Na nova guia **SharePoint** do navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-171">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="3f6bb-172">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-172">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="3f6bb-173">Em **nome do site**, digite um nome para o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-173">In **Site name**, type a name for the team site.</span></span> 
    
6. <span data-ttu-id="3f6bb-174">Em **Descrição do site de equipe,** digite uma descrição opcional do objetivo do site.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-174">In **Team site description,** type an optional description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="3f6bb-175">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-175">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="3f6bb-176">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-176">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="3f6bb-177">Em seguida, no novo site de equipe do SharePoint Online, configure as permissões.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-177">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="3f6bb-178">Na barra de ferramentas, clique no ícone Configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-178">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
2. <span data-ttu-id="3f6bb-179">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-179">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
3. <span data-ttu-id="3f6bb-180">Na nova guia **Permissões** do navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-180">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
4. <span data-ttu-id="3f6bb-181">Na caixa de diálogo **Configurações de Solicitações de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir solicitações de acesso** (para que todas as três caixas de seleção sejam desmarcadas) e, depois, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-181">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
5. <span data-ttu-id="3f6bb-182">Na guia **permissões** do navegador, clique em \*\* \<nome do site> Membros\*\* na lista.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-182">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
6. <span data-ttu-id="3f6bb-183">Em **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-183">In **People and Groups**, click **New**.</span></span>
    
7. <span data-ttu-id="3f6bb-184">Na caixa de diálogo **compartilhar** , digite o nome do grupo de acesso de membros do site, selecione-o e clique em **compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-184">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
8. <span data-ttu-id="3f6bb-185">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-185">Click the back button on your browser.</span></span>
    
9. <span data-ttu-id="3f6bb-186">Clique em \*\* \<nome do site> proprietários\*\* da lista.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-186">Click **\<site name> Owners** in the list.</span></span>
    
10. <span data-ttu-id="3f6bb-187">Em **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-187">In **People and Groups**, click **New**.</span></span>
    
11. <span data-ttu-id="3f6bb-188">Na caixa de diálogo **compartilhar** , digite o nome do grupo de acesso de administradores de site, selecione-o e clique em **compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-188">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
12. <span data-ttu-id="3f6bb-189">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-189">Click the back button on your browser.</span></span>
    
13. <span data-ttu-id="3f6bb-190">Clique em \*\* \<nome do site> visitantes\*\* na lista.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-190">Click **\<site name> Visitors** in the list.</span></span>
    
14. <span data-ttu-id="3f6bb-191">Em **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-191">In **People and Groups**, click **New**.</span></span>
    
15. <span data-ttu-id="3f6bb-192">Na caixa de diálogo **compartilhar** , digite o nome do grupo de acesso visualizadores de sites, selecione-o e clique em **compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-192">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="3f6bb-193">Feche a guia **Permissões** do navegador.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-193">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="3f6bb-194">Os resultados dessas configurações de permissão são:</span><span class="sxs-lookup"><span data-stu-id="3f6bb-194">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="3f6bb-195">O grupo \*\* \<nome do site> proprietários\*\* do SharePoint contém o grupo de acesso de administradores de site, em que todos os membros têm o nível de permissão **controle total** .</span><span class="sxs-lookup"><span data-stu-id="3f6bb-195">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="3f6bb-196">O \*\* \<nome do site>\*\* grupo de membros do SharePoint contém o grupo de acesso de membros do site, em que todos os membros têm o nível de permissão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="3f6bb-196">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="3f6bb-197">O \*\* \<nome do site> grupo visitantes\*\* do SharePoint contém o grupo de acesso visualizadores do site, em que todos os membros têm o nível de permissão de **leitura** .</span><span class="sxs-lookup"><span data-stu-id="3f6bb-197">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="3f6bb-198">A capacidade de os membros de convidar outros membros ou de não membros solicitarem o acesso está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-198">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="3f6bb-199">Aqui está a configuração resultante com os três grupos do SharePoint para o site configurado para usar os três grupos de acesso, que são preenchidos com contas de usuário ou grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-199">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![A configuração final do seu site isolado do SharePoint Online com grupos de acesso e contas de usuário.](../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="3f6bb-201">Você e os membros do site, por meio da Associação de grupo em um dos grupos de acesso, agora podem colaborar usando os recursos do site.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-201">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="3f6bb-202">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="3f6bb-202">Next step</span></span>

<span data-ttu-id="3f6bb-203">Quando você precisar alterar a associação de grupo de acesso ao site ou criar uma pasta de documentos com permissões personalizadas, consulte [gerenciar um site de equipe isolado do SharePoint Online](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="3f6bb-203">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3f6bb-204">Confira também</span><span class="sxs-lookup"><span data-stu-id="3f6bb-204">See Also</span></span>

[<span data-ttu-id="3f6bb-205">Sites de equipe do SharePoint Online isolados</span><span class="sxs-lookup"><span data-stu-id="3f6bb-205">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="3f6bb-206">Projetar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="3f6bb-206">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="3f6bb-207">Gerenciar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="3f6bb-207">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



