---
title: 'Gerenciar sua rede de gerenciamento de conhecimento (versão prévia) '
description: Como configurar o gerenciamento de conhecimento.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 87275dba78ab402a9ea9553198ce1a84072e3351
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540113"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="fa8c8-103">Gerenciar sua rede de gerenciamento de conhecimento (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="fa8c8-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="fa8c8-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="fa8c8-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="fa8c8-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="fa8c8-106">Depois de [Configurar o gerenciamento de conhecimento](set-up-knowledge-network.md), a qualquer momento depois, um administrador pode fazer ajustes nas suas definições de configuração através do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-106">After you [set up knowledge management](set-up-knowledge-network.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="fa8c8-107">Por exemplo, você pode precisar ajustar suas configurações para qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="fa8c8-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="fa8c8-108">Adicione novas fontes do SharePoint aos tópicos de meus.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="fa8c8-109">Alterar quais usuários terão acesso aos tópicos.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="fa8c8-110">Alterar quais usuários têm permissões para executar tarefas no centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="fa8c8-111">Alterar o nome do seu centro de tópico</span><span class="sxs-lookup"><span data-stu-id="fa8c8-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="fa8c8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa8c8-112">Requirements</span></span> 
<span data-ttu-id="fa8c8-113">Você deve ter permissões de administrador global ou administrador do SharePoint para poder acessar o centro de administração do Microsoft 365 e gerenciar tarefas de conhecimento organizacional.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="fa8c8-114">Para acessar as configurações de gerenciamento de conhecimento:</span><span class="sxs-lookup"><span data-stu-id="fa8c8-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="fa8c8-115">No centro de administração do Microsoft 365, selecione **configuração**e, em seguida, exiba a seção de **conhecimento organizacional** .</span><span class="sxs-lookup"><span data-stu-id="fa8c8-115">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="fa8c8-116">Na seção **conhecimento organizacional** , clique em **conectar pessoas a conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Conectar pessoas a conhecimento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="fa8c8-118">Na página **conectar pessoas a conhecimento** , selecione **gerenciar** para abrir o painel **configurações de rede de conhecimento** .</span><span class="sxs-lookup"><span data-stu-id="fa8c8-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![conhecimento-rede – configurações](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="fa8c8-120">Alterar o modo como a rede de conhecimento pode encontrar tópicos</span><span class="sxs-lookup"><span data-stu-id="fa8c8-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="fa8c8-121">Selecione a guia **descoberta de tópico** se quiser atualizar suas escolhas para as fontes de tópico do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="fa8c8-122">Essa configuração permite que você selecione os sites do SharePoint em seu locatário que serão rastreados e extraídos para tópicos.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="fa8c8-123">Na guia **descoberta de tópico** , em **selecionar fontes de tópicos do SharePoint**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-123">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="fa8c8-124">Na página **selecionar fontes de tópicos do SharePoint** , selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="fa8c8-125">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="fa8c8-125">This includes:</span></span></br>
    <span data-ttu-id="fa8c8-126">a.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-126">a.</span></span> <span data-ttu-id="fa8c8-127">**Todos os sites**: todos os sites do SharePoint em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-127">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="fa8c8-128">Isso captura sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="fa8c8-129">b.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-129">b.</span></span> <span data-ttu-id="fa8c8-130">**Todos, exceto sites selecionados**: digite os nomes dos sites que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-130">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="fa8c8-131">Você também pode carregar uma lista de sites que deseja recusar da descoberta.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="fa8c8-132">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="fa8c8-133">c.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-133">c.</span></span> <span data-ttu-id="fa8c8-134">**Somente sites selecionados**: digite os nomes dos sites que você deseja incluir.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-134">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="fa8c8-135">Você também pode carregar uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-135">You can also upload a list of sites.</span></span> <span data-ttu-id="fa8c8-136">Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Escolher como localizar tópicos](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="fa8c8-138">Se você tiver um número de sites que você deseja excluir (se você selecionar **todos, exceto os sites selecionados**) ou incluir (se você selecionou **apenas sites selecionados**), poderá optar por carregar um arquivo CSV com os nomes e URLs dos sites.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites**) or include (if you selected **Only selected sites**), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="fa8c8-139">Você pode selecionar **baixar modelo de site. csv** se quiser usar o arquivo de modelo CSV.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="fa8c8-140">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="fa8c8-141">Alterar quem pode ver os tópicos em sua organização</span><span class="sxs-lookup"><span data-stu-id="fa8c8-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="fa8c8-142">Selecione a guia **descoberta de tópico** se você deseja atualizar quem em sua organização pode ver tópicos descobertos nos resultados da pesquisa e quando os tópicos estão realçados em conteúdo como páginas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="fa8c8-143">Na guia **descoberta de tópicos** , em **quem pode ver os tópicos na rede de conhecimento**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network**, select **Edit**.</span></span>
2. <span data-ttu-id="fa8c8-144">Na página **quem pode ver os tópicos da página da rede de conhecimento** , você escolhe quem terá acesso aos detalhes do tópico, como tópicos realçados, cartões de tópicos, respostas de tópicos em pesquisa e páginas de tópicos.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="fa8c8-145">Você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="fa8c8-145">You can select:</span></span></br>
    <span data-ttu-id="fa8c8-146">a.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-146">a.</span></span> <span data-ttu-id="fa8c8-147">**Todos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="fa8c8-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="fa8c8-148">b.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-148">b.</span></span> <span data-ttu-id="fa8c8-149">**Apenas pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="fa8c8-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="fa8c8-150">c.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-150">c.</span></span> <span data-ttu-id="fa8c8-151">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="fa8c8-151">**No one**</span></span></br>

    ![Quem pode ver os tópicos](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="fa8c8-153">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="fa8c8-154">Embora essa configuração permita que você selecione qualquer usuário em sua organização, somente os usuários que têm licenças de gerenciamento de conhecimento atribuídas poderão exibir tópicos.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="fa8c8-155">Alterar quem tem permissões para executar tarefas no centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="fa8c8-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="fa8c8-156">Selecione a guia **permissões de tópico** se quiser atualizar quem tem permissões para fazer o seguinte na página central de tópicos:</span><span class="sxs-lookup"><span data-stu-id="fa8c8-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="fa8c8-157">Quais usuários podem criar e editar tópicos: criar novos tópicos que não foram encontrados durante a descoberta ou editar detalhes da página de tópico existente.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="fa8c8-158">Quais usuários podem gerenciar tópicos: confirmar ou rejeitar tópicos descobertos.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="fa8c8-159">Para atualizar as permissões para criar e editar tópicos:</span><span class="sxs-lookup"><span data-stu-id="fa8c8-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="fa8c8-160">Na guia **permissões de tópico** , em **quem pode criar e editar tópicos**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-160">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="fa8c8-161">Na página **quem pode criar e editar tópicos** , você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="fa8c8-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="fa8c8-162">a.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-162">a.</span></span> <span data-ttu-id="fa8c8-163">**Todos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="fa8c8-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="fa8c8-164">b.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-164">b.</span></span> <span data-ttu-id="fa8c8-165">**Apenas pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="fa8c8-165">**Only selected people or security groups**</span></span></br>

    ![Criar e editar tópicos](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="fa8c8-167">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-167">Select **Save**.</span></span></br>

<span data-ttu-id="fa8c8-168">Para atualizar as permissões para gerenciar tópicos:</span><span class="sxs-lookup"><span data-stu-id="fa8c8-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="fa8c8-169">Na guia **permissões de tópico** , em **quem pode gerenciar tópicos**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-169">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="fa8c8-170">Na página **quem pode gerenciar os tópicos** , você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="fa8c8-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="fa8c8-171">a.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-171">a.</span></span> <span data-ttu-id="fa8c8-172">**Todos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="fa8c8-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="fa8c8-173">b.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-173">b.</span></span> <span data-ttu-id="fa8c8-174">**Pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="fa8c8-174">**Selected people or security groups**</span></span></br>

    ![Gerenciar tópicos](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="fa8c8-176">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="fa8c8-177">Atualizar o nome da central de tópicos</span><span class="sxs-lookup"><span data-stu-id="fa8c8-177">Update your topic center name</span></span>

<span data-ttu-id="fa8c8-178">Selecione a guia **central de tópicos** se você deseja atualizar o nome do seu centro de tópico.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="fa8c8-179">Na guia **central de tópicos** , em **nome da central de tópicos**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-179">On the **Topic center** tab, under **Topic center name**, select **Edit**.</span></span>
2. <span data-ttu-id="fa8c8-180">Na página **Editar nome da central de tópicos** , na caixa **nome da central de tópicos** , digite o novo nome para o seu centro de tópico.</span><span class="sxs-lookup"><span data-stu-id="fa8c8-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="fa8c8-181">Selecione **Salvar**</span><span class="sxs-lookup"><span data-stu-id="fa8c8-181">Select **Save**</span></span>

    ![Editar nome da central de tópicos](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="fa8c8-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="fa8c8-183">See also</span></span>



  






