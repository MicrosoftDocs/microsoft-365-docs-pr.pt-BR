---
title: Investigar incidentes em Microsoft 365 Defender
description: Investigue incidentes relacionados a dispositivos, usuários e caixas de correio.
keywords: incidentes, incidentes, análise, resposta, máquinas, dispositivos, usuários, identidades, email, email, caixa de correio, investigação, gráfico, evidência
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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fdfc065aea3549e99de72c968c0fa19412f9e246
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105351"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="648d9-104">Investigar incidentes em Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="648d9-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="648d9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="648d9-105">**Applies to:**</span></span>

- <span data-ttu-id="648d9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="648d9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="648d9-107">Microsoft 365 Defender agrega todos os alertas, ativos, investigações e evidências relacionados de todos os dispositivos, usuários e caixas de correio em um incidente para dar uma olhada abrangente na amplitude de um ataque.</span><span class="sxs-lookup"><span data-stu-id="648d9-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="648d9-108">Em um incidente, você analisa os alertas que afetam sua rede, entende o que significam e cola as evidências para que você possa planejar um plano de correção eficaz.</span><span class="sxs-lookup"><span data-stu-id="648d9-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="648d9-109">Investigação inicial</span><span class="sxs-lookup"><span data-stu-id="648d9-109">Initial investigation</span></span>

<span data-ttu-id="648d9-110">Antes de mergulhar nos detalhes, confira as propriedades e o resumo do incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="648d9-111">Você pode começar selecionando o incidente na coluna marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="648d9-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="648d9-112">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="648d9-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Exemplo de seleção de um incidente na coluna marca de verificação":::

