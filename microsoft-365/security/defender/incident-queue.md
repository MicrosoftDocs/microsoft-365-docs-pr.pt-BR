---
title: Priorizar incidentes no Microsoft 365 Defender
description: Saiba como filtrar incidentes da fila de incidentes no Microsoft 365 Defender
keywords: incident, queue, overview, devices, identities, users, mailbox, email, incidents, analyze, response
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: a3b6edda36d2872177d9a88f3259220dcf2e76f3
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291310"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="f34b1-104">Priorizar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f34b1-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f34b1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f34b1-105">**Applies to:**</span></span>
- <span data-ttu-id="f34b1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f34b1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f34b1-107">Microsoft 365 O Defender aplica análises de correlação e agrega alertas relacionados e investigações automatizadas de diferentes produtos em um incidente.</span><span class="sxs-lookup"><span data-stu-id="f34b1-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="f34b1-108">Microsoft 365 O Defender também dispara alertas exclusivos sobre atividades que só podem ser identificadas como mal-intencionadas devido à visibilidade de ponta a ponta que o Microsoft 365 Defender tem em todo o pacote de produtos.</span><span class="sxs-lookup"><span data-stu-id="f34b1-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="f34b1-109">Essa exibição fornece aos seus analistas de segurança uma história de ataque mais ampla, que os ajuda a entender melhor e lidar com ameaças complexas em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="f34b1-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="f34b1-110">A **fila de incidentes** mostra uma coleção de incidentes que foram criados em dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="f34b1-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="f34b1-111">Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada.</span><span class="sxs-lookup"><span data-stu-id="f34b1-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="f34b1-112">Você pode chegar à fila de incidentes & alertas > **Incidentes** no início rápido do centro de segurança Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f34b1-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="f34b1-113">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="f34b1-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exemplo da fila de incidentes":::

<span data-ttu-id="f34b1-115">A **seção Incidentes e alertas** mais recentes mostra um gráfico do número de alertas recebidos e incidentes criados nas últimas 24 horas.</span><span class="sxs-lookup"><span data-stu-id="f34b1-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="f34b1-116">Por padrão, a fila de incidentes no centro de segurança Microsoft 365 exibe incidentes vistos nos últimos seis meses.</span><span class="sxs-lookup"><span data-stu-id="f34b1-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="f34b1-117">O incidente mais recente está na parte superior da lista para que você possa vê-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="f34b1-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="f34b1-118">A fila de incidentes tem colunas personalizáveis (selecione **Escolher colunas**) que dão visibilidade a diferentes características do incidente ou das entidades impactadas.</span><span class="sxs-lookup"><span data-stu-id="f34b1-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="f34b1-119">Isso ajuda você a tomar uma decisão informada sobre a priorização de incidentes para análise.</span><span class="sxs-lookup"><span data-stu-id="f34b1-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="f34b1-120">Para obter visibilidade adicional rapidamente, a nomenização automática de incidentes gera nomes de incidentes com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="f34b1-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="f34b1-121">Isso permite que você entenda rapidamente o escopo do incidente.</span><span class="sxs-lookup"><span data-stu-id="f34b1-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="f34b1-122">Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="f34b1-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="f34b1-123">Incidentes que existiam antes da adoção da nomenização automática de incidentes não terão seu nome alterado.</span><span class="sxs-lookup"><span data-stu-id="f34b1-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="f34b1-124">A fila de incidentes também expõe várias opções de filtragem, que, quando aplicadas, permitem que você execute uma ampla varredura de todos os incidentes existentes em seu ambiente ou decida se concentrar em um cenário ou ameaça específico.</span><span class="sxs-lookup"><span data-stu-id="f34b1-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="f34b1-125">A aplicação de filtros na fila de incidentes pode ajudar a determinar qual incidente exige atenção imediata.</span><span class="sxs-lookup"><span data-stu-id="f34b1-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="f34b1-126">Filtros disponíveis</span><span class="sxs-lookup"><span data-stu-id="f34b1-126">Available filters</span></span>

<span data-ttu-id="f34b1-127">Na fila de incidentes padrão, você pode selecionar **Filtros** para ver um painel Filtros, do qual você pode exibir um conjunto filtrado de incidentes.</span><span class="sxs-lookup"><span data-stu-id="f34b1-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="f34b1-128">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="f34b1-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Exemplo do painel filtros para a fila de incidentes":::

