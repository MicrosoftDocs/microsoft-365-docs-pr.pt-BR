---
title: Proteja arquivos do SharePoint Online com DLP e rótulos de retenção
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Resumo: Aplique rótulos de retenção e políticas de DLP (prevenção de perda de dados) aos sites de equipe do SharePoint Online com vários níveis de proteção de informações.'
ms.openlocfilehash: ab9026fa4c00038abb166677277145c8129e33e2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081732"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="0bf81-103">Proteja arquivos do SharePoint Online com DLP e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="0bf81-103">Protect SharePoint Online files with retention labels and DLP</span></span>

<span data-ttu-id="0bf81-104">Use as etapas neste artigo para projetar e implantar rótulos de retenção e políticas de DLP (prevenção de perda de dados) para sites de equipe do SharePoint Online de linha de base, confidenciais e altamente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="0bf81-104">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="0bf81-105">Para obter mais informações sobre essas três camadas de proteção, consulte [Proteção de arquivos e sites do SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="0bf81-105">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="0bf81-106">Como isso funciona</span><span class="sxs-lookup"><span data-stu-id="0bf81-106">How this works</span></span>

1. <span data-ttu-id="0bf81-107">Crie e publique as etiquetas de retenção desejadas.</span><span class="sxs-lookup"><span data-stu-id="0bf81-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="0bf81-108">Pode levar até 12 horas para que elas sejam publicadas.</span><span class="sxs-lookup"><span data-stu-id="0bf81-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="0bf81-109">Para os sites do SharePoint desejados, edite as configurações de biblioteca de documentos para aplicar os rótulos de retenção desejados a itens na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0bf81-109">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="0bf81-110">Crie políticas DLP para executar ações com base nos rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="0bf81-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="0bf81-111">Quando os usuários adicionarem um documento à biblioteca, este receberá por padrão o rótulo de retenção atribuído.</span><span class="sxs-lookup"><span data-stu-id="0bf81-111">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="0bf81-112">Os usuários podem alterar o rótulo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="0bf81-112">Users can change the label, if needed.</span></span> <span data-ttu-id="0bf81-113">Quando um usuário compartilha um documento para fora da organização, a DLP verificará se há um rótulo atribuído e agirá se houver uma política DLP que corresponda ao rótulo.</span><span class="sxs-lookup"><span data-stu-id="0bf81-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="0bf81-114">A DLP também procurará outras políticas que correspondam, como proteger arquivos com números de cartão de crédito, caso este tipo de política estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="0bf81-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="0bf81-115">Rótulos de retenção para seus sites do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0bf81-115">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="0bf81-116">Há três etapas para criar e atribuir rótulos de retenção a sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0bf81-116">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="0bf81-117">Etapa 1: Determinar os nomes dos rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="0bf81-117">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="0bf81-118">Nesta fase, você determina os nomes dos rótulos de retenção para os quatro níveis de proteção de informações aplicados a sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0bf81-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="0bf81-119">A tabela a seguir lista os nomes recomendados para cada nível.</span><span class="sxs-lookup"><span data-stu-id="0bf81-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="0bf81-120">**Nível de proteção do site de equipe do SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="0bf81-120">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="0bf81-121">**Nome do rótulo**</span><span class="sxs-lookup"><span data-stu-id="0bf81-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0bf81-122">Linha de base público</span><span class="sxs-lookup"><span data-stu-id="0bf81-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="0bf81-123">Público interno</span><span class="sxs-lookup"><span data-stu-id="0bf81-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="0bf81-124">Linha de base privado</span><span class="sxs-lookup"><span data-stu-id="0bf81-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="0bf81-125">Private</span><span class="sxs-lookup"><span data-stu-id="0bf81-125">Private</span></span>  <br/> |
|<span data-ttu-id="0bf81-126">Confidencial</span><span class="sxs-lookup"><span data-stu-id="0bf81-126">Sensitive</span></span>  <br/> |<span data-ttu-id="0bf81-127">Confidencial</span><span class="sxs-lookup"><span data-stu-id="0bf81-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="0bf81-128">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="0bf81-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="0bf81-129">Altamente confidencial</span><span class="sxs-lookup"><span data-stu-id="0bf81-129">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="0bf81-130">Fase 2: Criar as etiquetas de retenção</span><span class="sxs-lookup"><span data-stu-id="0bf81-130">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="0bf81-131">Nesta fase, você cria e publica seus rótulos determinados para os diferentes níveis de proteção de informações.</span><span class="sxs-lookup"><span data-stu-id="0bf81-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="0bf81-132">Entre no [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="0bf81-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="0bf81-133">Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="0bf81-134">Clique em **Rótulos de retenção > Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="0bf81-135">No painel **Atribuir nome ao seu rótulo**, digite o nome do rótulo e uma descrição para administradores e usuários e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="0bf81-136">No painel **Descritores do planejamento de arquivo**, preencha conforme necessário e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="0bf81-137">No painel **Configurações de rótulo**, se necessário, defina **Retenção** como **Ligado** e faça as configurações de retenção.</span><span class="sxs-lookup"><span data-stu-id="0bf81-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="0bf81-138">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="0bf81-139">No painel **Revise suas configurações**, clique em **Criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="0bf81-140">Para seus rótulos adicionais, clique em **Criar um rótulo** e, em seguida, repita as etapas 3 a 7, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0bf81-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="0bf81-141">Publique seus novos rótulos</span><span class="sxs-lookup"><span data-stu-id="0bf81-141">Publish your new labels</span></span>

<span data-ttu-id="0bf81-142">Em seguida, use estas etapas para publicar os novos rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="0bf81-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="0bf81-143">No painel **Rótulos**, clique na guia **Rótulos de retenção** e, em seguida, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="0bf81-144">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="0bf81-145">No painel **Escolher rótulos**, clique em **Adicionar**, selecione todos os quatro rótulos, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="0bf81-146">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="0bf81-147">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="0bf81-148">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="0bf81-149">No painel **Atribuir um nome à política**, digite um nome para o conjunto de rótulos em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0bf81-150">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="0bf81-151">Etapa 3: Aplicar os rótulos de retenção aos seus sites do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0bf81-151">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="0bf81-152">Use estas etapas para aplicar os rótulos de retenção às pastas de documentos de seus sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0bf81-152">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="0bf81-153">Acesse o [portal do Office 365](https://www.office.com), clique no aplicativo **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-153">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="0bf81-154">Na nova guia **SharePoint** no seu navegador, clique em um site que precise de um rótulo de retenção atribuído.</span><span class="sxs-lookup"><span data-stu-id="0bf81-154">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="0bf81-155">Na nova guia de site do SharePoint do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-155">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="0bf81-156">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-156">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="0bf81-157">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-157">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="0bf81-158">Em **Configurações – Aplicar Rótulo**, selecione o rótulo de retenção adequado e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-158">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="0bf81-159">Feche a guia para o site do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0bf81-159">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="0bf81-160">Repita as etapas 2 a 8 acima para atribuir rótulos de retenção aos seus sites adicionais do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0bf81-160">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="0bf81-161">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="0bf81-161">Here is your resulting configuration.</span></span>
  
![Rótulos de retenção para os quatro tipos de sites de equipe do SharePoint Online.](../media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="0bf81-163">Políticas DLP para seus sites do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0bf81-163">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="0bf81-164">Use estas etapas para configurar uma política DLP que notifica os usuários quando eles compartilham um documento em um site de equipe confidencial do SharePoint Online fora da organização.</span><span class="sxs-lookup"><span data-stu-id="0bf81-164">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="0bf81-165">Entre no [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="0bf81-165">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="0bf81-166">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-166">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="0bf81-167">No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-167">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="0bf81-168">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-168">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="0bf81-169">No painel **Atribuir um nome à política**, digite o nome da política DLP de nível confidencial em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-169">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="0bf81-170">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-170">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="0bf81-171">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-171">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0bf81-172">No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-172">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="0bf81-173">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-173">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="0bf81-174">No painel **Rótulos de retenção**, clique em \*\* Adicionar\*\*, selecione o rótulo **Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-174">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="0bf81-175">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-175">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="0bf81-176">No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-176">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="0bf81-177">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-177">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="0bf81-178">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-178">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="0bf81-179">Na caixa de texto, digite ou cole uma das dicas a seguir, dependendo se você está usando opcionalmente rótulos de confidencialidade para proteger arquivos altamente confidenciais:</span><span class="sxs-lookup"><span data-stu-id="0bf81-179">In the text box, type or paste in one of the following tips, depending on if you are optionallyusing sensitivity labels to protect sensitive files:</span></span>
    
  - <span data-ttu-id="0bf81-p106">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="0bf81-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="0bf81-p107">Arquivos altamente confidenciais são protegidos com criptografia. Somente usuários externos que recebam permissões do seu departamento de TI para esses arquivos poderão lê-los.</span><span class="sxs-lookup"><span data-stu-id="0bf81-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="0bf81-185">Como alternativa, digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.</span><span class="sxs-lookup"><span data-stu-id="0bf81-185">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="0bf81-186">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-186">Click **OK**.</span></span>
    
17. <span data-ttu-id="0bf81-187">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-187">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="0bf81-188">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-188">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="0bf81-189">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-189">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="0bf81-190">Aqui está a configuração resultante dos sites confidenciais da equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0bf81-190">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Política DLP para um site de equipe isolado do SharePoint Online usando o rótulo de retenção Confidencial.](../media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="0bf81-192">Em seguida, use estas etapas para configurar uma política DLP que bloqueia os usuários quando eles compartilham um documento em um site de equipe altamente confidencial do SharePoint Online fora da organização.</span><span class="sxs-lookup"><span data-stu-id="0bf81-192">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="0bf81-193">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-193">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="0bf81-194">No painel **Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-194">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="0bf81-195">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-195">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="0bf81-196">No painel **Atribuir um nome à política**, digite o nome da política DLP de nível altamente confidencial em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-196">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="0bf81-197">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-197">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="0bf81-198">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-198">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="0bf81-199">No painel **Personalizar os tipos de informações confidenciais que deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-199">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="0bf81-200">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-200">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="0bf81-201">No painel **Rótulos de retenção**, clique em **Adicionar**, selecione o rótulo **Altamente Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-201">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="0bf81-202">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-202">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="0bf81-203">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-203">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="0bf81-204">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-204">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="0bf81-205">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-205">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="0bf81-206">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0bf81-206">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="0bf81-p108">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="0bf81-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="0bf81-210">Como alternativa, digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.</span><span class="sxs-lookup"><span data-stu-id="0bf81-210">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="0bf81-211">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-211">Click **OK**.</span></span>
    
17. <span data-ttu-id="0bf81-212">Na caixa **O que você deseja fazer se detectarmos informações confidenciais?**, em **Detectar quando uma quantidade específica de informações confidenciais está sendo compartilhada ao mesmo tempo**, clique em **Restringir acesso ou criptografar o conteúdo** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-212">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="0bf81-213">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-213">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="0bf81-214">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-214">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="0bf81-215">Aqui está a configuração resultante para sites de equipe do SharePoint Online de alta confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="0bf81-215">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Política DLP para um site de equipe isolado do SharePoint Online usando o rótulo de retenção Altamente Confidencial](../media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="0bf81-217">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="0bf81-217">Next step</span></span>

[<span data-ttu-id="0bf81-218">Proteger arquivos do SharePoint Online com rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="0bf81-218">Protect SharePoint Online files with sensitivity labels</span></span>](protect-sharepoint-online-files-with-sensitivity-label.md)
    
## <a name="see-also"></a><span data-ttu-id="0bf81-219">Confira também</span><span class="sxs-lookup"><span data-stu-id="0bf81-219">See Also</span></span>

[<span data-ttu-id="0bf81-220">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações do Agile</span><span class="sxs-lookup"><span data-stu-id="0bf81-220">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="0bf81-221">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="0bf81-221">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


