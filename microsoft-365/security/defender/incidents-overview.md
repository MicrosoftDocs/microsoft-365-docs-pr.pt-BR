---
title: Incidentes no Microsoft 365 Defender
description: Investigue incidentes vistos em dispositivos, usuários e caixas de correio no centro de segurança do Microsoft 365.
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
ms.openlocfilehash: 890e64367c49c24c8c70e2cbda9869a5d0797219
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939571"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="97e30-104">Incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97e30-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="97e30-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="97e30-105">**Applies to:**</span></span>
- <span data-ttu-id="97e30-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97e30-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="97e30-107">Quer experimentar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="97e30-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="97e30-108">Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="97e30-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="97e30-109">Um incidente no Microsoft 365 Defender é uma coleção de alertas correlacionados e dados associados que comentam a história de um ataque.</span><span class="sxs-lookup"><span data-stu-id="97e30-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="97e30-110">Os serviços e aplicativos do Microsoft 365 criam alertas quando detectam um evento ou atividade suspeito ou mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="97e30-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="97e30-111">Alertas individuais fornecem dicas valiosas sobre um ataque concluído ou contínuo.</span><span class="sxs-lookup"><span data-stu-id="97e30-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="97e30-112">No entanto, os ataques geralmente empregam várias técnicas contra diferentes tipos de entidades, como dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="97e30-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="97e30-113">O resultado são vários alertas para várias entidades em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="97e30-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="97e30-114">Como reunir os alertas individuais para obter informações sobre um ataque pode ser desafiador e demorado, o Microsoft 365 Defender agrega automaticamente os alertas e suas informações associadas a um incidente.</span><span class="sxs-lookup"><span data-stu-id="97e30-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Como o Microsoft 365 Defender correlaciona eventos de entidades em um incidente":::

<span data-ttu-id="97e30-116">Assista a esta breve visão geral dos incidentes no Microsoft 365 Defender (4 minutos).</span><span class="sxs-lookup"><span data-stu-id="97e30-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="97e30-117">Agrupar alertas relacionados a um incidente oferece uma visão abrangente de um ataque.</span><span class="sxs-lookup"><span data-stu-id="97e30-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="97e30-118">Por exemplo, você pode ver:</span><span class="sxs-lookup"><span data-stu-id="97e30-118">For example, you can see:</span></span>

- <span data-ttu-id="97e30-119">Onde o ataque começou.</span><span class="sxs-lookup"><span data-stu-id="97e30-119">Where the attack started.</span></span>
- <span data-ttu-id="97e30-120">Quais táticas foram usadas.</span><span class="sxs-lookup"><span data-stu-id="97e30-120">What tactics were used.</span></span>
- <span data-ttu-id="97e30-121">Até que ponto o ataque foi para o seu locatário.</span><span class="sxs-lookup"><span data-stu-id="97e30-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="97e30-122">O escopo do ataque, como quantos dispositivos, usuários e caixas de correio foram afetados.</span><span class="sxs-lookup"><span data-stu-id="97e30-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="97e30-123">Todos os dados associados ao ataque.</span><span class="sxs-lookup"><span data-stu-id="97e30-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="97e30-124">Se [habilitado, o](m365d-enable.md)Microsoft 365 Defender pode investigar e resolver alertas automaticamente por meio da automação e da inteligência artificial.</span><span class="sxs-lookup"><span data-stu-id="97e30-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="97e30-125">Você também pode executar etapas de correção adicionais para resolver o ataque.</span><span class="sxs-lookup"><span data-stu-id="97e30-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="97e30-126">Incidentes e alertas no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="97e30-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="97e30-127">Você gerencia incidentes de **incidentes & alertas** > incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="97e30-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="97e30-128">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="97e30-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="A página Incidentes no centro de segurança do Microsoft 365":::

<span data-ttu-id="97e30-130">Selecionar um nome de incidente exibe um resumo do incidente e fornece acesso a guias com informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="97e30-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exemplo da página Resumo de um incidente no centro de segurança do Microsoft 365":::

