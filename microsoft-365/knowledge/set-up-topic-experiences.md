---
title: Configurar experiências de tópico no Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como configurar experiências de tópico no Microsoft 365
ms.openlocfilehash: e11f0b75556a4a8ac0ffa40269d7166258128daf
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698550"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="0c2c2-103">Configurar experiências de tópico no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c2c2-103">Set up topic experiences in Microsoft 365</span></span>

<span data-ttu-id="0c2c2-104">Você pode usar o centro de administração do Microsoft 365 para configurar e configurar [experiências de tópico](topic-experiences-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0c2c2-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="0c2c2-105">É importante planejar a melhor maneira de configurar e configurar tópicos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="0c2c2-106">Certifique-se de ler [planejar experiências de tópico](plan-topic-experiences.md) antes de começar os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="0c2c2-107">Você deve ser um administrador global ou administrador do SharePoint para acessar o centro de administração do Microsoft 365 e configurar experiências de tópico.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="0c2c2-108">Configurar experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="0c2c2-108">Set up topic experiences</span></span>

<span data-ttu-id="0c2c2-109">Para configurar experiências de tópico no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c2c2-109">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="0c2c2-110">No [centro de administração do Microsoft 365](https://admin.microsoft.com), selecione **configuração** e, em seguida, exiba a seção **arquivos e conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="0c2c2-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="0c2c2-111">Na seção **arquivos e conteúdo** , clique em **conectar pessoas a conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-111">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Conectar pessoas a conhecimento](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="0c2c2-113">Na página **conectar pessoas a conhecimento** **, clique em introdução para** orientá-lo no processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-113">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Introdução](../media/k-get-started.png) 

4. <span data-ttu-id="0c2c2-115">Na página **escolha como a rede de conhecimento pode encontrar tópicos** , você configurará a descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-115">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="0c2c2-116">Na seção **selecionar fontes de tópicos do SharePoint** , selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-116">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="0c2c2-117">Escolha entre:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-117">Choose from:</span></span>
    - <span data-ttu-id="0c2c2-118">**Todos os sites**: todos os sites do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-118">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="0c2c2-119">Isso inclui sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-119">This includes current and future sites.</span></span>
    - <span data-ttu-id="0c2c2-120">**Todos, exceto sites selecionados**: digite os nomes dos sites que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-120">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="0c2c2-121">Você também pode carregar uma lista de sites que deseja recusar da descoberta.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-121">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="0c2c2-122">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-122">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="0c2c2-123">**Somente sites selecionados**: digite os nomes dos sites que você deseja incluir.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-123">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="0c2c2-124">Você também pode carregar uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-124">You can also upload a list of sites.</span></span> <span data-ttu-id="0c2c2-125">Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-125">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="0c2c2-126">**Nenhum site**: não inclua nenhum site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-126">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Escolher como localizar tópicos](../media/ksetup1.png) 
   
