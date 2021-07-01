---
title: Revisar conversas no Advanced eDiscovery
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
description: Saiba mais sobre o recurso de reconstrução de conversa Advanced eDiscovery (chamado threading de conversa) para reconstruir, revisar e exportar conversas de chat em grupos Microsoft Teams e Yammer de conversa.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9848280a7d6dbcbd6128fff06f150c8458f09701
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227182"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="af8a7-103">Threading de conversa em Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="af8a7-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="af8a7-104">A mensagem instantânea é uma maneira conveniente de fazer perguntas, compartilhar ideias ou comunicar-se rapidamente entre grandes públicos.</span><span class="sxs-lookup"><span data-stu-id="af8a7-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="af8a7-105">À medida que as plataformas de mensagens instantâneas, como grupos Microsoft Teams e Yammer, se tornam fundamentais para a colaboração corporativa, as organizações devem avaliar como seu fluxo de trabalho de Descoberta Eletrônico aborda essas novas formas de comunicação e colaboração.</span><span class="sxs-lookup"><span data-stu-id="af8a7-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="af8a7-106">O recurso de Reconstrução de Conversa no Advanced eDiscovery foi projetado para ajudá-lo a identificar conteúdo contextual e produzir exibições de conversa distintas.</span><span class="sxs-lookup"><span data-stu-id="af8a7-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="af8a7-107">Esse recurso permite que você revise de forma eficiente e rápida conversas de mensagens instantâneas completas (também chamadas de conversas encadeadas *)* geradas em plataformas como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="af8a7-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="af8a7-108">Com a Reconstrução de Conversa, você pode usar recursos integrados para reconstruir, revisar e exportar conversas encadeadas.</span><span class="sxs-lookup"><span data-stu-id="af8a7-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="af8a7-109">Use Advanced eDiscovery reconstrução de conversa para:</span><span class="sxs-lookup"><span data-stu-id="af8a7-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="af8a7-110">Preservar metadados exclusivos no nível de mensagem em todas as mensagens em uma conversa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="af8a7-111">Colete mensagens contextuais em torno dos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="af8a7-112">Revisar, anotar e reencenar conversas encadeadas.</span><span class="sxs-lookup"><span data-stu-id="af8a7-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="af8a7-113">Exportar mensagens individuais ou conversas encadeadas</span><span class="sxs-lookup"><span data-stu-id="af8a7-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="af8a7-114">Terminologia</span><span class="sxs-lookup"><span data-stu-id="af8a7-114">Terminology</span></span>

<span data-ttu-id="af8a7-115">Aqui estão algumas definições para ajudá-lo a começar a usar a Reconstrução de Conversa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="af8a7-116">**Mensagens:** Representa a menor unidade de uma conversa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="af8a7-117">As mensagens podem variar em tamanho, estrutura e metadados.</span><span class="sxs-lookup"><span data-stu-id="af8a7-117">Messages may vary in size, structure, and metadata.</span></span>

