---
title: Investigar itens parcialmente indexados na descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Saiba como gerenciar itens parcialmente indexados (ou não indexados) do Exchange, SharePoint e OneDrive em sua organização.
ms.openlocfilehash: ed85a9351aad340c5840b6b9b9ea6e55833ed527
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817520"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="b0ca2-103">Investigar itens parcialmente indexados na descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="b0ca2-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="b0ca2-104">Uma pesquisa de conteúdo que você executa a partir do centro de conformidade & segurança inclui automaticamente itens parcialmente indexados nos resultados estimados da pesquisa quando você executa uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-104">A Content Search that you run from the Security & Compliance Center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="b0ca2-105">Itens parcialmente indexados são itens de caixa de correio do Exchange e documentos em sites do SharePoint e do OneDrive for Business que por algum motivo não foram completamente indexados para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="b0ca2-106">A maioria das mensagens de email e documentos de site são indexados com êxito porque estão dentro dos [limites de indexação para mensagens de email](limits-for-content-search.md#indexing-limits-for-email-messages).</span><span class="sxs-lookup"><span data-stu-id="b0ca2-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="b0ca2-107">No entanto, alguns itens podem exceder esses limites de indexação e serão parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="b0ca2-108">Aqui estão outras razões pelas quais os itens não podem ser indexados para pesquisa e são retornados como itens parcialmente indexados quando você executa uma pesquisa de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="b0ca2-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="b0ca2-109">As mensagens de email têm um arquivo anexado de um tipo de arquivo que não pode ser indexado; na maioria dos casos, o tipo de arquivo é [não reconhecido ou não tem suporte para indexação](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="b0ca2-109">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="b0ca2-110">As mensagens de email têm um arquivo anexado sem um manipulador válido, como arquivos de imagem; Esta é a causa mais comum de itens de email parcialmente indexados</span><span class="sxs-lookup"><span data-stu-id="b0ca2-110">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="b0ca2-111">Muitos arquivos anexados a uma mensagem de email</span><span class="sxs-lookup"><span data-stu-id="b0ca2-111">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="b0ca2-112">Um arquivo anexado a uma mensagem de email é muito grande</span><span class="sxs-lookup"><span data-stu-id="b0ca2-112">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="b0ca2-113">O tipo de arquivo tem suporte para indexação, mas ocorreu um erro de indexação para um arquivo específico</span><span class="sxs-lookup"><span data-stu-id="b0ca2-113">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="b0ca2-114">Embora varie, a maioria dos clientes da organização tem menos de 1% do conteúdo por volume e menos de 12% do conteúdo por tamanho parcialmente indexado.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-114">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="b0ca2-115">O motivo para a diferença entre o volume versus o tamanho é que os arquivos maiores têm uma maior probabilidade de conteúdo que não pode ser completamente indexado.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-115">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="b0ca2-116">Por que a contagem de itens parcialmente indexados é alterada para uma pesquisa?</span><span class="sxs-lookup"><span data-stu-id="b0ca2-116">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="b0ca2-117">Após executar uma pesquisa de conteúdo no centro de conformidade de & de segurança, o número total e o tamanho de itens parcialmente indexados nos locais que foram pesquisados são listados nas estatísticas de resultados de pesquisa que são exibidas nas estatísticas detalhadas da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-117">After you run a Content Search in the Security & Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="b0ca2-118">Observe que são chamados de *itens não indexados* nas estatísticas de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-118">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="b0ca2-119">Veja algumas coisas que afetarão o número de itens parcialmente indexados retornados nos resultados da pesquisa:</span><span class="sxs-lookup"><span data-stu-id="b0ca2-119">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="b0ca2-120">Se um item for parcialmente indexado e corresponder à consulta de pesquisa, ele será incluído na contagem (e no tamanho) dos itens de resultado de pesquisa e dos itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-120">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="b0ca2-121">No entanto, quando os resultados da mesma pesquisa são exportados, o item é incluído somente com o conjunto de resultados de pesquisa; Ele não está incluído como um item parcialmente indexado.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-121">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="b0ca2-122">Se você especificar um intervalo de datas para uma consulta de pesquisa (incluindo-a na consulta de palavra-chave ou usando uma condição), qualquer item parcialmente indexado que não coincida com o intervalo de datas não será incluído na contagem de itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-122">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="b0ca2-123">Somente os itens parcialmente indexados que estão no intervalo de datas são incluídos na contagem de itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-123">Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="b0ca2-124">**Observação:** Os itens parcialmente indexados localizados nos sites do SharePoint e do OneDrive *não são* incluídos na estimativa de itens parcialmente indexados que são exibidos nas estatísticas detalhadas da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-124">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="b0ca2-125">No entanto, os itens parcialmente indexados podem ser exportados quando você exporta os resultados de uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-125">However, partially indexed items can be exported when you export the results of a Content Search.</span></span> <span data-ttu-id="b0ca2-126">Por exemplo, se você só pesquisa sites em uma pesquisa de conteúdo, o número estimado de itens parcialmente indexados será zero.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-126">For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="b0ca2-127">Calculando a taxa de itens parcialmente indexados em sua organização</span><span class="sxs-lookup"><span data-stu-id="b0ca2-127">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="b0ca2-128">Para entender a exposição da sua organização a itens parcialmente indexados, você pode executar uma pesquisa de todo o conteúdo em todas as caixas de correio (usando uma consulta de palavra-chave em branco).</span><span class="sxs-lookup"><span data-stu-id="b0ca2-128">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="b0ca2-129">No exemplo a seguir, há itens totalmente indexados de 56.208 (4.830 MB) e 470 (316 MB) parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-129">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Exemplo de estatísticas de pesquisa mostrando itens parcialmente indexados](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="b0ca2-131">Você pode determinar a porcentagem de itens parcialmente indexados usando os seguintes cálculos.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-131">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="b0ca2-132">**Para calcular a taxa de itens parcialmente indexados em sua organização:**</span><span class="sxs-lookup"><span data-stu-id="b0ca2-132">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="b0ca2-133">Usando os resultados da pesquisa do exemplo anterior,. 84% de todos os itens de caixas de correio são parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-133">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="b0ca2-134">**Para calcular a porcentagem do tamanho de itens parcialmente indexados em sua organização:**</span><span class="sxs-lookup"><span data-stu-id="b0ca2-134">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="b0ca2-135">Portanto, no exemplo anterior, 6,54% do tamanho total dos itens de caixa de correio são de itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-135">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="b0ca2-136">Conforme mencionado anteriormente, a maioria das organizações tem menos de 1% de conteúdo por volume e menos de 12% de conteúdo por tamanho parcialmente indexado.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-136">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="b0ca2-137">Trabalhar com itens parcialmente indexados</span><span class="sxs-lookup"><span data-stu-id="b0ca2-137">Working with partially indexed items</span></span>

