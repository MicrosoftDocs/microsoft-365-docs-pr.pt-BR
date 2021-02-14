---
title: Revisar conversas na Descoberta Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como usar o recurso de Reconstrução de Conversa na Descoberta Avançada para reconstruir, revisar e exportar conversas encadeadas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf5c39f567240b58546dbeb353e3e461e9b69e48
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358339"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="3ed5d-103">Revisar conversas na Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="3ed5d-103">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="3ed5d-104">O sistema de mensagens instantâneas é uma maneira conveniente de fazer perguntas, compartilhar ideias ou comunicar-se rapidamente entre grandes públicos.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="3ed5d-105">À medida que as plataformas de mensagens instantâneas, como o Microsoft Teams, se tornam fundamentais para a colaboração corporativa, as organizações devem avaliar como seu fluxo de trabalho de Descoberta Eletrônico aborda essas novas formas de comunicação e colaboração.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-105">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="3ed5d-106">O recurso de Reconstrução de Conversa na Descoberta Avançada foi projetado para ajudá-lo a identificar conteúdo contextual e produzir exibições de conversa distintas.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="3ed5d-107">Esse recurso permite que você revise com eficiência e rapidez a conclusão de conversas de mensagens instantâneas (também chamadas de conversas encadeadas) geradas em plataformas como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="3ed5d-108">Com a Reconstrução da Conversa, você pode usar recursos integrados para reconstruir, revisar e exportar conversas encadeadas.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="3ed5d-109">Use Advanced eDiscovery Conversation Reconstruction to:</span><span class="sxs-lookup"><span data-stu-id="3ed5d-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="3ed5d-110">Preservar metadados exclusivos no nível da mensagem em todas as mensagens de uma conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="3ed5d-111">Coletar mensagens contextuais em torno dos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="3ed5d-112">Revise, anota e reacte conversas encadeadas.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="3ed5d-113">Exportar mensagens individuais ou conversas encadeadas</span><span class="sxs-lookup"><span data-stu-id="3ed5d-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="3ed5d-114">Terminologia</span><span class="sxs-lookup"><span data-stu-id="3ed5d-114">Terminology</span></span>

<span data-ttu-id="3ed5d-115">Aqui estão algumas definições para ajudá-lo a começar a usar a Reconstrução da Conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="3ed5d-116">**Mensagens:** Representa a menor unidade de uma conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="3ed5d-117">As mensagens podem variar em tamanho, estrutura e metadados.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="3ed5d-118">**Conversa:** Representa um grupo de uma ou mais mensagens.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="3ed5d-119">Em diferentes aplicativos, as conversas podem ser representadas de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="3ed5d-120">Em alguns aplicativos, há uma ação explícita que resulta da resposta a uma mensagem existente.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="3ed5d-121">As conversas são formadas explicitamente como resultado dessa ação do usuário.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="3ed5d-122">Por exemplo, aqui está uma captura de tela de uma conversa de canal no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Conversa do canal do Microsoft Teams](../media/threadedchat.png)

   <span data-ttu-id="3ed5d-124">Em outros aplicativos (como mensagens de chat 1xN no Teams), não há uma cadeia de resposta formal e, em vez disso, as mensagens aparecem como um "river plano de mensagens" dentro de um único thread.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="3ed5d-125">Nesses tipos de aplicativos, as conversas são adiadas de um grupo de mensagens que ocorrem dentro de um determinado tempo.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="3ed5d-126">Esse "soft-grouping" de mensagens (em vez de uma cadeia de resposta) representa a conversa "voltar e voltar" sobre um tópico específico de interesse.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="3ed5d-127">Etapa 1: Executar uma pesquisa</span><span class="sxs-lookup"><span data-stu-id="3ed5d-127">Step 1: Run a search</span></span>

