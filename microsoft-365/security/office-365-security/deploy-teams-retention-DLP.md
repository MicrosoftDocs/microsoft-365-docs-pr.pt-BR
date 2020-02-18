---
title: Proteger arquivos em equipes com rótulos de retenção e DLP
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
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
description: 'Resumo: aplique rótulos de retenção e políticas DLP (prevenção contra perda de dados) a arquivos em equipes com vários níveis de proteção de informações.'
ms.openlocfilehash: 94d8a02d0ea88fa8a05cd6a2c95a2db866d72fad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083383"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a><span data-ttu-id="7e021-103">Proteger arquivos em equipes com rótulos de retenção e DLP</span><span class="sxs-lookup"><span data-stu-id="7e021-103">Protect files in teams with retention labels and DLP</span></span>

 
<span data-ttu-id="7e021-104">Use as etapas neste artigo para projetar e implantar rótulos de retenção e DLP (prevenção contra perda de dados) em equipes de linha de base, confidenciais e altamente confidenciais e seus sites subjacentes do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e021-104">Use the steps in this article to design and deploy retention labels and data loss prevention (DLP) policies for baseline, sensitive, and highly confidential teams and their underlying SharePoint sites.</span></span> <span data-ttu-id="7e021-105">Para obter mais informações sobre essas três camadas de proteção, confira [Proteção de arquivos no Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7e021-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="7e021-106">Como isso funciona</span><span class="sxs-lookup"><span data-stu-id="7e021-106">How this works</span></span>

1. <span data-ttu-id="7e021-107">Crie e publique as etiquetas de retenção desejadas.</span><span class="sxs-lookup"><span data-stu-id="7e021-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="7e021-108">Pode levar até 12 horas para que elas sejam publicadas.</span><span class="sxs-lookup"><span data-stu-id="7e021-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="7e021-109">Para os sites subjacentes do SharePoint desejados, edite as configurações da biblioteca de documentos para aplicar os rótulos de retenção desejados a itens na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="7e021-109">For the desired underlying SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="7e021-110">Crie políticas DLP para executar ações com base nos rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="7e021-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="7e021-111">Quando os usuários adicionarem um documento à biblioteca de sites subjacentes do SharePoint da equipe, o documento receberá o rótulo de retenção atribuído por padrão.</span><span class="sxs-lookup"><span data-stu-id="7e021-111">When users add a document to the underlying SharePoint site library for the team, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="7e021-112">Os usuários podem alterar o rótulo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="7e021-112">Users can change the label, if needed.</span></span> <span data-ttu-id="7e021-113">Quando um usuário compartilha um documento para fora da organização, a DLP verificará se há um rótulo atribuído e agirá se houver uma política DLP que corresponda ao rótulo.</span><span class="sxs-lookup"><span data-stu-id="7e021-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="7e021-114">A DLP também procurará outras políticas que correspondam, como proteger arquivos com números de cartão de crédito, caso este tipo de política estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="7e021-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="7e021-115">Rótulos de retenção para sites subjacentes do SharePoint</span><span class="sxs-lookup"><span data-stu-id="7e021-115">Retention labels for your underlying SharePoint sites</span></span>

<span data-ttu-id="7e021-116">Há três fases para criar e atribuir rótulos de retenção a sites subjacentes do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e021-116">There are three phases to creating and then assigning retention labels to underlying SharePoint sites.</span></span>
  
### <a name="step-1-determine-the-retention-label-names"></a><span data-ttu-id="7e021-117">Etapa 1: determinar os nomes dos rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="7e021-117">Step 1: Determine the retention label names</span></span>

<span data-ttu-id="7e021-118">Nessa fase, você determina os nomes dos rótulos de retenção para os quatro níveis de proteção de informações aplicados a sites subjacentes do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e021-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to underlying SharePoint sites.</span></span> <span data-ttu-id="7e021-119">A tabela a seguir lista os nomes recomendados para cada nível.</span><span class="sxs-lookup"><span data-stu-id="7e021-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="7e021-120">**nível de proteção de sites subjacentes do SharePoint**</span><span class="sxs-lookup"><span data-stu-id="7e021-120">**underlying SharePoint sites protection level**</span></span>|<span data-ttu-id="7e021-121">**Nome do rótulo**</span><span class="sxs-lookup"><span data-stu-id="7e021-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7e021-122">Linha de base público</span><span class="sxs-lookup"><span data-stu-id="7e021-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="7e021-123">Público interno</span><span class="sxs-lookup"><span data-stu-id="7e021-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="7e021-124">Linha de base privado</span><span class="sxs-lookup"><span data-stu-id="7e021-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="7e021-125">Private</span><span class="sxs-lookup"><span data-stu-id="7e021-125">Private</span></span>  <br/> |
|<span data-ttu-id="7e021-126">Confidencial</span><span class="sxs-lookup"><span data-stu-id="7e021-126">Sensitive</span></span>  <br/> |<span data-ttu-id="7e021-127">Confidencial</span><span class="sxs-lookup"><span data-stu-id="7e021-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="7e021-128">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="7e021-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="7e021-129">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="7e021-129">Highly Confidential</span></span>  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a><span data-ttu-id="7e021-130">Fase 2: criar os rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="7e021-130">Step 2: Create the retention labels</span></span>

