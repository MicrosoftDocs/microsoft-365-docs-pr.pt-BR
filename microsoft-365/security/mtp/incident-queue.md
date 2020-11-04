---
title: Priorizar incidentes no Microsoft 365 defender
description: Saiba como priorizar incidentes da fila de incidentes no Microsoft 365 defender
keywords: incidente, fila, visão geral, dispositivos, identidades, usuários, caixa de correio, email, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4369d51ed740af652be632ba0b8752c708d6c719
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877214"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="58c17-104">Priorizar incidentes no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="58c17-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="58c17-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="58c17-105">**Applies to:**</span></span>
- <span data-ttu-id="58c17-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58c17-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="58c17-107">O Microsoft 365 defender aplica a análise de correlação e agrega todos os alertas e investigações relacionados de produtos diferentes em um único incidente.</span><span class="sxs-lookup"><span data-stu-id="58c17-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="58c17-108">O Microsoft 365 defender também dispara alertas exclusivos em atividades que só podem ser identificados como mal-intencionados, dada a visibilidade de ponta a ponta que a Microsoft 365 defender tem em toda a imobiliária e pacote de produtos.</span><span class="sxs-lookup"><span data-stu-id="58c17-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="58c17-109">Fazendo isso, o Microsoft 365 defender narra a história de ataque mais ampla, permitindo que um analista de operações de segurança entenda e lide com ameaças complexas em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="58c17-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="58c17-110">A **Fila de incidentes** exibe um conjunto de incidentes sinalizados de vários dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="58c17-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="58c17-111">Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada.</span><span class="sxs-lookup"><span data-stu-id="58c17-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Imagem da fila de incidentes](../../media/incidents-queue.png) 

