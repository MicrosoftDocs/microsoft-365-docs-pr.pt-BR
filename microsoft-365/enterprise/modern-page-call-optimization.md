---
title: Otimizar chamadas de página em páginas do site de publicação clássico e moderno do SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Saiba como otimizar as páginas do site de publicação clássico e moderno no SharePoint Online, limitando o número de chamadas para pontos de extremidade de serviço do SharePoint Online.
ms.openlocfilehash: cab0f6a020bd1148a0e852b5a393a6ad907f9771
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921613"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="fcede-103">Otimizar chamadas de página em páginas do site de publicação clássico e moderno do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fcede-103">Optimize page calls in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="fcede-104">Os sites de publicação clássico e moderno do SharePoint Online contêm links que carregam dados de (ou fazem chamadas) recursos do SharePoint e CDNs.</span><span class="sxs-lookup"><span data-stu-id="fcede-104">Both SharePoint Online modern and classic publishing sites contain links that load data from (or make calls to) SharePoint features and CDNs.</span></span> <span data-ttu-id="fcede-105">Quanto mais chamadas forem feitas por uma página, maior será o tempo de carregamento da página.</span><span class="sxs-lookup"><span data-stu-id="fcede-105">The more calls made by a page, the longer the page takes to load.</span></span> <span data-ttu-id="fcede-106">Isso é conhecido como **latência percebida pelo usuário final** ou **EUPL**.</span><span class="sxs-lookup"><span data-stu-id="fcede-106">This is known as **end user perceived latency** or **EUPL**.</span></span>

<span data-ttu-id="fcede-107">Este artigo vai ajudá-lo a entender como determinar o número e o impacto das chamadas para pontos de extremidade externos nas páginas do site de publicação clássico e moderno e como limitar o efeito na latência percebida pelo usuário final.</span><span class="sxs-lookup"><span data-stu-id="fcede-107">This article will help you understand how to determine the number and impact of calls to external endpoints from your modern and classic publishing site pages and how to limit their effect on end user perceived latency.</span></span>

