---
title: 'Configurar o gerenciamento de conhecimento (versão prévia) '
description: Como configurar o gerenciamento de conhecimento.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988903"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="1e3ad-103">Configurar o gerenciamento de conhecimento (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="1e3ad-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="1e3ad-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="1e3ad-105">[Mais informações sobre o Projeto Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="1e3ad-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="1e3ad-106">Você pode usar o centro de administração do Microsoft 365 para configurar e configurar o [Gerenciamento de conhecimento](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1e3ad-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="1e3ad-107">É importante planejar a melhor maneira de configurar e configurar o gerenciamento de conhecimento em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="1e3ad-108">Por exemplo, você precisará fazer considerações sobre o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="1e3ad-109">Quais sites do SharePoint você deseja analisar os tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="1e3ad-110">Para quais usuários você deseja tornar os tópicos visíveis.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="1e3ad-111">Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="1e3ad-112">Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="1e3ad-113">Que nome você deseja dar à sua central de tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="1e3ad-114">Você pode achar útil criar grupos de segurança para atribuir aos usuários as permissões necessárias para exibir tópicos, gerenciar tópico e criar e editar tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="1e3ad-115">Um administrador também pode [fazer alterações nas configurações selecionadas a qualquer momento após a configuração](topic-experiences-discovery.md) , por meio das configurações de gerenciamento de conhecimento no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-115">An admin can also [make changes to your selected settings anytime after setup](topic-experiences-discovery.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="1e3ad-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="1e3ad-116">Requirements</span></span> 
<span data-ttu-id="1e3ad-117">Você deve ter permissões de administrador global ou administrador do SharePoint para poder acessar o centro de administração do Microsoft 365 e configurar tarefas de conhecimento organizacional.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="1e3ad-118">Configurar sua rede de conhecimento</span><span class="sxs-lookup"><span data-stu-id="1e3ad-118">Set up your knowledge network</span></span>

<span data-ttu-id="1e3ad-119">Configurar sua rede de conhecimento orienta você por meio do seguinte:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="1e3ad-120">Descoberta de tópico: selecionar fontes e tópicos de tópico para excluir da descoberta.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="1e3ad-121">Visibilidade do tópico: selecionar quem pode exibir tópicos como destaques, nas páginas de pesquisa e tópico.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="1e3ad-122">Permissões de tópico: selecionar quem pode criar, editar e gerenciar tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="1e3ad-123">Centro de tópicos: Crie seu centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="1e3ad-124">Revisão: Verifique e aplique suas configurações.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="1e3ad-125">Para configurar sua rede de conhecimento:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="1e3ad-126">No centro de administração do Microsoft 365 (admin.microsoft.com), selecione **configuração** e, em seguida, exiba a seção de **conhecimento organizacional** .</span><span class="sxs-lookup"><span data-stu-id="1e3ad-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="1e3ad-127">Na seção **conhecimento organizacional** , clique em **conectar pessoas a conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Conectar pessoas a conhecimento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="1e3ad-129">Na página **conectar pessoas a conhecimento** **, clique em introdução para** orientá-lo no processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Introdução](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="1e3ad-131">Na página **escolha como a rede de conhecimento pode encontrar tópicos** , você configurará a descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="1e3ad-132">Na seção **selecionar fontes de tópicos do SharePoint** , selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="1e3ad-133">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-133">This includes:</span></span></br>
    <span data-ttu-id="1e3ad-134">a.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-134">a.</span></span> <span data-ttu-id="1e3ad-135">**Todos os sites** : todos os sites do SharePoint em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-135">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="1e3ad-136">Isso captura sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="1e3ad-137">b.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-137">b.</span></span> <span data-ttu-id="1e3ad-138">**Todos, exceto sites selecionados** : digite os nomes dos sites que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-138">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="1e3ad-139">Você também pode carregar uma lista de sites que deseja recusar da descoberta.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="1e3ad-140">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="1e3ad-141">c.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-141">c.</span></span> <span data-ttu-id="1e3ad-142">**Somente sites selecionados** : digite os nomes dos sites que você deseja incluir.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-142">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="1e3ad-143">Você também pode carregar uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-143">You can also upload a list of sites.</span></span> <span data-ttu-id="1e3ad-144">Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Escolher como localizar tópicos](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="1e3ad-146">Na seção **excluir tópicos por nome** , você pode optar por incluir nomes de tópicos que não deseja que estejam nos resultados detectados.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="1e3ad-147">Use essa configuração para impedir que tópicos confidenciais sejam incluídos como parte da rede de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="1e3ad-148">As opções incluem:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-148">Your options include:</span></span></br>
    <span data-ttu-id="1e3ad-149">a.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-149">a.</span></span> <span data-ttu-id="1e3ad-150">**Não excluir nenhum tópico**</span><span class="sxs-lookup"><span data-stu-id="1e3ad-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="1e3ad-151">b.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-151">b.</span></span> <span data-ttu-id="1e3ad-152">**Excluir tópicos por nome** : se você tiver tópicos que não deseja mostrar aos usuários como parte da rede de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-152">**Exclude topics by name** :  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![Excluir tópicos](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="1e3ad-154">Como excluir tópicos por nome</span><span class="sxs-lookup"><span data-stu-id="1e3ad-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="1e3ad-155">Se você precisar excluir tópicos, depois de selecionar **excluir tópicos por nome** , selecione **baixar o modelo. csv**.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-155">If you need to exclude topics, after selecting **Exclude topics by name** , select **Download the .csv template**.</span></span> <span data-ttu-id="1e3ad-156">Use o Excel. Modelo CSV para incluir uma lista de tópicos que você deseja excluir dos resultados da descoberta.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![Excluir tópicos no modelo CSV](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="1e3ad-158">No modelo CSV, insira as seguintes informações sobre os tópicos que você deseja excluir:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="1e3ad-159">**Name** : digite o nome do tópico que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-159">**Name** : Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="1e3ad-160">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="1e3ad-161">Correspondência exata: você pode incluir o nome exato ou o acrônimo (por exemplo, *contoso* ou *ATL* ).</span><span class="sxs-lookup"><span data-stu-id="1e3ad-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL* ).</span></span></br>
        - <span data-ttu-id="1e3ad-162">Correspondência parcial: você pode excluir todos os tópicos que possuem uma palavra específica.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="1e3ad-163">Por exemplo, o *arco* excluirá todos os tópicos com a palavra *arco* nele, como *círculo de arco* , solda de arco de *plasma* ou arco de *treinamento*. Observe que ele não excluirá tópicos nos quais o texto está incluído como parte de uma palavra, como *arquitetura*.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle* , *Plasma arc welding* , or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="1e3ad-164">**Expansão (opcional)** : se você deseja excluir um acrônimo, digite as palavras que o acrônimo significa.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-164">**Expansion (optional)** : If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="1e3ad-165">**MatchType-Exact/partial** : digite se o nome inserido foi um tipo de correspondência *exata* ou *parcial* .</span><span class="sxs-lookup"><span data-stu-id="1e3ad-165">**MatchType-Exact/Partial** : Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="1e3ad-166">Depois de concluir e salvar o arquivo de modelo CSV, selecione **procurar** para localizá-lo e selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="1e3ad-167">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="1e3ad-168">Na página **quem pode ver os tópicos e onde eles podem vê-los** , você configurará a visibilidade do tópico.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="1e3ad-169">Na configuração **quem pode ver os tópicos da configuração de rede de conhecimento** , você escolhe quem terá acesso aos detalhes do tópico, como tópicos realçados, cartões de tópicos, respostas de tópicos em pesquisa e páginas de tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="1e3ad-170">Você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-170">You can select:</span></span></br>
    <span data-ttu-id="1e3ad-171">a.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-171">a.</span></span> <span data-ttu-id="1e3ad-172">**Todos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="1e3ad-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="1e3ad-173">b.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-173">b.</span></span> <span data-ttu-id="1e3ad-174">**Apenas pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="1e3ad-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="1e3ad-175">c.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-175">c.</span></span> <span data-ttu-id="1e3ad-176">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="1e3ad-176">**No one**</span></span></br>

    ![Quem pode ver os tópicos](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="1e3ad-178">Embora essa configuração permita que você selecione qualquer usuário em sua organização, somente os usuários que têm licenças de gerenciamento de conhecimento atribuídas poderão exibir tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="1e3ad-179">Na página **permissões para gerenciamento de tópicos** , escolha quem poderá criar, editar ou gerenciar tópicos.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="1e3ad-180">Na seção **quem pode criar e editar tópicos** , você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="1e3ad-181">a.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-181">a.</span></span> <span data-ttu-id="1e3ad-182">**Todos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="1e3ad-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="1e3ad-183">b.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-183">b.</span></span> <span data-ttu-id="1e3ad-184">**Apenas pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="1e3ad-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="1e3ad-185">Na seção **quem pode gerenciar tópicos** , você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="1e3ad-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="1e3ad-186">a.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-186">a.</span></span> <span data-ttu-id="1e3ad-187">**Todos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="1e3ad-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="1e3ad-188">b.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-188">b.</span></span> <span data-ttu-id="1e3ad-189">**Pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="1e3ad-189">**Selected people or security groups**</span></span></br>

    ![Permissões para gerenciamento de tópicos](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="1e3ad-191">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="1e3ad-192">Na página **criar centro de tópicos** , você pode criar seu site do centro de tópicos no qual as páginas de tópicos podem ser exibidas e os tópicos podem ser gerenciados.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="1e3ad-193">Na caixa **nome da central de tópicos** , digite um nome para o seu centro de tópico.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="1e3ad-194">Opcionalmente, você pode digitar uma descrição curta na caixa **Descrição do site** .</span><span class="sxs-lookup"><span data-stu-id="1e3ad-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="1e3ad-195">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-195">Select **Next**.</span></span></br>

   ![Criar centro de conhecimento](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="1e3ad-197">Na página **Revisão e acabamento** , você pode olhar para a configuração selecionada e escolher fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="1e3ad-198">Se estiver satisfeito com as suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Concluir e revisar](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="1e3ad-200">A página **da rede de conhecimento ativada** será exibida, confirmando que o sistema agora vai começar a analisar os sites selecionados para tópicos e criar o site do centro de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="1e3ad-201">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-201">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="1e3ad-203">Você retornará à página **conectar pessoas para o conhecimento** .</span><span class="sxs-lookup"><span data-stu-id="1e3ad-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="1e3ad-204">A partir desta página, é possível selecionar **Gerenciar** para fazer quaisquer alterações em suas configurações.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configurações aplicadas](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="1e3ad-206">Após a instalação, um administrador pode [fazer alterações nas configurações de gerenciamento de conhecimento selecionadas](topic-experiences-discovery.md) a qualquer momento, retornando a essa página.</span><span class="sxs-lookup"><span data-stu-id="1e3ad-206">After setup, an admin can [make changes to your selected knowledge management settings](topic-experiences-discovery.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="1e3ad-207">Confira também</span><span class="sxs-lookup"><span data-stu-id="1e3ad-207">See also</span></span>



  






