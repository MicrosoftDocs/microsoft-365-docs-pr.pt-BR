---
title: Classificação de dados para o ambiente de teste do Microsoft 365 for Enterprise
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
description: Use este guia de laboratório de teste para criar e usar rótulos de retenção em documentos no ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487727"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="15b6a-103">Classificação de dados para o ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="15b6a-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="15b6a-104">*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*</span><span class="sxs-lookup"><span data-stu-id="15b6a-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="15b6a-105">Este artigo descreve como configurar a classificação de dados usando rótulos de retenção no ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="15b6a-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="15b6a-106">Classificar dados em seu ambiente de teste envolve três fases:</span><span class="sxs-lookup"><span data-stu-id="15b6a-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="15b6a-107">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="15b6a-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="15b6a-108">Fase 2: criar rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="15b6a-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="15b6a-109">Fase 3: aplicar rótulos de retenção a documentos</span><span class="sxs-lookup"><span data-stu-id="15b6a-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="15b6a-111">Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="15b6a-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="15b6a-112">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="15b6a-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="15b6a-113">Se você só quiser configurar os rótulos de retenção de uma forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="15b6a-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="15b6a-114">Se você quiser configurar os rótulos de retenção em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="15b6a-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="15b6a-115">O teste de rótulos de retenção não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="15b6a-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="15b6a-116">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="15b6a-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="15b6a-117">Fase 2: criar rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="15b6a-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="15b6a-118">Nesta fase, crie os rótulos de retenção para os diferentes níveis de retenção para as pastas de documentos do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="15b6a-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="15b6a-119">Entre na central de [segurança do Microsoft 365](https://security.microsoft.com/homepage) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="15b6a-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="15b6a-120">Na guia **segurança doméstica-Microsoft 365** do navegador, selecione rótulos de **Classification**  >  **retenção**de classificação.</span><span class="sxs-lookup"><span data-stu-id="15b6a-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="15b6a-121">Selecione **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="15b6a-122">No painel **nomear seu rótulo** , digite **público interno** em **nome seu rótulo**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="15b6a-123">No painel de **descritores de plano de arquivo** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="15b6a-124">No painel **configurações do rótulo** , se necessário, defina **retenção** como **ativado**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="15b6a-125">No painel **examinar suas configurações** , selecione **criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="15b6a-126">Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:</span><span class="sxs-lookup"><span data-stu-id="15b6a-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="15b6a-127">Private</span><span class="sxs-lookup"><span data-stu-id="15b6a-127">Private</span></span>
  - <span data-ttu-id="15b6a-128">Confidencial</span><span class="sxs-lookup"><span data-stu-id="15b6a-128">Sensitive</span></span>
  - <span data-ttu-id="15b6a-129">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="15b6a-129">Highly Confidential</span></span>
1. <span data-ttu-id="15b6a-130">No painel **Rótulos de retenção** , selecione **publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="15b6a-131">No painel **escolher rótulos para publicar** , selecione **escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="15b6a-132">No painel **escolher rótulos** , selecione **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="15b6a-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="15b6a-133">Selecione **Adicionar**e, em seguida, selecione **concluído**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="15b6a-134">No painel **escolher rótulos para publicar** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="15b6a-135">No painel **escolher locais** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="15b6a-136">No painel **nomear sua política** , digite **organização de exemplo** em **nome**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="15b6a-137">No painel **rever suas configurações** , selecione **publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="15b6a-138">Pode levar alguns minutos para que os rótulos de retenção sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="15b6a-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="15b6a-139">Fase 3: aplicar rótulos de retenção a documentos</span><span class="sxs-lookup"><span data-stu-id="15b6a-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="15b6a-140">Nesta fase, você descobre o comportamento de rótulo de retenção padrão para arquivos na pasta documentos de um site do SharePoint Online e altera manualmente o rótulo de retenção de um documento.</span><span class="sxs-lookup"><span data-stu-id="15b6a-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="15b6a-141">Primeiro, crie um site de equipe do SharePoint Online de nível confidencial:</span><span class="sxs-lookup"><span data-stu-id="15b6a-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="15b6a-142">Usando uma instância privada do navegador, entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="15b6a-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="15b6a-143">Na lista de blocos, selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="15b6a-144">Na nova guia **SharePoint** no navegador, selecione **criar site**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="15b6a-145">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="15b6a-146">Na caixa **nome do site de equipe** , digite **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="15b6a-147">Na caixa **Descrição do site de equipe** , digite **site do SharePoint para arquivos confidenciais**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="15b6a-148">Em **configurações de privacidade**, selecione **membros somente privados podem acessar esse site**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="15b6a-149">No painel **quem você deseja adicionar?** , selecione **concluir**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="15b6a-150">Em seguida, configure a pasta de documentos do site de equipe do SensitiveFiles para o rótulo de retenção confidencial.</span><span class="sxs-lookup"><span data-stu-id="15b6a-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="15b6a-151">Na guia **SensitiveFiles** do navegador, selecione **documentos**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="15b6a-152">Selecione o ícone **configurações** e, em seguida, selecione **configurações da biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="15b6a-153">Em **permissões e gerenciamento**, selecione **aplicar rótulo a itens nesta lista ou biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="15b6a-154">Se essa opção não for exibida, seus rótulos de retenção ainda não foram publicados.</span><span class="sxs-lookup"><span data-stu-id="15b6a-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="15b6a-155">Tente esta etapa mais tarde.</span><span class="sxs-lookup"><span data-stu-id="15b6a-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="15b6a-156">Em **Configurações – Aplicar rótulo**, selecione **confidencial** na caixa suspensa e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="15b6a-157">Em seguida, crie um novo documento no site do SensitiveFiles e altere seu rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="15b6a-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="15b6a-158">Na pasta documentos, selecione **novo**  >  **documento do Word**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="15b6a-159">Insira algum texto no documento em branco.</span><span class="sxs-lookup"><span data-stu-id="15b6a-159">Enter some text in the blank document.</span></span> <span data-ttu-id="15b6a-160">Aguarde o texto ser salvo.</span><span class="sxs-lookup"><span data-stu-id="15b6a-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="15b6a-161">Na barra de menus, selecione **documentos compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="15b6a-162">Ao lado do nome do arquivo **Document.docx** , selecione as reticências verticais e, em seguida, selecione **detalhes**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="15b6a-163">No painel direito, na seção **Propriedades** , em **aplicar rótulo de retenção**, observe que o rótulo de retenção **confidencial** foi aplicado automaticamente ao documento.</span><span class="sxs-lookup"><span data-stu-id="15b6a-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="15b6a-164">Clique em **Editar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="15b6a-165">No painel **Document.docx** , em **aplicar rótulo de retenção**, selecione o rótulo **altamente confidencial** e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="15b6a-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="15b6a-166">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="15b6a-166">Next step</span></span>

<span data-ttu-id="15b6a-167">Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="15b6a-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="15b6a-168">Confira também</span><span class="sxs-lookup"><span data-stu-id="15b6a-168">See also</span></span>

[<span data-ttu-id="15b6a-169">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="15b6a-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="15b6a-170">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="15b6a-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="15b6a-171">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="15b6a-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
