---
title: Investigando itens parcialmente indexados na Descoberta eDiscovery
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
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Saiba como gerenciar itens parcialmente indexados (também chamados de itens não indexados) do Exchange, do SharePoint e do OneDrive for Business em sua organização.
ms.openlocfilehash: 5d30c0f7c6ae77236ba7fd9f2dbfcc7a0397ae21
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922575"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="12b0a-103">Investigando itens parcialmente indexados na Descoberta eDiscovery</span><span class="sxs-lookup"><span data-stu-id="12b0a-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="12b0a-104">Uma pesquisa de Descoberta Automática que você executar do centro de conformidade do Microsoft 365 inclui automaticamente itens parcialmente indexados nos resultados estimados da pesquisa ao executar uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="12b0a-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="12b0a-105">Itens parcialmente indexados são itens de caixa de correio e documentos do Exchange em sites do SharePoint e do OneDrive for Business que, por algum motivo, não foram totalmente indexados para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="12b0a-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="12b0a-106">A maioria das mensagens de email e documentos de site são indexadas com êxito porque estão dentro dos [limites de indexação para mensagens de email.](limits-for-content-search.md#indexing-limits-for-email-messages)</span><span class="sxs-lookup"><span data-stu-id="12b0a-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="12b0a-107">No entanto, alguns itens podem exceder esses limites de indexação e serão parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="12b0a-108">Aqui estão outros motivos pelos quais os itens não podem ser indexados para pesquisa e são retornados como itens parcialmente indexados quando você executar uma pesquisa de Descoberta E:</span><span class="sxs-lookup"><span data-stu-id="12b0a-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="12b0a-109">As mensagens de email têm um arquivo anexado sem um manipulador válido, como arquivos de imagem; essa é a causa mais comum de itens de email parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="12b0a-110">Muitos arquivos anexados a uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="12b0a-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="12b0a-111">Um arquivo anexado a uma mensagem de email é muito grande.</span><span class="sxs-lookup"><span data-stu-id="12b0a-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="12b0a-112">O tipo de arquivo é compatível com a indexação, mas ocorreu um erro de indexação com um arquivo específico.</span><span class="sxs-lookup"><span data-stu-id="12b0a-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="12b0a-113">Embora varie, a maioria dos clientes de organizações tem menos de 1% do conteúdo por volume e menos de 12% do conteúdo por tamanho parcialmente indexado.</span><span class="sxs-lookup"><span data-stu-id="12b0a-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="12b0a-114">O motivo da diferença entre o volume e o tamanho é que arquivos maiores têm uma maior probabilidade de conter conteúdo que não pode ser totalmente indexado.</span><span class="sxs-lookup"><span data-stu-id="12b0a-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="12b0a-115">Por que a contagem de itens parcialmente indexada muda para uma pesquisa?</span><span class="sxs-lookup"><span data-stu-id="12b0a-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="12b0a-116">Depois que você executar uma pesquisa de Descobertas E, o número total e o tamanho de itens parcialmente indexados nos locais pesquisados são listados nas estatísticas de resultados da pesquisa exibidas nas estatísticas detalhadas da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="12b0a-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="12b0a-117">Observe que eles são chamados de itens  *não índicedos*  nas estatísticas de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="12b0a-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="12b0a-118">Aqui estão algumas coisas que afetarão o número de itens parcialmente indexados que são retornados nos resultados da pesquisa:</span><span class="sxs-lookup"><span data-stu-id="12b0a-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="12b0a-119">Se um item for parcialmente indexado e corresponde à consulta de pesquisa, ele será incluído na contagem (e no tamanho) dos itens de resultado da pesquisa e itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="12b0a-120">No entanto, quando os resultados dessa mesma pesquisa são exportados, o item é incluído apenas com o conjunto de resultados da pesquisa; ele não está incluído como um item parcialmente indexado.</span><span class="sxs-lookup"><span data-stu-id="12b0a-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="12b0a-121">Se você especificar um intervalo de datas para uma consulta de pesquisa (incluindo-a na consulta de palavra-chave ou usando uma condição), qualquer item parcialmente indexado que não corresponder ao intervalo de datas não será incluído na contagem de itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-121">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="12b0a-122">Itens parcialmente indexados que se enquadram no intervalo de datas são incluídos na contagem de itens indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-122">Partially indexed items that fall within date range are included in the count of indexed items.</span></span>

  > [!NOTE]
  > <span data-ttu-id="12b0a-123">Os itens parcialmente indexados localizados nos *sites* do SharePoint e do OneDrive não são incluídos na estimativa de itens parcialmente indexados exibidos nas estatísticas detalhadas da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="12b0a-123">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="12b0a-124">No entanto, itens parcialmente indexados podem ser exportados quando você exporta os resultados de uma pesquisa de Descoberta e.</span><span class="sxs-lookup"><span data-stu-id="12b0a-124">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="12b0a-125">Por exemplo, se você pesquisar apenas sites, o número estimado parcialmente indexado itens será zero.</span><span class="sxs-lookup"><span data-stu-id="12b0a-125">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="12b0a-126">Calculando a proporção de itens parcialmente indexados em sua organização</span><span class="sxs-lookup"><span data-stu-id="12b0a-126">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="12b0a-127">Para entender a exposição da sua organização a itens parcialmente indexados, você pode executar uma pesquisa de todo o conteúdo em todas as caixas de correio (usando uma consulta de palavra-chave em branco).</span><span class="sxs-lookup"><span data-stu-id="12b0a-127">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="12b0a-128">No exemplo a seguir, há 56.208 (4.830 MB) itens totalmente indexados e 470 (316 MB) parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-128">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Exemplo de estatísticas de pesquisa mostrando itens parcialmente indexados](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="12b0a-130">Você pode determinar a porcentagem de itens parcialmente indexados usando os cálculos a seguir.</span><span class="sxs-lookup"><span data-stu-id="12b0a-130">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="12b0a-131">**Para calcular a proporção de itens parcialmente indexados em sua organização:**</span><span class="sxs-lookup"><span data-stu-id="12b0a-131">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

<span data-ttu-id="12b0a-132">Usando os resultados da pesquisa do exemplo anterior, 0,84% de todos os itens de caixas de correio são parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-132">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="12b0a-133">**Para calcular a porcentagem do tamanho de itens parcialmente indexados em sua organização:**</span><span class="sxs-lookup"><span data-stu-id="12b0a-133">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="12b0a-134">Portanto, no exemplo anterior, 6,54% do tamanho total de itens de caixa de correio são de itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-134">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="12b0a-135">Como mencionado anteriormente, a maioria dos clientes de organizações tem menos de 1% do conteúdo por volume e menos de 12% do conteúdo por tamanho parcialmente indexado.</span><span class="sxs-lookup"><span data-stu-id="12b0a-135">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="12b0a-136">Trabalhando com itens parcialmente indexados</span><span class="sxs-lookup"><span data-stu-id="12b0a-136">Working with partially indexed items</span></span>

<span data-ttu-id="12b0a-137">Nos casos em que você precisa examinar parcialmente itens para validar que eles não contêm informações relevantes, você pode [exportar](export-a-content-search-report.md) um relatório de pesquisa de conteúdo que contém informações sobre itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-137">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="12b0a-138">Ao exportar um relatório de pesquisa de conteúdo, certifique-se de escolher uma das opções de exportação que inclui itens parcialmente indexados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-138">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![Escolha a segunda ou a terceira opção para exportar itens parcialmente indexados](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="12b0a-140">Quando você exporta resultados de pesquisa de Descoberta Items.csv.</span><span class="sxs-lookup"><span data-stu-id="12b0a-140">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="12b0a-141">Este relatório inclui a maioria das mesmas informações que o arquivo ResultsLog.csv arquivo; no entanto, o arquivo Items.csv também inclui dois campos relacionados a itens parcialmente **indexados:** **Marcas** de Erro e Propriedades de Erro .</span><span class="sxs-lookup"><span data-stu-id="12b0a-141">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="12b0a-142">Esses campos contêm informações sobre o erro de indexação para cada item parcialmente indexado.</span><span class="sxs-lookup"><span data-stu-id="12b0a-142">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="12b0a-143">O uso das informações nesses dois campos pode ajudá-lo a determinar se o erro de indexação de um determinado afeta ou não sua investigação.</span><span class="sxs-lookup"><span data-stu-id="12b0a-143">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="12b0a-144">Se isso acontecer, você poderá executar uma pesquisa direcionada e recuperar e exportar mensagens de email específicas e documentos do SharePoint ou do OneDrive para que você possa examiná-los para determinar se elas são relevantes para sua investigação.</span><span class="sxs-lookup"><span data-stu-id="12b0a-144">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="12b0a-145">Para obter instruções passo a passo, consulte [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="12b0a-145">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="12b0a-146">O arquivo Items.csv não Items.csv também contém campos denominados **Tipo de** Erro e Mensagem **de Erro.**</span><span class="sxs-lookup"><span data-stu-id="12b0a-146">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="12b0a-147">Esses são campos herdados que contêm informações semelhantes  às informações nos campos **Marcas** de Erro e Propriedades de Erro, mas com informações menos detalhadas.</span><span class="sxs-lookup"><span data-stu-id="12b0a-147">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="12b0a-148">Você pode ignorar com segurança esses campos herddos.</span><span class="sxs-lookup"><span data-stu-id="12b0a-148">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="12b0a-149">Erros relacionados a itens parcialmente indexados</span><span class="sxs-lookup"><span data-stu-id="12b0a-149">Errors related to partially indexed items</span></span>

<span data-ttu-id="12b0a-150">As marcas de erro são feitas de duas informações, o erro e o tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="12b0a-150">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="12b0a-151">Por exemplo, neste par de erro/tipo de arquivo:</span><span class="sxs-lookup"><span data-stu-id="12b0a-151">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="12b0a-152">`parseroutputsize` é o erro e `xls` é o tipo de arquivo do arquivo em que o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="12b0a-152">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="12b0a-153">Nos casos em que o tipo de arquivo não foi reconhecido ou o tipo de arquivo não se aplica ao erro, você verá o valor no lugar do tipo `noformat` de arquivo.</span><span class="sxs-lookup"><span data-stu-id="12b0a-153">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="12b0a-154">Veja a seguir uma lista de erros de indexação e uma descrição da possível causa do erro.</span><span class="sxs-lookup"><span data-stu-id="12b0a-154">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="12b0a-155">Marca de erro</span><span class="sxs-lookup"><span data-stu-id="12b0a-155">Error tag</span></span> | <span data-ttu-id="12b0a-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="12b0a-156">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="12b0a-157">Uma mensagem de email tinha muitos anexos e alguns desses anexos não foram processados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-157">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="12b0a-158">O recuperador de conteúdo e o analisador de documentos encontraram muitos níveis de anexos aninhados dentro de outros anexos.</span><span class="sxs-lookup"><span data-stu-id="12b0a-158">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="12b0a-159">Alguns desses anexos não foram processados.</span><span class="sxs-lookup"><span data-stu-id="12b0a-159">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="12b0a-160">Falha na decodificação de um anexo porque estava protegido por RMS.</span><span class="sxs-lookup"><span data-stu-id="12b0a-160">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="12b0a-161">Um arquivo anexado a uma mensagem de email era muito grande e não podia ser processado.</span><span class="sxs-lookup"><span data-stu-id="12b0a-161">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="12b0a-162">Ao escrever a mensagem de email processada no índice, uma das propriedades indexáveis era muito grande e foi truncada.</span><span class="sxs-lookup"><span data-stu-id="12b0a-162">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="12b0a-163">As propriedades truncadas estão listadas no campo Propriedades de Erro.</span><span class="sxs-lookup"><span data-stu-id="12b0a-163">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="12b0a-164">Uma mensagem de email continha texto que não poderia ser processado como Unicode válido.</span><span class="sxs-lookup"><span data-stu-id="12b0a-164">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="12b0a-165">A indexação para este item pode estar incompleta.</span><span class="sxs-lookup"><span data-stu-id="12b0a-165">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="12b0a-166">O conteúdo do anexo ou da mensagem de email é criptografado e o Microsoft 365 não conseguiu decodificar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="12b0a-166">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="12b0a-167">Ocorreu um erro desconhecido durante a análise.</span><span class="sxs-lookup"><span data-stu-id="12b0a-167">An unknown error occurred during parsing.</span></span> <span data-ttu-id="12b0a-168">Isso normalmente resulta de um bug de software ou de uma falha de serviço.</span><span class="sxs-lookup"><span data-stu-id="12b0a-168">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="12b0a-169">Um anexo era muito grande para o analisador manipular, e a análise desse anexo não aconteceu ou não foi concluída.</span><span class="sxs-lookup"><span data-stu-id="12b0a-169">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="12b0a-170">Um anexo foi malformado e não pôde ser manipulado pelo analisador.</span><span class="sxs-lookup"><span data-stu-id="12b0a-170">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="12b0a-171">Esse resultado pode ser devido a formatos de arquivo antigos, arquivos criados por software incompatível ou vírus que fingem ser algo diferente de reivindicado.</span><span class="sxs-lookup"><span data-stu-id="12b0a-171">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="12b0a-172">A saída da análise de um anexo era muito grande e precisava ser truncada.</span><span class="sxs-lookup"><span data-stu-id="12b0a-172">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="12b0a-173">Um anexo tinha um tipo de arquivo que o Microsoft 365 não detectou.</span><span class="sxs-lookup"><span data-stu-id="12b0a-173">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="12b0a-174">Um anexo tinha um tipo de arquivo que o Office 365 poderia detectar, mas não há suporte para analisar esse tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="12b0a-174">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="12b0a-175">O valor de uma propriedade de email no Exchange Store era muito grande para ser recuperado e a mensagem não pôde ser processada.</span><span class="sxs-lookup"><span data-stu-id="12b0a-175">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="12b0a-176">Normalmente, isso só acontece com a propriedade body de uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="12b0a-176">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="12b0a-177">O recuperador de conteúdo falhou ao decodificar uma mensagem protegida por RMS.</span><span class="sxs-lookup"><span data-stu-id="12b0a-177">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="12b0a-178">Muitas palavras foram identificadas no documento durante a indexação.</span><span class="sxs-lookup"><span data-stu-id="12b0a-178">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="12b0a-179">O processamento da propriedade parou ao atingir o limite e a propriedade é truncada.</span><span class="sxs-lookup"><span data-stu-id="12b0a-179">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="12b0a-180">Os campos de erro descrevem quais campos são afetados pelo erro de processamento listado no campo Marcas de Erro.</span><span class="sxs-lookup"><span data-stu-id="12b0a-180">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="12b0a-181">Se você estiver pesquisando uma propriedade como ou , erros no corpo da mensagem não afetarão os  `subject`  `participants` resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="12b0a-181">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="12b0a-182">Isso pode ser útil ao determinar exatamente quais itens parcialmente indexados você pode precisar investigar mais.</span><span class="sxs-lookup"><span data-stu-id="12b0a-182">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="12b0a-183">Usando um script do PowerShell para determinar a exposição da sua organização a itens de email parcialmente indexados</span><span class="sxs-lookup"><span data-stu-id="12b0a-183">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="12b0a-184">As etapas a seguir mostram como executar um script do PowerShell que pesquisa todos os itens em todas as caixas de correio do Exchange e, em seguida, gera um relatório sobre a taxa de sua organização de itens de email parcialmente indexados (por contagem e por tamanho) e exibe o número de itens (e seu tipo de arquivo) para cada erro de indexação que ocorre.</span><span class="sxs-lookup"><span data-stu-id="12b0a-184">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="12b0a-185">Use as descrições da marca de erro na seção anterior para identificar o erro de indexação.</span><span class="sxs-lookup"><span data-stu-id="12b0a-185">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="12b0a-186">Salve o texto a seguir em um arquivo Windows PowerShell script usando um sufixo de nome de arquivo de .ps1; por exemplo, `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="12b0a-186">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="12b0a-187">[Conectar-se ao PowerShell do Centro de Conformidade e Segurança](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="12b0a-187">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

3. <span data-ttu-id="12b0a-188">No Centro de Conformidade & Segurança do PowerShell, vá para a pasta onde você salvou o script na etapa 1 e execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="12b0a-188">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="12b0a-189">Veja um exemplo para a saída retornada pelo script.</span><span class="sxs-lookup"><span data-stu-id="12b0a-189">Here's an example fo the output returned by the script.</span></span>
  
![Exemplo de saída do script que gera um relatório sobre a exposição da sua organização a itens de email parcialmente indexados](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="12b0a-191">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12b0a-191">Note the following:</span></span>
>  
> - <span data-ttu-id="12b0a-192">O número total e o tamanho dos itens de email e a taxa de itens de email parcialmente indexados da sua organização (por contagem e por tamanho).</span><span class="sxs-lookup"><span data-stu-id="12b0a-192">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="12b0a-193">Uma lista de marcas de erro e os tipos de arquivo correspondentes para os quais o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="12b0a-193">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="12b0a-194">Confira também</span><span class="sxs-lookup"><span data-stu-id="12b0a-194">See also</span></span>

[<span data-ttu-id="12b0a-195">Itens parcialmente indexados na Descoberta eDiscovery</span><span class="sxs-lookup"><span data-stu-id="12b0a-195">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)