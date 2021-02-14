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
description: Use arquivos CSV de uma Pesquisa de Conteúdo existente para criar uma pesquisa de lista de IDs que retorna mensagens de email específicas.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817970"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="136b6-103">Preparar um arquivo CSV para uma lista de IDs de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="136b6-103">Prepare a CSV file for an ID list Content Search</span></span>

<span data-ttu-id="136b6-104">Você pode pesquisar mensagens de email de caixa de correio específicas e outros itens de caixa de correio usando uma lista de IDs do Exchange.</span><span class="sxs-lookup"><span data-stu-id="136b6-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="136b6-105">Para criar uma pesquisa de lista de IDs (chamada formalmente de pesquisa direcionada), envie um arquivo de valores separados por vírgula (CSV) que identifique os itens de caixa de correio específicos a ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="136b6-105">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="136b6-106">Para esse arquivo CSV, você usa o arquivo **Results.csv** ou o arquivo **Items.csv** não Items.csvque são incluídos quando você exporta os resultados da Pesquisa de Conteúdo ou exporta um relatório de Pesquisa de Conteúdo da Pesquisa de Conteúdo e da Pesquisa de Conteúdo existente.</span><span class="sxs-lookup"><span data-stu-id="136b6-106">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="136b6-107">Em seguida, edite um desses arquivos para indicar os itens específicos a ser pesquisado e, em seguida, crie uma nova pesquisa de lista de IDs e envie o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="136b6-107">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span>