<span data-ttu-id="648d9-114">Quando você faz isso, um painel de resumo é aberto com informações importantes sobre o incidente, como gravidade, a quem ele é atribuído, e as categorias de CK do [MITRE ATT &trade; ](https://attack.mitre.org/)&CK para o incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="648d9-115">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="648d9-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Exemplo do painel de resumo de um incidente":::

<span data-ttu-id="648d9-117">A partir daqui, você pode selecionar **Abrir página de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="648d9-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="648d9-118">Isso abre a página principal do incidente em que você encontrará mais informações resumidas e guias para alertas, dispositivos, usuários, investigações e evidências.</span><span class="sxs-lookup"><span data-stu-id="648d9-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="648d9-119">Você também pode abrir a página principal de um incidente selecionando o nome do incidente na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="648d9-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="648d9-120">Resumo</span><span class="sxs-lookup"><span data-stu-id="648d9-120">Summary</span></span>

<span data-ttu-id="648d9-121">A **página** Resumo fornece um resumo das principais coisas a observar sobre o incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exemplo da página Resumo de um incidente no centro Microsoft 365 segurança":::

<span data-ttu-id="648d9-123">As categorias de ataque dão a você uma visão visual e numérica de como o ataque avançou contra a cadeia de kill.</span><span class="sxs-lookup"><span data-stu-id="648d9-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="648d9-124">Assim como com outros produtos de segurança da Microsoft, Microsoft 365 Defender está alinhado à estrutura de CK do [MITRE ATT&&trade; CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="648d9-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="648d9-125">A seção escopo fornece uma lista dos principais ativos afetados que fazem parte desse incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="648d9-126">Se houver informações específicas sobre esse ativo, como nível de risco, prioridade de investigação, além de qualquer marcação nos ativos, também virão à tona nesta seção.</span><span class="sxs-lookup"><span data-stu-id="648d9-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="648d9-127">A linha do tempo de alertas fornece uma prévia da ordem cronológica na qual os alertas ocorreram, bem como os motivos pelos quais esses alertas estão vinculados a esse incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="648d9-128">E por último - a seção de evidências fornece um resumo de quantos artefatos diferentes foram incluídos no incidente e seu status de correção, para que você possa identificar imediatamente se qualquer ação é necessária por você.</span><span class="sxs-lookup"><span data-stu-id="648d9-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="648d9-129">Essa visão geral pode ajudar na triagem inicial do incidente fornecendo informações sobre as principais características do incidente que você deve estar ciente.</span><span class="sxs-lookup"><span data-stu-id="648d9-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="648d9-130">Alertas</span><span class="sxs-lookup"><span data-stu-id="648d9-130">Alerts</span></span>

<span data-ttu-id="648d9-131">Na guia **Alerta,** você pode exibir a fila de alertas para alertas relacionados ao incidente e outras informações sobre eles, como:</span><span class="sxs-lookup"><span data-stu-id="648d9-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="648d9-132">Severidade.</span><span class="sxs-lookup"><span data-stu-id="648d9-132">Severity.</span></span>
- <span data-ttu-id="648d9-133">As entidades envolvidas no alerta.</span><span class="sxs-lookup"><span data-stu-id="648d9-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="648d9-134">A origem dos alertas (Microsoft Defender para Identidade, Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="648d9-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="648d9-135">O motivo pelo qual eles foram vinculados.</span><span class="sxs-lookup"><span data-stu-id="648d9-135">The reason they were linked together.</span></span>

<span data-ttu-id="648d9-136">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="648d9-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Exemplo de uma página Alertas para um incidente":::

<span data-ttu-id="648d9-138">Por padrão, os alertas são ordenados cronologicamente para permitir que você veja como o incidente ocorreu ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="648d9-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="648d9-139">Quando você seleciona um alerta dentro de um incidente, Microsoft 365 Defender exibe as informações de alerta específicas para o contexto do incidente geral.</span><span class="sxs-lookup"><span data-stu-id="648d9-139">When you select an alert within an incident, Microsoft 365 Defender displays the alert information specific to the context of the overall incident.</span></span> 

<span data-ttu-id="648d9-140">Você pode ver os eventos do alerta, quais outros alertas disparados causaram o alerta atual e todas as entidades e atividades afetadas envolvidas no ataque, incluindo arquivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="648d9-140">You can see the events of the alert, which other triggered alerts caused the current alert, and all the affected entities and activities involved in the attack, including files, users, and mailboxes.</span></span>

<span data-ttu-id="648d9-141">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="648d9-141">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Exemplo de uma página de detalhes de alerta dentro de um incidente":::

<span data-ttu-id="648d9-143">Esta página de alerta de incidente é composta por estas seções:</span><span class="sxs-lookup"><span data-stu-id="648d9-143">This incident alert page is composed of these sections:</span></span>

- <span data-ttu-id="648d9-144">História do alerta, que inclui um resumo do que aconteceu</span><span class="sxs-lookup"><span data-stu-id="648d9-144">Alert story, which includes a summary of what happened</span></span>
- <span data-ttu-id="648d9-145">Eventos e alertas relacionados</span><span class="sxs-lookup"><span data-stu-id="648d9-145">Related events and alerts</span></span>
- <span data-ttu-id="648d9-146">Detalhes de resumo</span><span class="sxs-lookup"><span data-stu-id="648d9-146">Summary details</span></span>

<span data-ttu-id="648d9-147">Saiba como usar a fila de alertas e as páginas de alerta em [alertas de investigação.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="648d9-147">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="648d9-148">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="648d9-148">Devices</span></span>

<span data-ttu-id="648d9-149">A **guia Dispositivos** lista todos os dispositivos relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-149">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="648d9-150">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="648d9-150">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Exemplo de uma página Dispositivos para um incidente":::

<span data-ttu-id="648d9-152">Você pode selecionar a marca de seleção de um dispositivo para ver detalhes do dispositivo, dados de diretório, alertas ativos e usuários conectados.</span><span class="sxs-lookup"><span data-stu-id="648d9-152">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="648d9-153">Selecione o nome do dispositivo para ver detalhes do dispositivo no inventário de dispositivos do Microsoft Defender for Endpoints.</span><span class="sxs-lookup"><span data-stu-id="648d9-153">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Exemplo de uma página de dispositivos do Microsoft Defender para Pontos de Extremidade":::

<span data-ttu-id="648d9-155">Na página do dispositivo, você pode coletar informações adicionais sobre o dispositivo, como todos os alertas, uma linha do tempo e recomendações de segurança.</span><span class="sxs-lookup"><span data-stu-id="648d9-155">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="648d9-156">Por exemplo,  na guia Linha do Tempo, você pode rolar pela linha do tempo do computador e exibir todos os eventos e comportamentos observados no computador em ordem cronológica, intercalados com os alertas gerados.</span><span class="sxs-lookup"><span data-stu-id="648d9-156">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="648d9-157">Você pode fazer verificações sob demanda em uma página de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="648d9-157">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="648d9-158">No centro de Microsoft 365 de segurança, escolha **Pontos de extremidade > Inventário de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="648d9-158">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="648d9-159">Selecione um dispositivo que tenha alertas e execute uma verificação antivírus.</span><span class="sxs-lookup"><span data-stu-id="648d9-159">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="648d9-160">Ações, como verificações de antivírus, são controladas e ficam visíveis na página **Inventário de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="648d9-160">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="648d9-161">Para saber mais, confira [Executar Microsoft Defender Antivírus verificação em dispositivos](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="648d9-161">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="648d9-162">Usuários</span><span class="sxs-lookup"><span data-stu-id="648d9-162">Users</span></span>

<span data-ttu-id="648d9-163">A **guia** Usuários lista todos os usuários que foram identificados para fazer parte ou relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-163">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="648d9-164">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="648d9-164">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exemplo de uma página Usuários para um incidente":::

<span data-ttu-id="648d9-166">Você pode selecionar a marca de seleção de um usuário para ver detalhes da ameaça, exposição e informações de contato da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="648d9-166">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="648d9-167">Selecione o nome de usuário para ver detalhes adicionais da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="648d9-167">Select the user name to see additional user account details.</span></span>

<span data-ttu-id="648d9-168">Saiba como exibir informações adicionais do usuário e gerenciar os usuários de um incidente na [investigação de usuários](investigate-users.md).</span><span class="sxs-lookup"><span data-stu-id="648d9-168">Learn how to view additional user information and manage the users of an incident in [investigate users](investigate-users.md).</span></span>


## <a name="mailboxes"></a><span data-ttu-id="648d9-169">Caixas de correio</span><span class="sxs-lookup"><span data-stu-id="648d9-169">Mailboxes</span></span>

<span data-ttu-id="648d9-170">A **guia Caixas de** Correio lista todas as caixas de correio identificadas como parte ou relacionadas ao incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-170">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="648d9-171">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="648d9-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Exemplo de uma página de Caixas de Correio para um incidente":::

<span data-ttu-id="648d9-173">Você pode selecionar a marca de seleção de uma caixa de correio para ver uma lista de alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="648d9-173">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="648d9-174">Selecione o nome da caixa de correio para ver detalhes adicionais da caixa de correio na página Explorer do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="648d9-174">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="648d9-175">Investigações</span><span class="sxs-lookup"><span data-stu-id="648d9-175">Investigations</span></span>

<span data-ttu-id="648d9-176">A **guia Investigações** lista todas [as investigações automatizadas](m365d-autoir.md) disparadas por alertas neste incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-176">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="648d9-177">As investigações executarão ações de correção ou aguardarão a aprovação de ações do analista, dependendo de como você configurou suas investigações automatizadas para executar no Microsoft Defender para Ponto de Extremidade e Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="648d9-177">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Exemplo de uma página Investigações para um incidente":::

<span data-ttu-id="648d9-179">Selecione uma investigação para navegar até sua página de detalhes para obter informações completas sobre o status da investigação e correção.</span><span class="sxs-lookup"><span data-stu-id="648d9-179">Select an investigation to navigate to its details page for full information on the investigation and remediation status.</span></span> <span data-ttu-id="648d9-180">Se houver ações pendentes para aprovação como parte da investigação, elas aparecerão na guia Histórico de ações **pendentes.** Tome medidas como parte da correção de incidentes.</span><span class="sxs-lookup"><span data-stu-id="648d9-180">If there are any actions pending for approval as part of the investigation, they will appear in the **Pending actions history** tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="648d9-181">Há também uma guia **Gráfico de Investigação** que mostra:</span><span class="sxs-lookup"><span data-stu-id="648d9-181">There is also an **Investigation graph** tab that shows:</span></span>

- <span data-ttu-id="648d9-182">A conexão de alertas com os ativos afetados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="648d9-182">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="648d9-183">Quais entidades estão relacionadas a quais alertas e como eles fazem parte da história do ataque.</span><span class="sxs-lookup"><span data-stu-id="648d9-183">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="648d9-184">Os alertas do incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-184">The alerts for the incident.</span></span>

<span data-ttu-id="648d9-185">O gráfico de investigação ajuda você a entender rapidamente o escopo completo do ataque conectando as diferentes entidades suspeitas que fazem parte do ataque com seus ativos relacionados, como usuários, dispositivos e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="648d9-185">The investigation graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="648d9-186">Para obter mais informações, consulte [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span><span class="sxs-lookup"><span data-stu-id="648d9-186">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="648d9-187">Evidências e resposta</span><span class="sxs-lookup"><span data-stu-id="648d9-187">Evidence and Response</span></span>

<span data-ttu-id="648d9-188">A **guia Evidências e Resposta** mostra todos os eventos com suporte e entidades suspeitas nos alertas do incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-188">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="648d9-189">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="648d9-189">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Exemplo de uma página evidências e resposta para um incidente":::

<span data-ttu-id="648d9-191">Microsoft 365 Defender investiga automaticamente todos os eventos com suporte dos incidentes e entidades suspeitas nos alertas, fornecendo informações sobre os emails importantes, arquivos, processos, serviços, endereços IP e muito mais.</span><span class="sxs-lookup"><span data-stu-id="648d9-191">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="648d9-192">Isso ajuda você a detectar e bloquear rapidamente possíveis ameaças no incidente.</span><span class="sxs-lookup"><span data-stu-id="648d9-192">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="648d9-193">Cada uma das entidades analisadas é marcada com um veredito (Mal-intencionado, suspeito, limpo) e um status de correção.</span><span class="sxs-lookup"><span data-stu-id="648d9-193">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="648d9-194">Isso ajuda você a entender o status de correção de todo o incidente e quais próximas etapas podem ser tomadas.</span><span class="sxs-lookup"><span data-stu-id="648d9-194">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="next-steps"></a><span data-ttu-id="648d9-195">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="648d9-195">Next steps</span></span>

<span data-ttu-id="648d9-196">Conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="648d9-196">As needed:</span></span>

- [<span data-ttu-id="648d9-197">Investigar os alertas de um incidente</span><span class="sxs-lookup"><span data-stu-id="648d9-197">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="648d9-198">Investigar os usuários de um incidente</span><span class="sxs-lookup"><span data-stu-id="648d9-198">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="648d9-199">Confira também</span><span class="sxs-lookup"><span data-stu-id="648d9-199">See also</span></span>

- [<span data-ttu-id="648d9-200">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="648d9-200">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="648d9-201">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="648d9-201">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="648d9-202">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="648d9-202">Manage incidents</span></span>](manage-incidents.md)

