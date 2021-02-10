---
title: Implantar um site de equipe do SharePoint Online isolado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Use este guia de implantação passo a passo para criar e configurar um site de equipe do SharePoint Online isolado no Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b1f0342afc92b4540330417ad0fc9cabe1dc8a8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165494"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="060ed-103">Implantar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="060ed-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="060ed-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="060ed-104">**Applies to**</span></span>
- [<span data-ttu-id="060ed-105">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="060ed-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="060ed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="060ed-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="060ed-107">**Resumo:** Implante um novo site de equipe isolado do SharePoint Online com estas instruções passo a passo.</span><span class="sxs-lookup"><span data-stu-id="060ed-107">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>

<span data-ttu-id="060ed-108">Este artigo é um guia de implantação passo a passo para criar e configurar um site de equipe isolado do SharePoint Online no Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="060ed-108">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="060ed-109">Essas etapas assumem o uso dos três grupos padrão do SharePoint e níveis de permissão correspondentes, com um único grupo de acesso baseado no Azure Active Directory (AD) para cada nível de acesso.</span><span class="sxs-lookup"><span data-stu-id="060ed-109">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="060ed-110">Fase 1: Criar e preencher os grupos de acesso ao site de equipe</span><span class="sxs-lookup"><span data-stu-id="060ed-110">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="060ed-111">Nesta fase, você cria os três grupos de acesso baseados no Azure AD para os três grupos padrão do SharePoint e os preenche com as contas de usuário apropriadas.</span><span class="sxs-lookup"><span data-stu-id="060ed-111">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="060ed-112">As etapas a seguir presumem que todas as contas de usuário necessárias já existem e que foram atribuídas as licenças apropriadas.</span><span class="sxs-lookup"><span data-stu-id="060ed-112">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="060ed-113">Caso não tenha, adicione-os e atribua licenças antes de prosseguir para a etapa 1.</span><span class="sxs-lookup"><span data-stu-id="060ed-113">If not, please add them and assign licenses before proceeding to step 1.</span></span>

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="060ed-114">Etapa 1: Listar os administradores do SharePoint Online para o site</span><span class="sxs-lookup"><span data-stu-id="060ed-114">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="060ed-115">Determine o conjunto de contas de usuário correspondentes aos administradores do SharePoint Online para o site de equipe isolado.</span><span class="sxs-lookup"><span data-stu-id="060ed-115">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>

<span data-ttu-id="060ed-116">Se você estiver gerenciando contas de usuário e grupos por meio do Microsoft 365 e quiser usar o Windows PowerShell, faça uma lista de seus nomes upNs (upns de exemplo: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="060ed-116">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>

### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="060ed-117">Etapa 2: Listar os membros do site</span><span class="sxs-lookup"><span data-stu-id="060ed-117">Step 2: List the members for the site</span></span>

<span data-ttu-id="060ed-118">Determine o conjunto de contas de usuário correspondentes aos membros do site de equipe isolado, aqueles que colaborarão em recursos armazenados no site.</span><span class="sxs-lookup"><span data-stu-id="060ed-118">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>

<span data-ttu-id="060ed-119">Se você estiver gerenciando contas e grupos de usuários por meio do Microsoft 365 e quiser usar o PowerShell, faça uma lista de seus UPNs.</span><span class="sxs-lookup"><span data-stu-id="060ed-119">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="060ed-120">Se houver muitos membros do site, você poderá armazenar a lista de UPNs em um arquivo de texto e adicioná-los todos com um único comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="060ed-120">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="060ed-121">Etapa 3: Listar os visualizadores do site</span><span class="sxs-lookup"><span data-stu-id="060ed-121">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="060ed-122">Determine o conjunto de contas de usuário correspondentes aos visualizadores do site de equipe isolado, aqueles que podem exibir os recursos armazenados no site, mas não modificá-los ou colaborar diretamente em seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="060ed-122">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>

<span data-ttu-id="060ed-123">Se você estiver gerenciando contas e grupos de usuários por meio do Microsoft 365 e quiser usar o PowerShell, faça uma lista de seus UPNs.</span><span class="sxs-lookup"><span data-stu-id="060ed-123">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="060ed-124">Se houver muitos membros do site, você poderá armazenar a lista de UPNs em um arquivo de texto e adicioná-los todos com um único comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="060ed-124">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

<span data-ttu-id="060ed-125">Os visitantes do site podem incluir gerenciamento executivo, consultoria jurídica ou participantes entre departamentos.</span><span class="sxs-lookup"><span data-stu-id="060ed-125">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="060ed-126">Etapa 4: Criar os três grupos de acesso para o site no Azure AD</span><span class="sxs-lookup"><span data-stu-id="060ed-126">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="060ed-127">Você precisa criar os seguintes grupos de acesso no Azure AD:</span><span class="sxs-lookup"><span data-stu-id="060ed-127">You need to create the following access groups in Azure AD:</span></span>

- <span data-ttu-id="060ed-128">Administradores de site (que conterão a lista da etapa 1)</span><span class="sxs-lookup"><span data-stu-id="060ed-128">Site admins (which will contain the list from step 1)</span></span>
- <span data-ttu-id="060ed-129">Membros do site (que conterão a lista da etapa 2)</span><span class="sxs-lookup"><span data-stu-id="060ed-129">Site members (which will contain the list from step 2)</span></span>
- <span data-ttu-id="060ed-130">Visualizadores do site (que conterão a lista da etapa 3)</span><span class="sxs-lookup"><span data-stu-id="060ed-130">Site viewers (which will contain the list from step 3)</span></span>

1. <span data-ttu-id="060ed-131">No navegador, vá para o portal do Azure em e entre com as credenciais de uma conta que tenha sido atribuída com a função de Administrador de Gerenciamento de Usuários ou <https://portal.azure.com> Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="060ed-131">In your browser, go to the Azure portal at <https://portal.azure.com> and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>

2. <span data-ttu-id="060ed-132">No Portal do Azure, clique em **Azure Active Directory > Grupos**.</span><span class="sxs-lookup"><span data-stu-id="060ed-132">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="060ed-133">Na folha **Grupos – Todos os grupos**, clique em **+ Novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="060ed-133">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="060ed-134">Na folha **Novo** Grupo:</span><span class="sxs-lookup"><span data-stu-id="060ed-134">On the **New Group** blade:</span></span>

   - <span data-ttu-id="060ed-135">Selecione **Segurança** em **Tipo de grupo**.</span><span class="sxs-lookup"><span data-stu-id="060ed-135">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="060ed-136">Digite o nome do grupo no **nome.**</span><span class="sxs-lookup"><span data-stu-id="060ed-136">Type the group name in **Name**.</span></span>

   - <span data-ttu-id="060ed-137">Digite uma descrição do grupo na **descrição do grupo.**</span><span class="sxs-lookup"><span data-stu-id="060ed-137">Type a description of the group in **Group description**.</span></span>

   - <span data-ttu-id="060ed-138">Escolha **Atribuído** em **Tipo de Associação**.</span><span class="sxs-lookup"><span data-stu-id="060ed-138">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="060ed-139">Clique em **Criar** e, em seguida, feche a folha **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="060ed-139">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="060ed-140">Repita as etapas de 3 a 5 para seus grupos adicionais.</span><span class="sxs-lookup"><span data-stu-id="060ed-140">Repeat steps 3-5 for your additional groups.</span></span>

> [!NOTE]
> <span data-ttu-id="060ed-141">Você precisa usar o portal do Azure para criar os grupos para que eles tenham recursos do Office habilitados.</span><span class="sxs-lookup"><span data-stu-id="060ed-141">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="060ed-142">Se um site isolado do SharePoint Online for configurado posteriormente como um site Altamente Confidencial com um rótulo de Proteção de Informações do Azure para criptografar arquivos e atribuir permissão a grupos específicos, os grupos permitidos deverão ter sido criados com os recursos do Office habilitados.</span><span class="sxs-lookup"><span data-stu-id="060ed-142">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="060ed-143">Você não pode alterar a configuração de recursos do Office de um grupo do Azure AD depois que ele tiver sido criado.</span><span class="sxs-lookup"><span data-stu-id="060ed-143">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span>

<span data-ttu-id="060ed-144">Esta é a configuração resultante com os três grupos de acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="060ed-144">Here is your resulting configuration with the three site access groups.</span></span>

![Os três grupos de acesso para sua implantação de um site isolado do SharePoint Online.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="060ed-146">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="060ed-146">Step 5.</span></span> <span data-ttu-id="060ed-147">Adicionar as contas de usuário aos grupos de acesso</span><span class="sxs-lookup"><span data-stu-id="060ed-147">Add the user accounts to the access groups</span></span>

<span data-ttu-id="060ed-148">Nesta etapa, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="060ed-148">In this step, do the following:</span></span>

1. <span data-ttu-id="060ed-149">Adicione a lista de usuários da etapa 1 ao grupo de acesso de administradores do site.</span><span class="sxs-lookup"><span data-stu-id="060ed-149">Add the list of users from step 1 to the site admins access group.</span></span>
2. <span data-ttu-id="060ed-150">Adicione a lista de usuários da etapa 2 ao grupo de acesso de membros do site.</span><span class="sxs-lookup"><span data-stu-id="060ed-150">Add the list of users from step 2 to the site members access group.</span></span>
3. <span data-ttu-id="060ed-151">Adicione a lista de usuários da etapa 3 ao grupo de acesso dos visualizadores do site.</span><span class="sxs-lookup"><span data-stu-id="060ed-151">Add the list of users from step 3 to the site viewers access group.</span></span>

<span data-ttu-id="060ed-152">Se você estiver gerenciando contas e grupos de usuários por meio do AD DS (Serviços de Domínio Active Directory), adicione usuários aos grupos de acesso apropriados usando os procedimentos normais de gerenciamento de usuários e grupos do AD DS e aguarde a sincronização com sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="060ed-152">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>

<span data-ttu-id="060ed-153">Se você estiver gerenciando contas e grupos de usuários por meio do Office 365, poderá usar o Centro de administração do Microsoft 365 ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="060ed-153">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="060ed-154">Se você tiver nomes de grupo duplicados para qualquer um dos grupos de acesso, use o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="060ed-154">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>

<span data-ttu-id="060ed-155">Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função de Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para adicionar as contas de usuário e grupos apropriados aos grupos de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="060ed-155">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>

<span data-ttu-id="060ed-156">Para o PowerShell, primeiro [conecte-se ao Azure Active Directory PowerShell para o módulo do Graph.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="060ed-156">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="060ed-157">Em seguida, use o seguinte bloco de comando para adicionar uma conta de usuário individual a um grupo de acesso:</span><span class="sxs-lookup"><span data-stu-id="060ed-157">Next, use the following command block to add an individual user account to an access group:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="060ed-158">Se você armazenou os UPNs de contas de usuário para qualquer um dos grupos de acesso em um arquivo de texto, poderá usar o seguinte bloco de comando do PowerShell para adicioná-los todos de uma só vez:</span><span class="sxs-lookup"><span data-stu-id="060ed-158">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="060ed-159">Para o PowerShell, use o seguinte bloco de comando para adicionar um grupo individual a um grupo de acesso:</span><span class="sxs-lookup"><span data-stu-id="060ed-159">For PowerShell, use the following command block to add an individual group to an access group:</span></span>

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="060ed-160">Os resultados devem ser os seguintes:</span><span class="sxs-lookup"><span data-stu-id="060ed-160">The results should be the following:</span></span>

- <span data-ttu-id="060ed-161">O grupo de administradores do site do Azure AD contém as contas de usuário ou grupos de administradores do site</span><span class="sxs-lookup"><span data-stu-id="060ed-161">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
- <span data-ttu-id="060ed-162">O grupo de membros do site do Azure AD contém as contas de usuário ou grupos de membros do site</span><span class="sxs-lookup"><span data-stu-id="060ed-162">The site members Azure AD group contains the site member user accounts or groups</span></span>
- <span data-ttu-id="060ed-163">O grupo de visualizadores do site do Azure AD contém as contas de usuário ou grupos que só podem exibir o conteúdo do site</span><span class="sxs-lookup"><span data-stu-id="060ed-163">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>

<span data-ttu-id="060ed-164">Valide a lista de membros do grupo para cada grupo de acesso com o centro de administração do Microsoft 365 ou com o seguinte bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="060ed-164">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="060ed-165">Esta é a configuração resultante com os três grupos de acesso ao site preenchidos com contas de usuário ou grupos.</span><span class="sxs-lookup"><span data-stu-id="060ed-165">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>

![Os três grupos de acesso preenchidos com contas de usuário.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="060ed-167">Fase 2: Criar e configurar o site de equipe isolado</span><span class="sxs-lookup"><span data-stu-id="060ed-167">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="060ed-168">Nesta fase, você cria o site isolado do SharePoint Online e configura as permissões para os níveis de permissão padrão do SharePoint Online para usar seus novos grupos de acesso baseados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="060ed-168">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="060ed-169">Por padrão, novos sites de equipe incluem um grupo do Microsoft 365 e outros recursos relacionados, mas neste caso, criaremos um site de equipe sem um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="060ed-169">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="060ed-170">Isso permite manter permissões inteiramente por meio do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="060ed-170">This allows maintaining permissions entirely through SharePoint.</span></span>

<span data-ttu-id="060ed-171">Primeiro, crie o site de equipe do SharePoint Online com estas etapas.</span><span class="sxs-lookup"><span data-stu-id="060ed-171">First, create the SharePoint Online team site with these steps.</span></span>

1. <span data-ttu-id="060ed-172">Entre no centro de administração do Microsoft 365 com uma conta que também será usada para administrar o site de equipe do SharePoint Online (um administrador do SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="060ed-172">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="060ed-173">Para obter ajuda, consulte [Onde entrar no Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="060ed-173">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="060ed-174">No Centro de administração do Microsoft 365, em **Centros de administração,** clique **em SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="060ed-174">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="060ed-175">No centro de administração do SharePoint, **expanda Sites** e clique em **Sites ativos.**</span><span class="sxs-lookup"><span data-stu-id="060ed-175">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="060ed-176">Clique **em** Criar e escolha **Outras opções.**</span><span class="sxs-lookup"><span data-stu-id="060ed-176">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="060ed-177">In the **Choose a template** list, choose Team **site**.</span><span class="sxs-lookup"><span data-stu-id="060ed-177">In the **Choose a template** list, choose **Team site**.</span></span>

6. <span data-ttu-id="060ed-178">No **nome do** site, digite um nome para o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="060ed-178">In **Site name**, type a name for the team site.</span></span>

7. <span data-ttu-id="060ed-179">No **administrador principal,** digite a conta com a qual você está conectado.</span><span class="sxs-lookup"><span data-stu-id="060ed-179">In **Primary administrator**, type the account that you are logged in with.</span></span>

8. <span data-ttu-id="060ed-180">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="060ed-180">Click **Finish**.</span></span>

<span data-ttu-id="060ed-181">Em seguida, no novo site de equipe do SharePoint Online, configure as permissões.</span><span class="sxs-lookup"><span data-stu-id="060ed-181">Next, from the new SharePoint Online team site, configure permissions.</span></span>

1. <span data-ttu-id="060ed-182">Na barra de ferramentas, clique no ícone Configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="060ed-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="060ed-183">Em **Compartilhamento de** sites, **clique em Alterar como os membros podem compartilhar.**</span><span class="sxs-lookup"><span data-stu-id="060ed-183">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="060ed-184">Choose the **Only site owners can share files, folders, and the site**.</span><span class="sxs-lookup"><span data-stu-id="060ed-184">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="060ed-185">Definir **Permitir solicitações de acesso** como **Desligado.**</span><span class="sxs-lookup"><span data-stu-id="060ed-185">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="060ed-186">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="060ed-186">Click **Save**.</span></span>

6. <span data-ttu-id="060ed-187">No painel **Permissões,** clique em **Configurações avançadas de permissões.**</span><span class="sxs-lookup"><span data-stu-id="060ed-187">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>

7. <span data-ttu-id="060ed-188">Na guia **Permissões** do navegador, clique **\<site name> em Membros** na lista.</span><span class="sxs-lookup"><span data-stu-id="060ed-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>

8. <span data-ttu-id="060ed-189">Em **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="060ed-189">In **People and Groups**, click **New**.</span></span>

9. <span data-ttu-id="060ed-190">Na caixa **de** diálogo Compartilhar, digite o nome do grupo de acesso de membros do site, selecione-o e clique em **Compartilhar.**</span><span class="sxs-lookup"><span data-stu-id="060ed-190">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>

10. <span data-ttu-id="060ed-191">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="060ed-191">Click the back button on your browser.</span></span>

11. <span data-ttu-id="060ed-192">Clique **\<site name> em** Proprietários na lista.</span><span class="sxs-lookup"><span data-stu-id="060ed-192">Click **\<site name> Owners** in the list.</span></span>

12. <span data-ttu-id="060ed-193">Em **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="060ed-193">In **People and Groups**, click **New**.</span></span>

13. <span data-ttu-id="060ed-194">Na caixa **de** diálogo Compartilhar, digite o nome do grupo de acesso de administradores do site, selecione-o e clique em **Compartilhar.**</span><span class="sxs-lookup"><span data-stu-id="060ed-194">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="060ed-195">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="060ed-195">Click the back button on your browser.</span></span>

15. <span data-ttu-id="060ed-196">Clique **\<site name> em** Visitantes na lista.</span><span class="sxs-lookup"><span data-stu-id="060ed-196">Click **\<site name> Visitors** in the list.</span></span>

16. <span data-ttu-id="060ed-197">Em **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="060ed-197">In **People and Groups**, click **New**.</span></span>

17. <span data-ttu-id="060ed-198">Na caixa **de** diálogo Compartilhar, digite o nome do grupo de acesso dos visualizadores do site, selecione-o e clique em **Compartilhar.**</span><span class="sxs-lookup"><span data-stu-id="060ed-198">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="060ed-199">Feche a guia **Permissões** do navegador.</span><span class="sxs-lookup"><span data-stu-id="060ed-199">Close the **Permissions** tab of your browser.</span></span>

<span data-ttu-id="060ed-200">Os resultados dessas configurações de permissão são:</span><span class="sxs-lookup"><span data-stu-id="060ed-200">The results of these permission settings are:</span></span>

- <span data-ttu-id="060ed-201">O **\<site name> grupo proprietários** do SharePoint contém o grupo de acesso de administradores de site, no qual todos os membros têm o **nível de** permissão Controle total.</span><span class="sxs-lookup"><span data-stu-id="060ed-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
- <span data-ttu-id="060ed-202">O **\<site name> grupo Membros** do SharePoint contém o grupo de acesso de membros do site, no qual todos os membros têm o **nível de** permissão Editar.</span><span class="sxs-lookup"><span data-stu-id="060ed-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
- <span data-ttu-id="060ed-203">O **\<site name> grupo Visitantes** do SharePoint contém o grupo de acesso dos visualizadores do site, no qual todos os membros têm o **nível de permissão** Leitura.</span><span class="sxs-lookup"><span data-stu-id="060ed-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
- <span data-ttu-id="060ed-204">A capacidade dos membros de convidar outros membros ou de não membros solicitarem acesso está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="060ed-204">The ability for members to invite other members or for non-members to request access is disabled.</span></span>

<span data-ttu-id="060ed-205">Esta é a configuração resultante com os três grupos do SharePoint para o site configurados para usar os três grupos de acesso, que são preenchidos com contas de usuário ou grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="060ed-205">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>

![A configuração final do site isolado do SharePoint Online com grupos de acesso e contas de usuário.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

<span data-ttu-id="060ed-207">Você e os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar usando os recursos do site.</span><span class="sxs-lookup"><span data-stu-id="060ed-207">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>

## <a name="next-step"></a><span data-ttu-id="060ed-208">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="060ed-208">Next step</span></span>

<span data-ttu-id="060ed-209">Quando precisar alterar a associação do grupo de acesso ao site ou criar uma pasta de documentos com permissões personalizadas, confira Gerenciar um site de equipe do [SharePoint Online isolado.](manage-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="060ed-209">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="060ed-210">Confira também</span><span class="sxs-lookup"><span data-stu-id="060ed-210">See Also</span></span>

[<span data-ttu-id="060ed-211">Sites de equipe do SharePoint Online isolados</span><span class="sxs-lookup"><span data-stu-id="060ed-211">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="060ed-212">Projetar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="060ed-212">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="060ed-213">Gerenciar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="060ed-213">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
