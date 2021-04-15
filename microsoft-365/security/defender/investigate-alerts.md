---
title: Investigar alertas no Microsoft 365 Defender
description: Investigue alertas vistos em dispositivos, usuários e caixas de correio.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
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
ms.openlocfilehash: 601a8674327c424592c65014793599dc19b2bcd3
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51759427"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="961db-104">Investigar alertas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="961db-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="961db-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="961db-105">**Applies to:**</span></span>
- <span data-ttu-id="961db-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="961db-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="961db-107">Os alertas são a base de todos os incidentes e indicam a ocorrência de eventos mal-intencionados ou suspeitos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="961db-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="961db-108">Os alertas geralmente fazem parte de um ataque mais amplo e fornecem pistas sobre um incidente.</span><span class="sxs-lookup"><span data-stu-id="961db-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="961db-109">No Microsoft 365 Defender, os alertas relacionados são agregados em incidentes de formulário.</span><span class="sxs-lookup"><span data-stu-id="961db-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="961db-110">Os incidentes sempre fornecerão o contexto mais amplo de um ataque, no entanto, a investigação de alertas pode ser valiosa quando uma análise mais profunda é necessária.</span><span class="sxs-lookup"><span data-stu-id="961db-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="961db-111">Usando páginas de alerta em investigações</span><span class="sxs-lookup"><span data-stu-id="961db-111">Using alert pages in investigations</span></span>

<span data-ttu-id="961db-112">Na guia Alertas de qualquer página de incidente, selecionar um alerta o leva às páginas de alerta individuais.</span><span class="sxs-lookup"><span data-stu-id="961db-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="961db-113">Uma página de alerta é composta por três seções: ativos afetados, o alerta e o painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="961db-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![Imagem da página de alerta de exemplo](../../media/new-alert-page2.png)

<span data-ttu-id="961db-115">Ao longo de uma página de alerta, você pode selecionar o ícone de três pontos (**...**) ao lado de qualquer entidade para que você possa ver ações disponíveis, como abrir a página de ativo específica ou realizar etapas de correção específicas.</span><span class="sxs-lookup"><span data-stu-id="961db-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="961db-116">Analisar ativos afetados</span><span class="sxs-lookup"><span data-stu-id="961db-116">Analyze affected assets</span></span>
<span data-ttu-id="961db-117">A seção ativos afetados lista caixas de correio, dispositivos e usuários afetados por esse alerta.</span><span class="sxs-lookup"><span data-stu-id="961db-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="961db-118">Selecionar qualquer um dos cartões de ativos preenche o painel de detalhes com informações, incluindo outros alertas que ocorreram envolvendo os ativos, se for o caso.</span><span class="sxs-lookup"><span data-stu-id="961db-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="961db-119">Rastrear a função de um alerta no artigo de alerta</span><span class="sxs-lookup"><span data-stu-id="961db-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="961db-120">O artigo de alerta exibe todos os ativos ou entidades relacionados ao alerta em uma exibição de árvore de processo.</span><span class="sxs-lookup"><span data-stu-id="961db-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="961db-121">O alerta no título é aquele em foco quando você aterra pela primeira vez na página do alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="961db-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="961db-122">Os ativos no artigo de alerta são expansíveis e clicáveis.</span><span class="sxs-lookup"><span data-stu-id="961db-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="961db-123">Eles fornecem informações adicionais e aceleram a resposta permitindo que você tome ações imediatamente no contexto da página de alerta.</span><span class="sxs-lookup"><span data-stu-id="961db-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="961db-124">A seção de texto do alerta pode conter mais de um alerta, com alertas adicionais relacionados à mesma árvore de execução que aparece antes ou depois do alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="961db-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="961db-125">Exibir mais informações de alerta no painel de detalhes</span><span class="sxs-lookup"><span data-stu-id="961db-125">View more alert information in the details pane</span></span>

<span data-ttu-id="961db-126">O painel de detalhes mostra os detalhes do alerta selecionado no início, com detalhes e ações relacionadas a ele.</span><span class="sxs-lookup"><span data-stu-id="961db-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="961db-127">Se você selecionar qualquer um dos ativos ou entidades afetados no histórico de alertas, o painel de detalhes muda para fornecer informações contextuais e ações para o objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="961db-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="961db-128">Depois de selecionar uma entidade de interesse, o painel de detalhes muda para exibir informações sobre o tipo de entidade selecionado, informações históricas quando ela estiver disponível e opções para tomar medidas nessa entidade diretamente na página de alerta.</span><span class="sxs-lookup"><span data-stu-id="961db-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="961db-129">Gerenciar alertas</span><span class="sxs-lookup"><span data-stu-id="961db-129">Manage alerts</span></span>

