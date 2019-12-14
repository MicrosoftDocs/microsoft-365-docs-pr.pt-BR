---
title: Investigar incidentes na Proteção contra Ameaças da Microsoft
description: Analisar incidentes relacionados a dispositivos, usuários e caixas de correio.
keywords: incidente, incidentes, computadores, dispositivos, usuários, identidades, correio, email, caixa de correio, investigação, gráfico, evidência
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
ms.openlocfilehash: 716feb3317989ebcc89593c89d05a6717b4ca0ee
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910774"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="00aaf-104">Investigar incidentes na Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="00aaf-104">Investigate incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="00aaf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="00aaf-105">**Applies to:**</span></span>
- <span data-ttu-id="00aaf-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="00aaf-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]


<span data-ttu-id="00aaf-107">A proteção contra ameaças da Microsoft agrega todos os alertas, ativos, investigações e evidências relacionados a todos os seus dispositivos, usuários e caixas de correio para fornecer uma visão abrangente de toda a amplitude de um ataque.</span><span class="sxs-lookup"><span data-stu-id="00aaf-107">Microsoft Threat Protection aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span> 

<span data-ttu-id="00aaf-108">Investigue os alertas que afetam a sua rede, entenda o que cada um significa e agrupe as evidências associadas aos incidentes para planejar uma correção eficaz.</span><span class="sxs-lookup"><span data-stu-id="00aaf-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span> 

## <a name="investigate-an-incident"></a><span data-ttu-id="00aaf-109">Investigar um incidente</span><span class="sxs-lookup"><span data-stu-id="00aaf-109">Investigate an incident</span></span>

1. <span data-ttu-id="00aaf-110">Selecionar um incidente na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="00aaf-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="00aaf-111">Isso abre um painel lateral e fornece uma visualização de informações importantes como status, gravidade, categorias e entidades afetadas.</span><span class="sxs-lookup"><span data-stu-id="00aaf-111">This opens a side panel and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Imagem do painel lateral do incidente](../images/incident-side-panel.png)

2. <span data-ttu-id="00aaf-113">Selecione **Abrir página do incidente**.</span><span class="sxs-lookup"><span data-stu-id="00aaf-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="00aaf-114">Isso abre a página Incidente, com mais informações detalhadas do incidente, comentários e ações, guias (visão geral, alertas, dispositivos, usuários, investigações, evidências).</span><span class="sxs-lookup"><span data-stu-id="00aaf-114">This opens the incident page where you'll find more information incident details, comments and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="00aaf-115">Examine os alertas, dispositivos, usuários e outras entidades envolvidas no incidente.</span><span class="sxs-lookup"><span data-stu-id="00aaf-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="00aaf-116">Visão geral do incidente</span><span class="sxs-lookup"><span data-stu-id="00aaf-116">Incident overview</span></span> 
<span data-ttu-id="00aaf-117">A página da visão geral oferece uma imagem instantânea das principais coisas a serem observadas sobre o incidente.</span><span class="sxs-lookup"><span data-stu-id="00aaf-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>


![Imagem da página da visão geral dos incidentes](../images/incidents-overview.png)