<span data-ttu-id="58c17-113">Por padrão, a fila na central de segurança do Microsoft 365 exibe incidentes vistos nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="58c17-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="58c17-114">O incidente mais recente fica na parte superior da lista para que você possa vê-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="58c17-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="58c17-115">A fila de incidentes expõe colunas personalizáveis que lhe dão visibilidade de diferentes características do incidente ou das entidades contidas.</span><span class="sxs-lookup"><span data-stu-id="58c17-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="58c17-116">Isso ajuda você a tomar decisões informadas sobre a priorização de incidentes para lidar.</span><span class="sxs-lookup"><span data-stu-id="58c17-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="58c17-117">Para obter visibilidade adicional em um relance, o nome automático de incidentes gera nomes de incidentes com base em atributos de alerta como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="58c17-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="58c17-118">Isso permite que você entenda rapidamente o escopo do incidente.</span><span class="sxs-lookup"><span data-stu-id="58c17-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="58c17-119">Por exemplo: *incidente de vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="58c17-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="58c17-120">Incidentes que existiam antes da distribuição da nomeação automática de incidentes não terão o nome alterado.</span><span class="sxs-lookup"><span data-stu-id="58c17-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="58c17-121">A fila de incidentes também expõe várias opções de filtragem, que, quando aplicadas, permitem que você realize uma ampla varredura de todos os incidentes existentes no seu ambiente ou decida se concentrar em um cenário ou ameaça específico.</span><span class="sxs-lookup"><span data-stu-id="58c17-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="58c17-122">A aplicação de filtros na fila de incidentes pode ajudar a determinar qual incidente exige atenção imediata.</span><span class="sxs-lookup"><span data-stu-id="58c17-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="58c17-123">Filtros disponíveis</span><span class="sxs-lookup"><span data-stu-id="58c17-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="58c17-124">Atribuído a</span><span class="sxs-lookup"><span data-stu-id="58c17-124">Assigned to</span></span>
<span data-ttu-id="58c17-125">Você pode optar por mostrar alertas que são atribuídos a você ou aqueles tratados pela automação.</span><span class="sxs-lookup"><span data-stu-id="58c17-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="58c17-126">Categorias</span><span class="sxs-lookup"><span data-stu-id="58c17-126">Categories</span></span>
<span data-ttu-id="58c17-127">Escolha categorias para se concentrar em táticas, técnicas ou componentes de ataque específicos vistos.</span><span class="sxs-lookup"><span data-stu-id="58c17-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="58c17-128">Classificação</span><span class="sxs-lookup"><span data-stu-id="58c17-128">Classification</span></span>
<span data-ttu-id="58c17-129">Filtrar incidentes com base nas classificações de conjunto dos alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="58c17-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="58c17-130">Os valores incluem alertas verdadeiros, falsos alertas ou não definidos.</span><span class="sxs-lookup"><span data-stu-id="58c17-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="58c17-131">Confidencialidade de dados</span><span class="sxs-lookup"><span data-stu-id="58c17-131">Data sensitivity</span></span>
<span data-ttu-id="58c17-132">Alguns ataques se concentram no direcionamento para exfiltrar dados confidenciais ou valiosos.</span><span class="sxs-lookup"><span data-stu-id="58c17-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="58c17-133">Ao aplicar um filtro para ver se os dados confidenciais estão envolvidos no incidente, você pode determinar rapidamente se as informações confidenciais estão potencialmente comprometidas e priorizar o tratamento desses incidentes.</span><span class="sxs-lookup"><span data-stu-id="58c17-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="58c17-134">Só é aplicável se a Proteção de Informações da Microsoft estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="58c17-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="58c17-135">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="58c17-135">Device group</span></span>
<span data-ttu-id="58c17-136">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="58c17-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="58c17-137">Estado de investigação</span><span class="sxs-lookup"><span data-stu-id="58c17-137">Investigation state</span></span>
<span data-ttu-id="58c17-138">Filtrar incidentes pelo status de investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="58c17-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="58c17-139">Várias categorias</span><span class="sxs-lookup"><span data-stu-id="58c17-139">Multiple categories</span></span> 
<span data-ttu-id="58c17-140">Você pode optar por ver apenas os incidentes que foram mapeados para várias categorias e podem possivelmente causar mais danos.</span><span class="sxs-lookup"><span data-stu-id="58c17-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="58c17-141">Várias fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="58c17-141">Multiple service sources</span></span> 
<span data-ttu-id="58c17-142">Filtro para ver apenas incidentes que contenham alertas de fontes diferentes (Microsoft defender para ponto de extremidade, Microsoft Cloud app Security, Microsoft defender para identidade, Microsoft defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="58c17-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="58c17-143">Plataforma do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="58c17-143">OS platform</span></span>
<span data-ttu-id="58c17-144">Limitar o modo de exibição fila de incidentes por sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="58c17-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="58c17-145">Fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="58c17-145">Service sources</span></span>
<span data-ttu-id="58c17-146">Ao escolher uma fonte específica, é possível se concentrar em incidentes com pelo menos um alerta da fonte escolhida.</span><span class="sxs-lookup"><span data-stu-id="58c17-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="58c17-147">Severity</span><span class="sxs-lookup"><span data-stu-id="58c17-147">Severity</span></span>
<span data-ttu-id="58c17-148">A gravidade de um incidente indica o impacto que ele pode ter em seus ativos.</span><span class="sxs-lookup"><span data-stu-id="58c17-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="58c17-149">Quanto maior a gravidade, maior o impacto e normalmente requer a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="58c17-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="58c17-150">Status</span><span class="sxs-lookup"><span data-stu-id="58c17-150">Status</span></span>
<span data-ttu-id="58c17-151">Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos.</span><span class="sxs-lookup"><span data-stu-id="58c17-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

>[!IMPORTANT]
><span data-ttu-id="58c17-152">Os filtros de classificação, grupo de dispositivos, estado de investigação e plataforma de SO atualmente só estão disponíveis na visualização pública.</span><span class="sxs-lookup"><span data-stu-id="58c17-152">The Classification, Device group, Investigation state, and OS platform filters are currently only available in public preview.</span></span>


## <a name="next-steps"></a><span data-ttu-id="58c17-153">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="58c17-153">Next steps</span></span>
<span data-ttu-id="58c17-154">Após determinar qual incidente requer a prioridade mais alta, você pode continuar a fazer um trabalho mais investigativo em um incidente.</span><span class="sxs-lookup"><span data-stu-id="58c17-154">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="58c17-155">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="58c17-155">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="58c17-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="58c17-156">See also</span></span>
- [<span data-ttu-id="58c17-157">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="58c17-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="58c17-158">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="58c17-158">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="58c17-159">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="58c17-159">Manage incidents</span></span>](manage-incidents.md)
