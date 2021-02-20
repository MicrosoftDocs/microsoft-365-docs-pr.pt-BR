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
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Resumo: crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste de campanha política.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c12970fb3ff6d5616201ff153085d411068d11c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288390"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="c2a0d-103">Criar sites de equipe em um ambiente de desenvolvimento/teste de campanha política</span><span class="sxs-lookup"><span data-stu-id="c2a0d-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c2a0d-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="c2a0d-104">**Applies to**</span></span>

- [<span data-ttu-id="c2a0d-105">Plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c2a0d-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- 
 <span data-ttu-id="c2a0d-106">**Resumo:** crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste de campanha política.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
   
<span data-ttu-id="c2a0d-p101">Use as instruções deste artigo para criar um ambiente de desenvolvimento/teste com quatro diferentes tipos de sites de equipe do SharePoint Online para a solução de [Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Esses sites são descritos em detalhes no tópico 10, intitulado **SharePoint e OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="c2a0d-109">Fase 1: Criar seu ambiente de desenvolvimento/teste de campanha política</span><span class="sxs-lookup"><span data-stu-id="c2a0d-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="c2a0d-110">Primeiro, siga as instruções em [Configurar grupos e usuários para um ambiente de desenvolvimento/teste de campanha política](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) para criar assinaturas, usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="c2a0d-111">Fase 2: criar rótulos</span><span class="sxs-lookup"><span data-stu-id="c2a0d-111">Phase 2: Create labels</span></span>

<span data-ttu-id="c2a0d-112">Nesta fase, você deve criar os rótulos para os diferentes níveis de segurança para as pastas e documentos do site da equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="c2a0d-113">Se necessário, entre no centro de administração com as credenciais da conta do administrador global da sua assinatura de avaliação.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-113">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="c2a0d-114">Para obter ajuda, consulte [Como entrar no Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="c2a0d-114">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="c2a0d-115">Na guia **Microsoft Office Home**, clique no bloco **Administração**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-115">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>

3. <span data-ttu-id="c2a0d-116">Na nova guia **Centro de Administração da Microsoft 365** do navegador, clique em **Centros de administração > Segurança e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-116">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>

4. <span data-ttu-id="c2a0d-117">Na nova guia **Início – Segurança e Conformidade** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-117">From the new **Home - Security & Compliance** tab of your browser, click **Classifications > Labels**.</span></span>

5. <span data-ttu-id="c2a0d-118">No painel **Início > Rótulos**, clique em **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-118">From the **Home > Labels** pane, click **Create a label**.</span></span>

6. <span data-ttu-id="c2a0d-119">No painel **Atribuir nome ao seu rótulo**, digite **Interno** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-119">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>

7. <span data-ttu-id="c2a0d-120">No painel **Configurações do rótulo**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-120">On the **Label settings** pane, click **Next**.</span></span>

8. <span data-ttu-id="c2a0d-121">No painel **Examine as configurações**, clique em **Criar este rótulo** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-121">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

9. <span data-ttu-id="c2a0d-122">Repita as etapas de 5 a 8 para os rótulos adicionais:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-122">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="c2a0d-123">Private</span><span class="sxs-lookup"><span data-stu-id="c2a0d-123">Private</span></span>
   - <span data-ttu-id="c2a0d-124">Confidencial</span><span class="sxs-lookup"><span data-stu-id="c2a0d-124">Sensitive</span></span>
   - <span data-ttu-id="c2a0d-125">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="c2a0d-125">Highly Confidential</span></span>

10. <span data-ttu-id="c2a0d-126">No painel **Início > Rótulos**, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>

11. <span data-ttu-id="c2a0d-127">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

12. <span data-ttu-id="c2a0d-128">No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

13. <span data-ttu-id="c2a0d-129">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-129">Click **Done**.</span></span>

14. <span data-ttu-id="c2a0d-130">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-130">On the **Choose labels to publish** pane, click **Next**.</span></span>

15. <span data-ttu-id="c2a0d-131">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-131">On the **Choose locations** pane, click **Next**.</span></span>

16. <span data-ttu-id="c2a0d-132">No painel **Nomear sua política**, digite **Campanha** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-132">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

17. <span data-ttu-id="c2a0d-133">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="c2a0d-134">Fase 3: Criar seus sites de equipe do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c2a0d-134">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="c2a0d-135">Nessa fase, você cria e configura sites de equipe do SharePoint Online para a campanha política correspondente aos quatro tipos de sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-135">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="c2a0d-136">Site de equipe de toda a campanha</span><span class="sxs-lookup"><span data-stu-id="c2a0d-136">Campaign wide team site</span></span>

<span data-ttu-id="c2a0d-137">Para criar um site de equipe do SharePoint Online público de linha de base, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-137">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="c2a0d-138">Se necessário, use um navegador do seu computador local e entre no centro de administração (<https://admin.microsoft.com>) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-138">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="c2a0d-139">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-139">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="c2a0d-140">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-140">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="c2a0d-141">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-141">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="c2a0d-142">Em **Nome do site**, digite **Toda a campanha**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-142">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="c2a0d-143">Na **Descrição do site de equipe**, digite **Site do SharePoint para toda a campanha**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-143">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="c2a0d-144">Em **Configurações de privacidade**, selecione **Público – qualquer pessoa na organização pode acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-144">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="c2a0d-145">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="c2a0d-146">Em seguida, configure a pasta de documentos do site de equipe Toda a campanha com o rótulo Interno.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-146">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="c2a0d-147">Na guia **Toda a campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-147">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="c2a0d-148">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-148">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="c2a0d-149">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="c2a0d-150">Em **Configurações – Aplicar Rótulo**, selecione **Interno** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-150">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="c2a0d-151">Site de equipe 1 de projeto de campanha</span><span class="sxs-lookup"><span data-stu-id="c2a0d-151">Campaign project 1 team site</span></span>

<span data-ttu-id="c2a0d-152">Para criar um site de equipe do SharePoint Online privado de linha de base para um projeto dentro da campanha, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-152">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="c2a0d-153">Se necessário, use um navegador do seu computador local e entre no centro de administração (<https://admin.microsoft.com>) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-153">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="c2a0d-154">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-154">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="c2a0d-155">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-155">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="c2a0d-156">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-156">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="c2a0d-157">Em **Nome do site**, digite **Projeto 1 da campanha**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-157">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="c2a0d-158">Na **Descrição do site de equipe**, digite **Site do SharePoint para Projeto 1 de campanha**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-158">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="c2a0d-159">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-159">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="c2a0d-160">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-160">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="c2a0d-161">Em seguida, configure a pasta de documentos do site de equipe Projeto 1 de campanha com o rótulo Privado.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-161">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="c2a0d-162">Na guia **Projeto 1 de campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-162">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="c2a0d-163">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-163">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="c2a0d-164">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-164">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="c2a0d-165">Em **Configurações – Aplicar Rótulo**, selecione **Privado** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-165">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="c2a0d-166">Site de equipe de marketing de campanha</span><span class="sxs-lookup"><span data-stu-id="c2a0d-166">Campaign marketing team site</span></span>

<span data-ttu-id="c2a0d-167">Para criar um site de equipe do SharePoint Online isolado de nível confidencial para recursos de marketing de campanha, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-167">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="c2a0d-168">Usando um navegador no seu computador local, entre no centro de administração (<https://admin.microsoft.com>) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-168">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="c2a0d-169">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-169">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="c2a0d-170">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-170">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="c2a0d-171">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-171">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="c2a0d-172">Em **Nome do site de equipe**, digite **Marketing de campanha**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-172">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="c2a0d-173">Em **Descrição do site de equipe**, digite **Site do SharePoint para marketing de campanha (confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-173">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="c2a0d-174">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-174">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="c2a0d-175">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-175">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="c2a0d-176">Na nova guia **Marketing de campanha** no navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-176">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="c2a0d-177">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-177">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="c2a0d-178">Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-178">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="c2a0d-179">Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque as caixas de seleção **Permitir que membros compartilhem o site e arquivos e pastas individuais** e **Permitir que membros convidem outras pessoas para o grupo de membros do site**, digite **ITAdmin1 @**\<your organization name\> **.onmicrosoft.com** em **Enviar todas as solicitações para acesso** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-179">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="c2a0d-180">Clique em **Membros da campanha de marketing** na lista.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-180">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="c2a0d-181">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-181">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="c2a0d-182">Na caixa de diálogo **Compartilhar**, digite **Funcionários sênior e estratégicos**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-182">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="c2a0d-183">Repita as etapas 14 e 15 para o grupo **Equipe de análise** e a conta de usuário **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-183">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="c2a0d-184">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-184">Click the back button on your browser.</span></span>

18. <span data-ttu-id="c2a0d-185">Clique em **Proprietários da campanha de marketing** na lista.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-185">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="c2a0d-186">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-186">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="c2a0d-187">Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-187">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="c2a0d-188">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-188">Click the back button on your browser.</span></span>

22. <span data-ttu-id="c2a0d-189">Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Página inicial da campanha de marketing** no navegador e feche o painel **Permissões de site**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-189">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="c2a0d-190">Aqui estão os resultados da configuração de permissões:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-190">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="c2a0d-191">O grupo do SharePoint **Membros da campanha de marketing** contém apenas o grupo **Funcionários sênior e estratégicos** (que contém as contas de usuário Candidato, ChiefOfStaff e Strategic1), o grupo **Marketing de campanha** (que contém a conta de administrador global), o grupo **Equipe de análise** (que contém a conta de usuário DataScientist1) e a conta de usuário **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-191">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="c2a0d-192">O grupo do SharePoint **Marketing de campanha – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="c2a0d-192">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="c2a0d-193">O grupo do SharePoint **Marketing de campanha – Visitantes** não contém grupos ou contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-193">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="c2a0d-194">Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Marketing de campanhas – Proprietários**).</span><span class="sxs-lookup"><span data-stu-id="c2a0d-194">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="c2a0d-195">Outras contas de usuário não podem acessar o site ou seus recursos, mas podem solicitar o acesso ao site, que enviará um email para a caixa de correio da conta de usuário ITAdmin1.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-195">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="c2a0d-196">Em seguida, configure a pasta de documentos do site de equipe de marketing de campanha com o rótulo Confidencial.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-196">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="c2a0d-197">Na guia **Marketing de campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-197">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="c2a0d-198">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-198">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="c2a0d-199">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="c2a0d-200">Em **Configurações – Aplicar Rótulo**, selecione **Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-200">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="c2a0d-p103">Em seguida, configure uma política de DLP (prevenção de perda de dados) que notifica os usuários quando eles compartilham um documento em um site de equipe do Microsoft SharePoint Online com o rótulo Confidencial fora da organização. Essa política de DLP se aplicará a recursos no site de marketing da campanha.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-p103">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="c2a0d-203">Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-203">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="c2a0d-204">Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-204">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="c2a0d-205">No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-205">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="c2a0d-206">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-206">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="c2a0d-207">No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-207">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="c2a0d-208">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-208">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="c2a0d-209">Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-209">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="c2a0d-210">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-210">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="c2a0d-211">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-211">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="c2a0d-212">No painel **Rótulos**, clique em **+ Adicionar**, selecione o rótulo **Confidencial**, clique em **Adicionar** e clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-212">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="c2a0d-213">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-213">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="c2a0d-214">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-214">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="c2a0d-215">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-215">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="c2a0d-216">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-216">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="c2a0d-217">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-217">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="c2a0d-p104">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="c2a0d-221">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-221">Click **OK**.</span></span>

17. <span data-ttu-id="c2a0d-222">No painel **O que deseja fazer se detectarmos informações confidenciais?**, desmarque a caixa de seleção **Impedir que as pessoas compartilhem e restringir o acesso ao conteúdo compartilhado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-222">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="c2a0d-223">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-223">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="c2a0d-224">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-224">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="c2a0d-225">Site de equipe de estratégia de campanha</span><span class="sxs-lookup"><span data-stu-id="c2a0d-225">Campaign strategy team site</span></span>

<span data-ttu-id="c2a0d-226">Para criar um site de equipe do SharePoint Online isolado no nível altamente confidencial para recursos de estratégia de campanha, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-226">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="c2a0d-227">Se necessário, use um navegador do seu computador local e entre no centro de administração (<https://admin.microsoft.com>) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-227">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="c2a0d-228">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-228">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="c2a0d-229">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-229">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="c2a0d-230">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-230">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="c2a0d-231">Em **Nome do site de equipe**, digite **Estratégia da campanha**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-231">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="c2a0d-232">Em **Descrição do site da equipe**, digite **Site do SharePoint para estratégia da campanha (altamente confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-232">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="c2a0d-233">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-233">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="c2a0d-234">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-234">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="c2a0d-235">Na nova guia **Estratégia da campanha** no navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-235">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="c2a0d-236">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-236">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="c2a0d-237">Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-237">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="c2a0d-238">Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir que os membros convidem outros para o grupo de membros do site** (de forma que todas as três caixas de seleção estejam desmarcadas) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-238">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="c2a0d-239">Clique em **Membros da estratégia da campanha** na lista.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-239">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="c2a0d-240">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-240">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="c2a0d-241">Na caixa de diálogo **Compartilhar**, digite **Funcionários sênior e estratégicos**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-241">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="c2a0d-242">Clique em **Proprietários de Estratégia de Campanha** na lista.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-242">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="c2a0d-243">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-243">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="c2a0d-244">Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-244">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="c2a0d-245">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-245">Click the back button on your browser.</span></span>

20. <span data-ttu-id="c2a0d-246">Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Estratégia de campanha – Página Inicial** no navegador e feche o painel **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-246">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="c2a0d-247">Aqui estão os resultados da configuração de permissões:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-247">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="c2a0d-248">O grupo **Membros estratégicos da campanha** do SharePoint contém apenas o grupo **Funcionários sênior e estratégicos** (que contém apenas as contas de usuário Candidato, ChiefOfStaff e Strategic1) e o grupo **Estratégia da campanha** (que contém a conta de usuário de administrador global).</span><span class="sxs-lookup"><span data-stu-id="c2a0d-248">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="c2a0d-249">O grupo do SharePoint **Estratégia da campanha – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="c2a0d-249">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="c2a0d-250">O grupo do SharePoint **Estratégia da campanha – Visitantes** não contém grupos ou contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-250">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="c2a0d-251">Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Estratégia da campanha – Proprietários**).</span><span class="sxs-lookup"><span data-stu-id="c2a0d-251">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="c2a0d-p105">Outras contas de usuário não podem acessar o site ou seus recursos ou solicitar o acesso ao site. As permissões adicionais para o site devem ser feias pelo administrador global ou por um membro do grupo **Estratégia da campanha – Proprietários**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="c2a0d-254">Em seguida, configure a pasta de documentos do Site de equipe de estratégia de campanha com o rótulo Altamente Confidencial.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-254">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="c2a0d-255">Na guia **Estratégia da campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-255">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="c2a0d-256">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-256">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="c2a0d-257">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-257">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="c2a0d-258">Em **Configurações – Aplicar Rótulo**, selecione **Altamente Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-258">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="c2a0d-p106">Em seguida, configure uma política de DLP que bloqueia os usuários quando eles compartilham um documento em um site de equipe do SharePoint Online com o rótulo altamente confidencial fora da organização. Essa política de DLP se aplicará a recursos no site de estratégia da campanha.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-p106">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="c2a0d-261">Se necessário, use um navegador no seu computador local e entre no centro de administração (<https://admin.microsoft.com>) com uma conta com a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-261">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="c2a0d-262">Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-262">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="c2a0d-263">Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-263">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="c2a0d-264">No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-264">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="c2a0d-265">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-265">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="c2a0d-266">No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Altamente Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-266">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="c2a0d-267">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-267">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="c2a0d-268">Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-268">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="c2a0d-269">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-269">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="c2a0d-270">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-270">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="c2a0d-271">No painel **Rótulos**, clique em **+ Adicionar**, selecione o **rótulo Altamente Confidencial**, clique em **Adicionar** e clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-271">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="c2a0d-272">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-272">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="c2a0d-273">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-273">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="c2a0d-274">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-274">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="c2a0d-275">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-275">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="c2a0d-276">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-276">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="c2a0d-p107">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="c2a0d-280">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-280">Click **OK**.</span></span>

18. <span data-ttu-id="c2a0d-281">No painel **O que deseja fazer se detectarmos informações confidenciais?**, selecione **Exigir uma justificativa de negócios para substituir** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-281">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="c2a0d-282">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-282">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="c2a0d-283">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-283">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="c2a0d-284">Use as instruções em [Ativar o Azure RMS com o centro de administração do Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="c2a0d-284">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="c2a0d-285">Depois, configure a Proteção de Informações do Azure com uma nova política e sub-rótulo em escopo para proteção e permissões com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c2a0d-285">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="c2a0d-286">Acesse o centro de administração com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-286">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="c2a0d-287">Para obter ajuda, consulte [Onde entrar no Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="c2a0d-287">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="c2a0d-288">Em uma guia separada do navegador, vá para o portal do Microsoft Azure (<https://portal.azure.com>).</span><span class="sxs-lookup"><span data-stu-id="c2a0d-288">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="c2a0d-289">No painel de pesquisa, digite **informações** e, em seguida, clique em **Proteção de Informações do Azure**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-289">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="c2a0d-290">Clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-290">Click **Labels**.</span></span>

5. <span data-ttu-id="c2a0d-291">Clique com o botão direito do mouse no rótulo **Altamente Confidencial** e clique em **Adicionar um sub-rótulo**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-291">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="c2a0d-292">Digite **CampaignStrategy** em **Nome** e **Rótulo para documentos no Site de equipe de estratégia de campanha** em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-292">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="c2a0d-293">Em **Definir permissões para documentos e emails que contenham este rótulo**, clique em **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-293">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="c2a0d-294">Na seção **Proteção**, clique em **Azure (chave de nuvem)**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-294">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="c2a0d-295">Na folha **Proteção**, em **Configurações de proteção**, clique em **+ Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-295">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="c2a0d-296">Na folha **Adicionar permissões**, em **Especificar usuários e grupos**, clique em **+ Procurar no diretório**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-296">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="c2a0d-297">No painel **Usuários e Grupos do AAD**, selecione **Funcionários sênior e estratégicos** e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-297">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="c2a0d-298">Em **Escolher permissões a partir de valores predefinidos ou definir valores personalizados**, clique em **Personalizar** e, em seguida, clique nas caixas de seleção **Exibir Direitos**, **Editar Conteúdo**, **Salvar**, **Responder** e **Responder a Todos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-298">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="c2a0d-299">Clique em **OK** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-299">Click **OK** twice.</span></span>

14. <span data-ttu-id="c2a0d-300">Na folha **Sub-rótulo**, clique em **Salvar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-300">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="c2a0d-301">Na folha **Proteção de Informações do Azure**, clique em **Políticas > + Adicionar uma nova política**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-301">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="c2a0d-302">Digite **CampaignStrategy** em **Nome** e **Documentos no Site de equipe de estratégia de campanha** em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-302">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="c2a0d-303">Clique em **Selecionar usuários ou grupos que obtêm essa política > Usuário/Grupos** e selecione **Funcionários sênior e estratégicos**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-303">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="c2a0d-304">Clique em **Selecionar\> OK**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-304">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="c2a0d-p109">Clique em **Adicionar ou remover rótulos**. No painel **Política: adicionar ou remover rótulos**, clique em **CampaignStrategy** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-p109">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="c2a0d-307">Clique em **Salvar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-307">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="c2a0d-308">Agora você está pronto para começar a criar documentos nesses quatro sites e testar o acesso a eles com várias contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-308">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="c2a0d-309">Para proteger um documento com a Proteção de Informações do Azure e esse novo rótulo, você deve [instalar o cliente de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/install-client-app) em um computador de teste, instalar o Office do centro de administração e entrar no Microsoft Word com uma conta no grupo **Funcionários sênior e estratégicos** de sua assinatura de avaliação.</span><span class="sxs-lookup"><span data-stu-id="c2a0d-309">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2a0d-310">Confira também</span><span class="sxs-lookup"><span data-stu-id="c2a0d-310">See Also</span></span>

[<span data-ttu-id="c2a0d-311">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile</span><span class="sxs-lookup"><span data-stu-id="c2a0d-311">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="c2a0d-312">Defina grupos e usuários para um ambiente de desenvolvimento/teste de uma campanha política</span><span class="sxs-lookup"><span data-stu-id="c2a0d-312">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="c2a0d-313">Guias do Laboratório de Teste (TLGs) para adoção de nuvem</span><span class="sxs-lookup"><span data-stu-id="c2a0d-313">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="c2a0d-314">Centro de soluções e arquitetura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2a0d-314">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)
