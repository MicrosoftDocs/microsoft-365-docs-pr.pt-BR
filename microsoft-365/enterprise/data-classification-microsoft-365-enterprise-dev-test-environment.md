---
title: Classificação de dados para seu ambiente de teste do Microsoft 365 para empresas
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
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919183"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="db7a2-103">Classificação de dados para seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="db7a2-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="db7a2-104">*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="db7a2-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="db7a2-105">Este artigo descreve como configurar a classificação de dados usando rótulos de retenção em seu ambiente de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="db7a2-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="db7a2-106">A classificação de dados em seu ambiente de teste envolve três fases:</span><span class="sxs-lookup"><span data-stu-id="db7a2-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="db7a2-107">Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="db7a2-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="db7a2-108">Fase 2: Criar rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="db7a2-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="db7a2-109">Fase 3: aplicar rótulos de retenção a documentos</span><span class="sxs-lookup"><span data-stu-id="db7a2-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="db7a2-111">Para um mapa visual de todos os artigos na pilha guia de laboratório de teste do Microsoft 365 para empresas, vá para [o Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="db7a2-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="db7a2-112">Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="db7a2-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="db7a2-113">Se você deseja apenas configurar rótulos de retenção de maneira leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="db7a2-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="db7a2-114">Se você quiser configurar rótulos de retenção em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="db7a2-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="db7a2-115">Os rótulos de retenção de teste não exigem o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="db7a2-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="db7a2-116">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação ao grupo e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="db7a2-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="db7a2-117">Fase 2: Criar rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="db7a2-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="db7a2-118">Nesta fase, crie os rótulos de retenção para os diferentes níveis de retenção para pastas de documentos do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="db7a2-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="db7a2-119">Entre no Centro de segurança do [Microsoft 365](https://security.microsoft.com/homepage) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="db7a2-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="db7a2-120">Na guia Home - Segurança do **Microsoft 365** do navegador, selecione **Rótulos de**  >  **Retenção de Classificação.**</span><span class="sxs-lookup"><span data-stu-id="db7a2-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="db7a2-121">Selecione **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="db7a2-122">No painel **Nomear seu rótulo,** insira **Público Interno** em **Nome do** rótulo e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="db7a2-123">No painel **Descritores de plano de** arquivo, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="db7a2-124">No painel **Configurações de** rótulo, se necessário, desem conjunto **Retenção** como **Em** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="db7a2-125">No painel **Revisar suas configurações,** selecione **Criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="db7a2-126">Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:</span><span class="sxs-lookup"><span data-stu-id="db7a2-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="db7a2-127">Private</span><span class="sxs-lookup"><span data-stu-id="db7a2-127">Private</span></span>
  - <span data-ttu-id="db7a2-128">Confidencial</span><span class="sxs-lookup"><span data-stu-id="db7a2-128">Sensitive</span></span>
  - <span data-ttu-id="db7a2-129">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="db7a2-129">Highly Confidential</span></span>
1. <span data-ttu-id="db7a2-130">No painel **Rótulos de retenção,** selecione **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="db7a2-131">No painel **Escolher rótulos para publicar,** selecione **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="db7a2-132">No painel **Escolher rótulos,** selecione **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="db7a2-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="db7a2-133">Selecione **Adicionar** e, em seguida, selecione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="db7a2-134">No painel **Escolher rótulos para publicar,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="db7a2-135">No painel **Escolher locais,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="db7a2-136">No painel **Nomear sua política,** digite **Exemplo de organização** em **Nome** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="db7a2-137">No painel **Revisar suas configurações,** selecione **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="db7a2-138">Pode levar alguns minutos para que os rótulos de retenção sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="db7a2-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="db7a2-139">Fase 3: aplicar rótulos de retenção a documentos</span><span class="sxs-lookup"><span data-stu-id="db7a2-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="db7a2-140">Nesta fase, você descobre o comportamento padrão do rótulo de retenção para arquivos na pasta Documentos de um site do SharePoint Online e altera manualmente o rótulo de retenção de um documento.</span><span class="sxs-lookup"><span data-stu-id="db7a2-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="db7a2-141">Primeiro, crie um site de equipe do SharePoint Online de nível sensível:</span><span class="sxs-lookup"><span data-stu-id="db7a2-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="db7a2-142">Usando uma instância privada do navegador, entre no Centro de administração do [Microsoft 365](https://admin.microsoft.com) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="db7a2-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="db7a2-143">Na lista de blocos, selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="db7a2-144">Na nova guia **SharePoint** em seu navegador, selecione **Criar site**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="db7a2-145">Na página **Criar um site**, clique em **Site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="db7a2-146">Na caixa **Nome do site de** equipe, digite **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="db7a2-147">Na caixa **Descrição do site de** equipe, insira **o site do SharePoint para arquivos confidenciais**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="db7a2-148">Em **Configurações de Privacidade**, selecione Privado - somente membros podem acessar este **site** e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="db7a2-149">No painel **Quem você deseja adicionar?** selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="db7a2-150">Em seguida, configure a pasta Documentos do site de equipe SensitiveFiles para o rótulo de retenção Sensitive.</span><span class="sxs-lookup"><span data-stu-id="db7a2-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="db7a2-151">Na guia **SensitiveFiles** do navegador, selecione **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="db7a2-152">Selecione o **ícone Configurações** e, em seguida, selecione **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="db7a2-153">Em **Permissões e Gerenciamento,** selecione **Aplicar rótulo a itens nesta lista ou biblioteca.**</span><span class="sxs-lookup"><span data-stu-id="db7a2-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="db7a2-154">Se essa opção não aparecer, seus rótulos de retenção ainda não foram publicados.</span><span class="sxs-lookup"><span data-stu-id="db7a2-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="db7a2-155">Tente esta etapa posteriormente.</span><span class="sxs-lookup"><span data-stu-id="db7a2-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="db7a2-156">Em **Configurações-Aplicar Rótulo,** selecione **Confidenciais** na caixa de menu drop-down e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="db7a2-157">Em seguida, crie um novo documento no site SensitiveFiles e altere seu rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="db7a2-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="db7a2-158">Na pasta documentos, selecione **Novo documento**  >  **do Word**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="db7a2-159">Insira algum texto no documento em branco.</span><span class="sxs-lookup"><span data-stu-id="db7a2-159">Enter some text in the blank document.</span></span> <span data-ttu-id="db7a2-160">Aguarde até que o texto seja salvo.</span><span class="sxs-lookup"><span data-stu-id="db7a2-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="db7a2-161">Na barra de menus, selecione **Documentos Compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="db7a2-162">Ao lado do **nomeDocument.docx** arquivo, selecione a releição vertical e selecione **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="db7a2-163">No painel direito, na seção **Propriedades,** em **Aplicar** rótulo de retenção, observe que o documento teve o **rótulo** de retenção Sensitive aplicado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="db7a2-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="db7a2-164">Clique em **Editar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="db7a2-165">No painel **Document.docx,** em **Aplicar** rótulo de retenção, selecione o rótulo **Altamente** Confidencial e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="db7a2-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="db7a2-166">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="db7a2-166">Next step</span></span>

<span data-ttu-id="db7a2-167">Explore recursos [e recursos adicionais de proteção](m365-enterprise-test-lab-guides.md#information-protection) de informações em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="db7a2-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="db7a2-168">Confira também</span><span class="sxs-lookup"><span data-stu-id="db7a2-168">See also</span></span>

[<span data-ttu-id="db7a2-169">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="db7a2-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="db7a2-170">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="db7a2-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="db7a2-171">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="db7a2-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)