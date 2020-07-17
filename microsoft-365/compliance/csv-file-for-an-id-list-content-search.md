---
title: Preparar um arquivo CSV para uma lista de IDs de Pesquisa de Conteúdo
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Use arquivos CSV de uma pesquisa de conteúdo existente para criar uma pesquisa de lista de ID que retorne mensagens de email específicas.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817970"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="0018c-103">Preparar um arquivo CSV para uma lista de IDs de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="0018c-103">Prepare a CSV file for an ID list Content Search</span></span>

<span data-ttu-id="0018c-104">Você pode pesquisar mensagens de email de caixa de correio específicas e outros itens de caixa de correio usando uma lista de IDs do Exchange.</span><span class="sxs-lookup"><span data-stu-id="0018c-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="0018c-105">Para criar uma pesquisa de lista de ID (formalmente chamada de pesquisa direcionada), você envia um arquivo CSV (valor separado por vírgula) que identifica os itens de caixa de correio específicos para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0018c-105">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="0018c-106">Para este arquivo CSV, você usa o arquivo **Results.csv** ou o arquivo **Items.csvnão indexado** que é incluído quando você exporta os resultados da pesquisa de conteúdo ou exporta um relatório de pesquisa de conteúdo da pesquisa de conteúdo existente.</span><span class="sxs-lookup"><span data-stu-id="0018c-106">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="0018c-107">Em seguida, edite um desses arquivos para indicar os itens específicos que serão pesquisados e, em seguida, crie uma nova lista de ID pesquisa e envie o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="0018c-107">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span>

