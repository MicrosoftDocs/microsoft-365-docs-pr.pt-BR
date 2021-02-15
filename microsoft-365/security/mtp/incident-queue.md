---
title: Priorizar incidentes no Microsoft 365 Defender
description: Saiba como filtrar incidentes da fila de incidentes no Microsoft 365 Defender
keywords: incidente, fila, visão geral, dispositivos, identidades, usuários, caixa de correio, email, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929289"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="de02c-104">Priorizar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de02c-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="de02c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="de02c-105">**Applies to:**</span></span>
- <span data-ttu-id="de02c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de02c-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="de02c-107">O Microsoft 365 Defender aplica análises de correlação e agrega todos os alertas e investigações relacionados de diferentes produtos em um único incidente.</span><span class="sxs-lookup"><span data-stu-id="de02c-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="de02c-108">O Microsoft 365 Defender também dispara alertas exclusivos sobre atividades que só podem ser identificadas como mal-intencionadas devido à visibilidade de ponta a ponta que o Microsoft 365 Defender tem em todo o estado e pacote de produtos.</span><span class="sxs-lookup"><span data-stu-id="de02c-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="de02c-109">Essa exibição oferece ao analista de operações de segurança a história mais ampla de ataques, o que os ajuda a entender e lidar melhor com ameaças complexas em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="de02c-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="de02c-110">A **Fila de incidentes** exibe um conjunto de incidentes sinalizados de vários dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="de02c-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="de02c-111">Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada.</span><span class="sxs-lookup"><span data-stu-id="de02c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Imagem da fila de incidentes](../../media/incidents-queue.png) 

