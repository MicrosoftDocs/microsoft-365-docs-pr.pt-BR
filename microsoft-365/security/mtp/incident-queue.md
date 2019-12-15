---
title: Priorizar Incidentes na Proteção contra Ameaças da Microsoft
description: Saiba como priorizar incidentes na fila de incidentes na Proteção contra Ameaças da Microsoft
keywords: incidente, fila, visão geral, dispositivos, identidades, usuários, caixa de correio, email, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 0c4231fa6284d967bcc49e4d46b0869c57733443
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910710"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="738a3-104">Priorizar Incidentes na Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="738a3-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="738a3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="738a3-105">**Applies to:**</span></span>
- <span data-ttu-id="738a3-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="738a3-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="738a3-107">A Proteção contra Ameaças da Microsoft aplica a análise de correlação e agrega todas as investigações e alertas relacionados de diferentes produtos em um incidente.</span><span class="sxs-lookup"><span data-stu-id="738a3-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="738a3-108">A Proteção contra Ameaças da Microsoft também disparará alertas exclusivos em atividades que só podem ser identificadas como mal-intencionadas, tendo em conta a visibilidade de ponta a ponta que a Proteção contra Ameaças da Microsoft tem em todo o estado e pacote de produtos.</span><span class="sxs-lookup"><span data-stu-id="738a3-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="738a3-109">Ao fazer isso, a Proteção contra Ameaças da Microsoft conta a história mais completa do ataque, permitindo que um analista de operações de segurança entenda e lide com ameaças complexas em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="738a3-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="738a3-110">A **Fila de incidentes** exibe um conjunto de incidentes sinalizados de vários dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="738a3-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="738a3-111">Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada.</span><span class="sxs-lookup"><span data-stu-id="738a3-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Imagem da fila de incidentes](../images/incidents-queue.png) 

<span data-ttu-id="738a3-113">Por padrão, a fila no centro de segurança do Microsoft 365 exibe os incidentes vistos nos últimos 30 dias, com o incidente mais recente exibido na parte superior da lista, ajudando a visualizar os incidentes mais recentes primeiro.</span><span class="sxs-lookup"><span data-stu-id="738a3-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="738a3-114">A fila de incidentes expõe colunas personalizáveis que fornecem visibilidade de diferentes características do incidente ou das entidades contidas, ajudando a tomar uma decisão embasada sobre a priorização de incidentes a serem tratados.</span><span class="sxs-lookup"><span data-stu-id="738a3-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span> 

<span data-ttu-id="738a3-115">A fila de incidentes também expõe várias opções de filtragem que, quando aplicadas, permitem a escolha de executar uma visão geral de todos os incidentes existentes em seu ambiente ou de se concentrar em um cenário ou ameaça específica.</span><span class="sxs-lookup"><span data-stu-id="738a3-115">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="738a3-116">A aplicação de filtros na fila de incidentes pode ajudar a determinar qual incidente exige atenção imediata.</span><span class="sxs-lookup"><span data-stu-id="738a3-116">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="738a3-117">Filtros disponíveis</span><span class="sxs-lookup"><span data-stu-id="738a3-117">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="738a3-118">Status</span><span class="sxs-lookup"><span data-stu-id="738a3-118">Status</span></span>
<span data-ttu-id="738a3-119">Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos.</span><span class="sxs-lookup"><span data-stu-id="738a3-119">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="738a3-120">Gravidade</span><span class="sxs-lookup"><span data-stu-id="738a3-120">Severity</span></span>
<span data-ttu-id="738a3-121">A gravidade de um incidente indica o impacto que pode ter em seus ativos.</span><span class="sxs-lookup"><span data-stu-id="738a3-121">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="738a3-122">Quanto maior a gravidade, maior o impacto e, normalmente, exige atenção imediata.</span><span class="sxs-lookup"><span data-stu-id="738a3-122">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="738a3-123">Atribuído a (proprietário)</span><span class="sxs-lookup"><span data-stu-id="738a3-123">Assigned to (owner)</span></span>
<span data-ttu-id="738a3-124">Você pode optar por filtrar a lista selecionando não atribuir a ninguém ou os que estão atribuídos a você.</span><span class="sxs-lookup"><span data-stu-id="738a3-124">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="738a3-125">Vários alertas</span><span class="sxs-lookup"><span data-stu-id="738a3-125">Multiple alerts</span></span> 
<span data-ttu-id="738a3-126">Filtre para ver somente os incidentes com mais de um alerta.</span><span class="sxs-lookup"><span data-stu-id="738a3-126">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="738a3-127">Isso pode ser uma indicação de um ataque que é mais complexo ou progredido no kill chain.</span><span class="sxs-lookup"><span data-stu-id="738a3-127">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="738a3-128">Várias fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="738a3-128">Multiple service sources</span></span> 
<span data-ttu-id="738a3-129">Filtrar para exibir somente incidentes com alertas de diferentes fontes (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="738a3-129">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="738a3-130">Fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="738a3-130">Service sources</span></span>
<span data-ttu-id="738a3-131">Ao escolher uma fonte específica, é possível se concentrar em incidentes com pelo menos um alerta da fonte escolhida.</span><span class="sxs-lookup"><span data-stu-id="738a3-131">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="738a3-132">Várias categorias</span><span class="sxs-lookup"><span data-stu-id="738a3-132">Multiple categories are supported.</span></span> 
<span data-ttu-id="738a3-133">Você pode optar por ver apenas os incidentes que estão mapeados em várias categorias do kill chain e que podem causar mais danos.</span><span class="sxs-lookup"><span data-stu-id="738a3-133">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="738a3-134">Categorias</span><span class="sxs-lookup"><span data-stu-id="738a3-134">Categories</span></span>
<span data-ttu-id="738a3-135">Escolha categorias específicas para se concentrar em uma etapa específica no kill chain</span><span class="sxs-lookup"><span data-stu-id="738a3-135">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="738a3-136">Confidencialidade de dados</span><span class="sxs-lookup"><span data-stu-id="738a3-136">Data sensitivity</span></span>
<span data-ttu-id="738a3-137">Alguns ataques se concentram no direcionamento para exfiltrar dados confidenciais ou valiosos.</span><span class="sxs-lookup"><span data-stu-id="738a3-137">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="738a3-138">Ao aplicar um filtro para ver se os dados confidenciais estão envolvidos no incidente, você pode determinar rapidamente se as informações confidenciais estão potencialmente comprometidas e priorizar o tratamento desses incidentes.</span><span class="sxs-lookup"><span data-stu-id="738a3-138">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="738a3-139">Só é aplicável se a Proteção de Informações da Microsoft estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="738a3-139">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="738a3-140">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="738a3-140">Next steps</span></span>
<span data-ttu-id="738a3-141">Após determinar qual incidente requer a prioridade mais alta, você pode continuar a fazer um trabalho mais investigativo em um incidente.</span><span class="sxs-lookup"><span data-stu-id="738a3-141">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="738a3-142">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="738a3-142">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="738a3-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="738a3-143">Related topics</span></span>
- [<span data-ttu-id="738a3-144">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="738a3-144">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="738a3-145">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="738a3-145">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="738a3-146">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="738a3-146">Manage incidents</span></span>](manage-incidents.md)