<span data-ttu-id="0018c-108">Veja uma rápida visão geral do processo de criação de uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-108">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="0018c-109">Criar e executar uma pesquisa de conteúdo nova ou dirigida no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="0018c-109">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="0018c-110">Exporte os resultados da pesquisa de conteúdo ou exporte o relatório de pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0018c-110">Export the content search results or export the content search report.</span></span> <span data-ttu-id="0018c-111">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="0018c-111">For more information, see:</span></span>

    - [<span data-ttu-id="0018c-112">Exportar resultados de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="0018c-112">Export Content Search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="0018c-113">Exportar um relatório da Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="0018c-113">Export a Content Search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="0018c-114">Edite o arquivo **Results.csv** ou o **Items.csvnão indexado** e identifique os itens de caixa de correio específicos que você deseja incluir na pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-114">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="0018c-115">Consulte as [instruções](#prepare-the-csv-file-for-an-id-list-search) para preparar um arquivo CSV para uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-115">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="0018c-116">Crie uma nova pesquisa de lista de ID (consulte as [instruções](#create-an-id-list-search)) e envie o arquivo CSV que você preparou.</span><span class="sxs-lookup"><span data-stu-id="0018c-116">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="0018c-117">A consulta de pesquisa criada só pesquisará os itens selecionados no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="0018c-117">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="0018c-118">Pesquisas de lista de ID têm suporte apenas para itens de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="0018c-118">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="0018c-119">Você não pode pesquisar documentos do SharePoint e do OneDrive em uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-119">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

 <span data-ttu-id="0018c-120">**Por que criar uma pesquisa de lista de ID?**</span><span class="sxs-lookup"><span data-stu-id="0018c-120">**Why create an ID list search?**</span></span> <span data-ttu-id="0018c-121">Se você não conseguir determinar se um item está respondendo a uma solicitação de descoberta eletrônica com base nos metadados dos arquivos de Items.csv**Results.csv** ou não **indexado** , você poderá usar uma pesquisa de lista de ID para localizar, Visualizar e exportar esse item para determinar se ele é responsivo ao caso que você está investigando.</span><span class="sxs-lookup"><span data-stu-id="0018c-121">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="0018c-122">Pesquisas de lista de ID normalmente são usadas para pesquisar e retornar um conjunto específico de itens não indexados.</span><span class="sxs-lookup"><span data-stu-id="0018c-122">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="0018c-123">Preparar o arquivo CSV para uma pesquisa de lista de ID</span><span class="sxs-lookup"><span data-stu-id="0018c-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="0018c-124">Depois de exportar os resultados de pesquisa ou o relatório de uma pesquisa de conteúdo, você pode executar as seguintes etapas para preparar o arquivo CSV para uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-124">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="0018c-125">Este arquivo CSV identificará todos os itens na pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-125">This CSV file will identify every item in the ID list search.</span></span>

<span data-ttu-id="0018c-126">Observe que você pode usar um arquivo CSV de uma pesquisa que incluiu sites do SharePoint e contas do OneDrive, mas *só* pode selecionar itens de caixa de correio para uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-126">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="0018c-127">Se você selecionar um documento no SharePoint ou no OneDrive, o arquivo CSV apresentará falha na validação quando você criar uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="0018c-128">Abra o arquivo de Items.csv**Results.csv** ou não **indexado** no Excel.</span><span class="sxs-lookup"><span data-stu-id="0018c-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="0018c-129">Na coluna **selecionado** , digite **Sim** na célula que corresponde ao item que você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="0018c-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="0018c-130">Repita essa etapa para cada item que você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="0018c-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0018c-131">Quando você abre o arquivo CSV no Excel, o formato de dados da coluna **ID do documento** é alterado para **geral**.</span><span class="sxs-lookup"><span data-stu-id="0018c-131">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="0018c-132">Isso resulta na exibição da ID do documento para um item em notação científica.</span><span class="sxs-lookup"><span data-stu-id="0018c-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="0018c-133">Por exemplo, a ID de documento de "481037338205" é exibida como "4.81037 E + 11" você tem que executar as próximas etapas para alterar o formato de dados da coluna **ID do documento** para **número** para restaurar o formato correto para a ID do documento.</span><span class="sxs-lookup"><span data-stu-id="0018c-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="0018c-134">Se você não fizer isso, a pesquisa de lista de ID que usa o arquivo CSV falhará.</span><span class="sxs-lookup"><span data-stu-id="0018c-134">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="0018c-135">Clique com o botão direito do mouse na coluna **ID do documento** inteiro e selecione **Formatar células**.</span><span class="sxs-lookup"><span data-stu-id="0018c-135">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="0018c-136">Na caixa **categoria** , clique em **número**.</span><span class="sxs-lookup"><span data-stu-id="0018c-136">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="0018c-137">Altere o número de casas decimais para **0**e, em seguida, clique em **OK** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="0018c-137">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="0018c-138">Observe que os valores na coluna ID do documento são alterados para números.</span><span class="sxs-lookup"><span data-stu-id="0018c-138">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="0018c-139">Veja um exemplo do arquivo CSV que está pronto para ser enviado para uma pesquisa de conteúdo de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-139">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>

    ![Exemplo de um arquivo CSV para uma pesquisa de conteúdo direcionada](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. <span data-ttu-id="0018c-141">Salve o arquivo CSV ou use **salvar como** para salvar o arquivo com outro nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="0018c-141">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="0018c-142">Em ambos os casos, certifique-se de salvar o arquivo com o formato CSV.</span><span class="sxs-lookup"><span data-stu-id="0018c-142">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="0018c-143">Criar uma pesquisa de lista de ID</span><span class="sxs-lookup"><span data-stu-id="0018c-143">Create an ID list search</span></span>

<span data-ttu-id="0018c-144">A próxima etapa é criar uma nova pesquisa de conteúdo de lista de ID e enviar o arquivo CSV que você preparou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="0018c-144">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0018c-145">Você deve criar uma pesquisa de lista de ID que não tenha mais de dois dias após a exportação dos resultados ou do relatório de uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0018c-145">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="0018c-146">Se os resultados da pesquisa ou o relatório onde exportados há mais de 2 dias, você deve exportar novamente os resultados da pesquisa ou o relatório para gerar arquivos CSV atualizados.</span><span class="sxs-lookup"><span data-stu-id="0018c-146">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="0018c-147">Em seguida, você pode preparar um dos arquivos CSV atualizados e usá-lo para criar uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-147">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="0018c-148">No centro de conformidade & segurança, vá para **Search** \> **pesquisa de conteúdo**de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0018c-148">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>

2. <span data-ttu-id="0018c-149">Na página de **pesquisa** , clique na seta ao lado de ![ Adicionar ícone ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nova pesquisa**e, em seguida, clique em **Pesquisar por lista de ID**.</span><span class="sxs-lookup"><span data-stu-id="0018c-149">On the **Search** page, click the arrow next to ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>

    ![Clique em Pesquisar pela lista de IDs na nova lista suspensa de pesquisa](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. <span data-ttu-id="0018c-151">No submenu de **lista Pesquisar por ID** , nomeie a pesquisa (e, opcionalmente, descreva-a) e clique em **procurar** e selecione o arquivo CSV que você preparou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="0018c-151">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="0018c-152">O Microsoft 365 tenta validar o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="0018c-152">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="0018c-153">Se a validação não for bem sucedida, será exibida uma mensagem de erro que poderá ajudá-lo a solucionar os erros de validação.</span><span class="sxs-lookup"><span data-stu-id="0018c-153">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="0018c-154">O arquivo CSV deve ser validado com êxito para criar uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-154">The CSV file has to be successfully validated to create an ID list search.</span></span>

4. <span data-ttu-id="0018c-155">Depois que o arquivo CSV for validado com êxito, clique em **Pesquisar** para criar a pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-155">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="0018c-156">Veja um exemplo dos resultados estimados da pesquisa e a consulta que é gerada para uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-156">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>

    ![Consulta de pesquisa para uma pesquisa de conteúdo direcionada no painel de detalhes](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    <span data-ttu-id="0018c-158">Observe que o número de itens estimados exibidos em estatísticas para a pesquisa de ID deve corresponder ao número de itens que você selecionou no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="0018c-158">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

5. <span data-ttu-id="0018c-159">Visualize ou exporte os itens retornados pela pesquisa da lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-159">Preview or export the items returned by the ID list search.</span></span>

> [!NOTE]
> <span data-ttu-id="0018c-160">Se você mover uma caixa de correio depois de criar uma pesquisa de lista de ID, a consulta para a pesquisa não retornará os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="0018c-160">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="0018c-161">Isso ocorre porque a propriedade **DocumentID** para itens da caixa de correio é alterada quando uma caixa de correio é movida.</span><span class="sxs-lookup"><span data-stu-id="0018c-161">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="0018c-162">Na rara instância, quando uma caixa de correio é movida depois de criar uma pesquisa de lista de ID, você deve criar uma nova pesquisa de conteúdo (ou atualizar os resultados da pesquisa para a pesquisa de conteúdo existente) e exportar os resultados da pesquisa ou o relatório para gerar arquivos CSV atualizados que podem ser usados para criar uma nova pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="0018c-162">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
