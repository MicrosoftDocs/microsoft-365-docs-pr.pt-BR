---
title: Site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste
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
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Resumo: Configure um site de equipe do SharePoint Online isolado do restante da organização em seu ambiente de teste/dev do Microsoft 365.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286604"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="a3ac6-103">Site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste</span><span class="sxs-lookup"><span data-stu-id="a3ac6-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a3ac6-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a3ac6-104">**Applies to**</span></span>
- [<span data-ttu-id="a3ac6-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a3ac6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a3ac6-106">Microsoft Defender para Office 365 plano 1</span><span class="sxs-lookup"><span data-stu-id="a3ac6-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="a3ac6-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3ac6-107">SharePoint Online</span></span> 


 <span data-ttu-id="a3ac6-108">**Resumo:** Configure um site de equipe do SharePoint Online isolado do restante da organização no ambiente de teste/desv do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-108">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="a3ac6-109">Os sites de equipe do SharePoint Online no Microsoft 365 são locais para colaboração usando uma biblioteca de documentos comum, um bloco de anotações do OneNote e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-109">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="a3ac6-110">Em muitos casos, convém ter acesso e colaboração amplos entre departamentos ou organizações.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-110">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="a3ac6-111">No entanto, em alguns casos, você deseja controlar fortemente o acesso e as permissões para colaboração entre um pequeno grupo de pessoas.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-111">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="a3ac6-112">O acesso aos sites de equipe do SharePoint Online e o que os usuários podem fazer é controlado por grupos e níveis de permissão do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-112">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="a3ac6-113">Por padrão, os sites do SharePoint Online têm três níveis de acesso:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-113">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="a3ac6-114">**Membros**, que podem exibir, criar e modificar recursos no site.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-114">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="a3ac6-115">**Proprietários**, que têm controle total do site, incluindo a capacidade de alterar permissões.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-115">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="a3ac6-116">**Visitantes**, que só podem exibir recursos no site.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-116">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="a3ac6-117">Este artigo explica a configuração de um site de equipe isolado do SharePoint Online para um projeto de pesquisa secreto chamado ProjectX.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-117">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="a3ac6-118">Os requisitos de acesso são:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-118">The access requirements are:</span></span>

- <span data-ttu-id="a3ac6-119">Somente os membros do projeto podem acessar o site e seu conteúdo (documentos, Bloco de Anotações do OneNote, Páginas), com níveis de permissão de edição e exibição do SharePoint controlados por meio de associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-119">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="a3ac6-120">Somente o criador do site e os membros de um grupo de Administradores do site podem executar a administração do site, a qual inclui modificação de permissões no nível do site.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-120">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="a3ac6-121">Há três fases para configurar um site de equipe isolado do SharePoint Online em seu ambiente de desenvolvimento/teste do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-121">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="a3ac6-122">Crie o ambiente de teste/desv do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-122">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="a3ac6-123">Criação de usuários e grupos para o Projeto X.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-123">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="a3ac6-124">Crie um novo site de equipe do SharePoint Online projectX e o isole.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-124">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="a3ac6-125">Clique [aqui](https://aka.ms/catlgstack) para ver um mapa visual para todos os artigos da pilha do Guia do Laboratório de Teste do One Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-125">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="a3ac6-126">Fase 1: Criar seu ambiente de desenvolvimento/teste leve ou simulado do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3ac6-126">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="a3ac6-127">Se você quiser apenas criar um site de equipe do SharePoint Online isolado de maneira leve com os requisitos mínimos, siga as instruções nas fases 2 e 3 da configuração [de base leve.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="a3ac6-127">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="a3ac6-128">Se você quiser criar um site de equipe do SharePoint Online isolado em uma configuração corporativa simulada, siga as instruções na sincronização de hash de senha para seu ambiente de teste do [Microsoft 365.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a3ac6-128">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](../../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3ac6-129">Criar um site isolado do SharePoint Online não exige o ambiente de teste/dev corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="a3ac6-129">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a3ac6-130">Ele é fornecido aqui como uma opção para que você possa testar um site do SharePoint Online isolado e fazer testes com ele em um ambiente que representa uma organização comum.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-130">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="a3ac6-131">Fase 2: Criar contas de usuário e grupos de acesso</span><span class="sxs-lookup"><span data-stu-id="a3ac6-131">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="a3ac6-132">Use as instruções em [Conectar-se ao Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) para se conectar à sua assinatura de avaliação com sua conta de administrador global de:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-132">Use the instructions in [Connect to Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="a3ac6-133">Seu computador (para o leve ambiente de dev/teste do Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="a3ac6-133">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="a3ac6-134">A máquina virtual CLIENT1 (para o ambiente dev/teste corporativo simulado do Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="a3ac6-134">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="a3ac6-135">Para criar os novos grupos de acesso para o site de equipe do SharePoint Online do ProjectX, execute estes comandos no prompt do Módulo Do Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-135">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
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

<span data-ttu-id="a3ac6-136">Preencha o nome de sua organização (exemplo: contosotoycompany), o código de país com dois caracteres de seu local e execute os seguintes comandos no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-136">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="a3ac6-137">Na exibição do comando **New-MsolUser**, anote a senha gerada para a conta de Designer Chefe e grave-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-137">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="a3ac6-138">Execute os seguintes comandos no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-138">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="a3ac6-139">Na exibição do comando **New-MsolUser**, anote a senha gerada para a conta de Pesquisador Chefe e grave-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-139">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="a3ac6-140">Execute os seguintes comandos no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-140">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="a3ac6-141">Na exibição do comando **New-MsolUser**, anote a senha gerada para a conta de VP de Desenvolvimento e grave-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-141">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="a3ac6-142">Em seguida, para adicionar as novas contas aos novos grupos de acesso, execute estes comandos do PowerShell no prompt do Módulo Do Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-142">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
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

<span data-ttu-id="a3ac6-143">Resultados:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-143">Results:</span></span>

- <span data-ttu-id="a3ac6-144">O ProjectX-Members grupo de acesso de grupo contém as contas de usuário Designer Chefe e Pesquisador Chefe</span><span class="sxs-lookup"><span data-stu-id="a3ac6-144">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="a3ac6-145">O ProjectX-Admins grupo de acesso contém a conta de administrador global da sua assinatura de avaliação</span><span class="sxs-lookup"><span data-stu-id="a3ac6-145">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="a3ac6-146">O ProjectX-Viewers grupo de acesso de grupo contém a conta de usuário vp de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="a3ac6-146">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="a3ac6-147">A Figura 1 mostra os grupos de acesso e sua associação.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-147">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="a3ac6-148">**Figura 1:**</span><span class="sxs-lookup"><span data-stu-id="a3ac6-148">**Figure 1**:</span></span>

![Os grupos do Microsoft 365 e sua associação a um site de grupo do SharePoint Online isolado](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="a3ac6-150">Fase 3: Criar um novo site de equipe do SharePoint Online projectX e isolá-lo</span><span class="sxs-lookup"><span data-stu-id="a3ac6-150">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="a3ac6-151">Para criar um site de equipe do SharePoint Online para o ProjectX, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-151">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="a3ac6-152">Usando um navegador no computador local (configuração leve) ou no CLIENT1 (configuração corporativa simulada), entre no Centro de administração do Microsoft 365 usando sua conta de administrador <https://admin.microsoft.com> global.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-152">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="a3ac6-153">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-153">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="a3ac6-154">Na nova guia do SharePoint em seu navegador, clique em **Criar site**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-154">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="a3ac6-155">Em **Nome do site de equipe**, digite **Projeto X**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-155">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="a3ac6-156">Em **Configurações de privacidade**, selecione Privado - somente membros podem acessar este **site**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-156">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="a3ac6-157">Em **Descrição do site de equipe**, digite **Site do SharePoint para o Projeto X** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-157">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="a3ac6-158">No painel **Quem você quer adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-158">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="a3ac6-159">Na nova guia **Projeto X-Página Inicial** em seu navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-159">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="a3ac6-160">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-160">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="a3ac6-161">Na nova guia **Permissões: Projeto X** em seu navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-161">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="a3ac6-162">Na caixa de diálogo **Configurações de Solicitações de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir solicitações de acesso** (para que todas as três caixas de seleção sejam desmarcadas) e, depois, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-162">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="a3ac6-163">Clique em **Membros do Projeto X** na lista.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-163">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="a3ac6-164">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-164">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="a3ac6-165">Na caixa de diálogo **Compartilhar**, digite **Projeto X-Membros**, selecione-o e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-165">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="a3ac6-166">Clique no botão voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-166">Click the back button on your browser.</span></span>

15. <span data-ttu-id="a3ac6-167">Clique em **Proprietários do Projeto X** na lista.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-167">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="a3ac6-168">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-168">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="a3ac6-169">Na caixa de diálogo **Compartilhar**, digite **Projeto X-Administradores**, selecione-o e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-169">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="a3ac6-170">Clique no botão voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-170">Click the back button on your browser.</span></span>

19. <span data-ttu-id="a3ac6-171">Clique em **Visitantes do Projeto X** na lista.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-171">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="a3ac6-172">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-172">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="a3ac6-173">Na caixa de diálogo **Compartilhar**, digite **Projeto X-Visualizadores**, selecione-o e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-173">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="a3ac6-174">Feche a guia **Pessoas e Grupos** em seu navegador, clique na guia **Projeto X-Página Inicial** em seu navegador e feche o painel **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-174">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="a3ac6-175">Estes são os resultados da configuração das permissões:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-175">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="a3ac6-176">O grupo membros do ProjectX do SharePoint contém apenas o grupo de acesso ProjectX-Members (que contém apenas as contas de usuário Designer Chefe e Pesquisador Chefe) e o grupo ProjectX (que contém apenas a conta de usuário de administrador global).</span><span class="sxs-lookup"><span data-stu-id="a3ac6-176">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="a3ac6-177">O grupo do SharePoint de proprietários do ProjectX contém apenas o grupo ProjectX-Admins de acesso (que contém apenas a conta de usuário de administrador global).</span><span class="sxs-lookup"><span data-stu-id="a3ac6-177">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="a3ac6-178">O grupo do SharePoint de Visitantes do ProjectX contém apenas o grupo ProjectX-Viewers de acesso (que contém apenas a conta de usuário vp de desenvolvimento).</span><span class="sxs-lookup"><span data-stu-id="a3ac6-178">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="a3ac6-179">Os membros não podem modificar as permissões no nível do site (isso só pode ser feito por membros do grupo Projeto X-Administradores).</span><span class="sxs-lookup"><span data-stu-id="a3ac6-179">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="a3ac6-180">Outras contas de usuário não podem acessar o site ou seus recursos ou solicitar acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-180">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="a3ac6-181">A Figura 2 mostra os grupos do SharePoint e suas associações.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-181">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="a3ac6-182">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="a3ac6-182">**Figure 2**</span></span>

![Os grupos do SharePoint Online e sua associação a um site de grupo do SharePoint Online isolado](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="a3ac6-184">Agora vamos demonstrar o acesso usando a conta de usuário do Designer Chefe:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-184">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="a3ac6-185">Feche a guia **Projeto X-Página Inicial** em seu navegador e clique na guia **Microsoft Office Home** em seu navegador.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-185">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="a3ac6-186">Clique no nome do administrador global e clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-186">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="a3ac6-187">Entre no centro de administração do Microsoft 365 usando o nome da conta <https://admin.microsoft.com> do Designer Chefe e sua senha.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-187">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="a3ac6-188">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-188">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="a3ac6-189">Na nova guia **do SharePoint** no navegador, digite **Projeto X** na caixa de pesquisa, ative a pesquisa e clique no site de equipe **do ProjectX.**</span><span class="sxs-lookup"><span data-stu-id="a3ac6-189">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="a3ac6-190">Você verá uma nova guia no navegador para o site de equipe do ProjectX.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-190">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="a3ac6-p107">Clique no ícone de configurações. Observe que não há opção para **Permissões de Site**. Isso está correto, pois somente os membros do grupo Projeto X-Administradores podem modificar as permissões no site</span><span class="sxs-lookup"><span data-stu-id="a3ac6-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="a3ac6-194">Abra o bloco de notas ou um editor de texto de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-194">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="a3ac6-195">Copie a URL do site de equipe do ProjectX e a colar em uma nova linha no Bloco de Notas ou no editor de texto.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-195">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="a3ac6-196">Na nova guia **Projeto X-Página Inicial** em seu navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-196">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="a3ac6-197">Copie a URL da pasta de documentos do Projeto X e cole-a em uma nova linha no Bloco de Notas ou em seu editor de texto.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-197">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="a3ac6-198">Na nova guia **Projeto X-Documentos** em seu navegador, clique em **Novo > Documento do Word**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-198">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="a3ac6-199">Digite algum texto na página, aguarde até que o status indique **Salvo,** clique no botão Voltar no navegador e atualize a página.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-199">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="a3ac6-200">Você deverá ver um novo **Document.docx** na pasta **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-200">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="a3ac6-201">Clique nas reticências do documento **Document.docx** e clique em **Obter um link**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-201">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="a3ac6-202">Copie a URL na caixa de diálogo **Compartilhar "Document.docx"** e a copie em uma nova linha no Bloco de Notas ou no editor de texto e feche a caixa de diálogo **Compartilhar 'Document.docx'.**</span><span class="sxs-lookup"><span data-stu-id="a3ac6-202">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="a3ac6-203">Feche as guias **Projeto X-Documentos** e **SharePoint** em seu navegador e clique na guia **Microsoft Office Home**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-203">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="a3ac6-204">Clique no nome **Designer Chefe** e clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-204">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="a3ac6-205">Agora vamos demonstrar o acesso usando a conta de usuário vp de desenvolvimento:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-205">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="a3ac6-206">Entre no Centro de administração do Microsoft 365 usando o nome da conta <https://admin.microsoft.com> vp de desenvolvimento e sua senha.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-206">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="a3ac6-207">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-207">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="a3ac6-208">Na nova guia **do SharePoint** no navegador, digite **Projeto X** na caixa de pesquisa, ative a pesquisa e clique no site de equipe **do ProjectX.**</span><span class="sxs-lookup"><span data-stu-id="a3ac6-208">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="a3ac6-209">Você verá uma nova guia em seu navegador para o site de equipe do ProjectX.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-209">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="a3ac6-210">Clique em **Documentos** e clique no arquivo **Document.docx**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-210">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="a3ac6-p110">Na guia **Document.docx** em seu navegador, tente modificar o texto. Você deve ver uma mensagem informando que **Este documento é somente leitura.** Isso é esperado, pois a conta de usuário de VP de Desenvolvimento só tem permissões de exibição no site.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="a3ac6-214">Feche as guias **Document.docx**, **Projeto X-Documentos** e **SharePoint** em seu navegador.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-214">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="a3ac6-215">Clique na guia **Microsoft Office Home**, clique no nome **VP de Desenvolvimento** e clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-215">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="a3ac6-216">Agora vamos demonstrar o acesso com uma conta de usuário que não tem permissões:</span><span class="sxs-lookup"><span data-stu-id="a3ac6-216">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="a3ac6-217">Entre no Centro de administração do Microsoft 365 usando o nome da conta <https://admin.microsoft.com> do Usuário 3 e sua senha.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-217">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="a3ac6-218">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-218">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="a3ac6-p111">	Na nova guia *\*SharePoint** em seu navegador, digite *\*Projeto X** na caixa de pesquisa e ative a pesquisa. Você deverá ver a mensagem *\*Não houve resultados para sua pesquisa.**</span><span class="sxs-lookup"><span data-stu-id="a3ac6-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="a3ac6-p112">Na instância aberta do Bloco de Notas ou de seu editor de texto, copie a URL do site do Projeto X na barra de endereços de seu navegador e pressione **Enter**. Você deverá ver uma página **Acesso Negado**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="a3ac6-p113">No Bloco de Notas ou seu editor de texto, copie a URL da pasta Documentos do Projeto X e cole-a na barra de endereços de seu navegador e pressione **Enter**. Você deverá ver uma página **Acesso Negado**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="a3ac6-p114">No Bloco de Notas ou seu editor de texto, copie a URL do arquivo Documents.docx na barra de endereços de seu navegador e pressione **Enter**. Você deverá ver uma página **Acesso Negado**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="a3ac6-227">Feche a guia **SharePoint** em seu navegador, clique na guia **Microsoft Office Home**, clique no nome **Usuário 3** e clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-227">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="a3ac6-228">Seu site isolado do SharePoint Online agora está pronto para sua experimentação adicional.</span><span class="sxs-lookup"><span data-stu-id="a3ac6-228">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="a3ac6-229">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a3ac6-229">Next Step</span></span>

<span data-ttu-id="a3ac6-230">Quando estiver pronto para implantar um site de equipe do SharePoint Online isolado na produção, confira as considerações de design passo a passo no [Projetar um site de equipe do SharePoint Online isolado](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="a3ac6-230">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a3ac6-231">Confira também</span><span class="sxs-lookup"><span data-stu-id="a3ac6-231">See Also</span></span>

[<span data-ttu-id="a3ac6-232">Sites de equipe do SharePoint Online isolados</span><span class="sxs-lookup"><span data-stu-id="a3ac6-232">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="a3ac6-233">Guias do Laboratório de Teste (TLGs) para adoção de nuvem</span><span class="sxs-lookup"><span data-stu-id="a3ac6-233">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="a3ac6-234">A configuração base de empresa simulada</span><span class="sxs-lookup"><span data-stu-id="a3ac6-234">The simulated enterprise base configuration</span></span>](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="a3ac6-235">A configuração de base leve</span><span class="sxs-lookup"><span data-stu-id="a3ac6-235">The lightweight base configuration</span></span>](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="a3ac6-236">Centro de soluções e arquitetura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3ac6-236">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)