- <span data-ttu-id="af8a7-118">**Conversa:** Representa um grupo de uma ou mais mensagens.</span><span class="sxs-lookup"><span data-stu-id="af8a7-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="af8a7-119">Em diferentes aplicativos, as conversas podem ser representadas de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="af8a7-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="af8a7-120">Em alguns aplicativos, há uma ação explícita que resulta da resposta a uma mensagem existente.</span><span class="sxs-lookup"><span data-stu-id="af8a7-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="af8a7-121">As conversas são formadas explicitamente como resultado dessa ação do usuário.</span><span class="sxs-lookup"><span data-stu-id="af8a7-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="af8a7-122">Por exemplo, aqui está uma captura de tela de uma conversa de canal em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="af8a7-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams Conversa do Canal](../media/threadedchat.png)

   <span data-ttu-id="af8a7-124">Em outros aplicativos (como mensagens de chat 1xN no Teams), não há uma cadeia de resposta formal e, em vez disso, as mensagens aparecem como um "rio plano de mensagens" dentro de um único thread.</span><span class="sxs-lookup"><span data-stu-id="af8a7-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="af8a7-125">Nesses tipos de aplicativos, as conversas são inferidos de um grupo de mensagens que ocorrem em um determinado momento.</span><span class="sxs-lookup"><span data-stu-id="af8a7-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="af8a7-126">Esse "grupo suave" de mensagens (em vez de uma cadeia de resposta) representa a conversa "ir e vir" sobre um tópico específico de interesse.</span><span class="sxs-lookup"><span data-stu-id="af8a7-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="af8a7-127">Etapa 1: Criar uma coleção de rascunhos</span><span class="sxs-lookup"><span data-stu-id="af8a7-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="af8a7-128">Depois de identificar os custodiantes relevantes e os locais de conteúdo, você pode criar uma pesquisa para encontrar conteúdo potencialmente relevante.</span><span class="sxs-lookup"><span data-stu-id="af8a7-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="af8a7-129">Na guia **Coleções** no caso Advanced eDiscovery, você pode criar uma coleção clicando em **Nova coleção** e seguindo o assistente.</span><span class="sxs-lookup"><span data-stu-id="af8a7-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="af8a7-130">Para obter informações sobre como você pode criar uma coleção, criar uma consulta de pesquisa e visualizar os resultados da pesquisa, consulte [Create a draft collection](create-draft-collection.md).</span><span class="sxs-lookup"><span data-stu-id="af8a7-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="af8a7-131">Etapa 2: Comprometer um conjunto de rascunhos em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="af8a7-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="af8a7-132">Depois de revisar e finalizar a consulta de pesquisa em uma coleção, você pode adicionar os resultados da pesquisa a um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="af8a7-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="af8a7-133">Quando você adiciona seus resultados de pesquisa a um conjunto de revisão, os dados originais são copiados para uma área de Armazenamento do Azure para facilitar o processo de revisão e análise.</span><span class="sxs-lookup"><span data-stu-id="af8a7-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="af8a7-134">Para obter mais informações sobre como adicionar resultados de pesquisa a um conjunto de revisão, consulte [Commit a draft collection to a review set](commit-draft-collection.md).</span><span class="sxs-lookup"><span data-stu-id="af8a7-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="af8a7-135">Ao adicionar itens de conversas a um conjunto de revisão, você pode usar a opção de conversas encadeadas para coletar mensagens contextuais de conversas que contenham itens que corresponderem aos critérios de pesquisa da coleção.</span><span class="sxs-lookup"><span data-stu-id="af8a7-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="af8a7-136">Depois de selecionar a opção de conversas de thread, as seguintes coisas podem acontecer:</span><span class="sxs-lookup"><span data-stu-id="af8a7-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![Recuperação de Conversa](../media/messagesandconversations.png)

1. <span data-ttu-id="af8a7-138">Usando uma palavra-chave e uma consulta de intervalo de datas, a pesquisa retornou um acerto *na Mensagem 3*.</span><span class="sxs-lookup"><span data-stu-id="af8a7-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="af8a7-139">Esta mensagem fazia parte de uma conversa maior, ilustrada por *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="af8a7-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>

2. <span data-ttu-id="af8a7-140">Quando você adiciona os dados a um conjunto de revisão e habilita as opções de recuperação de conversa, Advanced eDiscovery retornará e coletará outros itens no *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="af8a7-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>

3. <span data-ttu-id="af8a7-141">Depois que os itens foram adicionados ao conjunto de revisão, você pode revisar todas as mensagens individuais de *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="af8a7-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="af8a7-142">Para habilitar a opção conversas encadeadas, consulte [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="af8a7-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>

## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="af8a7-143">Etapa 3: Revisar e exportar conversas encadeadas</span><span class="sxs-lookup"><span data-stu-id="af8a7-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="af8a7-144">Depois que o conteúdo tiver sido processado e adicionado ao conjunto de revisão, você poderá começar a revisar os dados no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="af8a7-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="af8a7-145">Os recursos de revisão são diferentes, dependendo se o conteúdo foi adicionado a um conjunto de revisão padrão ou a um conjunto de revisão de conversa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="af8a7-146">Revisão de conversas em um conjunto de revisão padrão</span><span class="sxs-lookup"><span data-stu-id="af8a7-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="af8a7-147">Em um conjunto de revisão padrão, as mensagens são processadas e exibidas como itens individuais, semelhantes à forma como são armazenadas em uma pasta de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="af8a7-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="af8a7-148">Nesse fluxo de trabalho, cada mensagem é processada como um item separado.</span><span class="sxs-lookup"><span data-stu-id="af8a7-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="af8a7-149">Como resultado, as opções de resumo e exportação threaded não estão disponíveis em um conjunto de revisão padrão.</span><span class="sxs-lookup"><span data-stu-id="af8a7-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![Conjunto de revisão padrão](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="af8a7-151">Revisão de conversas em um conjunto de revisão de conversa</span><span class="sxs-lookup"><span data-stu-id="af8a7-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="af8a7-152">Em um conjunto de revisão de conversa, as mensagens individuais são encadeadas e apresentadas como conversas.</span><span class="sxs-lookup"><span data-stu-id="af8a7-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="af8a7-153">Isso permite que você revise e exporte conversas contextuais.</span><span class="sxs-lookup"><span data-stu-id="af8a7-153">This lets you review and export contextual conversations.</span></span>

  ![Conjunto de revisão de conversa](../media/ConversationRSOptions.PNG)

<span data-ttu-id="af8a7-155">As seções a seguir descrevem a revisão e exportação de conversas em um conjunto de revisão de conversa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="af8a7-156">Revisão de conversas</span><span class="sxs-lookup"><span data-stu-id="af8a7-156">Reviewing conversations</span></span>

<span data-ttu-id="af8a7-157">Em um conjunto de revisão de conversa, você pode usar as seguintes opções para facilitar o processo de revisão.</span><span class="sxs-lookup"><span data-stu-id="af8a7-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="af8a7-158">**Grupo por conversa:** Reúne mensagens na mesma conversa para ajudar os usuários a simplificar e acelerar o processo de revisão.</span><span class="sxs-lookup"><span data-stu-id="af8a7-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="af8a7-159">**Exibição de resumo:** Exibe a conversa encadeada.</span><span class="sxs-lookup"><span data-stu-id="af8a7-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="af8a7-160">Nesta exibição, você pode ver a conversa inteira e também acessar os metadados de cada mensagem individual.</span><span class="sxs-lookup"><span data-stu-id="af8a7-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>

   - <span data-ttu-id="af8a7-161">Exibir metadados para mensagens individuais</span><span class="sxs-lookup"><span data-stu-id="af8a7-161">View metadata for individual messages</span></span>

   - <span data-ttu-id="af8a7-162">Baixar mensagens individuais</span><span class="sxs-lookup"><span data-stu-id="af8a7-162">Download individual messages</span></span>

- <span data-ttu-id="af8a7-163">**Exibição de texto:** Fornece o texto extraído para toda a conversa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="af8a7-164">**Exibição de anotações:** Permite marcar uma exibição encadeada da conversa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="af8a7-165">Todas as mensagens na conversa compartilham o mesmo documento anotado.</span><span class="sxs-lookup"><span data-stu-id="af8a7-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="af8a7-166">**Marcação:** Ao exibir conversas em um conjunto de revisão, você pode exibir e aplicar marcas clicando em Painel de **Marcação** no painel Codificação.</span><span class="sxs-lookup"><span data-stu-id="af8a7-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="af8a7-167">**Conversão de conversa de repetição:** Quando as mensagens são adicionadas a um conjunto de revisão de conversa, um trabalho de conversão é executado automaticamente para criar o resumo encadeado e anotar exibições.</span><span class="sxs-lookup"><span data-stu-id="af8a7-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="af8a7-168">Se o trabalho de Reconstrução de Conversa falhar, você poderá reprisar esse trabalho clicando em **Ação > Criar PDFs** de conversa no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="af8a7-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="af8a7-169">Exportando conversas</span><span class="sxs-lookup"><span data-stu-id="af8a7-169">Exporting conversations</span></span>

<span data-ttu-id="af8a7-170">Em um conjunto de revisão de conversa, você pode definir as seguintes opções para exportar conversas:</span><span class="sxs-lookup"><span data-stu-id="af8a7-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![Opções de exportação para conversas](../media/export.png)