<span data-ttu-id="3ed5d-128">Depois de identificar os custodiantes relevantes e locais de conteúdo, você pode criar uma pesquisa para encontrar conteúdo potencialmente relevante.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="3ed5d-129">Na guia **Pesquisas** no caso de Descobertas Avançadas, você pode criar uma pesquisa clicando em Nova pesquisa **e** seguindo o assistente.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-129">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="3ed5d-130">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="3ed5d-130">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="3ed5d-131">Etapa 2: Criar um conjunto de revisão de conversa</span><span class="sxs-lookup"><span data-stu-id="3ed5d-131">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="3ed5d-132">Em um conjunto de revisão, você pode pesquisar, marcar, anotar e reencenar documentos, mensagens de email e conversas de chat.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-132">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="3ed5d-133">Na Descoberta Avançada, você pode personalizar sua revisão de conversas, com base em mensagens individuais ou conversas encadeadas.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-133">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="3ed5d-134">Isso é determinado pelo tipo de conjunto de revisão ao qual você adiciona os resultados da pesquisa criada na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-134">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="3ed5d-135">Há dois tipos diferentes de conjuntos de revisão:</span><span class="sxs-lookup"><span data-stu-id="3ed5d-135">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="3ed5d-136">**Conjuntos de revisão padrão:** As mensagens em conversas são processadas e exibidas como itens individuais.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-136">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="3ed5d-137">**Conjuntos de revisão de conversa:** As mensagens em conversas são processadas individualmente, mas exibidas em uma exibição de conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-137">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="3ed5d-138">Em um conjunto de revisão de conversa, você pode anotar, marcar e reactar mensagens em uma exibição de conversa encadeada.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-138">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="3ed5d-139">Para obter mais informações sobre como revisar e gerenciar conteúdo em um conjunto de revisão, consulte [Gerenciar conjuntos de revisão.](managing-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="3ed5d-139">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="3ed5d-140">Etapa 3: Habilitar opções de recuperação de conversa</span><span class="sxs-lookup"><span data-stu-id="3ed5d-140">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="3ed5d-141">Depois de revisar e finalizar a consulta de pesquisa, você poderá adicionar os resultados da pesquisa a um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-141">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="3ed5d-142">Quando você adiciona os resultados da pesquisa em um conjunto de revisão, os dados originais são copiados para uma área de Armazenamento do Azure para facilitar o processo de análise e revisão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-142">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="3ed5d-143">Para obter mais informações sobre como adicionar resultados de pesquisa a um conjunto de revisão, consulte [Adicionar resultados de pesquisa a um conjunto de revisão.](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="3ed5d-143">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="3ed5d-144">Ao adicionar dados de conversas a um conjunto de revisão, você pode usar as opções de recuperação de conversa para expandir sua pesquisa e incluir mensagens contextuais.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-144">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="3ed5d-145">Depois de definir as opções de recuperação de conversa, as seguintes coisas podem acontecer:</span><span class="sxs-lookup"><span data-stu-id="3ed5d-145">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![Recuperação de Conversa](../media/messagesandconversations.png)
  
1. <span data-ttu-id="3ed5d-147">Usando uma palavra-chave e uma consulta de intervalo de datas, a pesquisa retornou uma mensagem *3*.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-147">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="3ed5d-148">Esta mensagem fazia parte de uma conversa maior, ilustrada por *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="3ed5d-148">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="3ed5d-149">Quando você adiciona os dados em um conjunto de revisão e habilita as opções de recuperação de conversa, a Descoberta Avançada volta e coleta outros itens no *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-149">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="3ed5d-150">Depois que os itens foram adicionados ao conjunto de revisão, você pode revisar todas as mensagens individuais de *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-150">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 

<span data-ttu-id="3ed5d-151">Para habilitar a recuperação de conversa:</span><span class="sxs-lookup"><span data-stu-id="3ed5d-151">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="3ed5d-152">Na guia **Pesquisas no** caso de Descobertas Avançadas, selecione  uma pesquisa e clique em Adicionar para revisar definida na página do flyout.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-152">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="3ed5d-153">Selecione um conjunto de revisão existente ou crie um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-153">Select an existing review set or create a review set.</span></span> <span data-ttu-id="3ed5d-154">Você pode configurar opções de recuperação ao adicionar resultados de pesquisa a um conjunto de revisão de conversa ou padrão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-154">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="3ed5d-155">Em **Opções de coleção,** configure as opções de recuperação de conversa para as  fontes de conteúdo que você deseja expandir em sua pesquisa e clique em Adicionar para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-155">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="3ed5d-156">Depois que **o trabalho de conjunto Adicionar a revisão** na guia **Trabalhos** tiver sido concluído, você poderá começar a revisar as conversas.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-156">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a><span data-ttu-id="3ed5d-157">Etapa 4: Revisar e exportar conversas em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="3ed5d-157">Step 4: Review and export conversations in a review set</span></span>