<span data-ttu-id="136b6-108">Aqui está uma rápida visão geral do processo de criação de uma pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-108">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="136b6-109">Crie e execute uma Pesquisa de Conteúdo nova ou guiada no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="136b6-109">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="136b6-110">Exporte os resultados da pesquisa de conteúdo ou exporte o relatório de pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="136b6-110">Export the content search results or export the content search report.</span></span> <span data-ttu-id="136b6-111">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="136b6-111">For more information, see:</span></span>

    - [<span data-ttu-id="136b6-112">Exportar resultados de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="136b6-112">Export Content Search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="136b6-113">Exportar um relatório da Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="136b6-113">Export a Content Search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="136b6-114">Edite **oResults.csv** ou  o arquivo Items.csve identifique os itens de caixa de correio específicos que você deseja incluir na pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-114">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="136b6-115">Consulte as [instruções](#prepare-the-csv-file-for-an-id-list-search) para preparar um arquivo CSV para uma pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-115">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="136b6-116">Crie uma nova pesquisa de lista de IDs (veja as [instruções)](#create-an-id-list-search)e envie o arquivo CSV que você preparou.</span><span class="sxs-lookup"><span data-stu-id="136b6-116">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="136b6-117">A consulta de pesquisa criada pesquisa apenas os itens selecionados no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="136b6-117">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="136b6-118">As pesquisas de lista de IDs só têm suporte para itens de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="136b6-118">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="136b6-119">Você não pode pesquisar documentos do SharePoint e do OneDrive em uma pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-119">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

 <span data-ttu-id="136b6-120">**Por que criar uma pesquisa de lista de IDs?**</span><span class="sxs-lookup"><span data-stu-id="136b6-120">**Why create an ID list search?**</span></span> <span data-ttu-id="136b6-121">Se você não puder determinar se um item está respondendo a uma solicitação de Descoberta eDiscovery com base nos metadados nos arquivos **Results.csv** ou **não** Items.csv, você pode usar uma pesquisa de lista de IDs para encontrar, visualizar e exportar esse item para determinar se ele responde ao caso que você está investigando.</span><span class="sxs-lookup"><span data-stu-id="136b6-121">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="136b6-122">As pesquisas de lista de IDs são normalmente usadas para pesquisar e retornar um conjunto específico de itens não índicedos.</span><span class="sxs-lookup"><span data-stu-id="136b6-122">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="136b6-123">Preparar o arquivo CSV para uma pesquisa de lista de IDs</span><span class="sxs-lookup"><span data-stu-id="136b6-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="136b6-124">Depois de exportar os resultados da pesquisa ou o relatório para uma pesquisa de conteúdo, você pode executar as seguintes etapas para preparar o arquivo CSV para uma pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-124">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="136b6-125">Esse arquivo CSV identificará cada item na pesquisa da lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-125">This CSV file will identify every item in the ID list search.</span></span>

<span data-ttu-id="136b6-126">Observe que você pode usar um arquivo CSV de uma pesquisa que incluiu  sites do SharePoint e contas do OneDrive, mas pode selecionar apenas itens de caixa de correio para uma pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-126">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="136b6-127">Se você selecionar um documento no SharePoint ou no OneDrive, o arquivo CSV falhará na validação ao criar uma pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="136b6-128">Abra o **Results.csv** arquivo de Items.csv **não Items.csv** no Excel.</span><span class="sxs-lookup"><span data-stu-id="136b6-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="136b6-129">Na coluna **Selecionado,** digite **Sim** na célula que corresponde ao item que você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="136b6-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="136b6-130">Repita essa etapa para cada item que você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="136b6-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="136b6-131">Quando você abre o arquivo CSV no Excel, o formato de dados para a coluna **ID do** Documento é alterado para **Geral.**</span><span class="sxs-lookup"><span data-stu-id="136b6-131">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="136b6-132">Isso resulta na exibição da ID do documento de um item em notação científica.</span><span class="sxs-lookup"><span data-stu-id="136b6-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="136b6-133">Por exemplo, a ID do documento "481037338205" é exibida como "4.81037E+11". Você precisa executar as  próximas etapas para alterar o formato de dados da coluna **ID** do Documento para Número para restaurar o formato correto para a ID do documento.</span><span class="sxs-lookup"><span data-stu-id="136b6-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="136b6-134">Se você não fizer isso, a pesquisa da lista de IDs que usa o arquivo CSV falhará.</span><span class="sxs-lookup"><span data-stu-id="136b6-134">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="136b6-135">Clique com o botão direito do mouse na coluna **ID do** Documento inteira e selecione **Formatar Células.**</span><span class="sxs-lookup"><span data-stu-id="136b6-135">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="136b6-136">Na caixa **Categoria,** clique em **Número.**</span><span class="sxs-lookup"><span data-stu-id="136b6-136">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="136b6-137">Altere o número de casas decimais para **0** e clique em **OK** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="136b6-137">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="136b6-138">Observe que os valores na coluna ID do Documento são alterados para números.</span><span class="sxs-lookup"><span data-stu-id="136b6-138">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="136b6-139">Veja um exemplo de um arquivo CSV que está pronto para ser enviado para uma pesquisa de conteúdo de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-139">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>

    ![Exemplo de um arquivo CSV para uma pesquisa de conteúdo direcionada](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. <span data-ttu-id="136b6-141">Salve o arquivo CSV ou use **Salvar como** para salvar o arquivo com um nome de arquivo diferente.</span><span class="sxs-lookup"><span data-stu-id="136b6-141">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="136b6-142">Em ambos os casos, certifique-se de salvar o arquivo com o formato CSV.</span><span class="sxs-lookup"><span data-stu-id="136b6-142">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="136b6-143">Criar uma pesquisa de lista de IDs</span><span class="sxs-lookup"><span data-stu-id="136b6-143">Create an ID list search</span></span>

<span data-ttu-id="136b6-144">A próxima etapa é criar uma nova Lista de IDs de Pesquisa de Conteúdo e enviar o arquivo CSV que você preparou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="136b6-144">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="136b6-145">Você deve criar uma pesquisa de lista de IDs no mais de 2 dias após exportar os resultados ou relatório de uma Pesquisa de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="136b6-145">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="136b6-146">Se os resultados da pesquisa ou relatório onde foi exportado há mais de 2 dias, exporte os resultados da pesquisa ou relatório para gerar arquivos CSV atualizados.</span><span class="sxs-lookup"><span data-stu-id="136b6-146">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="136b6-147">Em seguida, você pode preparar um dos arquivos CSV atualizados e usá-lo para criar uma pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-147">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="136b6-148">No Centro de Conformidade & segurança, vá **para** Pesquisa \> **de Conteúdo de Pesquisa.**</span><span class="sxs-lookup"><span data-stu-id="136b6-148">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>

2. <span data-ttu-id="136b6-149">Na página **Pesquisar,** clique na seta ao lado do ícone Adicionar Nova pesquisa e clique em ![ Pesquisar por Lista de ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)  **IDs.**</span><span class="sxs-lookup"><span data-stu-id="136b6-149">On the **Search** page, click the arrow next to ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>

    ![Click Search by ID List from the New search dropdown list](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. <span data-ttu-id="136b6-151">No flyout Pesquisar por **Lista de IDs,** nomee a  pesquisa (e, opcionalmente, descreva-a) e clique em Procurar e selecione o arquivo CSV preparado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="136b6-151">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="136b6-152">O Microsoft 365 tenta validar o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="136b6-152">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="136b6-153">Se a validação não for bem-sucedida, será exibida uma mensagem de erro que pode ajudá-lo a solucionar os erros de validação.</span><span class="sxs-lookup"><span data-stu-id="136b6-153">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="136b6-154">O arquivo CSV deve ser validado com êxito para criar uma pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-154">The CSV file has to be successfully validated to create an ID list search.</span></span>

4. <span data-ttu-id="136b6-155">Depois que o arquivo CSV for validado com êxito, clique em **Pesquisar** para criar a pesquisa da lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-155">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="136b6-156">Veja um exemplo dos resultados estimados da pesquisa e da consulta gerada para uma pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-156">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>

    ![Consulta de pesquisa para uma pesquisa de conteúdo direcionado no painel de detalhes](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    <span data-ttu-id="136b6-158">Observe que o número de itens estimados exibidos nas estatísticas da pesquisa de ID deve corresponder ao número de itens selecionados no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="136b6-158">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

5. <span data-ttu-id="136b6-159">Visualize ou exporte os itens retornados pela pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-159">Preview or export the items returned by the ID list search.</span></span>

> [!NOTE]
> <span data-ttu-id="136b6-160">Se você mover uma caixa de correio após criar uma pesquisa de lista de IDs, a consulta para a pesquisa não retornará os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="136b6-160">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="136b6-161">Isso acontece porque a propriedade **DocumentId** dos itens da caixa de correio é alterada quando uma caixa de correio é movida.</span><span class="sxs-lookup"><span data-stu-id="136b6-161">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="136b6-162">Na rara instância em que uma caixa de correio é movida depois de criar uma pesquisa de lista de IDs, você deve criar uma nova pesquisa de conteúdo (ou atualizar os resultados da pesquisa para a pesquisa de conteúdo existente) e exportar os resultados da pesquisa ou relatório para gerar arquivos CSV atualizados que podem ser usados para criar uma nova pesquisa de lista de IDs.</span><span class="sxs-lookup"><span data-stu-id="136b6-162">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
