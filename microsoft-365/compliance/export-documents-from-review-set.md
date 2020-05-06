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
description: Saiba como selecionar e exportar ou baixar o conteúdo de um conjunto de revisão para apresentações ou revisões externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 29c2224a1ce0a92bca3b2057352f6f82fdc7afde
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034089"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="fd694-103">Exportar documentos de um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="fd694-103">Export documents from a review set</span></span>

<span data-ttu-id="fd694-104">Você pode exportar conteúdo para apresentação ou revisão externa de uma análise definida por um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="fd694-104">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="fd694-105">Baixar documentos</span><span class="sxs-lookup"><span data-stu-id="fd694-105">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="fd694-106">Exportar documentos</span><span class="sxs-lookup"><span data-stu-id="fd694-106">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="fd694-107">Baixar documentos de um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="fd694-107">Download documents from a review set</span></span>

<span data-ttu-id="fd694-108">O download oferece uma maneira simples de baixar o conteúdo de uma revisão definida no formato nativo.</span><span class="sxs-lookup"><span data-stu-id="fd694-108">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="fd694-109">Ele aproveita os recursos de transferência de dados do navegador para que um prompt do navegador seja exibido quando um download estiver pronto.</span><span class="sxs-lookup"><span data-stu-id="fd694-109">It leverages the browser's data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="fd694-110">Arquivos baixados usando este método serão zipados em um arquivo de contêiner e serão arquivos de nível de item.</span><span class="sxs-lookup"><span data-stu-id="fd694-110">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="fd694-111">Isso significa que, se você selecionar um anexo, receberá automaticamente o email com o anexo incluído.</span><span class="sxs-lookup"><span data-stu-id="fd694-111">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="fd694-112">Da mesma forma, se você selecionar uma planilha do Excel incorporada em um documento do Word, receberá o documento do Word com a planilha do Excel incorporada.</span><span class="sxs-lookup"><span data-stu-id="fd694-112">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="fd694-113">Os itens baixados preservarão a data da última modificação que pode ser exibida como uma propriedade de arquivo.</span><span class="sxs-lookup"><span data-stu-id="fd694-113">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="fd694-114">Para baixar o conteúdo de um conjunto de revisão, comece selecionando os arquivos que você deseja baixar e, em seguida, selecione "download" no menu ações.</span><span class="sxs-lookup"><span data-stu-id="fd694-114">To download content from a review set, start by selecting the files you want to download then select "Download" under the Actions menu.</span></span>