<span data-ttu-id="7e021-131">Nesta fase, você cria e publica seus rótulos determinados para os diferentes níveis de proteção de informações.</span><span class="sxs-lookup"><span data-stu-id="7e021-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="7e021-132">Entre no [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="7e021-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="7e021-133">Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="7e021-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="7e021-134">Clique em **Rótulos de retenção > Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="7e021-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="7e021-135">No painel **Atribuir nome ao seu rótulo**, digite o nome do rótulo e uma descrição para administradores e usuários e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="7e021-136">No painel **Descritores do planejamento de arquivo**, preencha conforme necessário e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7e021-137">No painel **Configurações de rótulo**, se necessário, defina **Retenção** como **Ligado** e faça as configurações de retenção.</span><span class="sxs-lookup"><span data-stu-id="7e021-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="7e021-138">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="7e021-139">No painel **Revise suas configurações**, clique em **Criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="7e021-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="7e021-140">Para obter mais rótulos, clique em **Criar um rótulo** e repita as etapas 3-7 deste procedimento conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7e021-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 in this procedure as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="7e021-141">Publique seus novos rótulos</span><span class="sxs-lookup"><span data-stu-id="7e021-141">Publish your new labels</span></span>

<span data-ttu-id="7e021-142">Em seguida, use estas etapas para publicar os novos rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="7e021-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="7e021-143">No painel **Rótulos**, clique na guia **Rótulos de retenção** e, em seguida, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="7e021-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="7e021-144">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="7e021-145">No painel **Escolher rótulos**, clique em **Adicionar**, selecione todos os quatro rótulos, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="7e021-146">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="7e021-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="7e021-147">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="7e021-148">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="7e021-149">No painel **Atribuir um nome à política**, digite um nome para o conjunto de rótulos em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7e021-150">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a><span data-ttu-id="7e021-151">Etapa 3: aplicar os rótulos de retenção a sites subjacentes do SharePoint</span><span class="sxs-lookup"><span data-stu-id="7e021-151">Step 3: Apply the retention labels to your underlying SharePoint sites</span></span>

<span data-ttu-id="7e021-152">Use estas etapas para aplicar os rótulos de retenção às pastas de documentos dos sites subjacentes do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e021-152">Use these steps to apply the retention labels to the documents folders of your underlying SharePoint sites.</span></span>
  
1.  <span data-ttu-id="7e021-153">Na equipe, clique em **Arquivos** e em **Abrir no SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7e021-153">From the team, click **Files**, and then click **Open in SharePoint**.</span></span>

2. <span data-ttu-id="7e021-154">Na nova guia de site do SharePoint do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="7e021-154">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
3. <span data-ttu-id="7e021-155">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="7e021-155">Click the settings icon, and then click **Library settings**.</span></span>
    
4. <span data-ttu-id="7e021-156">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="7e021-156">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
5. <span data-ttu-id="7e021-157">Em **Configurações – Aplicar Rótulo**, selecione o rótulo de retenção adequado e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-157">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
6. <span data-ttu-id="7e021-158">Feche a guia do site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e021-158">Close the tab for the SharePoint site.</span></span>
    
7. <span data-ttu-id="7e021-159">Repita as etapas 1-6 para atribuir rótulos de retenção a sites subjacentes do SharePoint adicionais.</span><span class="sxs-lookup"><span data-stu-id="7e021-159">Repeat steps 1-6 to assign retention labels to your additional underlying SharePoint sites.</span></span>
    
<span data-ttu-id="7e021-160">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="7e021-160">Here is your resulting configuration.</span></span>
  
