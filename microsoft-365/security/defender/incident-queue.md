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
ms.openlocfilehash: 3b381749108d4a75024d9a546c0d3f1631c948ed
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887252"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="c3e40-104">Priorizar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3e40-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c3e40-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c3e40-105">**Applies to:**</span></span>
- <span data-ttu-id="c3e40-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3e40-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c3e40-107">O Microsoft 365 Defender aplica análises de correlação e agrega alertas relacionados e investigações automatizadas de diferentes produtos em um incidente.</span><span class="sxs-lookup"><span data-stu-id="c3e40-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="c3e40-108">O Microsoft 365 Defender também dispara alertas exclusivos sobre atividades que só podem ser identificadas como mal-intencionadas devido à visibilidade de ponta a ponta que o Microsoft 365 Defender tem em todo o pacote de produtos.</span><span class="sxs-lookup"><span data-stu-id="c3e40-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="c3e40-109">Essa exibição fornece aos seus analistas de segurança uma história de ataque mais ampla, que os ajuda a entender melhor e lidar com ameaças complexas em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="c3e40-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="c3e40-110">A **fila de incidentes** mostra uma coleção de incidentes que foram criados em dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c3e40-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="c3e40-111">Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada.</span><span class="sxs-lookup"><span data-stu-id="c3e40-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="c3e40-112">Você pode chegar à fila de incidentes de **Incidentes & alertas** > Incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="c3e40-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exemplo da fila de incidentes":::

<span data-ttu-id="c3e40-114">Por padrão, a fila de incidentes no centro de segurança do Microsoft 365 exibe incidentes vistos nos últimos seis meses.</span><span class="sxs-lookup"><span data-stu-id="c3e40-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="c3e40-115">O incidente mais recente está na parte superior da lista para que você possa vê-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="c3e40-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="c3e40-116">A fila de incidentes tem colunas personalizáveis (selecione **Escolher colunas**) que dão visibilidade a diferentes características do incidente ou das entidades impactadas.</span><span class="sxs-lookup"><span data-stu-id="c3e40-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="c3e40-117">Isso ajuda você a tomar uma decisão informada sobre a priorização de incidentes para análise.</span><span class="sxs-lookup"><span data-stu-id="c3e40-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="c3e40-118">Para obter visibilidade adicional rapidamente, a nomenização automática de incidentes gera nomes de incidentes com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="c3e40-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="c3e40-119">Isso permite que você entenda rapidamente o escopo do incidente.</span><span class="sxs-lookup"><span data-stu-id="c3e40-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="c3e40-120">Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="c3e40-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="c3e40-121">Incidentes que existiam antes da adoção da nomenização automática de incidentes não terão seu nome alterado.</span><span class="sxs-lookup"><span data-stu-id="c3e40-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="c3e40-122">A fila de incidentes também expõe várias opções de filtragem, que, quando aplicadas, permitem que você execute uma ampla varredura de todos os incidentes existentes em seu ambiente ou decida se concentrar em um cenário ou ameaça específico.</span><span class="sxs-lookup"><span data-stu-id="c3e40-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="c3e40-123">A aplicação de filtros na fila de incidentes pode ajudar a determinar qual incidente exige atenção imediata.</span><span class="sxs-lookup"><span data-stu-id="c3e40-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="c3e40-124">Filtros disponíveis</span><span class="sxs-lookup"><span data-stu-id="c3e40-124">Available filters</span></span>

<span data-ttu-id="c3e40-125">Na fila de incidentes padrão, você pode selecionar **Filtros** para ver um painel Filtros, do qual você pode exibir um conjunto filtrado de incidentes.</span><span class="sxs-lookup"><span data-stu-id="c3e40-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="c3e40-126">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="c3e40-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Exemplo do painel filtros para a fila de incidentes":::

