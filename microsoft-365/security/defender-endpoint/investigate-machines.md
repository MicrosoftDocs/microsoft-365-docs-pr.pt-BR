---
title: Investigar dispositivos na lista Defender for Endpoint Defender ATP Devices
description: Investigue os dispositivos afetados revisando alertas, informações de conexão de rede, adicionando marcas de dispositivo e grupos e verificando a saúde do serviço.
keywords: devices, tags, groups, endpoint, alerts queue, alerts, device name, domain, last seen, internal IP, active alerts, threat category, filter, sort, review alerts, network, connection, type, password stealer, ransomware, exploit, threat, low severity, service health
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8f5415b6337d21b780a75a192a565078a6cacc06
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185726"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="15217-104">Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="15217-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="15217-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="15217-105">**Applies to:**</span></span>
- [<span data-ttu-id="15217-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="15217-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="15217-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15217-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="15217-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="15217-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="15217-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="15217-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="15217-110">Investigue os detalhes de um alerta gerado em um dispositivo específico para identificar outros comportamentos ou eventos que possam estar relacionados ao alerta ou ao escopo potencial da violação.</span><span class="sxs-lookup"><span data-stu-id="15217-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="15217-111">Como parte do processo de investigação ou resposta, você pode coletar um pacote de investigação de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15217-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="15217-112">Veja como: Coletar o pacote [de investigação de dispositivos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="15217-112">Here's how: [Collect investigation package from devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="15217-113">Você pode clicar em dispositivos afetados sempre que os vir no portal para abrir um relatório detalhado sobre esse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15217-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="15217-114">Os dispositivos afetados são identificados nas seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="15217-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="15217-115">Lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="15217-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="15217-116">Fila de alertas</span><span class="sxs-lookup"><span data-stu-id="15217-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="15217-117">Painel de operações de segurança</span><span class="sxs-lookup"><span data-stu-id="15217-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="15217-118">Qualquer alerta individual</span><span class="sxs-lookup"><span data-stu-id="15217-118">Any individual alert</span></span>
- <span data-ttu-id="15217-119">Qualquer exibição de detalhes de arquivo individual</span><span class="sxs-lookup"><span data-stu-id="15217-119">Any individual file details view</span></span>
- <span data-ttu-id="15217-120">Qualquer endereço IP ou exibição de detalhes de domínio</span><span class="sxs-lookup"><span data-stu-id="15217-120">Any IP address or domain details view</span></span>

<span data-ttu-id="15217-121">Ao investigar um dispositivo específico, você verá:</span><span class="sxs-lookup"><span data-stu-id="15217-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="15217-122">Detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="15217-122">Device details</span></span>
- <span data-ttu-id="15217-123">Ações de resposta</span><span class="sxs-lookup"><span data-stu-id="15217-123">Response actions</span></span>
- <span data-ttu-id="15217-124">Guias (visão geral, alertas, linha do tempo, recomendações de segurança, inventário de software, vulnerabilidades descobertas, KBs ausentes)</span><span class="sxs-lookup"><span data-stu-id="15217-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="15217-125">Cartões (alertas ativos, usuários conectados, avaliação de segurança)</span><span class="sxs-lookup"><span data-stu-id="15217-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Imagem do visualização do dispositivo](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="15217-127">Detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="15217-127">Device details</span></span>

<span data-ttu-id="15217-128">A seção detalhes do dispositivo fornece informações como o domínio, o sistema operacional e o estado de saúde do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15217-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="15217-129">Se houver um pacote de investigação disponível no dispositivo, você verá um link que permite baixar o pacote.</span><span class="sxs-lookup"><span data-stu-id="15217-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="15217-130">Ações de resposta</span><span class="sxs-lookup"><span data-stu-id="15217-130">Response actions</span></span>

<span data-ttu-id="15217-131">As ações de resposta são executados ao longo da parte superior de uma página de dispositivo específica e incluem:</span><span class="sxs-lookup"><span data-stu-id="15217-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="15217-132">Gerenciar marcas</span><span class="sxs-lookup"><span data-stu-id="15217-132">Manage tags</span></span>
- <span data-ttu-id="15217-133">Isolar dispositivo</span><span class="sxs-lookup"><span data-stu-id="15217-133">Isolate device</span></span>
- <span data-ttu-id="15217-134">Restringir a execução do aplicativo</span><span class="sxs-lookup"><span data-stu-id="15217-134">Restrict app execution</span></span>
- <span data-ttu-id="15217-135">Executar verificação antivírus</span><span class="sxs-lookup"><span data-stu-id="15217-135">Run antivirus scan</span></span>
- <span data-ttu-id="15217-136">Coletar pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="15217-136">Collect investigation package</span></span>
- <span data-ttu-id="15217-137">Iniciar sessão de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="15217-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="15217-138">Iniciar investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="15217-138">Initiate automated investigation</span></span>
- <span data-ttu-id="15217-139">Consultar um especialista em ameaças</span><span class="sxs-lookup"><span data-stu-id="15217-139">Consult a threat expert</span></span>
- <span data-ttu-id="15217-140">Central de ações</span><span class="sxs-lookup"><span data-stu-id="15217-140">Action center</span></span>

<span data-ttu-id="15217-141">Você pode tomar ações de resposta no Centro de Ações, em uma página de dispositivo específica ou em uma página de arquivo específica.</span><span class="sxs-lookup"><span data-stu-id="15217-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="15217-142">Para obter mais informações sobre como agir em um dispositivo, consulte [Take response action on a device](respond-machine-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="15217-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="15217-143">Para obter mais informações, consulte [Investigar entidades do usuário](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="15217-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="15217-144">Guias</span><span class="sxs-lookup"><span data-stu-id="15217-144">Tabs</span></span>

<span data-ttu-id="15217-145">As guias fornecem informações relevantes de prevenção de ameaças e segurança relacionadas ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15217-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="15217-146">Em cada guia, você pode personalizar as colunas mostradas selecionando **Personalizar colunas** da barra acima dos headers da coluna.</span><span class="sxs-lookup"><span data-stu-id="15217-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="15217-147">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="15217-147">Overview</span></span>
<span data-ttu-id="15217-148">A **guia Visão** geral exibe os cartões [para](#cards) alertas ativos, conectados aos usuários e avaliação de segurança.</span><span class="sxs-lookup"><span data-stu-id="15217-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Imagem da guia visão geral na página do dispositivo](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="15217-150">Alertas</span><span class="sxs-lookup"><span data-stu-id="15217-150">Alerts</span></span>

<span data-ttu-id="15217-151">A **guia Alertas** fornece uma lista de alertas associados ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15217-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="15217-152">Esta lista é uma versão filtrada da fila de [Alertas](alerts-queue.md)e mostra uma breve descrição do alerta, gravidade (alto, médio, baixo, informacional), status na fila (novo, em andamento, resolvido), classificação (não definido, alerta falso, alerta verdadeiro), estado de investigação, categoria de alerta, quem está abordando o alerta e a última atividade.</span><span class="sxs-lookup"><span data-stu-id="15217-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="15217-153">Você também pode filtrar os alertas.</span><span class="sxs-lookup"><span data-stu-id="15217-153">You can also filter the alerts.</span></span>

![Imagem de alertas relacionados ao dispositivo](images/alerts-device.png)

<span data-ttu-id="15217-155">Quando o ícone de círculo à esquerda de um alerta é selecionado, um sub-menu é exibido.</span><span class="sxs-lookup"><span data-stu-id="15217-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="15217-156">Neste painel, você pode gerenciar o alerta e exibir mais detalhes, como número de incidentes e dispositivos relacionados.</span><span class="sxs-lookup"><span data-stu-id="15217-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="15217-157">Vários alertas podem ser selecionados por vez.</span><span class="sxs-lookup"><span data-stu-id="15217-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="15217-158">Para ver uma exibição de página completa de um alerta, incluindo gráfico de incidentes e árvore de processo, selecione o título do alerta.</span><span class="sxs-lookup"><span data-stu-id="15217-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="15217-159">Linha do tempo</span><span class="sxs-lookup"><span data-stu-id="15217-159">Timeline</span></span>

<span data-ttu-id="15217-160">A **guia Linha** do Tempo fornece uma exibição cronológica dos eventos e alertas associados que foram observados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15217-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="15217-161">Isso pode ajudá-lo a correlacionar quaisquer eventos, arquivos e endereços IP em relação ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15217-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="15217-162">A linha do tempo também permite que você faça uma análise seletiva de eventos que ocorreram dentro de um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="15217-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="15217-163">Você pode exibir a sequência temporal de eventos que ocorreram em um dispositivo durante um período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="15217-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="15217-164">Para controlar ainda mais sua exibição, você pode filtrar por grupos de eventos ou personalizar as colunas.</span><span class="sxs-lookup"><span data-stu-id="15217-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="15217-165">Para que os eventos de firewall sejam exibidos, você precisará habilitar a política de auditoria, consulte [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span><span class="sxs-lookup"><span data-stu-id="15217-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="15217-166">O firewall abrange os seguintes eventos</span><span class="sxs-lookup"><span data-stu-id="15217-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="15217-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - serviço de firewall interrompido</span><span class="sxs-lookup"><span data-stu-id="15217-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="15217-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - aplicativo impedido de aceitar conexões de entrada na rede</span><span class="sxs-lookup"><span data-stu-id="15217-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="15217-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - conexão bloqueada</span><span class="sxs-lookup"><span data-stu-id="15217-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Imagem da linha do tempo do dispositivo com eventos](images/timeline-device.png)

<span data-ttu-id="15217-171">Algumas das funcionalidades incluem:</span><span class="sxs-lookup"><span data-stu-id="15217-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="15217-172">Pesquisar eventos específicos</span><span class="sxs-lookup"><span data-stu-id="15217-172">Search for specific events</span></span>
  - <span data-ttu-id="15217-173">Use a barra de pesquisa para procurar eventos de linha do tempo específicos.</span><span class="sxs-lookup"><span data-stu-id="15217-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="15217-174">Filtrar eventos de uma data específica</span><span class="sxs-lookup"><span data-stu-id="15217-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="15217-175">Selecione o ícone de calendário no canto superior esquerdo da tabela para exibir eventos no último dia, semana, 30 dias ou intervalo personalizado.</span><span class="sxs-lookup"><span data-stu-id="15217-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="15217-176">Por padrão, a linha do tempo do dispositivo é definida para exibir os eventos dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="15217-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="15217-177">Use a linha do tempo para pular para um momento específico no tempo realçando a seção.</span><span class="sxs-lookup"><span data-stu-id="15217-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="15217-178">As setas na linha do tempo apontam investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="15217-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="15217-179">Exportar eventos de linha do tempo detalhados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="15217-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="15217-180">Exporte a linha do tempo do dispositivo para a data atual ou um intervalo de data especificado até sete dias.</span><span class="sxs-lookup"><span data-stu-id="15217-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="15217-181">Mais detalhes sobre determinados eventos são fornecidos na **seção Informações** adicionais.</span><span class="sxs-lookup"><span data-stu-id="15217-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="15217-182">Esses detalhes variam dependendo do tipo de evento, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="15217-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="15217-183">Contido pelo Application Guard - o evento do navegador da Web foi restrito por um contêiner isolado</span><span class="sxs-lookup"><span data-stu-id="15217-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="15217-184">Ameaça ativa detectada - a detecção de ameaça ocorreu enquanto a ameaça estava em execução</span><span class="sxs-lookup"><span data-stu-id="15217-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="15217-185">Correção malsucedida - uma tentativa de correção da ameaça detectada foi invocada, mas falhou</span><span class="sxs-lookup"><span data-stu-id="15217-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="15217-186">Correção bem-sucedida - a ameaça detectada foi interrompida e limpa</span><span class="sxs-lookup"><span data-stu-id="15217-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="15217-187">Aviso ignorado pelo usuário - o aviso Windows Defender SmartScreen foi ignorado e substituído por um usuário</span><span class="sxs-lookup"><span data-stu-id="15217-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="15217-188">Script suspeito detectado - um script potencialmente mal-intencionado foi encontrado em execução</span><span class="sxs-lookup"><span data-stu-id="15217-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="15217-189">A categoria de alerta - se o evento levou à geração de um alerta, a categoria de alerta ("Movimento Lateral", por exemplo) é fornecida</span><span class="sxs-lookup"><span data-stu-id="15217-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="15217-190">Detalhes do evento</span><span class="sxs-lookup"><span data-stu-id="15217-190">Event details</span></span>
<span data-ttu-id="15217-191">Selecione um evento para exibir detalhes relevantes sobre esse evento.</span><span class="sxs-lookup"><span data-stu-id="15217-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="15217-192">Um painel é exibido para mostrar informações gerais do evento.</span><span class="sxs-lookup"><span data-stu-id="15217-192">A panel displays to show general event information.</span></span> <span data-ttu-id="15217-193">Quando aplicável e os dados estão disponíveis, um gráfico mostrando entidades relacionadas e suas relações também são mostrados.</span><span class="sxs-lookup"><span data-stu-id="15217-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="15217-194">Para inspecionar ainda mais o evento e [](advanced-hunting-overview.md) os eventos relacionados, você pode executar rapidamente uma consulta de busca avançada selecionando **Hunt para eventos relacionados.**</span><span class="sxs-lookup"><span data-stu-id="15217-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="15217-195">A consulta retornará o evento selecionado e a lista de outros eventos que ocorreram ao mesmo tempo no mesmo ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="15217-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Imagem do painel de detalhes do evento](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="15217-197">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="15217-197">Security recommendations</span></span>

<span data-ttu-id="15217-198">**As recomendações de segurança** são geradas do Microsoft Defender para o recurso de Gerenciamento de [Vulnerabilidades](tvm-dashboard-insights.md) & Ameaças do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="15217-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="15217-199">Selecionar uma recomendação mostrará um painel onde você pode exibir detalhes relevantes, como a descrição da recomendação e os riscos potenciais associados à não decretação.</span><span class="sxs-lookup"><span data-stu-id="15217-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="15217-200">Consulte [Recomendação de segurança](tvm-security-recommendation.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="15217-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Guia De recomendações de segurança](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="15217-202">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="15217-202">Software inventory</span></span>

<span data-ttu-id="15217-203">A **guia Inventário de** software permite que você veja o software no dispositivo, juntamente com quaisquer pontos fracos ou ameaças.</span><span class="sxs-lookup"><span data-stu-id="15217-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="15217-204">Selecionar o nome do software levará você para a página de detalhes do software onde você pode exibir recomendações de segurança, vulnerabilidades descobertas, dispositivos instalados e distribuição de versão.</span><span class="sxs-lookup"><span data-stu-id="15217-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="15217-205">Consulte [Inventário de software](tvm-software-inventory.md) para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="15217-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Imagem da guia inventário de software](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="15217-207">Vulnerabilidades descobertas</span><span class="sxs-lookup"><span data-stu-id="15217-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="15217-208">A **guia Vulnerabilidades Descobertas** mostra o nome, a gravidade e as percepções de ameaça das vulnerabilidades descobertas no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15217-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="15217-209">Selecionar vulnerabilidades específicas mostrará uma descrição e detalhes.</span><span class="sxs-lookup"><span data-stu-id="15217-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![Imagem da guia vulnerabilidades descobertas](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="15217-211">KBs ausentes</span><span class="sxs-lookup"><span data-stu-id="15217-211">Missing KBs</span></span>
<span data-ttu-id="15217-212">A **guia KBs ausentes** lista as atualizações de segurança ausentes para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15217-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Imagem da guia kbs ausente](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="15217-214">Cartões</span><span class="sxs-lookup"><span data-stu-id="15217-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="15217-215">Alertas ativos</span><span class="sxs-lookup"><span data-stu-id="15217-215">Active alerts</span></span>

<span data-ttu-id="15217-216">O cartão proteção avançada contra ameaças do **Azure** exibirá uma visão geral de alto nível dos alertas relacionados ao dispositivo e seu nível de risco, se você tiver habilitado o recurso ATP do Azure e houver alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="15217-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Azure ATP feature, and there are any active alerts.</span></span> <span data-ttu-id="15217-217">Mais informações estão disponíveis na sonda "Alertas".</span><span class="sxs-lookup"><span data-stu-id="15217-217">More information is available in the "Alerts" drill down.</span></span>

![Imagem do cartão de alertas ativos](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="15217-219">Você precisará habilitar a integração no Azure ATP e no Defender for Endpoint para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="15217-219">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="15217-220">No Defender para Ponto de Extremidade, você pode habilitar esse recurso em recursos avançados.</span><span class="sxs-lookup"><span data-stu-id="15217-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="15217-221">Para obter mais informações sobre como habilitar recursos avançados, consulte [Ativar recursos avançados](advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="15217-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="15217-222">Usuários conectados</span><span class="sxs-lookup"><span data-stu-id="15217-222">Logged on users</span></span>

<span data-ttu-id="15217-223">O **cartão Usuários** Conectados mostra quantos usuários entraram nos últimos 30 dias, juntamente com os usuários mais e menos frequentes.</span><span class="sxs-lookup"><span data-stu-id="15217-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="15217-224">Selecionar o link "Ver todos os usuários" abre o painel de detalhes, que exibe informações como tipo de usuário, tipo de logoff e quando o usuário foi visto pela primeira e última vez.</span><span class="sxs-lookup"><span data-stu-id="15217-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="15217-225">Para obter mais informações, consulte [Investigar entidades do usuário](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="15217-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Imagem do painel de detalhes do usuário](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="15217-227">Avaliações de segurança</span><span class="sxs-lookup"><span data-stu-id="15217-227">Security assessments</span></span>

<span data-ttu-id="15217-228">O **cartão de avaliações de** segurança mostra o nível geral de exposição, recomendações de segurança, software instalado e vulnerabilidades descobertas.</span><span class="sxs-lookup"><span data-stu-id="15217-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="15217-229">O nível de exposição de um dispositivo é determinado pelo impacto acumulado de suas recomendações de segurança pendentes.</span><span class="sxs-lookup"><span data-stu-id="15217-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Imagem do cartão de avaliações de segurança](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="15217-231">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="15217-231">Related topics</span></span>

- [<span data-ttu-id="15217-232">Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="15217-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="15217-233">Gerenciar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="15217-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="15217-234">Investigar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="15217-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="15217-235">Investigar um arquivo associado a um alerta do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="15217-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="15217-236">Investigar um endereço IP associado a um alerta do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="15217-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="15217-237">Investigar um domínio associado a um alerta do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="15217-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="15217-238">Investigar uma conta de usuário no Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="15217-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="15217-239">Recomendação de segurança</span><span class="sxs-lookup"><span data-stu-id="15217-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="15217-240">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="15217-240">Software inventory</span></span>](tvm-software-inventory.md)
