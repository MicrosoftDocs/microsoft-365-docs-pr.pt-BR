---
title: Visualizar os resultados de uma pesquisa de Descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Visualizar um exemplo dos resultados retornados por uma Pesquisa de conteúdo ou uma pesquisa de Descoberta eletrônica Principal no Centro de Conformidade do Microsoft 365.
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538575"
---
# <a name="preview-ediscovery-search-results"></a><span data-ttu-id="6f3d2-103">Visualização de resultados de pesquisa da Descoberta Eletrônica</span><span class="sxs-lookup"><span data-stu-id="6f3d2-103">Preview eDiscovery search results</span></span>

<span data-ttu-id="6f3d2-104">Depois de executar uma pesquisa de Conteúdo ou uma pesquisa associada a um caso de Descoberta eletrônica principal, você pode visualizar uma amostra dos resultados retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-104">After you run a Content search or a search associated with a Core eDiscovery case, you can preview a sample of the results returned by the search.</span></span> <span data-ttu-id="6f3d2-105">A visualização de itens retornados pela consulta de pesquisa pode ajudá-lo a determinar se a pesquisa está retornando os resultados que você espera ou se você precisa alterar a consulta de pesquisa e realizar a pesquisa outra vez.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-105">Previewing items returned by the search query can help you determine if the search is returning the results you hope for or if you need to change the search query and rerun the search.</span></span>

<span data-ttu-id="6f3d2-106">Para visualizar um exemplo de resultados retornados por uma pesquisa:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-106">To preview a sample of results returned by a search:</span></span>

1. <span data-ttu-id="6f3d2-107">No Centro de Conformidade do Microsoft 365, vá para a página de Pesquisa de conteúdo ou um caso de Descoberta eletrônica principal.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-107">In the Microsoft 365 compliance center, go to the Content search page or a Core eDiscovery case.</span></span>

2. <span data-ttu-id="6f3d2-108">Selecione a pesquisa para exibir a página de sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-108">Select search to display the flyout page.</span></span>

3. <span data-ttu-id="6f3d2-109">Na parte inferior da página de sobrevoo, clique em **Revisar exemplo**.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-109">On the bottom of the flyout page, click **Review sample**.</span></span>

   ![Clique em Revisar exemplo na página flyout para exibir os resultados](../media/PreviewSearchResults1.png)

   <span data-ttu-id="6f3d2-111">É exibida uma página contendo um exemplo dos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-111">A page is displayed containing a sample of the search results.</span></span>

4. <span data-ttu-id="6f3d2-112">Selecione um item para exibir seu conteúdo no painel de leitura.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-112">Select an item to view its contents in the reading pane.</span></span>

   ![Exibir itens no painel de leitura](../media/PreviewSearchResults2.png)

   <span data-ttu-id="6f3d2-114">Na captura de tela anterior, observe que as palavras-chave da consulta de pesquisa são realçadas quando você visualiza itens.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-114">In the previous screenshot, notice that keywords from the search query are highlighted when you preview items.</span></span>

## <a name="how-the-search-result-samples-are-selected"></a><span data-ttu-id="6f3d2-115">Como são selecionados os exemplos dos resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="6f3d2-115">How the search result samples are selected</span></span>

<span data-ttu-id="6f3d2-116">No máximo 1.000 itens selecionados aleatoriamente estão disponíveis para visualização.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-116">A maximum of 1,000 randomly selected items are available to preview.</span></span> <span data-ttu-id="6f3d2-117">Além de serem selecionados aleatoriamente, os itens disponíveis para visualização também devem atender aos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-117">In addition to being randomly selected, items available for preview must also meet the following criteria:</span></span>