<span data-ttu-id="c3e40-128">Esta tabela lista os nomes de filtro disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c3e40-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="c3e40-129">Nome do filtro</span><span class="sxs-lookup"><span data-stu-id="c3e40-129">Filter name</span></span> | <span data-ttu-id="c3e40-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="c3e40-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="c3e40-131">Atribuído a</span><span class="sxs-lookup"><span data-stu-id="c3e40-131">Assigned to</span></span> | <span data-ttu-id="c3e40-132">Você pode optar por mostrar alertas atribuídos a você ou aos manipulados pela automação.</span><span class="sxs-lookup"><span data-stu-id="c3e40-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="c3e40-133">Categorias</span><span class="sxs-lookup"><span data-stu-id="c3e40-133">Categories</span></span> | <span data-ttu-id="c3e40-134">Escolha categorias para se concentrar em táticas, técnicas ou componentes de ataque específicos vistos.</span><span class="sxs-lookup"><span data-stu-id="c3e40-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="c3e40-135">Classificação</span><span class="sxs-lookup"><span data-stu-id="c3e40-135">Classification</span></span> | <span data-ttu-id="c3e40-136">Filtrar incidentes com base nas classificações definidas dos alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="c3e40-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="c3e40-137">Os valores incluem alertas verdadeiros, alertas falsos ou não definidos.</span><span class="sxs-lookup"><span data-stu-id="c3e40-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="c3e40-138">Confidencialidade de dados</span><span class="sxs-lookup"><span data-stu-id="c3e40-138">Data sensitivity</span></span> | <span data-ttu-id="c3e40-139">Alguns ataques se concentram no direcionamento para exfiltrar dados confidenciais ou valiosos.</span><span class="sxs-lookup"><span data-stu-id="c3e40-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="c3e40-140">Ao aplicar um filtro para ver se os dados confidenciais estão envolvidos no incidente, você pode determinar rapidamente se as informações confidenciais estão potencialmente comprometidas e priorizar o tratamento desses incidentes.</span><span class="sxs-lookup"><span data-stu-id="c3e40-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="c3e40-141">Só é aplicável se a Proteção de Informações da Microsoft estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="c3e40-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="c3e40-142">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c3e40-142">Device group</span></span> | <span data-ttu-id="c3e40-143">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="c3e40-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="c3e40-144">Estado da investigação</span><span class="sxs-lookup"><span data-stu-id="c3e40-144">Investigation state</span></span> | <span data-ttu-id="c3e40-145">Filtrar incidentes pelo status da investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="c3e40-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="c3e40-146">Várias categorias</span><span class="sxs-lookup"><span data-stu-id="c3e40-146">Multiple categories</span></span> | <span data-ttu-id="c3e40-147">Você pode optar por ver apenas incidentes mapeados para várias categorias e, portanto, pode causar mais danos.</span><span class="sxs-lookup"><span data-stu-id="c3e40-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="c3e40-148">Várias fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="c3e40-148">Multiple service sources</span></span>  | <span data-ttu-id="c3e40-149">Filtrar para ver apenas incidentes que contenham alertas de fontes diferentes (Microsoft Defender para Ponto de Extremidade, Microsoft Cloud App Security, Microsoft Defender para Identidade, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="c3e40-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="c3e40-150">Plataforma do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="c3e40-150">OS platform</span></span> | <span data-ttu-id="c3e40-151">Limite a exibição de fila de incidentes pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c3e40-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="c3e40-152">Fontes de serviço</span><span class="sxs-lookup"><span data-stu-id="c3e40-152">Service sources</span></span> | <span data-ttu-id="c3e40-153">Ao escolher uma fonte específica, é possível se concentrar em incidentes com pelo menos um alerta da fonte escolhida.</span><span class="sxs-lookup"><span data-stu-id="c3e40-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="c3e40-154">Severity</span><span class="sxs-lookup"><span data-stu-id="c3e40-154">Severity</span></span> | <span data-ttu-id="c3e40-155">A gravidade de um incidente indica o impacto que ele pode ter em seus ativos.</span><span class="sxs-lookup"><span data-stu-id="c3e40-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="c3e40-156">Quanto maior a gravidade, maior o impacto e normalmente exige a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="c3e40-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="c3e40-157">Status</span><span class="sxs-lookup"><span data-stu-id="c3e40-157">Status</span></span> | <span data-ttu-id="c3e40-158">Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos.</span><span class="sxs-lookup"><span data-stu-id="c3e40-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="c3e40-159">Fluxo de trabalho de resposta a incidentes</span><span class="sxs-lookup"><span data-stu-id="c3e40-159">Incident response workflow</span></span>

