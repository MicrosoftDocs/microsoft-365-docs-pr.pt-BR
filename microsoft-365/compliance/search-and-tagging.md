---
title: Pesquisa e marcação
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: Na descoberta eletrônica avançada, o módulo de pesquisa e marcação permite pesquisar, Visualizar e organizar os documentos em seu caso. Atualmente, este módulo está no beta.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eba95f4832e674bae0a26d3fa8466b0118a9715d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818890"
---
# <a name="search-and-tagging"></a><span data-ttu-id="c7d48-104">Pesquisa e marcação</span><span class="sxs-lookup"><span data-stu-id="c7d48-104">Search and Tagging</span></span>

<span data-ttu-id="c7d48-105">Na descoberta eletrônica avançada, o módulo de pesquisa e marcação permite pesquisar, Visualizar e organizar os documentos em seu caso.</span><span class="sxs-lookup"><span data-stu-id="c7d48-105">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case.</span></span> <span data-ttu-id="c7d48-106">Atualmente, este módulo está no beta.</span><span class="sxs-lookup"><span data-stu-id="c7d48-106">Currently, this module is in beta.</span></span> <span data-ttu-id="c7d48-107">Para obter uma breve demonstração de pesquisa e marcação, confira o botão [gerenciar seus dados com vídeo de descoberta eletrônica avançada](https://www.youtube.com/watch?v=VaPYL3DHP6I) .</span><span class="sxs-lookup"><span data-stu-id="c7d48-107">For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="c7d48-108">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="c7d48-108">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="c7d48-109">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="c7d48-109">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="c7d48-110">Pesquisar os documentos no seu caso</span><span class="sxs-lookup"><span data-stu-id="c7d48-110">Search the documents in your case</span></span>

<span data-ttu-id="c7d48-111">Depois de processar documentos em um caso de descoberta eletrônica avançada (e, opcionalmente, executar o módulo de análise ou relevância), você pode usar a pesquisa e marcação para pesquisar documentos e organizá-los aplicando marcas específicas de maiúsculas e minúsculas (também chamados de rótulos).</span><span class="sxs-lookup"><span data-stu-id="c7d48-111">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels).</span></span> <span data-ttu-id="c7d48-112">Você pode definir uma consulta de pesquisa usando os cartões de condição fornecidos ou usando um idioma de consulta semelhante ao KQL no cartão de condição de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="c7d48-112">You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card.</span></span> <span data-ttu-id="c7d48-113">A sintaxe KQL comum, como e, ou, não e NEAR (n), é suportada, assim como um curinga de vários caracteres à direita (\*).</span><span class="sxs-lookup"><span data-stu-id="c7d48-113">Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="c7d48-114">A tabela a seguir lista as propriedades que você pode pesquisar usando uma consulta de palavra-chave KQL.</span><span class="sxs-lookup"><span data-stu-id="c7d48-114">The following table lists the properties that you can search for using a KQL keyword query.</span></span> <span data-ttu-id="c7d48-115">Como alternativa, você pode usar um cartão de condição para na ferramenta de pesquisa de descoberta eletrônica avançada para adicionar uma condição (para propriedades selecionadas) a uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c7d48-115">Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="c7d48-116">**Propriedade**</span><span class="sxs-lookup"><span data-stu-id="c7d48-116">**Property**</span></span>|<span data-ttu-id="c7d48-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c7d48-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c7d48-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="c7d48-118">**caselabel**</span></span> <br/> | <span data-ttu-id="c7d48-119">O nome da marca criada/aplicada quando um documento é marcado.</span><span class="sxs-lookup"><span data-stu-id="c7d48-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="c7d48-120">**custódia**</span><span class="sxs-lookup"><span data-stu-id="c7d48-120">**custodian**</span></span> <br/> | <span data-ttu-id="c7d48-121">Os responsáveis associados a um documento; sujeito a limitações.</span><span class="sxs-lookup"><span data-stu-id="c7d48-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="c7d48-122">**data**</span><span class="sxs-lookup"><span data-stu-id="c7d48-122">**date**</span></span> <br/> | <span data-ttu-id="c7d48-123">Data de envio de email; a data de modificação para documentos de site.</span><span class="sxs-lookup"><span data-stu-id="c7d48-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="c7d48-124">**FileID**</span><span class="sxs-lookup"><span data-stu-id="c7d48-124">**fileid**</span></span> <br/> | <span data-ttu-id="c7d48-125">A ID do arquivo no caso.</span><span class="sxs-lookup"><span data-stu-id="c7d48-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="c7d48-126">**filetype**</span><span class="sxs-lookup"><span data-stu-id="c7d48-126">**filetype**</span></span> <br/> | <span data-ttu-id="c7d48-127">A extensão de arquivo nativo.</span><span class="sxs-lookup"><span data-stu-id="c7d48-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="c7d48-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="c7d48-128">**fileclass**</span></span> <br/> | <span data-ttu-id="c7d48-129">Email, documento ou anexo.</span><span class="sxs-lookup"><span data-stu-id="c7d48-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="c7d48-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="c7d48-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="c7d48-131">O remetente de email; o autor para documentos de site.</span><span class="sxs-lookup"><span data-stu-id="c7d48-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="c7d48-132">**size**</span><span class="sxs-lookup"><span data-stu-id="c7d48-132">**size**</span></span> <br/> | <span data-ttu-id="c7d48-133">O tamanho do arquivo em KB.</span><span class="sxs-lookup"><span data-stu-id="c7d48-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="c7d48-134">**subjecttitle**</span><span class="sxs-lookup"><span data-stu-id="c7d48-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="c7d48-135">O assunto de email; o título dos documentos do site.</span><span class="sxs-lookup"><span data-stu-id="c7d48-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="c7d48-136">**bcc**</span><span class="sxs-lookup"><span data-stu-id="c7d48-136">**bcc**</span></span> <br/> | <span data-ttu-id="c7d48-137">O campo Cco de um email.</span><span class="sxs-lookup"><span data-stu-id="c7d48-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="c7d48-138">**cc**</span><span class="sxs-lookup"><span data-stu-id="c7d48-138">**cc**</span></span> <br/> | <span data-ttu-id="c7d48-139">O campo CC de um email.</span><span class="sxs-lookup"><span data-stu-id="c7d48-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="c7d48-140">**participants**</span><span class="sxs-lookup"><span data-stu-id="c7d48-140">**participants**</span></span> <br/> | <span data-ttu-id="c7d48-141">O endereço de email de todos os participantes de um thread de email, incluindo links ausentes.</span><span class="sxs-lookup"><span data-stu-id="c7d48-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="c7d48-142">**received**</span><span class="sxs-lookup"><span data-stu-id="c7d48-142">**received**</span></span> <br/> | <span data-ttu-id="c7d48-143">A data em que um email foi recebido.</span><span class="sxs-lookup"><span data-stu-id="c7d48-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="c7d48-144">**recipients**</span><span class="sxs-lookup"><span data-stu-id="c7d48-144">**recipients**</span></span> <br/> | <span data-ttu-id="c7d48-145">Destinatários de um email, incluídos nos campos para, CC ou Cco.</span><span class="sxs-lookup"><span data-stu-id="c7d48-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="c7d48-146">**sender**</span><span class="sxs-lookup"><span data-stu-id="c7d48-146">**sender**</span></span> <br/> | <span data-ttu-id="c7d48-147">O remetente de um email.</span><span class="sxs-lookup"><span data-stu-id="c7d48-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="c7d48-148">**lastmodifieddate**</span><span class="sxs-lookup"><span data-stu-id="c7d48-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="c7d48-149">A data da última modificação de um documento de site.</span><span class="sxs-lookup"><span data-stu-id="c7d48-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="c7d48-150">**sent**</span><span class="sxs-lookup"><span data-stu-id="c7d48-150">**sent**</span></span> <br/> | <span data-ttu-id="c7d48-151">A data de envio de um email.</span><span class="sxs-lookup"><span data-stu-id="c7d48-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="c7d48-152">**to**</span><span class="sxs-lookup"><span data-stu-id="c7d48-152">**to**</span></span> <br/> | <span data-ttu-id="c7d48-153">O destinatário listado no campo para de um email.</span><span class="sxs-lookup"><span data-stu-id="c7d48-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="c7d48-154">**autor**</span><span class="sxs-lookup"><span data-stu-id="c7d48-154">**author**</span></span> <br/> | <span data-ttu-id="c7d48-155">O autor de um documento de site.</span><span class="sxs-lookup"><span data-stu-id="c7d48-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="c7d48-156">**title**</span><span class="sxs-lookup"><span data-stu-id="c7d48-156">**title**</span></span> <br/> | <span data-ttu-id="c7d48-157">O título de um documento de site.</span><span class="sxs-lookup"><span data-stu-id="c7d48-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="c7d48-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="c7d48-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="c7d48-159">O tema dominante de um item.</span><span class="sxs-lookup"><span data-stu-id="c7d48-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="c7d48-160">**themelist**\*</span><span class="sxs-lookup"><span data-stu-id="c7d48-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="c7d48-161">Temas associados a um item.</span><span class="sxs-lookup"><span data-stu-id="c7d48-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="c7d48-162">**readpercentile_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="c7d48-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="c7d48-163">O percentil de leitura de um item, para o problema definido por [issuenum].</span><span class="sxs-lookup"><span data-stu-id="c7d48-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="c7d48-164">**relevancescore_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="c7d48-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="c7d48-165">A pontuação de relevância de um item, para o problema definido por [issuenum].</span><span class="sxs-lookup"><span data-stu-id="c7d48-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="c7d48-166">**relevancetag_ [TagName]**\*\*</span><span class="sxs-lookup"><span data-stu-id="c7d48-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="c7d48-167">Se um item tiver sido marcado manualmente para relevância, a marca definida por [TagName].</span><span class="sxs-lookup"><span data-stu-id="c7d48-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="c7d48-168">\*Disponível somente se o módulo de temas tiver sido executado.</span><span class="sxs-lookup"><span data-stu-id="c7d48-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="c7d48-169">\*\*Disponível somente se o módulo de relevância tiver sido executado.</span><span class="sxs-lookup"><span data-stu-id="c7d48-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="c7d48-170">Como alternativa, você pode usar um cartão de condição na ferramenta de pesquisa de descoberta eletrônica avançada para adicionar uma condição (para propriedades selecionadas) a uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c7d48-170">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span> <span data-ttu-id="c7d48-171">A captura de tela a seguir mostra as condições que podem ser adicionadas a uma consulta.</span><span class="sxs-lookup"><span data-stu-id="c7d48-171">The following screenshot shows the conditions that can be added to a query.</span></span> <span data-ttu-id="c7d48-172">A coluna **grupo** indica se a propriedade se aplica a emails, documentos de site ou ambos (indicados pelo valor *comum*).</span><span class="sxs-lookup"><span data-stu-id="c7d48-172">The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*).</span></span> <span data-ttu-id="c7d48-173">Essa coluna também identifica as propriedades pesquisáveis que estão disponíveis após a execução do módulo de relevância.</span><span class="sxs-lookup"><span data-stu-id="c7d48-173">This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![Condições de pesquisa na ferramenta de pesquisa de descoberta eletrônica avançada](../media/AeDSearchConditions.png)

<span data-ttu-id="c7d48-175">Para obter mais informações sobre propriedades pesquisáveis, consulte [keyword queries and Search Conditions](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="c7d48-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c7d48-176">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c7d48-176">Related topics</span></span>

[<span data-ttu-id="c7d48-177">Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="c7d48-177">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c7d48-178">Noções básicas sobre avaliação em relevância</span><span class="sxs-lookup"><span data-stu-id="c7d48-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c7d48-179">Marcação e avaliação</span><span class="sxs-lookup"><span data-stu-id="c7d48-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c7d48-180">Treinamento de marcação e relevância</span><span class="sxs-lookup"><span data-stu-id="c7d48-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c7d48-181">Análise de relevância de rastreamento</span><span class="sxs-lookup"><span data-stu-id="c7d48-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c7d48-182">Decidindo com base nos resultados</span><span class="sxs-lookup"><span data-stu-id="c7d48-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c7d48-183">Testando análise de relevância</span><span class="sxs-lookup"><span data-stu-id="c7d48-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