>[!NOTE]
><span data-ttu-id="fcede-108">Para obter mais informações sobre o desempenho dos portais modernos do SharePoint Online, confira [Desempenho na experiência moderna do SharePoint](/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="fcede-108">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a><span data-ttu-id="fcede-109">Usar a ferramenta Diagnóstico de Página do SharePoint para analisar as chamadas da página</span><span class="sxs-lookup"><span data-stu-id="fcede-109">Use the Page Diagnostics for SharePoint tool to analyze page calls</span></span>

<span data-ttu-id="fcede-110">A ferramenta Diagnóstico de Página para SharePoint é uma extensão do navegador para os novos navegadores Microsoft Edge (https://www.microsoft.com/edge) e Chrome que analisam o portal moderno do SharePoint Online e as páginas clássicas de site de publicação.</span><span class="sxs-lookup"><span data-stu-id="fcede-110">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="fcede-111">A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho.</span><span class="sxs-lookup"><span data-stu-id="fcede-111">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="fcede-112">Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="fcede-112">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="fcede-113">A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fcede-113">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="fcede-114">Ao analisar uma página de site do SharePoint com a ferramenta Diagnóstico de Página para SharePoint, você pode ver informações sobre as chamadas externas nos resultado das **Solicitações para o SharePoint** no painel de _Testes de Diagnóstico_.</span><span class="sxs-lookup"><span data-stu-id="fcede-114">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about external calls in the **Requests to SharePoint** result in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="fcede-115">A linha aparecerá em verde se a página do site contiver menos que o número da linha de base de chamadas e em vermelho se a página ultrapassar o número da linha de base.</span><span class="sxs-lookup"><span data-stu-id="fcede-115">The line will appear in green if the site page contains fewer than the baseline number of calls, and red if the page exceeds the baseline number.</span></span> <span data-ttu-id="fcede-116">O número da linha de base é diferente para as páginas clássicas e modernas porque as páginas do site clássico usam HTTP1.1 e as modernas usam HTTP2.0:</span><span class="sxs-lookup"><span data-stu-id="fcede-116">The baseline number is different for modern and classic pages because classic site pages use HTTP1.1 and modern pages use HTTP2.0:</span></span>

- <span data-ttu-id="fcede-117">As páginas de site moderno não devem conter mais de **25** chamadas</span><span class="sxs-lookup"><span data-stu-id="fcede-117">Modern site pages should contain no more than **25** calls</span></span>
- <span data-ttu-id="fcede-118">As páginas de publicação clássicas não devem conter mais de **6** chamadas</span><span class="sxs-lookup"><span data-stu-id="fcede-118">Classic publishing pages should contain no more than **6** calls</span></span>

<span data-ttu-id="fcede-119">Os resultados possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="fcede-119">Possible results include:</span></span>

- <span data-ttu-id="fcede-120">**Atenção necessária** (vermelho): a página ultrapassa o número da linha de base de chamadas</span><span class="sxs-lookup"><span data-stu-id="fcede-120">**Attention required** (red): The page exceeds the baseline number of calls</span></span>
- <span data-ttu-id="fcede-121">**Nenhuma ação necessária** (verde): a página contém menos do que o número da linha de base de chamadas</span><span class="sxs-lookup"><span data-stu-id="fcede-121">**No action required** (green): The page contains fewer than the baseline number of calls</span></span>

<span data-ttu-id="fcede-122">Se o resultado das **Solicitações para o SharePoint** aparecer na seção **Atenção necessária**, você poderá clicar no resultado para obter detalhes, incluindo o número total de chamadas na página e uma lista de URLs.</span><span class="sxs-lookup"><span data-stu-id="fcede-122">If the **Requests to SharePoint** result appears in the **Attention required** section, you can click the result for details, including the total number of calls on the page and a list of the URLs.</span></span>

![Solicitações para resultados do SharePoint](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a><span data-ttu-id="fcede-124">Solucionar problemas de desempenho relacionados a muitas chamadas em uma página</span><span class="sxs-lookup"><span data-stu-id="fcede-124">Remediate performance issues related to too many calls on a page</span></span>

<span data-ttu-id="fcede-125">Se uma página contiver muitas chamadas, você poderá usar a lista de URLs no resultado das **Solicitações do SharePoint** para determinar se há chamadas repetidas, chamadas que devem ser em lotes ou chamadas que retornam dados que devem ser armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="fcede-125">If a page contains too many calls, you can use the list of URLs in the **Requests to Sharepoint** results to determine whether there are any repeated calls, calls that should be batched, or calls that return data that should be cached.</span></span>

<span data-ttu-id="fcede-126">As **chamadas de REST em lote** podem ajudar a reduzir a sobrecarga de desempenho.</span><span class="sxs-lookup"><span data-stu-id="fcede-126">**Batching REST calls** can help to reduce performance overhead.</span></span> <span data-ttu-id="fcede-127">Para obter mais informações sobre a chamada da API em lote, confira [Fazer solicitações em lote com as APIs REST](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="fcede-127">For more information about API call batching, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

<span data-ttu-id="fcede-128">**Usar um cache** para armazenar os resultados de uma chamada de API pode melhorar o desempenho de uma solicitação ativa, permitindo que o cliente use os dados armazenados em cache, em vez de fazer uma chamada adicional para cada carregamento de página subsequente.</span><span class="sxs-lookup"><span data-stu-id="fcede-128">**Using a cache** to store the results of an API call can improve the performance of a warm request by allowing the client to use the cached data instead of making an additional call for each subsequent page load.</span></span> <span data-ttu-id="fcede-129">Há várias maneiras de abordar essa solução dependendo da necessidade comercial.</span><span class="sxs-lookup"><span data-stu-id="fcede-129">There are multiple ways to approach this solution depending on the business requirement.</span></span> <span data-ttu-id="fcede-130">Geralmente, se os dados forem os mesmos para todos os usuários, o uso de um serviço de armazenamento hierárquico, como o [cache do _Azure Redis_](https://azure.microsoft.com/services/cache/), é uma ótima opção para reduzir significativamente o tráfego da API em um site, pois os usuários podem solicite os dados do serviço de cache, em vez de diretamente do SPO.</span><span class="sxs-lookup"><span data-stu-id="fcede-130">Typically if the data will be the same for all users, using a middle-tier caching service like [_Azure Redis_ cache](https://azure.microsoft.com/services/cache/) is a great option to significantly reduce API traffic against a site, as the users would request the data from the caching service instead of directly from SPO.</span></span> <span data-ttu-id="fcede-131">As únicas chamadas SPO necessárias seriam para atualizar o cache da camada intermediária.</span><span class="sxs-lookup"><span data-stu-id="fcede-131">The only SPO calls needed would be to refresh the middle-tier's cache.</span></span> <span data-ttu-id="fcede-132">Se os dados flutuarem com base no usuário individual, talvez seja melhor implementar um cache no lado do cliente, como LocalStorage ou até mesmo um cookie.</span><span class="sxs-lookup"><span data-stu-id="fcede-132">If the data will fluctuate on an individual user basis, it may be best to implement a client side cache, like LocalStorage or even a Cookie.</span></span> <span data-ttu-id="fcede-133">Isso ainda reduzirá os volumes de chamadas, eliminando as solicitações subsequentes feitas pelo mesmo usuário na duração do cache, mas será menos eficiente do que um serviço de cache dedicado.</span><span class="sxs-lookup"><span data-stu-id="fcede-133">This will still reduce call volumes by eliminating subsequent requests made by the same user for the cache duration, but will be less efficient than a dedicated caching service.</span></span> <span data-ttu-id="fcede-134">O PnP permite que você use o LocalStorage com um pequeno desenvolvimento adicional necessário.</span><span class="sxs-lookup"><span data-stu-id="fcede-134">PnP allows you to use LocalStorage with little additional development required.</span></span>

<span data-ttu-id="fcede-135">Antes de fazer as revisões das páginas para corrigir problemas de desempenho, anote o tempo de carregamento da página nos resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="fcede-135">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="fcede-136">Execute a ferramenta novamente após a revisão para ver se o novo resultado está dentro do padrão da linha de base e verifique o tempo de carregamento da nova página para ver se melhorou.</span><span class="sxs-lookup"><span data-stu-id="fcede-136">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Resultados do tempo de carregamento da página](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="fcede-138">O tempo de carregamento da página pode variar de acordo com vários fatores, como a carga da rede, hora do dia e outras condições transitórias.</span><span class="sxs-lookup"><span data-stu-id="fcede-138">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="fcede-139">Você deve testar o tempo de carregamento da página algumas vezes antes e depois de fazer as alterações para ajudá-lo a calcular uma média dos resultados.</span><span class="sxs-lookup"><span data-stu-id="fcede-139">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fcede-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fcede-140">Related topics</span></span>

[<span data-ttu-id="fcede-141">Ajustar o desempenho do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fcede-141">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="fcede-142">Ajustar o desempenho do Office 365</span><span class="sxs-lookup"><span data-stu-id="fcede-142">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="fcede-143">Desempenho na experiência moderna do SharePoint</span><span class="sxs-lookup"><span data-stu-id="fcede-143">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="fcede-144">Redes de distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="fcede-144">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="fcede-145">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fcede-145">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)