![Captura de tela de uma descrição de computador gerada automaticamente](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="fd694-116">Exportar documentos de um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="fd694-116">Export documents from a review set</span></span>

<span data-ttu-id="fd694-117">Exportar permite que os usuários personalizem o conteúdo que está incluído no pacote de download.</span><span class="sxs-lookup"><span data-stu-id="fd694-117">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="fd694-118">Ele fornece uma página de configuração com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fd694-118">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="fd694-119">Arquivo de metadados</span><span class="sxs-lookup"><span data-stu-id="fd694-119">Metadata file</span></span>

<span data-ttu-id="fd694-120">Isso pode ser considerado o "carregar arquivo" que contém metadados associados aos arquivos exportados.</span><span class="sxs-lookup"><span data-stu-id="fd694-120">This can be considered your "load file" that contains metadata associated with the files you export.</span></span> <span data-ttu-id="fd694-121">Para obter uma lista de campos exportados disponíveis no arquivo de metadados, confira [campos de metadados de documentos na descoberta eletrônica avançada](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="fd694-121">For a list of exported fields available in the metadata file, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="fd694-122">Normalmente, esse arquivo pode ser ingerido por ferramentas de terceiros.</span><span class="sxs-lookup"><span data-stu-id="fd694-122">This file can typically be ingested by third-party tools.</span></span>

### <a name="tag-data"></a><span data-ttu-id="fd694-123">Dados de marca</span><span class="sxs-lookup"><span data-stu-id="fd694-123">Tag data</span></span>

<span data-ttu-id="fd694-124">Esse conteúdo seria adicionado como campos no arquivo de metadados.</span><span class="sxs-lookup"><span data-stu-id="fd694-124">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="fd694-125">Ele contém todas as informações de marca aplicadas nos conjuntos de revisão.</span><span class="sxs-lookup"><span data-stu-id="fd694-125">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="fd694-126">Arquivos de texto</span><span class="sxs-lookup"><span data-stu-id="fd694-126">Text files</span></span>

<span data-ttu-id="fd694-127">Arquivos de texto podem ser gerados para cada arquivo exportado de um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="fd694-127">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="fd694-128">Muitas vezes, esses arquivos são necessários para parceiros de serviço como parte da inclusão de dados em ferramentas de terceiros.</span><span class="sxs-lookup"><span data-stu-id="fd694-128">Often times these files are required by service partners as part of ingesting data into third-party tools.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="fd694-129">Arquivos reredigidos</span><span class="sxs-lookup"><span data-stu-id="fd694-129">Redacted files</span></span>

<span data-ttu-id="fd694-130">Se arquivos PDF redigidos forem gerados durante a revisão, esses arquivos estarão disponíveis durante a exportação.</span><span class="sxs-lookup"><span data-stu-id="fd694-130">If redacted PDF files are generated during review, these files are available during export.</span></span> <span data-ttu-id="fd694-131">Você pode decidir se deseja exportar somente arquivos nativos ou substituir os arquivos nativos que requeram a redação com os arquivos PDF que contêm as redaçãos reais.</span><span class="sxs-lookup"><span data-stu-id="fd694-131">You can decide whether to export native files only or to replace the native files that required redaction with the PDF files that contain the actual redactions.</span></span>

### <a name="export-location"></a><span data-ttu-id="fd694-132">Local de exportação</span><span class="sxs-lookup"><span data-stu-id="fd694-132">Export location</span></span>

<span data-ttu-id="fd694-133">O conteúdo exportado é entregue a um blob do Azure fornecido pela Microsoft ou o blob de um cliente pode ser usado se os detalhes forem fornecidos na exportação.</span><span class="sxs-lookup"><span data-stu-id="fd694-133">Exported content is delivered to either a Microsoft provided Azure blob or a customer's blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="fd694-134">Exportar estrutura</span><span class="sxs-lookup"><span data-stu-id="fd694-134">Export structure</span></span>

<span data-ttu-id="fd694-135">Quando o conteúdo é exportado de um conjunto de revisão, o conteúdo é organizado na estrutura a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd694-135">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="fd694-136">Pasta raiz – ID de download</span><span class="sxs-lookup"><span data-stu-id="fd694-136">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="fd694-137">Exportar\_arquivo\_de carregamento. csv = arquivo de metadados</span><span class="sxs-lookup"><span data-stu-id="fd694-137">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="fd694-138">Summary. txt = um arquivo de resumo com estatísticas de exportação</span><span class="sxs-lookup"><span data-stu-id="fd694-138">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="fd694-139">Entrada\_ou arquivos\_nativos = contém todos os arquivos nativos</span><span class="sxs-lookup"><span data-stu-id="fd694-139">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="fd694-140">Arquivos\_de erro = contém qualquer arquivo de erro incluído na exportação</span><span class="sxs-lookup"><span data-stu-id="fd694-140">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="fd694-141">ExtractionError – um CSV que contém metadados disponíveis de arquivos que não foram extraídos corretamente de arquivos pai</span><span class="sxs-lookup"><span data-stu-id="fd694-141">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="fd694-142">ProcessingError – conteúdo com erros de processamento.</span><span class="sxs-lookup"><span data-stu-id="fd694-142">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="fd694-143">Esse conteúdo é o nível do item se um anexo sofreu um erro de processamento, o email que contém o anexo será incluído nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="fd694-143">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="fd694-144">Arquivos\_de\_texto extraídos = contém todos os arquivos de texto extraídos gerados no processamento.</span><span class="sxs-lookup"><span data-stu-id="fd694-144">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>
