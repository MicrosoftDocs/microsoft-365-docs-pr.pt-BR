---
title: Classificação de dados para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para criar e usar rótulos de retenção do Office 365 em documentos no ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 66e06f9a89b102c131bc29af17c4564fabbab9b4
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072411"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="318dd-103">Classificação de dados para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="318dd-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="318dd-104">Com as instruções deste artigo, você configura a classificação de dados usando rótulos de retenção do Office 365 no ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="318dd-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="318dd-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="318dd-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="318dd-107">Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="318dd-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="318dd-108">Se você só quiser configurar rótulos de retenção do Office 365 de uma forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="318dd-108">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="318dd-109">Se você quiser configurar os rótulos de retenção do Office 365 em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="318dd-109">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="318dd-110">O teste dos rótulos de retenção do Office 365 não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="318dd-110">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="318dd-111">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="318dd-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="318dd-112">Fase 2: criar rótulos de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="318dd-112">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="318dd-113">Nesta fase, você cria os rótulos de retenção para os diferentes níveis de retenção para pastas de documentos do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="318dd-113">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="318dd-114">Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="318dd-114">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="318dd-115">Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="318dd-115">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="318dd-116">Clique em **Rótulos de retenção > Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="318dd-116">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="318dd-117">No painel **Atribuir nome ao seu rótulo** digite **Público interno** em **Atribuir nome ao seu rótulo**, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="318dd-117">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="318dd-118">No painel **descritores de plano de arquivo**, clique em **próximo**.</span><span class="sxs-lookup"><span data-stu-id="318dd-118">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="318dd-119">No painel **configurações de etiqueta**, se necessário, defina **retenção** para **no**e, em seguida, clique em **próximo**.</span><span class="sxs-lookup"><span data-stu-id="318dd-119">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="318dd-120">No painel **Revise suas configurações**, clique em **Criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="318dd-120">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="318dd-121">Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:</span><span class="sxs-lookup"><span data-stu-id="318dd-121">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="318dd-122">Private</span><span class="sxs-lookup"><span data-stu-id="318dd-122">Private</span></span>
    
  - <span data-ttu-id="318dd-123">Confidencial</span><span class="sxs-lookup"><span data-stu-id="318dd-123">Sensitive</span></span>
    
  - <span data-ttu-id="318dd-124">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="318dd-124">Highly Confidential</span></span>
  
9. <span data-ttu-id="318dd-125">No painel **Início > Rótulos**, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="318dd-125">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="318dd-126">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="318dd-126">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="318dd-127">No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="318dd-127">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="318dd-128">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="318dd-128">Click **Done**.</span></span>
    
13. <span data-ttu-id="318dd-129">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="318dd-129">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="318dd-130">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="318dd-130">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="318dd-131">No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="318dd-131">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="318dd-132">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="318dd-132">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="318dd-133">Observe que pode levar alguns minutos para que os rótulos de retenção sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="318dd-133">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="318dd-134">Fase 3: aplicar rótulos de retenção do Office 365 a documentos</span><span class="sxs-lookup"><span data-stu-id="318dd-134">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="318dd-135">Nesta fase, você descobre o comportamento de rótulo de retenção padrão para arquivos na pasta documentos de um site do SharePoint Online e altera manualmente o rótulo de retenção de um documento.</span><span class="sxs-lookup"><span data-stu-id="318dd-135">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="318dd-136">Primeiro, crie um site de equipe do SharePoint Online de nível confidencial:</span><span class="sxs-lookup"><span data-stu-id="318dd-136">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="318dd-137">Usando um navegador no computador local, entre no [Portal do Office 365](https://portal.office.com) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="318dd-137">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="318dd-138">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="318dd-138">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="318dd-139">Na nova guia **SharePoint** no navegador, clique em **criar site**.</span><span class="sxs-lookup"><span data-stu-id="318dd-139">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="318dd-140">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="318dd-140">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="318dd-141">Em **nome do site de equipe**, digite **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="318dd-141">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="318dd-142">Em **Descrição do site de equipe**, digite **site do SharePoint para arquivos confidenciais**.</span><span class="sxs-lookup"><span data-stu-id="318dd-142">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="318dd-143">Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="318dd-143">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="318dd-144">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="318dd-144">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="318dd-145">Em seguida, configure a pasta de documentos do site de equipe do SensitiveFiles para o rótulo de retenção confidencial.</span><span class="sxs-lookup"><span data-stu-id="318dd-145">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="318dd-146">Na guia **SensitiveFiles** do navegador, clique em **documentos**.</span><span class="sxs-lookup"><span data-stu-id="318dd-146">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="318dd-147">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="318dd-147">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="318dd-148">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="318dd-148">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="318dd-149">Em **Configurações – Aplicar rótulo**, selecione **confidencial** na caixa suspensa e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="318dd-149">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="318dd-150">Em seguida, crie um novo documento no site do SensitiveFiles e altere seu rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="318dd-150">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="318dd-151">Na pasta documentos, clique em **novo documento do Word do >**.</span><span class="sxs-lookup"><span data-stu-id="318dd-151">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="318dd-152">Digite algum texto no documento em branco.</span><span class="sxs-lookup"><span data-stu-id="318dd-152">Type some text in the blank document.</span></span> <span data-ttu-id="318dd-153">Aguarde o texto ser salvo.</span><span class="sxs-lookup"><span data-stu-id="318dd-153">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="318dd-154">Na barra de menus, clique em **documentos compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="318dd-154">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="318dd-155">Clique no ícone do Word ao lado do nome do arquivo **Document. docx** .</span><span class="sxs-lookup"><span data-stu-id="318dd-155">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="318dd-156">No painel direito, na seção **Propriedades** , em **aplicar rótulo de retenção**, observe que o documento teve o rótulo **confidencial** aplicado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="318dd-156">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="318dd-157">Clique em **Editar tudo**.</span><span class="sxs-lookup"><span data-stu-id="318dd-157">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="318dd-158">No painel **Document. docx** , em **aplicar rótulo**, selecione o rótulo **altamente confidencial** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="318dd-158">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="318dd-159">Consulte a etapa [Configurar a classificação para seu ambiente](infoprotect-configure-classification.md) na fase de **proteção de informações** para obter informações e links sobre como implantar rótulos de retenção do Office 365 em produção.</span><span class="sxs-lookup"><span data-stu-id="318dd-159">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="318dd-160">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="318dd-160">Next step</span></span>

<span data-ttu-id="318dd-161">Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="318dd-161">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="318dd-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="318dd-162">See also</span></span>

[<span data-ttu-id="318dd-163">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="318dd-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="318dd-164">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="318dd-164">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="318dd-165">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="318dd-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 