<span data-ttu-id="de02c-113">Por padrão, a fila no centro de segurança do Microsoft 365 exibe incidentes vistos nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="de02c-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="de02c-114">O incidente mais recente está no topo da lista para que você possa vê-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="de02c-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="de02c-115">A fila de incidentes expõe colunas personalizáveis que dão visibilidade a diferentes características do incidente ou das entidades contidas.</span><span class="sxs-lookup"><span data-stu-id="de02c-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="de02c-116">Isso ajuda você a tomar uma decisão informada em relação à priorização de incidentes a tratar.</span><span class="sxs-lookup"><span data-stu-id="de02c-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="de02c-117">Para obter visibilidade adicional em um relance, a nomenização automática de incidentes gera nomes de incidentes com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="de02c-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="de02c-118">Isso permite que você entenda rapidamente o escopo do incidente.</span><span class="sxs-lookup"><span data-stu-id="de02c-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="de02c-119">Por exemplo: *incidente de vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="de02c-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="de02c-120">Os incidentes que existiam antes da lançamento da nomenização automática de incidentes não terão seu nome alterado.</span><span class="sxs-lookup"><span data-stu-id="de02c-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="de02c-121">A fila de incidentes também expõe várias opções de filtragem que, quando aplicadas, permitem executar uma varredura ampla de todos os incidentes existentes em seu ambiente ou decidir se concentrar em um cenário ou ameaça específico.</span><span class="sxs-lookup"><span data-stu-id="de02c-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="de02c-122">A aplicação de filtros na fila de incidentes pode ajudar a determinar qual incidente exige atenção imediata.</span><span class="sxs-lookup"><span data-stu-id="de02c-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="de02c-123">Filtros disponíveis</span><span class="sxs-lookup"><span data-stu-id="de02c-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="de02c-124">Atribuído a</span><span class="sxs-lookup"><span data-stu-id="de02c-124">Assigned to</span></span>
<span data-ttu-id="de02c-125">Você pode optar por mostrar alertas atribuídos a você ou aos tratados pela automação.</span><span class="sxs-lookup"><span data-stu-id="de02c-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="de02c-126">Categorias</span><span class="sxs-lookup"><span data-stu-id="de02c-126">Categories</span></span>
<span data-ttu-id="de02c-127">Escolha categorias para se concentrar em táticas específicas, técnicas ou componentes de ataque vistos.</span><span class="sxs-lookup"><span data-stu-id="de02c-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="de02c-128">Classificação</span><span class="sxs-lookup"><span data-stu-id="de02c-128">Classification</span></span>
<span data-ttu-id="de02c-129">Filtrar incidentes com base nas classificações definidas dos alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="de02c-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="de02c-130">Os valores incluem alertas verdadeiros, alertas falsos ou não definidos.</span><span class="sxs-lookup"><span data-stu-id="de02c-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="de02c-131">Confidencialidade de dados</span><span class="sxs-lookup"><span data-stu-id="de02c-131">Data sensitivity</span></span>
<span data-ttu-id="de02c-132">Alguns ataques se concentram no direcionamento para exfiltrar dados confidenciais ou valiosos.</span><span class="sxs-lookup"><span data-stu-id="de02c-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="de02c-133">Ao aplicar um filtro para ver se os dados confidenciais estão envolvidos no incidente, você pode determinar rapidamente se as informações confidenciais estão potencialmente comprometidas e priorizar o tratamento desses incidentes.</span><span class="sxs-lookup"><span data-stu-id="de02c-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="de02c-134">Só é aplicável se a Proteção de Informações da Microsoft estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="de02c-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="de02c-135">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="de02c-135">Device group</span></span>
<span data-ttu-id="de02c-136">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="de02c-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="de02c-137">Estado de investigação</span><span class="sxs-lookup"><span data-stu-id="de02c-137">Investigation state</span></span>
<span data-ttu-id="de02c-138">Filtrar incidentes pelo status de investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="de02c-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="de02c-139">Várias categorias</span><span class="sxs-lookup"><span data-stu-id="de02c-139">Multiple categories</span></span> 
<span data-ttu-id="de02c-140">Você pode optar por ver apenas incidentes que foram mapeados para várias categorias e, portanto, pode causar mais danos.</span><span class="sxs-lookup"><span data-stu-id="de02c-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="de02c-141">Várias fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="de02c-141">Multiple service sources</span></span> 
<span data-ttu-id="de02c-142">Filtrar para ver apenas incidentes que contêm alertas de diferentes fontes (Microsoft Defender para Ponto de Extremidade, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="de02c-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="de02c-143">Plataforma do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="de02c-143">OS platform</span></span>
<span data-ttu-id="de02c-144">Limitar a exibição da fila de incidentes por sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="de02c-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="de02c-145">Fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="de02c-145">Service sources</span></span>
<span data-ttu-id="de02c-146">Ao escolher uma fonte específica, é possível se concentrar em incidentes com pelo menos um alerta da fonte escolhida.</span><span class="sxs-lookup"><span data-stu-id="de02c-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="de02c-147">Severity</span><span class="sxs-lookup"><span data-stu-id="de02c-147">Severity</span></span>
<span data-ttu-id="de02c-148">A gravidade de um incidente indica o impacto que ele pode ter em seus ativos.</span><span class="sxs-lookup"><span data-stu-id="de02c-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="de02c-149">Quanto maior a gravidade, maior o impacto e normalmente exige a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="de02c-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="de02c-150">Status</span><span class="sxs-lookup"><span data-stu-id="de02c-150">Status</span></span>
<span data-ttu-id="de02c-151">Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos.</span><span class="sxs-lookup"><span data-stu-id="de02c-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="de02c-152">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="de02c-152">Next steps</span></span>
<span data-ttu-id="de02c-153">Após determinar qual incidente requer a prioridade mais alta, você pode continuar a fazer um trabalho mais investigativo em um incidente.</span><span class="sxs-lookup"><span data-stu-id="de02c-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="de02c-154">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="de02c-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="de02c-155">Confira também</span><span class="sxs-lookup"><span data-stu-id="de02c-155">See also</span></span>
- [<span data-ttu-id="de02c-156">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="de02c-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="de02c-157">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="de02c-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="de02c-158">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="de02c-158">Manage incidents</span></span>](manage-incidents.md)
