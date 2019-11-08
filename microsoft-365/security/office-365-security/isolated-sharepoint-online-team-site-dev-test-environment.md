---
title: Site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Resumo: Configure um site de equipe do SharePoint Online isolado do restante da organização no seu ambiente de desenvolvimento/teste do Office 365.'
ms.openlocfilehash: 0f91bcce140fd1ad00c51b27e8b1e134e5f2a283
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032336"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="f19ae-103">Site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste</span><span class="sxs-lookup"><span data-stu-id="f19ae-103">Isolated SharePoint Online team site dev/test environment</span></span>

 <span data-ttu-id="f19ae-104">**Resumo:** Configure um site de equipe do SharePoint Online isolado do restante da organização no seu ambiente de desenvolvimento/teste do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f19ae-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Office 365 dev/test environment.</span></span>
  
<span data-ttu-id="f19ae-105">Os sites de equipe do SharePoint Online no Office 365 são locais para colaboração usando uma biblioteca de documentos comum, um bloco de anotações do OneNote e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="f19ae-105">SharePoint Online team sites in Office 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="f19ae-106">Em muitos casos, convém ter acesso e colaboração amplos entre departamentos ou organizações.</span><span class="sxs-lookup"><span data-stu-id="f19ae-106">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="f19ae-107">No entanto, em alguns casos, você deseja controlar rigidamente o acesso e as permissões para colaboração entre um pequeno grupo de pessoas.</span><span class="sxs-lookup"><span data-stu-id="f19ae-107">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>
  
<span data-ttu-id="f19ae-108">Acesso aos sites de equipe do SharePoint Online e o que os usuários podem fazer são controlados pelos grupos do SharePoint e níveis de permissão.</span><span class="sxs-lookup"><span data-stu-id="f19ae-108">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="f19ae-109">Por padrão, os sites do SharePoint Online têm três níveis de acesso:</span><span class="sxs-lookup"><span data-stu-id="f19ae-109">By default, SharePoint Online sites have three levels of access:</span></span>
  
- <span data-ttu-id="f19ae-110">**Membros**, que podem exibir, criar e modificar recursos no site.</span><span class="sxs-lookup"><span data-stu-id="f19ae-110">**Members**, who can view, create, and modify resources on the site.</span></span>
    
- <span data-ttu-id="f19ae-111">**Proprietários**, que têm controle total do site, incluindo a capacidade de alterar permissões.</span><span class="sxs-lookup"><span data-stu-id="f19ae-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
    
- <span data-ttu-id="f19ae-112">**Visitantes**, que só podem exibir recursos no site.</span><span class="sxs-lookup"><span data-stu-id="f19ae-112">**Visitors**, who only can view resources on the site.</span></span>
    
<span data-ttu-id="f19ae-113">Este artigo orienta você pela configuração de um site de equipe do SharePoint Online isolado para um projeto de pesquisa secreto chamado projeto x.</span><span class="sxs-lookup"><span data-stu-id="f19ae-113">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="f19ae-114">Os requisitos de acesso são:</span><span class="sxs-lookup"><span data-stu-id="f19ae-114">The access requirements are:</span></span>
  
- <span data-ttu-id="f19ae-115">Somente os membros do projeto podem acessar o site e seu conteúdo (documentos, Bloco de Anotações do OneNote, Páginas), com níveis de permissão de edição e exibição do SharePoint controlados por meio de associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="f19ae-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>
    
- <span data-ttu-id="f19ae-116">Somente o criador do site e os membros de um grupo de Administradores do site podem executar a administração do site, a qual inclui modificação de permissões no nível do site.</span><span class="sxs-lookup"><span data-stu-id="f19ae-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>
    
<span data-ttu-id="f19ae-117">Há três fases para configurar um site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste do Office 365:</span><span class="sxs-lookup"><span data-stu-id="f19ae-117">There are three phases to setting up an isolated SharePoint Online team site in your Office 365 dev/test environment:</span></span>
  
1. <span data-ttu-id="f19ae-118">Criação do ambiente de desenvolvimento/teste do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f19ae-118">Create the Office 365 dev/test environment.</span></span>
    
2. <span data-ttu-id="f19ae-119">Criação de usuários e grupos para o Projeto X.</span><span class="sxs-lookup"><span data-stu-id="f19ae-119">Create the users and groups for ProjectX.</span></span>
    
