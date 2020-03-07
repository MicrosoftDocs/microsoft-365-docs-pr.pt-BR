---
title: Marcar documentos em um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1c0eaed5d5971a55e4e9851bac3133bcd961eb36
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557691"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="7eea8-102">Marcar documentos em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="7eea8-102">Tag documents in a review set</span></span>

<span data-ttu-id="7eea8-103">Organizar o conteúdo em um conjunto de revisão é importante para concluir vários fluxos de trabalho no processo de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="7eea8-103">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="7eea8-104">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="7eea8-104">This includes:</span></span>

- <span data-ttu-id="7eea8-105">Como analisar conteúdo desnecessário</span><span class="sxs-lookup"><span data-stu-id="7eea8-105">Culling unnecessary content</span></span>

- <span data-ttu-id="7eea8-106">Identificando conteúdo relevante</span><span class="sxs-lookup"><span data-stu-id="7eea8-106">Identifying relevant content</span></span>
 
- <span data-ttu-id="7eea8-107">Identificar conteúdo que deve ser revisado por um especialista ou advogado</span><span class="sxs-lookup"><span data-stu-id="7eea8-107">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="7eea8-108">Quando especialistas, advogados ou outros usuários revisam o conteúdo em um conjunto de revisão, suas opiniões relacionadas ao conteúdo podem ser capturadas usando marcas.</span><span class="sxs-lookup"><span data-stu-id="7eea8-108">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="7eea8-109">Por exemplo, se a intenção é de analisar conteúdo desnecessário, um usuário pode marcar documentos com uma marca como "não responsiva".</span><span class="sxs-lookup"><span data-stu-id="7eea8-109">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as “non-responsive”.</span></span> <span data-ttu-id="7eea8-110">Após o conteúdo ter sido revisado e marcado, um conjunto de análise de pesquisa pode ser criado para excluir qualquer conteúdo marcado como "não responsivo", o que elimina esse conteúdo das próximas etapas no fluxo de trabalho de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="7eea8-110">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as “non-responsive”, which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="7eea8-111">O painel de marcas pode ser personalizado para todos os casos, para que as marcas possam suportar o fluxo de trabalho de revisão desejado.</span><span class="sxs-lookup"><span data-stu-id="7eea8-111">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="7eea8-112">Tipos de marca</span><span class="sxs-lookup"><span data-stu-id="7eea8-112">Tag types</span></span>

<span data-ttu-id="7eea8-113">A descoberta eletrônica avançada fornece dois tipos de marcas:</span><span class="sxs-lookup"><span data-stu-id="7eea8-113">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="7eea8-114">**Marcas de escolha única** -restringe os usuários a selecionar uma única marca dentro de um grupo.</span><span class="sxs-lookup"><span data-stu-id="7eea8-114">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="7eea8-115">Isso pode ser útil para garantir que os usuários não selecionem marcas conflitantes, como "responsiva" e "sem resposta".</span><span class="sxs-lookup"><span data-stu-id="7eea8-115">This can be useful to ensure users don’t select conflicting tags such as “responsive” and “non-responsive”.</span></span> <span data-ttu-id="7eea8-116">Eles serão exibidos como botões de opção.</span><span class="sxs-lookup"><span data-stu-id="7eea8-116">These will appear as radio buttons.</span></span>

- <span data-ttu-id="7eea8-117">**Marcas de múltipla escolha** : permitir que os usuários selecionem várias marcas em um grupo.</span><span class="sxs-lookup"><span data-stu-id="7eea8-117">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="7eea8-118">Eles serão exibidos como caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="7eea8-118">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="7eea8-119">Estrutura da marca</span><span class="sxs-lookup"><span data-stu-id="7eea8-119">Tag structure</span></span>

<span data-ttu-id="7eea8-120">Além dos tipos de marca, a estrutura de como as marcas são organizadas no painel de marcas pode ser usada para tornar os documentos de marcação mais intuitivos.</span><span class="sxs-lookup"><span data-stu-id="7eea8-120">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="7eea8-121">As marcas são agrupadas por seções.</span><span class="sxs-lookup"><span data-stu-id="7eea8-121">Tags are grouped by sections.</span></span> <span data-ttu-id="7eea8-122">Revisar definir pesquisa oferece suporte à capacidade de Pesquisar por marca e seção de marca.</span><span class="sxs-lookup"><span data-stu-id="7eea8-122">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="7eea8-123">Isso significa que você pode criar uma análise definir pesquisa para recuperar documentos marcados com qualquer marca em uma seção.</span><span class="sxs-lookup"><span data-stu-id="7eea8-123">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Seções de marcas no painel de marcas](../media/Tagtypes.png)

