---
title: Relatório de proteção contra ameaças no Microsoft Defender ATP
description: Rastrear detecções, categorias e gravidade de alerta usando o relatório de proteção contra ameaças
keywords: detecção de alerta, origem, alerta por categoria, gravidade do alerta, classificação de alerta, determinação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 104548314b8ef0ceb15d8d2683dad552233a509f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053562"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="5ee72-104">Relatório de proteção contra ameaças no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5ee72-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5ee72-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5ee72-105">**Applies to:**</span></span>
- [<span data-ttu-id="5ee72-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5ee72-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="5ee72-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ee72-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5ee72-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5ee72-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5ee72-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5ee72-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="5ee72-110">O relatório de proteção contra ameaças fornece informações de alto nível sobre alertas gerados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5ee72-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="5ee72-111">O relatório inclui informações de tendência que mostram as fontes de detecção, categorias, gravidades, status, classificações e determinações de alertas ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="5ee72-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="5ee72-112">O painel é estruturado em duas seções:</span><span class="sxs-lookup"><span data-stu-id="5ee72-112">The dashboard is structured into two sections:</span></span>

![Imagem do relatório de proteção contra ameaças](images/threat-protection-reports.png)

<span data-ttu-id="5ee72-114">Seção</span><span class="sxs-lookup"><span data-stu-id="5ee72-114">Section</span></span> | <span data-ttu-id="5ee72-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ee72-115">Description</span></span> 
:---|:---
<span data-ttu-id="5ee72-116">1</span><span class="sxs-lookup"><span data-stu-id="5ee72-116">1</span></span> | <span data-ttu-id="5ee72-117">Tendências de alertas</span><span class="sxs-lookup"><span data-stu-id="5ee72-117">Alerts trends</span></span>
<span data-ttu-id="5ee72-118">2</span><span class="sxs-lookup"><span data-stu-id="5ee72-118">2</span></span> | <span data-ttu-id="5ee72-119">Resumo do alerta</span><span class="sxs-lookup"><span data-stu-id="5ee72-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="5ee72-120">Tendências de alerta</span><span class="sxs-lookup"><span data-stu-id="5ee72-120">Alert trends</span></span>
<span data-ttu-id="5ee72-121">Por padrão, as tendências de alerta exibem informações de alerta do período de 30 dias que termina no último dia completo.</span><span class="sxs-lookup"><span data-stu-id="5ee72-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="5ee72-122">Para obter uma perspectiva melhor sobre as tendências que ocorrem em sua organização, você pode ajustar o período de relatório ajustando o período de tempo mostrado.</span><span class="sxs-lookup"><span data-stu-id="5ee72-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="5ee72-123">Para ajustar o período de tempo, selecione um intervalo de tempo nas opções listadas:</span><span class="sxs-lookup"><span data-stu-id="5ee72-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="5ee72-124">30 dias</span><span class="sxs-lookup"><span data-stu-id="5ee72-124">30 days</span></span>
- <span data-ttu-id="5ee72-125">3 meses</span><span class="sxs-lookup"><span data-stu-id="5ee72-125">3 months</span></span>
- <span data-ttu-id="5ee72-126">6 meses</span><span class="sxs-lookup"><span data-stu-id="5ee72-126">6 months</span></span>
- <span data-ttu-id="5ee72-127">Personalizado</span><span class="sxs-lookup"><span data-stu-id="5ee72-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="5ee72-128">Esses filtros só são aplicados na seção tendências de alerta.</span><span class="sxs-lookup"><span data-stu-id="5ee72-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="5ee72-129">Ele não afeta a seção resumo do alerta.</span><span class="sxs-lookup"><span data-stu-id="5ee72-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="5ee72-130">Resumo do alerta</span><span class="sxs-lookup"><span data-stu-id="5ee72-130">Alert summary</span></span>
<span data-ttu-id="5ee72-131">Embora as tendências de alerta mostrem informações de alerta tendência, o resumo de alerta mostra informações de alerta com escopo para o dia atual.</span><span class="sxs-lookup"><span data-stu-id="5ee72-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="5ee72-132">O resumo do alerta permite que você faça uma pesquisa em uma fila de alertas específica com o filtro correspondente aplicado a ela.</span><span class="sxs-lookup"><span data-stu-id="5ee72-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="5ee72-133">Por exemplo, clicar na barra EDR no cartão Detecção de fontes trará a fila de alertas com resultados mostrando apenas alertas gerados a partir de detecções de EDR.</span><span class="sxs-lookup"><span data-stu-id="5ee72-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="5ee72-134">Os dados refletidos na seção resumo são escopos para 180 dias antes da data atual.</span><span class="sxs-lookup"><span data-stu-id="5ee72-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="5ee72-135">Por exemplo, se a data de hoje for 5 de novembro de 2019, os dados da seção de resumo refletirão números que começam de 5 de maio de 2019 a 5 de novembro de 2019.</span><span class="sxs-lookup"><span data-stu-id="5ee72-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="5ee72-136">O filtro aplicado na seção tendências não é aplicado na seção resumo.</span><span class="sxs-lookup"><span data-stu-id="5ee72-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="5ee72-137">Atributos de alerta</span><span class="sxs-lookup"><span data-stu-id="5ee72-137">Alert attributes</span></span>
<span data-ttu-id="5ee72-138">O relatório é feito de cartões que exibem os seguintes atributos de alerta:</span><span class="sxs-lookup"><span data-stu-id="5ee72-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="5ee72-139">**Fontes de detecção**: mostra informações sobre os sensores e tecnologias de detecção que fornecem os dados usados pelo Microsoft Defender para Endpoint para disparar alertas.</span><span class="sxs-lookup"><span data-stu-id="5ee72-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="5ee72-140">**Categorias de** ameaça : mostra os tipos de atividade de ameaça ou ataque que dispararam alertas, indicando possíveis áreas de foco para suas operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="5ee72-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="5ee72-141">**Severidade**: mostra o nível de gravidade dos alertas, indicando o impacto potencial coletivo das ameaças à sua organização e o nível de resposta necessário para lidar com eles.</span><span class="sxs-lookup"><span data-stu-id="5ee72-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="5ee72-142">**Status**: mostra o status de resolução dos alertas, indicando a eficiência de suas respostas de alerta manual e de correção automatizada (se habilitada).</span><span class="sxs-lookup"><span data-stu-id="5ee72-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="5ee72-143">**Classificação &** determinação : mostra como você classificou alertas após a resolução, se você os classificou como ameaças reais (alertas verdadeiros) ou como detecções incorretas (alertas falsos).</span><span class="sxs-lookup"><span data-stu-id="5ee72-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="5ee72-144">Esses cartões também mostram a determinação de alertas resolvidos, fornecendo informações adicionais, como os tipos de ameaças reais encontradas ou as atividades legítimas detectadas incorretamente.</span><span class="sxs-lookup"><span data-stu-id="5ee72-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="5ee72-145">Filtrar dados</span><span class="sxs-lookup"><span data-stu-id="5ee72-145">Filter data</span></span>

<span data-ttu-id="5ee72-146">Use os filtros fornecidos para incluir ou excluir alertas com determinados atributos.</span><span class="sxs-lookup"><span data-stu-id="5ee72-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="5ee72-147">Esses filtros se aplicam **a** todos os cartões do relatório.</span><span class="sxs-lookup"><span data-stu-id="5ee72-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="5ee72-148">Por exemplo, para mostrar dados somente sobre alertas de alta gravidade:</span><span class="sxs-lookup"><span data-stu-id="5ee72-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="5ee72-149">Em **Filtros > Severidade,** selecione **Alta**</span><span class="sxs-lookup"><span data-stu-id="5ee72-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="5ee72-150">Certifique-se de que todas as outras opções **em Gravidade** sejam deselegidas.</span><span class="sxs-lookup"><span data-stu-id="5ee72-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="5ee72-151">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="5ee72-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="5ee72-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5ee72-152">Related topic</span></span>
- [<span data-ttu-id="5ee72-153">Relatório de conformidade e saúde do dispositivo</span><span class="sxs-lookup"><span data-stu-id="5ee72-153">Device health and compliance report</span></span>](machine-reports.md)
