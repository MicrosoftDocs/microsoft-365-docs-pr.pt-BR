---
title: 'Configurar o gerenciamento de conhecimento (versão prévia) '
description: Como configurar o gerenciamento de conhecimento.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612543"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="d8a70-103">Configurar o gerenciamento de conhecimento (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="d8a70-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="d8a70-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="d8a70-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d8a70-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="d8a70-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="d8a70-106">Você pode usar o centro de administração do Microsoft 365 para configurar e configurar o [Gerenciamento de conhecimento](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8a70-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="d8a70-107">É importante planejar a melhor maneira de configurar e configurar o gerenciamento de conhecimento em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="d8a70-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="d8a70-108">Por exemplo, você precisará fazer considerações sobre o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d8a70-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="d8a70-109">Quais sites do SharePoint você deseja analisar os tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="d8a70-110">Para quais usuários você deseja tornar os tópicos visíveis.</span><span class="sxs-lookup"><span data-stu-id="d8a70-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="d8a70-111">Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="d8a70-112">Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="d8a70-113">Que nome você deseja dar à sua central de tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="d8a70-114">Você pode achar útil criar grupos de segurança para atribuir aos usuários as permissões necessárias para exibir tópicos, gerenciar tópico e criar e editar tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="d8a70-115">Um administrador também pode [fazer alterações nas configurações selecionadas a qualquer momento após a configuração](manage-knowledge-network.md) , por meio das configurações de gerenciamento de conhecimento no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8a70-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="d8a70-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8a70-116">Requirements</span></span> 
<span data-ttu-id="d8a70-117">Você deve ter permissões de administrador global ou administrador do SharePoint para poder acessar o centro de administração do Microsoft 365 e configurar tarefas de conhecimento organizacional.</span><span class="sxs-lookup"><span data-stu-id="d8a70-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="d8a70-118">Configurar sua rede de conhecimento</span><span class="sxs-lookup"><span data-stu-id="d8a70-118">Set up your knowledge network</span></span>