<span data-ttu-id="961db-130">Depois de terminar de investigar os alertas, você pode voltar ao alerta com o que começou, marcar o status do alerta como Resolvido e classificá-lo como um alerta False ou True.</span><span class="sxs-lookup"><span data-stu-id="961db-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="961db-131">Classificar alertas ajuda a ajustar seu produto para fornecer alertas mais verdadeiros e menos alertas falsos.</span><span class="sxs-lookup"><span data-stu-id="961db-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="961db-132">Uma maneira de gerenciar o alerta por meio do uso de marcas.</span><span class="sxs-lookup"><span data-stu-id="961db-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="961db-133">O recurso de marcação do Microsoft Defender para Office 365 está sendo lançado incrementalmente e está atualmente em visualização.</span><span class="sxs-lookup"><span data-stu-id="961db-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="961db-134">Atualmente, os nomes de marcas modificadas só são aplicados a alertas criados *após* a atualização.</span><span class="sxs-lookup"><span data-stu-id="961db-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="961db-135">Os alertas gerados antes da modificação não refletirão o nome da marca atualizado.</span><span class="sxs-lookup"><span data-stu-id="961db-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="961db-136">Gerenciar a fila de alertas unificada</span><span class="sxs-lookup"><span data-stu-id="961db-136">Manage the unified alert queue</span></span>

<span data-ttu-id="961db-137">Selecionar Alertas em Incidentes & alertas no painel de navegação do Centro de Segurança do Microsoft 365 o leva à fila de alertas unificada.</span><span class="sxs-lookup"><span data-stu-id="961db-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="961db-138">Alertas de diferentes soluções de segurança da Microsoft, como o Microsoft Defender para Ponto de Extremidade, o Microsoft Defender para Office 365 e o Microsoft 365 Defender aparecem nesta seção.</span><span class="sxs-lookup"><span data-stu-id="961db-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![Imagem da página de alerta de exemplo](../../media/unified-alert-queue.png)

<span data-ttu-id="961db-140">A fila Alertas mostra uma lista de alertas que foram sinalizados em sua rede.</span><span class="sxs-lookup"><span data-stu-id="961db-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="961db-141">Por padrão, a fila exibe alertas vistos nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="961db-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="961db-142">Os alertas mais recentes são mostrados na parte superior da lista, ajudando você a ver os alertas mais recentes primeiro.</span><span class="sxs-lookup"><span data-stu-id="961db-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="961db-143">No momento do início, a fila de alertas unificados terá apenas 7 dias de alertas do Microsoft Defender para Office 365 disponíveis.</span><span class="sxs-lookup"><span data-stu-id="961db-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="961db-144">A fila continuará a ser construída ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="961db-144">The queue will continue to build over time.</span></span> <span data-ttu-id="961db-145">Se você precisar triagem de alertas antes do início da fila de alertas unificados, use a fila de alertas no Centro de Segurança [e Conformidade.](https://protection.office.com/viewalerts)</span><span class="sxs-lookup"><span data-stu-id="961db-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="961db-146">Na navegação superior, você pode:</span><span class="sxs-lookup"><span data-stu-id="961db-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="961db-147">Aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="961db-147">Apply filters</span></span>
- <span data-ttu-id="961db-148">Personalizar colunas para adicionar ou remover colunas</span><span class="sxs-lookup"><span data-stu-id="961db-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="961db-149">Exportar dados</span><span class="sxs-lookup"><span data-stu-id="961db-149">Export data</span></span>

<span data-ttu-id="961db-150">Você também pode filtrar alertas de acordo com diferentes critérios:</span><span class="sxs-lookup"><span data-stu-id="961db-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="961db-151">Severity</span><span class="sxs-lookup"><span data-stu-id="961db-151">Severity</span></span>
- <span data-ttu-id="961db-152">Status</span><span class="sxs-lookup"><span data-stu-id="961db-152">Status</span></span>
- <span data-ttu-id="961db-153">Categoria</span><span class="sxs-lookup"><span data-stu-id="961db-153">Category</span></span>
- <span data-ttu-id="961db-154">Fonte de detecção</span><span class="sxs-lookup"><span data-stu-id="961db-154">Detection source</span></span>
- <span data-ttu-id="961db-155">Política</span><span class="sxs-lookup"><span data-stu-id="961db-155">Policy</span></span>
- <span data-ttu-id="961db-156">Ativos afetados</span><span class="sxs-lookup"><span data-stu-id="961db-156">Impacted assets</span></span>
- <span data-ttu-id="961db-157">Primeira atividade</span><span class="sxs-lookup"><span data-stu-id="961db-157">First activity</span></span>
- <span data-ttu-id="961db-158">Última atividade</span><span class="sxs-lookup"><span data-stu-id="961db-158">Last activity</span></span>


<span data-ttu-id="961db-159">Para iniciar uma investigação sobre um incidente, leia [Investigar incidentes no Microsoft 365 Defender](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="961db-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="961db-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="961db-160">See also</span></span>

- [<span data-ttu-id="961db-161">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="961db-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="961db-162">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="961db-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="961db-163">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="961db-163">Manage incidents</span></span>](manage-incidents.md)
