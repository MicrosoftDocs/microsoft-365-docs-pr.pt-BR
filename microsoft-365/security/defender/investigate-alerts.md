---
title: Investigar alertas no Microsoft 365 Defender
description: Investigue alertas vistos em dispositivos, usuários e caixas de correio.
keywords: incidentes, alertas, investigar, analisar, responder, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
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
ms.openlocfilehash: 6a34269c414f59d40c9160d5728159ed9cddf976
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651339"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="8120c-104">Investigar alertas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8120c-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8120c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8120c-105">**Applies to:**</span></span>
- <span data-ttu-id="8120c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8120c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8120c-107">Os alertas são a base de todos os incidentes e indicam a ocorrência de eventos mal-intencionados ou suspeitos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="8120c-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="8120c-108">Os alertas geralmente fazem parte de um ataque mais amplo e fornecem pistas sobre um incidente.</span><span class="sxs-lookup"><span data-stu-id="8120c-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="8120c-109">No Microsoft 365 Defender, alertas relacionados são agregados juntos a [incidentes de formulário.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8120c-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="8120c-110">Os incidentes sempre fornecerão o contexto mais amplo de um ataque, no entanto, a análise de alertas pode ser valiosa quando uma análise mais profunda é necessária.</span><span class="sxs-lookup"><span data-stu-id="8120c-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="8120c-111">A **fila Alertas** mostra o conjunto atual de alertas.</span><span class="sxs-lookup"><span data-stu-id="8120c-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="8120c-112">Você pode chegar à fila de alertas de **Incidentes & alertas** > alertas sobre o início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="8120c-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Exemplo da fila de alertas":::

<span data-ttu-id="8120c-114">Alertas de diferentes soluções de segurança da Microsoft, como o Microsoft Defender para Ponto de Extremidade, o Microsoft Defender para Office 365 e Microsoft 365 Defender aparecem aqui.</span><span class="sxs-lookup"><span data-stu-id="8120c-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="8120c-115">Por padrão, a fila de alertas no centro de segurança Microsoft 365 exibe os alertas novos e em andamento dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="8120c-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="8120c-116">O alerta mais recente está na parte superior da lista para que você possa vê-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="8120c-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="8120c-117">Na fila de alertas padrão, você pode selecionar **Filtros** para ver um painel **Filtros,** do qual você pode especificar um subconjunto dos alertas.</span><span class="sxs-lookup"><span data-stu-id="8120c-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="8120c-118">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8120c-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Exemplo do painel filtros para a fila de alertas":::

<span data-ttu-id="8120c-120">Você pode filtrar alertas de acordo com estes critérios:</span><span class="sxs-lookup"><span data-stu-id="8120c-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="8120c-121">Severity</span><span class="sxs-lookup"><span data-stu-id="8120c-121">Severity</span></span>
- <span data-ttu-id="8120c-122">Status</span><span class="sxs-lookup"><span data-stu-id="8120c-122">Status</span></span>
- <span data-ttu-id="8120c-123">Categoria</span><span class="sxs-lookup"><span data-stu-id="8120c-123">Category</span></span>
- <span data-ttu-id="8120c-124">Fonte de detecção</span><span class="sxs-lookup"><span data-stu-id="8120c-124">Detection source</span></span>
- <span data-ttu-id="8120c-125">Tags</span><span class="sxs-lookup"><span data-stu-id="8120c-125">Tags</span></span>
- <span data-ttu-id="8120c-126">Política</span><span class="sxs-lookup"><span data-stu-id="8120c-126">Policy</span></span>
- <span data-ttu-id="8120c-127">Ativos afetados</span><span class="sxs-lookup"><span data-stu-id="8120c-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="8120c-128">Analisar um alerta</span><span class="sxs-lookup"><span data-stu-id="8120c-128">Analyze an alert</span></span>

<span data-ttu-id="8120c-129">Para ver a página de alerta principal, selecione o nome do alerta.</span><span class="sxs-lookup"><span data-stu-id="8120c-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="8120c-130">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8120c-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exemplo da página de detalhes de um alerta no centro Microsoft 365 segurança":::

<span data-ttu-id="8120c-132">Você também pode selecionar **a ação Abrir a página de alerta** principal no painel **Gerenciar** alerta.</span><span class="sxs-lookup"><span data-stu-id="8120c-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="8120c-133">Uma página de alerta é composta por estas seções:</span><span class="sxs-lookup"><span data-stu-id="8120c-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="8120c-134">História do alerta, que é a cadeia de eventos e alertas relacionados a esse alerta em ordem cronológica</span><span class="sxs-lookup"><span data-stu-id="8120c-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="8120c-135">Detalhes de resumo</span><span class="sxs-lookup"><span data-stu-id="8120c-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exemplo da página de detalhes de um alerta no centro Microsoft 365 segurança":::

<span data-ttu-id="8120c-137">Ao longo de uma página de alerta, você pode selecionar as regiões (**...**) ao lado de qualquer entidade para ver ações disponíveis, como abrir a página de alerta ou vincular o alerta a outro incidente.</span><span class="sxs-lookup"><span data-stu-id="8120c-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="8120c-138">Analisar ativos afetados</span><span class="sxs-lookup"><span data-stu-id="8120c-138">Analyze affected assets</span></span>

<span data-ttu-id="8120c-139">A **seção Ações realizadas** tem uma lista de ativos afetados, como caixas de correio, dispositivos e usuários afetados por esse alerta.</span><span class="sxs-lookup"><span data-stu-id="8120c-139">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="8120c-140">Você também pode selecionar **Exibir no centro de** ações para exibir a guia **Histórico** do **Centro** de Ações no centro de Microsoft 365 de segurança.</span><span class="sxs-lookup"><span data-stu-id="8120c-140">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="8120c-141">Rastrear a função de um alerta no artigo de alerta</span><span class="sxs-lookup"><span data-stu-id="8120c-141">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="8120c-142">O artigo de alerta exibe todos os ativos ou entidades relacionados ao alerta em uma exibição de árvore de processo.</span><span class="sxs-lookup"><span data-stu-id="8120c-142">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="8120c-143">O alerta no título é aquele em foco quando você aterra pela primeira vez na página do alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="8120c-143">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="8120c-144">Os ativos no artigo de alerta são expansíveis e clicáveis.</span><span class="sxs-lookup"><span data-stu-id="8120c-144">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="8120c-145">Eles fornecem informações adicionais e aceleram sua resposta permitindo que você tome medidas imediatamente no contexto da página de alerta.</span><span class="sxs-lookup"><span data-stu-id="8120c-145">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="8120c-146">A seção de texto do alerta pode conter mais de um alerta, com alertas adicionais relacionados à mesma árvore de execução que aparece antes ou depois do alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="8120c-146">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="8120c-147">Exibir mais informações de alerta na página de detalhes</span><span class="sxs-lookup"><span data-stu-id="8120c-147">View more alert information on the details page</span></span>

<span data-ttu-id="8120c-148">A página de detalhes mostra os detalhes do alerta selecionado, com detalhes e ações relacionadas a ele.</span><span class="sxs-lookup"><span data-stu-id="8120c-148">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="8120c-149">Se você selecionar qualquer um dos ativos ou entidades afetados no histórico de alerta, a página de detalhes será mudada para fornecer informações contextuais e ações para o objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="8120c-149">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="8120c-150">Depois de selecionar uma entidade de interesse, a página de detalhes muda para exibir informações sobre o tipo de entidade selecionado, informações históricas quando ela estiver disponível e opções para tomar medidas nessa entidade diretamente na página de alerta.</span><span class="sxs-lookup"><span data-stu-id="8120c-150">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="8120c-151">Gerenciar alertas</span><span class="sxs-lookup"><span data-stu-id="8120c-151">Manage alerts</span></span>

<span data-ttu-id="8120c-152">Para gerenciar um alerta, selecione o alerta na fila de alertas em sua linha para ver um **painel Gerenciar** alerta.</span><span class="sxs-lookup"><span data-stu-id="8120c-152">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="8120c-153">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8120c-153">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Exemplo do painel de resumo para um alerta":::

<span data-ttu-id="8120c-155">O **painel Gerenciar** alerta permite que você especifique:</span><span class="sxs-lookup"><span data-stu-id="8120c-155">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="8120c-156">O status do alerta (Novo, Resolvido, Em andamento).</span><span class="sxs-lookup"><span data-stu-id="8120c-156">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="8120c-157">A classificação do alerta (Não definido, Alerta Verdadeiro, Alerta Falso).</span><span class="sxs-lookup"><span data-stu-id="8120c-157">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="8120c-158">Para a classificação como um alerta verdadeiro, o tipo de ameaça para o alerta no campo **Determinação.**</span><span class="sxs-lookup"><span data-stu-id="8120c-158">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="8120c-159">Um comentário sobre o alerta.</span><span class="sxs-lookup"><span data-stu-id="8120c-159">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="8120c-160">Uma maneira de gerenciar o alerta por meio do uso de marcas.</span><span class="sxs-lookup"><span data-stu-id="8120c-160">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="8120c-161">O recurso de marcação do Microsoft Defender para Office 365 está sendo gradualmente lançado e está atualmente em visualização.</span><span class="sxs-lookup"><span data-stu-id="8120c-161">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="8120c-162">Atualmente, os nomes de marcas modificadas só são aplicados a alertas criados *após* a atualização.</span><span class="sxs-lookup"><span data-stu-id="8120c-162">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="8120c-163">Alertas gerados antes da modificação não refletirão o nome da marca atualizado.</span><span class="sxs-lookup"><span data-stu-id="8120c-163">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="8120c-164">Neste painel, você também pode executar estas ações adicionais:</span><span class="sxs-lookup"><span data-stu-id="8120c-164">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="8120c-165">Abra a página de alerta principal</span><span class="sxs-lookup"><span data-stu-id="8120c-165">Open the main alert page</span></span>
- <span data-ttu-id="8120c-166">Consultar um especialista em ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8120c-166">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="8120c-167">Exibir envio</span><span class="sxs-lookup"><span data-stu-id="8120c-167">View submission</span></span>
- <span data-ttu-id="8120c-168">Link para outro incidente</span><span class="sxs-lookup"><span data-stu-id="8120c-168">Link to another incident</span></span>
- <span data-ttu-id="8120c-169">Consulte o alerta em uma linha do tempo</span><span class="sxs-lookup"><span data-stu-id="8120c-169">See the alert in a timeline</span></span>
- <span data-ttu-id="8120c-170">Criar uma regra de supressão</span><span class="sxs-lookup"><span data-stu-id="8120c-170">Create a suppression rule</span></span>

<span data-ttu-id="8120c-171">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8120c-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Exemplo das ações em um alerta no centro Microsoft 365 segurança":::

<span data-ttu-id="8120c-173">A lista de ações adicionais depende do tipo de alerta.</span><span class="sxs-lookup"><span data-stu-id="8120c-173">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="8120c-174">Resolver um alerta</span><span class="sxs-lookup"><span data-stu-id="8120c-174">Resolve an alert</span></span>

<span data-ttu-id="8120c-175">Depois de terminar de analisar um alerta e ele  puder ser resolvido, vá para o  painel Gerenciar alerta para o alerta e marque o status dele como Resolvido e classifique-o como um alerta **False** ou **Alerta** True.</span><span class="sxs-lookup"><span data-stu-id="8120c-175">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="8120c-176">Para alertas verdadeiros, especifique o tipo de ameaça do alerta no campo **Determinação.**</span><span class="sxs-lookup"><span data-stu-id="8120c-176">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="8120c-177">Classificar alertas e especificar sua determinação ajuda a ajustar o Microsoft 365 Defender para fornecer alertas mais verdadeiros e menos alertas falsos.</span><span class="sxs-lookup"><span data-stu-id="8120c-177">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8120c-178">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8120c-178">Next steps</span></span>

<span data-ttu-id="8120c-179">Conforme necessário para incidentes no processo, continue sua [investigação](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="8120c-179">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8120c-180">Confira também</span><span class="sxs-lookup"><span data-stu-id="8120c-180">See also</span></span>

- [<span data-ttu-id="8120c-181">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="8120c-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="8120c-182">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="8120c-182">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="8120c-183">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="8120c-183">Investigate incidents</span></span>](investigate-incidents.md)
