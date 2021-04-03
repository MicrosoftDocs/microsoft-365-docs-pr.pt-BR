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
description: Saiba como selecionar e exportar conteúdo de um conjunto de revisão de Descoberta Externa Avançada para apresentações ou avaliações externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581010"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="2a49d-103">Exportar documentos de um conjunto de revisão em Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="2a49d-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="2a49d-104">Exportar permite que os usuários personalizem o conteúdo incluído no pacote de download quando você exporta o documento de um conjunto de revisão em Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="2a49d-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="2a49d-105">Para exportar documentos de um conjunto de revisão:</span><span class="sxs-lookup"><span data-stu-id="2a49d-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="2a49d-106">No Centro de conformidade do Microsoft 365, abra o  caso Descoberta Avançada, selecione a guia Revisar conjuntos e selecione o conjunto de revisão que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="2a49d-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="2a49d-107">No conjunto de revisão, clique em **Ação**  >  **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="2a49d-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="2a49d-108">A ferramenta Exportar exibe a página de sobrevoo com as configurações para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="2a49d-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="2a49d-109">Algumas opções são selecionadas por padrão, mas você pode alterá-los.</span><span class="sxs-lookup"><span data-stu-id="2a49d-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="2a49d-110">Consulte a seção a seguir para ver descrições das opções de exportação que você pode configurar.</span><span class="sxs-lookup"><span data-stu-id="2a49d-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Opções de configuração para exportar itens de um conjunto de revisão](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="2a49d-112">Depois de configurar a exportação, clique em **Exportar** para iniciar o processo de exportação.</span><span class="sxs-lookup"><span data-stu-id="2a49d-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="2a49d-113">Dependendo da opção selecionada  na seção Opções de saída, você pode acessar os arquivos de exportação por download direto ou na conta de Armazenamento do Azure da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2a49d-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="2a49d-114">Os trabalhos de exportação são mantidos durante a vida útil do caso.</span><span class="sxs-lookup"><span data-stu-id="2a49d-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="2a49d-115">No entanto, você deve baixar o conteúdo de um trabalho de exportação dentro de 30 dias após a conclusão do trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="2a49d-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="2a49d-116">Opções de exportação</span><span class="sxs-lookup"><span data-stu-id="2a49d-116">Export options</span></span>