<span data-ttu-id="97e30-132">As guias adicionais para um incidente são:</span><span class="sxs-lookup"><span data-stu-id="97e30-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="97e30-133">Alertas</span><span class="sxs-lookup"><span data-stu-id="97e30-133">Alerts</span></span> 

  <span data-ttu-id="97e30-134">Todos os alertas relacionados ao incidente e suas informações.</span><span class="sxs-lookup"><span data-stu-id="97e30-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="97e30-135">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="97e30-135">Devices</span></span>

  <span data-ttu-id="97e30-136">Todos os dispositivos que foram identificados para fazer parte ou relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="97e30-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="97e30-137">Usuários</span><span class="sxs-lookup"><span data-stu-id="97e30-137">Users</span></span>

  <span data-ttu-id="97e30-138">Todos os usuários identificados para fazer parte ou relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="97e30-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="97e30-139">Caixas de correio</span><span class="sxs-lookup"><span data-stu-id="97e30-139">Mailboxes</span></span>

  <span data-ttu-id="97e30-140">Todas as caixas de correio identificadas para fazer parte ou relacionadas ao incidente.</span><span class="sxs-lookup"><span data-stu-id="97e30-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="97e30-141">Investigações</span><span class="sxs-lookup"><span data-stu-id="97e30-141">Investigations</span></span>

  <span data-ttu-id="97e30-142">Todas as investigações automatizadas disparadas por alertas no incidente.</span><span class="sxs-lookup"><span data-stu-id="97e30-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="97e30-143">Evidências e resposta</span><span class="sxs-lookup"><span data-stu-id="97e30-143">Evidence and Response</span></span>

  <span data-ttu-id="97e30-144">Todos os eventos com suporte e entidades suspeitas nos alertas no incidente.</span><span class="sxs-lookup"><span data-stu-id="97e30-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="97e30-145">Aqui está a relação entre um incidente e seus dados e as guias de um incidente no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97e30-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="A relação de um incidente e seus dados com as guias de um incidente no centro de segurança do Microsoft 365":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="97e30-147">Exemplo de fluxo de trabalho de resposta a incidentes para o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97e30-147">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="97e30-148">Veja um exemplo de fluxo de trabalho para responder a incidentes no Microsoft 365 com o centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97e30-148">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Exemplo de um fluxo de trabalho de resposta a incidentes para o Microsoft 365":::

<span data-ttu-id="97e30-150">Em uma base contínua, identifique os incidentes de maior prioridade para análise e resolução na fila de incidentes e prepare-os para resposta.</span><span class="sxs-lookup"><span data-stu-id="97e30-150">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="97e30-151">Esta é uma combinação de:</span><span class="sxs-lookup"><span data-stu-id="97e30-151">This is a combination of:</span></span>