3. <span data-ttu-id="f19ae-120">Criar um novo site de equipe do projeto x SharePoint Online e isolá-lo.</span><span class="sxs-lookup"><span data-stu-id="f19ae-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>
    
> [!TIP]
> <span data-ttu-id="f19ae-121">Clique [aqui](https://aka.ms/catlgstack) para exibir um mapa visual para todos os artigos da pilha da Guia do Laboratório de Teste do One Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="f19ae-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a><span data-ttu-id="f19ae-122">Fase 1: desenvolver seu ambiente de desenvolvimento/teste do Office 365 leve ou em uma empresa simulada</span><span class="sxs-lookup"><span data-stu-id="f19ae-122">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="f19ae-123">Se você só quiser criar um site de equipe isolado do SharePoint Online de forma leve com os requisitos mínimos, siga as instruções nas fases 2 e 3 do [ambiente de desenvolvimento/teste do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="f19ae-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="f19ae-124">Se você quiser criar um site de equipe do SharePoint Online isolado em uma configuração empresarial simulada, siga as instruções em [DirSync para seu ambiente de desenvolvimento/teste do Office 365](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="f19ae-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [DirSync for your Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f19ae-125">A criação de um site do SharePoint Online isolado não exige o ambiente de desenvolvimento/teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f19ae-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f19ae-126">Ele é fornecido aqui como uma opção para que você possa testar um site do SharePoint Online isolado e fazer testes com ele em um ambiente que representa uma organização comum.</span><span class="sxs-lookup"><span data-stu-id="f19ae-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="f19ae-127">Fase 2: criar contas de usuário e grupos de acesso</span><span class="sxs-lookup"><span data-stu-id="f19ae-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="f19ae-128">Use as instruções em [conectar-se ao office 365 PowerShell](https://technet.microsoft.com/library/dn975125.aspx) para se conectar à sua assinatura do Office 365 Trail com sua conta de administrador global em:</span><span class="sxs-lookup"><span data-stu-id="f19ae-128">Use the instructions in [Connect to Office 365 PowerShell](https://technet.microsoft.com/library/dn975125.aspx) to connect to your Office 365 trail subscription with your global administrator account from:</span></span>
  
- <span data-ttu-id="f19ae-129">Seu computador (para o ambiente leve de desenvolvimento/teste do Office 365).</span><span class="sxs-lookup"><span data-stu-id="f19ae-129">Your computer (for the lightweight Office 365 dev/test environment).</span></span>
    
- <span data-ttu-id="f19ae-130">A máquina virtual CLIENT1 (para o ambiente de desenvolvimento/teste corporativo simulado do Office 365).</span><span class="sxs-lookup"><span data-stu-id="f19ae-130">The CLIENT1 virtual machine (for the simulated enterprise Office 365 dev/test environment).</span></span>
    
<span data-ttu-id="f19ae-131">Para criar os novos grupos de acesso para o site de equipe do SharePoint Online do projeto x, execute esses comandos no prompt do módulo do Active Directory do Windows Azure para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f19ae-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

> [!TIP]
> <span data-ttu-id="f19ae-132">Clique [aqui](https://gallery.technet.microsoft.com/PowerShell-commands-for-an-b2608df1) para obter um arquivo de texto que contém todos os comandos do PowerShell deste artigo.</span><span class="sxs-lookup"><span data-stu-id="f19ae-132">Click [here](https://gallery.technet.microsoft.com/PowerShell-commands-for-an-b2608df1) for a text file that contains all of the PowerShell commands in this article.</span></span>
  
<span data-ttu-id="f19ae-133">Preencha o nome de sua organização (exemplo: contosotoycompany), o código de país com dois caracteres de seu local e execute os seguintes comandos no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f19ae-133">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="f19ae-134">Na exibição do comando **New-MsolUser**, anote a senha gerada para a conta de Designer Chefe e grave-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="f19ae-134">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>
  
<span data-ttu-id="f19ae-135">Execute os seguintes comandos no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f19ae-135">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="f19ae-136">Na exibição do comando **New-MsolUser**, anote a senha gerada para a conta de Pesquisador Chefe e grave-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="f19ae-136">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>
  
<span data-ttu-id="f19ae-137">Execute os seguintes comandos no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f19ae-137">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="f19ae-138">Na exibição do comando **New-MsolUser**, anote a senha gerada para a conta de VP de Desenvolvimento e grave-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="f19ae-138">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>
  
<span data-ttu-id="f19ae-139">Em seguida, para adicionar as novas contas aos novos grupos de acesso, execute estes comandos do PowerShell no prompt do módulo do Active Directory do Windows Azure para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f19ae-139">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="f19ae-140">Resultados</span><span class="sxs-lookup"><span data-stu-id="f19ae-140">Results:</span></span>
  
- <span data-ttu-id="f19ae-141">O grupo de acesso projeto x-Members contém as contas de usuário designer de líder e pesquisadora líder</span><span class="sxs-lookup"><span data-stu-id="f19ae-141">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>
    
- <span data-ttu-id="f19ae-142">O grupo de acesso projeto x-admins contém a conta de administrador global para sua assinatura de avaliação</span><span class="sxs-lookup"><span data-stu-id="f19ae-142">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>
    
- <span data-ttu-id="f19ae-143">O grupo de acesso projeto x-visualizadores contém a conta de usuário VP de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="f19ae-143">The ProjectX-Viewers access group contains the Development VP user account</span></span>
    
<span data-ttu-id="f19ae-144">A Figura 1 mostra os grupos de acesso e sua associação.</span><span class="sxs-lookup"><span data-stu-id="f19ae-144">Figure 1 shows the access groups and their membership.</span></span>
  
<span data-ttu-id="f19ae-145">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="f19ae-145">**Figure 1**</span></span>

![Os grupos do Office 365 e seus membros para um site de grupo do SharePoint Online isolado](../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)
  
## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="f19ae-147">Fase 3: criar um novo site de equipe do projeto x SharePoint Online e isolá-lo</span><span class="sxs-lookup"><span data-stu-id="f19ae-147">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="f19ae-148">Para criar um site de equipe do SharePoint Online para o projeto x, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f19ae-148">To create a SharePoint Online team site for ProjectX, do the following:</span></span>
  
1. <span data-ttu-id="f19ae-149">Usando um navegador no computador local (configuração leve) ou em CLIENT1 (configuração corporativa simulada), entre no portal do Office 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="f19ae-149">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="f19ae-150">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-150">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="f19ae-151">Na nova guia do SharePoint em seu navegador, clique em **Criar site**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-151">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="f19ae-152">Em **Nome do site de equipe**, digite **Projeto X**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-152">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="f19ae-153">Em **configurações de privacidade**, selecione **membros somente privados podem acessar este site**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-153">In **Privacy settings**, select **Private - only members can access this site**.</span></span>
    
5. <span data-ttu-id="f19ae-154">Em **Descrição do site de equipe**, digite **Site do SharePoint para o Projeto X** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-154">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="f19ae-155">No painel **Quem você quer adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-155">On the **Who do you want to add**? pane, click **Finish**.</span></span>
    
7. <span data-ttu-id="f19ae-156">Na nova guia **Projeto X-Página Inicial** em seu navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-156">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
8. <span data-ttu-id="f19ae-157">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-157">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
9. <span data-ttu-id="f19ae-158">Na nova guia **Permissões: Projeto X** em seu navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-158">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>
    
10. <span data-ttu-id="f19ae-159">Na caixa de diálogo **Configurações de Solicitações de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir solicitações de acesso** (para que todas as três caixas de seleção sejam desmarcadas) e, depois, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-159">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
11. <span data-ttu-id="f19ae-160">Clique em **Membros do Projeto X** na lista.</span><span class="sxs-lookup"><span data-stu-id="f19ae-160">Click **ProjectX Members** in the list.</span></span>
    
12. <span data-ttu-id="f19ae-161">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-161">On the **People and Groups** page, click **New**.</span></span>
    
13. <span data-ttu-id="f19ae-162">Na caixa de diálogo **Compartilhar**, digite **Projeto X-Membros**, selecione-o e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-162">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="f19ae-163">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="f19ae-163">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="f19ae-164">Clique em **Proprietários do Projeto X** na lista.</span><span class="sxs-lookup"><span data-stu-id="f19ae-164">Click **ProjectX Owners** in the list.</span></span>
    
16. <span data-ttu-id="f19ae-165">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-165">On the **People and Groups** page, click **New**.</span></span>
    
17. <span data-ttu-id="f19ae-166">Na caixa de diálogo **Compartilhar**, digite **Projeto X-Administradores**, selecione-o e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-166">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="f19ae-167">Clique no botão voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="f19ae-167">Click the back button on your browser.</span></span>
    
19. <span data-ttu-id="f19ae-168">Clique em **Visitantes do Projeto X** na lista.</span><span class="sxs-lookup"><span data-stu-id="f19ae-168">Click **ProjectX Visitors** in the list.</span></span>
    
20. <span data-ttu-id="f19ae-169">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-169">On the **People and Groups** page, click **New**.</span></span>
    
21. <span data-ttu-id="f19ae-170">Na caixa de diálogo **Compartilhar**, digite **Projeto X-Visualizadores**, selecione-o e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-170">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>
    
22. <span data-ttu-id="f19ae-171">Feche a guia **Pessoas e Grupos** em seu navegador, clique na guia **Projeto X-Página Inicial** em seu navegador e feche o painel **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-171">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="f19ae-172">Estes são os resultados da configuração das permissões:</span><span class="sxs-lookup"><span data-stu-id="f19ae-172">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="f19ae-173">O grupo de membros do projeto x do SharePoint contém apenas o grupo de acesso projeto x-Members (que contém apenas as contas de usuário do designer de clientes e do pesquisador principal) e o grupo projeto x (que contém apenas a conta de usuário administrador global).</span><span class="sxs-lookup"><span data-stu-id="f19ae-173">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="f19ae-174">O grupo de proprietários do projeto x do SharePoint contém apenas o grupo de acesso projeto x-admins (que contém apenas a conta de usuário de administrador global).</span><span class="sxs-lookup"><span data-stu-id="f19ae-174">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="f19ae-175">O grupo visitantes do projeto x do SharePoint contém apenas o grupo de acesso projeto x-visualizadores (que contém apenas a conta de usuário VP de desenvolvimento).</span><span class="sxs-lookup"><span data-stu-id="f19ae-175">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>
    
- <span data-ttu-id="f19ae-176">Os membros não podem modificar as permissões no nível do site (isso só pode ser feito por membros do grupo Projeto X-Administradores).</span><span class="sxs-lookup"><span data-stu-id="f19ae-176">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>
    
- <span data-ttu-id="f19ae-177">Outras contas de usuário não podem acessar o site ou seus recursos ou solicitar acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="f19ae-177">Other user accounts cannot access the site or its resources or request access to the site.</span></span>
    
<span data-ttu-id="f19ae-178">A Figura 2 mostra os grupos do SharePoint e suas associações.</span><span class="sxs-lookup"><span data-stu-id="f19ae-178">Figure 2 shows the SharePoint groups and their membership.</span></span>
  
<span data-ttu-id="f19ae-179">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="f19ae-179">**Figure 2**</span></span>

![Os grupos do SharePoint Online e seus membros para um site de grupo do SharePoint Online isolado](../media/595abff4-64f9-49de-a37a-c70c6856936b.png)
  
<span data-ttu-id="f19ae-181">Agora, vamos demonstrar o acesso usando a conta de usuário do designer de cliente potencial:</span><span class="sxs-lookup"><span data-stu-id="f19ae-181">Now let's demonstrate access using the Lead Designer user account:</span></span>
  
1. <span data-ttu-id="f19ae-182">Feche a guia **Projeto X-Página Inicial** em seu navegador e clique na guia **Microsoft Office Home** em seu navegador.</span><span class="sxs-lookup"><span data-stu-id="f19ae-182">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>
    
2. <span data-ttu-id="f19ae-183">Clique no nome do administrador global e clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-183">Click the name of your global administrator, and then click **Sign out**.</span></span>
    
3. <span data-ttu-id="f19ae-184">Entre no portal do Office 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) usando o nome da conta do designer líder e sua senha.</span><span class="sxs-lookup"><span data-stu-id="f19ae-184">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Lead Designer account name and its password.</span></span>
    
4. <span data-ttu-id="f19ae-185">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-185">In the list of tiles, click **SharePoint**.</span></span>
    
5. <span data-ttu-id="f19ae-186">Na nova guia **SharePoint** no navegador, digite **projeto x** na caixa de pesquisa, ative a pesquisa e clique no site de equipe do **projeto x** .</span><span class="sxs-lookup"><span data-stu-id="f19ae-186">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="f19ae-187">Você deve ver uma nova guia no navegador para o site de equipe do projeto x.</span><span class="sxs-lookup"><span data-stu-id="f19ae-187">You should see a new tab in your browser for the ProjectX team site.</span></span>
    
6. <span data-ttu-id="f19ae-p107">Clique no ícone de configurações. Observe que não há opção para **Permissões de Site**. Isso está correto, pois somente os membros do grupo Projeto X-Administradores podem modificar as permissões no site</span><span class="sxs-lookup"><span data-stu-id="f19ae-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>
    
7. <span data-ttu-id="f19ae-191">Abra o bloco de notas ou um editor de texto de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="f19ae-191">Open Notepad or a text editor of your choice.</span></span>
    
8. <span data-ttu-id="f19ae-192">Copie a URL do site de equipe do projeto x e cole-a em uma nova linha no bloco de notas ou em seu editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f19ae-192">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>
    
9. <span data-ttu-id="f19ae-193">Na nova guia **Projeto X-Página Inicial** em seu navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-193">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>
    
10. <span data-ttu-id="f19ae-194">Copie a URL da pasta de documentos do Projeto X e cole-a em uma nova linha no Bloco de Notas ou em seu editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f19ae-194">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>
    
11. <span data-ttu-id="f19ae-195">Na nova guia **Projeto X-Documentos** em seu navegador, clique em **Novo > Documento do Word**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-195">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>
    
12. <span data-ttu-id="f19ae-196">Digite algum texto na página, espere o status indicar que foi **salvo**, clique no botão voltar do navegador e atualize a página.</span><span class="sxs-lookup"><span data-stu-id="f19ae-196">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="f19ae-197">Você deverá ver um novo **Document.docx** na pasta **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-197">You should see a new **Document.docx** in the **Documents** folder.</span></span>
    
13. <span data-ttu-id="f19ae-198">Clique nas reticências do documento **Document.docx** e clique em **Obter um link**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-198">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>
    
14. <span data-ttu-id="f19ae-199">Copie a URL na caixa de diálogo **compartilhar ' Document. docx '** e cole-a em uma nova linha no bloco de notas ou em seu editor de texto e, em seguida, feche a caixa de diálogo **compartilhar ' Document. docx '** .</span><span class="sxs-lookup"><span data-stu-id="f19ae-199">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>
    
15. <span data-ttu-id="f19ae-200">Feche as guias **Projeto X-Documentos** e **SharePoint** em seu navegador e clique na guia **Microsoft Office Home**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-200">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>
    
16. <span data-ttu-id="f19ae-201">Clique no nome **Designer Chefe** e clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-201">Click the **Lead Designer** name, and then click **Sign out**.</span></span>
    
<span data-ttu-id="f19ae-202">Agora, vamos demonstrar o acesso usando a conta de usuário do VP de desenvolvimento:</span><span class="sxs-lookup"><span data-stu-id="f19ae-202">Now let's demonstrate access using the Development VP user account:</span></span>
  
1. <span data-ttu-id="f19ae-203">Entre no portal do Office 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) usando o nome da conta de VP de desenvolvimento e sua senha.</span><span class="sxs-lookup"><span data-stu-id="f19ae-203">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Development VP account name and its password.</span></span>
    