<span data-ttu-id="c3e40-160">Este é o fluxo de trabalho típico para responder a incidentes:</span><span class="sxs-lookup"><span data-stu-id="c3e40-160">Here's the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="c3e40-161">Identificar e triagem dos incidentes de maior prioridade para investigação e resolução.</span><span class="sxs-lookup"><span data-stu-id="c3e40-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="c3e40-162">Para cada incidente de alta prioridade, inicie uma [investigação:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="c3e40-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="c3e40-163">a.</span><span class="sxs-lookup"><span data-stu-id="c3e40-163">a.</span></span> <span data-ttu-id="c3e40-164">Exibir o resumo do incidente para entender seu escopo e gravidade e quais entidades são afetadas (a **guia Resumo).**</span><span class="sxs-lookup"><span data-stu-id="c3e40-164">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="c3e40-165">b.</span><span class="sxs-lookup"><span data-stu-id="c3e40-165">b.</span></span> <span data-ttu-id="c3e40-166">Comece a olhar para os alertas para entender sua origem, escopo e gravidade (a **guia Alertas).**</span><span class="sxs-lookup"><span data-stu-id="c3e40-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="c3e40-167">c.</span><span class="sxs-lookup"><span data-stu-id="c3e40-167">c.</span></span> <span data-ttu-id="c3e40-168">Conforme necessário, reúna informações sobre dispositivos, usuários e caixas de correio afetados (as guias **Dispositivos,** **Usuários** e **Caixas** de Correio).</span><span class="sxs-lookup"><span data-stu-id="c3e40-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="c3e40-169">d.</span><span class="sxs-lookup"><span data-stu-id="c3e40-169">d.</span></span> <span data-ttu-id="c3e40-170">Veja como o Microsoft 365 Defender resolveu automaticamente alguns alertas (a guia **Investigações).**</span><span class="sxs-lookup"><span data-stu-id="c3e40-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="c3e40-171">e.</span><span class="sxs-lookup"><span data-stu-id="c3e40-171">e.</span></span> <span data-ttu-id="c3e40-172">Conforme necessário, use informações no conjunto de dados do incidente para obter mais informações (a **guia Evidências e Resposta).**</span><span class="sxs-lookup"><span data-stu-id="c3e40-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

   <span data-ttu-id="c3e40-173">À medida que você investiga, você deve se preocupar com:</span><span class="sxs-lookup"><span data-stu-id="c3e40-173">As you investigate, you should be concerned with:</span></span>

   - <span data-ttu-id="c3e40-174">Contenção: reduzindo qualquer impacto adicional em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c3e40-174">Containment: Reducing any additional impact on your tenant.</span></span>
   - <span data-ttu-id="c3e40-175">Erradicação: Removendo a ameaça de segurança.</span><span class="sxs-lookup"><span data-stu-id="c3e40-175">Eradication: Removing the security threat.</span></span>
   - <span data-ttu-id="c3e40-176">Recuperação: restaurando os recursos do locatário para o estado em que estavam antes do incidente.</span><span class="sxs-lookup"><span data-stu-id="c3e40-176">Recovery: Restoring your tenant resources to the state they were in before the incident.</span></span>

3. <span data-ttu-id="c3e40-177">Depois de resolver o incidente, aproveite o tempo para:</span><span class="sxs-lookup"><span data-stu-id="c3e40-177">After you resolve the incident, take the time to:</span></span>

   - <span data-ttu-id="c3e40-178">Entenda o tipo de ataque e seu impacto.</span><span class="sxs-lookup"><span data-stu-id="c3e40-178">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="c3e40-179">Pesquise o ataque na comunidade de segurança para uma tendência de ataque de segurança.</span><span class="sxs-lookup"><span data-stu-id="c3e40-179">Research the attack in the security community for a security attack trend.</span></span>
   - <span data-ttu-id="c3e40-180">Lembre-se do fluxo de trabalho usado para resolver o incidente e atualizar seus fluxos de trabalho padrão e playbooks conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c3e40-180">Recall the workflow you used to resolve the incident and update your standard workflows and playbooks as needed.</span></span>
   - <span data-ttu-id="c3e40-181">Determine se as alterações na postura de segurança são necessárias e tome as etapas para implementá-las.</span><span class="sxs-lookup"><span data-stu-id="c3e40-181">Determine whether changes in your security posture are needed and take the steps to implement them.</span></span>

<span data-ttu-id="c3e40-182">Aqui está um resumo do processo básico.</span><span class="sxs-lookup"><span data-stu-id="c3e40-182">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="O processo básico para investigar incidentes":::

## <a name="next-step"></a><span data-ttu-id="c3e40-184">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c3e40-184">Next step</span></span>

<span data-ttu-id="c3e40-185">Depois de determinar qual incidente requer a maior prioridade, selecione-o e inicie a [investigação.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="c3e40-185">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3e40-186">Confira também</span><span class="sxs-lookup"><span data-stu-id="c3e40-186">See also</span></span>
- [<span data-ttu-id="c3e40-187">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="c3e40-187">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c3e40-188">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="c3e40-188">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="c3e40-189">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="c3e40-189">Manage incidents</span></span>](manage-incidents.md)