<span data-ttu-id="b0ca2-138">Em casos em que você precisa examinar itens parcialmente para validar que eles não contêm informações relevantes, é possível [exportar um relatório de pesquisa de conteúdo](export-a-content-search-report.md) que contenha informações sobre itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-138">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="b0ca2-139">Ao exportar um relatório de pesquisa de conteúdo, certifique-se de escolher uma das opções de exportação que inclui itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-139">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![Escolha a segunda ou terceira opção para exportar itens parcialmente indexados](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="b0ca2-141">Quando você exporta resultados de pesquisa de conteúdo ou um relatório de pesquisa de conteúdo usando uma destas opções, a exportação inclui um relatório chamado Items.csv não indexado.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-141">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="b0ca2-142">Este relatório inclui a maioria das mesmas informações que o arquivo de ResultsLog.csv; no entanto, o arquivo Items.csv não indexado também inclui dois campos relacionados a itens parcialmente indexados: **marcas de erro** e **Propriedades de erro**.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-142">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="b0ca2-143">Esses campos contêm informações sobre o erro de indexação para cada item parcialmente indexado.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-143">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="b0ca2-144">O uso das informações nesses dois campos pode ajudá-lo a determinar se o erro de indexação para um determinado impacto em sua investigação.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-144">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="b0ca2-145">Se isso acontecer, você poderá executar uma pesquisa de conteúdo direcionado e recuperar e exportar mensagens de email específicas e documentos do SharePoint ou do OneDrive para que possa examiná-las para determinar se elas são relevantes para a investigação.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-145">If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="b0ca2-146">Para obter instruções passo a passo, consulte [preparar um arquivo CSV para uma pesquisa de conteúdo direcionado no Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="b0ca2-146">For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="b0ca2-147">**Observação:** O arquivo Items.csv não indexado também contém campos chamados de **tipo de erro** e mensagem de **erro**.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-147">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="b0ca2-148">Estes são campos herdados que contêm informações semelhantes às informações nos campos marcas de **erro** e **Propriedades de erro** , mas com informações menos detalhadas.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-148">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="b0ca2-149">Você pode ignorar com segurança esses campos herdados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-149">You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="b0ca2-150">Erros relacionados a itens parcialmente indexados</span><span class="sxs-lookup"><span data-stu-id="b0ca2-150">Errors related to partially indexed items</span></span>

<span data-ttu-id="b0ca2-151">Marcas de erro são comparadas de duas partes de informação, o erro e o tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-151">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="b0ca2-152">Por exemplo, neste par erro/filetype:</span><span class="sxs-lookup"><span data-stu-id="b0ca2-152">For example, in this error/filetype pair:</span></span>

```text
 parseroutputsize_xls
```

   
 <span data-ttu-id="b0ca2-153">`parseroutputsize`é o erro e `xls` é o tipo de arquivo do arquivo no qual o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-153">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="b0ca2-154">Nos casos em que o tipo de arquivo não foi reconhecido ou o tipo de arquivo não se aplica ao erro, você verá o valor `noformat` no lugar do tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-154">In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="b0ca2-155">Veja a seguir uma lista de erros de indexação e uma descrição da possível causa do erro.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-155">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="b0ca2-156">**Marca de erro**</span><span class="sxs-lookup"><span data-stu-id="b0ca2-156">**Error tag**</span></span>|<span data-ttu-id="b0ca2-157">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b0ca2-157">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="b0ca2-158">Uma mensagem de email tinha muitos anexos e alguns desses anexos não foram processados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-158">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="b0ca2-159">O recuperador de conteúdo e o analisador de documentos encontraram muitos níveis de anexos aninhados dentro de outros anexos.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-159">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="b0ca2-160">Alguns desses anexos não foram processados.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-160">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="b0ca2-161">Um anexo falhou ao decodificar porque estava protegido por RMS.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-161">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="b0ca2-162">Um arquivo anexado a uma mensagem de email era muito grande e não pôde ser processado.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-162">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="b0ca2-163">Ao gravar a mensagem de email processada no índice, uma das propriedades indexáveis era muito grande e estava truncada.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-163">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="b0ca2-164">As propriedades truncadas estão listadas no campo Propriedades do erro.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-164">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="b0ca2-165">Uma mensagem de email continha texto que não pôde ser processado como Unicode válido.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-165">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="b0ca2-166">A indexação deste item pode estar incompleta.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-166">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="b0ca2-167">O conteúdo do anexo ou da mensagem de email é criptografado, e o Microsoft 365 não pôde decodificar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-167">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="b0ca2-168">Ocorreu um erro desconhecido durante a análise.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-168">An unknown error occurred during parsing.</span></span> <span data-ttu-id="b0ca2-169">Isso normalmente resulta de um bug de software ou uma falha de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-169">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="b0ca2-170">Um anexo era muito grande para o analisador manipular, e a análise desse anexo não aconteceu ou não foi concluída.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-170">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="b0ca2-171">Um anexo foi malformado e não pôde ser manipulado pelo analisador.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-171">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="b0ca2-172">Esse resultado pode ser de formatos de arquivo antigos, arquivos criados por software incompatível ou vírus que fingim ser algo diferente de alegado.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-172">This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="b0ca2-173">A saída da análise de um anexo era muito grande e teve de ser truncada.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-173">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="b0ca2-174">Um anexo tinha um tipo de arquivo que o Microsoft 365 não pôde detectar.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-174">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="b0ca2-175">Um anexo tinha um tipo de arquivo que o Office 365could detectou, mas não há suporte para a análise desse tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-175">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="b0ca2-176">O valor de uma propriedade de email no repositório do Exchange era muito grande para ser recuperado e a mensagem não pôde ser processada.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-176">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="b0ca2-177">Isso geralmente ocorre apenas na Propriedade Body de uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-177">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="b0ca2-178">O recuperador de conteúdo falhou ao decodificar uma mensagem protegida por RMS.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-178">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="b0ca2-179">Muitas palavras foram identificadas no documento durante a indexação.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-179">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="b0ca2-180">Processamento da propriedade parado ao atingir o limite, e a propriedade será truncada.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-180">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="b0ca2-181">Os campos de erro descrevem quais campos são afetados pelo erro de processamento listado no campo marcas de erro.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-181">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="b0ca2-182">Se você estiver pesquisando uma propriedade como `subject` ou `participants` , os erros no corpo da mensagem não afetarão os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-182">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="b0ca2-183">Isso pode ser útil ao determinar exatamente quais itens parcialmente indexados você talvez precise investigar.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-183">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="b0ca2-184">Usando um script do PowerShell para determinar a exposição da sua organização a itens de email parcialmente indexados</span><span class="sxs-lookup"><span data-stu-id="b0ca2-184">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="b0ca2-185">As etapas a seguir mostram como executar um script do PowerShell que pesquisa todos os itens em todas as caixas de correio do Exchange e, em seguida, gera um relatório sobre a taxa da organização de itens de email parcialmente indexados (por contagem e por tamanho) e exibe o número de itens (e o tipo de arquivo) para cada erro de indexação que ocorre.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-185">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="b0ca2-186">Use as descrições de marcas de erro na seção anterior para identificar o erro de indexação.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-186">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="b0ca2-187">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="b0ca2-187">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```powershell
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```

2. <span data-ttu-id="b0ca2-188">[Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://go.microsoft.com/fwlink/p/?linkid=627084).</span><span class="sxs-lookup"><span data-stu-id="b0ca2-188">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="b0ca2-189">Em segurança & centro de conformidade do PowerShell, vá para a pasta onde você salvou o script na etapa 1 e execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b0ca2-189">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

<span data-ttu-id="b0ca2-190">Aqui está um exemplo de saída retornada pelo script.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-190">Here's an example fo the output returned by the script.</span></span>
  
![Exemplo de saída do script que gera um relatório sobre a exposição da sua organização para itens de email parcialmente indexados](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="b0ca2-192">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b0ca2-192">Note the following:</span></span>
  
1. <span data-ttu-id="b0ca2-193">O número total e o tamanho dos itens de email e a taxa da sua organização de itens de email parcialmente indexados (por contagem e por tamanho)</span><span class="sxs-lookup"><span data-stu-id="b0ca2-193">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="b0ca2-194">Uma lista de marcas de erro e os tipos de arquivo correspondentes para os quais o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-194">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b0ca2-195">Confira também</span><span class="sxs-lookup"><span data-stu-id="b0ca2-195">See also</span></span>

[<span data-ttu-id="b0ca2-196">Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365</span><span class="sxs-lookup"><span data-stu-id="b0ca2-196">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