<span data-ttu-id="00aaf-119">As categorias de ataque oferecem uma visualização numérica e visual do quão avançado o ataque progrediu em relação ao kill chain.</span><span class="sxs-lookup"><span data-stu-id="00aaf-119">The attack categories give you visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="00aaf-120">Assim como ocorre com outros produtos de segurança da Microsoft, a Proteção contra Ameaças da Microsoft está alinhada à estrutura [MITRE ATT&CK&trade;](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="00aaf-120">As with other Microsoft security products, Microsoft Threat Protection is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span> 

<span data-ttu-id="00aaf-121">A seção escopo fornece uma lista dos principais ativos afetados que fazem parte desse incidente.</span><span class="sxs-lookup"><span data-stu-id="00aaf-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="00aaf-122">Se houver informações específicas sobre esse ativo, como nível de risco, prioridade de investigação, além de qualquer marcação nos ativos, também virão à tona nesta seção.</span><span class="sxs-lookup"><span data-stu-id="00aaf-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="00aaf-123">A linha do tempo de alerta apresenta uma amostra da ordem cronológica da ocorrência dos alertas, bem como os motivos pelos quais esses alertas estão vinculados a esse incidente.</span><span class="sxs-lookup"><span data-stu-id="00aaf-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="00aaf-124">Em seguida, a seção de evidências apresenta um resumo de quantos artefatos diferentes foram incluídos no incidente e o status da sua correção, para saber imediatamente se você precisa executar alguma ação.</span><span class="sxs-lookup"><span data-stu-id="00aaf-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span> 

<span data-ttu-id="00aaf-125">Essa visão geral pode ajudar na triagem inicial do incidente, fornecendo ideias para as principais características do incidente que você deve conhecer.</span><span class="sxs-lookup"><span data-stu-id="00aaf-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span> 


## <a name="alerts"></a><span data-ttu-id="00aaf-126">Alertas</span><span class="sxs-lookup"><span data-stu-id="00aaf-126">Alerts</span></span> 
<span data-ttu-id="00aaf-127">Você pode ver todos os alertas relacionados ao incidente e outras informações sobre eles, como gravidade, entidades envolvidas no alerta, a origem dos alertas (Azure ATP, Microsoft Defender ATP, Office 365 ATP) e o motivo pelo qual eles foram vinculados.</span><span class="sxs-lookup"><span data-stu-id="00aaf-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Azure ATP, Microsoft Defender ATP , Office  365 ATP) and the reason they were linked together.</span></span> 

![Imagem da página de alertas de incidente](../images/incident-alerts.png)

<span data-ttu-id="00aaf-129">Por padrão, os alertas são classificados em ordem cronológica, para exibir primeiro como o ataque se desenvolveu.</span><span class="sxs-lookup"><span data-stu-id="00aaf-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="00aaf-130">Clicar em cada alerta o redirecionará à página de alerta relevante, para realizar uma investigação detalhada desse alerta.</span><span class="sxs-lookup"><span data-stu-id="00aaf-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in depth investigation of that alert.</span></span> 

## <a name="devices"></a><span data-ttu-id="00aaf-131">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="00aaf-131">Devices</span></span> 
<span data-ttu-id="00aaf-132">A guia Dispositivos lista todos os dispositivos onde os alertas relacionados ao incidente são exibidos.</span><span class="sxs-lookup"><span data-stu-id="00aaf-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span> 

<span data-ttu-id="00aaf-133">Ao clicar no nome do computador onde ocorreu o ataque, você será direcionado para a página do computador, onde poderá ver os alertas disparados e os eventos relacionados para facilitar a investigação.</span><span class="sxs-lookup"><span data-stu-id="00aaf-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span> 

![Imagem da guia Computadores de um incidente](../images/incident-machines.png)

<span data-ttu-id="00aaf-135">Selecionar a guia Linha do tempo permite percorrer a linha do tempo do computador e exibir todos os eventos e comportamentos observados no computador em ordem cronológica, intercalados com os alertas gerados.</span><span class="sxs-lookup"><span data-stu-id="00aaf-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span> 


## <a name="users"></a><span data-ttu-id="00aaf-136">Usuários</span><span class="sxs-lookup"><span data-stu-id="00aaf-136">Users</span></span> 
<span data-ttu-id="00aaf-137">Veja os usuários identificados como parte ou relacionados a um determinado incidente.</span><span class="sxs-lookup"><span data-stu-id="00aaf-137">See users that have been identified to be part of, or related to a given incident.</span></span> 

<span data-ttu-id="00aaf-138">Ao clicar no nome do usuário, você será direcionado para a página do Cloud App Security, onde poderá ser realizada uma investigação mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="00aaf-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>


![Imagem da guia Usuários de um incidente](../images/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="00aaf-140">Caixas de correio</span><span class="sxs-lookup"><span data-stu-id="00aaf-140">Mailboxes</span></span>
<span data-ttu-id="00aaf-141">Investigue os usuários identificados como parte ou relacionados a um determinado incidente.</span><span class="sxs-lookup"><span data-stu-id="00aaf-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="00aaf-142">Para uma investigação com mais detalhes, clicar no alerta relacionado ao email abrirá a Proteção Avançada contra Ameaças do Office 365, onde será possível executar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="00aaf-142">To do further investigative work, selecting the mail related alert will open Office 365 Advanced Threat Protection where you can take remediation actions.</span></span>


![Imagem da guia Caixas de correio de um incidente](../images/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="00aaf-144">Investigações</span><span class="sxs-lookup"><span data-stu-id="00aaf-144">Investigations</span></span>
<span data-ttu-id="00aaf-145">Clique em **Investigações** para ver todas as investigações automatizadas geradas por alertas neste incidente.</span><span class="sxs-lookup"><span data-stu-id="00aaf-145">Select **Investigations** to see all the automated investigation striggered by alerts in this incident.</span></span> <span data-ttu-id="00aaf-146">As investigações irão executar ações de correção ou aguardar a aprovação de ações do analista, dependendo da configuração das investigações automatizadas a serem executadas no Microsoft Defender ATP e na Proteção Avançada contra Ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="00aaf-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender ATP and Office 365 Advanced Threat Protection.</span></span>

![Imagem da guia Investigações de um incidente](../images/incident-investigations.png)


<span data-ttu-id="00aaf-148">Clique em uma investigação para navegar até a página Detalhes da investigação e obter informações completas sobre o status da investigação e da correção.</span><span class="sxs-lookup"><span data-stu-id="00aaf-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="00aaf-149">Caso haja ações pendentes para aprovação como parte da investigação, elas aparecerão na guia Ações pendentes. Execute uma ação como parte da correção de incidentes.</span><span class="sxs-lookup"><span data-stu-id="00aaf-149">If there are any actions pending for approval as part of the investigation they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>


## <a name="evidence"></a><span data-ttu-id="00aaf-150">Evidências</span><span class="sxs-lookup"><span data-stu-id="00aaf-150">Evidence</span></span>
<span data-ttu-id="00aaf-151">A Proteção contra Ameaças da Microsoft investiga automaticamente todos os eventos e entidades suspeitas com suporte dos incidentes nos alertas, fornecendo a você respostas automáticas e informações sobre arquivos, processos, serviços, emails e muito mais.</span><span class="sxs-lookup"><span data-stu-id="00aaf-151">Microsoft Threat Protection automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with auto-response and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="00aaf-152">Isso ajuda a detectar e bloquear rapidamente ameaças potenciais no incidente.</span><span class="sxs-lookup"><span data-stu-id="00aaf-152">This helps quickly detect and block potential threats in the incident.</span></span> 

![Imagem da guia Evidências de um incidente](../images/incident-evidence.png)

<span data-ttu-id="00aaf-154">Cada entidade analisada será marcada com um veredicto (mal-intencionada, suspeita, limpa), bem como um status de correção.</span><span class="sxs-lookup"><span data-stu-id="00aaf-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="00aaf-155">Isso ajuda a entender o status da correção de todo o incidente e quais são as próximas etapas que podem ser seguidas para continuar a correção.</span><span class="sxs-lookup"><span data-stu-id="00aaf-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>


## <a name="related-topics"></a><span data-ttu-id="00aaf-156">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="00aaf-156">Related topics</span></span>
- [<span data-ttu-id="00aaf-157">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="00aaf-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="00aaf-158">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="00aaf-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="00aaf-159">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="00aaf-159">Manage incidents</span></span>](manage-incidents.md)