1. <span data-ttu-id="af8a7-172">Opções de metadados:</span><span class="sxs-lookup"><span data-stu-id="af8a7-172">Metadata options:</span></span>
   - <span data-ttu-id="af8a7-173">**Arquivo de carga:** Os metadados são incluídos para cada mensagem, email e documento individuais.</span><span class="sxs-lookup"><span data-stu-id="af8a7-173">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="af8a7-174">Há uma linha para cada mensagem em uma conversa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-174">There is one row for each message in a conversation.</span></span>
   - <span data-ttu-id="af8a7-175">**Tags:** As marcas do processo de revisão são incluídas no arquivo de metadados.</span><span class="sxs-lookup"><span data-stu-id="af8a7-175">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="af8a7-176">As mensagens em uma conversa compartilham as mesmas marcas.</span><span class="sxs-lookup"><span data-stu-id="af8a7-176">Messages in a conversation share the same tags.</span></span>

2. <span data-ttu-id="af8a7-177">Opções de conversa:</span><span class="sxs-lookup"><span data-stu-id="af8a7-177">Conversation options:</span></span>
   - <span data-ttu-id="af8a7-178">**Arquivos de conversa:** Quando você exporta arquivos de conversa, o exibição anotado é convertido em um arquivo PDF e baixado para a pasta de exportação.</span><span class="sxs-lookup"><span data-stu-id="af8a7-178">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="af8a7-179">As mensagens em um arquivo de conversa apontam para a versão PDF do mesmo arquivo de conversa.</span><span class="sxs-lookup"><span data-stu-id="af8a7-179">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>
   - <span data-ttu-id="af8a7-180">**Mensagens de chat individuais:** Quando você exporta mensagens individuais, cada mensagem exclusiva na conversa é exportada como um item autônomo.</span><span class="sxs-lookup"><span data-stu-id="af8a7-180">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="af8a7-181">O arquivo é exportado no mesmo formato que foi salvo na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="af8a7-181">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="af8a7-182">Para uma conversa específica, você recebe vários arquivos .msg.</span><span class="sxs-lookup"><span data-stu-id="af8a7-182">For a specific conversation, you receive multiple .msg files.</span></span>

     > [!NOTE]
     > <span data-ttu-id="af8a7-183">Se você aplicou anotações ao arquivo de conversa, essas anotações não serão transferidas para as mensagens individuais.</span><span class="sxs-lookup"><span data-stu-id="af8a7-183">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

3. <span data-ttu-id="af8a7-184">Outras opções:</span><span class="sxs-lookup"><span data-stu-id="af8a7-184">Other options:</span></span>
   - <span data-ttu-id="af8a7-185">**Gerar arquivos de texto para todo o conteúdo exportado:** Gera um arquivo de texto para cada conversa exportada do conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="af8a7-185">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>
   - <span data-ttu-id="af8a7-186">**Substitua o conteúdo exportado por PDFs redacionados:** Se os arquivos de conversa redacted são gerados durante o processo de revisão, esses arquivos estarão disponíveis durante a exportação.</span><span class="sxs-lookup"><span data-stu-id="af8a7-186">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="af8a7-187">Você pode decidir se deve exportar somente os arquivos nativos (não selecionando essa opção) ou substituir os arquivos nativos pelas versões redacted dos arquivos nativos (selecionando essa opção), que são exportados como arquivos PDF.</span><span class="sxs-lookup"><span data-stu-id="af8a7-187">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="af8a7-188">Mais informações</span><span class="sxs-lookup"><span data-stu-id="af8a7-188">More information</span></span>

<span data-ttu-id="af8a7-189">Para saber mais sobre como revisar dados de caso Advanced eDiscovery, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="af8a7-189">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="af8a7-190">Exibir dados de caso</span><span class="sxs-lookup"><span data-stu-id="af8a7-190">View case data</span></span>](view-documents-in-review-set.md)
- [<span data-ttu-id="af8a7-191">Analisar dados de ocorrência</span><span class="sxs-lookup"><span data-stu-id="af8a7-191">Analyze case data</span></span>](analyzing-data-in-review-set.md)
- [<span data-ttu-id="af8a7-192">Exportar dados de ocorrência</span><span class="sxs-lookup"><span data-stu-id="af8a7-192">Export case data</span></span>](exporting-data-ediscover20.md)
