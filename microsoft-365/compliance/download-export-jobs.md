---
title: Baixar trabalhos de exportação para um caso de Descoberta Descoberta Avançada
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Instale e use o Azure Storage Explorer para baixar documentos que foram exportados de um conjunto de revisão no Advanced eDiscovery.
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751288"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="96f64-103">Baixar trabalhos de exportação em um caso de Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="96f64-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="96f64-104">Quando você exporta documentos de um conjunto de revisão em um caso de Descoberta Avançada, os documentos são carregados para um local de Armazenamento do Azure fornecido pela Microsoft ou para um local de Armazenamento do Azure gerenciado pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="96f64-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="96f64-105">O tipo de local de armazenamento do Azure usado depende de qual opção foi selecionada quando os documentos foram exportados.</span><span class="sxs-lookup"><span data-stu-id="96f64-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="96f64-106">Este artigo fornece instruções sobre como usar o Microsoft Azure Storage Explorer para se conectar a um local de armazenamento do Azure para procurar e baixar os documentos exportados.</span><span class="sxs-lookup"><span data-stu-id="96f64-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="96f64-107">Para obter mais informações sobre o Azure Storage Explorer, consulte [Guia de início rápido: Use o Azure Storage Explorer.](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="96f64-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="96f64-108">Etapa 1: Instalar o Azure Storage Explorer</span><span class="sxs-lookup"><span data-stu-id="96f64-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="96f64-109">A primeira etapa é baixar e instalar o Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="96f64-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="96f64-110">Para obter instruções, confira [a ferramenta Do Azure Storage Explorer.](https://go.microsoft.com/fwlink/p/?LinkId=544842)</span><span class="sxs-lookup"><span data-stu-id="96f64-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="96f64-111">Use essa ferramenta para se conectar e baixar os documentos exportados na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="96f64-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="96f64-112">Etapa 2: Obter a URL SAS do trabalho de exportação</span><span class="sxs-lookup"><span data-stu-id="96f64-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="96f64-113">A próxima etapa é obter a URL de assinatura de acesso compartilhado (SAS) gerada quando você criou o trabalho de exportação para exportar documentos de um conjunto [de revisão.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="96f64-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="96f64-114">Você pode copiar a URL do SAS para documentos carregados em um local de Armazenamento do Azure fornecido pela Microsoft ou em um local de Armazenamento do Azure gerenciado pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="96f64-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="96f64-115">Em ambos os casos, use a URL SAS para se conectar ao local de armazenamento do Azure na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="96f64-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="96f64-116">Na página **Descobertas Avançadas,** vá para a ocorrência e clique na **guia** Exportações.</span><span class="sxs-lookup"><span data-stu-id="96f64-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="96f64-117">Na guia **Exportações,** clique no trabalho de exportação que você deseja baixar.</span><span class="sxs-lookup"><span data-stu-id="96f64-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="96f64-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span><span class="sxs-lookup"><span data-stu-id="96f64-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="96f64-119">Se necessário, você pode salvá-lo em um arquivo para poder acessá-lo na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="96f64-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![Copiar a URL SAS exibida em Locais](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="96f64-121">Etapa 3: Conectar-se ao local de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="96f64-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="96f64-122">A etapa final é usar o Explorador de Armazenamento do Azure e a URL SAS para se conectar ao local de armazenamento do Azure e baixar os documentos que você exportou para um computador local.</span><span class="sxs-lookup"><span data-stu-id="96f64-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="96f64-123">Abra o Azure Storage Explorer que você instalou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="96f64-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="96f64-124">Clique no **ícone Adicionar** conta.</span><span class="sxs-lookup"><span data-stu-id="96f64-124">Click the **Add account** icon.</span></span> <span data-ttu-id="96f64-125">Como alternativa, você pode clicar com o botão direito do mouse **em Contas de Armazenamento.**</span><span class="sxs-lookup"><span data-stu-id="96f64-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![Clique no ícone Adicionar conta](../media/AzureStorageConnect.png)

3. <span data-ttu-id="96f64-127">Na página **Conectar-se ao Armazenamento do Azure,** clique em Usar um URI de assinatura de acesso **compartilhado (SAS)** e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="96f64-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![Clique em Usar um URI de assinatura de acesso compartilhado (SAS) e clique em Próximo](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="96f64-129">Na página **Anexar com URI SAS,** clique na caixa URI e, em seguida, colar a URL SAS obtida na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="96f64-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![Colar a URL SAS na caixa URI](../media/AzureStorageConnect3.png)

    <span data-ttu-id="96f64-131">Observe que uma parte da URL SAS é exibida na caixa **Nome de** exibição.</span><span class="sxs-lookup"><span data-stu-id="96f64-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="96f64-132">Isso será usado como o nome de exibição do contêiner criado sob as contas **de** Armazenamento depois que você se conectar ao local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="96f64-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="96f64-133">Esse nome consiste na ID da ocorrência da Descoberta Avançada e em um identificador exclusivo.</span><span class="sxs-lookup"><span data-stu-id="96f64-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="96f64-134">Você pode manter o nome de exibição padrão ou alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="96f64-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="96f64-135">Se você alterá-lo, o nome de exibição deverá ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="96f64-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="96f64-136">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="96f64-136">Click **Next**.</span></span>

    <span data-ttu-id="96f64-137">A **página de resumo** de conexão é exibida.</span><span class="sxs-lookup"><span data-stu-id="96f64-137">The **Connection summary** page is displayed.</span></span>

    ![Clique em Conectar na página de resumo de conexão para se conectar ao local de armazenamento do Azure](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="96f64-139">Na página **Resumo da** conexão, revise as informações de conexão e clique em **Conectar.**</span><span class="sxs-lookup"><span data-stu-id="96f64-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="96f64-140">O **nó de contêineres de Blob** (em **Contas de Armazenamento**  >  **(Contêineres Anexados)** \> é aberto.</span><span class="sxs-lookup"><span data-stu-id="96f64-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Exportar trabalhos no nó de contêineres de Blobs](../media/AzureStorageConnect5.png)

    <span data-ttu-id="96f64-142">Ele contém um contêiner nomeado com o nome de exibição da etapa 4.</span><span class="sxs-lookup"><span data-stu-id="96f64-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="96f64-143">Esse contêiner contém uma pasta para cada trabalho de exportação que você criou.</span><span class="sxs-lookup"><span data-stu-id="96f64-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="96f64-144">Essas pastas são nomeadas com uma ID que corresponde à ID do trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="96f64-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="96f64-145">Você pode encontrar essas IDs de exportação (e o nome da exportação) em Informações de suporte na página do sub80 para cada preparação de dados para o trabalho de exportação listado na guia **Trabalhos.**  </span><span class="sxs-lookup"><span data-stu-id="96f64-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="96f64-146">Clique duas vezes na pasta de trabalho de exportação para abri-la.</span><span class="sxs-lookup"><span data-stu-id="96f64-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="96f64-147">Uma lista de pastas e relatórios de exportação é exibida.</span><span class="sxs-lookup"><span data-stu-id="96f64-147">A list of folders and export reports is displayed.</span></span>
   
    ![A pasta de exportação contém arquivos exportados e relatórios de exportação](../media/AzureStorageConnect6.png)

   <span data-ttu-id="96f64-149">A pasta de trabalho de exportação contém os itens a seguir.</span><span class="sxs-lookup"><span data-stu-id="96f64-149">The export job folder contains the following items.</span></span> <span data-ttu-id="96f64-150">Os itens reais na pasta de exportação são determinados pelas opções de exportação configuradas quando o trabalho de exportação foi criado.</span><span class="sxs-lookup"><span data-stu-id="96f64-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="96f64-151">Para obter mais informações, [consulte Exportar documentos de um conjunto de revisão.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="96f64-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="96f64-152">Export_load_file.csv: esse arquivo CSV é um relatório de exportação detalhado que contém informações sobre cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="96f64-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="96f64-153">O arquivo consiste em uma coluna para cada propriedade de metadados de um documento.</span><span class="sxs-lookup"><span data-stu-id="96f64-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="96f64-154">Para uma lista e uma descrição dos metadados  incluídos neste relatório, consulte a coluna Nome do campo exportado na tabela nos campos de metadados do documento na [Descoberta eDiscovery Avançada.](document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="96f64-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="96f64-155">Summary.txt: um arquivo de texto que contém um resumo da exportação, incluindo estatísticas de exportação.</span><span class="sxs-lookup"><span data-stu-id="96f64-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="96f64-156">Extracted_text_files: essa pasta contém uma versão de arquivo de texto de cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="96f64-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="96f64-157">NativeFiles: essa pasta contém uma versão de arquivo nativa de cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="96f64-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="96f64-158">Error_files: essa pasta inclui os seguintes itens quando o trabalho de exportação contém arquivos de erro:</span><span class="sxs-lookup"><span data-stu-id="96f64-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="96f64-159">ExtractionError.csv: esse arquivo CSV contém os metadados disponíveis para arquivos que não foram extraídos corretamente do item pai.</span><span class="sxs-lookup"><span data-stu-id="96f64-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="96f64-160">ProcessingError: Esta pasta contém documentos com erros de processamento.</span><span class="sxs-lookup"><span data-stu-id="96f64-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="96f64-161">Esse conteúdo está em um nível de item, o que significa que se um anexo tiver um erro de processamento, o documento que contém o anexo também será incluído nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="96f64-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="96f64-162">Para exportar todo o conteúdo na exportação, selecione a pasta de exportação e clique em **Baixar.**</span><span class="sxs-lookup"><span data-stu-id="96f64-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="96f64-163">Especifique o local onde você deseja baixar os arquivos exportados e clique em Selecionar pasta.</span><span class="sxs-lookup"><span data-stu-id="96f64-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="96f64-164">O Explorador de Armazenamento do Azure inicia o processo de exportação.</span><span class="sxs-lookup"><span data-stu-id="96f64-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="96f64-165">O status do download dos itens exportados é exibido no **painel** Atividades.</span><span class="sxs-lookup"><span data-stu-id="96f64-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="96f64-166">Uma mensagem é exibida quando o download é concluído.</span><span class="sxs-lookup"><span data-stu-id="96f64-166">A message is displayed when the download is finished.</span></span>

    ![Uma mensagem é exibida quando o download é concluído](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="96f64-168">Em vez de baixar todo o trabalho de exportação, você pode selecionar itens específicos para baixar.</span><span class="sxs-lookup"><span data-stu-id="96f64-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="96f64-169">E, em vez de baixar itens, você pode clicar duas vezes em um item para exibi-lo.</span><span class="sxs-lookup"><span data-stu-id="96f64-169">And instead of downloading items, you can double-click an item to view it.</span></span>
