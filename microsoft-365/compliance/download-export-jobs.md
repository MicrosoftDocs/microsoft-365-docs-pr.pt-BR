---
title: Exportar documentos para a conta do Azure Armazenamento sua organização
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
ms.custom: seo-marvel-mar2020
description: Exporte documentos em um conjunto de revisão para uma conta do Azure Armazenamento e use Gerenciador de Armazenamento do Azure para baixá-los para um computador local.
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574696"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a><span data-ttu-id="b7fe8-103">Exportar documentos em um conjunto de revisão para uma conta Armazenamento Azure</span><span class="sxs-lookup"><span data-stu-id="b7fe8-103">Export documents in a review set to an Azure Storage account</span></span>

<span data-ttu-id="b7fe8-104">Quando você exporta documentos de um conjunto de revisão em um caso Advanced eDiscovery, você tem a opção de exportá-los para uma conta do Azure Armazenamento gerenciada pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-104">When you export documents from a review set in an Advanced eDiscovery case, you have the option to export them to an Azure Storage account managed by your organization.</span></span> <span data-ttu-id="b7fe8-105">Se você usou essa opção, os documentos serão carregados no local de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-105">If you used this option, the documents are uploaded to your Azure Storage location.</span></span> <span data-ttu-id="b7fe8-106">Depois que eles são exportados, você pode acessar os documentos (e baixá-los para um computador local ou outro local) usando o Gerenciador de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-106">After they are exported, you can access the documents (and download them to a local computer or other location) by using the Azure Storage Explorer.</span></span> <span data-ttu-id="b7fe8-107">Este artigo fornece instruções sobre como exportar documentos para sua conta do Azure Armazenamento e o uso do Gerenciador de Armazenamento do Azure para se conectar a um local de Armazenamento do Azure para baixar os documentos exportados.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-107">This article provides instructions for how to export documents to your Azure Storage account and the use the Azure Storage Explorer to connect to an Azure Storage location to download the exported documents.</span></span> <span data-ttu-id="b7fe8-108">Para obter mais informações sobre Gerenciador de Armazenamento do Azure, consulte [Use Gerenciador de Armazenamento do Azure](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span><span class="sxs-lookup"><span data-stu-id="b7fe8-108">For more information about Azure Storage Explorer, see [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="before-you-export-documents-from-a-review-set"></a><span data-ttu-id="b7fe8-109">Antes de exportar documentos de um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="b7fe8-109">Before you export documents from a review set</span></span>

- <span data-ttu-id="b7fe8-110">Você precisa fornecer um token de assinatura de acesso compartilhado (SAS) para sua conta do Azure Armazenamento e a URL de um contêiner específico na conta de armazenamento para exportar documentos de um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-110">You need to provide a shared access signature (SAS) token for your Azure Storage account and the URL for a specific container in the storage account to export documents from a review set.</span></span> <span data-ttu-id="b7fe8-111">Certifique-se de que elas estão em mãos (por exemplo, copiadas para um arquivo de texto) ao executar a Etapa 2</span><span class="sxs-lookup"><span data-stu-id="b7fe8-111">Be sure to have these at hand (for example, copied to a text file) when you perform Step 2</span></span>

  - <span data-ttu-id="b7fe8-112">**Token SAS**: Certifique-se de obter o token SAS é para sua conta de Armazenamento do Azure (e não para o contêiner).</span><span class="sxs-lookup"><span data-stu-id="b7fe8-112">**SAS token**: Be sure to get the SAS token is for your Azure Storage account (and not for the container).</span></span> <span data-ttu-id="b7fe8-113">Você pode gerar um token SAS para sua conta no Azure Armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-113">You can generate an SAS token for your account in Azure Storage.</span></span> <span data-ttu-id="b7fe8-114">Para fazer isso, vá para a conta do Azure Armazenamento  e selecione Compartilhar assinatura de acesso sob as configurações Configurações na folha de conta de armazenamento. </span><span class="sxs-lookup"><span data-stu-id="b7fe8-114">To do this, go to the Azure Storage account, and select **Share access signature** under the **Settings** settings in the storage account blade.</span></span> <span data-ttu-id="b7fe8-115">Use as configurações padrão e permita todos os tipos de recursos ao gerar o token SAS.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-115">Use the default settings and allow all resource types when you generate the SAS token.</span></span>

  - <span data-ttu-id="b7fe8-116">**URL do contêiner:** você precisa criar um contêiner para carregar os documentos do conjunto de revisão e obter uma cópia da URL do contêiner; por exemplo, `https://ediscoverydata.blob.core.windows.net/exportdata` .</span><span class="sxs-lookup"><span data-stu-id="b7fe8-116">**Container URL**: You need to create a container to upload the review set documents to, and then get a copy of the URL for the container; for example, `https://ediscoverydata.blob.core.windows.net/exportdata`.</span></span> <span data-ttu-id="b7fe8-117">Para obter a URL, vá para o contêiner no Azure Armazenamento e selecione **Propriedades** na seção Configurações **na** folha do contêiner.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-117">To get the URL, go to the container in Azure Storage, and select **Properties** under the **Settings** section in the container blade.</span></span>

- <span data-ttu-id="b7fe8-118">Baixe e instale o Gerenciador de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-118">Download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="b7fe8-119">Para obter instruções, [consulte Gerenciador de Armazenamento do Azure ferramenta](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span><span class="sxs-lookup"><span data-stu-id="b7fe8-119">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="b7fe8-120">Use essa ferramenta para se conectar ao contêiner em sua conta do Azure Armazenamento e baixe os documentos exportados na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-120">You use this tool to connect to the container in your Azure Storage account and download the documents that you exported in Step 1.</span></span>

## <a name="step-1-export-the-documents-from-a-review-set"></a><span data-ttu-id="b7fe8-121">Etapa 1: Exportar os documentos de um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="b7fe8-121">Step 1: Export the documents from a review set</span></span>

<span data-ttu-id="b7fe8-122">A primeira etapa é criar um trabalho de exportação para exportar documentos de um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-122">The first step is to create an export job to export documents out of a review set.</span></span> <span data-ttu-id="b7fe8-123">Para obter instruções mais detalhadas sobre todas as opções de exportação, consulte [Exportar documentos de um conjunto de revisão](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="b7fe8-123">For more detailed instructions about all the export options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="b7fe8-124">O procedimento a seguir destaca as configurações para exportar documentos para a conta do Azure Armazenamento sua organização.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-124">The following procedure highlights the settings to export documents to your organization's Azure Storage account.</span></span>

1. <span data-ttu-id="b7fe8-125">No centro Microsoft 365 de conformidade, abra o caso Advanced eDiscovery, selecione a guia Revisar conjuntos e selecione o conjunto de revisão que você deseja exportar. </span><span class="sxs-lookup"><span data-stu-id="b7fe8-125">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="b7fe8-126">No conjunto de revisão, clique em **Ação**  >  **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-126">In the review set, click **Action** > **Export**.</span></span>

3. <span data-ttu-id="b7fe8-127">Na página **Exportar opções,** digite um nome (obrigatório) e descrição (opcional) para a exportação.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-127">On the **Export options** flyout page, type a name (required) and description (optional) for the export.</span></span>

4. <span data-ttu-id="b7fe8-128">Configure as configurações nas seções documentos, metadados, conteúdo e opções.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-128">Configure the settings in the documents, metadata, content, and options sections.</span></span> <span data-ttu-id="b7fe8-129">Para obter mais informações sobre essas configurações, consulte [Exportar documentos de um conjunto de revisão](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="b7fe8-129">For more information about these settings, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

5. <span data-ttu-id="b7fe8-130">Na seção **Opções de saída,** selecione a estrutura de diretório condensada exportada para sua opção de Armazenamento **conta do Azure.**</span><span class="sxs-lookup"><span data-stu-id="b7fe8-130">In the **Output options** section, select the **Condensed directory structure exported to your Azure Storage account** option.</span></span>

6. <span data-ttu-id="b7fe8-131">Colar a URL do contêiner e o token SAS da sua conta de armazenamento nos campos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-131">Paste the container URL and the SAS token for your storage account in the corresponding fields.</span></span>

   ![Colar a URL de conexão e o token SAS nos campos correspondentes](../media/AzureStorageOutputOptions.png)

7. <span data-ttu-id="b7fe8-133">Clique **em Exportar** para criar o trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-133">Click **Export** to create the export job.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="b7fe8-134">Etapa 2: Obter a URL do SAS do trabalho de exportação</span><span class="sxs-lookup"><span data-stu-id="b7fe8-134">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="b7fe8-135">A próxima etapa é obter a URL do SAS gerada após criar o trabalho de exportação na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-135">The next step is to obtain the SAS URL that's generated after you create the export job in Step 1.</span></span> <span data-ttu-id="b7fe8-136">Você usa a URL do SAS para se conectar ao contêiner em sua conta do Azure Armazenamento que você exportou os documentos do conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-136">You use the SAS URL to connect to the container in your Azure Storage account that you exported the review set documents to.</span></span>

1. <span data-ttu-id="b7fe8-137">Na página **Advanced eDiscovery,** vá para a ocorrência e clique na **guia Exportações.**</span><span class="sxs-lookup"><span data-stu-id="b7fe8-137">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="b7fe8-138">Na guia **Exportar**, clique no trabalho de exportação que você deseja baixar.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-138">On the **Exports** tab, click the export job that you want to download.</span></span> <span data-ttu-id="b7fe8-139">Este é o trabalho de exportação que você criou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-139">This is the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="b7fe8-140">Na página sub-sub-texto, em **Locais**, copie a URL do SAS exibida.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-140">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="b7fe8-141">Se necessário, você pode salvá-lo em um arquivo de texto para poder acessá-lo na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-141">If necessary, you can save it to a text file so you can access it in Step 3.</span></span>

   ![Copie a URL do SAS exibida em Locais](../media/eDiscoExportJob.png)

   > [!TIP]
   > <span data-ttu-id="b7fe8-143">A URL do SAS exibida no trabalho de exportação é uma concatenação da URL do contêiner e do token SAS da sua conta do Azure Armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-143">The SAS URL that's displayed in the export job is a concatenation of the container URL and the SAS token for your Azure Storage account.</span></span> <span data-ttu-id="b7fe8-144">Você pode copiá-lo do trabalho de exportação ou criar você mesmo combinando a URL e o token SAS.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-144">You can copy it from the export job or create it yourself by combining the URL and the SAS token.</span></span>

## <a name="step-3-connect-to-the-azure-storage-container"></a><span data-ttu-id="b7fe8-145">Etapa 3: Conexão para o contêiner de Armazenamento Azure</span><span class="sxs-lookup"><span data-stu-id="b7fe8-145">Step 3: Connect to the Azure Storage container</span></span>

<span data-ttu-id="b7fe8-146">A etapa final é usar o Gerenciador de Armazenamento do Azure e a URL do SAS para se conectar ao contêiner em sua conta do Azure Armazenamento e baixar os documentos exportados para um computador local.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-146">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the container in your Azure Storage account and download the exported documents to a local computer.</span></span>

1. <span data-ttu-id="b7fe8-147">Inicie a Gerenciador de Armazenamento do Azure que você baixou e instalou.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-147">Start the Azure Storage Explorer that you downloaded and installed.</span></span>

2. <span data-ttu-id="b7fe8-148">Clique no **ícone Abrir Conexão Caixa de** Diálogo.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-148">Click the **Open Connect Dialog** icon.</span></span>

   ![Clique no ícone Adicionar conta](../media/AzureStorageConnect.png)

3. <span data-ttu-id="b7fe8-150">Na página **Conexão para o Azure Armazenamento,** clique em **Blob container**.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-150">On the **Connect to Azure Storage** page, click **Blob container**.</span></span>

4. <span data-ttu-id="b7fe8-151">Na página **Selecionar Método de Autenticação,** selecione a opção Assinatura de Acesso **Compartilhado (SAS)** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-151">On the **Select Authentication Method** page, select the **Shared access signature (SAS)** option and then click **Next**.</span></span>

5. <span data-ttu-id="b7fe8-152">Na página **Inserir Informações de** Conexão, colar a URL do SAS (obtida no trabalho de exportação na Etapa 2) na caixa URL do SAS do Contêiner de **Blob.**</span><span class="sxs-lookup"><span data-stu-id="b7fe8-152">On the **Enter Connection Info** page, paste the SAS URL (that you obtained in the export job in Step 2) in the **Blob Container SAS URL** box.</span></span>

    ![Colar a URL do SAS na caixa URI](../media/AzureStorageConnect3.png)

    <span data-ttu-id="b7fe8-154">Observe que o nome do contêiner é exibido na caixa **Nome de** exibição.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-154">Notice that the container name is displayed in the **Display name** box.</span></span> <span data-ttu-id="b7fe8-155">Você pode editar esse nome.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-155">You can edit this name.</span></span>

6. <span data-ttu-id="b7fe8-156">Clique **em Próximo** para exibir a página **de** resumo e clique em **Conexão**.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-156">Click **Next** to display the **summary** page and then click **Connect**.</span></span>

    <span data-ttu-id="b7fe8-157">O **nó contêineres Blob** **(em Armazenamento Contas**  >  **(Contêineres Anexados)** é \> aberto.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-157">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Exportar trabalhos no nó contêineres Blobs](../media/AzureStorageConnect5.png)

    <span data-ttu-id="b7fe8-159">Ele contém um contêiner chamado com o nome de exibição da etapa 5.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-159">It contains a container named with the display name from step 5.</span></span> <span data-ttu-id="b7fe8-160">Esse contêiner contém uma pasta para cada trabalho de exportação que você baixou para o contêiner em sua conta do Azure Armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-160">This container contains a folder for each export job that you've downloaded to the container in your Azure Storage account.</span></span> <span data-ttu-id="b7fe8-161">Essas pastas são nomeadas com uma ID que corresponde à ID do trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-161">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="b7fe8-162">Você pode encontrar essas IDs de exportação (e o nome da exportação) em Informações de suporte na página sub-sublta para cada Preparação de dados para o trabalho de exportação listados na guia **Trabalhos** no caso Advanced eDiscovery.  </span><span class="sxs-lookup"><span data-stu-id="b7fe8-162">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab in the Advanced eDiscovery case.</span></span>

7. <span data-ttu-id="b7fe8-163">Clique duas vezes na pasta de trabalho de exportação para abri-la.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-163">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="b7fe8-164">Uma lista de pastas e relatórios de exportação é exibida.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-164">A list of folders and export reports is displayed.</span></span>

    ![A pasta de exportação contém arquivos exportados e relatórios de exportação](../media/AzureStorageConnect6.png)

8. <span data-ttu-id="b7fe8-166">Para exportar todo o conteúdo do  trabalho de exportação, clique na seta Para cima para voltar à pasta de trabalho de exportação e clique em **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-166">To export all contents from the export job, click the **Up** arrow to go back to the export job folder, and then click **Download**.</span></span>

9. <span data-ttu-id="b7fe8-167">Especifique o local para onde você deseja baixar os arquivos exportados e clique em Selecionar pasta.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-167">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="b7fe8-168">A Gerenciador de Armazenamento do Azure inicia o processo de download.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-168">The Azure Storage Explorer starts the download process.</span></span> <span data-ttu-id="b7fe8-169">O status do download dos itens exportados é exibido no painel **Atividades.**</span><span class="sxs-lookup"><span data-stu-id="b7fe8-169">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="b7fe8-170">Uma mensagem é exibida quando o download é concluído.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-170">A message is displayed when the download is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="b7fe8-171">Em vez de baixar todo o trabalho de exportação no Gerenciador de Armazenamento do Azure, você pode selecionar itens específicos para baixar e exibir.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-171">Instead of downloading the entire export job in Azure Storage Explorer, you can select specific items to download and view.</span></span>

## <a name="more-information"></a><span data-ttu-id="b7fe8-172">Mais informações</span><span class="sxs-lookup"><span data-stu-id="b7fe8-172">More information</span></span>

- <span data-ttu-id="b7fe8-173">A pasta de trabalho de exportação contém os itens a seguir.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-173">The export job folder contains the following items.</span></span> <span data-ttu-id="b7fe8-174">Os itens reais na pasta de exportação são determinados pelas opções de exportação configuradas quando o trabalho de exportação foi criado.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-174">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="b7fe8-175">Para obter mais informações sobre essas opções, consulte [Exportar documentos de um conjunto de revisão](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="b7fe8-175">For more information about these options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

  - <span data-ttu-id="b7fe8-176">Export_load_file.csv: esse arquivo CSV é um relatório de exportação detalhado que contém informações sobre cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-176">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="b7fe8-177">O arquivo consiste em uma coluna para cada propriedade de metadados de um documento.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-177">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="b7fe8-178">Para uma lista e descrição dos metadados incluídos neste relatório, consulte a coluna **Nome** do campo exportado na tabela em Campos de metadados de documento [em Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="b7fe8-178">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>

  - <span data-ttu-id="b7fe8-179">Summary.txt: um arquivo de texto que contém um resumo da exportação, incluindo estatísticas de exportação.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-179">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>

  - <span data-ttu-id="b7fe8-180">Extracted_text_files: esta pasta contém uma versão de arquivo de texto de cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-180">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>

  - <span data-ttu-id="b7fe8-181">NativeFiles: esta pasta contém uma versão de arquivo nativa de cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-181">NativeFiles: This folder contains a native file version of each exported document.</span></span>

  - <span data-ttu-id="b7fe8-182">Error_files: essa pasta inclui os seguintes itens quando o trabalho de exportação contém arquivos de erro:</span><span class="sxs-lookup"><span data-stu-id="b7fe8-182">Error_files: This folder includes the following items when the export job contains any error files:</span></span>

    - <span data-ttu-id="b7fe8-183">ExtractionError.csv: esse arquivo CSV contém os metadados disponíveis para arquivos que não foram extraídos corretamente do item pai.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-183">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>

    - <span data-ttu-id="b7fe8-184">ProcessingError: esta pasta contém documentos com erros de processamento.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-184">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="b7fe8-185">Esse conteúdo está em um nível de item, o que significa que se um anexo tiver um erro de processamento, o documento que contém o anexo também será incluído nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="b7fe8-185">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
