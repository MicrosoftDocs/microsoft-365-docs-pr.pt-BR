---
title: Classificação de dados para seu ambiente de teste do Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para criar e usar rótulos de retenção do Office 365 em documentos no ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 6534eff67e9c91423eb6f81415cb3ef2e965dcc1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067988"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a36e2-103">Classificação de dados para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a36e2-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a36e2-104">*Este Guia de Laboratório de Testes pode ser usado para ambientes de teste corporativo do Microsoft 365 Enterprise e do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="a36e2-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a36e2-105">Com as instruções deste artigo, você configura a classificação de dados usando rótulos de retenção do Office 365 no ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a36e2-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a36e2-107">Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a36e2-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a36e2-108">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a36e2-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a36e2-109">Se você só quiser configurar rótulos de retenção do Office 365 de uma forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a36e2-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a36e2-110">Se você quiser configurar os rótulos de retenção do Office 365 em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a36e2-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a36e2-111">O teste dos rótulos de retenção do Office 365 não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a36e2-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a36e2-112">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="a36e2-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="a36e2-113">Fase 2: criar rótulos de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="a36e2-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="a36e2-114">Nesta fase, você cria os rótulos de retenção para os diferentes níveis de retenção para pastas de documentos do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a36e2-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="a36e2-115">Entre na central de [segurança do Microsoft 365](https://security.microsoft.com/homepage) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a36e2-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="a36e2-116">Na guia **segurança doméstica-Microsoft 365** do navegador, clique em **classificação > rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="a36e2-117">Clique em **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="a36e2-118">No painel **nomear seu rótulo** , digite **público interno** em **nome seu rótulo**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="a36e2-119">No painel **descritores de plano de arquivo** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="a36e2-120">No painel **configurações do rótulo** , se necessário, defina **retenção** como **ativado**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a36e2-121">No painel **examinar as configurações** , clique em **criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="a36e2-122">Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:</span><span class="sxs-lookup"><span data-stu-id="a36e2-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="a36e2-123">Private</span><span class="sxs-lookup"><span data-stu-id="a36e2-123">Private</span></span>
    
  - <span data-ttu-id="a36e2-124">Confidencial</span><span class="sxs-lookup"><span data-stu-id="a36e2-124">Sensitive</span></span>
    
  - <span data-ttu-id="a36e2-125">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="a36e2-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="a36e2-126">No painel **Rótulos de retenção** , clique em **publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="a36e2-127">No painel **escolher rótulos para publicar** , clique em **escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="a36e2-128">No painel **escolher rótulos** , clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="a36e2-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="a36e2-129">Clique em **Adicionar**e em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="a36e2-130">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="a36e2-131">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="a36e2-132">No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="a36e2-133">No painel **revisar as configurações** , clique em **publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="a36e2-134">Observe que pode levar alguns minutos para que os rótulos de retenção sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="a36e2-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="a36e2-135">Fase 3: aplicar rótulos de retenção do Office 365 a documentos</span><span class="sxs-lookup"><span data-stu-id="a36e2-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="a36e2-136">Nesta fase, você descobre o comportamento de rótulo de retenção padrão para arquivos na pasta documentos de um site do SharePoint Online e altera manualmente o rótulo de retenção de um documento.</span><span class="sxs-lookup"><span data-stu-id="a36e2-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="a36e2-137">Primeiro, crie um site de equipe do SharePoint Online de nível confidencial:</span><span class="sxs-lookup"><span data-stu-id="a36e2-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="a36e2-138">Usando uma instância privada do navegador, entre no [portal do Office 365](https://portal.office.com) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a36e2-138">Using a private instance of your browser, sign in to the [Office 365 portal](https://portal.office.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="a36e2-139">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="a36e2-140">Na nova guia **SharePoint** no navegador, clique em **criar site**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="a36e2-141">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="a36e2-142">Em **nome do site de equipe**, digite **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="a36e2-143">Em **Descrição do site de equipe**, digite **site do SharePoint para arquivos confidenciais**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="a36e2-144">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a36e2-145">No painel **quem você deseja adicionar?** , clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="a36e2-146">Em seguida, configure a pasta de documentos do site de equipe do SensitiveFiles para o rótulo de retenção confidencial.</span><span class="sxs-lookup"><span data-stu-id="a36e2-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="a36e2-147">Na guia **SensitiveFiles** do navegador, clique em **documentos**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="a36e2-148">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="a36e2-149">Em **permissões e gerenciamento**, clique em **aplicar rótulo aos itens nesta lista ou biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="a36e2-150">Se essa opção não aparecer, seus rótulos de retenção ainda não serão publicados.</span><span class="sxs-lookup"><span data-stu-id="a36e2-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="a36e2-151">Tente esta etapa mais tarde.</span><span class="sxs-lookup"><span data-stu-id="a36e2-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="a36e2-152">Em **Configurações – Aplicar rótulo**, selecione **confidencial** na caixa suspensa e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="a36e2-153">Em seguida, crie um novo documento no site do SensitiveFiles e altere seu rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="a36e2-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="a36e2-154">Na pasta documentos, clique em **novo documento do Word >**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="a36e2-155">Digite algum texto no documento em branco.</span><span class="sxs-lookup"><span data-stu-id="a36e2-155">Type some text in the blank document.</span></span> <span data-ttu-id="a36e2-156">Aguarde o texto ser salvo.</span><span class="sxs-lookup"><span data-stu-id="a36e2-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="a36e2-157">Na barra de menus, clique em **documentos compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="a36e2-158">Clique nas reticências verticais ao lado do nome de arquivo **Document. docx** e, em seguida, clique em **detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="a36e2-159">No painel direito, na seção **Propriedades** , em **aplicar rótulo de retenção**, observe que o documento teve o rótulo de retenção **confidencial** aplicado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a36e2-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="a36e2-160">Clique em **Editar tudo**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="a36e2-161">No painel **Document. docx** , em **aplicar rótulo de retenção**, selecione o rótulo **altamente confidencial** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="a36e2-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="a36e2-162">Consulte a etapa [Configurar a classificação para seu ambiente](infoprotect-configure-classification.md) na fase de **proteção de informações** para obter informações e links sobre como implantar rótulos de retenção do Office 365 em produção.</span><span class="sxs-lookup"><span data-stu-id="a36e2-162">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a36e2-163">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a36e2-163">Next step</span></span>

<span data-ttu-id="a36e2-164">Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a36e2-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a36e2-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="a36e2-165">See also</span></span>

[<span data-ttu-id="a36e2-166">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a36e2-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a36e2-167">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a36e2-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a36e2-168">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a36e2-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
