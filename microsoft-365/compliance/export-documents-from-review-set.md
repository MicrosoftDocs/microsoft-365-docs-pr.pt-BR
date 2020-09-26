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
description: Saiba como selecionar e exportar o conteúdo de um conjunto de revisão para apresentações ou revisões externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285357"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="72f8d-103">Exportar documentos de um conjunto de revisão na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="72f8d-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="72f8d-104">Exportar permite que os usuários personalizem o conteúdo que está incluído no pacote de download.</span><span class="sxs-lookup"><span data-stu-id="72f8d-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="72f8d-105">A ferramenta de exportação fornece uma página de configuração com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="72f8d-105">The Export tool provides a configuration page with the following settings:</span></span>

![Opções para exportar itens de um conjunto de revisão](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="72f8d-107">Opções de exportação</span><span class="sxs-lookup"><span data-stu-id="72f8d-107">Export options</span></span>

- <span data-ttu-id="72f8d-108">Nome para exportação: o nome do trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="72f8d-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="72f8d-109">Descrição: campo de texto livre para que você adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="72f8d-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="72f8d-110">Exportar estes documentos:</span><span class="sxs-lookup"><span data-stu-id="72f8d-110">Export these documents:</span></span>

  - <span data-ttu-id="72f8d-111">Somente documentos selecionados-exporta somente os documentos que estão atualmente selecionados.</span><span class="sxs-lookup"><span data-stu-id="72f8d-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="72f8d-112">Todos os documentos no conjunto de revisão-exporta todos os documentos no conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="72f8d-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="72f8d-113">Metadata</span><span class="sxs-lookup"><span data-stu-id="72f8d-113">Metadata</span></span>
  
  - <span data-ttu-id="72f8d-114">Carregar arquivo-esse arquivo contém metadados para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="72f8d-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="72f8d-115">Confira [campos de metadados de documentos na descoberta eletrônica avançada](document-metadata-fields-in-Advanced-eDiscovery.md) para obter mais informações sobre quais campos estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="72f8d-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="72f8d-116">Normalmente, esse arquivo pode ser ingerido por ferramentas de descoberta eletrônica de terceiros.</span><span class="sxs-lookup"><span data-stu-id="72f8d-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="72f8d-117">Marcas-quando selecionadas, as informações de marcação serão incluídas no arquivo de carregamento.</span><span class="sxs-lookup"><span data-stu-id="72f8d-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="72f8d-118">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="72f8d-118">Content</span></span>
  
  - <span data-ttu-id="72f8d-119">Arquivos nativos-Marque esta caixa de seleção para incluir os arquivos nativos.</span><span class="sxs-lookup"><span data-stu-id="72f8d-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="72f8d-120">Opções de conversa</span><span class="sxs-lookup"><span data-stu-id="72f8d-120">Conversation options</span></span>
    
    - <span data-ttu-id="72f8d-121">Arquivos de conversa-exportar mensagens de chat reconstruídas.</span><span class="sxs-lookup"><span data-stu-id="72f8d-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="72f8d-122">Este formato apresenta as conversas em um formulário que se assemelham ao que os usuários vêem no aplicativo nativo.</span><span class="sxs-lookup"><span data-stu-id="72f8d-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="72f8d-123">Mensagens de chat individuais-exporte os arquivos de conversa originais conforme eles são armazenados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72f8d-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="72f8d-124">Opções</span><span class="sxs-lookup"><span data-stu-id="72f8d-124">Options</span></span>

  - <span data-ttu-id="72f8d-125">Arquivos de texto: inclui versões de texto extraídas de arquivos nativos.</span><span class="sxs-lookup"><span data-stu-id="72f8d-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="72f8d-126">Substituir os nativos recriados por PDFs convertidos, se forem gerados arquivos PDF revisados durante a revisão, esses arquivos estarão disponíveis para exportação.</span><span class="sxs-lookup"><span data-stu-id="72f8d-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="72f8d-127">Você pode optar por exportar somente os arquivos nativos que foram redigidos (sem selecionar essa opção) ou pode selecionar essa opção para exportar os arquivos PDF que contêm as redaçãos reais.</span><span class="sxs-lookup"><span data-stu-id="72f8d-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="72f8d-128">As opções de saída (o conteúdo exportado estão disponíveis para download diretamente por meio de um navegador da Web ou podem ser enviadas para uma conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="72f8d-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="72f8d-129">As duas primeiras opções habilitam o download direto.)</span><span class="sxs-lookup"><span data-stu-id="72f8d-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="72f8d-130">Arquivos soltos e PSTs (email é adicionado a PSTs quando possível)-os arquivos são exportados em um formato semelhante à estrutura de diretório original vista pelos usuários em seus aplicativos nativos.</span><span class="sxs-lookup"><span data-stu-id="72f8d-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="72f8d-131">Para obter mais informações, consulte a seção [arquivos soltos e estrutura de exportação de PST](#loose-files-and-pst-export-structure) .</span><span class="sxs-lookup"><span data-stu-id="72f8d-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="72f8d-132">Estrutura de diretório condensada-os arquivos são exportados e incluídos no download.</span><span class="sxs-lookup"><span data-stu-id="72f8d-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="72f8d-133">Estrutura de diretório condensada exportada para sua conta de armazenamento do Azure-os arquivos são exportados para o repositório de armazenamento do Azure da sua organização accouunt.</span><span class="sxs-lookup"><span data-stu-id="72f8d-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="72f8d-134">Estrutura de exportação de arquivos soltos e de PST</span><span class="sxs-lookup"><span data-stu-id="72f8d-134">Loose files and PST export structure</span></span>

<span data-ttu-id="72f8d-135">Se você selecionar essa opção de exportação, o conteúdo exportado será organizado na seguinte estrutura:</span><span class="sxs-lookup"><span data-stu-id="72f8d-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="72f8d-136">Pasta raiz – esta pasta em nome ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="72f8d-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="72f8d-137">Arquivo de metadados Export_load_file.csv.</span><span class="sxs-lookup"><span data-stu-id="72f8d-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="72f8d-138">Summary.csv-um arquivo de resumo que também contém estatísticas de exportação.</span><span class="sxs-lookup"><span data-stu-id="72f8d-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="72f8d-139">Exchange-esta pasta contém todo o conteúdo do Exchange no formato de arquivo nativo.</span><span class="sxs-lookup"><span data-stu-id="72f8d-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="72f8d-140">Os arquivos nativos são substituídos por PDFs redigidos se você selecionou a opção **substituir nativos redigidos por PDFs convertidos** .</span><span class="sxs-lookup"><span data-stu-id="72f8d-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="72f8d-141">SharePoint = esta pasta contém todo o conteúdo nativo do SharePoint em um formato de arquivo nativo.</span><span class="sxs-lookup"><span data-stu-id="72f8d-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="72f8d-142">Os arquivos nativos são substituídos por PDFs redigidos se você selecionou a opção **substituir nativos redigidos por PDFs convertidos** .</span><span class="sxs-lookup"><span data-stu-id="72f8d-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="72f8d-143">Estrutura de diretório condensada</span><span class="sxs-lookup"><span data-stu-id="72f8d-143">Condensed directory structure</span></span>

- <span data-ttu-id="72f8d-144">Pasta raiz-esta pasta é nomeada ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="72f8d-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="72f8d-145">Arquivo de metadados Export_load_file.csv.</span><span class="sxs-lookup"><span data-stu-id="72f8d-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="72f8d-146">Summary.txt-um arquivo de resumo que também contém estatísticas de exportação.</span><span class="sxs-lookup"><span data-stu-id="72f8d-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="72f8d-147">Input_or_native_files-esta pasta contém todos os arquivos nativos que foram exportados.</span><span class="sxs-lookup"><span data-stu-id="72f8d-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="72f8d-148">Se você exportar arquivos PDF redigidos, eles não serão colocados em arquivos PST.</span><span class="sxs-lookup"><span data-stu-id="72f8d-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="72f8d-149">Em vez disso, eles são adicionados a uma pasta separada.</span><span class="sxs-lookup"><span data-stu-id="72f8d-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="72f8d-150">Error_files-esta pasta contém os seguintes arquivos de erro, se eles estiverem incluídos na exportação:</span><span class="sxs-lookup"><span data-stu-id="72f8d-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="72f8d-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="72f8d-151">ExtractionError.</span></span> <span data-ttu-id="72f8d-152">Um arquivo CSV que contém metadados disponíveis de arquivos que não foram extraídos corretamente de arquivos pai.</span><span class="sxs-lookup"><span data-stu-id="72f8d-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="72f8d-153">ProcessingError – este arquivo contém uma lista de documentos com erros de processamento.</span><span class="sxs-lookup"><span data-stu-id="72f8d-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="72f8d-154">Esse conteúdo é de nível de item, ou seja, se um anexo resultar em um erro de processamento, a mensagem de email que contém o anexo será incluída nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="72f8d-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="72f8d-155">Extracted_text_files-esta pasta contém todos os arquivos de texto extraídos que foram gerados no processamento.</span><span class="sxs-lookup"><span data-stu-id="72f8d-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="72f8d-156">Os trabalhos de exportação são mantidos durante a vida útil do caso e podem ser baixados, desde que o caso não seja excluído.</span><span class="sxs-lookup"><span data-stu-id="72f8d-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
