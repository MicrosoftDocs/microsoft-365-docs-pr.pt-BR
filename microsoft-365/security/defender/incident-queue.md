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
ms.openlocfilehash: c3efff1e7ebb3a5e868ede018512d12cf38e38fc
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939701"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="1edce-104">Priorizar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1edce-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1edce-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1edce-105">**Applies to:**</span></span>
- <span data-ttu-id="1edce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1edce-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1edce-107">O Microsoft 365 Defender aplica análises de correlação e agrega alertas relacionados e investigações automatizadas de diferentes produtos em um incidente.</span><span class="sxs-lookup"><span data-stu-id="1edce-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="1edce-108">O Microsoft 365 Defender também dispara alertas exclusivos sobre atividades que só podem ser identificadas como mal-intencionadas devido à visibilidade de ponta a ponta que o Microsoft 365 Defender tem em todo o pacote de produtos.</span><span class="sxs-lookup"><span data-stu-id="1edce-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="1edce-109">Essa exibição fornece aos seus analistas de segurança uma história de ataque mais ampla, que os ajuda a entender melhor e lidar com ameaças complexas em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="1edce-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="1edce-110">A **fila de incidentes** mostra uma coleção de incidentes que foram criados em dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="1edce-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="1edce-111">Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada.</span><span class="sxs-lookup"><span data-stu-id="1edce-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="1edce-112">Você pode chegar à fila de incidentes de **Incidentes & alertas** > Incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="1edce-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exemplo da fila de incidentes":::

<span data-ttu-id="1edce-114">Por padrão, a fila de incidentes no centro de segurança do Microsoft 365 exibe incidentes vistos nos últimos seis meses.</span><span class="sxs-lookup"><span data-stu-id="1edce-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="1edce-115">O incidente mais recente está na parte superior da lista para que você possa vê-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="1edce-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="1edce-116">A fila de incidentes tem colunas personalizáveis (selecione **Escolher colunas**) que dão visibilidade a diferentes características do incidente ou das entidades impactadas.</span><span class="sxs-lookup"><span data-stu-id="1edce-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="1edce-117">Isso ajuda você a tomar uma decisão informada sobre a priorização de incidentes para análise.</span><span class="sxs-lookup"><span data-stu-id="1edce-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="1edce-118">Para obter visibilidade adicional rapidamente, a nomenização automática de incidentes gera nomes de incidentes com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="1edce-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="1edce-119">Isso permite que você entenda rapidamente o escopo do incidente.</span><span class="sxs-lookup"><span data-stu-id="1edce-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="1edce-120">Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="1edce-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="1edce-121">Incidentes que existiam antes da adoção da nomenização automática de incidentes não terão seu nome alterado.</span><span class="sxs-lookup"><span data-stu-id="1edce-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="1edce-122">A fila de incidentes também expõe várias opções de filtragem, que, quando aplicadas, permitem que você execute uma ampla varredura de todos os incidentes existentes em seu ambiente ou decida se concentrar em um cenário ou ameaça específico.</span><span class="sxs-lookup"><span data-stu-id="1edce-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="1edce-123">A aplicação de filtros na fila de incidentes pode ajudar a determinar qual incidente exige atenção imediata.</span><span class="sxs-lookup"><span data-stu-id="1edce-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="1edce-124">Filtros disponíveis</span><span class="sxs-lookup"><span data-stu-id="1edce-124">Available filters</span></span>

<span data-ttu-id="1edce-125">Na fila de incidentes padrão, você pode selecionar **Filtros** para ver um painel Filtros, do qual você pode exibir um conjunto filtrado de incidentes.</span><span class="sxs-lookup"><span data-stu-id="1edce-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="1edce-126">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="1edce-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Exemplo do painel filtros para a fila de incidentes":::

