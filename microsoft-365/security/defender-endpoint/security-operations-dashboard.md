---
title: Painel de operações do Centro de Segurança do Microsoft Defender
description: Use o painel para identificar dispositivos em risco, acompanhar o status do serviço e ver estatísticas e informações sobre dispositivos e alertas.
keywords: painel, alertas, novo, em andamento, resolvido, risco, dispositivos em risco, infecções, relatórios, estatísticas, gráficos, gráficos, saúde, detecções de malware ativo, categoria de ameaças, categorias, roubo de senha, ransomware, exploração, ameaça, baixa gravidade, malware ativo
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053573"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="70da8-104">Painel de operações do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="70da8-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="70da8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="70da8-105">**Applies to:**</span></span>
- [<span data-ttu-id="70da8-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="70da8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="70da8-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="70da8-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="70da8-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="70da8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="70da8-109">O **painel operações de segurança** é onde os recursos de detecção e resposta do ponto de extremidade são a superfície.</span><span class="sxs-lookup"><span data-stu-id="70da8-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="70da8-110">Ele fornece uma visão geral de alto nível de onde as detecções foram vistas e realça onde as ações de resposta são necessárias.</span><span class="sxs-lookup"><span data-stu-id="70da8-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="70da8-111">O painel exibe um instantâneo de:</span><span class="sxs-lookup"><span data-stu-id="70da8-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="70da8-112">Alertas ativos</span><span class="sxs-lookup"><span data-stu-id="70da8-112">Active alerts</span></span>
- <span data-ttu-id="70da8-113">Dispositivos em risco</span><span class="sxs-lookup"><span data-stu-id="70da8-113">Devices at risk</span></span>
- <span data-ttu-id="70da8-114">Saúde do sensor</span><span class="sxs-lookup"><span data-stu-id="70da8-114">Sensor health</span></span>
- <span data-ttu-id="70da8-115">Integridade do serviço</span><span class="sxs-lookup"><span data-stu-id="70da8-115">Service health</span></span>
- <span data-ttu-id="70da8-116">Relatórios diários de dispositivos</span><span class="sxs-lookup"><span data-stu-id="70da8-116">Daily devices reporting</span></span>
- <span data-ttu-id="70da8-117">Investigações automatizadas ativas</span><span class="sxs-lookup"><span data-stu-id="70da8-117">Active automated investigations</span></span>
- <span data-ttu-id="70da8-118">Estatísticas de investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="70da8-118">Automated investigations statistics</span></span>
- <span data-ttu-id="70da8-119">Usuários em risco</span><span class="sxs-lookup"><span data-stu-id="70da8-119">Users at risk</span></span>
- <span data-ttu-id="70da8-120">Atividades suspeitas</span><span class="sxs-lookup"><span data-stu-id="70da8-120">Suspicious activities</span></span>


![Painel de operações de segurança](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="70da8-122">Você pode explorar e investigar alertas e dispositivos para determinar rapidamente se, onde e quando atividades suspeitas ocorreram em sua rede para ajudá-lo a entender o contexto em que eles surgiram.</span><span class="sxs-lookup"><span data-stu-id="70da8-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="70da8-123">No painel **Operações de segurança,** você verá eventos agregados para facilitar a identificação de eventos significativos ou comportamentos em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="70da8-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="70da8-124">Você também pode detalhar eventos granulares e indicadores de baixo nível.</span><span class="sxs-lookup"><span data-stu-id="70da8-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="70da8-125">Ele também tem blocos clicáveis que dão dicas visuais sobre o estado de saúde geral da sua organização.</span><span class="sxs-lookup"><span data-stu-id="70da8-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="70da8-126">Cada tile abre uma exibição detalhada da visão geral correspondente.</span><span class="sxs-lookup"><span data-stu-id="70da8-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="70da8-127">Alertas ativos</span><span class="sxs-lookup"><span data-stu-id="70da8-127">Active alerts</span></span>
<span data-ttu-id="70da8-128">Você pode exibir o número geral de alertas ativos dos últimos 30 dias em sua rede a partir do azulejo.</span><span class="sxs-lookup"><span data-stu-id="70da8-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="70da8-129">Os alertas são agrupados **em Novo** e **Em andamento.**</span><span class="sxs-lookup"><span data-stu-id="70da8-129">Alerts are grouped into **New** and **In progress**.</span></span>

![Clique em cada fatia ou severidade para ver uma lista de alertas dos últimos 30 dias](images/active-alerts-tile.png)

<span data-ttu-id="70da8-131">Cada grupo é ainda mais sub categorizado em seus níveis de gravidade de alerta correspondentes.</span><span class="sxs-lookup"><span data-stu-id="70da8-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="70da8-132">Clique no número de alertas dentro de cada anel de alerta para ver uma exibição classificação da fila dessa categoria (**Novo** **ou Em andamento**).</span><span class="sxs-lookup"><span data-stu-id="70da8-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="70da8-133">Para obter mais informações, consulte Visão [geral de alertas.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="70da8-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="70da8-134">Cada linha inclui uma categoria de gravidade de alerta e uma breve descrição do alerta.</span><span class="sxs-lookup"><span data-stu-id="70da8-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="70da8-135">Você pode clicar em um alerta para ver sua exibição detalhada.</span><span class="sxs-lookup"><span data-stu-id="70da8-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="70da8-136">Para obter mais informações, [consulte Investigar o Microsoft Defender para alertas](investigate-alerts.md) de ponto de extremidade e visão geral de [alertas.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="70da8-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="70da8-137">Dispositivos em risco</span><span class="sxs-lookup"><span data-stu-id="70da8-137">Devices at risk</span></span>
<span data-ttu-id="70da8-138">Esse azulejo mostra uma lista de dispositivos com o maior número de alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="70da8-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="70da8-139">O número total de alertas para cada dispositivo é mostrado em um círculo ao lado do nome do dispositivo e, em seguida, categorizado ainda mais por níveis de severidade no final do azulejo (passe o mouse sobre cada barra de gravidade para ver seu rótulo).</span><span class="sxs-lookup"><span data-stu-id="70da8-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![O telha dispositivos em risco mostra uma lista de dispositivos com o maior número de alertas e uma divisão da gravidade dos alertas](images/devices-at-risk-tile.png)

<span data-ttu-id="70da8-141">Clique no nome do dispositivo para ver detalhes sobre esse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="70da8-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="70da8-142">Para obter mais informações, [consulte Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="70da8-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="70da8-143">Você também pode clicar na lista **Dispositivos** na parte superior do azulejo para ir diretamente para a lista **Dispositivos**, classificação pelo número de alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="70da8-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="70da8-144">Para obter mais informações, [consulte Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="70da8-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="70da8-145">Dispositivos com problemas de sensor</span><span class="sxs-lookup"><span data-stu-id="70da8-145">Devices with sensor issues</span></span>
<span data-ttu-id="70da8-146">O **pacote Dispositivos com problemas** de sensor fornece informações sobre a capacidade do dispositivo individual de fornecer dados do sensor ao serviço Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="70da8-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="70da8-147">Ele relata quantos dispositivos exigem atenção e ajuda a identificar dispositivos problemáticos.</span><span class="sxs-lookup"><span data-stu-id="70da8-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![Dispositivos com problemas de sensor de tile](images/atp-tile-sensor-health.png)

<span data-ttu-id="70da8-149">Há dois indicadores de status que fornecem informações sobre o número de dispositivos que não estão relatando corretamente para o serviço:</span><span class="sxs-lookup"><span data-stu-id="70da8-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="70da8-150">**Mal configurado** – esses dispositivos podem estar relatando parcialmente dados do sensor para o serviço do Microsoft Defender para Ponto de Extremidade e podem ter erros de configuração que precisam ser corrigidos.</span><span class="sxs-lookup"><span data-stu-id="70da8-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="70da8-151">**Inativos** - Dispositivos que pararam de relatar para o serviço Microsoft Defender para Ponto de Extremidade por mais de sete dias no mês passado.</span><span class="sxs-lookup"><span data-stu-id="70da8-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="70da8-152">Quando você clicar em qualquer um dos grupos, você será direcionado para a lista de dispositivos, filtrado de acordo com sua escolha.</span><span class="sxs-lookup"><span data-stu-id="70da8-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="70da8-153">Para obter mais informações, consulte [Verificar o estado do sensor](check-sensor-status.md) e investigar [dispositivos](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="70da8-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="70da8-154">Integridade do serviço</span><span class="sxs-lookup"><span data-stu-id="70da8-154">Service health</span></span>
<span data-ttu-id="70da8-155">O **azulejo de** saúde do serviço informa se o serviço está ativo ou se há problemas.</span><span class="sxs-lookup"><span data-stu-id="70da8-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![O azulejo de saúde do serviço mostra um indicador geral do serviço](images/status-tile.png)

<span data-ttu-id="70da8-157">Para obter mais informações sobre a saúde do serviço, consulte [Check the Microsoft Defender for Endpoint service health](service-status.md).</span><span class="sxs-lookup"><span data-stu-id="70da8-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="70da8-158">Relatórios diários de dispositivos</span><span class="sxs-lookup"><span data-stu-id="70da8-158">Daily devices reporting</span></span>
<span data-ttu-id="70da8-159">O **gráfico de relatório** de dispositivos diários mostra um gráfico de barras que representa o número de dispositivos que relatam diariamente nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="70da8-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="70da8-160">Passe o mouse sobre barras individuais no gráfico para ver o número exato de dispositivos relatando em cada dia.</span><span class="sxs-lookup"><span data-stu-id="70da8-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![Imagem do tile de relatório de dispositivos diários](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="70da8-162">Investigações automatizadas ativas</span><span class="sxs-lookup"><span data-stu-id="70da8-162">Active automated investigations</span></span>
<span data-ttu-id="70da8-163">Você pode exibir o número geral de investigações automatizadas dos últimos 30 dias em sua rede a partir do conjunto de **investigações automatizadas** ativas.</span><span class="sxs-lookup"><span data-stu-id="70da8-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="70da8-164">As investigações são agrupadas em **Ação Pendente,** **Aguardando dispositivo** e **Execução.**</span><span class="sxs-lookup"><span data-stu-id="70da8-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![Inmage of active automated investigations](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="70da8-166">Estatísticas de investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="70da8-166">Automated investigations statistics</span></span>
<span data-ttu-id="70da8-167">Este tile mostra estatísticas relacionadas a investigações automatizadas nos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="70da8-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="70da8-168">Ele mostra o número de investigações concluídas, o número de investigações remediadas com êxito, o tempo médio de espera necessário para que uma investigação seja iniciada, o tempo médio necessário para correção de um alerta, o número de alertas investigados e o número de horas de automação salvas de uma investigação manual típica.</span><span class="sxs-lookup"><span data-stu-id="70da8-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![Imagem das estatísticas de investigações automatizadas](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="70da8-170">Você pode clicar em **Investigações Automatizadas,** **Investigações** Corretivas e **Alertas investigados** para navegar até a página **Investigações,** filtrada pela categoria apropriada.</span><span class="sxs-lookup"><span data-stu-id="70da8-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="70da8-171">Isso permite que você veja uma divisão detalhada das investigações no contexto.</span><span class="sxs-lookup"><span data-stu-id="70da8-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="70da8-172">Usuários em risco</span><span class="sxs-lookup"><span data-stu-id="70da8-172">Users at risk</span></span>
<span data-ttu-id="70da8-173">O azulejo mostra uma lista de contas de usuário com alertas mais ativos e o número de alertas vistos em alertas altos, médios ou baixos.</span><span class="sxs-lookup"><span data-stu-id="70da8-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![As contas de usuário em um tile de risco mostram uma lista de contas de usuário com o maior número de alertas e uma divisão da gravidade dos alertas](images/atp-users-at-risk.png)

<span data-ttu-id="70da8-175">Clique na conta de usuário para ver detalhes sobre a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="70da8-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="70da8-176">Para obter mais informações, [consulte Investigar uma conta de usuário](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="70da8-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="70da8-177">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="70da8-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="70da8-178">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="70da8-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="70da8-179">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="70da8-179">Related topics</span></span>
- [<span data-ttu-id="70da8-180">Entender o portal do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="70da8-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="70da8-181">Visão geral do portal</span><span class="sxs-lookup"><span data-stu-id="70da8-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="70da8-182">Exibir o painel gerenciamento de & de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="70da8-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="70da8-183">Exibir o painel de análise de ameaças e tomar ações de mitigação recomendadas</span><span class="sxs-lookup"><span data-stu-id="70da8-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