- <span data-ttu-id="6f3d2-118">É possível visualizar no máximo 100 itens de um único local de conteúdo (uma caixa de correio ou um site).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-118">A maximum of 100 items from a single content location (a mailbox or a site) can be previewed.</span></span> <span data-ttu-id="6f3d2-119">Isso significa que é possível que menos de 1.000 itens possam estar disponíveis para visualização.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-119">This means that it's possible that less than 1,000 items might be available for preview.</span></span> <span data-ttu-id="6f3d2-120">Por exemplo, se você pesquisar quatro caixas de correio e a pesquisa retornar 1.500 itens estimados, apenas 400 estarão disponíveis para visualização porque somente 100 itens de cada caixa de correio podem ser visualizados.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-120">For example, if you search four mailboxes and the search returns 1,500 estimated items, only 400 will be available for preview because only 100 items from each mailbox can be previewed.</span></span>

- <span data-ttu-id="6f3d2-121">Para itens de caixa de correio, apenas as mensagens de email estão disponíveis para visualização.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-121">For mailbox items, only email messages are available to preview.</span></span> <span data-ttu-id="6f3d2-122">Itens como tarefas, itens de calendário e contatos não podem ser visualizados.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-122">Items like tasks, calendar items, and contacts can't be previewed.</span></span>

- <span data-ttu-id="6f3d2-123">Para itens de site, somente os documentos estão disponíveis para visualização.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-123">For site items, only documents are available to preview.</span></span> <span data-ttu-id="6f3d2-124">Itens como pastas, listas ou anexos de listas não podem ser visualizados.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-124">Items like folders, lists, or list attachments can't be previewed.</span></span>

## <a name="file-types-supported-when-previewing-search-results"></a><span data-ttu-id="6f3d2-125">Tipos de arquivos com suporte durante a visualização de resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="6f3d2-125">File types supported when previewing search results</span></span>

<span data-ttu-id="6f3d2-126">É possível visualizar os tipos de arquivo com suporte no painel de visualização.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-126">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="6f3d2-127">Se não há suporte para um tipo de arquivo, você precisa baixar uma cópia do arquivo no computador local (clicando em **Baixar o item original**).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-127">If a file type isn't supported, you have to download a copy of the file to your local computer (by clicking **Download original item**).</span></span> <span data-ttu-id="6f3d2-128">Para páginas da Web .aspx, a URL da página está incluída, mas pode ser que não haja permissões para acessar a página.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-128">For .aspx Web pages, the URL for the page is included though you may not have permissions to access the page.</span></span> <span data-ttu-id="6f3d2-129">Itens não indexados não estão disponíveis para visualização.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-129">Unindexed items aren't available for previewing.</span></span>

<span data-ttu-id="6f3d2-130">Os seguintes tipos de arquivo têm suporte e podem ser visualizados no painel de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-130">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="6f3d2-131">.txt, .html, .mhtml</span><span class="sxs-lookup"><span data-stu-id="6f3d2-131">.txt, .html, .mhtml</span></span>

- <span data-ttu-id="6f3d2-132">.eml</span><span class="sxs-lookup"><span data-stu-id="6f3d2-132">.eml</span></span>

- <span data-ttu-id="6f3d2-133">.doc, .docx, .docm</span><span class="sxs-lookup"><span data-stu-id="6f3d2-133">.doc, .docx, .docm</span></span>

- <span data-ttu-id="6f3d2-134">.pptm, .pptx</span><span class="sxs-lookup"><span data-stu-id="6f3d2-134">.pptm, .pptx</span></span>

- <span data-ttu-id="6f3d2-135">.pdf</span><span class="sxs-lookup"><span data-stu-id="6f3d2-135">.pdf</span></span>

<span data-ttu-id="6f3d2-136">Além disso, os seguintes tipos de contêiner de arquivos possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-136">Also, the following file container types are supported.</span></span> <span data-ttu-id="6f3d2-137">Você pode exibir a lista de arquivos no contêiner no painel de visualização.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-137">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="6f3d2-138">.zip</span><span class="sxs-lookup"><span data-stu-id="6f3d2-138">.zip</span></span>

- <span data-ttu-id="6f3d2-139">.gzip</span><span class="sxs-lookup"><span data-stu-id="6f3d2-139">.gzip</span></span>