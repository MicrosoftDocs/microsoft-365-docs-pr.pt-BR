---
title: Ambiente de teste de classificação de dados para a sua empresa de 365 da Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para criar e usar o Office 365 rótulos em documentos em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865293"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="60ac7-103">Ambiente de teste de classificação de dados para a sua empresa de 365 da Microsoft</span><span class="sxs-lookup"><span data-stu-id="60ac7-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="60ac7-104">Com as instruções deste artigo, você deve configurar o uso de rótulos de retenção do Office 365 em seu ambiente de teste do Microsoft 365 Enterprise de classificação de dados.</span><span class="sxs-lookup"><span data-stu-id="60ac7-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="60ac7-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="60ac7-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="60ac7-107">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="60ac7-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="60ac7-108">Se você deseja configurar rótulos de Office 365 de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="60ac7-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="60ac7-109">Se você deseja configurar rótulos do Office 365 em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="60ac7-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="60ac7-p101">Teste o Office 365 rótulos não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="60ac7-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="60ac7-112">Fase 2: Criar rótulos do Office 365</span><span class="sxs-lookup"><span data-stu-id="60ac7-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="60ac7-113">Nesta fase, você deve criar os rótulos para os diferentes níveis de retenção para pastas de documentos do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="60ac7-113">In this phase, you create the labels for the different levels of retention for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="60ac7-p102">Se necessário, use uma instância particular do seu navegador da Internet e entrar no portal do Office com sua conta de administrador global. Para obter ajuda, consulte [Where entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="60ac7-p102">If needed, use a private instance of your Internet browser and sign in to the Office portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="60ac7-116">Na guia **Microsoft Office Home**, clique no bloco **Administração**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="60ac7-117">Na nova guia **Centro de Administração do Office** do navegador, clique em **Centros de Administração > Segurança&amp; e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="60ac7-p103">Do novo **Home - segurança &amp; conformidade** guia do navegador, clique em **classificações > rótulos**. Da **Home > rótulos** painel, clique na guia **retenção** .</span><span class="sxs-lookup"><span data-stu-id="60ac7-p103">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**. From the **Home > Labels** pane, click the **Retention** tab.</span></span>
    
5. <span data-ttu-id="60ac7-120">Clique em **criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-120">Click **Create a label**.</span></span>
    
6. <span data-ttu-id="60ac7-121">No painel **Atribuir nome ao seu rótulo**, digite **Público interno** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-121">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="60ac7-122">No painel **Configurações de rótulo**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-122">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="60ac7-123">No painel **Examine as configurações**, clique em **Criar este rótulo** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-123">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="60ac7-124">Repita as etapas de 5 a 8 para os rótulos adicionais:</span><span class="sxs-lookup"><span data-stu-id="60ac7-124">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="60ac7-125">Private</span><span class="sxs-lookup"><span data-stu-id="60ac7-125">Private</span></span>
    
  - <span data-ttu-id="60ac7-126">Confidencial</span><span class="sxs-lookup"><span data-stu-id="60ac7-126">Sensitive</span></span>
    
  - <span data-ttu-id="60ac7-127">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="60ac7-127">Highly Confidential</span></span>
    
10. <span data-ttu-id="60ac7-128">No painel **Início > Rótulos**, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-128">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="60ac7-129">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-129">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="60ac7-130">No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="60ac7-130">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="60ac7-131">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-131">Click **Done**.</span></span>
    
14. <span data-ttu-id="60ac7-132">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-132">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="60ac7-133">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-133">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="60ac7-134">No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-134">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="60ac7-135">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-135">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="60ac7-136">Observe que poderá levar alguns minutos para que os rótulos sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="60ac7-136">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="60ac7-137">Fase 3: Aplicar rótulos de retenção do Office 365 a documentos</span><span class="sxs-lookup"><span data-stu-id="60ac7-137">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="60ac7-138">Nesta fase, você pode descobrir o comportamento padrão de rótulo para arquivos na pasta de documentos de um site do SharePoint Online e altera manualmente o rótulo de um documento.</span><span class="sxs-lookup"><span data-stu-id="60ac7-138">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="60ac7-139">Primeiro, crie um site de equipe do SharePoint Online confidenciais nível:</span><span class="sxs-lookup"><span data-stu-id="60ac7-139">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="60ac7-p104">Usando um navegador no computador local, entre no portal do Office usando sua conta de administrador global. Para obter ajuda, consulte [Where entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="60ac7-p104">Using a browser on your local computer, sign in to the Office portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="60ac7-142">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-142">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="60ac7-143">Na guia **SharePoint** de novo no seu navegador, clique em **Criar site**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-143">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="60ac7-144">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-144">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="60ac7-145">Em **nome do site de equipe**, digite **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-145">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="60ac7-146">Na **Descrição do site de equipe**, digite o **site do SharePoint para arquivos confidenciais**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-146">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="60ac7-147">Em **Configurações de privacidade**, escolha **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-147">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="60ac7-148">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-148">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="60ac7-149">Em seguida, configure a pasta de documentos do site da equipe SensitiveFiles para o rótulo de confidencial.</span><span class="sxs-lookup"><span data-stu-id="60ac7-149">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="60ac7-150">Na guia **SensitiveFiles** do seu navegador, clique em **documentos**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-150">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="60ac7-151">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-151">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="60ac7-152">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-152">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="60ac7-153">Em **Configurações se aplicam rótulo**, selecione **confidenciais** na caixa suspensa e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-153">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="60ac7-154">Em seguida, crie um novo documento no site SensitiveFiles e altere seu rótulo.</span><span class="sxs-lookup"><span data-stu-id="60ac7-154">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="60ac7-155">Na pasta de documentos, clique em **New > documento do Word**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-155">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="60ac7-p105">Digite um texto do documento em branco. Aguarde até que o texto seja salvo.</span><span class="sxs-lookup"><span data-stu-id="60ac7-p105">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="60ac7-158">Na barra de menus, clique em **Documentos compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-158">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="60ac7-159">Clique no ícone do Word ao lado do nome de arquivo **Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="60ac7-159">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="60ac7-160">No painel direito, na seção **Propriedades** , em **Aplicar rótulo de retenção**, observe que o documento teve o rótulo **confidenciais** automaticamente aplicado.</span><span class="sxs-lookup"><span data-stu-id="60ac7-160">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="60ac7-161">Clique em **Editar todos**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-161">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="60ac7-162">No painel **Document.docx** , em **Aplicar rótulo**, selecione o rótulo **Altamente confidenciais** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="60ac7-162">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="60ac7-163">Consulte a etapa de [classificação de Configure para seu ambiente](infoprotect-configure-classification.md) na fase de **proteção de informações** para obter informações e links para os rótulos de retenção do Office 365 em produção.</span><span class="sxs-lookup"><span data-stu-id="60ac7-163">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="60ac7-164">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="60ac7-164">Next step</span></span>

<span data-ttu-id="60ac7-165">Explore recursos adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) e recursos no seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="60ac7-165">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="60ac7-166">Confira também</span><span class="sxs-lookup"><span data-stu-id="60ac7-166">See also</span></span>

[<span data-ttu-id="60ac7-167">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="60ac7-167">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="60ac7-168">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="60ac7-168">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="60ac7-169">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="60ac7-169">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 