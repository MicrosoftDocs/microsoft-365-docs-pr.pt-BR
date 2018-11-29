---
title: Ambiente de teste de classificação de dados para a sua empresa de 365 da Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para criar e usar o Office 365 rótulos em documentos em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865293"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="dbb66-103">Ambiente de teste de classificação de dados para a sua empresa de 365 da Microsoft</span><span class="sxs-lookup"><span data-stu-id="dbb66-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="dbb66-104">Com as instruções deste artigo, você deve configurar a classificação de dados usando o Office 365 rótulos em seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="dbb66-104">With the instructions in this article, you configure data classification using Office 365 labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="dbb66-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="dbb66-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="dbb66-107">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dbb66-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="dbb66-108">Se você deseja configurar rótulos de Office 365 de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="dbb66-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="dbb66-109">Se você deseja configurar rótulos do Office 365 em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="dbb66-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dbb66-p101">Teste o Office 365 rótulos não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="dbb66-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="dbb66-112">Fase 2: Criar rótulos do Office 365</span><span class="sxs-lookup"><span data-stu-id="dbb66-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="dbb66-113">Nesta fase, você deve criar os rótulos para os diferentes níveis de segurança para as pastas de documentos do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dbb66-113">In this phase, you create the labels for the different levels of security for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="dbb66-p102">Se necessário, use uma instância particular do seu navegador da Internet e entrar no portal do Office 365 com sua conta de administrador global. Para obter ajuda, consulte [Where entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="dbb66-p102">If needed, use a private instance of your Internet browser and sign in to the Office 365 portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="dbb66-116">Na guia **Microsoft Office Home**, clique no bloco **Administração**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="dbb66-117">Na nova guia **Centro de Administração do Office** do navegador, clique em **Centros de Administração > Segurança&amp; e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="dbb66-118">Na nova guia **Início – Segurança &amp;e Conformidade** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-118">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="dbb66-119">No painel **Início > Rótulos**, clique em **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-119">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="dbb66-120">No painel **Atribuir nome ao seu rótulo**, digite **Público interno** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-120">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="dbb66-121">No painel **Configurações de rótulo**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-121">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="dbb66-122">No painel **Examine as configurações**, clique em **Criar este rótulo** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-122">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="dbb66-123">Repita as etapas de 5 a 8 para os rótulos adicionais:</span><span class="sxs-lookup"><span data-stu-id="dbb66-123">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="dbb66-124">Private</span><span class="sxs-lookup"><span data-stu-id="dbb66-124">Private</span></span>
    
  - <span data-ttu-id="dbb66-125">Confidencial</span><span class="sxs-lookup"><span data-stu-id="dbb66-125">Sensitive</span></span>
    
  - <span data-ttu-id="dbb66-126">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="dbb66-126">Highly Confidential</span></span>
    
10. <span data-ttu-id="dbb66-127">No painel **Início > Rótulos**, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-127">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="dbb66-128">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-128">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="dbb66-129">No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="dbb66-129">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="dbb66-130">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-130">Click **Done**.</span></span>
    
14. <span data-ttu-id="dbb66-131">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-131">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="dbb66-132">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-132">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="dbb66-133">No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-133">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="dbb66-134">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-134">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="dbb66-135">Observe que poderá levar alguns minutos para que os rótulos sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="dbb66-135">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-labels-to-documents"></a><span data-ttu-id="dbb66-136">Fase 3: Aplicar rótulos do Office 365 a documentos</span><span class="sxs-lookup"><span data-stu-id="dbb66-136">Phase 3: Apply Office 365 labels to documents</span></span>

<span data-ttu-id="dbb66-137">Nesta fase, você pode descobrir o comportamento padrão de rótulo para arquivos na pasta de documentos de um site do SharePoint Online e altera manualmente o rótulo de um documento.</span><span class="sxs-lookup"><span data-stu-id="dbb66-137">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="dbb66-138">Primeiro, crie um site de equipe do SharePoint Online confidenciais nível:</span><span class="sxs-lookup"><span data-stu-id="dbb66-138">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="dbb66-p103">Usando um navegador no computador local, entre no Portal do Office 365 usando sua conta de administrador global. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="dbb66-p103">Using a browser on your local computer, sign in to the Office 365 portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="dbb66-141">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-141">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="dbb66-142">Na guia **SharePoint** de novo no seu navegador, clique em **Criar site**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-142">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="dbb66-143">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-143">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="dbb66-144">Em **nome do site de equipe**, digite **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-144">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="dbb66-145">Na **Descrição do site de equipe**, digite o **site do SharePoint para arquivos confidenciais**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-145">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="dbb66-146">Em **Configurações de privacidade**, escolha **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-146">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="dbb66-147">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-147">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="dbb66-148">Em seguida, configure a pasta de documentos do site da equipe SensitiveFiles para o rótulo de confidencial.</span><span class="sxs-lookup"><span data-stu-id="dbb66-148">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="dbb66-149">Na guia **SensitiveFiles** do seu navegador, clique em **documentos**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-149">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="dbb66-150">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-150">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="dbb66-151">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-151">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="dbb66-152">Em **Configurações se aplicam rótulo**, selecione **confidenciais** na caixa suspensa e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="dbb66-153">Em seguida, crie um novo documento no site SensitiveFiles e altere seu rótulo.</span><span class="sxs-lookup"><span data-stu-id="dbb66-153">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="dbb66-154">Na pasta de documentos, clique em **New > documento do Word**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="dbb66-p104">Digite um texto do documento em branco. Aguarde até que o texto seja salvo.</span><span class="sxs-lookup"><span data-stu-id="dbb66-p104">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="dbb66-157">Na barra de menus, clique em **Documentos compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="dbb66-158">Clique no ícone do Word ao lado do nome de arquivo **Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="dbb66-158">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="dbb66-159">No painel direito, na seção **Propriedades** , em **Aplicar rótulo**, observe que o documento teve o rótulo **confidenciais** automaticamente aplicado.</span><span class="sxs-lookup"><span data-stu-id="dbb66-159">In the right-hand pane, in the **Properties** section, under **Apply label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="dbb66-160">Clique em **Editar todos**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="dbb66-161">No painel **Document.docx** , em **Aplicar rótulo**, selecione o rótulo **Altamente confidenciais** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dbb66-161">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="dbb66-162">Consulte a etapa de [classificação de Configure para seu ambiente](data-classification-microsoft-365-enterprise-dev-test-environment.md) na fase de **proteção de informações** para obter informações e links para os rótulos do Office 365 em produção.</span><span class="sxs-lookup"><span data-stu-id="dbb66-162">See the [Configure classification for your environment](data-classification-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to Office 365 labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="dbb66-163">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="dbb66-163">Next step</span></span>

<span data-ttu-id="dbb66-164">Explore recursos adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) e recursos no seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="dbb66-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbb66-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="dbb66-165">See also</span></span>

[<span data-ttu-id="dbb66-166">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dbb66-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="dbb66-167">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dbb66-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="dbb66-168">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dbb66-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 