5. <span data-ttu-id="0c2c2-128">Na seção **excluir tópicos por nome** , você pode adicionar nomes de tópicos que você deseja excluir da descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-128">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="0c2c2-129">Use essa configuração para evitar que informações confidenciais sejam incluídas como tópicos.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-129">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="0c2c2-130">As opções são:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-130">The options are:</span></span>
    - <span data-ttu-id="0c2c2-131">**Não excluir nenhum tópico**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-131">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="0c2c2-132">**Excluir tópicos por nome**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-132">**Exclude topics by name**</span></span>

    ![Excluir tópicos](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="0c2c2-134">(Os gerentes de conhecimento também podem excluir tópicos no centro de tópicos após a descoberta.)</span><span class="sxs-lookup"><span data-stu-id="0c2c2-134">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="0c2c2-135">Como excluir tópicos por nome</span><span class="sxs-lookup"><span data-stu-id="0c2c2-135">How to exclude topics by name</span></span>    

    <span data-ttu-id="0c2c2-136">Se você precisar excluir tópicos, depois de selecionar **excluir tópicos por nome**, selecione baixar o modelo. csv e atualizá-lo com a lista de tópicos que você deseja excluir dos resultados da descoberta.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-136">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="0c2c2-138">No modelo CSV, insira as seguintes informações sobre os tópicos que você deseja excluir:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-138">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="0c2c2-139">**Name**: digite o nome do tópico que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-139">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="0c2c2-140">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-140">There are two ways to do this:</span></span>
        - <span data-ttu-id="0c2c2-141">Correspondência exata: você pode incluir o nome exato ou o acrônimo (por exemplo, *contoso* ou *ATL*).</span><span class="sxs-lookup"><span data-stu-id="0c2c2-141">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="0c2c2-142">Correspondência parcial: você pode excluir todos os tópicos que possuem uma palavra específica.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-142">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="0c2c2-143">Por exemplo, o *arco* excluirá todos os tópicos com a palavra *arco* nele, como *círculo de arco*, solda de arco de *plasma* ou arco de *treinamento*. Observe que ele não excluirá tópicos nos quais o texto está incluído como parte de uma palavra, como *arquitetura*.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-143">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="0c2c2-144">**Significa (opcional)**: se você deseja excluir um acrônimo, digite as palavras que o acrônimo significa.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-144">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="0c2c2-145">**MatchType-Exact/partial**: digite se o nome inserido foi um tipo de correspondência *exata* ou *parcial* .</span><span class="sxs-lookup"><span data-stu-id="0c2c2-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="0c2c2-146">Depois de concluir e salvar seu arquivo. csv, selecione **procurar** para localizá-lo e selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-146">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="0c2c2-147">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-147">Select **Next**.</span></span>

6. <span data-ttu-id="0c2c2-148">Na página **quem pode ver os tópicos e onde eles podem vê-los** , você configurará a visibilidade do tópico.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-148">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="0c2c2-149">Na configuração **quem pode ver os tópicos da configuração de rede de conhecimento** , você escolhe quem terá acesso aos detalhes do tópico, como tópicos realçados, cartões de tópicos, respostas de tópicos em pesquisa e páginas de tópicos.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-149">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="0c2c2-150">Você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-150">You can select:</span></span>
    - <span data-ttu-id="0c2c2-151">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-151">**Everyone in my organization**</span></span>
    - <span data-ttu-id="0c2c2-152">**Apenas pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-152">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="0c2c2-153">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-153">**No one**</span></span>

    ![Quem pode ver os tópicos](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="0c2c2-155">Embora essa configuração permita que você selecione qualquer usuário da sua organização, somente os usuários que tiverem o tópico experiências de licenças atribuídas poderão exibir tópicos.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-155">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="0c2c2-156">Na página **permissões para gerenciamento de tópicos** , escolha quem poderá criar, editar ou gerenciar tópicos.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-156">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="0c2c2-157">Na seção **quem pode criar e editar tópicos** , você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-157">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="0c2c2-158">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-158">**Everyone in my organization**</span></span>
    - <span data-ttu-id="0c2c2-159">**Apenas pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-159">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="0c2c2-160">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-160">**No one**</span></span>

    ![Permissões para gerenciamento de tópicos, que podem criar e editar tópicos](../media/ksetup3.png) 

8. <span data-ttu-id="0c2c2-162">Na seção **quem pode gerenciar tópicos** , você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-162">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="0c2c2-163">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-163">**Everyone in my organization**</span></span>
    - <span data-ttu-id="0c2c2-164">**Apenas pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="0c2c2-164">**Only selected people or security groups**</span></span>

    ![Permissões para gerenciamento de tópicos](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="0c2c2-166">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-166">Select **Next**.</span></span>

9. <span data-ttu-id="0c2c2-167">Na página **criar centro de tópicos** , você pode criar seu site do centro de tópicos no qual as páginas de tópicos podem ser exibidas e os tópicos podem ser gerenciados.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-167">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="0c2c2-168">Na caixa **nome do site** , digite um nome para o seu centro de tópico.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-168">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="0c2c2-169">Opcionalmente, você pode digitar uma descrição curta na caixa **Descrição** .</span><span class="sxs-lookup"><span data-stu-id="0c2c2-169">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="0c2c2-170">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-170">Select **Next**.</span></span>

   ![Criar centro de conhecimento](../media/ksetup4.png)  

10. <span data-ttu-id="0c2c2-172">Na página **Revisão e acabamento**, você pode olhar para a configuração selecionada e escolher fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-172">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="0c2c2-173">Se estiver satisfeito com as suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-173">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="0c2c2-174">A página **da rede de conhecimento ativada** será exibida, confirmando que o sistema agora vai começar a analisar os sites selecionados para tópicos e criar o site do centro de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-174">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="0c2c2-175">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-175">Select **Done**.</span></span>

12. <span data-ttu-id="0c2c2-176">Você retornará à página **conectar pessoas para o conhecimento** .</span><span class="sxs-lookup"><span data-stu-id="0c2c2-176">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="0c2c2-177">A partir desta página, é possível selecionar **Gerenciar** para fazer quaisquer alterações em suas configurações.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-177">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configurações aplicadas](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="0c2c2-179">Atribua licenças</span><span class="sxs-lookup"><span data-stu-id="0c2c2-179">Assign licenses</span></span>

<span data-ttu-id="0c2c2-180">Depois de configurar as experiências de tópico, você deve atribuir licenças para os usuários que utilizarão experiências de tópico.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-180">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="0c2c2-181">Somente os usuários com uma licença podem ver informações sobre tópicos, incluindo realces, cartões de tópicos, páginas de tópicos e o tópico central.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-181">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="0c2c2-182">Atribuição de licenças:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-182">To assign licenses:</span></span>

1. <span data-ttu-id="0c2c2-183">No Centro de administração do Microsoft 365, em **Usuários**, clique em **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-183">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="0c2c2-184">Selecione os usuários que você deseja licenciar, e clique **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-184">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="0c2c2-185">Selecione **Atribuir mais**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-185">Select **Assign more**.</span></span>

4. <span data-ttu-id="0c2c2-186">Em **licenças**, selecione **experiências de tópico**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-186">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="0c2c2-187">Em **aplicativos**, certifique-se **de que a pesquisa de conectores do Graph com** as experiências de índice e **tópico** esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c2c2-188">![Licenças do SharePoint Syntex no Centro de administração do Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="0c2c2-188">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="0c2c2-189">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="0c2c2-189">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="0c2c2-190">Gerenciar experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="0c2c2-190">Manage topic experiences</span></span>

<span data-ttu-id="0c2c2-191">Depois de configurar experiências de tópico, você poderá alterar as configurações escolhidas durante a instalação no centro de [Administração do Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span><span class="sxs-lookup"><span data-stu-id="0c2c2-191">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="0c2c2-192">Confira as seguintes referências:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-192">See the following references:</span></span>

- [<span data-ttu-id="0c2c2-193">Gerenciar descoberta de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c2c2-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="0c2c2-194">Gerenciar a visibilidade de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c2c2-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="0c2c2-195">Gerenciar permissões de tópico no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c2c2-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="0c2c2-196">Alterar o nome da central de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c2c2-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="0c2c2-197">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c2c2-197">See also</span></span>

[<span data-ttu-id="0c2c2-198">Visão geral da experiência do tópico</span><span class="sxs-lookup"><span data-stu-id="0c2c2-198">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
