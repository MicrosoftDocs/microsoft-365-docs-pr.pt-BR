---
title: Investigar incidentes no Microsoft 365 Defender
description: Analisar incidentes relacionados a dispositivos, usuários e caixas de correio.
keywords: incidente, incidentes, computadores, dispositivos, usuários, identidades, correio, email, caixa de correio, investigação, gráfico, evidência
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 10fa2765a4fe5bd256e0588af0db51f5a22339a2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052837"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="1225a-104">Investigar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1225a-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1225a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1225a-105">**Applies to:**</span></span>

- <span data-ttu-id="1225a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1225a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1225a-107">O Microsoft 365 Defender agrega todos os alertas, ativos, investigações e evidências relacionados em todos os dispositivos, usuários e caixas de correio para dar uma olhada abrangente em toda a amplitude de um ataque.</span><span class="sxs-lookup"><span data-stu-id="1225a-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="1225a-108">Investigue os alertas que afetam a sua rede, entenda o que cada um significa e agrupe as evidências associadas aos incidentes para planejar uma correção eficaz.</span><span class="sxs-lookup"><span data-stu-id="1225a-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="1225a-109">Investigar um incidente</span><span class="sxs-lookup"><span data-stu-id="1225a-109">Investigate an incident</span></span>

1. <span data-ttu-id="1225a-110">Selecionar um incidente na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="1225a-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="1225a-111">Um painel lateral é aberto e fornece uma visualização de informações importantes, como status, gravidade, categorias e as entidades impactadas.</span><span class="sxs-lookup"><span data-stu-id="1225a-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Imagem do painel lateral do incidente](../../media/incident-side-panel.png)

2. <span data-ttu-id="1225a-113">Selecione **Abrir página do incidente**.</span><span class="sxs-lookup"><span data-stu-id="1225a-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="1225a-114">Isso abre a página de incidentes onde você encontrará mais detalhes de incidentes de informações, comentários e ações, guias (visão geral, alertas, dispositivos, usuários, investigações, evidências).</span><span class="sxs-lookup"><span data-stu-id="1225a-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="1225a-115">Examine os alertas, dispositivos, usuários e outras entidades envolvidas no incidente.</span><span class="sxs-lookup"><span data-stu-id="1225a-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="1225a-116">Visão geral do incidente</span><span class="sxs-lookup"><span data-stu-id="1225a-116">Incident overview</span></span>

<span data-ttu-id="1225a-117">A página da visão geral oferece uma imagem instantânea das principais coisas a serem observadas sobre o incidente.</span><span class="sxs-lookup"><span data-stu-id="1225a-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Imagem da página da visão geral dos incidentes](../../media/incidents-overview.png)

<span data-ttu-id="1225a-119">As categorias de ataque dão a você uma visão visual e numérica de como o ataque avançou contra a cadeia de kill.</span><span class="sxs-lookup"><span data-stu-id="1225a-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="1225a-120">Assim como com outros produtos de segurança da Microsoft, o Microsoft 365 Defender é alinhado à estrutura de CK do [MITRE ATT&&trade; CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="1225a-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="1225a-121">A seção escopo fornece uma lista dos principais ativos afetados que fazem parte desse incidente.</span><span class="sxs-lookup"><span data-stu-id="1225a-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="1225a-122">Se houver informações específicas sobre esse ativo, como nível de risco, prioridade de investigação, além de qualquer marcação nos ativos, também virão à tona nesta seção.</span><span class="sxs-lookup"><span data-stu-id="1225a-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="1225a-123">A linha do tempo de alerta apresenta uma amostra da ordem cronológica da ocorrência dos alertas, bem como os motivos pelos quais esses alertas estão vinculados a esse incidente.</span><span class="sxs-lookup"><span data-stu-id="1225a-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="1225a-124">Em seguida, a seção de evidências apresenta um resumo de quantos artefatos diferentes foram incluídos no incidente e o status da sua correção, para saber imediatamente se você precisa executar alguma ação.</span><span class="sxs-lookup"><span data-stu-id="1225a-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="1225a-125">Essa visão geral pode ajudar na triagem inicial do incidente, fornecendo ideias para as principais características do incidente que você deve conhecer.</span><span class="sxs-lookup"><span data-stu-id="1225a-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="1225a-126">Alertas</span><span class="sxs-lookup"><span data-stu-id="1225a-126">Alerts</span></span>

<span data-ttu-id="1225a-127">Você pode exibir todos os alertas relacionados ao incidente e outras informações sobre eles, como gravidade, entidades envolvidas no alerta, a origem dos alertas (Microsoft Defender para Identidade, Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365) e o motivo pelo qual eles foram vinculados.</span><span class="sxs-lookup"><span data-stu-id="1225a-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Imagem da página de alertas de incidente](../../media/incident-alerts.png)

