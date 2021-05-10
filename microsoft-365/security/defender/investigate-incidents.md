---
title: Investigar incidentes no Microsoft 365 Defender
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7abc99a14ec538afea8cdbd4d8f3b4940bcccd9f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300080"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="93db6-104">Investigar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93db6-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="93db6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="93db6-105">**Applies to:**</span></span>

- <span data-ttu-id="93db6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93db6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="93db6-107">Microsoft 365 O Defender agrega todos os alertas, ativos, investigações e evidências relacionados entre seus dispositivos, usuários e caixas de correio em um incidente para dar uma olhada abrangente em toda a amplitude de um ataque.</span><span class="sxs-lookup"><span data-stu-id="93db6-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="93db6-108">Em um incidente, você analisa os alertas que afetam sua rede, entende o que significam e cola as evidências para que você possa planejar um plano de correção eficaz.</span><span class="sxs-lookup"><span data-stu-id="93db6-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="93db6-109">Investigação inicial</span><span class="sxs-lookup"><span data-stu-id="93db6-109">Initial investigation</span></span>

<span data-ttu-id="93db6-110">Antes de mergulhar nos detalhes, confira as propriedades e o resumo do incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="93db6-111">Você pode começar selecionando o incidente na coluna marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="93db6-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="93db6-112">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="93db6-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Exemplo de seleção de um incidente na coluna marca de verificação":::