<span data-ttu-id="1edce-128">Esta tabela lista os nomes de filtro disponíveis.</span><span class="sxs-lookup"><span data-stu-id="1edce-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="1edce-129">Nome do filtro</span><span class="sxs-lookup"><span data-stu-id="1edce-129">Filter name</span></span> | <span data-ttu-id="1edce-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="1edce-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="1edce-131">Atribuído a</span><span class="sxs-lookup"><span data-stu-id="1edce-131">Assigned to</span></span> | <span data-ttu-id="1edce-132">Você pode optar por mostrar alertas atribuídos a você ou aos manipulados pela automação.</span><span class="sxs-lookup"><span data-stu-id="1edce-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="1edce-133">Categorias</span><span class="sxs-lookup"><span data-stu-id="1edce-133">Categories</span></span> | <span data-ttu-id="1edce-134">Escolha categorias para se concentrar em táticas, técnicas ou componentes de ataque específicos vistos.</span><span class="sxs-lookup"><span data-stu-id="1edce-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="1edce-135">Classificação</span><span class="sxs-lookup"><span data-stu-id="1edce-135">Classification</span></span> | <span data-ttu-id="1edce-136">Filtrar incidentes com base nas classificações definidas dos alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="1edce-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="1edce-137">Os valores incluem alertas verdadeiros, alertas falsos ou não definidos.</span><span class="sxs-lookup"><span data-stu-id="1edce-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="1edce-138">Confidencialidade de dados</span><span class="sxs-lookup"><span data-stu-id="1edce-138">Data sensitivity</span></span> | <span data-ttu-id="1edce-139">Alguns ataques se concentram no direcionamento para exfiltrar dados confidenciais ou valiosos.</span><span class="sxs-lookup"><span data-stu-id="1edce-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="1edce-140">Ao aplicar um filtro para ver se os dados confidenciais estão envolvidos no incidente, você pode determinar rapidamente se as informações confidenciais estão potencialmente comprometidas e priorizar o tratamento desses incidentes.</span><span class="sxs-lookup"><span data-stu-id="1edce-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="1edce-141">Só é aplicável se a Proteção de Informações da Microsoft estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="1edce-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="1edce-142">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="1edce-142">Device group</span></span> | <span data-ttu-id="1edce-143">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="1edce-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="1edce-144">Estado da investigação</span><span class="sxs-lookup"><span data-stu-id="1edce-144">Investigation state</span></span> | <span data-ttu-id="1edce-145">Filtrar incidentes pelo status da investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="1edce-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="1edce-146">Várias categorias</span><span class="sxs-lookup"><span data-stu-id="1edce-146">Multiple categories</span></span> | <span data-ttu-id="1edce-147">Você pode optar por ver apenas incidentes mapeados para várias categorias e, portanto, pode causar mais danos.</span><span class="sxs-lookup"><span data-stu-id="1edce-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="1edce-148">Várias fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="1edce-148">Multiple service sources</span></span>  | <span data-ttu-id="1edce-149">Filtrar para ver apenas incidentes que contenham alertas de fontes diferentes (Microsoft Defender para Ponto de Extremidade, Microsoft Cloud App Security, Microsoft Defender para Identidade, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="1edce-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="1edce-150">Plataforma do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="1edce-150">OS platform</span></span> | <span data-ttu-id="1edce-151">Limite a exibição de fila de incidentes pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1edce-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="1edce-152">Fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="1edce-152">Service sources</span></span> | <span data-ttu-id="1edce-153">Ao escolher uma fonte específica, é possível se concentrar em incidentes com pelo menos um alerta da fonte escolhida.</span><span class="sxs-lookup"><span data-stu-id="1edce-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="1edce-154">Severity</span><span class="sxs-lookup"><span data-stu-id="1edce-154">Severity</span></span> | <span data-ttu-id="1edce-155">A gravidade de um incidente indica o impacto que ele pode ter em seus ativos.</span><span class="sxs-lookup"><span data-stu-id="1edce-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="1edce-156">Quanto maior a gravidade, maior o impacto e normalmente exige a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="1edce-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="1edce-157">Status</span><span class="sxs-lookup"><span data-stu-id="1edce-157">Status</span></span> | <span data-ttu-id="1edce-158">Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos.</span><span class="sxs-lookup"><span data-stu-id="1edce-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="1edce-159">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1edce-159">Next step</span></span>

<span data-ttu-id="1edce-160">Depois de determinar qual incidente requer a maior prioridade, selecione-o e inicie a [análise.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="1edce-160">After you've determined which incident requires the highest priority, select it and begin your [analysis](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1edce-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="1edce-161">See also</span></span>
- [<span data-ttu-id="1edce-162">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="1edce-162">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1edce-163">Analisar incidentes</span><span class="sxs-lookup"><span data-stu-id="1edce-163">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="1edce-164">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="1edce-164">Manage incidents</span></span>](manage-incidents.md)
