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
description: ''
ms.openlocfilehash: 0448082ce6dcbcd9d1cee52557a78b2d7913a034
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41588351"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="45d20-102">Exportar documentos de um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="45d20-102">Export documents from a review set</span></span>

<span data-ttu-id="45d20-103">Você pode exportar conteúdo para apresentação ou revisão externa de uma análise definida por um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="45d20-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="45d20-104">Baixar documentos</span><span class="sxs-lookup"><span data-stu-id="45d20-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="45d20-105">Exportar documentos</span><span class="sxs-lookup"><span data-stu-id="45d20-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="45d20-106">Baixar documentos de um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="45d20-106">Download documents from a review set</span></span>

<span data-ttu-id="45d20-107">O download oferece uma maneira simples de baixar o conteúdo de uma revisão definida no formato nativo.</span><span class="sxs-lookup"><span data-stu-id="45d20-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="45d20-108">Ele aproveita os recursos de transferência de dados do navegador para que um prompt do navegador seja exibido quando um download estiver pronto.</span><span class="sxs-lookup"><span data-stu-id="45d20-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="45d20-109">Arquivos baixados usando este método serão zipados em um arquivo de contêiner e serão arquivos de nível de item.</span><span class="sxs-lookup"><span data-stu-id="45d20-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="45d20-110">Isso significa que, se você selecionar um anexo, receberá automaticamente o email com o anexo incluído.</span><span class="sxs-lookup"><span data-stu-id="45d20-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="45d20-111">Da mesma forma, se você selecionar uma planilha do Excel incorporada em um documento do Word, receberá o documento do Word com a planilha do Excel incorporada.</span><span class="sxs-lookup"><span data-stu-id="45d20-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="45d20-112">Os itens baixados preservarão a data da última modificação que pode ser exibida como uma propriedade de arquivo.</span><span class="sxs-lookup"><span data-stu-id="45d20-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="45d20-113">Para baixar o conteúdo de um conjunto de revisão, comece selecionando os arquivos que você deseja baixar e, em seguida, selecione "download" no menu ações.</span><span class="sxs-lookup"><span data-stu-id="45d20-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![Captura de tela de uma descrição de computador gerada automaticamente](media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="45d20-115">Exportar documentos de um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="45d20-115">Export documents from a review set</span></span>

<span data-ttu-id="45d20-116">Exportar permite que os usuários personalizem o conteúdo que está incluído no pacote de download.</span><span class="sxs-lookup"><span data-stu-id="45d20-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="45d20-117">Ele fornece uma página de configuração com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="45d20-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="45d20-118">Arquivo de metadados</span><span class="sxs-lookup"><span data-stu-id="45d20-118">Metadata file</span></span>

<span data-ttu-id="45d20-119">Isso pode ser considerado o "carregar arquivo" que contém metadados associados aos arquivos exportados.</span><span class="sxs-lookup"><span data-stu-id="45d20-119">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="45d20-120">Para obter uma lista de campos disponíveis no arquivo de metadados, \[consulte\]link.</span><span class="sxs-lookup"><span data-stu-id="45d20-120">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="45d20-121">Normalmente, esse arquivo pode ser ingerido<sup>por três ferramentas</sup> de terceiros para downstream.</span><span class="sxs-lookup"><span data-stu-id="45d20-121">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="45d20-122">Dados de marca</span><span class="sxs-lookup"><span data-stu-id="45d20-122">Tag data</span></span>

<span data-ttu-id="45d20-123">Esse conteúdo seria adicionado como campos no arquivo de metadados.</span><span class="sxs-lookup"><span data-stu-id="45d20-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="45d20-124">Ele contém todas as informações de marca aplicadas nos conjuntos de revisão.</span><span class="sxs-lookup"><span data-stu-id="45d20-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="45d20-125">Arquivos de texto</span><span class="sxs-lookup"><span data-stu-id="45d20-125">Text files</span></span>

<span data-ttu-id="45d20-126">Arquivos de texto podem ser gerados para cada arquivo exportado de um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="45d20-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="45d20-127">Muitas vezes, esses arquivos são necessários para parceiros de serviço como parte da inclusão de dados em uma área de 3<sup>RD</sup> ferramentas de terceiros.</span><span class="sxs-lookup"><span data-stu-id="45d20-127">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="45d20-128">Arquivos reredigidos</span><span class="sxs-lookup"><span data-stu-id="45d20-128">Redacted files</span></span>

<span data-ttu-id="45d20-129">Se PDFs redigidos forem gerados durante a revisão, esses arquivos estarão disponíveis durante a exportação.</span><span class="sxs-lookup"><span data-stu-id="45d20-129">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="45d20-130">Os usuários podem decidir se serão exportados apenas arquivos nativos ou para substituir os nativos que têm redaçãos com o gravado em PDFs.</span><span class="sxs-lookup"><span data-stu-id="45d20-130">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="45d20-131">Local de exportação</span><span class="sxs-lookup"><span data-stu-id="45d20-131">Export Location</span></span>

<span data-ttu-id="45d20-132">O conteúdo exportado é entregue a um blob do Azure fornecido pela Microsoft ou o blob de um cliente pode ser usado se os detalhes forem fornecidos na exportação.</span><span class="sxs-lookup"><span data-stu-id="45d20-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="45d20-133">Exportar estrutura</span><span class="sxs-lookup"><span data-stu-id="45d20-133">Export Structure</span></span>

<span data-ttu-id="45d20-134">Quando o conteúdo é exportado de um conjunto de revisão, o conteúdo é organizado na estrutura a seguir.</span><span class="sxs-lookup"><span data-stu-id="45d20-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="45d20-135">Pasta raiz – ID de download</span><span class="sxs-lookup"><span data-stu-id="45d20-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="45d20-136">Exportar\_arquivo\_de carregamento. csv = arquivo de metadados</span><span class="sxs-lookup"><span data-stu-id="45d20-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="45d20-137">Summary. txt = um arquivo de resumo com estatísticas de exportação</span><span class="sxs-lookup"><span data-stu-id="45d20-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="45d20-138">Entrada\_ou arquivos\_nativos = contém todos os arquivos nativos</span><span class="sxs-lookup"><span data-stu-id="45d20-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="45d20-139">Arquivos\_de erro = contém qualquer arquivo de erro incluído na exportação</span><span class="sxs-lookup"><span data-stu-id="45d20-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="45d20-140">ExtractionError – um CSV que contém metadados disponíveis de arquivos que não foram extraídos corretamente de arquivos pai</span><span class="sxs-lookup"><span data-stu-id="45d20-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="45d20-141">ProcessingError – conteúdo com erros de processamento.</span><span class="sxs-lookup"><span data-stu-id="45d20-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="45d20-142">Esse conteúdo é o nível do item se um anexo sofreu um erro de processamento, o email que contém o anexo será incluído nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="45d20-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="45d20-143">Arquivos\_de\_texto extraídos = contém todos os arquivos de texto extraídos gerados no processamento.</span><span class="sxs-lookup"><span data-stu-id="45d20-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>