<span data-ttu-id="93db6-114">Quando você faz isso, um painel de resumo é aberto com informações importantes sobre o incidente, como gravidade, a quem ele é atribuído, e as categorias de CK do [MITRE ATT &trade; ](https://attack.mitre.org/)&CK para o incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="93db6-115">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="93db6-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Exemplo do painel de resumo de um incidente":::

<span data-ttu-id="93db6-117">A partir daqui, você pode selecionar **Abrir página de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="93db6-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="93db6-118">Isso abre a página principal do incidente em que você encontrará mais informações resumidas e guias para alertas, dispositivos, usuários, investigações e evidências.</span><span class="sxs-lookup"><span data-stu-id="93db6-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="93db6-119">Você também pode abrir a página principal de um incidente selecionando o nome do incidente na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="93db6-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="93db6-120">Resumo</span><span class="sxs-lookup"><span data-stu-id="93db6-120">Summary</span></span>

<span data-ttu-id="93db6-121">A **página** Resumo fornece um resumo das principais coisas a observar sobre o incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exemplo da página Resumo de um incidente no centro Microsoft 365 segurança":::

<span data-ttu-id="93db6-123">As categorias de ataque dão a você uma visão visual e numérica de como o ataque avançou contra a cadeia de kill.</span><span class="sxs-lookup"><span data-stu-id="93db6-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="93db6-124">Assim como com outros produtos de segurança da Microsoft, Microsoft 365 Defender é alinhado à estrutura de CK do [MITRE ATT&&trade; CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="93db6-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="93db6-125">A seção escopo fornece uma lista dos principais ativos afetados que fazem parte desse incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="93db6-126">Se houver informações específicas sobre esse ativo, como nível de risco, prioridade de investigação, além de qualquer marcação nos ativos, também virão à tona nesta seção.</span><span class="sxs-lookup"><span data-stu-id="93db6-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="93db6-127">A linha do tempo de alertas fornece uma prévia da ordem cronológica na qual os alertas ocorreram, bem como os motivos pelos quais esses alertas estão vinculados a esse incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="93db6-128">E por último - a seção de evidências fornece um resumo de quantos artefatos diferentes foram incluídos no incidente e seu status de correção, para que você possa identificar imediatamente se qualquer ação é necessária por você.</span><span class="sxs-lookup"><span data-stu-id="93db6-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="93db6-129">Essa visão geral pode ajudar na triagem inicial do incidente fornecendo informações sobre as principais características do incidente que você deve estar ciente.</span><span class="sxs-lookup"><span data-stu-id="93db6-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="93db6-130">Alertas</span><span class="sxs-lookup"><span data-stu-id="93db6-130">Alerts</span></span>

<span data-ttu-id="93db6-131">Na guia **Alerta,** você pode exibir a fila de alertas para alertas relacionados ao incidente e outras informações sobre eles, como:</span><span class="sxs-lookup"><span data-stu-id="93db6-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="93db6-132">Severidade.</span><span class="sxs-lookup"><span data-stu-id="93db6-132">Severity.</span></span>
- <span data-ttu-id="93db6-133">As entidades envolvidas no alerta.</span><span class="sxs-lookup"><span data-stu-id="93db6-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="93db6-134">A origem dos alertas (Microsoft Defender para Identidade, Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="93db6-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="93db6-135">O motivo pelo qual eles foram vinculados.</span><span class="sxs-lookup"><span data-stu-id="93db6-135">The reason they were linked together.</span></span>

<span data-ttu-id="93db6-136">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="93db6-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Exemplo de uma página Alertas para um incidente":::

<span data-ttu-id="93db6-138">Por padrão, os alertas são ordenados cronologicamente para permitir que você veja como o incidente ocorreu ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="93db6-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="93db6-139">Selecionar cada alerta o leva à página principal do alerta, onde você pode conduzir uma análise detalhada desse alerta.</span><span class="sxs-lookup"><span data-stu-id="93db6-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth analysis of that alert.</span></span> 

<span data-ttu-id="93db6-140">Saiba como usar a fila de alertas e as páginas de alerta em [alertas de investigação.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="93db6-140">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="93db6-141">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="93db6-141">Devices</span></span>

<span data-ttu-id="93db6-142">A **guia Dispositivos** lista todos os dispositivos relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="93db6-143">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="93db6-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Exemplo de uma página Dispositivos para um incidente":::

<span data-ttu-id="93db6-145">Você pode selecionar a marca de seleção de um dispositivo para ver detalhes do dispositivo, dados de diretório, alertas ativos e usuários conectados.</span><span class="sxs-lookup"><span data-stu-id="93db6-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="93db6-146">Selecione o nome do dispositivo para ver detalhes do dispositivo no inventário de dispositivos do Microsoft Defender for Endpoints.</span><span class="sxs-lookup"><span data-stu-id="93db6-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Exemplo de uma página de dispositivos do Microsoft Defender para Pontos de Extremidade":::

<span data-ttu-id="93db6-148">Na página do dispositivo, você pode coletar informações adicionais sobre o dispositivo, como todos os alertas, uma linha do tempo e recomendações de segurança.</span><span class="sxs-lookup"><span data-stu-id="93db6-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="93db6-149">Por exemplo,  na guia Linha do Tempo, você pode rolar pela linha do tempo do computador e exibir todos os eventos e comportamentos observados no computador em ordem cronológica, intercalados com os alertas gerados.</span><span class="sxs-lookup"><span data-stu-id="93db6-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="93db6-150">Você pode fazer verificações sob demanda em uma página de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="93db6-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="93db6-151">No centro de Microsoft 365 de segurança, escolha **Pontos de extremidade > Inventário de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="93db6-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="93db6-152">Selecione um dispositivo que tenha alertas e execute uma verificação antivírus.</span><span class="sxs-lookup"><span data-stu-id="93db6-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="93db6-153">Ações, como verificações de antivírus, são controladas e ficam visíveis na página **Inventário de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="93db6-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="93db6-154">Para saber mais, confira [Executar Microsoft Defender Antivírus verificação em dispositivos](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="93db6-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="93db6-155">Usuários</span><span class="sxs-lookup"><span data-stu-id="93db6-155">Users</span></span>

<span data-ttu-id="93db6-156">A **guia** Usuários lista todos os usuários que foram identificados para fazer parte ou relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="93db6-157">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="93db6-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exemplo de uma página Usuários para um incidente":::

<span data-ttu-id="93db6-159">Você pode selecionar a marca de seleção de um usuário para ver detalhes da ameaça, exposição e informações de contato da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="93db6-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="93db6-160">Selecione o nome de usuário para ver detalhes adicionais da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="93db6-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="93db6-161">Caixas de correio</span><span class="sxs-lookup"><span data-stu-id="93db6-161">Mailboxes</span></span>

<span data-ttu-id="93db6-162">A **guia Caixas de** Correio lista todas as caixas de correio identificadas como parte ou relacionadas ao incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="93db6-163">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="93db6-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Exemplo de uma página de Caixas de Correio para um incidente":::

<span data-ttu-id="93db6-165">Você pode selecionar a marca de seleção de uma caixa de correio para ver uma lista de alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="93db6-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="93db6-166">Selecione o nome da caixa de correio para ver detalhes adicionais da caixa de correio na página Explorer do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="93db6-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="93db6-167">Investigações</span><span class="sxs-lookup"><span data-stu-id="93db6-167">Investigations</span></span>

<span data-ttu-id="93db6-168">A **guia Investigações** lista todas [as investigações automatizadas](m365d-autoir.md) disparadas por alertas neste incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-168">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="93db6-169">As investigações executarão ações de correção ou aguardarão a aprovação de ações do analista, dependendo de como você configurou suas investigações automatizadas para executar no Microsoft Defender para Ponto de Extremidade e Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="93db6-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Exemplo de uma página Investigações para um incidente":::

<span data-ttu-id="93db6-171">Clique em uma investigação para navegar até a página Detalhes da investigação e obter informações completas sobre o status da investigação e da correção.</span><span class="sxs-lookup"><span data-stu-id="93db6-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="93db6-172">Se houver ações pendentes para aprovação como parte da investigação, elas aparecerão na guia Ações pendentes. Tome medidas como parte da correção de incidentes.</span><span class="sxs-lookup"><span data-stu-id="93db6-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="93db6-173">Para obter mais informações, consulte [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span><span class="sxs-lookup"><span data-stu-id="93db6-173">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="93db6-174">Evidências e resposta</span><span class="sxs-lookup"><span data-stu-id="93db6-174">Evidence and Response</span></span>

<span data-ttu-id="93db6-175">A **guia Evidências e Resposta** mostra todos os eventos com suporte e entidades suspeitas nos alertas do incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-175">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="93db6-176">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="93db6-176">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Exemplo de uma página evidências e resposta para um incidente":::

<span data-ttu-id="93db6-178">Microsoft 365 O Defender investiga automaticamente todos os eventos com suporte dos incidentes e entidades suspeitas nos alertas, fornecendo informações sobre os emails importantes, arquivos, processos, serviços, endereços IP e muito mais.</span><span class="sxs-lookup"><span data-stu-id="93db6-178">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="93db6-179">Isso ajuda você a detectar e bloquear rapidamente possíveis ameaças no incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-179">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="93db6-180">Cada uma das entidades analisadas é marcada com um veredito (Mal-intencionado, suspeito, limpo) e um status de correção.</span><span class="sxs-lookup"><span data-stu-id="93db6-180">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="93db6-181">Isso ajuda você a entender o status de correção de todo o incidente e quais próximas etapas podem ser tomadas.</span><span class="sxs-lookup"><span data-stu-id="93db6-181">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="93db6-182">Graph (em visualização)</span><span class="sxs-lookup"><span data-stu-id="93db6-182">Graph (in preview)</span></span>

<span data-ttu-id="93db6-183">Com a nova **guia Graph** (na visualização), você pode ver:</span><span class="sxs-lookup"><span data-stu-id="93db6-183">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="93db6-184">A conexão de alertas com os ativos afetados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="93db6-184">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="93db6-185">Quais entidades estão relacionadas a quais alertas e como eles fazem parte da história do ataque.</span><span class="sxs-lookup"><span data-stu-id="93db6-185">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="93db6-186">Os alertas do incidente.</span><span class="sxs-lookup"><span data-stu-id="93db6-186">The alerts for the incident.</span></span>

<span data-ttu-id="93db6-187">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="93db6-187">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="Exemplo de uma página Graph para um incidente":::

<span data-ttu-id="93db6-189">O gráfico de incidentes ajuda você a entender rapidamente o escopo completo do ataque conectando as diferentes entidades suspeitas que fazem parte do ataque com seus ativos relacionados, como usuários, dispositivos e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="93db6-189">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="93db6-190">Agora você pode entender como o ataque se propaga pela rede ao longo do tempo, onde ele começou e até onde o ataque foi.</span><span class="sxs-lookup"><span data-stu-id="93db6-190">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>

## <a name="next-steps"></a><span data-ttu-id="93db6-191">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="93db6-191">Next steps</span></span>

<span data-ttu-id="93db6-192">Conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="93db6-192">As needed:</span></span>

- [<span data-ttu-id="93db6-193">Investigar os alertas de um incidente</span><span class="sxs-lookup"><span data-stu-id="93db6-193">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="93db6-194">Investigar os usuários de um incidente</span><span class="sxs-lookup"><span data-stu-id="93db6-194">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="93db6-195">Confira também</span><span class="sxs-lookup"><span data-stu-id="93db6-195">See also</span></span>

- [<span data-ttu-id="93db6-196">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="93db6-196">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="93db6-197">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="93db6-197">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="93db6-198">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="93db6-198">Manage incidents</span></span>](manage-incidents.md)

