---
title: Exportar documentos de um conjunto de revisão
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
description: Saiba como selecionar e exportar conteúdo de um conjunto de revisão para apresentações ou avaliações externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285357"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="d3ed9-103">Exportar documentos de um conjunto de revisão na Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="d3ed9-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="d3ed9-104">A exportação permite que os usuários personalizem o conteúdo incluído no pacote de download.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="d3ed9-105">A ferramenta Exportar fornece uma página de configuração com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="d3ed9-105">The Export tool provides a configuration page with the following settings:</span></span>

![Opções para exportar itens de um conjunto de revisão](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="d3ed9-107">Opções de exportação</span><span class="sxs-lookup"><span data-stu-id="d3ed9-107">Export options</span></span>

- <span data-ttu-id="d3ed9-108">Nome da exportação: Nome do trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="d3ed9-109">Descrição: campo de texto livre para adicionar uma descrição.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="d3ed9-110">Exporte estes documentos:</span><span class="sxs-lookup"><span data-stu-id="d3ed9-110">Export these documents:</span></span>

  - <span data-ttu-id="d3ed9-111">Somente documentos selecionados - Exporta somente os documentos selecionados no momento.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="d3ed9-112">Todos os documentos no conjunto de revisão - Exporta todos os documentos no conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="d3ed9-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="d3ed9-113">Metadata</span><span class="sxs-lookup"><span data-stu-id="d3ed9-113">Metadata</span></span>
  
  - <span data-ttu-id="d3ed9-114">Carregar arquivo – Esse arquivo contém metadados para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="d3ed9-115">consulte [Campos de metadados do documento na Descoberta eDiscovery Avançada](document-metadata-fields-in-Advanced-eDiscovery.md) para obter mais informações sobre quais campos estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="d3ed9-116">Normalmente, esse arquivo pode ser ingerido por ferramentas de Descoberta eDiscovery de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="d3ed9-117">Marcas - Quando selecionada, as informações de marcação serão incluídas no arquivo de carregamento.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="d3ed9-118">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="d3ed9-118">Content</span></span>
  
  - <span data-ttu-id="d3ed9-119">Arquivos nativos - Marque essa caixa de seleção para incluir os arquivos nativos.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="d3ed9-120">Opções de conversa</span><span class="sxs-lookup"><span data-stu-id="d3ed9-120">Conversation options</span></span>
    
    - <span data-ttu-id="d3ed9-121">Arquivos de conversa - Exportar mensagens de chat reconstruídas.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="d3ed9-122">Esse formato apresenta conversas em um formato semelhante ao que os usuários veem no aplicativo nativo.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="d3ed9-123">Mensagens de chat individuais - Exporte os arquivos de conversa originais à medida que são armazenados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="d3ed9-124">Opções</span><span class="sxs-lookup"><span data-stu-id="d3ed9-124">Options</span></span>

  - <span data-ttu-id="d3ed9-125">Arquivos de texto – Inclua versões de texto extraídas de arquivos nativos.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="d3ed9-126">Substituir nativos redacted por PDFs convertidos - se os arquivos PDF redacted são gerados durante a revisão, esses arquivos estão disponíveis para exportação.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="d3ed9-127">Você pode optar por exportar somente os arquivos nativos que foram editados (não selecionando essa opção) ou pode selecionar essa opção para exportar os arquivos PDF que contêm as redação reais.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="d3ed9-128">Opções de saída (o conteúdo exportado está disponível para download diretamente por meio de um navegador da Web ou pode ser enviado para uma conta de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="d3ed9-129">As duas primeiras opções habilitam o download direto.)</span><span class="sxs-lookup"><span data-stu-id="d3ed9-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="d3ed9-130">Arquivos soltos e PSTs (o email é adicionado a PSTs quando possível) - Os arquivos são exportados em um formato semelhante à estrutura de diretório original vista pelos usuários em seus aplicativos nativos.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="d3ed9-131">Para obter mais informações, consulte a [seção Arquivos soltos e estrutura de exportação de PST.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="d3ed9-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="d3ed9-132">Estrutura de diretórios condensados - Os arquivos são exportados e incluídos no download.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="d3ed9-133">Estrutura de diretório condensada exportada para sua conta de Armazenamento do Azure : os arquivos são exportados para o adcouunt do Armazenamento do Azure da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="d3ed9-134">Arquivos soltos e estrutura de exportação PST</span><span class="sxs-lookup"><span data-stu-id="d3ed9-134">Loose files and PST export structure</span></span>

<span data-ttu-id="d3ed9-135">Se você selecionar essa opção de exportação, o conteúdo exportado será organizado na seguinte estrutura:</span><span class="sxs-lookup"><span data-stu-id="d3ed9-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="d3ed9-136">Pasta raiz – essa pasta no nome ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="d3ed9-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="d3ed9-137">Export_load_file.csv - Arquivo de metadados.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="d3ed9-138">Summary.csv - Um arquivo de resumo que também contém estatísticas de exportação.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="d3ed9-139">Exchange – Essa pasta contém todo o conteúdo do Exchange no formato de arquivo nativo.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="d3ed9-140">Os arquivos nativos serão substituídos por PDFs redacionados se você tiver selecionado a opção Substituir nativos **redacted por PDFs convertidos.**</span><span class="sxs-lookup"><span data-stu-id="d3ed9-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="d3ed9-141">SharePoint = Esta pasta contém todo o conteúdo nativo do SharePoint em um formato de arquivo nativo.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="d3ed9-142">Os arquivos nativos serão substituídos por PDFs redacionados se você tiver selecionado a opção Substituir nativos **redacted por PDFs convertidos.**</span><span class="sxs-lookup"><span data-stu-id="d3ed9-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="d3ed9-143">Estrutura de diretórios condensados</span><span class="sxs-lookup"><span data-stu-id="d3ed9-143">Condensed directory structure</span></span>

- <span data-ttu-id="d3ed9-144">Pasta raiz - Essa pasta é denominada ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="d3ed9-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="d3ed9-145">Export_load_file.csv - Arquivo de metadados.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="d3ed9-146">Summary.txt - Um arquivo de resumo que também contém estatísticas de exportação.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="d3ed9-147">Input_or_native_files - Essa pasta contém todos os arquivos nativos que foram exportados.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="d3ed9-148">Se você exportar arquivos PDF editados, eles não serão colocados em arquivos PST.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="d3ed9-149">Em vez disso, eles são adicionados a uma pasta separada.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="d3ed9-150">Error_files - Esta pasta contém os seguintes arquivos de erro, se eles estão incluídos na exportação:</span><span class="sxs-lookup"><span data-stu-id="d3ed9-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="d3ed9-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-151">ExtractionError.</span></span> <span data-ttu-id="d3ed9-152">Um arquivo CSV que contém todos os metadados disponíveis de arquivos que não foram extraídos corretamente dos arquivos pai.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="d3ed9-153">ProcessingError – Este arquivo contém uma lista de documentos com erros de processamento.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="d3ed9-154">Esse conteúdo é de nível de item, ou seja, se um anexo resultou em um erro de processamento, a mensagem de email que contém o anexo será incluída nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="d3ed9-155">Extracted_text_files - Essa pasta contém todos os arquivos de texto extraídos que foram gerados no processamento.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="d3ed9-156">Os trabalhos de exportação são mantidos durante a vida útil do caso e podem ser baixados, desde que o caso não seja excluído.</span><span class="sxs-lookup"><span data-stu-id="d3ed9-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
