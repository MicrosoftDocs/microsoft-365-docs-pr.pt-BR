---
title: Decisão com base nos resultados em Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Saiba como a guia Decidir no Advanced eDiscovery fornece dados que podem ajudá-lo a determinar o tamanho correto do conjunto de revisão de arquivos de caso.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769146"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="ab1a0-103">Decisões baseadas em relevância resulta em Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ab1a0-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="ab1a0-104">No módulo De relevância no Advanced eDiscovery, a guia Decidir fornece informações adicionais para exibição e uso de estatísticas de suporte à decisão para determinar o tamanho do conjunto de revisão de arquivos de caso.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="ab1a0-105">Usando a guia Decidir</span><span class="sxs-lookup"><span data-stu-id="ab1a0-105">Using the Decide tab</span></span>

![Decisão de Relevância](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="ab1a0-107">Esta guia inclui os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="ab1a0-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="ab1a0-108">**Problema**: a partir daqui, você pode selecionar o problema de interesse na lista.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="ab1a0-109">**Taxa de reavaliação-recall**: comparações de Advanced eDiscovery de acordo com as pontuações de relevância.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="ab1a0-110">O ponto de corte no gráfico representa a porcentagem de arquivos a revisar, mapeado para uma pontuação de Relevância.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="ab1a0-111">Isso é usado na fase teste de relevância e como um limite de exportação para o descarte.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="ab1a0-112">O ponto de corte padrão, para o número de arquivos a revisar está no ponto em que o equilíbrio entre Recall e Precision é ideal.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="ab1a0-113">O ponto de corte real deve ser determinado pelo usuário, dependendo dos objetivos e da troca de custo (%revisão) e do risco (%recall).</span><span class="sxs-lookup"><span data-stu-id="ab1a0-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="ab1a0-114">Usando o controle deslizante, você pode ajustar o ponto de corte e ver o efeito no gráfico e nos parâmetros, ao ajustar a porcentagem de arquivos relevantes a serem recuperados e antes de validar uma decisão.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="ab1a0-115">**Parâmetros**: Revisão, Recall, Próximo relevante e Total de parâmetros de custo são estatísticas calculadas cumulativas referentes ao conjunto de revisão em relação à coleção para todo o caso.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="ab1a0-116">As definições para esses parâmetros são as seguinte:</span><span class="sxs-lookup"><span data-stu-id="ab1a0-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="ab1a0-117">**Revisão**: Porcentagem de arquivos a analisar com base nesse recorte.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="ab1a0-118">**Recall**: Porcentagem de arquivos relevantes no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="ab1a0-119">**Próximo relevante**: Custo para revisar e identificar outro arquivo relevante que não está atualmente no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="ab1a0-120">**Custo total**: Custo para revisar essa porcentagem dos arquivos de caso.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="ab1a0-121">As configurações de parâmetros de custo podem ser definidas pelo Gerente de Caso.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="ab1a0-122">**Distribuição por pontuação de relevância:** Os arquivos na exibição cinza escuro à esquerda estão abaixo da pontuação de recorte.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="ab1a0-123">Uma dica de ferramenta exibe a pontuação de relevância e a porcentagem relacionada de arquivos no conjunto de arquivos de revisão em relação ao total de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="ab1a0-124">O painel **Detalhes expandidos** exibe mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="ab1a0-125">Os arquivos em figuras de coleção não incluem arquivos vazios ou nebulares.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="ab1a0-126">Os números de arquivos de família representam arquivos que não são carregados em Relevância, mas ainda contam como parte da família.</span><span class="sxs-lookup"><span data-stu-id="ab1a0-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
