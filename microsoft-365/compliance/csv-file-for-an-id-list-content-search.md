---
title: Preparar um arquivo CSV para uma pesquisa de conteúdo de lista de ID
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
description: Use um arquivo CSV de uma pesquisa de Conteúdo existente para criar uma pesquisa de lista de ID que retorna itens de email específicos.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311527"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="1decb-103">Preparar um arquivo CSV para uma pesquisa de conteúdo de lista de ID</span><span class="sxs-lookup"><span data-stu-id="1decb-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="1decb-104">Você pode pesquisar mensagens de email de caixa de correio específicas e outros itens de caixa de correio usando uma lista de Exchange IDs.</span><span class="sxs-lookup"><span data-stu-id="1decb-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="1decb-105">Para criar uma pesquisa de lista de IDs, você envia um arquivo de valores separados por vírgula (CSV) que identifica os itens específicos da caixa de correio a serem pesquisados.</span><span class="sxs-lookup"><span data-stu-id="1decb-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="1decb-106">Para esse arquivo CSV, você usa o arquivo **Results.csv** ou o arquivo Items.csvnão **Items.csv** que são incluídos ao exportar os resultados da pesquisa de conteúdo ou exportar um relatório de pesquisa de conteúdo de uma pesquisa de Conteúdo existente.</span><span class="sxs-lookup"><span data-stu-id="1decb-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="1decb-107">Em seguida, edite um desses arquivos para indicar os itens específicos a ser pesquisado, crie uma nova pesquisa de lista de ID e envie o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1decb-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="1decb-108">**Por que criar uma pesquisa de lista de ID?**</span><span class="sxs-lookup"><span data-stu-id="1decb-108">**Why create an ID list search?**</span></span> <span data-ttu-id="1decb-109">Se você não conseguir determinar se um item está respondendo a uma solicitação de Descoberta E com base nos metadados nos arquivos Items.csvou **não** Results.csv, você pode usar **uma** pesquisa de lista de ID para encontrar, visualizar e exportar esse item para determinar se ele responde ao caso que você está investigando.</span><span class="sxs-lookup"><span data-stu-id="1decb-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="1decb-110">As pesquisas de lista de ID geralmente são usadas para pesquisar e retornar um conjunto específico de itens não índicedos.</span><span class="sxs-lookup"><span data-stu-id="1decb-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="1decb-111">Aqui está uma visão geral rápida do processo para criar uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="1decb-112">Crie e execute uma nova pesquisa no Microsoft 365 de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1decb-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="1decb-113">Exporte os resultados da pesquisa de conteúdo ou o relatório de pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="1decb-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="1decb-114">Para saber mais, veja:</span><span class="sxs-lookup"><span data-stu-id="1decb-114">For more information, see:</span></span>

    - [<span data-ttu-id="1decb-115">Exportar resultados de Pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="1decb-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="1decb-116">Exportar um relatório de Pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="1decb-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="1decb-117">Edite **o arquivoResults.csv** ou **o** arquivo Items.csve identifique os itens de caixa de correio específicos para incluir na pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="1decb-118">Consulte as [instruções](#prepare-the-csv-file-for-an-id-list-search) para preparar um arquivo CSV para uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="1decb-119">Crie uma nova pesquisa de lista de ID (consulte as [instruções](#create-an-id-list-search)) e envie o arquivo CSV que você preparou.</span><span class="sxs-lookup"><span data-stu-id="1decb-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="1decb-120">A consulta de pesquisa criada procurará apenas os itens selecionados no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1decb-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="1decb-121">As pesquisas de lista de ID são suportadas apenas para itens de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="1decb-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="1decb-122">Não é possível pesquisar SharePoint documentos OneDrive em uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="1decb-123">Preparar o arquivo CSV para uma pesquisa de lista de ID</span><span class="sxs-lookup"><span data-stu-id="1decb-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="1decb-124">Depois de exportar os resultados da pesquisa ou o relatório de uma pesquisa, execute as etapas a seguir para preparar o arquivo CSV para uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="1decb-125">Esse arquivo CSV identifica cada item na pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="1decb-126">Você pode usar um arquivo CSV de uma pesquisa que incluiu SharePoint sites e OneDrive contas, mas você só pode selecionar itens de caixa de correio para uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="1decb-127">Se você selecionar um documento em SharePoint ou OneDrive, o arquivo CSV falhará na validação ao criar uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="1decb-128">Abra o **Results.csv** **ou o arquivo Items.csvnão Excel.**</span><span class="sxs-lookup"><span data-stu-id="1decb-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="1decb-129">Na coluna **Selecionado,** digite **Sim** na célula que corresponde ao item que você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="1decb-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="1decb-130">Repita esta etapa para cada item que você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="1decb-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1decb-131">Quando você abre o arquivo CSV no Excel, o formato de dados da coluna **ID** do Documento pode ter sido alterado para **Geral**.</span><span class="sxs-lookup"><span data-stu-id="1decb-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="1decb-132">Isso resulta na exibição da ID do documento de um item em notação científica.</span><span class="sxs-lookup"><span data-stu-id="1decb-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="1decb-133">Por exemplo, a ID do documento de "481037338205" é exibida como "4.81037E+11".</span><span class="sxs-lookup"><span data-stu-id="1decb-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="1decb-134">Se isso acontecer, você terá que executar as próximas etapas para alterar o formato de dados da coluna **ID** do Documento para **Número** para restaurar o formato correto para a ID do documento.</span><span class="sxs-lookup"><span data-stu-id="1decb-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="1decb-135">Se você não fizer isso, a pesquisa de lista de ID que usa o arquivo CSV falhará.</span><span class="sxs-lookup"><span data-stu-id="1decb-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="1decb-136">Clique com o botão direito do mouse em toda a **coluna ID** do Documento e selecione **Formatar Células**.</span><span class="sxs-lookup"><span data-stu-id="1decb-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="1decb-137">Na caixa **Categoria,** clique em **Número**.</span><span class="sxs-lookup"><span data-stu-id="1decb-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="1decb-138">Altere o número de casas decimais **para 0** e clique em **OK** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="1decb-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="1decb-139">Observe que os valores na coluna ID do documento são alterados para números.</span><span class="sxs-lookup"><span data-stu-id="1decb-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="1decb-140">Aqui está um exemplo de um arquivo CSV que está pronto para ser enviado para uma pesquisa de conteúdo de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![Exemplo de um arquivo CSV para uma pesquisa de conteúdo direcionada](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="1decb-142">Salve o arquivo CSV ou use **Salvar como** para salvar o arquivo com nome de arquivo diferente.</span><span class="sxs-lookup"><span data-stu-id="1decb-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="1decb-143">Em ambos os casos, salve o arquivo com o formato CSV.</span><span class="sxs-lookup"><span data-stu-id="1decb-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="1decb-144">Criar uma pesquisa de lista de ID</span><span class="sxs-lookup"><span data-stu-id="1decb-144">Create an ID list search</span></span>

<span data-ttu-id="1decb-145">A próxima etapa é criar uma nova pesquisa de lista de ID e enviar o arquivo CSV que você preparou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="1decb-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1decb-146">Você deve criar uma pesquisa de lista de ID não mais do que 2 dias após exportar os resultados ou relatório da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1decb-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="1decb-147">Se os resultados da pesquisa ou o relatório de onde foi exportado há mais de 2 dias, você deve exportar os resultados da pesquisa ou o relatório para gerar arquivos CSV atualizados.</span><span class="sxs-lookup"><span data-stu-id="1decb-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="1decb-148">Em seguida, você pode preparar um dos arquivos CSV atualizados e usá-lo para criar uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="1decb-149">Acesse <https://compliance.microsoft.com> e entre.</span><span class="sxs-lookup"><span data-stu-id="1decb-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="1decb-150">No painel de navegação esquerdo do Centro de Conformidade do Microsoft 365, clique em **Mostrar tudo** e, a seguir, clique em **Pesquisa de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="1decb-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="1decb-151">Na página **Pesquisa de** conteúdo, clique em Pesquisar por Lista **de IDs.**</span><span class="sxs-lookup"><span data-stu-id="1decb-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="1decb-152">No flyout **Search by ID List,** nomeia a pesquisa (e, opcionalmente, a descreverá) e clique em Procurar e selecione o arquivo CSV que você preparou na etapa anterior. </span><span class="sxs-lookup"><span data-stu-id="1decb-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="1decb-153">Microsoft 365 tenta validar o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1decb-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="1decb-154">Se a validação não tiver êxito, será exibida uma mensagem de erro que pode ajudá-lo a solucionar os erros de validação.</span><span class="sxs-lookup"><span data-stu-id="1decb-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="1decb-155">O arquivo CSV precisa ser validado com êxito para criar uma pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="1decb-156">Depois que o arquivo CSV for validado com êxito, clique em **Pesquisar** para criar a pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="1decb-157">Veja um exemplo da página de sobrevoo de uma pesquisa de lista de ID que mostra a consulta gerada e o número estimado de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1decb-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![Consulta de pesquisa para pesquisa de lista de ID](../media/SearchIDListFlyout.png)

    <span data-ttu-id="1decb-159">O número de itens estimados exibidos em estatísticas para a pesquisa de ID deve corresponder ao número de itens selecionados no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1decb-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="1decb-160">Visualizar ou exportar os itens retornados pela pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="1decb-161">Mais informações</span><span class="sxs-lookup"><span data-stu-id="1decb-161">More information</span></span>

<span data-ttu-id="1decb-162">Se você mover uma caixa de correio após a criação de uma pesquisa de lista de ID, a consulta para a pesquisa não retornará os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="1decb-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="1decb-163">Isso acontece porque a propriedade **DocumentId para** itens de caixa de correio é alterada quando uma caixa de correio é movida.</span><span class="sxs-lookup"><span data-stu-id="1decb-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="1decb-164">Na rara instância em que uma caixa de correio é movida após a criação de uma pesquisa de lista de ID, você deve criar uma nova pesquisa de Conteúdo (ou atualizar os resultados da pesquisa para uma pesquisa existente) e, em seguida, exportar os resultados da pesquisa ou relatório para gerar arquivos CSV atualizados que podem ser usados para criar uma nova pesquisa de lista de ID.</span><span class="sxs-lookup"><span data-stu-id="1decb-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