2. <span data-ttu-id="f19ae-204">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-204">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="f19ae-205">Na nova guia **SharePoint** no navegador, digite **projeto x** na caixa de pesquisa, ative a pesquisa e clique no site de equipe do **projeto x** .</span><span class="sxs-lookup"><span data-stu-id="f19ae-205">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="f19ae-206">Você deve ver uma nova guia no navegador para o site de equipe do projeto x.</span><span class="sxs-lookup"><span data-stu-id="f19ae-206">You should see a new tab in your browser for the ProjectX team site.</span></span>
    
4. <span data-ttu-id="f19ae-207">Clique em **Documentos** e clique no arquivo **Document.docx**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-207">Click **Documents**, and then click the **Document.docx** file.</span></span>
    
5. <span data-ttu-id="f19ae-p110">Na guia **Document.docx** em seu navegador, tente modificar o texto. Você deve ver uma mensagem informando que **Este documento é somente leitura.** Isso é esperado, pois a conta de usuário de VP de Desenvolvimento só tem permissões de exibição no site.</span><span class="sxs-lookup"><span data-stu-id="f19ae-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>
    
6. <span data-ttu-id="f19ae-211">Feche as guias **Document.docx**, **Projeto X-Documentos** e **SharePoint** em seu navegador.</span><span class="sxs-lookup"><span data-stu-id="f19ae-211">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>
    
