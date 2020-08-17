---
title: Otimize extensões personalizadas nas páginas do site modernas do SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
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
description: Aprenda como otimizar o desempenho de extensões personalizadas nas páginas do site modernas do SharePoint Online.
ms.openlocfilehash: 3f9474bcfa3266742d2e01af2f1df6eb5c0d017c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687312"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="2cb2a-103">Otimizar o desempenho da extensão personalizada nas páginas do site modernas do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2cb2a-103">Optimize custom extension performance in SharePoint Online modern site pages</span></span>

<span data-ttu-id="2cb2a-104">Este artigo ajudará você a entender como determinar de que modo as extensões personalizadas afetam a latência percebida pelo usuário e como corrigir problemas comuns.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-104">This article will help you understand how to determine how custom extensions affect user perceived latency, and how to remediate common issues.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a><span data-ttu-id="2cb2a-105">Usar a ferramenta Diagnóstico de Página para SharePoint para analisar as extensões personalizadas</span><span class="sxs-lookup"><span data-stu-id="2cb2a-105">Use the Page Diagnostics for SharePoint tool to analyze custom extensions</span></span>

<span data-ttu-id="2cb2a-106">A ferramenta Diagnóstico de Página para SharePoint é uma extensão do navegador para os novos navegadores Microsoft Edge (https://www.microsoft.com/edge) e Chrome que analisam o portal moderno do SharePoint Online e as páginas clássicas do site de publicação.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-106">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="2cb2a-107">A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-107">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="2cb2a-108">Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="2cb2a-108">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="2cb2a-109">A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-109">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="2cb2a-110">Ao analisar uma página de site do SharePoint com a ferramenta Diagnóstico de Página para SharePoint, você pode visualizar informações sobre extensões personalizadas que excedem a métrica de linha de base em**As extensões estão afetando o tempo de carregamento** e/ou em **Excesso de extensões usadas** resultam no painel _Testes de diagnóstico_</span><span class="sxs-lookup"><span data-stu-id="2cb2a-110">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about custom extensions that exceed the baseline metric in the **Extensions are impacting load time** and/or the **Too many extensions used** result in the _Diagnostic tests_ pane</span></span> 

<span data-ttu-id="2cb2a-111">Os resultados possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="2cb2a-111">Possible results include:</span></span>

- <span data-ttu-id="2cb2a-112">**Atenção necessária** (vermelho): Qualquer extensão _personalizada_ que leva mais do que **um** segundo para carregar.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-112">**Attention required** (red): Any _custom_ extension that takes longer than **one** second to load.</span></span> <span data-ttu-id="2cb2a-113">O tempo total de carregamento, conforme exibido nos resultados de teste, é dividido por carregamento do módulo, carga lenta, inicialização e renderização.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-113">Total load time as displayed in test results is broken down by module load and init.</span></span> <span data-ttu-id="2cb2a-114">Além disso, se houver muitas extensões em uma página, elas poderão afetar o tempo de carregamento da página e isso será destacado se **sete** ou mais extensões forem usadas na página.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-114">Additionally, if there are too many extensions on a page they can impact the page load time and this will be highlighted if **seven** or more extensions are used on the page.</span></span>
- <span data-ttu-id="2cb2a-115">**Oportunidades de melhoria** (amarelo) Se **cinco** ou mais extensões forem usadas, elas serão destacadas nesta seção como um aviso até que sete ou mais sejam usadas, e então serão destacadas como Atenção Necessária.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-115">**Improvement Opportunities** (yellow) If **five** or more extensions are used they will be highlighted in this section as a warning until seven or more are used which will then be highlighted as Attention Required.</span></span>
- <span data-ttu-id="2cb2a-116">**Nenhuma ação é necessária** (verde): Nenhuma extensão está levando mais de um segundo para carregar.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-116">**No action required** (green): No extension is taking longer than one second to load.</span></span>

<span data-ttu-id="2cb2a-117">Se uma extensão estiver afetando o tempo de carregamento da página ou se houver muitas extensões na página, o resultado será exibido na seção **Atenção necessária** dos resultados.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-117">If an extension is impacting page load time or there are too many extsnions on the page, the result appears in the **Attention required** section of the results.</span></span> <span data-ttu-id="2cb2a-118">Clique no resultado para ver os detalhes sobre qual extensão está carregando lentamente ou se muitas extensões foram destacadas.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-118">Click the result to see details about which extension is loading slowly or too many extensions has been highlighted.</span></span> <span data-ttu-id="2cb2a-119">Futuras atualizações da ferramenta Diagnóstico de Página para SharePoint podem incluir atualizações de regras de análise, portanto, garanta que você sempre tenha a versão mais recente da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-119">Future updates to the Page Diagnostics for SharePoint tool may include updates to analysis rules, so please ensure you always have the latest version of the tool.</span></span>

![Resultados do tempo de carregamento da página](../media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

<span data-ttu-id="2cb2a-121">As informações disponíveis nos resultados incluem:</span><span class="sxs-lookup"><span data-stu-id="2cb2a-121">Information available in the results includes:</span></span>

- <span data-ttu-id="2cb2a-122">**Nome e ID** mostram informações de identificação que podem ajudá-lo a encontrar a extensão na página</span><span class="sxs-lookup"><span data-stu-id="2cb2a-122">**Name and ID** shows identifying information that can help you find the extension on the page</span></span>
- <span data-ttu-id="2cb2a-123">**Total** mostra o tempo total para a extensão inicializar e carregar</span><span class="sxs-lookup"><span data-stu-id="2cb2a-123">**Total** shows the total time for the extension to initialize and load</span></span>
- <span data-ttu-id="2cb2a-124">**Carregamento do Módulo** mostra o tempo necessário para buscar e carregar a extensão</span><span class="sxs-lookup"><span data-stu-id="2cb2a-124">**Module Load** shows the time taken to fetch and load the extension</span></span>
- <span data-ttu-id="2cb2a-125">**Inicialização** mostra o tempo necessário para a extensão inicializar</span><span class="sxs-lookup"><span data-stu-id="2cb2a-125">**Init** shows the time taken for the extension to initialize</span></span>

<span data-ttu-id="2cb2a-126">Essas informações são fornecidas para ajudar designers e desenvolvedores a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-126">This information is provided to help designers and developers troubleshoot issues.</span></span> <span data-ttu-id="2cb2a-127">Elas devem ser encaminhadas à equipe de design e desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-127">This information should be provided to your design and development team.</span></span>

## <a name="overview-of-extensions"></a><span data-ttu-id="2cb2a-128">Visão geral das extensões</span><span class="sxs-lookup"><span data-stu-id="2cb2a-128">Overview of extensions</span></span>

<span data-ttu-id="2cb2a-129">As Extensões da Estrutura do SharePoint (SPFx) podem ser usadas para estender a experiência do usuário do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-129">SharePoint Framework (SPFx) Extensions can be used to extend the SharePoint user experience.</span></span> <span data-ttu-id="2cb2a-130">Com as Extensões da Estrutura do SharePoint, é possível personalizar mais facetas da experiência do SharePoint, incluindo modos de exibição de dados de lista, barras de ferramentas e áreas de notificação.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-130">With SharePoint Framework Extensions, you can customize more facets of the SharePoint experience, including notification areas, toolbars, and list data views.</span></span>

<span data-ttu-id="2cb2a-131">As extensões podem ter uma influência ruim no desempenho de uma página do SharePoint, pois também são necessários recursos da CPU e da rede para o trabalho necessário.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-131">Extensions can have a bad influence on the performance of a SharePoint page as it also takes CPU and network resources to do required work.</span></span>

<span data-ttu-id="2cb2a-132">Há quatro tipos de extensões:</span><span class="sxs-lookup"><span data-stu-id="2cb2a-132">There are four types of extensions:</span></span>

- <span data-ttu-id="2cb2a-133">**Personalizadores de Aplicativos** adicionam scripts à página e acessam os espaços reservados de elementos HTML conhecidos e os estendem com renderizações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-133">**Application Customizers** adds scripts to the page, and accesses well-known HTML element placeholders and extends them with custom renderings.</span></span>
- <span data-ttu-id="2cb2a-134">**Personalizadores de campo** fornecem visualizações modificadas aos dados dos campos em uma lista.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-134">**Field Customizers** provides modified views to data for fields within a list.</span></span>
- <span data-ttu-id="2cb2a-135">**Conjuntos de Comandos** estendem as superfícies de comando do SharePoint para adicionar novas ações e fornecem código do lado do cliente que você pode usar para implementar comportamentos.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-135">**Command Sets** extend the SharePoint command surfaces to add new actions, and provides client-side code that you can use to implement behaviors.</span></span>
- <span data-ttu-id="2cb2a-136">**Modificador de Consulta de Pesquisa (somente visualização)** são invocados antes de executar a consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-136">**Search Query Modifier (preview only)** are invoked just before the search query is executed.</span></span>

## <a name="remediate-extension-performance-issues"></a><span data-ttu-id="2cb2a-137">Corrigir problemas de desempenho da extensão</span><span class="sxs-lookup"><span data-stu-id="2cb2a-137">Remediate extension performance issues</span></span>

<span data-ttu-id="2cb2a-138">Siga as orientações desta seção para identificar e corrigir problemas de desempenho com extensões listadas nos resultados **As extensões estão afetando o tempo de carregamento da página**.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-138">Follow the guidance in this section to identify and remediate performance issues with extensions listed in the **Extensions are impacting page load time** results.</span></span>

>[!NOTE]
><span data-ttu-id="2cb2a-139">Os personalizadores de aplicativos podem ser executados no estágio inicial durante o ciclo de vida de uma página e podem influenciar o desempenho de outras extensões na página.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-139">Application customizers may be executed in the early stage during the lifecycle of a page and it may influence the performance of other extensions on the page.</span></span>

<span data-ttu-id="2cb2a-140">Os resultados da auditoria na Ferramenta de Diagnóstico da Página exibirão dois estágios de execução de uma extensão para ajudar a identificar o potencial impacto no desempenho.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-140">The audit results in the Page Diagnostic Tool will display two stages of executing an extension in order to help identify the potential performance impact.</span></span>

- <span data-ttu-id="2cb2a-141">**Carregamento do módulo** é o tempo que leva para carregar a extensão, que é impactado pelo tamanho de uma extensão, portanto, é uma boa ideia agrupar apenas as bibliotecas necessárias na extensão e também escolher bibliotecas mais leves.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-141">**Module load** is how long it takes to load the extension, which is impacted by the size of an extension so it is a good idea to only bundle the necessary libraries in the extension and to also choose lighter libraries.</span></span>
- <span data-ttu-id="2cb2a-142">**Inicialização** é o tempo de inicialização da extensão e os desenvolvedores de extensão devem considerar se a extensão está executando um trabalho desnecessário ou executando muitos comandos durante o estágio de inicialização.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-142">**Init** is the initialization time of the extension and extension developers should consider whether the extension is doing unnecessary work or executing too many commands during the initializing stage.</span></span>

<span data-ttu-id="2cb2a-143">Os autores da página também podem usar o resultado da auditoria para verificar se uma página possui muitas extensões, pois muitas delas impactarão negativamente o desempenho de uma página.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-143">Page authors can also use the audit result to see whether a page has too many extensions as too many extensions will negatively impact the performance of a page.</span></span>

- <span data-ttu-id="2cb2a-144">**Tamanho da extensão e dependências**</span><span class="sxs-lookup"><span data-stu-id="2cb2a-144">**Extension size and dependencies**</span></span>
  - <span data-ttu-id="2cb2a-145">É necessário usar a CDN do Office 365 para baixar o recurso estático ideal.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-145">Use of the Office 365 CDN is required for optimal static resource download.</span></span> <span data-ttu-id="2cb2a-146">As origens da CDN pública são preferíveis para arquivos _js/css_.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-146">Public CDN origins are preferable for _js/css_ files.</span></span> <span data-ttu-id="2cb2a-147">Para saber mais sobre como usar a CDN do Office 365, confira [Usar a CDN (Rede de Distribuição de Conteúdo) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="2cb2a-147">For more information about using the Office 365 CDN, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="2cb2a-148">Reutilize estruturas como _importações do React_ e do _Fabric_, que vêm como parte da Estrutura do SharePoint (SPFx).</span><span class="sxs-lookup"><span data-stu-id="2cb2a-148">Reuse frameworks like _React_ and _Fabric imports_ that come as part of the SharePoint Framework (SPFx).</span></span> <span data-ttu-id="2cb2a-149">Para saber mais, confira [Visão geral da Estrutura do SharePoint](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).</span><span class="sxs-lookup"><span data-stu-id="2cb2a-149">For more information, see [Overview of the SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).</span></span>
  - <span data-ttu-id="2cb2a-150">Verifique se você está usando a versão mais recente da Estrutura do SharePoint e atualize para novas versões quando elas estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-150">Ensure that you are using the latest version of the SharePoint Framework, and upgrade to new versions as they become available.</span></span>
- <span data-ttu-id="2cb2a-151">**Busca/cache de dados**</span><span class="sxs-lookup"><span data-stu-id="2cb2a-151">**Data fetching/caching**</span></span>
  - <span data-ttu-id="2cb2a-152">Se a extensão contar com chamadas adicionais do servidor para buscar dados para exibição, verifique se as APIs do servidor são rápidas e/ou implemente cache do lado do cliente (por exemplo, use _localStorage_ ou _IndexDB_ para conjuntos maiores).</span><span class="sxs-lookup"><span data-stu-id="2cb2a-152">If the extension relies on extra server calls to fetch data for display, ensure those server APIs are fast and/or implement client side caching (such as using _localStorage_ or _IndexDB_ for larger sets).</span></span>
  - <span data-ttu-id="2cb2a-153">Se várias chamadas forem necessárias para renderizar dados críticos, considere o uso de envio em lote no servidor ou de outros métodos de consolidação de solicitações em uma única chamada.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-153">If multiple calls are required to render critical data, consider batching on the server or other methods of consolidating requests to a single call.</span></span>
  - <span data-ttu-id="2cb2a-154">Como alternativa, se alguns elementos de dados exigirem uma API mais lenta, mas não forem críticos para a renderização inicial, separe-os em outra chamada, executada após a renderização dos dados críticos.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-154">Alternatively, if some elements of data require a slower API, but are not critical to initial rendering, decouple these to a separate call that is executed after critical data is rendered.</span></span>
  - <span data-ttu-id="2cb2a-155">Se várias partes usarem os mesmos dados, utilize uma camada de dados comum para evitar chamadas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-155">If multiple parts use the same data, utilize a common data layer to avoid duplicate calls.</span></span>
- <span data-ttu-id="2cb2a-156">**Tempo de renderização**</span><span class="sxs-lookup"><span data-stu-id="2cb2a-156">**Rendering time**</span></span>
  - <span data-ttu-id="2cb2a-157">Quaisquer fontes de mídia, como imagens e vídeos, devem ser dimensionadas de acordo com os limites do contêiner, dispositivo e/ou rede para evitar o download de grandes recursos desnecessários.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-157">Any media sources like images and videos should be sized to the limits of the container, device and/or network to avoid downloading unnecessary large assets.</span></span> <span data-ttu-id="2cb2a-158">Para saber mais sobre como usar dependências de conteúdo, confira [Usar a CDN (Rede de Distribuição de Conteúdo) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="2cb2a-158">For more information about content dependencies, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="2cb2a-159">Evite chamadas de API que causem refluxo, regras CSS complexas ou animações complicadas.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-159">Avoid API calls that cause re-flow, complex CSS rules or complicated animations.</span></span> <span data-ttu-id="2cb2a-160">Para obter mais informações, confira [Minimizar o refluxo do navegador](https://developers.google.com/speed/docs/insights/browser-reflow).</span><span class="sxs-lookup"><span data-stu-id="2cb2a-160">For more information, see [Minimizing browser reflow](https://developers.google.com/speed/docs/insights/browser-reflow).</span></span>
  - <span data-ttu-id="2cb2a-161">Evite o uso de tarefas de longa execução encadeadas.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-161">Avoid use of chained long running tasks.</span></span> <span data-ttu-id="2cb2a-162">Em vez disso, divida as tarefas de longa execução em filas separadas.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-162">Instead, break long running tasks apart into separate queues.</span></span> <span data-ttu-id="2cb2a-163">Para obter mais informações, confira [Otimizar a execução do JavaScript](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).</span><span class="sxs-lookup"><span data-stu-id="2cb2a-163">For more information, see [Optimize JavaScript Execution](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).</span></span>
  - <span data-ttu-id="2cb2a-164">Reserve o espaço correspondente para renderizar de forma assíncrona mídia ou elementos visuais, a fim de evitar quadros ignorados e instabilidade (também conhecida como _jank_).</span><span class="sxs-lookup"><span data-stu-id="2cb2a-164">Reserve corresponding space for asynchronously rendering media or visual elements to avoid skipped frames and stuttering (also known as _jank_).</span></span>
  - <span data-ttu-id="2cb2a-165">Se determinado navegador não oferecer suporte a um recurso usado na renderização, carregue um polyfill ou exclua o código dependente em execução.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-165">If a certain browser doesn't support a feature used in rendering, either load a polyfill or exclude running dependent code.</span></span> <span data-ttu-id="2cb2a-166">Se o recurso não for crítico, descarte recursos como manipuladores de eventos para evitar vazamentos de memória.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-166">If the feature is not critical, dispose resources such as event handlers to avoid memory leaks.</span></span>

<span data-ttu-id="2cb2a-167">Antes de fazer as revisões das páginas para corrigir problemas de desempenho, anote o tempo de carregamento da página nos resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-167">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="2cb2a-168">Execute a ferramenta novamente após a revisão para ver se o novo resultado está dentro do padrão da linha de base e verifique o tempo de carregamento da nova página para ver se melhorou.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-168">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Resultados do tempo de carregamento da página](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="2cb2a-170">O tempo de carregamento da página pode variar de acordo com vários fatores, como a carga da rede, hora do dia e outras condições transitórias.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-170">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="2cb2a-171">Você deve testar o tempo de carregamento da página algumas vezes antes e depois de fazer as alterações para ajudá-lo a calcular uma média dos resultados.</span><span class="sxs-lookup"><span data-stu-id="2cb2a-171">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2cb2a-172">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2cb2a-172">Related topics</span></span>

[<span data-ttu-id="2cb2a-173">Ajustar o desempenho do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2cb2a-173">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="2cb2a-174">Ajustar o desempenho do Office 365</span><span class="sxs-lookup"><span data-stu-id="2cb2a-174">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="2cb2a-175">Desempenho na experiência moderna do SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cb2a-175">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="2cb2a-176">Redes de distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="2cb2a-176">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="2cb2a-177">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2cb2a-177">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)