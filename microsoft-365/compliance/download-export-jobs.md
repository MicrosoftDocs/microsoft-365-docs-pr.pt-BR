---
title: Baixar trabalhos de exportação
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
description: Instale e use o Azure Storage Explorer para baixar documentos que foram exportados de uma análise definida na descoberta eletrônica avançada.
ms.openlocfilehash: 640dd9b6d5768a22cb6529f476e4003c5eeb4d86
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074836"
---
# <a name="download-export-jobs"></a><span data-ttu-id="716a4-103">Baixar trabalhos de exportação</span><span class="sxs-lookup"><span data-stu-id="716a4-103">Download export jobs</span></span>

<span data-ttu-id="716a4-104">Quando você exporta documentos de um conjunto de revisão em um caso de descoberta eletrônica avançada, os documentos são carregados em um local de armazenamento do Azure fornecido pela Microsoft ou em um local de armazenamento do Azure gerenciado por sua organização.</span><span class="sxs-lookup"><span data-stu-id="716a4-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="716a4-105">O tipo de local de armazenamento do Azure usado depende de qual opção foi selecionada quando os documentos foram exportados.</span><span class="sxs-lookup"><span data-stu-id="716a4-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span> 

<span data-ttu-id="716a4-106">Este artigo fornece instruções sobre como usar o Microsoft Azure Storage Explorer para se conectar a um local de armazenamento do Azure para navegar e baixar os documentos exportados.</span><span class="sxs-lookup"><span data-stu-id="716a4-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="716a4-107">Para obter mais informações sobre o Azure Storage Explorer, consulte [QuickStart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span><span class="sxs-lookup"><span data-stu-id="716a4-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="716a4-108">Etapa 1: instalar o Azure Storage Explorer</span><span class="sxs-lookup"><span data-stu-id="716a4-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="716a4-109">A primeira etapa é baixar e instalar o Gerenciador de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="716a4-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="716a4-110">Para obter instruções, consulte [Azure Storage Explorer Tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span><span class="sxs-lookup"><span data-stu-id="716a4-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="716a4-111">Use essa ferramenta para se conectar e baixar os documentos exportados na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="716a4-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="716a4-112">Etapa 2: obter a URL SAS do trabalho de exportação</span><span class="sxs-lookup"><span data-stu-id="716a4-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="716a4-113">A próxima etapa é obter a URL de assinatura de acesso compartilhado (SAS) gerada quando você criou o trabalho de exportação para [exportar documentos de um conjunto de revisão](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="716a4-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="716a4-114">Você pode copiar a URL SAS para documentos que são carregados para um local de armazenamento do Azure fornecido pela Microsoft ou um local de armazenamento do Azure gerenciado por sua organização.</span><span class="sxs-lookup"><span data-stu-id="716a4-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="716a4-115">Em ambos os casos, você usa a URL SAS para se conectar ao local de armazenamento do Azure na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="716a4-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="716a4-116">Na página **descoberta eletrônica avançada** , vá para o caso e clique na guia **exportações** .</span><span class="sxs-lookup"><span data-stu-id="716a4-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="716a4-117">Na guia **exportações** , clique no trabalho de exportação que você deseja baixar.</span><span class="sxs-lookup"><span data-stu-id="716a4-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="716a4-118">Na página do menu suspenso, em **locais**, copie a URL SAS que é exibida.</span><span class="sxs-lookup"><span data-stu-id="716a4-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="716a4-119">Se necessário, você pode salvá-lo em um arquivo para que possa acessá-lo na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="716a4-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![Copiar a URL SAS exibida em locais](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="716a4-121">Etapa 3: conectar-se ao local de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="716a4-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="716a4-122">A etapa final é usar o Gerenciador de armazenamento do Azure e a URL SAS para se conectar ao local de armazenamento do Azure e baixar os documentos que você exportou para um computador local.</span><span class="sxs-lookup"><span data-stu-id="716a4-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1.  <span data-ttu-id="716a4-123">Abra o Azure Storage Explorer que você instalou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="716a4-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="716a4-124">Clique no ícone **adicionar conta** .</span><span class="sxs-lookup"><span data-stu-id="716a4-124">Click the **Add account** icon.</span></span> <span data-ttu-id="716a4-125">Como alternativa, você pode clicar com o botão direito do mouse em **contas de armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="716a4-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![Clique no ícone Adicionar conta](../media/AzureStorageConnect.png)

3.  <span data-ttu-id="716a4-127">Na página **conectar ao Azure Storage** , clique em **usar um URI de assinatura de acesso compartilhado (SAS)** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="716a4-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![Clique em usar um URI de assinatura de acesso compartilhado (SAS) e clique em avançar](../media/AzureStorageConnect2.png)

4.  <span data-ttu-id="716a4-129">Na página **anexar com URI SAS** , clique na caixa URI e cole a URL SAS obtida na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="716a4-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![Colar a URL SAS na caixa URI](../media/AzureStorageConnect3.png)

    <span data-ttu-id="716a4-131">Observe que uma parte da URL SAS é exibida na caixa **nome para exibição** .</span><span class="sxs-lookup"><span data-stu-id="716a4-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="716a4-132">Ele será usado como o nome de exibição do contêiner que é criado nas contas de **armazenamento** depois que você se conecta ao local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="716a4-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="716a4-133">Esse nome consiste na ID do caso de descoberta eletrônica avançada ser de um identificador exclusivo.</span><span class="sxs-lookup"><span data-stu-id="716a4-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="716a4-134">Você pode manter o nome de exibição padrão ou alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="716a4-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="716a4-135">Se você alterá-lo, o nome para exibição deverá ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="716a4-135">If you change it, the display name must be unique.</span></span>

5.  <span data-ttu-id="716a4-136">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="716a4-136">Click **Next**.</span></span>

    <span data-ttu-id="716a4-137">A página de **Resumo de conexão** é exibida.</span><span class="sxs-lookup"><span data-stu-id="716a4-137">The **Connection summary** page is displayed.</span></span>
   
    ![Clique em conectar na página Resumo de conexão para se conectar ao local de armazenamento do Azure](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="716a4-139">Na página **Resumo da conexão** , revise as informações de conexão e clique em **conectar**.</span><span class="sxs-lookup"><span data-stu-id="716a4-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span> 

    <span data-ttu-id="716a4-140">O **nó contêineres blob** (em **contas** > **de armazenamento (contêineres anexados)** \> é aberto.</span><span class="sxs-lookup"><span data-stu-id="716a4-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span> 

    ![Exportar trabalhos no nó contêineres de BLOBs](../media/AzureStorageConnect5.png)

    <span data-ttu-id="716a4-142">Ele contém um contêiner nomeado com o nome de exibição da etapa 4.</span><span class="sxs-lookup"><span data-stu-id="716a4-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="716a4-143">Este contêiner contém uma pasta para cada trabalho de exportação que você criou.</span><span class="sxs-lookup"><span data-stu-id="716a4-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="716a4-144">Essas pastas são nomeadas com uma ID que corresponde à ID do trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="716a4-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="716a4-145">Você pode encontrar essas IDs de exportação (e o nome da exportação) em **informações de suporte** na página de menu para cada um dos **dados de preparação do trabalho de exportação** listados na guia **trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="716a4-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="716a4-146">Clique duas vezes na pasta de trabalho de exportação para abri-la.</span><span class="sxs-lookup"><span data-stu-id="716a4-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="716a4-147">Uma lista de pastas e relatórios de exportação é exibida.</span><span class="sxs-lookup"><span data-stu-id="716a4-147">A list of folders and export reports is displayed.</span></span>
   
    ![A pasta de exportação contém arquivos exportados e relatórios de exportação](../media/AzureStorageConnect6.png)

   <span data-ttu-id="716a4-149">A pasta de trabalho de exportação contém os itens a seguir.</span><span class="sxs-lookup"><span data-stu-id="716a4-149">The export job folder contains the following items.</span></span> <span data-ttu-id="716a4-150">Os itens reais na pasta de exportação são determinados pelas opções de exportação configuradas quando o trabalho de exportação foi criado.</span><span class="sxs-lookup"><span data-stu-id="716a4-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="716a4-151">Para obter mais informações, consulte [exportar documentos de um conjunto de revisão](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="716a4-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="716a4-152">Export_load_file. csv: este arquivo CSV é um relatório de exportação de detalhes que contém informações sobre cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="716a4-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="716a4-153">O arquivo consiste em uma coluna para cada propriedade de metadados de um documento.</span><span class="sxs-lookup"><span data-stu-id="716a4-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="716a4-154">Para obter uma lista e uma descrição dos metadados incluídos neste relatório, confira a coluna **nome do campo exportado** na tabela em [campos de metadados do documento na descoberta eletrônica avançada](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="716a4-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields.md).</span></span>
    
    - <span data-ttu-id="716a4-155">Summary. txt: um arquivo de texto que contém um resumo da exportação, incluindo as estatísticas de exportação.</span><span class="sxs-lookup"><span data-stu-id="716a4-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="716a4-156">Extracted_text_files: esta pasta contém uma versão de arquivo de texto de cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="716a4-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="716a4-157">NativeFiles: esta pasta contém uma versão de arquivo nativo de cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="716a4-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="716a4-158">Error_files: esta pasta inclui os seguintes itens quando o trabalho de exportação contém qualquer arquivo de erro:</span><span class="sxs-lookup"><span data-stu-id="716a4-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="716a4-159">ExtractionError. csv: este arquivo CSV contém os metadados disponíveis para arquivos que não foram extraídos corretamente de seu item pai.</span><span class="sxs-lookup"><span data-stu-id="716a4-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="716a4-160">ProcessingError: esta pasta contém documentos com erros de processamento.</span><span class="sxs-lookup"><span data-stu-id="716a4-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="716a4-161">Esse conteúdo está em um nível de item, o que significa que, se um anexo tiver um erro de processamento, o documento que contém o anexo também será incluído nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="716a4-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="716a4-162">Para exportar todo o conteúdo da exportação, selecione a pasta exportar e clique em **baixar**.</span><span class="sxs-lookup"><span data-stu-id="716a4-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="716a4-163">Especifique o local onde você deseja baixar os arquivos exportados e clique em Selecionar pasta.</span><span class="sxs-lookup"><span data-stu-id="716a4-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="716a4-164">O explorador de armazenamento do Azure inicia o processo de exportação.</span><span class="sxs-lookup"><span data-stu-id="716a4-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="716a4-165">O status do download dos itens exportados é exibido no painel de **atividades** .</span><span class="sxs-lookup"><span data-stu-id="716a4-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="716a4-166">Uma mensagem é exibida quando o download é concluído.</span><span class="sxs-lookup"><span data-stu-id="716a4-166">A message is displayed when the download is finished.</span></span>

    ![Uma mensagem é exibida quando o download é concluído](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="716a4-168">Em vez de baixar todo o trabalho de exportação, você pode selecionar itens específicos para baixar.</span><span class="sxs-lookup"><span data-stu-id="716a4-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="716a4-169">E, em vez de baixar itens, você pode clicar duas vezes em um item para exibi-lo.</span><span class="sxs-lookup"><span data-stu-id="716a4-169">And instead of downloading items, you can double-click an item to view it.</span></span>