7. <span data-ttu-id="f19ae-212">Clique na guia **Microsoft Office Home**, clique no nome **VP de Desenvolvimento** e clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-212">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>
    
<span data-ttu-id="f19ae-213">Agora vamos demonstrar o acesso a uma conta de usuário que não tem permissões:</span><span class="sxs-lookup"><span data-stu-id="f19ae-213">Now let's demonstrate access with a user account that has no permissions:</span></span>
  
1. <span data-ttu-id="f19ae-214">Entre no portal do Office 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) usando o nome da conta do usuário 3 e sua senha.</span><span class="sxs-lookup"><span data-stu-id="f19ae-214">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the User 3 account name and its password.</span></span>
    
2. <span data-ttu-id="f19ae-215">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-215">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="f19ae-p111">	Na nova guia *\*SharePoint** em seu navegador, digite *\*Projeto X** na caixa de pesquisa e ative a pesquisa. Você deverá ver a mensagem *\*Não houve resultados para sua pesquisa.**</span><span class="sxs-lookup"><span data-stu-id="f19ae-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>
    
4. <span data-ttu-id="f19ae-p112">Na instância aberta do Bloco de Notas ou de seu editor de texto, copie a URL do site do Projeto X na barra de endereços de seu navegador e pressione **Enter**. Você deverá ver uma página **Acesso Negado**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>
    
