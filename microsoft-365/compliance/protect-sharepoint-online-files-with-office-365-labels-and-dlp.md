---
title: Proteja arquivos do SharePoint Online com DLP e rótulos de retenção
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Resumo: Aplique rótulos de retenção e políticas de DLP (prevenção de perda de dados) aos sites de equipe do SharePoint Online com vários níveis de proteção de informações.'
ms.openlocfilehash: cf1565f2a3fbe420abf7739528a78befda9dfe82
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073403"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="9217c-103">Proteja arquivos do SharePoint Online com DLP e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="9217c-103">Protect SharePoint Online files with retention labels and DLP</span></span>

 <span data-ttu-id="9217c-104">**Resumo:** Aplique rótulos de retenção e políticas de DLP (prevenção de perda de dados) aos sites de equipe do SharePoint Online com vários níveis de proteção de informações.</span><span class="sxs-lookup"><span data-stu-id="9217c-104">**Summary:** Apply retention labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="9217c-105">Use as etapas neste artigo para projetar e implantar rótulos de retenção e políticas de DLP (prevenção de perda de dados) para sites de equipe do SharePoint Online de linha de base, confidenciais e altamente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="9217c-105">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="9217c-106">Para obter mais informações sobre essas três camadas de proteção, consulte [Proteção de arquivos e sites do SharePoint Online](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="9217c-106">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="9217c-107">Como isso funciona</span><span class="sxs-lookup"><span data-stu-id="9217c-107">How this works</span></span>

1. <span data-ttu-id="9217c-108">Crie e publique as etiquetas de retenção desejadas.</span><span class="sxs-lookup"><span data-stu-id="9217c-108">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="9217c-109">Pode levar até 12 horas para que elas sejam publicadas.</span><span class="sxs-lookup"><span data-stu-id="9217c-109">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="9217c-110">Para os sites do SharePoint desejados, edite as configurações de biblioteca de documentos para aplicar os rótulos de retenção desejados a itens na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9217c-110">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="9217c-111">Crie políticas DLP para executar ações com base nos rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="9217c-111">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="9217c-112">Quando os usuários adicionarem um documento à biblioteca, este receberá por padrão o rótulo de retenção atribuído.</span><span class="sxs-lookup"><span data-stu-id="9217c-112">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="9217c-113">Os usuários podem alterar o rótulo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="9217c-113">Users can change the label, if needed.</span></span> <span data-ttu-id="9217c-114">Quando um usuário compartilha um documento para fora da organização, a DLP verificará se há um rótulo atribuído e agirá se houver uma política DLP que corresponda ao rótulo.</span><span class="sxs-lookup"><span data-stu-id="9217c-114">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="9217c-115">A DLP também procurará outras políticas que correspondam, como proteger arquivos com números de cartão de crédito, caso este tipo de política estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="9217c-115">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="9217c-116">Rótulos de retenção para seus sites do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9217c-116">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="9217c-117">Há três etapas para criar e atribuir rótulos de retenção a sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9217c-117">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="9217c-118">Etapa 1: Determinar os nomes dos rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="9217c-118">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="9217c-119">Nesta fase, você determina os nomes dos rótulos de retenção para os quatro níveis de proteção de informações aplicados a sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9217c-119">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="9217c-120">A tabela a seguir lista os nomes recomendados para cada nível.</span><span class="sxs-lookup"><span data-stu-id="9217c-120">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="9217c-121">**Nível de proteção do site de equipe do SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="9217c-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="9217c-122">**Nome do rótulo**</span><span class="sxs-lookup"><span data-stu-id="9217c-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9217c-123">Linha de base público</span><span class="sxs-lookup"><span data-stu-id="9217c-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="9217c-124">Público interno</span><span class="sxs-lookup"><span data-stu-id="9217c-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="9217c-125">Linha de base privado</span><span class="sxs-lookup"><span data-stu-id="9217c-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="9217c-126">Private</span><span class="sxs-lookup"><span data-stu-id="9217c-126">Private</span></span>  <br/> |
|<span data-ttu-id="9217c-127">Confidencial</span><span class="sxs-lookup"><span data-stu-id="9217c-127">Sensitive</span></span>  <br/> |<span data-ttu-id="9217c-128">Confidencial</span><span class="sxs-lookup"><span data-stu-id="9217c-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="9217c-129">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="9217c-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="9217c-130">Altamente confidencial</span><span class="sxs-lookup"><span data-stu-id="9217c-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="9217c-131">Fase 2: Criar as etiquetas de retenção</span><span class="sxs-lookup"><span data-stu-id="9217c-131">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="9217c-132">Nesta fase, você cria e publica seus rótulos determinados para os diferentes níveis de proteção de informações.</span><span class="sxs-lookup"><span data-stu-id="9217c-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="9217c-133">Entre no [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="9217c-133">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="9217c-134">Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="9217c-134">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="9217c-135">Clique em **Rótulos de retenção > Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="9217c-135">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="9217c-136">No painel **Atribuir nome ao seu rótulo**, digite o nome do rótulo e uma descrição para administradores e usuários e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-136">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="9217c-137">No painel **Descritores do planejamento de arquivo**, preencha conforme necessário e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-137">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="9217c-138">No painel **Configurações de rótulo**, se necessário, defina **Retenção** como **Ligado** e faça as configurações de retenção.</span><span class="sxs-lookup"><span data-stu-id="9217c-138">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="9217c-139">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-139">Click **Next**.</span></span>
    
7. <span data-ttu-id="9217c-140">No painel **Revise suas configurações**, clique em **Criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="9217c-140">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="9217c-141">Para seus rótulos adicionais, clique em **Criar um rótulo** e, em seguida, repita as etapas 3 a 7, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9217c-141">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="9217c-142">Publique seus novos rótulos</span><span class="sxs-lookup"><span data-stu-id="9217c-142">Publish your new labels</span></span>

<span data-ttu-id="9217c-143">Em seguida, use estas etapas para publicar os novos rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="9217c-143">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="9217c-144">No painel **Rótulos**, clique na guia **Rótulos de retenção** e, em seguida, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="9217c-144">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="9217c-145">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-145">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="9217c-146">No painel **Escolher rótulos**, clique em **Adicionar**, selecione todos os quatro rótulos, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-146">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="9217c-147">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="9217c-147">Click **Done**.</span></span>
    
5. <span data-ttu-id="9217c-148">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-148">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="9217c-149">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-149">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="9217c-150">No painel **Atribuir um nome à política**, digite um nome para o conjunto de rótulos em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-150">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="9217c-151">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-151">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="9217c-152">Etapa 3: Aplicar os rótulos de retenção aos seus sites do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9217c-152">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="9217c-153">Use estas etapas para aplicar os rótulos de retenção às pastas de documentos de seus sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9217c-153">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="9217c-154">Acesse o [portal do Office 365](https://www.office.com), clique no aplicativo **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9217c-154">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="9217c-155">Na nova guia **SharePoint** no seu navegador, clique em um site que precise de um rótulo de retenção atribuído.</span><span class="sxs-lookup"><span data-stu-id="9217c-155">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="9217c-156">Na nova guia de site do SharePoint do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="9217c-156">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="9217c-157">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="9217c-157">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="9217c-158">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="9217c-158">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="9217c-159">Em **Configurações – Aplicar Rótulo**, selecione o rótulo de retenção adequado e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-159">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="9217c-160">Feche a guia para o site do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9217c-160">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="9217c-161">Repita as etapas 2 a 8 acima para atribuir rótulos de retenção aos seus sites adicionais do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9217c-161">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="9217c-162">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="9217c-162">Here is your resulting configuration.</span></span>
  
![Rótulos de retenção para os quatro tipos de sites de equipe do SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="9217c-164">Políticas DLP para seus sites do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9217c-164">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="9217c-165">Use estas etapas para configurar uma política DLP que notifica os usuários quando eles compartilham um documento em um site de equipe confidencial do SharePoint Online fora da organização.</span><span class="sxs-lookup"><span data-stu-id="9217c-165">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="9217c-166">Entre no [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="9217c-166">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="9217c-167">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="9217c-167">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="9217c-168">No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="9217c-168">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="9217c-169">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-169">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="9217c-170">No painel **Atribuir um nome à política**, digite o nome da política DLP de nível confidencial em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-170">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="9217c-171">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-171">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="9217c-172">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-172">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="9217c-173">No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-173">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="9217c-174">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="9217c-174">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="9217c-175">No painel **Rótulos de retenção**, clique em \*\* Adicionar\*\*, selecione o rótulo **Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="9217c-175">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="9217c-176">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-176">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="9217c-177">No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.</span><span class="sxs-lookup"><span data-stu-id="9217c-177">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="9217c-178">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="9217c-178">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="9217c-179">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="9217c-179">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="9217c-180">Na caixa de texto, digite ou cole uma das dicas a seguir, dependendo de se você implementou a Proteção de Informações do Azure para proteger arquivos altamente confidenciais:</span><span class="sxs-lookup"><span data-stu-id="9217c-180">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="9217c-p106">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="9217c-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="9217c-p107">Arquivos altamente confidenciais são protegidos com criptografia. Somente usuários externos que recebam permissões do seu departamento de TI para esses arquivos poderão lê-los.</span><span class="sxs-lookup"><span data-stu-id="9217c-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="9217c-186">Como alternativa, digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.</span><span class="sxs-lookup"><span data-stu-id="9217c-186">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="9217c-187">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9217c-187">Click **OK**.</span></span>
    
17. <span data-ttu-id="9217c-188">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-188">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="9217c-189">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-189">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="9217c-190">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-190">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="9217c-191">Aqui está a configuração resultante dos sites confidenciais da equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9217c-191">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Política DLP para um site de equipe isolado do SharePoint Online usando o rótulo de retenção Confidencial.](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="9217c-193">Em seguida, use estas etapas para configurar uma política DLP que bloqueia os usuários quando eles compartilham um documento em um site de equipe altamente confidencial do SharePoint Online fora da organização.</span><span class="sxs-lookup"><span data-stu-id="9217c-193">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="9217c-194">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="9217c-194">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="9217c-195">No painel **Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="9217c-195">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="9217c-196">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-196">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="9217c-197">No painel **Atribuir um nome à política**, digite o nome da política DLP de nível altamente confidencial em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-197">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="9217c-198">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-198">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="9217c-199">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-199">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="9217c-200">No painel **Personalizar os tipos de informações confidenciais que deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-200">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="9217c-201">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="9217c-201">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="9217c-202">No painel **Rótulos de retenção**, clique em **Adicionar**, selecione o rótulo **Altamente Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="9217c-202">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="9217c-203">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-203">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="9217c-204">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-204">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="9217c-205">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="9217c-205">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="9217c-206">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="9217c-206">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="9217c-207">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9217c-207">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="9217c-p108">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="9217c-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="9217c-211">Como alternativa, digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.</span><span class="sxs-lookup"><span data-stu-id="9217c-211">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="9217c-212">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9217c-212">Click **OK**.</span></span>
    
17. <span data-ttu-id="9217c-213">Na caixa **O que você deseja fazer se detectarmos informações confidenciais?**, em **Detectar quando uma quantidade específica de informações confidenciais está sendo compartilhada ao mesmo tempo**, clique em **Restringir acesso ou criptografar o conteúdo** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-213">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="9217c-214">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-214">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="9217c-215">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="9217c-215">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="9217c-216">Aqui está a configuração resultante para sites de equipe do SharePoint Online de alta confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="9217c-216">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Política DLP para um site de equipe isolado do SharePoint Online usando o rótulo de retenção Altamente Confidencial](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="9217c-218">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="9217c-218">Next step</span></span>

[<span data-ttu-id="9217c-219">Proteger arquivos do SharePoint Online com a Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="9217c-219">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="9217c-220">Confira Também</span><span class="sxs-lookup"><span data-stu-id="9217c-220">See Also</span></span>

<span data-ttu-id="9217c-221"><<<<<<< TÍTULO [Proteger arquivos e sites do SharePoint Online](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="9217c-221">[Secure SharePoint Online sites and files](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)</span></span>
  
<a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizationssecurityoffice-365-securitymicrosoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-omd"></a>[<span data-ttu-id="9217c-222">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações do Agile</span><span class="sxs-lookup"><span data-stu-id="9217c-222">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
=======
[<span data-ttu-id="9217c-223">Proteger arquivos e sites do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9217c-223">Secure SharePoint Online sites and files</span></span>](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="9217c-224">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações do Agile</span><span class="sxs-lookup"><span data-stu-id="9217c-224">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
>>>>>>> <span data-ttu-id="9217c-225">9904103ea22646c71f6541e03c7491a767a783ce</span><span class="sxs-lookup"><span data-stu-id="9217c-225">9904103ea22646c71f6541e03c7491a767a783ce</span></span>
  
[<span data-ttu-id="9217c-226">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="9217c-226">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


