---
title: Coletar dados para uma ocorrência na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: esclee
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
ms.openlocfilehash: a6b86d9f86edc427e10c02a99e3cda3e5e79db66
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595848"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="01f67-102">Coletar dados para uma ocorrência na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="01f67-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="01f67-103">Depois de identificar os responsáveis e as fontes de dados que são de interesse para o seu caso, é hora de identificar o conjunto de documentos para o qual se aprofundar.</span><span class="sxs-lookup"><span data-stu-id="01f67-103">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="01f67-104">Você pode usar a ferramenta de pesquisa na descoberta eletrônica avançada para identificá-las de locais custodial e não custodial no Office 365.</span><span class="sxs-lookup"><span data-stu-id="01f67-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="01f67-105">Após executar uma pesquisa, você pode exibir estatísticas sobre os itens recuperados, como os locais que tinham a maioria dos itens que corresponderam à consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="01f67-105">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="01f67-106">Você também pode visualizar um subconjunto dos resultados.</span><span class="sxs-lookup"><span data-stu-id="01f67-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="01f67-107">Ao identificar o conjunto de documentos que você deseja examinar mais, você pode adicionar os resultados da pesquisa a uma revisão definida como coletar e processar.</span><span class="sxs-lookup"><span data-stu-id="01f67-107">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="01f67-108">Criar uma pesquisa</span><span class="sxs-lookup"><span data-stu-id="01f67-108">Create a search</span></span>

<span data-ttu-id="01f67-109">Selecionar **nova pesquisa** na guia **pesquisas** iniciará um assistente que orienta você durante a criação de uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="01f67-109">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="01f67-110">Para obter informações detalhadas sobre como criar uma pesquisa, consulte [criar uma pesquisa para coletar dados](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="01f67-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="01f67-111">Após a criação de uma pesquisa, uma página de submenu com detalhes é exibida.</span><span class="sxs-lookup"><span data-stu-id="01f67-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="01f67-112">Os botões de **estatísticas** e **Visualização** estão inicialmente indisponíveis porque a pesquisa ainda não foi concluída.</span><span class="sxs-lookup"><span data-stu-id="01f67-112">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="01f67-113">Você pode acompanhar o progresso da pesquisa na guia **pesquisas** .</span><span class="sxs-lookup"><span data-stu-id="01f67-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="01f67-114">Exibir resultados e estatísticas de pesquisa</span><span class="sxs-lookup"><span data-stu-id="01f67-114">View search results and statistics</span></span>

<span data-ttu-id="01f67-115">Há dois componentes de uma pesquisa de conteúdo: estatísticas (estimativas) e visualização.</span><span class="sxs-lookup"><span data-stu-id="01f67-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="01f67-116">À medida que cada um desses componentes for concluído, você verá o status exibido nas colunas correspondentes na guia **pesquisas** mudar de **enviado** para **em andamento** para **concluído**.</span><span class="sxs-lookup"><span data-stu-id="01f67-116">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="01f67-117">Depois que a estimativa de pesquisa for concluída, selecione a pesquisa para exibir a página de submenu, que exibirá algumas estatísticas de alto nível sobre os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="01f67-117">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="01f67-118">Neste ponto, o botão **estatísticas** estará ativo.</span><span class="sxs-lookup"><span data-stu-id="01f67-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="01f67-119">Você pode selecioná-lo para ver as estatísticas de pesquisa, como:</span><span class="sxs-lookup"><span data-stu-id="01f67-119">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="01f67-120">Resumo</span><span class="sxs-lookup"><span data-stu-id="01f67-120">Summary</span></span>
- <span data-ttu-id="01f67-121">Principais locais</span><span class="sxs-lookup"><span data-stu-id="01f67-121">Top locations</span></span>
- <span data-ttu-id="01f67-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="01f67-122">Queries</span></span>

<span data-ttu-id="01f67-123">Para obter mais informações sobre estatísticas de pesquisa, confira [Estatísticas de pesquisa](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="01f67-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="01f67-124">Após a conclusão da visualização, o botão **Visualizar** estará ativo.</span><span class="sxs-lookup"><span data-stu-id="01f67-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="01f67-125">Selecione-o para visualizar um subconjunto de amostra dos resultados.</span><span class="sxs-lookup"><span data-stu-id="01f67-125">Select it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="01f67-126">Adicionando resultados de pesquisa a um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="01f67-126">Adding search results to a review set</span></span>

<span data-ttu-id="01f67-127">Quando estiver pronto para coletar e processar os resultados inteiros de uma pesquisa, você poderá fazê-lo adicionando-o a um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="01f67-127">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="01f67-128">Para obter detalhes, consulte [Adicionar dados a um conjunto de revisão](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="01f67-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>
