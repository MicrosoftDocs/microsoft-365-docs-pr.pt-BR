---
title: Classificação de dados do ambiente de teste do Microsoft 365 para empresas
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
description: Use este Guia de Laboratório de Teste para criar e usar rótulos de retenção em documentos em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487727"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="11f39-103">Classificação de dados do ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="11f39-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="11f39-104">*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e do Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="11f39-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="11f39-105">Este artigo descreve como configurar a classificação de dados usando rótulos de retenção no ambiente de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="11f39-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="11f39-106">A classificação de dados em seu ambiente de teste envolve três fases:</span><span class="sxs-lookup"><span data-stu-id="11f39-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="11f39-107">Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="11f39-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="11f39-108">Fase 2: Criar rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="11f39-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="11f39-109">Fase 3: Aplicar rótulos de retenção a documentos</span><span class="sxs-lookup"><span data-stu-id="11f39-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="11f39-111">Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.</span><span class="sxs-lookup"><span data-stu-id="11f39-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="11f39-112">Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="11f39-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="11f39-113">Se você só quiser configurar rótulos de retenção de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="11f39-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="11f39-114">Se você quiser configurar rótulos de retenção em uma empresa simulada, siga as instruções na [autenticação de passagem.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="11f39-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="11f39-115">O teste de rótulos de retenção não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="11f39-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="11f39-116">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação a um grupo e fazer testes com ele em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="11f39-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="11f39-117">Fase 2: Criar rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="11f39-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="11f39-118">Nesta fase, crie os rótulos de retenção para os diferentes níveis de retenção para pastas de documentos do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="11f39-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="11f39-119">Entre no centro [de segurança do Microsoft 365](https://security.microsoft.com/homepage) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="11f39-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="11f39-120">Na página **Home - guia de segurança do Microsoft 365** do navegador, selecione **rótulos de** Retenção de  >  **Classificação.**</span><span class="sxs-lookup"><span data-stu-id="11f39-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="11f39-121">Selecione **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="11f39-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="11f39-122">In the **Name your label** pane, enter Internal **Public** in Name **your label**, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="11f39-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="11f39-123">No painel **descritores de plano de** arquivo, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="11f39-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="11f39-124">No painel **de configurações de** Rótulo, se necessário, **de** definida Retenção **como** Em e, em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="11f39-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="11f39-125">No painel **Revisar suas configurações,** selecione **Criar o rótulo.**</span><span class="sxs-lookup"><span data-stu-id="11f39-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="11f39-126">Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:</span><span class="sxs-lookup"><span data-stu-id="11f39-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="11f39-127">Private</span><span class="sxs-lookup"><span data-stu-id="11f39-127">Private</span></span>
  - <span data-ttu-id="11f39-128">Confidencial</span><span class="sxs-lookup"><span data-stu-id="11f39-128">Sensitive</span></span>
  - <span data-ttu-id="11f39-129">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="11f39-129">Highly Confidential</span></span>
1. <span data-ttu-id="11f39-130">No painel **Rótulos de** retenção, selecione **Publicar rótulos.**</span><span class="sxs-lookup"><span data-stu-id="11f39-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="11f39-131">No painel **Escolher rótulos para publicar,** selecione **Escolher rótulos para publicar.**</span><span class="sxs-lookup"><span data-stu-id="11f39-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="11f39-132">No painel **Escolher rótulos,** selecione **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="11f39-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="11f39-133">Selecione **Adicionar** e, em seguida, **Terminar.**</span><span class="sxs-lookup"><span data-stu-id="11f39-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="11f39-134">On the **Choose labels to publish** pane, select **Next**.</span><span class="sxs-lookup"><span data-stu-id="11f39-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="11f39-135">No painel **Escolher locais,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="11f39-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="11f39-136">On the **Name your policy** pane, enter Example **organization** in **Name**, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="11f39-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="11f39-137">No painel **Revisar suas configurações,** selecione **Publicar rótulos.**</span><span class="sxs-lookup"><span data-stu-id="11f39-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="11f39-138">Pode levar alguns minutos para que os rótulos de retenção sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="11f39-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="11f39-139">Fase 3: Aplicar rótulos de retenção a documentos</span><span class="sxs-lookup"><span data-stu-id="11f39-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="11f39-140">Nesta fase, você descobre o comportamento de rótulo de retenção padrão para arquivos na pasta Documentos de um site do SharePoint Online e altera manualmente o rótulo de retenção de um documento.</span><span class="sxs-lookup"><span data-stu-id="11f39-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="11f39-141">Primeiro, crie um site de equipe do SharePoint Online de nível sensível:</span><span class="sxs-lookup"><span data-stu-id="11f39-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="11f39-142">Usando uma instância privada do navegador, entre no Centro de administração do [Microsoft 365](https://admin.microsoft.com) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="11f39-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="11f39-143">Na lista de blocos, selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="11f39-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="11f39-144">Na nova guia **Do SharePoint** no navegador, selecione **Criar site.**</span><span class="sxs-lookup"><span data-stu-id="11f39-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="11f39-145">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="11f39-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="11f39-146">Na caixa **Nome do site de** equipe, insira **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="11f39-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="11f39-147">Na caixa **de descrição do site de** equipe, insira o site do **SharePoint para arquivos confidenciais.**</span><span class="sxs-lookup"><span data-stu-id="11f39-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="11f39-148">Em **Configurações de privacidade**, selecione Privado - somente membros podem acessar este **site** e, em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="11f39-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="11f39-149">In the **Who do you want to add?** pane, select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="11f39-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="11f39-150">Em seguida, configure a pasta Documentos do site de equipe SensitiveFiles para o rótulo de retenção Sensitive.</span><span class="sxs-lookup"><span data-stu-id="11f39-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="11f39-151">Na guia **SensitiveFiles** do navegador, selecione **Documentos.**</span><span class="sxs-lookup"><span data-stu-id="11f39-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="11f39-152">Selecione o **ícone Configurações** e, em seguida, selecione **Configurações de biblioteca.**</span><span class="sxs-lookup"><span data-stu-id="11f39-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="11f39-153">Em **Permissões e Gerenciamento,** selecione **Aplicar rótulo a itens nesta lista ou biblioteca.**</span><span class="sxs-lookup"><span data-stu-id="11f39-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="11f39-154">Se essa opção não aparecer, seus rótulos de retenção ainda não foram publicados.</span><span class="sxs-lookup"><span data-stu-id="11f39-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="11f39-155">Tente esta etapa posteriormente.</span><span class="sxs-lookup"><span data-stu-id="11f39-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="11f39-156">Em **Configurações – Aplicar Rótulo**, selecione **Sensitive** na caixa de lista drop-down e, em seguida, **selecione Salvar**.</span><span class="sxs-lookup"><span data-stu-id="11f39-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="11f39-157">Em seguida, crie um novo documento no site SensitiveFiles e altere seu rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="11f39-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="11f39-158">Na pasta documentos, selecione **Novo documento**  >  **do Word.**</span><span class="sxs-lookup"><span data-stu-id="11f39-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="11f39-159">Insira algum texto no documento em branco.</span><span class="sxs-lookup"><span data-stu-id="11f39-159">Enter some text in the blank document.</span></span> <span data-ttu-id="11f39-160">Aguarde até que o texto seja salvo.</span><span class="sxs-lookup"><span data-stu-id="11f39-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="11f39-161">Na barra de menus, selecione **Documentos Compartilhados.**</span><span class="sxs-lookup"><span data-stu-id="11f39-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="11f39-162">Ao lado do **Document.docx** nome do arquivo, selecione as reellipses verticais e selecione **Detalhes.**</span><span class="sxs-lookup"><span data-stu-id="11f39-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="11f39-163">No painel direito, na  seção Propriedades, em Aplicar rótulo de **retenção,** observe que o documento teve o rótulo de retenção Sensitive aplicado automaticamente. </span><span class="sxs-lookup"><span data-stu-id="11f39-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="11f39-164">Clique em **Editar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="11f39-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="11f39-165">No painel **Document.docx,** em Aplicar rótulo de **retenção,** selecione o rótulo Altamente **Confidencial** e selecione **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="11f39-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="11f39-166">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="11f39-166">Next step</span></span>

<span data-ttu-id="11f39-167">Explore recursos [e funcionalidades adicionais](m365-enterprise-test-lab-guides.md#information-protection) de proteção de informações em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="11f39-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="11f39-168">Confira também</span><span class="sxs-lookup"><span data-stu-id="11f39-168">See also</span></span>

[<span data-ttu-id="11f39-169">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="11f39-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="11f39-170">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="11f39-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="11f39-171">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="11f39-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
