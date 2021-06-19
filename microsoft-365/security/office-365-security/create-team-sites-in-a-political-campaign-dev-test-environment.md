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
ms.openlocfilehash: fcba6e2f3939115d6dfbaae80d322246bdeadee9
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029892"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="b58e2-103">Criar sites de equipe em um ambiente de desenvolvimento/teste de campanha política</span><span class="sxs-lookup"><span data-stu-id="b58e2-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b58e2-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="b58e2-104">**Applies to**</span></span>

- [<span data-ttu-id="b58e2-105">Plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b58e2-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="b58e2-106">**Resumo:** crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste de campanha política.</span><span class="sxs-lookup"><span data-stu-id="b58e2-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span>

<span data-ttu-id="b58e2-p101">Use as instruções deste artigo para criar um ambiente de desenvolvimento/teste com quatro diferentes tipos de sites de equipe do SharePoint Online para a solução de [Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Esses sites são descritos em detalhes no tópico 10, intitulado **SharePoint e OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="b58e2-109">Fase 1: Criar seu ambiente de desenvolvimento/teste de campanha política</span><span class="sxs-lookup"><span data-stu-id="b58e2-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="b58e2-110">Primeiro, siga as instruções em [Configurar grupos e usuários para um ambiente de desenvolvimento/teste de campanha política](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) para criar assinaturas, usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="b58e2-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="b58e2-111">Fase 2: criar rótulos</span><span class="sxs-lookup"><span data-stu-id="b58e2-111">Phase 2: Create labels</span></span>

<span data-ttu-id="b58e2-112">Nesta fase, você deve criar os rótulos para os diferentes níveis de segurança para as pastas e documentos do site da equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b58e2-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="b58e2-p102">Se necessário, entre no Centro de administração do Microsoft 365 (<https://admin.microsoft.com>) com as credenciais da conta de administrador global da sua assinatura de avaliação. Para obter ajuda, consulte [Onde entrar no Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="b58e2-p102">If needed, sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) with the credentials of the global administrator account of your trial subscription. For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="b58e2-115">Na Página **inicial**, clique em **Mostrar todos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-115">From the **Home** page where you start, click **Show all**.</span></span> <span data-ttu-id="b58e2-116">Na seção **Centro de administração** que aparece, clique em **Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-116">In the **Admin centers** section that appears, click **Compliance**.</span></span>

3. <span data-ttu-id="b58e2-117">Na página **Home** do Centro de conformidade do Microsoft 365, acesse a seção **Soluções**\> **Proteção de Informações**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-117">From the **Home** page of the Microsoft 365 compliance center, go to the **Solutions** section \> **Information protection**.</span></span> <span data-ttu-id="b58e2-118">Para ir diretamente à página de **Proteção de Informações**, use <https://compliance.microsoft.com//informationprotection>.</span><span class="sxs-lookup"><span data-stu-id="b58e2-118">To go directly to the **Information protection** page, use <https://compliance.microsoft.com//informationprotection>.</span></span>

4. <span data-ttu-id="b58e2-119">Na página de **Proteção de Informações**, verifique se a marca **Rótulo** está selecionada e clique em ![Criar um ícone de rótulo](../../media/m365-cc-sc-create-icon.png) **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-119">On the **Information protection** page, verify that the **Label** tag is selected, and then click  ![Create a label icon](../../media/m365-cc-sc-create-icon.png) **Create a label**.</span></span>

5. <span data-ttu-id="b58e2-120">O assistente de **Novo rótulo de confidencialidade** é aberto.</span><span class="sxs-lookup"><span data-stu-id="b58e2-120">The **New sensitivity label** wizard opens.</span></span> <span data-ttu-id="b58e2-121">Na etapa **Nome e descrição**, insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b58e2-121">On the **Name & description** step, enter the following values:</span></span>
   - <span data-ttu-id="b58e2-122">**Nome**: Tipo **Interno**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-122">**Name**: Type **Internal**.</span></span>
   - <span data-ttu-id="b58e2-123">**Nome de Exibição**</span><span class="sxs-lookup"><span data-stu-id="b58e2-123">**Display name**</span></span>
   - <span data-ttu-id="b58e2-124">**Descrição para usuários**</span><span class="sxs-lookup"><span data-stu-id="b58e2-124">**Description for users**</span></span>

   <span data-ttu-id="b58e2-125">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-125">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b58e2-126">No painel **Configurações do rótulo**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-126">On the **Label settings** pane, click **Next**.</span></span>

7. <span data-ttu-id="b58e2-127">No painel **Examine as configurações**, clique em **Criar este rótulo** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-127">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

8. <span data-ttu-id="b58e2-128">Repita as etapas de 5 a 8 para os rótulos adicionais:</span><span class="sxs-lookup"><span data-stu-id="b58e2-128">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="b58e2-129">Private</span><span class="sxs-lookup"><span data-stu-id="b58e2-129">Private</span></span>
   - <span data-ttu-id="b58e2-130">Confidencial</span><span class="sxs-lookup"><span data-stu-id="b58e2-130">Sensitive</span></span>
   - <span data-ttu-id="b58e2-131">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="b58e2-131">Highly Confidential</span></span>

9. <span data-ttu-id="b58e2-132">No painel **Início > Rótulos**, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-132">From the **Home > Labels** pane, click **Publish labels**.</span></span>

10. <span data-ttu-id="b58e2-133">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-133">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

11. <span data-ttu-id="b58e2-134">No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="b58e2-134">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

12. <span data-ttu-id="b58e2-135">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-135">Click **Done**.</span></span>

13. <span data-ttu-id="b58e2-136">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-136">On the **Choose labels to publish** pane, click **Next**.</span></span>

14. <span data-ttu-id="b58e2-137">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-137">On the **Choose locations** pane, click **Next**.</span></span>

15. <span data-ttu-id="b58e2-138">No painel **Nomear sua política**, digite **Campanha** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-138">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

16. <span data-ttu-id="b58e2-139">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-139">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="b58e2-140">Fase 3: Criar seus sites de equipe do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b58e2-140">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="b58e2-141">Nessa fase, você cria e configura sites de equipe do SharePoint Online para a campanha política correspondente aos quatro tipos de sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b58e2-141">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="b58e2-142">Site de equipe de toda a campanha</span><span class="sxs-lookup"><span data-stu-id="b58e2-142">Campaign wide team site</span></span>

<span data-ttu-id="b58e2-143">Para criar um site de equipe do SharePoint Online público de linha de base, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b58e2-143">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="b58e2-144">Se necessário, use um navegador do seu computador local e entre no centro de administração (<https://admin.microsoft.com>) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b58e2-144">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="b58e2-145">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-145">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="b58e2-146">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-146">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="b58e2-147">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-147">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="b58e2-148">Em **Nome do site**, digite **Toda a campanha**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-148">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="b58e2-149">Na **Descrição do site de equipe**, digite **Site do SharePoint para toda a campanha**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-149">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="b58e2-150">Em **Configurações de privacidade**, selecione **Público – qualquer pessoa na organização pode acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-150">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="b58e2-151">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-151">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="b58e2-152">Em seguida, configure a pasta de documentos do site de equipe Toda a campanha com o rótulo Interno.</span><span class="sxs-lookup"><span data-stu-id="b58e2-152">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="b58e2-153">Na guia **Toda a campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-153">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="b58e2-154">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-154">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="b58e2-155">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-155">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="b58e2-156">Em **Configurações – Aplicar Rótulo**, selecione **Interno** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-156">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="b58e2-157">Site de equipe 1 de projeto de campanha</span><span class="sxs-lookup"><span data-stu-id="b58e2-157">Campaign project 1 team site</span></span>

<span data-ttu-id="b58e2-158">Para criar um site de equipe do SharePoint Online privado de linha de base para um projeto dentro da campanha, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b58e2-158">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="b58e2-159">Se necessário, use um navegador do seu computador local e entre no centro de administração (<https://admin.microsoft.com>) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b58e2-159">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="b58e2-160">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-160">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="b58e2-161">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-161">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="b58e2-162">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-162">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="b58e2-163">Em **Nome do site**, digite **Projeto 1 da campanha**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-163">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="b58e2-164">Na **Descrição do site de equipe**, digite **Site do SharePoint para Projeto 1 de campanha**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-164">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="b58e2-165">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-165">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="b58e2-166">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-166">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="b58e2-167">Em seguida, configure a pasta de documentos do site de equipe Projeto 1 de campanha com o rótulo Privado.</span><span class="sxs-lookup"><span data-stu-id="b58e2-167">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="b58e2-168">Na guia **Projeto 1 de campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-168">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="b58e2-169">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-169">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="b58e2-170">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-170">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="b58e2-171">Em **Configurações – Aplicar Rótulo**, selecione **Privado** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-171">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="b58e2-172">Site de equipe de marketing de campanha</span><span class="sxs-lookup"><span data-stu-id="b58e2-172">Campaign marketing team site</span></span>

<span data-ttu-id="b58e2-173">Para criar um site de equipe do SharePoint Online isolado de nível confidencial para recursos de marketing de campanha, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b58e2-173">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="b58e2-174">Usando um navegador no seu computador local, entre no centro de administração (<https://admin.microsoft.com>) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b58e2-174">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="b58e2-175">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-175">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="b58e2-176">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-176">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="b58e2-177">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-177">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="b58e2-178">Em **Nome do site de equipe**, digite **Marketing de campanha**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-178">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="b58e2-179">Em **Descrição do site de equipe**, digite **Site do SharePoint para marketing de campanha (confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-179">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="b58e2-180">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-180">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="b58e2-181">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-181">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="b58e2-182">Na nova guia **Marketing de campanha** no navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-182">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="b58e2-183">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="b58e2-184">Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-184">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="b58e2-185">Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque as caixas de seleção **Permitir que membros compartilhem o site e arquivos e pastas individuais** e **Permitir que membros convidem outras pessoas para o grupo de membros do site**, digite **ITAdmin1 @**\<your organization name\> **.onmicrosoft.com** em **Enviar todas as solicitações para acesso** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-185">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="b58e2-186">Clique em **Membros da campanha de marketing** na lista.</span><span class="sxs-lookup"><span data-stu-id="b58e2-186">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="b58e2-187">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-187">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="b58e2-188">Na caixa de diálogo **Compartilhar**, digite **Funcionários sênior e estratégicos**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-188">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="b58e2-189">Repita as etapas 14 e 15 para o grupo **Equipe de análise** e a conta de usuário **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-189">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="b58e2-190">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="b58e2-190">Click the back button on your browser.</span></span>

18. <span data-ttu-id="b58e2-191">Clique em **Proprietários da campanha de marketing** na lista.</span><span class="sxs-lookup"><span data-stu-id="b58e2-191">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="b58e2-192">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-192">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="b58e2-193">Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-193">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="b58e2-194">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="b58e2-194">Click the back button on your browser.</span></span>

22. <span data-ttu-id="b58e2-195">Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Página inicial da campanha de marketing** no navegador e feche o painel **Permissões de site**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-195">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="b58e2-196">Aqui estão os resultados da configuração de permissões:</span><span class="sxs-lookup"><span data-stu-id="b58e2-196">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="b58e2-197">O grupo do SharePoint **Membros da campanha de marketing** contém apenas o grupo **Funcionários sênior e estratégicos** (que contém as contas de usuário Candidato, ChiefOfStaff e Strategic1), o grupo **Marketing de campanha** (que contém a conta de administrador global), o grupo **Equipe de análise** (que contém a conta de usuário DataScientist1) e a conta de usuário **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-197">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="b58e2-198">O grupo do SharePoint **Marketing de campanha – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="b58e2-198">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="b58e2-199">O grupo do SharePoint **Marketing de campanha – Visitantes** não contém grupos ou contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="b58e2-199">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="b58e2-200">Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Marketing de campanhas – Proprietários**).</span><span class="sxs-lookup"><span data-stu-id="b58e2-200">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="b58e2-201">Outras contas de usuário não podem acessar o site ou seus recursos, mas podem solicitar o acesso ao site, que enviará um email para a caixa de correio da conta de usuário ITAdmin1.</span><span class="sxs-lookup"><span data-stu-id="b58e2-201">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="b58e2-202">Em seguida, configure a pasta de documentos do site de equipe de marketing de campanha com o rótulo Confidencial.</span><span class="sxs-lookup"><span data-stu-id="b58e2-202">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="b58e2-203">Na guia **Marketing de campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-203">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="b58e2-204">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-204">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="b58e2-205">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-205">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="b58e2-206">Em **Configurações – Aplicar Rótulo**, selecione **Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-206">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="b58e2-p106">Em seguida, configure uma política de DLP (prevenção de perda de dados) que notifica os usuários quando eles compartilham um documento em um site de equipe do Microsoft SharePoint Online com o rótulo Confidencial fora da organização. Essa política de DLP se aplicará a recursos no site de marketing da campanha.</span><span class="sxs-lookup"><span data-stu-id="b58e2-p106">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="b58e2-209">Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-209">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="b58e2-210">Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-210">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="b58e2-211">No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-211">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="b58e2-212">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-212">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="b58e2-213">No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-213">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="b58e2-214">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-214">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="b58e2-215">Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-215">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="b58e2-216">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-216">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="b58e2-217">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-217">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="b58e2-218">No painel **Rótulos**, clique em **+ Adicionar**, selecione o rótulo **Confidencial**, clique em **Adicionar** e clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-218">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="b58e2-219">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-219">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="b58e2-220">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-220">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="b58e2-221">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-221">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="b58e2-222">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-222">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="b58e2-223">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b58e2-223">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="b58e2-p107">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="b58e2-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="b58e2-227">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-227">Click **OK**.</span></span>

17. <span data-ttu-id="b58e2-228">No painel **O que deseja fazer se detectarmos informações confidenciais?**, desmarque a caixa de seleção **Impedir que as pessoas compartilhem e restringir o acesso ao conteúdo compartilhado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-228">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="b58e2-229">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-229">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="b58e2-230">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-230">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="b58e2-231">Site de equipe de estratégia de campanha</span><span class="sxs-lookup"><span data-stu-id="b58e2-231">Campaign strategy team site</span></span>

<span data-ttu-id="b58e2-232">Para criar um site de equipe do SharePoint Online isolado no nível altamente confidencial para recursos de estratégia de campanha, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b58e2-232">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="b58e2-233">Se necessário, use um navegador do seu computador local e entre no centro de administração (<https://admin.microsoft.com>) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b58e2-233">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="b58e2-234">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-234">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="b58e2-235">Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-235">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="b58e2-236">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-236">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="b58e2-237">Em **Nome do site de equipe**, digite **Estratégia da campanha**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-237">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="b58e2-238">Em **Descrição do site da equipe**, digite **Site do SharePoint para estratégia da campanha (altamente confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-238">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="b58e2-239">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-239">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="b58e2-240">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-240">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="b58e2-241">Na nova guia **Estratégia da campanha** no navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-241">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="b58e2-242">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-242">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="b58e2-243">Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-243">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="b58e2-244">Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir que os membros convidem outros para o grupo de membros do site** (de forma que todas as três caixas de seleção estejam desmarcadas) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-244">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="b58e2-245">Clique em **Membros da estratégia da campanha** na lista.</span><span class="sxs-lookup"><span data-stu-id="b58e2-245">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="b58e2-246">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-246">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="b58e2-247">Na caixa de diálogo **Compartilhar**, digite **Funcionários sênior e estratégicos**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-247">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="b58e2-248">Clique em **Proprietários de Estratégia de Campanha** na lista.</span><span class="sxs-lookup"><span data-stu-id="b58e2-248">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="b58e2-249">Na página **Pessoas e Grupos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-249">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="b58e2-250">Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-250">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="b58e2-251">Clique no botão Voltar de seu navegador.</span><span class="sxs-lookup"><span data-stu-id="b58e2-251">Click the back button on your browser.</span></span>

20. <span data-ttu-id="b58e2-252">Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Estratégia de campanha – Página Inicial** no navegador e feche o painel **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-252">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="b58e2-253">Aqui estão os resultados da configuração de permissões:</span><span class="sxs-lookup"><span data-stu-id="b58e2-253">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="b58e2-254">O grupo **Membros estratégicos da campanha** do SharePoint contém apenas o grupo **Funcionários sênior e estratégicos** (que contém apenas as contas de usuário Candidato, ChiefOfStaff e Strategic1) e o grupo **Estratégia da campanha** (que contém a conta de usuário de administrador global).</span><span class="sxs-lookup"><span data-stu-id="b58e2-254">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="b58e2-255">O grupo do SharePoint **Estratégia da campanha – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="b58e2-255">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="b58e2-256">O grupo do SharePoint **Estratégia da campanha – Visitantes** não contém grupos ou contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="b58e2-256">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="b58e2-257">Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Estratégia da campanha – Proprietários**).</span><span class="sxs-lookup"><span data-stu-id="b58e2-257">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="b58e2-p108">Outras contas de usuário não podem acessar o site ou seus recursos ou solicitar o acesso ao site. As permissões adicionais para o site devem ser feias pelo administrador global ou por um membro do grupo **Estratégia da campanha – Proprietários**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-p108">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="b58e2-260">Em seguida, configure a pasta de documentos do Site de equipe de estratégia de campanha com o rótulo Altamente Confidencial.</span><span class="sxs-lookup"><span data-stu-id="b58e2-260">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="b58e2-261">Na guia **Estratégia da campanha – Página inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-261">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="b58e2-262">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-262">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="b58e2-263">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-263">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="b58e2-264">Em **Configurações – Aplicar Rótulo**, selecione **Altamente Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-264">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="b58e2-p109">Em seguida, configure uma política de DLP que bloqueia os usuários quando eles compartilham um documento em um site de equipe do SharePoint Online com o rótulo altamente confidencial fora da organização. Essa política de DLP se aplicará a recursos no site de estratégia da campanha.</span><span class="sxs-lookup"><span data-stu-id="b58e2-p109">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="b58e2-267">Se necessário, use um navegador no seu computador local e entre no centro de administração (<https://admin.microsoft.com>) com uma conta com a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="b58e2-267">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="b58e2-268">Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-268">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="b58e2-269">Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-269">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="b58e2-270">No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-270">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="b58e2-271">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-271">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="b58e2-272">No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Altamente Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-272">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="b58e2-273">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-273">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="b58e2-274">Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-274">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="b58e2-275">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-275">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="b58e2-276">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-276">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="b58e2-277">No painel **Rótulos**, clique em **+ Adicionar**, selecione o **rótulo Altamente Confidencial**, clique em **Adicionar** e clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-277">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="b58e2-278">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-278">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="b58e2-279">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-279">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="b58e2-280">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-280">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="b58e2-281">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-281">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="b58e2-282">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b58e2-282">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="b58e2-p110">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="b58e2-p110">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="b58e2-286">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-286">Click **OK**.</span></span>

18. <span data-ttu-id="b58e2-287">No painel **O que deseja fazer se detectarmos informações confidenciais?**, selecione **Exigir uma justificativa de negócios para substituir** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-287">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="b58e2-288">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-288">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="b58e2-289">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-289">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="b58e2-290">Use as instruções em [Ativar o Azure RMS com o centro de administração do Microsoft 365](/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="b58e2-290">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="b58e2-291">Depois, configure a Proteção de Informações do Azure com uma nova política e sub-rótulo em escopo para proteção e permissões com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b58e2-291">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="b58e2-p111">Entre no centro de administração com uma conta que tenha a função Administrador de Segurança ou Administrador da Empresa. Para obter ajuda, confira [Onde entrar no Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="b58e2-p111">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="b58e2-294">Em uma guia separada do navegador, vá para o portal do Microsoft Azure (<https://portal.azure.com>).</span><span class="sxs-lookup"><span data-stu-id="b58e2-294">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="b58e2-295">No painel de pesquisa, digite **informações** e, em seguida, clique em **Proteção de Informações do Azure**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-295">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="b58e2-296">Clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-296">Click **Labels**.</span></span>

5. <span data-ttu-id="b58e2-297">Clique com o botão direito do mouse no rótulo **Altamente Confidencial** e clique em **Adicionar um sub-rótulo**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-297">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="b58e2-298">Digite **CampaignStrategy** em **Nome** e **Rótulo para documentos no Site de equipe de estratégia de campanha** em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-298">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="b58e2-299">Em **Definir permissões para documentos e emails que contenham este rótulo**, clique em **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-299">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="b58e2-300">Na seção **Proteção**, clique em **Azure (chave de nuvem)**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-300">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="b58e2-301">Na folha **Proteção**, em **Configurações de proteção**, clique em **+ Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-301">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="b58e2-302">Na folha **Adicionar permissões**, em **Especificar usuários e grupos**, clique em **+ Procurar no diretório**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-302">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="b58e2-303">No painel **Usuários e Grupos do AAD**, selecione **Funcionários sênior e estratégicos** e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-303">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="b58e2-304">Em **Escolher permissões a partir de valores predefinidos ou definir valores personalizados**, clique em **Personalizar** e, em seguida, clique nas caixas de seleção **Exibir Direitos**, **Editar Conteúdo**, **Salvar**, **Responder** e **Responder a Todos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-304">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="b58e2-305">Clique em **OK** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="b58e2-305">Click **OK** twice.</span></span>

14. <span data-ttu-id="b58e2-306">Na folha **Sub-rótulo**, clique em **Salvar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-306">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="b58e2-307">Na folha **Proteção de Informações do Azure**, clique em **Políticas > + Adicionar uma nova política**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-307">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="b58e2-308">Digite **CampaignStrategy** em **Nome** e **Documentos no Site de equipe de estratégia de campanha** em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-308">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="b58e2-309">Clique em **Selecionar usuários ou grupos que obtêm essa política > Usuário/Grupos** e selecione **Funcionários sênior e estratégicos**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-309">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="b58e2-310">Clique em **Selecionar\> OK**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-310">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="b58e2-p112">Clique em **Adicionar ou remover rótulos**. No painel **Política: adicionar ou remover rótulos**, clique em **CampaignStrategy** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-p112">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="b58e2-313">Clique em **Salvar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b58e2-313">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="b58e2-314">Agora você está pronto para começar a criar documentos nesses quatro sites e testar o acesso a eles com várias contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="b58e2-314">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="b58e2-315">Para proteger um documento com a Proteção de Informações do Azure e esse novo rótulo, você deve [instalar o cliente de Proteção de Informações do Azure](/information-protection/rms-client/install-client-app) em um computador de teste, instalar o Office do centro de administração e entrar no Microsoft Word com uma conta no grupo **Funcionários sênior e estratégicos** de sua assinatura de avaliação.</span><span class="sxs-lookup"><span data-stu-id="b58e2-315">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="b58e2-316">Confira também</span><span class="sxs-lookup"><span data-stu-id="b58e2-316">See Also</span></span>

[<span data-ttu-id="b58e2-317">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile</span><span class="sxs-lookup"><span data-stu-id="b58e2-317">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="b58e2-318">Defina grupos e usuários para um ambiente de desenvolvimento/teste de uma campanha política</span><span class="sxs-lookup"><span data-stu-id="b58e2-318">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="b58e2-319">Guias do Laboratório de Teste (TLGs) para adoção de nuvem</span><span class="sxs-lookup"><span data-stu-id="b58e2-319">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="b58e2-320">Centro de soluções e arquitetura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b58e2-320">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)