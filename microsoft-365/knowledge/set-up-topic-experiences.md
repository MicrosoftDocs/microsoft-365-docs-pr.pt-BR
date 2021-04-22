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
ms.openlocfilehash: 19395cf3a9ecc991f08f375425803cb81a2a1d35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930216"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="55416-103">Configurar tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="55416-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="55416-104">Você pode usar o Centro de administração do Microsoft 365 para configurar e configurar [Tópicos.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="55416-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="55416-105">É importante planejar a melhor maneira de configurar e configurar tópicos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="55416-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="55416-106">Leia Plan [for Microsoft Viva Topics](plan-topic-experiences.md) antes de começar os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="55416-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="55416-107">Você deve estar inscrito em [Tópicos do Viva](https://www.microsoft.com/microsoft-viva/topics) e ser um administrador global ou administrador do SharePoint para acessar o centro de administração do Microsoft 365 e configurar Tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="55416-108">Se você configurou o SharePoint para [exigir dispositivos](/sharepoint/control-access-from-unmanaged-devices)gerenciados, certifique-se de configurar Tópicos de um dispositivo gerenciado.</span><span class="sxs-lookup"><span data-stu-id="55416-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="55416-109">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="55416-109">Video demonstration</span></span>

<span data-ttu-id="55416-110">Este vídeo mostra o processo de configuração de Tópicos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55416-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="55416-111">Atribua licenças</span><span class="sxs-lookup"><span data-stu-id="55416-111">Assign licenses</span></span>

<span data-ttu-id="55416-112">Você deve atribuir licenças para os usuários que usarão Tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="55416-113">Somente usuários com uma licença podem ver informações sobre tópicos, incluindo destaques, cartões de tópicos, páginas de tópicos e o centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="55416-114">Atribuição de licenças:</span><span class="sxs-lookup"><span data-stu-id="55416-114">To assign licenses:</span></span>

1. <span data-ttu-id="55416-115">No Centro de administração do Microsoft 365, em **Usuários**, clique em **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="55416-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="55416-116">Selecione os usuários que você deseja licenciar e clique **em Licenças e aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="55416-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="55416-117">Em **Licenças,** selecione **Viva Tópicos**.</span><span class="sxs-lookup"><span data-stu-id="55416-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="55416-118">Em **Aplicativos,** certifique-se de que a Pesquisa **de Conectores do Graph com Índice (Tópicos** do Viva) e os Tópicos do Viva estão **selecionados.**</span><span class="sxs-lookup"><span data-stu-id="55416-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="55416-119">![Licenças de tópicos do Microsoft Viva no centro de administração do Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="55416-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="55416-120">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="55416-120">Click **Save changes**.</span></span>

<span data-ttu-id="55416-121">Pode levar até uma hora para que os usuários tenham acesso a Tópicos depois que as licenças são atribuídas.</span><span class="sxs-lookup"><span data-stu-id="55416-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="55416-122">Configurar tópicos</span><span class="sxs-lookup"><span data-stu-id="55416-122">Set up Topics</span></span>

<span data-ttu-id="55416-123">Para configurar tópicos</span><span class="sxs-lookup"><span data-stu-id="55416-123">To set up Topics</span></span>

1. <span data-ttu-id="55416-124">No Centro de administração do [Microsoft 365,](https://admin.microsoft.com)selecione **Instalação** e, em seguida, exibir a **seção Arquivos e** conteúdo.</span><span class="sxs-lookup"><span data-stu-id="55416-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="55416-125">Na seção **Arquivos e conteúdo,** clique em **Conectar pessoas ao conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="55416-125">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Conectar pessoas ao conhecimento](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="55416-127">Na página **Conectar pessoas ao conhecimento,** clique em **Começar a** passar por você no processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="55416-127">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Introdução](../media/k-get-started.png) 

4. <span data-ttu-id="55416-129">Na página **Escolher como os Tópicos do Viva podem encontrar tópicos,** você configurará a descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-129">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="55416-130">Na seção **Selecionar fontes de tópicos do SharePoint,** selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta.</span><span class="sxs-lookup"><span data-stu-id="55416-130">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="55416-131">Escolha entre:</span><span class="sxs-lookup"><span data-stu-id="55416-131">Choose from:</span></span>
    - <span data-ttu-id="55416-132">**Todos os sites**: Todos os sites do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="55416-132">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="55416-133">Isso inclui sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="55416-133">This includes current and future sites.</span></span>
    - <span data-ttu-id="55416-134">**Todos, exceto sites selecionados:** Digite os nomes dos sites que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="55416-134">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="55416-135">Você também pode carregar uma lista de sites que deseja excluir da descoberta.</span><span class="sxs-lookup"><span data-stu-id="55416-135">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="55416-136">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-136">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="55416-137">**Somente sites selecionados**: Digite os nomes dos sites que você deseja incluir.</span><span class="sxs-lookup"><span data-stu-id="55416-137">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="55416-138">Você também pode carregar uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="55416-138">You can also upload a list of sites.</span></span> <span data-ttu-id="55416-139">Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-139">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="55416-140">**Nenhum site**: Não inclua sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="55416-140">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Escolha como encontrar tópicos](../media/ksetup1.png) 
   
5. <span data-ttu-id="55416-142">Na seção **Excluir tópicos por** nome, você pode adicionar nomes de tópicos que deseja excluir da descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-142">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="55416-143">Use essa configuração para impedir que informações confidenciais são incluídas como tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-143">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="55416-144">As opções são:</span><span class="sxs-lookup"><span data-stu-id="55416-144">The options are:</span></span>
    - <span data-ttu-id="55416-145">**Não exclua nenhum tópico**</span><span class="sxs-lookup"><span data-stu-id="55416-145">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="55416-146">**Excluir tópicos por nome**</span><span class="sxs-lookup"><span data-stu-id="55416-146">**Exclude topics by name**</span></span>

    ![Excluir tópicos](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="55416-148">(Os gerentes de conhecimento também podem excluir tópicos no centro de tópicos após a descoberta.)</span><span class="sxs-lookup"><span data-stu-id="55416-148">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="55416-149">Como excluir tópicos por nome</span><span class="sxs-lookup"><span data-stu-id="55416-149">How to exclude topics by name</span></span>    

    <span data-ttu-id="55416-150">Se você precisar excluir tópicos, depois de selecionar **Excluir tópicos** por nome, baixe o modelo .csv e atualize-o com a lista de tópicos que você deseja excluir dos resultados da descoberta.</span><span class="sxs-lookup"><span data-stu-id="55416-150">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="55416-152">No modelo CSV, insira as seguintes informações sobre os tópicos que você deseja excluir:</span><span class="sxs-lookup"><span data-stu-id="55416-152">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="55416-153">**Nome**: digite o nome do tópico que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="55416-153">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="55416-154">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="55416-154">There are two ways to do this:</span></span>
        - <span data-ttu-id="55416-155">Match exato: Você pode incluir o nome exato ou acrônimo (por exemplo, *Contoso* ou *ATL*).</span><span class="sxs-lookup"><span data-stu-id="55416-155">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="55416-156">Match parcial: você pode excluir todos os tópicos que tenham uma palavra específica nele.</span><span class="sxs-lookup"><span data-stu-id="55416-156">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="55416-157">Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavra nele, como círculo de *arco,* *soldagem* de arco de plasma ou arco *treinamento*. Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, como *Arquitetura*.</span><span class="sxs-lookup"><span data-stu-id="55416-157">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="55416-158">**Significa (opcional)**: Se você quiser excluir um acrônimo, digite as palavras que o acrônimo representa.</span><span class="sxs-lookup"><span data-stu-id="55416-158">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="55416-159">**MatchType-Exact/Partial**: Digite se o nome inserido foi *um tipo de* combinação exato *ou* parcial.</span><span class="sxs-lookup"><span data-stu-id="55416-159">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="55416-160">Depois de concluir e salvar seu arquivo .csv, selecione **Procurar** para localizá-lo e selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="55416-160">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="55416-161">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="55416-161">Select **Next**.</span></span>

6. <span data-ttu-id="55416-162">Na página **Quem pode ver tópicos e onde eles podem vê-los,** você configurará a visibilidade do tópico.</span><span class="sxs-lookup"><span data-stu-id="55416-162">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="55416-163">Na **configuração Quem pode ver tópicos,** escolha quem terá acesso aos detalhes do tópico, como tópicos destacados, cartões de tópicos, respostas de tópicos na pesquisa e páginas de tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-163">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="55416-164">Você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="55416-164">You can select:</span></span>
    - <span data-ttu-id="55416-165">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="55416-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="55416-166">**Somente pessoas selecionadas ou grupos de segurança**</span><span class="sxs-lookup"><span data-stu-id="55416-166">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="55416-167">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="55416-167">**No one**</span></span>

    ![Quem pode ver tópicos](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="55416-169">Embora essa configuração permita que você selecione qualquer usuário em sua organização, somente os usuários que têm licenças de Experiências de Tópico atribuídas a eles poderão exibir tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-169">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="55416-170">Na página **Permissões para gerenciamento de** tópicos, escolha quem poderá criar, editar ou gerenciar tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-170">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="55416-171">Na seção **Quem pode criar e editar tópicos,** você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="55416-171">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="55416-172">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="55416-172">**Everyone in my organization**</span></span>
    - <span data-ttu-id="55416-173">**Somente pessoas selecionadas ou grupos de segurança**</span><span class="sxs-lookup"><span data-stu-id="55416-173">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="55416-174">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="55416-174">**No one**</span></span>

    ![Permissões para gerenciamento de tópicos, que podem criar e editar tópicos](../media/ksetup3.png) 

8. <span data-ttu-id="55416-176">Na seção **Quem pode gerenciar tópicos,** você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="55416-176">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="55416-177">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="55416-177">**Everyone in my organization**</span></span>
    - <span data-ttu-id="55416-178">**Somente pessoas selecionadas ou grupos de segurança**</span><span class="sxs-lookup"><span data-stu-id="55416-178">**Only selected people or security groups**</span></span>

    ![Permissões para gerenciamento de tópicos](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="55416-180">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="55416-180">Select **Next**.</span></span>

9. <span data-ttu-id="55416-181">Na página **Criar centro de** tópicos, você pode criar seu site central de tópicos no qual as páginas de tópicos podem ser exibidas e os tópicos podem ser gerenciados.</span><span class="sxs-lookup"><span data-stu-id="55416-181">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="55416-182">Na caixa **Nome do site,** digite um nome para o centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-182">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="55416-183">Opcionalmente, você pode digitar uma breve descrição na caixa **Descrição.**</span><span class="sxs-lookup"><span data-stu-id="55416-183">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="55416-184">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="55416-184">Select **Next**.</span></span>

   ![Criar Centro de Conhecimento](../media/ksetup4.png)  

10. <span data-ttu-id="55416-186">Na página **Revisão e acabamento**, você pode olhar para a configuração selecionada e escolher fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="55416-186">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="55416-187">Se estiver satisfeito com as suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="55416-187">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="55416-188">A **página Tópicos do Viva** ativada será exibida, confirmando que o sistema agora começará a analisar os sites selecionados para tópicos e a criação do site central de tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-188">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="55416-189">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="55416-189">Select **Done**.</span></span>

12. <span data-ttu-id="55416-190">Você será retornado à página Conectar pessoas **à informação.**</span><span class="sxs-lookup"><span data-stu-id="55416-190">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="55416-191">A partir desta página, é possível selecionar **Gerenciar** para fazer quaisquer alterações em suas configurações.</span><span class="sxs-lookup"><span data-stu-id="55416-191">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Configurações aplicadas](../media/ksetup7.png)    

<span data-ttu-id="55416-193">Observe que a primeira descoberta de tópicos está habilitada, pode levar até duas semanas para que todos os tópicos sugeridos apareçam no modo de exibição Gerenciar Tópicos.</span><span class="sxs-lookup"><span data-stu-id="55416-193">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="55416-194">A descoberta de tópicos continua à medida que novos conteúdos ou atualizações para o conteúdo são feitos.</span><span class="sxs-lookup"><span data-stu-id="55416-194">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="55416-195">É normal ter flutuações no número de tópicos sugeridos em sua organização à medida que o Viva Topics avalia novas informações.</span><span class="sxs-lookup"><span data-stu-id="55416-195">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="55416-196">Gerenciar experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="55416-196">Manage topic experiences</span></span>

<span data-ttu-id="55416-197">Depois de configurar Tópicos, você pode alterar as configurações escolhidas durante a instalação no Centro de administração [do Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="55416-197">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="55416-198">Confira as seguintes referências:</span><span class="sxs-lookup"><span data-stu-id="55416-198">See the following references:</span></span>

- [<span data-ttu-id="55416-199">Gerenciar a descoberta de tópicos em Tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="55416-199">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="55416-200">Gerenciar visibilidade de tópicos em Tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="55416-200">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="55416-201">Gerenciar permissões de tópicos em Tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="55416-201">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="55416-202">Alterar o nome do centro de tópicos em Tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="55416-202">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="55416-203">Confira também</span><span class="sxs-lookup"><span data-stu-id="55416-203">See also</span></span>

[<span data-ttu-id="55416-204">Visão geral das experiências do tópico</span><span class="sxs-lookup"><span data-stu-id="55416-204">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