<span data-ttu-id="2a49d-117">Use as opções a seguir para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="2a49d-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="2a49d-118">**Nome da** exportação : nome do trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="2a49d-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="2a49d-119">**Descrição**: campo de texto livre para você adicionar uma descrição.</span><span class="sxs-lookup"><span data-stu-id="2a49d-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="2a49d-120">**Exportar esses documentos**</span><span class="sxs-lookup"><span data-stu-id="2a49d-120">**Export these documents**</span></span>

  - <span data-ttu-id="2a49d-121">**Somente documentos selecionados:** essa opção exporta apenas os documentos selecionados no momento.</span><span class="sxs-lookup"><span data-stu-id="2a49d-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="2a49d-122">**Todos os documentos no conjunto de revisão**: Essa opção exporta todos os documentos no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="2a49d-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="2a49d-123">**Metadados**</span><span class="sxs-lookup"><span data-stu-id="2a49d-123">**Metadata**</span></span>
  
  - <span data-ttu-id="2a49d-124">**Arquivo de carga**: este arquivo contém metadados para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="2a49d-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="2a49d-125">Normalmente, esse arquivo pode ser ingerido por ferramentas de Descoberta eDiscovery de terceiros.</span><span class="sxs-lookup"><span data-stu-id="2a49d-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="2a49d-126">Para obter mais informações sobre quais campos estão incluídos, consulte [Campos de metadados de documento em Descoberta Avançada de eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="2a49d-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="2a49d-127">**Marcas**: Quando selecionada, as informações de marcação são incluídas no arquivo de carga.</span><span class="sxs-lookup"><span data-stu-id="2a49d-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="2a49d-128">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="2a49d-128">**Content**</span></span>
  
  - <span data-ttu-id="2a49d-129">**Arquivos nativos**: selecione essa caixa de seleção para incluir os arquivos nativos dos documentos no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="2a49d-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="2a49d-130">Se você optar por exportar arquivos nativos, terá as seguintes opções para exportar conversas de chat.</span><span class="sxs-lookup"><span data-stu-id="2a49d-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="2a49d-131">**Opções de conversa**</span><span class="sxs-lookup"><span data-stu-id="2a49d-131">**Conversation options**</span></span>

    - <span data-ttu-id="2a49d-132">**Arquivos de conversa**: essa opção exporta conversas de chat reconstruídas.</span><span class="sxs-lookup"><span data-stu-id="2a49d-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="2a49d-133">Esse formato apresenta conversas em um formulário que se parece com o que os usuários veem no aplicativo nativo.</span><span class="sxs-lookup"><span data-stu-id="2a49d-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="2a49d-134">**Mensagens de chat individuais**: essa opção exporta os arquivos de conversa originais à medida que são armazenados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a49d-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="2a49d-135">**Opções**</span><span class="sxs-lookup"><span data-stu-id="2a49d-135">**Options**</span></span>

  - <span data-ttu-id="2a49d-136">**Arquivos de** texto : - Essa opção inclui as versões de texto extraídas de arquivos nativos na exportação.</span><span class="sxs-lookup"><span data-stu-id="2a49d-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="2a49d-137">**Substitua os nativos redacted por PDFs convertidos**: se os arquivos PDF redacted são gerados durante a revisão, esses arquivos estão disponíveis para exportação.</span><span class="sxs-lookup"><span data-stu-id="2a49d-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="2a49d-138">Você pode optar por exportar apenas os arquivos nativos que foram editados (não selecionando essa opção) ou pode selecionar essa opção para exportar os arquivos PDF que contêm as redação reais.</span><span class="sxs-lookup"><span data-stu-id="2a49d-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="2a49d-139">**Opções de** saída : O conteúdo exportado está disponível para download diretamente por meio de um navegador da Web ou pode ser enviado para uma conta de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="2a49d-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="2a49d-140">As duas primeiras opções habilitam o download direto.</span><span class="sxs-lookup"><span data-stu-id="2a49d-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="2a49d-141">**Arquivos soltos e PSTs (o email** é adicionado a PSTs quando possível) : Os arquivos são exportados em um formato que se parece com a estrutura de diretório original vista pelos usuários em seus aplicativos nativos.</span><span class="sxs-lookup"><span data-stu-id="2a49d-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="2a49d-142">Para obter mais informações, consulte a seção Arquivos Soltos e estrutura de [exportação PST.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="2a49d-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="2a49d-143">**Estrutura de diretório condensado**: Os arquivos são exportados e incluídos no download.</span><span class="sxs-lookup"><span data-stu-id="2a49d-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="2a49d-144">**Estrutura de diretório condensada exportada para** sua conta de Armazenamento do Azure : Os arquivos são exportados para a conta de Armazenamento do Azure da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2a49d-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="2a49d-145">Para essa opção, você precisa fornecer a URL do contêiner em sua conta de Armazenamento do Azure para exportar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="2a49d-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="2a49d-146">Você também precisa fornecer o token de assinatura de acesso compartilhado (SAS) para sua conta de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="2a49d-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="2a49d-147">Para obter mais informações, [consulte Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="2a49d-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="2a49d-148">As seções a seguir descrevem a estrutura de pastas para arquivos soltos e opções de estrutura de diretório condensada.</span><span class="sxs-lookup"><span data-stu-id="2a49d-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="2a49d-149">Arquivos soltos e estrutura de exportação PST</span><span class="sxs-lookup"><span data-stu-id="2a49d-149">Loose files and PST export structure</span></span>

<span data-ttu-id="2a49d-150">Se você selecionar essa opção de exportação, o conteúdo exportado será organizado na seguinte estrutura:</span><span class="sxs-lookup"><span data-stu-id="2a49d-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="2a49d-151">Pasta raiz: esta pasta no nome ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="2a49d-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="2a49d-152">Export_load_file.csv: o arquivo de metadados.</span><span class="sxs-lookup"><span data-stu-id="2a49d-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="2a49d-153">Summary.csv: um arquivo de resumo que também contém estatísticas de exportação.</span><span class="sxs-lookup"><span data-stu-id="2a49d-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="2a49d-154">Exchange: essa pasta contém todo o conteúdo do Exchange no formato de arquivo nativo.</span><span class="sxs-lookup"><span data-stu-id="2a49d-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="2a49d-155">Os arquivos nativos serão substituídos por PDFs redacionados se você tiver selecionado a opção Substituir nativos **redacted por PDFs convertidos.**</span><span class="sxs-lookup"><span data-stu-id="2a49d-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="2a49d-156">SharePoint: essa pasta contém todo o conteúdo nativo do SharePoint em um formato de arquivo nativo.</span><span class="sxs-lookup"><span data-stu-id="2a49d-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="2a49d-157">Os arquivos nativos serão substituídos por PDFs redacionados se você tiver selecionado a opção Substituir nativos **redacted por PDFs convertidos.**</span><span class="sxs-lookup"><span data-stu-id="2a49d-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="2a49d-158">Estrutura de diretório condensado</span><span class="sxs-lookup"><span data-stu-id="2a49d-158">Condensed directory structure</span></span>

- <span data-ttu-id="2a49d-159">Pasta raiz: essa pasta é chamada ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="2a49d-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="2a49d-160">Export_load_file.csv: o arquivo de metadados.</span><span class="sxs-lookup"><span data-stu-id="2a49d-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="2a49d-161">Summary.txt: um arquivo de resumo que também contém estatísticas de exportação.</span><span class="sxs-lookup"><span data-stu-id="2a49d-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="2a49d-162">NativeFiles: esta pasta contém todos os arquivos nativos que foram exportados.</span><span class="sxs-lookup"><span data-stu-id="2a49d-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="2a49d-163">Se você exportar arquivos PDF editados, eles não serão colocados em arquivos PST.</span><span class="sxs-lookup"><span data-stu-id="2a49d-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="2a49d-164">Em vez disso, eles são adicionados a uma pasta separada.</span><span class="sxs-lookup"><span data-stu-id="2a49d-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="2a49d-165">Error_files: esta pasta contém os seguintes arquivos de erro, se eles são incluídos na exportação:</span><span class="sxs-lookup"><span data-stu-id="2a49d-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="2a49d-166">ExtractionError: um arquivo CSV que contém todos os metadados disponíveis de arquivos que não foram extraídos corretamente dos arquivos pai.</span><span class="sxs-lookup"><span data-stu-id="2a49d-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="2a49d-167">ProcessingError: este arquivo contém uma lista de documentos com erros de processamento.</span><span class="sxs-lookup"><span data-stu-id="2a49d-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="2a49d-168">Esse conteúdo é de nível de item, ou seja, se um anexo resultou em um erro de processamento, a mensagem de email que contém o anexo será incluída nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="2a49d-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="2a49d-169">Extracted_text_files: esta pasta contém todos os arquivos de texto extraídos que foram gerados no processamento.</span><span class="sxs-lookup"><span data-stu-id="2a49d-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