<span data-ttu-id="d8a70-119">Configurar sua rede de conhecimento orienta você por meio do seguinte:</span><span class="sxs-lookup"><span data-stu-id="d8a70-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="d8a70-120">Descoberta de tópico: selecionar fontes e tópicos de tópico para excluir da descoberta.</span><span class="sxs-lookup"><span data-stu-id="d8a70-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="d8a70-121">Visibilidade do tópico: selecionar quem pode exibir tópicos como destaques, nas páginas de pesquisa e tópico.</span><span class="sxs-lookup"><span data-stu-id="d8a70-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="d8a70-122">Permissões de tópico: selecionar quem pode criar, editar e gerenciar tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="d8a70-123">Centro de tópicos: Crie seu centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="d8a70-124">Revisão: Verifique e aplique suas configurações.</span><span class="sxs-lookup"><span data-stu-id="d8a70-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="d8a70-125">Para configurar sua rede de conhecimento:</span><span class="sxs-lookup"><span data-stu-id="d8a70-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="d8a70-126">No centro de administração do Microsoft 365 (admin.microsoft.com), selecione **configuração**e, em seguida, exiba a seção de **conhecimento organizacional** .</span><span class="sxs-lookup"><span data-stu-id="d8a70-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="d8a70-127">Na seção **conhecimento organizacional** , clique em **conectar pessoas a conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="d8a70-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Conectar pessoas a conhecimento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="d8a70-129">Na página **conectar pessoas a conhecimento** **, clique em introdução para** orientá-lo no processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="d8a70-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Introdução](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="d8a70-131">Na página **escolha como a rede de conhecimento pode encontrar tópicos** , você configurará a descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="d8a70-132">Na seção **selecionar fontes de tópicos do SharePoint** , selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta.</span><span class="sxs-lookup"><span data-stu-id="d8a70-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="d8a70-133">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="d8a70-133">This includes:</span></span></br>
    <span data-ttu-id="d8a70-134">a.</span><span class="sxs-lookup"><span data-stu-id="d8a70-134">a.</span></span> <span data-ttu-id="d8a70-135">**Todos os sites**: todos os sites do SharePoint em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="d8a70-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="d8a70-136">Isso captura sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="d8a70-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="d8a70-137">b.</span><span class="sxs-lookup"><span data-stu-id="d8a70-137">b.</span></span> <span data-ttu-id="d8a70-138">**Todos, exceto sites selecionados**: digite os nomes dos sites que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="d8a70-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="d8a70-139">Você também pode carregar uma lista de sites que deseja recusar da descoberta.</span><span class="sxs-lookup"><span data-stu-id="d8a70-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="d8a70-140">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="d8a70-141">c.</span><span class="sxs-lookup"><span data-stu-id="d8a70-141">c.</span></span> <span data-ttu-id="d8a70-142">**Somente sites selecionados**: digite os nomes dos sites que você deseja incluir.</span><span class="sxs-lookup"><span data-stu-id="d8a70-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="d8a70-143">Você também pode carregar uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="d8a70-143">You can also upload a list of sites.</span></span> <span data-ttu-id="d8a70-144">Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Escolher como localizar tópicos](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="d8a70-146">Na seção **excluir tópicos por nome** , você pode optar por incluir nomes de tópicos que não deseja que estejam nos resultados detectados.</span><span class="sxs-lookup"><span data-stu-id="d8a70-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="d8a70-147">Use essa configuração para impedir que tópicos confidenciais sejam incluídos como parte da rede de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="d8a70-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="d8a70-148">As opções incluem:</span><span class="sxs-lookup"><span data-stu-id="d8a70-148">Your options include:</span></span></br>
    <span data-ttu-id="d8a70-149">a.</span><span class="sxs-lookup"><span data-stu-id="d8a70-149">a.</span></span> <span data-ttu-id="d8a70-150">**Não excluir nenhum tópico**</span><span class="sxs-lookup"><span data-stu-id="d8a70-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="d8a70-151">b.</span><span class="sxs-lookup"><span data-stu-id="d8a70-151">b.</span></span> <span data-ttu-id="d8a70-152">**Excluir tópico que contenha estes termos**: se você tiver tópicos que você não deseja mostrar aos usuários como parte da rede de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="d8a70-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="d8a70-153">– Baixar o modelo fornecido.</span><span class="sxs-lookup"><span data-stu-id="d8a70-153">- Download the provided template.</span></span>
   <span data-ttu-id="d8a70-154">– Insira os nomes dos tópicos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="d8a70-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="d8a70-155">Você deve indicar o tipo de correspondência como Exact ou partial.</span><span class="sxs-lookup"><span data-stu-id="d8a70-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="d8a70-156">Correspondência exata significa que os tópicos que se encaixam no termo exato serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="d8a70-157">A correspondência parcial é mais estrita e significa que os tópicos que contêm o termo serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="d8a70-158">Por exemplo, se você inserir *Doc* como o nome do tópico, o *assembly doc* será excluído enquanto o *Docker* não.</span><span class="sxs-lookup"><span data-stu-id="d8a70-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="d8a70-159">Os nomes dos tópicos não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d8a70-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="d8a70-160">-Selecione  **+**   para importar o arquivo CSV concluído.</span><span class="sxs-lookup"><span data-stu-id="d8a70-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="d8a70-161">Em seguida, selecione **carregar**.</span><span class="sxs-lookup"><span data-stu-id="d8a70-161">Then select **Upload**.</span></span> <span data-ttu-id="d8a70-162">Você verá uma marca de seleção verde se o arquivo tiver sido processado com êxito.</span><span class="sxs-lookup"><span data-stu-id="d8a70-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="d8a70-163">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d8a70-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="d8a70-164">Na página **quem pode ver os tópicos e onde eles podem vê-los** , você configurará a visibilidade do tópico.</span><span class="sxs-lookup"><span data-stu-id="d8a70-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="d8a70-165">Na configuração **quem pode ver os tópicos da configuração de rede de conhecimento** , você escolhe quem terá acesso aos detalhes do tópico, como tópicos realçados, cartões de tópicos, respostas de tópicos em pesquisa e páginas de tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="d8a70-166">Você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="d8a70-166">You can select:</span></span></br>
    <span data-ttu-id="d8a70-167">a.</span><span class="sxs-lookup"><span data-stu-id="d8a70-167">a.</span></span> <span data-ttu-id="d8a70-168">**Todos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="d8a70-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="d8a70-169">b.</span><span class="sxs-lookup"><span data-stu-id="d8a70-169">b.</span></span> <span data-ttu-id="d8a70-170">**Apenas pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="d8a70-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="d8a70-171">c.</span><span class="sxs-lookup"><span data-stu-id="d8a70-171">c.</span></span> <span data-ttu-id="d8a70-172">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="d8a70-172">**No one**</span></span></br>

    ![Quem pode ver os tópicos](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="d8a70-174">Embora essa configuração permita que você selecione qualquer usuário em sua organização, somente os usuários que têm licenças de gerenciamento de conhecimento atribuídas poderão exibir tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="d8a70-175">Na página **permissões para gerenciamento de tópicos** , escolha quem poderá criar, editar ou gerenciar tópicos.</span><span class="sxs-lookup"><span data-stu-id="d8a70-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="d8a70-176">Na seção **quem pode criar e editar tópicos** , você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="d8a70-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="d8a70-177">a.</span><span class="sxs-lookup"><span data-stu-id="d8a70-177">a.</span></span> <span data-ttu-id="d8a70-178">**Todos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="d8a70-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="d8a70-179">b.</span><span class="sxs-lookup"><span data-stu-id="d8a70-179">b.</span></span> <span data-ttu-id="d8a70-180">**Apenas pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="d8a70-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="d8a70-181">Na seção **quem pode gerenciar tópicos** , você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="d8a70-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="d8a70-182">a.</span><span class="sxs-lookup"><span data-stu-id="d8a70-182">a.</span></span> <span data-ttu-id="d8a70-183">**Todos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="d8a70-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="d8a70-184">b.</span><span class="sxs-lookup"><span data-stu-id="d8a70-184">b.</span></span> <span data-ttu-id="d8a70-185">**Pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="d8a70-185">**Selected people or security groups**</span></span></br>

    ![Permissões para gerenciamento de tópicos](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="d8a70-187">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d8a70-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="d8a70-188">Na página **criar centro de tópicos** , você pode criar seu site do centro de tópicos no qual as páginas de tópicos podem ser exibidas e os tópicos podem ser gerenciados.</span><span class="sxs-lookup"><span data-stu-id="d8a70-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="d8a70-189">Na caixa **nome da central de tópicos** , digite um nome para o seu centro de tópico.</span><span class="sxs-lookup"><span data-stu-id="d8a70-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="d8a70-190">Opcionalmente, você pode digitar uma descrição curta na caixa **Descrição do site** .</span><span class="sxs-lookup"><span data-stu-id="d8a70-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="d8a70-191">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d8a70-191">Select **Next**.</span></span></br>

   ![Criar centro de conhecimento](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="d8a70-193">Na página **revisão e término** , você pode examinar a configuração selecionada e optar por fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="d8a70-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="d8a70-194">Se estiver satisfeito com suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="d8a70-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Concluir e revisar](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="d8a70-196">A página **da rede de conhecimento ativada** será exibida, confirmando que o sistema agora vai começar a analisar os sites selecionados para tópicos e criar o site do centro de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="d8a70-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="d8a70-197">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d8a70-197">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="d8a70-199">Você retornará à página **conectar pessoas para o conhecimento** .</span><span class="sxs-lookup"><span data-stu-id="d8a70-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="d8a70-200">Nessa página, você pode selecionar **gerenciar** para fazer quaisquer alterações nas suas definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="d8a70-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configurações aplicadas](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="d8a70-202">Após a instalação, um administrador pode [fazer alterações nas configurações de gerenciamento de conhecimento selecionadas](manage-knowledge-network.md) a qualquer momento, retornando a essa página.</span><span class="sxs-lookup"><span data-stu-id="d8a70-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="d8a70-203">Confira também</span><span class="sxs-lookup"><span data-stu-id="d8a70-203">See also</span></span>



  