<span data-ttu-id="3ed5d-158">Depois que o conteúdo tiver sido processado e adicionado ao conjunto de revisão, você poderá começar a analisar os dados no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-158">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="3ed5d-159">Os recursos de revisão são diferentes dependendo se o conteúdo foi adicionado a um conjunto de revisão padrão ou a um conjunto de revisão de conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-159">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="3ed5d-160">Revendo conversas em um conjunto de revisão padrão</span><span class="sxs-lookup"><span data-stu-id="3ed5d-160">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="3ed5d-161">Em um conjunto de revisão padrão, as mensagens são processadas e exibidas como itens individuais, semelhante à forma como são armazenadas em uma pasta da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-161">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="3ed5d-162">Nesse fluxo de trabalho, cada mensagem é processada como um item separado.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-162">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="3ed5d-163">Como resultado, as opções de exportação e resumo threaded não estão disponíveis em um conjunto de revisão padrão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-163">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![Conjunto de revisão padrão](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="3ed5d-165">Revendo conversas em um conjunto de revisão de conversa</span><span class="sxs-lookup"><span data-stu-id="3ed5d-165">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="3ed5d-166">Em um conjunto de revisão de conversa, mensagens individuais são encadeadas e apresentadas como conversas.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-166">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="3ed5d-167">Isso permite que você revise e exporte conversas contextuais.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-167">This lets you review and export contextual conversations.</span></span> 

  ![Conjunto de revisão de conversa](../media/ConversationRSOptions.PNG)

<span data-ttu-id="3ed5d-169">As seções a seguir descrevem a revisão e a exportação de conversas em um conjunto de revisão de conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-169">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="3ed5d-170">Revendo conversas</span><span class="sxs-lookup"><span data-stu-id="3ed5d-170">Reviewing conversations</span></span>

<span data-ttu-id="3ed5d-171">Em um conjunto de revisão de conversa, você pode usar as seguintes opções para facilitar o processo de revisão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-171">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="3ed5d-172">**Agrupar por conversa:** Reúne mensagens dentro da mesma conversa para ajudar os usuários a simplificar e acelerar o processo de revisão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-172">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="3ed5d-173">**Exibição resumida:** Exibe a conversa encadeada.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-173">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="3ed5d-174">Nessa exibição, você pode ver a conversa inteira e também acessar os metadados de cada mensagem individual.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-174">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="3ed5d-175">Exibir metadados para mensagens individuais</span><span class="sxs-lookup"><span data-stu-id="3ed5d-175">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="3ed5d-176">Baixar mensagens individuais</span><span class="sxs-lookup"><span data-stu-id="3ed5d-176">Download individual messages</span></span>

- <span data-ttu-id="3ed5d-177">**Exibição de texto:** Fornece o texto extraído para toda a conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-177">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="3ed5d-178">**Exibição de anotações:** Permite marcar uma exibição encadeada da conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-178">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="3ed5d-179">Todas as mensagens na conversa compartilham o mesmo documento anotado.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-179">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="3ed5d-180">**Marcação:** Ao exibir conversas em um conjunto de revisão,  você pode exibir e aplicar marcas clicando no painel marcação no painel de codificação.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-180">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="3ed5d-181">**Rerun conversation conversion:** Quando as mensagens são adicionadas a um conjunto de revisão de conversa, um trabalho de conversão é executado automaticamente para criar o resumo encadeado e anotar as exibições.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-181">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="3ed5d-182">Se o trabalho de Reconstrução da Conversa falhar, você poderá reprisar esse trabalho clicando em Ação **> Criar PDFs** de conversa no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-182">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="3ed5d-183">Exportando conversas</span><span class="sxs-lookup"><span data-stu-id="3ed5d-183">Exporting conversations</span></span>

