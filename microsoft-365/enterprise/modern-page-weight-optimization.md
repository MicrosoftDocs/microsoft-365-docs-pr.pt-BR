---
title: Otimizar o peso da página nas páginas do site moderno do SharePoint Online.
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
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Saiba como usar a ferramenta Diagnóstico de Página para otimizar o peso da página SharePoint páginas de site modernas online.
ms.openlocfilehash: 780d8ca0debbc5efb834f8f3543b9a5a8d168108
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907439"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="9ad4e-103">Otimizar o peso da página nas páginas do site moderno do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-103">Optimize page weight in SharePoint Online modern site pages</span></span>

<span data-ttu-id="9ad4e-104">As páginas do site moderno do SharePoint Online contêm o código serializado necessário para renderizar o conteúdo da página, incluindo imagens, texto, objetos na área de conteúdo embaixo das barras de navegação/comando e outro código HTML que forma a estrutura da página.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-104">SharePoint Online modern site pages contain serialized code that is required to render page content of the page, including images, text, objects in the content area underneath navigation/command bars and other HTML code that forms the framework of the page.</span></span> <span data-ttu-id="9ad4e-105">A gramatura da página é uma medida desse código HTML e deve ser limitado para garantir o tempo de carregamento ideal da página.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-105">Page weight is a measurement of this HTML code, and should be limited to ensure optimal page load times.</span></span>

<span data-ttu-id="9ad4e-106">Este artigo vai ajudá-lo a entender como reduzir o peso da página em suas páginas de site modernos.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-106">This article will help you understand how to reduce page weight in your modern site pages.</span></span>

>[!NOTE]
><span data-ttu-id="9ad4e-107">Para obter mais informações sobre o desempenho dos portais modernos do SharePoint Online, confira [Desempenho na experiência moderna do SharePoint](/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="9ad4e-107">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a><span data-ttu-id="9ad4e-108">Usar a ferramenta Diagnóstico de Página do SharePoint para analisar o peso da página</span><span class="sxs-lookup"><span data-stu-id="9ad4e-108">Use the Page Diagnostics for SharePoint tool to analyze page weight</span></span>

<span data-ttu-id="9ad4e-109">A ferramenta Diagnóstico de Página para SharePoint é uma extensão do navegador para os novos navegadores Microsoft Edge (https://www.microsoft.com/edge) e Chrome que analisam o portal moderno do SharePoint Online e as páginas clássicas de site de publicação.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="9ad4e-110">A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="9ad4e-111">Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="9ad4e-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="9ad4e-112">A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="9ad4e-113">Ao analisar uma página de site do SharePoint com a ferramenta Diagnóstico de Página para SharePoint, você pode ver informações sobre a página **Peso da página em 500kB** resultado do painel dos _Testes de Diagnóstico_.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about page in the **Page weight under 500KB** result of the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="9ad4e-114">O resultado será exibido em verde se o peso da página estiver abaixo do valor da linha de base e vermelho se o peso da página exceder o valor da linha de base.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-114">The result will appear in green if the page weight is under the baseline value, and red if the page weight exceeds the baseline value.</span></span>

<span data-ttu-id="9ad4e-115">Os resultados possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="9ad4e-115">Possible results include:</span></span>

- <span data-ttu-id="9ad4e-116">**Atenção necessária** (vermelho): O peso da página ultrapassa 500kB</span><span class="sxs-lookup"><span data-stu-id="9ad4e-116">**Attention required** (red): Page weight exceeds 500KB</span></span>
- <span data-ttu-id="9ad4e-117">**Nenhuma ação necessário** (verde): O peso da página está abaixo de 500kB</span><span class="sxs-lookup"><span data-stu-id="9ad4e-117">**No action required** (green): Page weight is under 500KB</span></span>

<span data-ttu-id="9ad4e-118">Se o resultado **Peso da página abaixo de 500kB** aparecer na seção **Atenção necessária**, você pode clicar no resultado para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-118">If the **Page weight under 500KB** result appears in the **Attention required** section, you can click the result for details.</span></span>

![Solicitações para resultados do SharePoint](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a><span data-ttu-id="9ad4e-120">Solucionar problemas com o peso da página</span><span class="sxs-lookup"><span data-stu-id="9ad4e-120">Remediate page weight issues</span></span>

<span data-ttu-id="9ad4e-121">Se o peso da página exceder 500KB, você pode aumentar o tempo geral de carregamento da página reduzindo o número de Web Parts e limitando o conteúdo da página a um grau apropriado.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-121">If page weight exceeds 500KB, you can improve overall page load time by reducing the number of web parts and limiting page content to an appropriate degree.</span></span>

<span data-ttu-id="9ad4e-122">As diretrizes gerais para reduzir o peso da página incluem:</span><span class="sxs-lookup"><span data-stu-id="9ad4e-122">General guidance for reducing page weight includes:</span></span>

- <span data-ttu-id="9ad4e-123">Limite o conteúdo da página a um valor razoável e use várias páginas para conteúdo relacionado.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-123">Limit the page content to a reasonable amount and use multiple pages for related content.</span></span>
- <span data-ttu-id="9ad4e-124">Minimize o uso de Web Parts com grandes bolsas de propriedades.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-124">Minimize the use of web parts that have large property bags.</span></span>
- <span data-ttu-id="9ad4e-125">Use modos de exibição cumulativos não interativos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-125">Use non-interactive rollup views when possible.</span></span>
- <span data-ttu-id="9ad4e-126">Otimize os tamanhos das imagens dimensionando-as de forma adequada, usando formatos de imagem compactados e garantindo que eles sejam baixados de uma CDN.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-126">Optimize image sizes by sizing images appropriately, using compressed image formats and ensuring that they are downloaded from a CDN.</span></span>

<span data-ttu-id="9ad4e-127">Para saber mais, confira o artigo a seguir sobre como limitar o peso da página no seguinte artigo:</span><span class="sxs-lookup"><span data-stu-id="9ad4e-127">You can find additional guidance for limiting page weight in the following article:</span></span>

- [<span data-ttu-id="9ad4e-128">Otimizar o desempenho de página no SharePoint</span><span class="sxs-lookup"><span data-stu-id="9ad4e-128">Optimize page performance in SharePoint</span></span>](/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

<span data-ttu-id="9ad4e-129">Antes de criar revisões de página para corrigir problemas de desempenho, anote o tempo de carregamento da página nos resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-129">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="9ad4e-130">Execute a ferramenta novamente após a revisão para ver se o novo resultado está dentro do padrão da linha de base e verifique o tempo de carregamento da nova página para ver se melhorou.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-130">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Resultados do tempo de carregamento da página](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="9ad4e-132">O tempo de carregamento da página pode variar de acordo com vários fatores, como a carga da rede, hora do dia e outras condições transitórias.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-132">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="9ad4e-133">Você deve testar o tempo de carregamento da página algumas vezes antes e depois de fazer as alterações para ajudá-lo a calcular uma média dos resultados.</span><span class="sxs-lookup"><span data-stu-id="9ad4e-133">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9ad4e-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9ad4e-134">Related topics</span></span>

[<span data-ttu-id="9ad4e-135">Ajustar o desempenho do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9ad4e-135">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="9ad4e-136">Ajustar o desempenho do Office 365</span><span class="sxs-lookup"><span data-stu-id="9ad4e-136">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="9ad4e-137">Desempenho na experiência moderna do SharePoint</span><span class="sxs-lookup"><span data-stu-id="9ad4e-137">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="9ad4e-138">Redes de distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="9ad4e-138">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="9ad4e-139">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9ad4e-139">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)