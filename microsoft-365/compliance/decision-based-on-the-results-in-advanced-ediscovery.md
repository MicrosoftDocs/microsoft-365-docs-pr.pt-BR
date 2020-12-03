---
title: Decisão com base nos resultados da descoberta eletrônica avançada
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
description: Saiba como a guia decidir em descoberta eletrônica avançada fornece dados que podem ajudá-lo a determinar o tamanho correto do conjunto de arquivos de caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60213226bef1c04767d4be17a09b58d6940ac223
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562962"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="9454c-103">Decisão com base nos resultados da descoberta eletrônica avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="9454c-103">Decision based on the results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="9454c-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="9454c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="9454c-106">Na descoberta eletrônica avançada, a guia decidir fornece informações adicionais para exibir e usar estatísticas de suporte à decisão para determinar o tamanho do conjunto de análise de arquivos de caso.</span><span class="sxs-lookup"><span data-stu-id="9454c-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="9454c-107">Usando a guia decidir</span><span class="sxs-lookup"><span data-stu-id="9454c-107">Using the Decide tab</span></span>

![Decisão de Relevância](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="9454c-109">Esta guia inclui os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="9454c-109">This tab includes the following components:</span></span>
  
- <span data-ttu-id="9454c-110">**Problema**: aqui, você pode selecionar o problema de interesse na lista.</span><span class="sxs-lookup"><span data-stu-id="9454c-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="9454c-111">**Taxa de recuperação de revisão**: comparações de análise de descoberta eletrônica avançada de acordo com as pontuações de relevância.</span><span class="sxs-lookup"><span data-stu-id="9454c-111">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="9454c-112">O ponto de corte no gráfico representa a porcentagem de arquivos a serem revisados, mapeados para uma pontuação de relevância.</span><span class="sxs-lookup"><span data-stu-id="9454c-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="9454c-113">Isso é usado na fase de teste de relevância e como um limite de exportação para a seleção.</span><span class="sxs-lookup"><span data-stu-id="9454c-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="9454c-114">O ponto de corte padrão, para o número de arquivos a serem revisados, é o ponto no qual o equilíbrio entre recall e Precision é ideal.</span><span class="sxs-lookup"><span data-stu-id="9454c-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="9454c-115">O ponto de corte real deve ser determinado pelo usuário dependendo dos objetivos e da troca de custo (% revisão) e risco (% recall).</span><span class="sxs-lookup"><span data-stu-id="9454c-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="9454c-116">Usando o controle deslizante, você pode ajustar o ponto de corte e ver o efeito no gráfico e nos parâmetros, ao ajustar a porcentagem de arquivos relevantes a serem recuperados e antes de validar uma decisão.</span><span class="sxs-lookup"><span data-stu-id="9454c-116">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="9454c-117">**Parâmetros**: revisar, renovar, os parâmetros de custo total relevantes e totais são estatísticas calculadas cumulativas referentes ao conjunto de revisão em relação à coleção para o caso inteiro.</span><span class="sxs-lookup"><span data-stu-id="9454c-117">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="9454c-118">As definições desses parâmetros são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="9454c-118">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="9454c-119">**Revisão**: porcentagem de arquivos a serem revisados com base nesse corte.</span><span class="sxs-lookup"><span data-stu-id="9454c-119">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="9454c-120">**Recall**: porcentagem de arquivos relevantes no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="9454c-120">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="9454c-121">**Próximo relevante**: custo para revisar e identificar um arquivo relevante adicional que não está atualmente no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="9454c-121">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="9454c-122">**Custo total**: custo para a revisão desse percentual dos arquivos de caso.</span><span class="sxs-lookup"><span data-stu-id="9454c-122">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="9454c-123">As configurações de parâmetros de custo podem ser definidas pelo gerente de caso.</span><span class="sxs-lookup"><span data-stu-id="9454c-123">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="9454c-124">**Distribuição por Pontuação de relevância**: os arquivos na exibição cinza escuro à esquerda estão abaixo da Pontuação de corte.</span><span class="sxs-lookup"><span data-stu-id="9454c-124">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="9454c-125">Uma dica de ferramenta exibe a pontuação de relevância e a porcentagem relacionada de arquivos no conjunto de arquivos de revisão em relação ao total de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9454c-125">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="9454c-126">O painel de detalhes expandido exibe detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="9454c-126">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="9454c-127">Os arquivos nas figuras de coleção não incluem arquivos vazios ou nebulous.</span><span class="sxs-lookup"><span data-stu-id="9454c-127">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="9454c-128">Os números de arquivos da família representam arquivos que não são carregados em relevância, ainda que sejam contados como parte da família.</span><span class="sxs-lookup"><span data-stu-id="9454c-128">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9454c-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9454c-129">Related topics</span></span>

[<span data-ttu-id="9454c-130">Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="9454c-130">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="9454c-131">Noções básicas sobre avaliação em relevância</span><span class="sxs-lookup"><span data-stu-id="9454c-131">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9454c-132">Marcação e avaliação</span><span class="sxs-lookup"><span data-stu-id="9454c-132">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9454c-133">Realizando treinamento de relevância</span><span class="sxs-lookup"><span data-stu-id="9454c-133">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9454c-134">Análise de relevância de rastreamento</span><span class="sxs-lookup"><span data-stu-id="9454c-134">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9454c-135">Testando análise de relevância</span><span class="sxs-lookup"><span data-stu-id="9454c-135">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

