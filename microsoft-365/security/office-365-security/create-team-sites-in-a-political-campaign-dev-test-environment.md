---
title: Criar sites de equipe - Ambiente de desenvolvimento de campanha política
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Resumo: crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste de campanha política.'
ms.openlocfilehash: d6fe2067e51e47fed4bd90e1a1fa6c898034a6d7
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561190"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="592db-103">Criar sites de equipe em um ambiente de desenvolvimento/teste de campanha política</span><span class="sxs-lookup"><span data-stu-id="592db-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="592db-104">**Resumo:** crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste de campanha política.</span><span class="sxs-lookup"><span data-stu-id="592db-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
  
<span data-ttu-id="592db-p101">Use as instruções deste artigo para criar um ambiente de desenvolvimento/teste com quatro diferentes tipos de sites de equipe do SharePoint Online para a solução de [Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Esses sites são descritos em detalhes no tópico 10, intitulado **SharePoint e OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="592db-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="592db-107">Fase 1: Criar seu ambiente de desenvolvimento/teste de campanha política</span><span class="sxs-lookup"><span data-stu-id="592db-107">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="592db-108">Primeiro, siga as instruções em [Configurar grupos e usuários para um ambiente de desenvolvimento/teste de campanha política](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) para criar assinaturas, usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="592db-108">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>
  
## <a name="phase-2-create-labels"></a><span data-ttu-id="592db-109">Fase 2: criar rótulos</span><span class="sxs-lookup"><span data-stu-id="592db-109">Phase 2: Create labels</span></span>

<span data-ttu-id="592db-110">Nesta fase, você deve criar os rótulos para os diferentes níveis de segurança para as pastas e documentos do site da equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="592db-110">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>
  
1. <span data-ttu-id="592db-111">Se necessário, entre no centro de administração com as credenciais da conta do administrador global da sua assinatura de avaliação.</span><span class="sxs-lookup"><span data-stu-id="592db-111">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="592db-112">Para obter ajuda, consulte [Como entrar no Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="592db-112">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="592db-113">Na guia **Microsoft Office Home**, clique no bloco **Administração**.</span><span class="sxs-lookup"><span data-stu-id="592db-113">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="592db-114">Na nova guia **Centro de Administração da Microsoft 365** do navegador, clique em **Centros de administração > Segurança e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="592db-114">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
    
4. <span data-ttu-id="592db-115">Na nova guia **Início – Segurança e Conformidade** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="592db-115">From the new **Home - Security & Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="592db-116">No painel **Início > Rótulos**, clique em **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="592db-116">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="592db-117">No painel **Atribuir nome ao seu rótulo**, digite **Interno** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-117">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="592db-118">No painel **Configurações do rótulo**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-118">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="592db-119">No painel **Examine as configurações**, clique em **Criar este rótulo** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="592db-119">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="592db-120">Repita as etapas de 5 a 8 para os rótulos adicionais:</span><span class="sxs-lookup"><span data-stu-id="592db-120">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="592db-121">Private</span><span class="sxs-lookup"><span data-stu-id="592db-121">Private</span></span>
    
  - <span data-ttu-id="592db-122">Confidencial</span><span class="sxs-lookup"><span data-stu-id="592db-122">Sensitive</span></span>
    
  - <span data-ttu-id="592db-123">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="592db-123">Highly Confidential</span></span>
    
10. <span data-ttu-id="592db-124">No painel **Início > Rótulos**, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="592db-124">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="592db-125">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="592db-125">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="592db-126">No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="592db-126">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="592db-127">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="592db-127">Click **Done**.</span></span>
    
14. <span data-ttu-id="592db-128">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-128">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="592db-129">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-129">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="592db-130">No painel **Nomear sua política**, digite **Campanha** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-130">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="592db-131">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="592db-131">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="592db-132">Fase 3: Criar seus sites de equipe do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="592db-132">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="592db-133">Nessa fase, você cria e configura sites de equipe do SharePoint Online para a campanha política correspondente aos quatro tipos de sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="592db-133">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>
  
### <a name="campaign-wide-team-site"></a><span data-ttu-id="592db-134">Site de equipe de toda a campanha</span><span class="sxs-lookup"><span data-stu-id="592db-134">Campaign wide team site</span></span>

<span data-ttu-id="592db-135">Para criar um site de equipe do SharePoint Online público de linha de base, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="592db-135">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="592db-136">Se necessário, use um navegador do seu computador local e entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="592db-136">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="592db-137">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="592db-137">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="592db-138">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="592db-138">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="592db-139">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="592db-139">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="592db-140">Em **Nome do site**, digite **Toda a campanha**.</span><span class="sxs-lookup"><span data-stu-id="592db-140">In **Site name**, type **Campaign wide**.</span></span> 
    
6. <span data-ttu-id="592db-141">Na **Descrição do site de equipe**, digite **Site do SharePoint para toda a campanha**.</span><span class="sxs-lookup"><span data-stu-id="592db-141">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>
    
7. <span data-ttu-id="592db-142">Em **Configurações de privacidade**, selecione **Público – qualquer pessoa na organização pode acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-142">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="592db-143">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="592db-143">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="592db-144">Em seguida, configure a pasta de documentos do site de equipe Toda a campanha com o rótulo Interno.</span><span class="sxs-lookup"><span data-stu-id="592db-144">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>
  
1. <span data-ttu-id="592db-145">Na guia **Toda a campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="592db-145">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="592db-146">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="592db-146">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="592db-147">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="592db-147">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="592db-148">Em **Configurações – Aplicar Rótulo**, selecione **Interno** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="592db-148">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>
    
### <a name="campaign-project-1-team-site"></a><span data-ttu-id="592db-149">Site de equipe 1 de projeto de campanha</span><span class="sxs-lookup"><span data-stu-id="592db-149">Campaign project 1 team site</span></span>

<span data-ttu-id="592db-150">Para criar um site de equipe do SharePoint Online privado de linha de base para um projeto dentro da campanha, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="592db-150">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>
  
1. <span data-ttu-id="592db-151">Se necessário, use um navegador do seu computador local e entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="592db-151">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="592db-152">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="592db-152">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="592db-153">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="592db-153">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="592db-154">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="592db-154">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="592db-155">Em **Nome do site**, digite **Projeto 1 da campanha**.</span><span class="sxs-lookup"><span data-stu-id="592db-155">In **Site name**, type **Campaign project 1**.</span></span> 
    
6. <span data-ttu-id="592db-156">Na **Descrição do site de equipe**, digite **Site do SharePoint para Projeto 1 de campanha**.</span><span class="sxs-lookup"><span data-stu-id="592db-156">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>
    
7. <span data-ttu-id="592db-157">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-157">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="592db-158">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="592db-158">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="592db-159">Em seguida, configure a pasta de documentos do site de equipe Projeto 1 de campanha com o rótulo Privado.</span><span class="sxs-lookup"><span data-stu-id="592db-159">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="592db-160">Na guia **Projeto 1 de campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="592db-160">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="592db-161">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="592db-161">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="592db-162">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="592db-162">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="592db-163">Em **Configurações – Aplicar Rótulo**, selecione **Privado** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="592db-163">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="campaign-marketing-team-site"></a><span data-ttu-id="592db-164">Site de equipe de marketing de campanha</span><span class="sxs-lookup"><span data-stu-id="592db-164">Campaign marketing team site</span></span>

<span data-ttu-id="592db-165">Para criar um site de equipe do SharePoint Online isolado de nível confidencial para recursos de marketing de campanha, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="592db-165">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>
  
1. <span data-ttu-id="592db-166">Usando um navegador no seu computador local, entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="592db-166">Using a browser on your local computer, sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="592db-167">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="592db-167">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="592db-168">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="592db-168">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="592db-169">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="592db-169">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="592db-170">Em **Nome do site de equipe**, digite **Marketing de campanha**.</span><span class="sxs-lookup"><span data-stu-id="592db-170">In **Team site name**, type **Campaign marketing**.</span></span>
    
6. <span data-ttu-id="592db-171">Em **Descrição do site de equipe**, digite **Site do SharePoint para marketing de campanha (confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="592db-171">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>
    
7.  <span data-ttu-id="592db-172">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-172">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="592db-173">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="592db-173">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="592db-174">Na nova guia **Marketing de campanha** no navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="592db-174">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="592db-175">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="592db-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="592db-176">Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="592db-176">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="592db-177">Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque as caixas de seleção **Permitir que membros compartilhem o site e arquivos e pastas individuais** e **Permitir que membros convidem outras pessoas para o grupo de membros do site**, digite **ITAdmin1 @**<your organization name> **.onmicrosoft.com** em **Enviar todas as solicitações para acesso** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="592db-177">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**<your organization name> **.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="592db-178">Clique em **Membros da campanha de marketing** na lista.</span><span class="sxs-lookup"><span data-stu-id="592db-178">Click **Campaign marketing Members** in the list.</span></span>
    
14. <span data-ttu-id="592db-179">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="592db-179">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="592db-180">Na caixa de diálogo **Compartilhar**, digite **Funcionários sênior e estratégicos**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="592db-180">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="592db-181">Repita as etapas 14 e 15 para o grupo **Equipe de análise** e a conta de usuário **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="592db-181">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>
    
17. <span data-ttu-id="592db-182">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="592db-182">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="592db-183">Clique em **Proprietários da campanha de marketing** na lista.</span><span class="sxs-lookup"><span data-stu-id="592db-183">Click **Campaign marketing Owners** in the list.</span></span>
    
19. <span data-ttu-id="592db-184">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="592db-184">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="592db-185">Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="592db-185">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="592db-186">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="592db-186">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="592db-187">Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Página inicial da campanha de marketing** no navegador e feche o painel **Permissões de site**.</span><span class="sxs-lookup"><span data-stu-id="592db-187">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="592db-188">Aqui estão os resultados da configuração de permissões:</span><span class="sxs-lookup"><span data-stu-id="592db-188">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="592db-189">O grupo do SharePoint **Membros da campanha de marketing** contém apenas o grupo **Funcionários sênior e estratégicos** (que contém as contas de usuário Candidato, ChiefOfStaff e Strategic1), o grupo **Marketing de campanha** (que contém a conta de administrador global), o grupo **Equipe de análise** (que contém a conta de usuário DataScientist1) e a conta de usuário **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="592db-189">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>
    
- <span data-ttu-id="592db-190">O grupo do SharePoint **Marketing de campanha – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="592db-190">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="592db-191">O grupo do SharePoint **Marketing de campanha – Visitantes** não contém grupos ou contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="592db-191">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="592db-192">Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Marketing de campanhas – Proprietários**).</span><span class="sxs-lookup"><span data-stu-id="592db-192">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>
    
- <span data-ttu-id="592db-193">Outras contas de usuário não podem acessar o site ou seus recursos, mas podem solicitar o acesso ao site, que enviará um email para a caixa de correio da conta de usuário ITAdmin1.</span><span class="sxs-lookup"><span data-stu-id="592db-193">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="592db-194">Em seguida, configure a pasta de documentos do site de equipe de marketing de campanha com o rótulo Confidencial.</span><span class="sxs-lookup"><span data-stu-id="592db-194">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="592db-195">Na guia **Marketing de campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="592db-195">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="592db-196">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="592db-196">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="592db-197">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="592db-197">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="592db-198">Em **Configurações – Aplicar Rótulo**, selecione **Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="592db-198">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="592db-p103">Em seguida, configure uma política de DLP (prevenção de perda de dados) que notifica os usuários quando eles compartilham um documento em um site de equipe do Microsoft SharePoint Online com o rótulo Confidencial fora da organização. Essa política de DLP se aplicará a recursos no site de marketing da campanha.</span><span class="sxs-lookup"><span data-stu-id="592db-p103">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>
  
1. <span data-ttu-id="592db-201">Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="592db-201">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>
    
2. <span data-ttu-id="592db-202">Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.</span><span class="sxs-lookup"><span data-stu-id="592db-202">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="592db-203">No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="592db-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="592db-204">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="592db-205">No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-205">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="592db-206">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="592db-207">Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="592db-208">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="592db-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="592db-209">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="592db-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="592db-210">No painel **Rótulos**, clique em **+ Adicionar**, selecione o rótulo **Confidencial**, clique em **Adicionar** e clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="592db-210">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="592db-211">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="592db-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="592db-212">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="592db-213">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="592db-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="592db-214">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="592db-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="592db-215">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="592db-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="592db-p104">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="592db-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="592db-219">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="592db-219">Click **OK**.</span></span>
    
17. <span data-ttu-id="592db-220">No painel **O que deseja fazer se detectarmos informações confidenciais?**, desmarque a caixa de seleção **Impedir que as pessoas compartilhem e restringir o acesso ao conteúdo compartilhado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-220">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="592db-221">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-221">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="592db-222">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="592db-222">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
### <a name="campaign-strategy-team-site"></a><span data-ttu-id="592db-223">Site de equipe de estratégia de campanha</span><span class="sxs-lookup"><span data-stu-id="592db-223">Campaign strategy team site</span></span>

<span data-ttu-id="592db-224">Para criar um site de equipe do SharePoint Online isolado no nível altamente confidencial para recursos de estratégia de campanha, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="592db-224">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>
  
1. <span data-ttu-id="592db-225">Se necessário, use um navegador do seu computador local e entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="592db-225">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="592db-226">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="592db-226">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="592db-227">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="592db-227">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="592db-228">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="592db-228">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="592db-229">Em **Nome do site de equipe**, digite **Estratégia da campanha**.</span><span class="sxs-lookup"><span data-stu-id="592db-229">In **Team site name**, type **Campaign strategy**.</span></span>
    
6. <span data-ttu-id="592db-230">Em **Descrição do site da equipe**, digite **Site do SharePoint para estratégia da campanha (altamente confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="592db-230">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="592db-231">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-231">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="592db-232">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="592db-232">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="592db-233">Na nova guia **Estratégia da campanha** no navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="592db-233">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="592db-234">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="592db-234">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="592db-235">Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="592db-235">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="592db-236">Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir que os membros convidem outros para o grupo de membros do site** (de forma que todas as três caixas de seleção estejam desmarcadas) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="592db-236">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="592db-237">Clique em **Membros da estratégia da campanha** na lista.</span><span class="sxs-lookup"><span data-stu-id="592db-237">Click **Campaign strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="592db-238">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="592db-238">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="592db-239">Na caixa de diálogo **Compartilhar**, digite **Funcionários sênior e estratégicos**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="592db-239">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="592db-240">Clique em **Proprietários de Estratégia de Campanha** na lista.</span><span class="sxs-lookup"><span data-stu-id="592db-240">Click **Campaign strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="592db-241">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="592db-241">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="592db-242">Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="592db-242">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="592db-243">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="592db-243">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="592db-244">Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Estratégia de campanha – Página Inicial** no navegador e feche o painel **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="592db-244">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="592db-245">Aqui estão os resultados da configuração de permissões:</span><span class="sxs-lookup"><span data-stu-id="592db-245">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="592db-246">O grupo **Membros estratégicos da campanha** do SharePoint contém apenas o grupo **Funcionários sênior e estratégicos** (que contém apenas as contas de usuário Candidato, ChiefOfStaff e Strategic1) e o grupo **Estratégia da campanha** (que contém a conta de usuário de administrador global).</span><span class="sxs-lookup"><span data-stu-id="592db-246">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="592db-247">O grupo do SharePoint **Estratégia da campanha – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="592db-247">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="592db-248">O grupo do SharePoint **Estratégia da campanha – Visitantes** não contém grupos ou contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="592db-248">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="592db-249">Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Estratégia da campanha – Proprietários**).</span><span class="sxs-lookup"><span data-stu-id="592db-249">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>
    
- <span data-ttu-id="592db-p105">Outras contas de usuário não podem acessar o site ou seus recursos ou solicitar o acesso ao site. As permissões adicionais para o site devem ser feias pelo administrador global ou por um membro do grupo **Estratégia da campanha – Proprietários**.</span><span class="sxs-lookup"><span data-stu-id="592db-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>
    
<span data-ttu-id="592db-252">Em seguida, configure a pasta de documentos do Site de equipe de estratégia de campanha com o rótulo Altamente Confidencial.</span><span class="sxs-lookup"><span data-stu-id="592db-252">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="592db-253">Na guia **Estratégia da campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="592db-253">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="592db-254">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="592db-254">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="592db-255">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="592db-255">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="592db-256">Em **Configurações – Aplicar Rótulo**, selecione **Altamente Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="592db-256">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="592db-p106">Em seguida, configure uma política de DLP que bloqueia os usuários quando eles compartilham um documento em um site de equipe do SharePoint Online com o rótulo altamente confidencial fora da organização. Essa política de DLP se aplicará a recursos no site de estratégia da campanha.</span><span class="sxs-lookup"><span data-stu-id="592db-p106">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>
  
1. <span data-ttu-id="592db-259">Se necessário, use um navegador no seu computador local e entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) com uma conta com a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="592db-259">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="592db-260">Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="592db-260">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>
    
3. <span data-ttu-id="592db-261">Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.</span><span class="sxs-lookup"><span data-stu-id="592db-261">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="592db-262">No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="592db-262">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="592db-263">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-263">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="592db-264">No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Altamente Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-264">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="592db-265">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-265">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="592db-266">Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-266">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
9. <span data-ttu-id="592db-267">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="592db-267">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
10. <span data-ttu-id="592db-268">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="592db-268">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
11. <span data-ttu-id="592db-269">No painel **Rótulos**, clique em **+ Adicionar**, selecione o **rótulo Altamente Confidencial**, clique em **Adicionar** e clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="592db-269">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
12. <span data-ttu-id="592db-270">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="592db-270">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
13. <span data-ttu-id="592db-271">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-271">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="592db-272">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="592db-272">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
15. <span data-ttu-id="592db-273">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="592db-273">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
16. <span data-ttu-id="592db-274">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="592db-274">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="592db-p107">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="592db-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
17. <span data-ttu-id="592db-278">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="592db-278">Click **OK**.</span></span>
    
18. <span data-ttu-id="592db-279">No painel **O que deseja fazer se detectarmos informações confidenciais?**, selecione **Exigir uma justificativa de negócios para substituir** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-279">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="592db-280">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592db-280">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
20. <span data-ttu-id="592db-281">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="592db-281">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="592db-282">Use as instruções em [Ativar o Azure RMS com o centro de administração do Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="592db-282">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="592db-283">Depois, configure a Proteção de Informações do Azure com uma nova política e sub-rótulo em escopo para proteção e permissões com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="592db-283">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="592db-284">Acesse o centro de administração com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="592db-284">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="592db-285">Para obter ajuda, consulte [Onde entrar no Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="592db-285">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="592db-286">Em uma guia separada do navegador, vá para o Portal do Azure ([https://portal.azure.com](https://portal.azure.com)).</span><span class="sxs-lookup"><span data-stu-id="592db-286">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
4. <span data-ttu-id="592db-287">No painel de pesquisa, digite **informações** e, em seguida, clique em **Proteção de Informações do Azure**.</span><span class="sxs-lookup"><span data-stu-id="592db-287">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="592db-288">Clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="592db-288">Click **Labels**.</span></span>
    
6. <span data-ttu-id="592db-289">Clique com o botão direito do mouse no rótulo **Altamente Confidencial** e clique em **Adicionar um sub-rótulo**.</span><span class="sxs-lookup"><span data-stu-id="592db-289">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="592db-290">Digite **CampaignStrategy** em **Nome** e **Rótulo para documentos no Site de equipe de estratégia de campanha** em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="592db-290">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>
    
8. <span data-ttu-id="592db-291">Em **Definir permissões para documentos e emails que contenham este rótulo**, clique em **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="592db-291">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="592db-292">Na seção **Proteção**, clique em **Azure (chave de nuvem)**.</span><span class="sxs-lookup"><span data-stu-id="592db-292">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="592db-293">Na folha **Proteção**, em **Configurações de proteção**, clique em **+ Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="592db-293">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="592db-294">Na folha **Adicionar permissões**, em **Especificar usuários e grupos**, clique em **+ Procurar no diretório**.</span><span class="sxs-lookup"><span data-stu-id="592db-294">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="592db-295">No painel **Usuários e Grupos do AAD**, selecione **Funcionários sênior e estratégicos** e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="592db-295">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="592db-296">Em **Escolher permissões a partir de valores predefinidos ou definir valores personalizados**, clique em **Personalizar** e, em seguida, clique nas caixas de seleção **Exibir Direitos**, **Editar Conteúdo**, **Salvar**, **Responder** e **Responder a Todos**.</span><span class="sxs-lookup"><span data-stu-id="592db-296">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="592db-297">Clique em **OK** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="592db-297">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="592db-298">Na folha **Sub-rótulo**, clique em **Salvar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="592db-298">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="592db-299">Na folha **Proteção de Informações do Azure**, clique em **Políticas > + Adicionar uma nova política**.</span><span class="sxs-lookup"><span data-stu-id="592db-299">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="592db-300">Digite **CampaignStrategy** em **Nome** e **Documentos no Site de equipe de estratégia de campanha** em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="592db-300">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="592db-301">Clique em **Selecionar usuários ou grupos que obtêm essa política > Usuário/Grupos** e selecione **Funcionários sênior e estratégicos**.</span><span class="sxs-lookup"><span data-stu-id="592db-301">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>
    
19. <span data-ttu-id="592db-302">Clique em **Selecionar > OK**.</span><span class="sxs-lookup"><span data-stu-id="592db-302">Click **Select > OK**.</span></span>

20. <span data-ttu-id="592db-p109">Clique em **Adicionar ou remover rótulos**. No painel **Política: adicionar ou remover rótulos**, clique em **CampaignStrategy** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="592db-p109">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>   

21. <span data-ttu-id="592db-305">Clique em **Salvar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="592db-305">Click **Save**, and then click **OK**.</span></span>
  
<span data-ttu-id="592db-306">Agora você está pronto para começar a criar documentos nesses quatro sites e testar o acesso a eles com várias contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="592db-306">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span> 
  
<span data-ttu-id="592db-307">Para proteger um documento com a Proteção de Informações do Azure e esse novo rótulo, você deve [instalar o cliente de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/install-client-app) em um computador de teste, instalar o Office do centro de administração e entrar no Microsoft Word com uma conta no grupo **Funcionários sênior e estratégicos** de sua assinatura de avaliação.</span><span class="sxs-lookup"><span data-stu-id="592db-307">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="592db-308">Confira também</span><span class="sxs-lookup"><span data-stu-id="592db-308">See Also</span></span>

[<span data-ttu-id="592db-309">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile</span><span class="sxs-lookup"><span data-stu-id="592db-309">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="592db-310">Defina grupos e usuários para um ambiente de desenvolvimento/teste de uma campanha política</span><span class="sxs-lookup"><span data-stu-id="592db-310">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="592db-311">Guias do Laboratório de Teste (TLGs) para adoção de nuvem</span><span class="sxs-lookup"><span data-stu-id="592db-311">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="592db-312">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="592db-312">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