![Rótulos de retenção para os quatro tipos de sites subjacentes do SharePoint.](../../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="7e021-162">Políticas DLP para os sites subjacentes do SharePoint</span><span class="sxs-lookup"><span data-stu-id="7e021-162">DLP policies for your underlying SharePoint sites</span></span>

<span data-ttu-id="7e021-163">Use estas etapas para configurar uma política DLP que notifique os usuários quando eles compartilharem um documento em um site subjacente do SharePoint fora da organização.</span><span class="sxs-lookup"><span data-stu-id="7e021-163">Use these steps to configure a DLP policy that notifies users when they share a document on an underlying SharePoint site outside the organization.</span></span>

1. <span data-ttu-id="7e021-164">Entre no [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="7e021-164">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="7e021-165">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="7e021-165">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="7e021-166">No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="7e021-166">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="7e021-167">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-167">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="7e021-168">No painel **Atribuir um nome à política**, digite o nome da política DLP de nível confidencial em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-168">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7e021-169">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-169">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7e021-170">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-170">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7e021-171">No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-171">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="7e021-172">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="7e021-172">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="7e021-173">No painel **Rótulos de retenção**, clique em \*\* Adicionar\*\*, selecione o rótulo **Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="7e021-173">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="7e021-174">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-174">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="7e021-175">No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.</span><span class="sxs-lookup"><span data-stu-id="7e021-175">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="7e021-176">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="7e021-176">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="7e021-177">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="7e021-177">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="7e021-178">Na caixa de texto, digite ou cole uma das seguintes dicas:</span><span class="sxs-lookup"><span data-stu-id="7e021-178">In the text box, type or paste in one of the following tips:</span></span>
    
  - <span data-ttu-id="7e021-p106">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="7e021-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="7e021-p107">Arquivos altamente confidenciais são protegidos com criptografia. Somente usuários externos que recebam permissões do seu departamento de TI para esses arquivos poderão lê-los.</span><span class="sxs-lookup"><span data-stu-id="7e021-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="7e021-184">Como alternativa, digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.</span><span class="sxs-lookup"><span data-stu-id="7e021-184">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="7e021-185">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e021-185">Click **OK**.</span></span>
    
17. <span data-ttu-id="7e021-186">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-186">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="7e021-187">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-187">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="7e021-188">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-188">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="7e021-189">Estas são as configurações resultantes para equipes confidenciais.</span><span class="sxs-lookup"><span data-stu-id="7e021-189">Here is your resulting configuration for sensitive teams.</span></span>
  
![Política DLP para equipe confidencial usando o rótulo de retenção Confidencial](../../media/retention-labels-sensitive-dlp.png)
  
<span data-ttu-id="7e021-191">Depois, siga estas etapas para configurar uma política DLP que impeça os usuários de compartilhar um documento em um site subjacente do SharePoint fora da organização.</span><span class="sxs-lookup"><span data-stu-id="7e021-191">Next, use these steps to configure a DLP policy that blocks users when they share a document on an underlying SharePoint site outside the organization.</span></span>
  
1. <span data-ttu-id="7e021-192">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="7e021-192">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="7e021-193">No painel **Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="7e021-193">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="7e021-194">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-194">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="7e021-195">No painel **Atribuir um nome à política**, digite o nome da política DLP de nível altamente confidencial em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-195">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="7e021-196">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-196">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7e021-197">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-197">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7e021-198">No painel **Personalizar os tipos de informações confidenciais que deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-198">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="7e021-199">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="7e021-199">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="7e021-200">No painel **Rótulos de retenção**, clique em **Adicionar**, selecione o rótulo **Altamente Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="7e021-200">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="7e021-201">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-201">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="7e021-202">No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-202">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="7e021-203">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="7e021-203">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="7e021-204">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="7e021-204">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="7e021-205">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7e021-205">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="7e021-p108">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="7e021-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="7e021-209">Como alternativa, digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.</span><span class="sxs-lookup"><span data-stu-id="7e021-209">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="7e021-210">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e021-210">Click **OK**.</span></span>
    
17. <span data-ttu-id="7e021-211">Na caixa **O que você deseja fazer se detectarmos informações confidenciais?**, em **Detectar quando uma quantidade específica de informações confidenciais está sendo compartilhada ao mesmo tempo**, clique em **Restringir acesso ou criptografar o conteúdo** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-211">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="7e021-212">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-212">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="7e021-213">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7e021-213">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="7e021-214">Esta é a configuração resultante para a equipe de alta confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="7e021-214">Here is your resulting configuration for high confidentiality team.</span></span>
  
![Política DLP para uma equipe de alta confidencialidade usando o rótulo de retenção Altamente Confidencial](../../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a><span data-ttu-id="7e021-216">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7e021-216">Next step</span></span>

[<span data-ttu-id="7e021-217">Proteger arquivos em equipes com rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="7e021-217">Protect files in teams with sensitivity labels</span></span>](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a><span data-ttu-id="7e021-218">Confira também</span><span class="sxs-lookup"><span data-stu-id="7e021-218">See Also</span></span>

[<span data-ttu-id="7e021-219">Proteger arquivos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e021-219">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="7e021-220">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="7e021-220">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