<span data-ttu-id="7eea8-125">As marcas podem ser organizadas com o aninhamento de uma seção.</span><span class="sxs-lookup"><span data-stu-id="7eea8-125">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="7eea8-126">Por exemplo, se a intenção é identificar e marcar conteúdo privilegiado, o aninhamento pode ser usado para tornar claro que um usuário pode marcar um documento como "privilegiado" e selecionar o tipo de privilégio, verificando a marca aninhada apropriada.</span><span class="sxs-lookup"><span data-stu-id="7eea8-126">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as “Privileged” and select the type of privilege by checking the appropriate nested tag.</span></span>

![Marcas aninhadas em uma seção tag](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="7eea8-128">Aplicando marcas</span><span class="sxs-lookup"><span data-stu-id="7eea8-128">Applying tags</span></span>

<span data-ttu-id="7eea8-129">Há várias maneiras de aplicar uma marca ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7eea8-129">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="7eea8-130">Marcando um único documento</span><span class="sxs-lookup"><span data-stu-id="7eea8-130">Tagging a single document</span></span>

<span data-ttu-id="7eea8-131">Ao exibir um documento em um conjunto de revisão, você pode exibir as marcas que uma revisão pode usar clicando em **painel de marcação**.</span><span class="sxs-lookup"><span data-stu-id="7eea8-131">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Clique no painel de marcas para exibir o painel de marcas](../media/Singledoctag.png)

<span data-ttu-id="7eea8-133">Isso permitirá que você aplique marcas ao documento exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="7eea8-133">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="7eea8-134">Marcação em massa</span><span class="sxs-lookup"><span data-stu-id="7eea8-134">Bulk tagging</span></span>

<span data-ttu-id="7eea8-135">A marcação em massa pode ser feita selecionando vários arquivos na grade de resultados e, em seguida, usando as marcas no **painel de marcação** semelhante a marcação de documentos únicos.</span><span class="sxs-lookup"><span data-stu-id="7eea8-135">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="7eea8-136">A desmarcação em massa pode ser feita selecionando marcas duas vezes; o primeiro clique irá aplicar a marca e a segunda será garantir que a marca seja desmarcada para todos os arquivos selecionados.</span><span class="sxs-lookup"><span data-stu-id="7eea8-136">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Uma captura de tela de uma descrição de telefone de célula gerada automaticamente](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="7eea8-138">Quando a marcação em massa, o painel de marcação exibirá uma contagem de arquivos que estão marcados para cada marca no painel.</span><span class="sxs-lookup"><span data-stu-id="7eea8-138">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="7eea8-139">Marcação em outros painéis de revisão</span><span class="sxs-lookup"><span data-stu-id="7eea8-139">Tagging in other review panels</span></span>

<span data-ttu-id="7eea8-140">Ao revisar documentos, você pode usar os outros painéis de revisão para examinar outras características de documentos na grade de resultados.</span><span class="sxs-lookup"><span data-stu-id="7eea8-140">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="7eea8-141">Isso inclui a revisão de outros documentos relacionados, segmentos de email, duplicatas próximas e hash duplicados.</span><span class="sxs-lookup"><span data-stu-id="7eea8-141">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="7eea8-142">Por exemplo, quando você estiver revisando documentos relacionados (usando o documento painel de revisão **da família de documentos** ), poderá reduzir significativamente o tempo de análise ao marcar documentos relacionados em massa.</span><span class="sxs-lookup"><span data-stu-id="7eea8-142">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="7eea8-143">Por exemplo, se uma mensagem de email tiver vários anexos e você quiser garantir que toda a família seja marcada de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="7eea8-143">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="7eea8-144">Por exemplo, veja como exibir o painel de **marcação** ao usar o documento painel revisão **da família** :</span><span class="sxs-lookup"><span data-stu-id="7eea8-144">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="7eea8-145">Com o painel de revisão aberto para um documento selecionado (por exemplo, exibindo a lista de conteúdo relacionado no painel de revisão **da família de documentos** , clique em **documentos de marca** no painel revisão da família de documentos.</span><span class="sxs-lookup"><span data-stu-id="7eea8-145">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="7eea8-146">O painel de marcação é exibido como uma janela pop-up.</span><span class="sxs-lookup"><span data-stu-id="7eea8-146">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="7eea8-147">Escolha uma ou mais marcas para aplicar o documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="7eea8-147">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="7eea8-148">Para marcar todos os documentos, selecione todos os documentos no painel **família** de documentos, clique em **Marcar documentos**e, em seguida, escolha as marcas a serem aplicadas a toda a família de documentos.</span><span class="sxs-lookup"><span data-stu-id="7eea8-148">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Uma captura de tela de uma descrição de postagem de mídia social gerada automaticamente](../media/Relatedtag.png)