- <span data-ttu-id="97e30-152">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span><span class="sxs-lookup"><span data-stu-id="97e30-152">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="97e30-153">[Gerenciando](manage-incidents.md) incidentes modificando seu título, atribuindo-os a um analista e adicionando marcas e comentários.</span><span class="sxs-lookup"><span data-stu-id="97e30-153">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="97e30-154">Para cada incidente, inicie uma análise [de ataque e alerta:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="97e30-154">For each incident, begin an [attack and alert analysis](investigate-incidents.md):</span></span>

   <span data-ttu-id="97e30-155">a.</span><span class="sxs-lookup"><span data-stu-id="97e30-155">a.</span></span> <span data-ttu-id="97e30-156">Exibir o resumo do incidente para entender seu escopo e gravidade e quais entidades são afetadas (a **guia Resumo).**</span><span class="sxs-lookup"><span data-stu-id="97e30-156">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="97e30-157">b.</span><span class="sxs-lookup"><span data-stu-id="97e30-157">b.</span></span> <span data-ttu-id="97e30-158">Comece a analisar os alertas para entender sua origem, escopo e gravidade (a **guia Alertas).**</span><span class="sxs-lookup"><span data-stu-id="97e30-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="97e30-159">c.</span><span class="sxs-lookup"><span data-stu-id="97e30-159">c.</span></span> <span data-ttu-id="97e30-160">Conforme necessário, reúna informações sobre dispositivos, usuários e caixas de correio afetados (as guias **Dispositivos,** **Usuários** e **Caixas** de Correio).</span><span class="sxs-lookup"><span data-stu-id="97e30-160">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="97e30-161">d.</span><span class="sxs-lookup"><span data-stu-id="97e30-161">d.</span></span> <span data-ttu-id="97e30-162">Veja como o Microsoft 365 Defender resolveu automaticamente alguns alertas (a guia **Investigações).**</span><span class="sxs-lookup"><span data-stu-id="97e30-162">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="97e30-163">e.</span><span class="sxs-lookup"><span data-stu-id="97e30-163">e.</span></span> <span data-ttu-id="97e30-164">Conforme necessário, use informações no conjunto de dados do incidente para obter mais informações (a **guia Evidências e Resposta).**</span><span class="sxs-lookup"><span data-stu-id="97e30-164">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="97e30-165">Após ou durante sua análise, contenção de endereços para reduzir qualquer impacto adicional do ataque e da erradicação da ameaça de segurança.</span><span class="sxs-lookup"><span data-stu-id="97e30-165">After or during your analysis, address containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="97e30-166">O máximo possível, recupere-se do ataque restaurando os recursos do locatário para o estado em que estavam antes do incidente.</span><span class="sxs-lookup"><span data-stu-id="97e30-166">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="97e30-167">[Resolver](manage-incidents.md#resolve-incident) o incidente e levar tempo para o aprendizado pós-incidente para:</span><span class="sxs-lookup"><span data-stu-id="97e30-167">[Resolve](manage-incidents.md#resolve-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="97e30-168">Entenda o tipo de ataque e seu impacto.</span><span class="sxs-lookup"><span data-stu-id="97e30-168">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="97e30-169">Pesquise o ataque [no Threat Analytics](threat-analytics.md) e na comunidade de segurança para uma tendência de ataque de segurança.</span><span class="sxs-lookup"><span data-stu-id="97e30-169">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="97e30-170">Lembre-se do fluxo de trabalho usado para resolver o incidente e atualizar seus fluxos de trabalho, processos, políticas e playbooks padrão conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="97e30-170">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="97e30-171">Determine se as alterações na configuração de segurança são necessárias e implementá-las.</span><span class="sxs-lookup"><span data-stu-id="97e30-171">Determine whether changes in your security configuration are needed and implement them.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="97e30-172">Exemplo de operações de segurança para o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97e30-172">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="97e30-173">Veja um exemplo de operações de segurança para o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="97e30-173">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Um exemplo de operações de segurança para o Micosoft 365 Defender":::

<span data-ttu-id="97e30-175">Tarefas diárias podem incluir:</span><span class="sxs-lookup"><span data-stu-id="97e30-175">Daily tasks can include:</span></span>

- <span data-ttu-id="97e30-176">[Gerenciando](manage-incidents.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="97e30-176">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="97e30-177">Revisão de [ações automatizadas de investigação e resposta (AIR)](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="97e30-177">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions</span></span>
- <span data-ttu-id="97e30-178">Revisão da análise de [ameaças mais recente](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="97e30-178">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="97e30-179">[Respondendo](investigate-incidents.md) a incidentes</span><span class="sxs-lookup"><span data-stu-id="97e30-179">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="97e30-180">As tarefas mensais podem incluir:</span><span class="sxs-lookup"><span data-stu-id="97e30-180">Monthly tasks can include:</span></span>

- <span data-ttu-id="97e30-181">Revisão das [configurações do AIR](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="97e30-181">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="97e30-182">Revisão da [pontuação segura](microsoft-secure-score-improvement-actions.md) e [do & gerenciamento de vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="97e30-182">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="97e30-183">Relatórios para sua cadeia de gerenciamento de segurança de IT</span><span class="sxs-lookup"><span data-stu-id="97e30-183">Reporting to your IT security management chain</span></span>

<span data-ttu-id="97e30-184">As tarefas trimestrais podem incluir um relatório e uma reunião de resultados de segurança para o Diretor de Segurança da Informação (CISO).</span><span class="sxs-lookup"><span data-stu-id="97e30-184">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="97e30-185">As tarefas anuais podem incluir a realização de um grande incidente ou exercício de violação para testar sua equipe, sistemas e processos.</span><span class="sxs-lookup"><span data-stu-id="97e30-185">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="97e30-186">Tarefas diárias, mensais, trimestrais e anuais podem ser usadas para atualizar ou refinar processos, políticas e configurações de segurança.</span><span class="sxs-lookup"><span data-stu-id="97e30-186">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="97e30-187">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="97e30-187">Next steps</span></span>

<span data-ttu-id="97e30-188">A fila de **incidentes da página Incidentes** lista os incidentes mais recentes.</span><span class="sxs-lookup"><span data-stu-id="97e30-188">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="97e30-189">A partir daqui, você pode:</span><span class="sxs-lookup"><span data-stu-id="97e30-189">From here, you can:</span></span>

- <span data-ttu-id="97e30-190">Confira quais incidentes devem ser [priorizados](incident-queue.md) com base na gravidade e em outros fatores.</span><span class="sxs-lookup"><span data-stu-id="97e30-190">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="97e30-191">[Gerenciar incidentes](manage-incidents.md), que inclui renomeação, atribuição, classificação e adição de marcas e comentários para o fluxo de trabalho de gerenciamento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="97e30-191">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments for your incident management workflow.</span></span>
- <span data-ttu-id="97e30-192">Execute uma [análise](investigate-incidents.md) de um incidente.</span><span class="sxs-lookup"><span data-stu-id="97e30-192">Perform an [analysis](investigate-incidents.md) of an incident.</span></span>
