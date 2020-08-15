---
title: Otimizar imagens nas páginas de site moderno do SharePoint Online
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
description: Saiba como usar as ferramentas incluídas no SharePoint Online para otimizar imagens em páginas de site modernas do SharePoint Online.
ms.openlocfilehash: 09122dfd0bc832cf9a09cfb05bf0540e323797d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687410"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="6235b-103">Otimizar imagens nas páginas de site moderno do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6235b-103">Optimize images in SharePoint Online modern site pages</span></span>

<span data-ttu-id="6235b-104">Este artigo vai ajudá-lo a entender como otimizar imagens nas páginas de site moderno do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6235b-104">This article will help you understand how to optimize images in SharePoint Online modern site pages.</span></span>

<span data-ttu-id="6235b-105">Para saber mais sobre como otimizar imagens em sites de publicação clássicos, confira [Otimização de imagem do SharePoint Online](image-optimization-for-sharepoint-online.md)..</span><span class="sxs-lookup"><span data-stu-id="6235b-105">For information about optimizing images in classic publishing sites, see [Image optimization for SharePoint Online](image-optimization-for-sharepoint-online.md)..</span></span>

>[!NOTE]
><span data-ttu-id="6235b-106">Para obter mais informações sobre o desempenho dos portais modernos do SharePoint Online, confira [Desempenho na experiência moderna do SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="6235b-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a><span data-ttu-id="6235b-107">Usar a ferramenta Diagnóstico de página do SharePoint para analisar a otimização de imagens</span><span class="sxs-lookup"><span data-stu-id="6235b-107">Use the Page Diagnostics for SharePoint tool to analyze image optimization</span></span>

<span data-ttu-id="6235b-108">A ferramenta Diagnóstico de Página para SharePoint é uma extensão do navegador para os novos navegadores Microsoft Edge (https://www.microsoft.com/edge) e Chrome que analisam o portal moderno do SharePoint Online e as páginas clássicas de site de publicação.</span><span class="sxs-lookup"><span data-stu-id="6235b-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="6235b-109">A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho.</span><span class="sxs-lookup"><span data-stu-id="6235b-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="6235b-110">Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="6235b-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="6235b-111">A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6235b-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="6235b-112">Ao analisar um site moderno do SharePoint com a ferramenta Diagnóstico de página do SharePoint, você pode ver as informações sobre imagens grandes no painel _Testes de diagnóstico_.</span><span class="sxs-lookup"><span data-stu-id="6235b-112">When you analyze a SharePoint modern site with the Page Diagnostics for SharePoint tool, you can see information about large images in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="6235b-113">Os resultados possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="6235b-113">Possible results include:</span></span>

- <span data-ttu-id="6235b-114">**Atenção necessária** (vermelho): a página contém **uma ou mais** imagens com tamanho maior que 300 KB</span><span class="sxs-lookup"><span data-stu-id="6235b-114">**Attention required** (red): The page contains **one or more** images over 300KB in size</span></span>
- <span data-ttu-id="6235b-115">**Nenhuma ação necessária** (verde): a página não contém imagens com tamanho maior que 300 KB</span><span class="sxs-lookup"><span data-stu-id="6235b-115">**No action required** (green): The page contains no images over 300KB in size</span></span>

<span data-ttu-id="6235b-116">Se o resultado **Imagens grandes detectadas** aparecer na seção dos resultados **Atenção necessária**, você poderá clicar no resultado para ver mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="6235b-116">If the **Large images detected** result appears in the **Attention required** section of the results, you can click the result to see additional details.</span></span>

![Resultados da ferramenta Diagnóstico de Página](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a><span data-ttu-id="6235b-118">Solucionar problemas de imagens grandes</span><span class="sxs-lookup"><span data-stu-id="6235b-118">Remediate large image issues</span></span>

<span data-ttu-id="6235b-119">Se uma página contiver imagens com tamanho superior a 300 KB, selecione o resultado **Imagens grandes detectadas** para ver quais são as imagens muito grandes.</span><span class="sxs-lookup"><span data-stu-id="6235b-119">If a page contains images over 300KB in size, select the **Large images detected** result to see which images are too large.</span></span> <span data-ttu-id="6235b-120">Nas páginas modernas do SharePoint Online, as renderizações de imagens são fornecidas e dimensionadas automaticamente, dependendo do tamanho da janela do navegador e da resolução do monitor do cliente.</span><span class="sxs-lookup"><span data-stu-id="6235b-120">In modern SharePoint Online pages, renditions of images are automatically provided and sized depending on the size of the browser window and the resolution of the client monitor.</span></span> <span data-ttu-id="6235b-121">Você sempre deve otimizar as imagens para uso na Web antes de carregá-las no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6235b-121">You should always optimize images for web use prior to upload to SharePoint Online.</span></span> <span data-ttu-id="6235b-122">Imagens muito grandes serão reduzidas automaticamente em tamanho e resolução, o que pode resultar em características inesperadas de renderização.</span><span class="sxs-lookup"><span data-stu-id="6235b-122">Very large images will be automatically reduced in size and resolution which can result in unexpected rendering characteristics.</span></span>

<span data-ttu-id="6235b-123">Antes de fazer as revisões das páginas para corrigir problemas de desempenho, anote o tempo de carregamento da página nos resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="6235b-123">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="6235b-124">Execute a ferramenta novamente após a revisão para ver se o novo resultado está dentro do padrão da linha de base e verifique o tempo de carregamento da nova página para ver se melhorou.</span><span class="sxs-lookup"><span data-stu-id="6235b-124">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Resultados do tempo de carregamento da página](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="6235b-126">O tempo de carregamento da página pode variar de acordo com vários fatores, como a carga da rede, hora do dia e outras condições transitórias.</span><span class="sxs-lookup"><span data-stu-id="6235b-126">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="6235b-127">Você deve testar o tempo de carregamento da página algumas vezes antes e depois de fazer as alterações para ajudá-lo a calcular uma média dos resultados.</span><span class="sxs-lookup"><span data-stu-id="6235b-127">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6235b-128">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6235b-128">Related topics</span></span>

[<span data-ttu-id="6235b-129">Ajustar o desempenho do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6235b-129">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="6235b-130">Ajustar o desempenho do Office 365</span><span class="sxs-lookup"><span data-stu-id="6235b-130">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="6235b-131">Desempenho na experiência moderna do SharePoint</span><span class="sxs-lookup"><span data-stu-id="6235b-131">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="6235b-132">Redes de distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="6235b-132">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="6235b-133">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6235b-133">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
