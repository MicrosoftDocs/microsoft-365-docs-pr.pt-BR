---
title: Marcar documentos em um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Marcar documentos em um conjunto de revisão ajuda a remover conteúdo desnecessário e identificar conteúdo relevante em um Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736236"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="ab347-103">Marcar documentos em um conjunto de revisão em Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ab347-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="ab347-104">Organizar conteúdo em um conjunto de revisão é importante para concluir vários fluxos de trabalho no processo de Descoberta Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ab347-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="ab347-105">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="ab347-105">This includes:</span></span>

- <span data-ttu-id="ab347-106">Selecionando conteúdo desnecessário</span><span class="sxs-lookup"><span data-stu-id="ab347-106">Culling unnecessary content</span></span>

- <span data-ttu-id="ab347-107">Identificar conteúdo relevante</span><span class="sxs-lookup"><span data-stu-id="ab347-107">Identifying relevant content</span></span>

- <span data-ttu-id="ab347-108">Identificar conteúdo que deve ser revisado por um especialista ou advogado</span><span class="sxs-lookup"><span data-stu-id="ab347-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="ab347-109">Quando especialistas, advogados ou outros usuários revisam conteúdo em um conjunto de revisão, suas opiniões relacionadas ao conteúdo podem ser capturadas usando marcas.</span><span class="sxs-lookup"><span data-stu-id="ab347-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="ab347-110">Por exemplo, se a intenção for eliminar conteúdo desnecessário, um usuário poderá marcar documentos com uma marca como "não responsiva".</span><span class="sxs-lookup"><span data-stu-id="ab347-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="ab347-111">Depois que o conteúdo é revisado e marcado, uma pesquisa de conjunto de revisão pode ser criada para excluir qualquer conteúdo marcado como "não responsivo".</span><span class="sxs-lookup"><span data-stu-id="ab347-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="ab347-112">Esse processo elimina o conteúdo não responsivo das próximas etapas no fluxo de trabalho de Descoberta Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ab347-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="ab347-113">O painel de marcação em um conjunto de revisão pode ser personalizado para cada caso para que as marcas suportem o fluxo de trabalho de revisão pretendido para o caso.</span><span class="sxs-lookup"><span data-stu-id="ab347-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="ab347-114">O escopo das marcas é Advanced eDiscovery caso.</span><span class="sxs-lookup"><span data-stu-id="ab347-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="ab347-115">Isso significa que um caso só pode ter um conjunto de marcas que os revisadores podem usar para marcar documentos de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="ab347-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="ab347-116">Não é possível configurar um conjunto diferente de marcas para uso em conjuntos de revisão diferentes no mesmo caso.</span><span class="sxs-lookup"><span data-stu-id="ab347-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="ab347-117">Tipos de marca</span><span class="sxs-lookup"><span data-stu-id="ab347-117">Tag types</span></span>

<span data-ttu-id="ab347-118">Advanced eDiscovery fornece dois tipos de marcas:</span><span class="sxs-lookup"><span data-stu-id="ab347-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="ab347-119">**Marcas de opção única**: Restringe os revisadores a selecionar uma única marca dentro de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ab347-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="ab347-120">Esses tipos de marcas podem ser úteis para garantir que os revisadores não selecionem marcas conflitantes, como "responsiva" e "não responsiva".</span><span class="sxs-lookup"><span data-stu-id="ab347-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="ab347-121">Marcas de opção única aparecem como botões de opção.</span><span class="sxs-lookup"><span data-stu-id="ab347-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="ab347-122">**Marcas de várias opções**: Permitir que as avaliações selecionem várias marcas em um grupo.</span><span class="sxs-lookup"><span data-stu-id="ab347-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="ab347-123">Esses tipos de marcas aparecem como caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="ab347-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="ab347-124">Estrutura de marca</span><span class="sxs-lookup"><span data-stu-id="ab347-124">Tag structure</span></span>

