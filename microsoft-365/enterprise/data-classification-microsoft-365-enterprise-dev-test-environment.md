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
ms.openlocfilehash: e0186bcfc786356b34aff45b1b1e67f54dd40001
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672657"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1564f-103">Classificação de dados para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1564f-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1564f-104">*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 Enterprise e do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="1564f-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="1564f-105">Com as instruções deste artigo, você configura a classificação de dados usando rótulos de retenção do Office 365 no ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1564f-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="1564f-107">Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1564f-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1564f-108">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1564f-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1564f-109">Se você só quiser configurar rótulos de retenção do Office 365 de uma forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1564f-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1564f-110">Se você quiser configurar os rótulos de retenção do Office 365 em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1564f-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1564f-111">O teste dos rótulos de retenção do Office 365 não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1564f-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1564f-112">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="1564f-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="1564f-113">Fase 2: criar rótulos de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="1564f-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="1564f-114">Nesta fase, você cria os rótulos de retenção para os diferentes níveis de retenção para pastas de documentos do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1564f-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="1564f-115">Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1564f-115">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="1564f-116">Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="1564f-116">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="1564f-117">Clique em **Rótulos de retenção > Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="1564f-117">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="1564f-118">No painel **Atribuir nome ao seu rótulo** digite **Público interno** em **Atribuir nome ao seu rótulo**, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1564f-118">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="1564f-119">No painel **descritores de plano de arquivo**, clique em **próximo**.</span><span class="sxs-lookup"><span data-stu-id="1564f-119">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="1564f-120">No painel **configurações de etiqueta**, se necessário, defina **retenção** para **no**e, em seguida, clique em **próximo**.</span><span class="sxs-lookup"><span data-stu-id="1564f-120">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="1564f-121">No painel **Revise suas configurações**, clique em **Criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="1564f-121">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="1564f-122">Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:</span><span class="sxs-lookup"><span data-stu-id="1564f-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="1564f-123">Private</span><span class="sxs-lookup"><span data-stu-id="1564f-123">Private</span></span>
    
  - <span data-ttu-id="1564f-124">Confidencial</span><span class="sxs-lookup"><span data-stu-id="1564f-124">Sensitive</span></span>
    
  - <span data-ttu-id="1564f-125">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="1564f-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="1564f-126">No painel **Início > Rótulos**, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="1564f-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="1564f-127">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="1564f-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="1564f-128">No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="1564f-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="1564f-129">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="1564f-129">Click **Done**.</span></span>
    
13. <span data-ttu-id="1564f-130">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1564f-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="1564f-131">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1564f-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="1564f-132">No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1564f-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="1564f-133">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1564f-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="1564f-134">Observe que pode levar alguns minutos para que os rótulos de retenção sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="1564f-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="1564f-135">Fase 3: aplicar rótulos de retenção do Office 365 a documentos</span><span class="sxs-lookup"><span data-stu-id="1564f-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="1564f-136">Nesta fase, você descobre o comportamento de rótulo de retenção padrão para arquivos na pasta documentos de um site do SharePoint Online e altera manualmente o rótulo de retenção de um documento.</span><span class="sxs-lookup"><span data-stu-id="1564f-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="1564f-137">Primeiro, crie um site de equipe do SharePoint Online de nível confidencial:</span><span class="sxs-lookup"><span data-stu-id="1564f-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="1564f-138">Usando um navegador no computador local, entre no [Portal do Office 365](https://portal.office.com) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1564f-138">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="1564f-139">Na lista de blocos, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1564f-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="1564f-140">Na nova guia **SharePoint** no navegador, clique em **criar site**.</span><span class="sxs-lookup"><span data-stu-id="1564f-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="1564f-141">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="1564f-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="1564f-142">Em **nome do site de equipe**, digite **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="1564f-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="1564f-143">Em **Descrição do site de equipe**, digite **site do SharePoint para arquivos confidenciais**.</span><span class="sxs-lookup"><span data-stu-id="1564f-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="1564f-144">Em **Configurações de privacidade**, escolha **Privado – somente membros podem acessar esse site** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1564f-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="1564f-145">No painel **Quem você deseja adicionar?**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="1564f-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="1564f-146">Em seguida, configure a pasta de documentos do site de equipe do SensitiveFiles para o rótulo de retenção confidencial.</span><span class="sxs-lookup"><span data-stu-id="1564f-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="1564f-147">Na guia **SensitiveFiles** do navegador, clique em **documentos**.</span><span class="sxs-lookup"><span data-stu-id="1564f-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="1564f-148">Clique no ícone de configurações e em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="1564f-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="1564f-149">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="1564f-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="1564f-150">Em **Configurações – Aplicar rótulo**, selecione **confidencial** na caixa suspensa e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1564f-150">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="1564f-151">Em seguida, crie um novo documento no site do SensitiveFiles e altere seu rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="1564f-151">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="1564f-152">Na pasta documentos, clique em **novo documento do Word >**.</span><span class="sxs-lookup"><span data-stu-id="1564f-152">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="1564f-153">Digite algum texto no documento em branco.</span><span class="sxs-lookup"><span data-stu-id="1564f-153">Type some text in the blank document.</span></span> <span data-ttu-id="1564f-154">Aguarde o texto ser salvo.</span><span class="sxs-lookup"><span data-stu-id="1564f-154">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="1564f-155">Na barra de menus, clique em **documentos compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="1564f-155">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="1564f-156">Clique no ícone do Word ao lado do nome do arquivo **Document. docx** .</span><span class="sxs-lookup"><span data-stu-id="1564f-156">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="1564f-157">No painel direito, na seção **Propriedades** , em **aplicar rótulo de retenção**, observe que o documento teve o rótulo **confidencial** aplicado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1564f-157">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="1564f-158">Clique em **Editar tudo**.</span><span class="sxs-lookup"><span data-stu-id="1564f-158">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="1564f-159">No painel **Document. docx** , em **aplicar rótulo**, selecione o rótulo **altamente confidencial** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1564f-159">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="1564f-160">Consulte a etapa [Configurar a classificação para seu ambiente](infoprotect-configure-classification.md) na fase de **proteção de informações** para obter informações e links sobre como implantar rótulos de retenção do Office 365 em produção.</span><span class="sxs-lookup"><span data-stu-id="1564f-160">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="1564f-161">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1564f-161">Next step</span></span>

<span data-ttu-id="1564f-162">Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="1564f-162">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1564f-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="1564f-163">See also</span></span>

[<span data-ttu-id="1564f-164">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1564f-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1564f-165">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1564f-165">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1564f-166">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1564f-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 