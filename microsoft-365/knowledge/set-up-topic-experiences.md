---
title: Configurar tópicos do Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Saiba como configurar tópicos do Microsoft Viva
ms.openlocfilehash: 6bd0d3eca653ae44e46b410ef3ac55fe11629a6b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150495"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="4aea7-103">Configurar tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="4aea7-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="4aea7-104">Você pode usar o Centro de administração do Microsoft 365 para configurar e configurar [tópicos.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4aea7-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="4aea7-105">É importante planejar a melhor maneira de configurar e configurar tópicos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4aea7-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="4aea7-106">Certifique-se de [ler Plan for Microsoft Viva Topics](plan-topic-experiences.md) antes de começar os procedimentos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="4aea7-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="4aea7-107">Você deve estar inscrito nos [Tópicos](https://www.microsoft.com/microsoft-viva/topics) do Viva e ser um administrador global ou administrador do SharePoint para acessar o centro de administração do Microsoft 365 e configurar Tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="4aea7-108">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="4aea7-108">Video demonstration</span></span>

<span data-ttu-id="4aea7-109">Este vídeo mostra o processo de configuração de tópicos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4aea7-109">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="4aea7-110">Configurar tópicos</span><span class="sxs-lookup"><span data-stu-id="4aea7-110">Set up Topics</span></span>

<span data-ttu-id="4aea7-111">Para configurar tópicos</span><span class="sxs-lookup"><span data-stu-id="4aea7-111">To set up Topics</span></span>

1. <span data-ttu-id="4aea7-112">No Centro [de administração do Microsoft 365,](https://admin.microsoft.com)selecione **Instalação** e, em seguida, veja a seção **Arquivos e** conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4aea7-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="4aea7-113">Na seção **Arquivos e conteúdo,** clique em **Conectar pessoas ao conhecimento.**</span><span class="sxs-lookup"><span data-stu-id="4aea7-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Conectar as pessoas ao conhecimento](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="4aea7-115">Na página **Conectar pessoas ao conhecimento,** clique em **Começar** para ajudar você durante o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="4aea7-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Introdução](../media/k-get-started.png) 

4. <span data-ttu-id="4aea7-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span><span class="sxs-lookup"><span data-stu-id="4aea7-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="4aea7-118">Na seção **Selecionar fontes de tópicos do SharePoint,** selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta.</span><span class="sxs-lookup"><span data-stu-id="4aea7-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="4aea7-119">Escolha entre:</span><span class="sxs-lookup"><span data-stu-id="4aea7-119">Choose from:</span></span>
    - <span data-ttu-id="4aea7-120">**Todos os sites:** todos os sites do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4aea7-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="4aea7-121">Isso inclui sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="4aea7-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="4aea7-122">**Todos, exceto sites selecionados:** digite os nomes dos sites que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="4aea7-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="4aea7-123">Você também pode carregar uma lista de sites que deseja excluir da descoberta.</span><span class="sxs-lookup"><span data-stu-id="4aea7-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="4aea7-124">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="4aea7-125">**Somente sites selecionados:** digite os nomes dos sites que você deseja incluir.</span><span class="sxs-lookup"><span data-stu-id="4aea7-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="4aea7-126">Você também pode carregar uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="4aea7-126">You can also upload a list of sites.</span></span> <span data-ttu-id="4aea7-127">Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="4aea7-128">**Nenhum site:** não inclua sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4aea7-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Escolher como encontrar tópicos](../media/ksetup1.png) 
   
5. <span data-ttu-id="4aea7-130">Na seção **Excluir tópicos por nome,** você pode adicionar nomes de tópicos que deseja excluir da descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="4aea7-131">Use essa configuração para impedir que informações confidenciais são incluídas como tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="4aea7-132">As opções são:</span><span class="sxs-lookup"><span data-stu-id="4aea7-132">The options are:</span></span>
    - <span data-ttu-id="4aea7-133">**Não exclua nenhum tópico**</span><span class="sxs-lookup"><span data-stu-id="4aea7-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="4aea7-134">**Excluir tópicos por nome**</span><span class="sxs-lookup"><span data-stu-id="4aea7-134">**Exclude topics by name**</span></span>

    ![Excluir tópicos](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="4aea7-136">(Os gerentes de conhecimento também podem excluir tópicos no centro de tópicos após a descoberta.)</span><span class="sxs-lookup"><span data-stu-id="4aea7-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="4aea7-137">Como excluir tópicos por nome</span><span class="sxs-lookup"><span data-stu-id="4aea7-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="4aea7-138">Se você precisar excluir tópicos, depois de selecionar Excluir **tópicos** por nome, baixe o modelo .csv e atualize-o com a lista de tópicos que você deseja excluir dos resultados de descoberta.</span><span class="sxs-lookup"><span data-stu-id="4aea7-138">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="4aea7-140">No modelo CSV, insira as seguintes informações sobre os tópicos que você deseja excluir:</span><span class="sxs-lookup"><span data-stu-id="4aea7-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="4aea7-141">**Nome:** digite o nome do tópico que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="4aea7-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="4aea7-142">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="4aea7-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="4aea7-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span><span class="sxs-lookup"><span data-stu-id="4aea7-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="4aea7-144">Parciais: você pode excluir todos os tópicos que têm uma palavra específica.</span><span class="sxs-lookup"><span data-stu-id="4aea7-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="4aea7-145">Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavras nele, como arco *círculo,* arco *de Arc arc arc ou* arco *de treinamento.* Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, *como* Arquitetura .</span><span class="sxs-lookup"><span data-stu-id="4aea7-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="4aea7-146">**Significa (opcional)**: se você quiser excluir um acrônimo, digite as palavras que o acrônimo significa.</span><span class="sxs-lookup"><span data-stu-id="4aea7-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="4aea7-147">**MatchType-Exact/Partial**: digite se o nome digitado foi um *tipo de* combinação exato *ou* parcial.</span><span class="sxs-lookup"><span data-stu-id="4aea7-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="4aea7-148">Depois de concluir e salvar o arquivo .csv, selecione **Procurar** para localizá-lo e selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="4aea7-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="4aea7-149">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4aea7-149">Select **Next**.</span></span>

6. <span data-ttu-id="4aea7-150">Nos **tópicos Quem pode ver e onde eles** podem vê-los, você configurará a visibilidade do tópico.</span><span class="sxs-lookup"><span data-stu-id="4aea7-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="4aea7-151">Na configuração Quem pode **ver tópicos,** escolha quem terá acesso aos detalhes do tópico, como tópicos destacados, cartões de tópicos, respostas de tópicos em pesquisa e páginas de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-151">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="4aea7-152">Você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="4aea7-152">You can select:</span></span>
    - <span data-ttu-id="4aea7-153">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="4aea7-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="4aea7-154">**Somente pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="4aea7-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="4aea7-155">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="4aea7-155">**No one**</span></span>

    ![Quem pode ver tópicos](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="4aea7-157">Embora essa configuração permita que você selecione qualquer usuário em sua organização, somente os usuários que têm licenças de Experiências de Tópico atribuídas a eles poderão exibir tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="4aea7-158">Na página **Permissões de gerenciamento de tópicos,** escolha quem poderá criar, editar ou gerenciar tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="4aea7-159">Na seção **Quem pode criar e editar tópicos,** você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="4aea7-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="4aea7-160">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="4aea7-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="4aea7-161">**Somente pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="4aea7-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="4aea7-162">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="4aea7-162">**No one**</span></span>

    ![Permissões para gerenciamento de tópicos, quem pode criar e editar tópicos](../media/ksetup3.png) 

8. <span data-ttu-id="4aea7-164">Na seção **Quem pode gerenciar tópicos,** você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="4aea7-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="4aea7-165">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="4aea7-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="4aea7-166">**Somente pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="4aea7-166">**Only selected people or security groups**</span></span>

    ![Permissões para gerenciamento de tópicos](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="4aea7-168">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4aea7-168">Select **Next**.</span></span>

9. <span data-ttu-id="4aea7-169">Na página **Criar centro de** tópicos, você pode criar seu site central de tópicos no qual as páginas de tópicos podem ser exibidas e os tópicos podem ser gerenciados.</span><span class="sxs-lookup"><span data-stu-id="4aea7-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="4aea7-170">Na caixa **Nome do site,** digite um nome para o centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-170">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="4aea7-171">Opcionalmente, você pode digitar uma breve descrição na caixa **Descrição.**</span><span class="sxs-lookup"><span data-stu-id="4aea7-171">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="4aea7-172">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4aea7-172">Select **Next**.</span></span>

   ![Criar Centro de Conhecimento](../media/ksetup4.png)  

10. <span data-ttu-id="4aea7-174">Na página **Revisão e acabamento**, você pode olhar para a configuração selecionada e escolher fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="4aea7-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="4aea7-175">Se estiver satisfeito com as suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="4aea7-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="4aea7-176">A **página Tópicos do Viva** será exibida, confirmando que agora o sistema começará a analisar os sites selecionados para tópicos e a criar o site central de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-176">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="4aea7-177">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="4aea7-177">Select **Done**.</span></span>

12. <span data-ttu-id="4aea7-178">You'll be returned to your **Connect people to knowledge** page.</span><span class="sxs-lookup"><span data-stu-id="4aea7-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="4aea7-179">A partir desta página, é possível selecionar **Gerenciar** para fazer quaisquer alterações em suas configurações.</span><span class="sxs-lookup"><span data-stu-id="4aea7-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configurações aplicadas](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="4aea7-181">Atribua licenças</span><span class="sxs-lookup"><span data-stu-id="4aea7-181">Assign licenses</span></span>

<span data-ttu-id="4aea7-182">Depois de configurar as experiências de tópico, você deve atribuir licenças para os usuários que usarão Tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-182">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="4aea7-183">Somente os usuários com uma licença podem ver informações sobre tópicos, incluindo destaques, cartões de tópicos, páginas de tópicos e o centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4aea7-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="4aea7-184">Atribuição de licenças:</span><span class="sxs-lookup"><span data-stu-id="4aea7-184">To assign licenses:</span></span>

1. <span data-ttu-id="4aea7-185">No Centro de administração do Microsoft 365, em **Usuários**, clique em **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="4aea7-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="4aea7-186">Selecione os usuários que você deseja licenciar e clique em **Licenças e aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="4aea7-186">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="4aea7-187">Em **Aplicativos,** **certifique-se de que a Pesquisa de Conectores do Graph com Experiências** de Índice e **Tópicos** estão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="4aea7-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

4. <span data-ttu-id="4aea7-188">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="4aea7-188">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="4aea7-189">Gerenciar experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="4aea7-189">Manage topic experiences</span></span>

<span data-ttu-id="4aea7-190">Depois de configurar tópicos, você pode alterar as configurações escolhidas durante a configuração no Centro de administração do [Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="4aea7-190">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="4aea7-191">Consulte as seguintes referências:</span><span class="sxs-lookup"><span data-stu-id="4aea7-191">See the following references:</span></span>

- [<span data-ttu-id="4aea7-192">Gerenciar a descoberta de tópicos nos tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="4aea7-192">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="4aea7-193">Gerenciar visibilidade de tópicos nos tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="4aea7-193">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="4aea7-194">Gerenciar permissões de tópico nos tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="4aea7-194">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="4aea7-195">Alterar o nome do centro de tópicos nos tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="4aea7-195">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="4aea7-196">Confira também</span><span class="sxs-lookup"><span data-stu-id="4aea7-196">See also</span></span>

[<span data-ttu-id="4aea7-197">Visão geral das experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="4aea7-197">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