5. <span data-ttu-id="f19ae-p113">No Bloco de Notas ou seu editor de texto, copie a URL da pasta Documentos do Projeto X e cole-a na barra de endereços de seu navegador e pressione **Enter**. Você deverá ver uma página **Acesso Negado**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>
    
6. <span data-ttu-id="f19ae-p114">No Bloco de Notas ou seu editor de texto, copie a URL do arquivo Documents.docx na barra de endereços de seu navegador e pressione **Enter**. Você deverá ver uma página **Acesso Negado**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>
    
7. <span data-ttu-id="f19ae-224">Feche a guia **SharePoint** em seu navegador, clique na guia **Microsoft Office Home**, clique no nome **Usuário 3** e clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="f19ae-224">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>
    
<span data-ttu-id="f19ae-225">Seu site do SharePoint Online isolado agora está pronto para sua experimentação adicional.</span><span class="sxs-lookup"><span data-stu-id="f19ae-225">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="f19ae-226">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f19ae-226">Next Step</span></span>

<span data-ttu-id="f19ae-227">Quando estiver pronto para implantar um site de equipe do SharePoint Online isolado na produção, confira as considerações de design passo a passo no [Projetar um site de equipe do SharePoint Online isolado](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="f19ae-227">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f19ae-228">Confira também</span><span class="sxs-lookup"><span data-stu-id="f19ae-228">See Also</span></span>

[<span data-ttu-id="f19ae-229">Sites de equipe do SharePoint Online isolados</span><span class="sxs-lookup"><span data-stu-id="f19ae-229">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="f19ae-230">Guias do Laboratório de Teste (TLGs) para adoção de nuvem</span><span class="sxs-lookup"><span data-stu-id="f19ae-230">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
<span data-ttu-id="f19ae-231">[O ambiente de desenvolvimento/teste de configuração base](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment) </span><span class="sxs-lookup"><span data-stu-id="f19ae-231">[Base Configuration dev/test environment](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)</span></span>
  
[<span data-ttu-id="f19ae-232">Ambiente de desenvolvimento/teste do Office 365</span><span class="sxs-lookup"><span data-stu-id="f19ae-232">Office 365 dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)
  
[<span data-ttu-id="f19ae-233">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="f19ae-233">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