<span data-ttu-id="1225a-129">Por padrão, os alertas são classificados em ordem cronológica, para exibir primeiro como o ataque se desenvolveu.</span><span class="sxs-lookup"><span data-stu-id="1225a-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="1225a-130">Clicar em cada alerta o levará à página de alerta relevante onde você pode conduzir uma investigação detalhada desse alerta.</span><span class="sxs-lookup"><span data-stu-id="1225a-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="1225a-131">Saiba como usar páginas de alerta e a fila de alertas unificada em [Investigar alertas](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1225a-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="1225a-132">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="1225a-132">Devices</span></span>

<span data-ttu-id="1225a-133">A guia Dispositivos lista todos os dispositivos onde os alertas relacionados ao incidente são exibidos.</span><span class="sxs-lookup"><span data-stu-id="1225a-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="1225a-134">Ao clicar no nome do computador onde ocorreu o ataque, você será direcionado para a página do computador, onde poderá ver os alertas disparados e os eventos relacionados para facilitar a investigação.</span><span class="sxs-lookup"><span data-stu-id="1225a-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Imagem da guia Computadores de um incidente](../../media/incident-machines.png)

<span data-ttu-id="1225a-136">Selecionar a guia Linha do tempo permite percorrer a linha do tempo do computador e exibir todos os eventos e comportamentos observados no computador em ordem cronológica, intercalados com os alertas gerados.</span><span class="sxs-lookup"><span data-stu-id="1225a-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="1225a-137">Usuários</span><span class="sxs-lookup"><span data-stu-id="1225a-137">Users</span></span>

<span data-ttu-id="1225a-138">Veja os usuários identificados como parte ou relacionados a um determinado incidente.</span><span class="sxs-lookup"><span data-stu-id="1225a-138">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="1225a-139">Ao clicar no nome do usuário, você será direcionado para a página do Cloud App Security, onde poderá ser realizada uma investigação mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="1225a-139">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Imagem da guia Usuários de um incidente](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="1225a-141">Caixas de correio</span><span class="sxs-lookup"><span data-stu-id="1225a-141">Mailboxes</span></span>

<span data-ttu-id="1225a-142">Investigue os usuários identificados como parte ou relacionados a um determinado incidente.</span><span class="sxs-lookup"><span data-stu-id="1225a-142">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="1225a-143">Para realizar um trabalho mais investigativo, selecionar o alerta relacionado ao email abrirá o Microsoft Defender para o Office 365, onde você pode realizar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="1225a-143">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Imagem da guia Caixas de correio de um incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="1225a-145">Investigações</span><span class="sxs-lookup"><span data-stu-id="1225a-145">Investigations</span></span>

<span data-ttu-id="1225a-146">Selecione **Investigações** para ver todas as investigações automatizadas disparadas por alertas neste incidente.</span><span class="sxs-lookup"><span data-stu-id="1225a-146">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="1225a-147">As investigações executarão ações de correção ou aguardarão a aprovação de ações do analista, dependendo de como você configurou suas investigações automatizadas para executar no Microsoft Defender para Ponto de Extremidade e no Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="1225a-147">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Imagem da guia Investigações de um incidente](../../media/incident-investigations.png)

<span data-ttu-id="1225a-149">Clique em uma investigação para navegar até a página Detalhes da investigação e obter informações completas sobre o status da investigação e da correção.</span><span class="sxs-lookup"><span data-stu-id="1225a-149">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="1225a-150">Se houver ações pendentes para aprovação como parte da investigação, elas aparecerão na guia Ações pendentes. Tome medidas como parte da correção de incidentes.</span><span class="sxs-lookup"><span data-stu-id="1225a-150">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="1225a-151">Evidências</span><span class="sxs-lookup"><span data-stu-id="1225a-151">Evidence</span></span>

<span data-ttu-id="1225a-152">O Microsoft 365 Defender investiga automaticamente todos os eventos com suporte dos incidentes e entidades suspeitas nos alertas, fornecendo a você autoresponse e informações sobre os arquivos importantes, processos, serviços, emails e muito mais.</span><span class="sxs-lookup"><span data-stu-id="1225a-152">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="1225a-153">Isso ajuda a detectar e bloquear rapidamente ameaças potenciais no incidente.</span><span class="sxs-lookup"><span data-stu-id="1225a-153">This helps quickly detect and block potential threats in the incident.</span></span>

![Imagem da guia Evidências de um incidente](../../media/incident-evidence.png)

<span data-ttu-id="1225a-155">Cada entidade analisada será marcada com um veredicto (mal-intencionada, suspeita, limpa), bem como um status de correção.</span><span class="sxs-lookup"><span data-stu-id="1225a-155">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="1225a-156">Isso ajuda a entender o status da correção de todo o incidente e quais são as próximas etapas que podem ser seguidas para continuar a correção.</span><span class="sxs-lookup"><span data-stu-id="1225a-156">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1225a-157">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1225a-157">Related topics</span></span>

- [<span data-ttu-id="1225a-158">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="1225a-158">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1225a-159">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="1225a-159">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="1225a-160">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="1225a-160">Manage incidents</span></span>](manage-incidents.md)