<span data-ttu-id="3ed5d-184">Em um conjunto de revisão de conversa, você pode definir as seguintes opções para exportar conversas:</span><span class="sxs-lookup"><span data-stu-id="3ed5d-184">In a conversation review set, you can set the following options to export conversations:</span></span>

![Opções de exportação para conversas](../media/export.png)

<span data-ttu-id="3ed5d-186">a.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-186">a.</span></span> <span data-ttu-id="3ed5d-187">Opções de metadados</span><span class="sxs-lookup"><span data-stu-id="3ed5d-187">Metadata options</span></span>

   - <span data-ttu-id="3ed5d-188">**Carregar arquivo:** Os metadados são incluídos para cada mensagem individual, email e documento.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-188">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="3ed5d-189">Há uma linha para cada mensagem em uma conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-189">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="3ed5d-190">**Marcas:** As marcas do seu processo de revisão estão incluídas no arquivo de metadados.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-190">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="3ed5d-191">As mensagens em uma conversa compartilham as mesmas marcas.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-191">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="3ed5d-192">b.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-192">b.</span></span> <span data-ttu-id="3ed5d-193">Opções de conversa</span><span class="sxs-lookup"><span data-stu-id="3ed5d-193">Conversation options</span></span>
  
   - <span data-ttu-id="3ed5d-194">**Arquivos de conversa:** Quando você exporta arquivos de conversa, o exibição anotado é convertido em um arquivo PDF e baixado para a pasta de exportação.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-194">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="3ed5d-195">As mensagens em um arquivo de conversa apontam para a versão PDF do mesmo arquivo de conversa.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-195">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="3ed5d-196">**Mensagens de chat individuais:** Quando você exporta mensagens individuais, cada mensagem exclusiva na conversa é exportada como um item autônomo.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-196">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="3ed5d-197">O arquivo é exportado no mesmo formato em que foi salvo como na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-197">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="3ed5d-198">Para uma conversa específica, você recebe vários arquivos .msg.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-198">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="3ed5d-199">Se você aplicou anotações ao arquivo de conversa, essas anotações não serão transferidas para as mensagens individuais.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-199">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="3ed5d-200">c.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-200">c.</span></span> <span data-ttu-id="3ed5d-201">Outras opções</span><span class="sxs-lookup"><span data-stu-id="3ed5d-201">Other options</span></span>

   - <span data-ttu-id="3ed5d-202">**Gere arquivos de texto para todo o conteúdo exportado:** Gera um arquivo de texto para cada conversa exportada do conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-202">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="3ed5d-203">**Substitua o conteúdo exportado por PDFs redacionados:** Se os arquivos de conversa redacted são gerados durante o processo de revisão, esses arquivos estarão disponíveis durante a exportação.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-203">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="3ed5d-204">Você pode decidir se exportará somente os arquivos nativos (não selecionando essa opção) ou se substituirá os arquivos nativos pelas versões redacionadas dos arquivos nativos (selecionando essa opção), que serão exportados como arquivos PDF.</span><span class="sxs-lookup"><span data-stu-id="3ed5d-204">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="3ed5d-205">Mais informações</span><span class="sxs-lookup"><span data-stu-id="3ed5d-205">More information</span></span>

<span data-ttu-id="3ed5d-206">Para saber mais sobre como revisar dados de caso na Descoberta Avançada, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="3ed5d-206">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="3ed5d-207">Exibir dados de ocorrência</span><span class="sxs-lookup"><span data-stu-id="3ed5d-207">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="3ed5d-208">Analisar dados de ocorrência</span><span class="sxs-lookup"><span data-stu-id="3ed5d-208">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="3ed5d-209">Exportar dados de ocorrência</span><span class="sxs-lookup"><span data-stu-id="3ed5d-209">Export case data</span></span>](exporting-data-ediscover20.md)