<span data-ttu-id="ab347-125">Além dos tipos de marca, a estrutura de como as marcas são organizadas no painel de marcas pode ser usada para tornar a marcação de documentos mais intuitiva.</span><span class="sxs-lookup"><span data-stu-id="ab347-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="ab347-126">As marcas são agrupadas por seções.</span><span class="sxs-lookup"><span data-stu-id="ab347-126">Tags are grouped by sections.</span></span> <span data-ttu-id="ab347-127">A pesquisa de conjunto de revisão dá suporte à capacidade de pesquisar por marca e por seção de marca.</span><span class="sxs-lookup"><span data-stu-id="ab347-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="ab347-128">Isso significa que você pode criar uma pesquisa de conjunto de revisão para recuperar documentos marcados com qualquer marca em uma seção.</span><span class="sxs-lookup"><span data-stu-id="ab347-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Seções de marca no painel de marca](../media/TagTypes.png)

<span data-ttu-id="ab347-130">Você pode organizar ainda mais as marcas aninhando-as em uma seção.</span><span class="sxs-lookup"><span data-stu-id="ab347-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="ab347-131">Por exemplo, se a intenção for identificar e marcar conteúdo privilegiado, o aninhamento pode ser usado para deixar claro que um revistor pode marcar um documento como "Privileged" e selecionar o tipo de privilégio verificando a marca aninhada apropriada.</span><span class="sxs-lookup"><span data-stu-id="ab347-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Marcas aninhadas em uma seção de marca](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="ab347-133">Criar marcas</span><span class="sxs-lookup"><span data-stu-id="ab347-133">Create tags</span></span>

<span data-ttu-id="ab347-134">Antes de aplicar marcas a documentos no conjunto de revisão, você precisa criar uma estrutura de marca.</span><span class="sxs-lookup"><span data-stu-id="ab347-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="ab347-135">Abra um conjunto de revisão e navegue até a barra de comandos e selecione **Marcar por consulta**.</span><span class="sxs-lookup"><span data-stu-id="ab347-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="ab347-136">No painel de marcação, selecione **Gerenciar opções de marca**</span><span class="sxs-lookup"><span data-stu-id="ab347-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="ab347-137">Selecione **Adicionar seção de marca**.</span><span class="sxs-lookup"><span data-stu-id="ab347-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="ab347-138">Digite um título de grupo de marca e uma descrição opcional e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ab347-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="ab347-139">Selecione o menu suspenso ponto triplo ao lado do título do grupo de marca e clique em **Adicionar** caixa de seleção ou **no botão Adicionar opção**.</span><span class="sxs-lookup"><span data-stu-id="ab347-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="ab347-140">Digite um nome e uma descrição para a caixa de seleção ou botão de opção.</span><span class="sxs-lookup"><span data-stu-id="ab347-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="ab347-141">Repita esse processo para criar novas seções de marca, opções de marca e caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="ab347-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![Configurar estrutura de marca](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="ab347-143">Aplicando marcas</span><span class="sxs-lookup"><span data-stu-id="ab347-143">Applying tags</span></span>

<span data-ttu-id="ab347-144">Com a estrutura de marca no local, os revisadores podem aplicar marcas a documentos em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="ab347-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="ab347-145">Há duas maneiras diferentes de aplicar marcas:</span><span class="sxs-lookup"><span data-stu-id="ab347-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="ab347-146">Arquivos de marca</span><span class="sxs-lookup"><span data-stu-id="ab347-146">Tag files</span></span>

- <span data-ttu-id="ab347-147">Marca por consulta</span><span class="sxs-lookup"><span data-stu-id="ab347-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="ab347-148">Arquivos de marca</span><span class="sxs-lookup"><span data-stu-id="ab347-148">Tag files</span></span>

<span data-ttu-id="ab347-149">Se você selecionar um único item ou vários itens em um conjunto de revisão, poderá aplicar marcas à seleção deles clicando em **Arquivos de** marca na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ab347-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="ab347-150">No painel de marcação, você pode selecionar uma marca e ela é aplicada automaticamente aos documentos selecionados.</span><span class="sxs-lookup"><span data-stu-id="ab347-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![Marcar arquivos selecionados](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="ab347-152">As marcas serão aplicadas somente a itens selecionados na lista de itens.</span><span class="sxs-lookup"><span data-stu-id="ab347-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="ab347-153">Marca por consulta</span><span class="sxs-lookup"><span data-stu-id="ab347-153">Tag by query</span></span>

<span data-ttu-id="ab347-154">A marcação por consulta permite que você aplique marcas a todos os itens exibidos por uma consulta de filtro aplicada no momento no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="ab347-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="ab347-155">Desmarque todos os itens no conjunto de revisão e vá para a barra de comandos e selecione **Marcar por consulta**.</span><span class="sxs-lookup"><span data-stu-id="ab347-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="ab347-156">No painel de marcação, selecione a marca que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="ab347-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="ab347-157">Na lista **suspenso Seleção de** marca, há três opções que determinam a quais itens aplicar a marca.</span><span class="sxs-lookup"><span data-stu-id="ab347-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="ab347-158">**Itens que corresponderem à consulta aplicada**: aplica marcas a itens específicos que corresponderem às condições de consulta do filtro.</span><span class="sxs-lookup"><span data-stu-id="ab347-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="ab347-159">**Inclua itens da família associados**: Aplica marcas a itens específicos que corresponderem às condições de consulta do filtro e seus itens de família associados.</span><span class="sxs-lookup"><span data-stu-id="ab347-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="ab347-160">*Itens da* família são itens que compartilham o mesmo valor de metadados FamilyId.</span><span class="sxs-lookup"><span data-stu-id="ab347-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="ab347-161">**Inclua itens de conversa associados:** aplica marcas a itens que corresponderem às condições de consulta do filtro e seus itens de conversa associados.</span><span class="sxs-lookup"><span data-stu-id="ab347-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="ab347-162">*Os itens de* conversa são itens que compartilham os mesmos valores de metadados ConversationId.</span><span class="sxs-lookup"><span data-stu-id="ab347-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![Seleção de marca](../media/TagByQuery2.png)

4. <span data-ttu-id="ab347-164">Clique **em Iniciar o trabalho de marcação** para disparar o trabalho de marcação.</span><span class="sxs-lookup"><span data-stu-id="ab347-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="ab347-165">Filtro de marca</span><span class="sxs-lookup"><span data-stu-id="ab347-165">Tag filter</span></span>

<span data-ttu-id="ab347-166">Use o filtro de marca no conjunto de revisão para encontrar ou excluir rapidamente itens dos resultados da consulta com base em como um item é marcado.</span><span class="sxs-lookup"><span data-stu-id="ab347-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="ab347-167">Selecione **Filtros** para expandir o painel de filtro.</span><span class="sxs-lookup"><span data-stu-id="ab347-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="ab347-168">Selecione e **expanda propriedades de item**.</span><span class="sxs-lookup"><span data-stu-id="ab347-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="ab347-169">Role para baixo para encontrar o filtro chamado **Tag,** selecione a caixa de seleção e clique em **Feito**.</span><span class="sxs-lookup"><span data-stu-id="ab347-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="ab347-170">Para incluir ou excluir itens com uma marca específica de uma consulta, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="ab347-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="ab347-171">**Incluir itens**: selecione o valor da marca e selecione **Igual a qualquer um** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="ab347-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="ab347-172">Ou</span><span class="sxs-lookup"><span data-stu-id="ab347-172">Or</span></span>

   - <span data-ttu-id="ab347-173">**Excluir itens**: selecione o valor da marca e selecione Igual a **nenhum no** menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="ab347-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![Itens de exclusão de filtro de marca](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="ab347-175">Certifique-se de atualizar a página para garantir que o filtro de marca exibe as alterações mais recentes na estrutura de marca.</span><span class="sxs-lookup"><span data-stu-id="ab347-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