<span data-ttu-id="f34b1-130">Esta tabela lista os nomes de filtro disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f34b1-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="f34b1-131">Nome do filtro</span><span class="sxs-lookup"><span data-stu-id="f34b1-131">Filter name</span></span> | <span data-ttu-id="f34b1-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="f34b1-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="f34b1-133">Atribuído a</span><span class="sxs-lookup"><span data-stu-id="f34b1-133">Assigned to</span></span> | <span data-ttu-id="f34b1-134">Você pode optar por mostrar alertas atribuídos a você ou aos manipulados pela automação.</span><span class="sxs-lookup"><span data-stu-id="f34b1-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="f34b1-135">Categorias</span><span class="sxs-lookup"><span data-stu-id="f34b1-135">Categories</span></span> | <span data-ttu-id="f34b1-136">Escolha categorias para se concentrar em táticas, técnicas ou componentes de ataque específicos vistos.</span><span class="sxs-lookup"><span data-stu-id="f34b1-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="f34b1-137">Classificação</span><span class="sxs-lookup"><span data-stu-id="f34b1-137">Classification</span></span> | <span data-ttu-id="f34b1-138">Filtrar incidentes com base nas classificações definidas dos alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="f34b1-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="f34b1-139">Os valores incluem alertas verdadeiros, alertas falsos ou não definidos.</span><span class="sxs-lookup"><span data-stu-id="f34b1-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="f34b1-140">Confidencialidade de dados</span><span class="sxs-lookup"><span data-stu-id="f34b1-140">Data sensitivity</span></span> | <span data-ttu-id="f34b1-141">Alguns ataques se concentram no direcionamento para exfiltrar dados confidenciais ou valiosos.</span><span class="sxs-lookup"><span data-stu-id="f34b1-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="f34b1-142">Ao aplicar um filtro para ver se os dados confidenciais estão envolvidos no incidente, você pode determinar rapidamente se as informações confidenciais estão potencialmente comprometidas e priorizar o tratamento desses incidentes.</span><span class="sxs-lookup"><span data-stu-id="f34b1-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="f34b1-143">Só é aplicável se a Proteção de Informações da Microsoft estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="f34b1-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="f34b1-144">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f34b1-144">Device group</span></span> | <span data-ttu-id="f34b1-145">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="f34b1-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="f34b1-146">Estado da investigação</span><span class="sxs-lookup"><span data-stu-id="f34b1-146">Investigation state</span></span> | <span data-ttu-id="f34b1-147">Filtrar incidentes pelo status da investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="f34b1-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="f34b1-148">Várias categorias</span><span class="sxs-lookup"><span data-stu-id="f34b1-148">Multiple categories</span></span> | <span data-ttu-id="f34b1-149">Você pode optar por ver apenas incidentes mapeados para várias categorias e, portanto, pode causar mais danos.</span><span class="sxs-lookup"><span data-stu-id="f34b1-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="f34b1-150">Várias fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="f34b1-150">Multiple service sources</span></span>  | <span data-ttu-id="f34b1-151">Filtrar para ver apenas incidentes que contenham alertas de fontes diferentes (Microsoft Defender para Ponto de Extremidade, Microsoft Cloud App Security, Microsoft Defender para Identidade, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="f34b1-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="f34b1-152">Plataforma do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f34b1-152">OS platform</span></span> | <span data-ttu-id="f34b1-153">Limite a exibição de fila de incidentes pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="f34b1-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="f34b1-154">Fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="f34b1-154">Service sources</span></span> | <span data-ttu-id="f34b1-155">Ao escolher uma fonte específica, é possível se concentrar em incidentes com pelo menos um alerta da fonte escolhida.</span><span class="sxs-lookup"><span data-stu-id="f34b1-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="f34b1-156">Severity</span><span class="sxs-lookup"><span data-stu-id="f34b1-156">Severity</span></span> | <span data-ttu-id="f34b1-157">A gravidade de um incidente indica o impacto que ele pode ter em seus ativos.</span><span class="sxs-lookup"><span data-stu-id="f34b1-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="f34b1-158">Quanto maior a gravidade, maior o impacto e normalmente exige a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="f34b1-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="f34b1-159">Status</span><span class="sxs-lookup"><span data-stu-id="f34b1-159">Status</span></span> | <span data-ttu-id="f34b1-160">Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos.</span><span class="sxs-lookup"><span data-stu-id="f34b1-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-steps"></a><span data-ttu-id="f34b1-161">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f34b1-161">Next steps</span></span>

<span data-ttu-id="f34b1-162">Depois de determinar qual incidente exige a maior prioridade, selecione-o e:</span><span class="sxs-lookup"><span data-stu-id="f34b1-162">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="f34b1-163">[Gerencie](manage-incidents.md) as propriedades do incidente para marcas, atribuição a um analista de segurança e comentários.</span><span class="sxs-lookup"><span data-stu-id="f34b1-163">[Manage](manage-incidents.md) the properties of the incident for tags, assignment to a security analyst, and comments.</span></span>
- <span data-ttu-id="f34b1-164">Comece sua [investigação.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="f34b1-164">Begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f34b1-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="f34b1-165">See also</span></span>
- [<span data-ttu-id="f34b1-166">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="f34b1-166">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f34b1-167">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="f34b1-167">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f34b1-168">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="f34b1-168">Manage incidents</span></span>](manage-incidents.md)
