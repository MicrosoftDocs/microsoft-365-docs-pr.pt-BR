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
description: Saiba como identificar um conjunto de documentos para revisão em uma investigação usando a ferramenta de pesquisa na descoberta eletrônica avançada.
ms.custom: seo-marvel-2020
ms.openlocfilehash: 9d8a88ddfc6bcb30f8678f39ad2bc4fbaf717ecc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034345"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="39da2-103">Coletar dados para uma ocorrência na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="39da2-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="39da2-104">Depois de identificar os responsáveis e as fontes de dados que são de interesse para o seu caso, é hora de identificar o conjunto de documentos para o qual se aprofundar.</span><span class="sxs-lookup"><span data-stu-id="39da2-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="39da2-105">Você pode usar a ferramenta de pesquisa na descoberta eletrônica avançada para identificar documentos relevantes do custodial e locais não custodial no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39da2-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="39da2-106">Após executar uma pesquisa, você pode exibir estatísticas sobre os itens recuperados, como os locais que tinham a maioria dos itens que corresponderam à consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="39da2-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="39da2-107">Você também pode visualizar um subconjunto dos resultados.</span><span class="sxs-lookup"><span data-stu-id="39da2-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="39da2-108">Ao identificar o conjunto de documentos que você deseja examinar mais, você pode adicionar os resultados da pesquisa a uma revisão definida como coletar e processar.</span><span class="sxs-lookup"><span data-stu-id="39da2-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="39da2-109">Criar uma pesquisa</span><span class="sxs-lookup"><span data-stu-id="39da2-109">Create a search</span></span>

<span data-ttu-id="39da2-110">Selecionar **nova pesquisa** na guia **pesquisas** iniciará um assistente que orienta você durante a criação de uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="39da2-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="39da2-111">Para obter informações detalhadas sobre como criar uma pesquisa, consulte [criar uma pesquisa para coletar dados](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="39da2-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="39da2-112">Após a criação de uma pesquisa, uma página de submenu com detalhes é exibida.</span><span class="sxs-lookup"><span data-stu-id="39da2-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="39da2-113">Os botões de **estatísticas** e **Visualização** estão inicialmente indisponíveis porque a pesquisa ainda não foi concluída.</span><span class="sxs-lookup"><span data-stu-id="39da2-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="39da2-114">Você pode acompanhar o progresso da pesquisa na guia **pesquisas** .</span><span class="sxs-lookup"><span data-stu-id="39da2-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="39da2-115">Exibir resultados e estatísticas de pesquisa</span><span class="sxs-lookup"><span data-stu-id="39da2-115">View search results and statistics</span></span>

<span data-ttu-id="39da2-116">Há dois componentes de uma pesquisa de conteúdo: estatísticas (estimativas) e visualização.</span><span class="sxs-lookup"><span data-stu-id="39da2-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="39da2-117">À medida que cada um desses componentes for concluído, você verá o status exibido nas colunas correspondentes na guia **pesquisas** mudar de **enviado** para **em andamento** para **concluído**.</span><span class="sxs-lookup"><span data-stu-id="39da2-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="39da2-118">Depois que a estimativa de pesquisa for concluída, selecione a pesquisa para exibir a página de submenu, que exibirá algumas estatísticas de alto nível sobre os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="39da2-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="39da2-119">Neste ponto, o botão **estatísticas** estará ativo.</span><span class="sxs-lookup"><span data-stu-id="39da2-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="39da2-120">Você pode selecioná-lo para ver as estatísticas de pesquisa, como:</span><span class="sxs-lookup"><span data-stu-id="39da2-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="39da2-121">Resumo</span><span class="sxs-lookup"><span data-stu-id="39da2-121">Summary</span></span>
- <span data-ttu-id="39da2-122">Principais locais</span><span class="sxs-lookup"><span data-stu-id="39da2-122">Top locations</span></span>
- <span data-ttu-id="39da2-123">Consultas</span><span class="sxs-lookup"><span data-stu-id="39da2-123">Queries</span></span>

<span data-ttu-id="39da2-124">Para obter mais informações sobre estatísticas de pesquisa, confira [Estatísticas de pesquisa](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="39da2-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="39da2-125">Após a conclusão da visualização, o botão **Visualizar** estará ativo.</span><span class="sxs-lookup"><span data-stu-id="39da2-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="39da2-126">Selecione-o para visualizar um subconjunto de amostra dos resultados.</span><span class="sxs-lookup"><span data-stu-id="39da2-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="39da2-127">Adicionar os resultados da pesquisa a um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="39da2-127">Add search results to a review set</span></span>

<span data-ttu-id="39da2-128">Quando estiver pronto para coletar e processar os resultados inteiros de uma pesquisa, você poderá fazê-lo adicionando-o a um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="39da2-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="39da2-129">Para obter detalhes, consulte [Adicionar dados a um conjunto de revisão](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="39da2-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="39da2-130">Adicionar dados que não sejam da Microsoft 365 a um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="39da2-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="39da2-131">Como parte do processo de coleta para uma ocorrência, você também pode adicionar dados que não sejam do Office 365 a uma revisão de análise e análise e análise em conjunto com os dados do Office 365 que você coletou usando a ferramenta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="39da2-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="39da2-132">Ao adicionar um não-Office 365, você precisa associá-lo a um funcionário específico no caso.</span><span class="sxs-lookup"><span data-stu-id="39da2-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="39da2-133">Para obter mais informações, consulte [carregar dados não-Microsoft 365 em um conjunto de revisão](load-non-Office-365-data-into-a-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="39da2-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
