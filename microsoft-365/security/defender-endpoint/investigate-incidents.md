---
title: Investigar incidentes no Microsoft Defender ATP
description: Consulte alertas associados, gerencie o incidente e consulte metadados de alerta para ajudá-lo a investigar um incidente
keywords: investigar, incidente, alertas, metadados, risco, fonte de detecção, dispositivos afetados, padrões, correlação
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
ms.openlocfilehash: 5a74da55d733d690cb218c78b87b67d6eba6b9d2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186048"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="11f03-104">Investigar incidentes no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="11f03-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="11f03-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="11f03-105">**Applies to:**</span></span>
- [<span data-ttu-id="11f03-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="11f03-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="11f03-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11f03-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="11f03-108">Investigue incidentes que afetam sua rede, entenda o que significam e cole evidências para resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="11f03-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="11f03-109">Ao investigar um incidente, você verá:</span><span class="sxs-lookup"><span data-stu-id="11f03-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="11f03-110">Detalhes do incidente</span><span class="sxs-lookup"><span data-stu-id="11f03-110">Incident details</span></span>
- <span data-ttu-id="11f03-111">Comentários e ações de incidentes</span><span class="sxs-lookup"><span data-stu-id="11f03-111">Incident comments and actions</span></span>
- <span data-ttu-id="11f03-112">Guias (alertas, dispositivos, investigações, evidências, gráfico)</span><span class="sxs-lookup"><span data-stu-id="11f03-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="11f03-113">Analisar detalhes de incidentes</span><span class="sxs-lookup"><span data-stu-id="11f03-113">Analyze incident details</span></span> 
<span data-ttu-id="11f03-114">Clique em um incidente para ver o **painel Incidente.**</span><span class="sxs-lookup"><span data-stu-id="11f03-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="11f03-115">Selecione **Abrir página de incidentes** para ver os detalhes do incidente e informações relacionadas (alertas, dispositivos, investigações, evidências, gráfico).</span><span class="sxs-lookup"><span data-stu-id="11f03-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![Imagem dos detalhes do incidente1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="11f03-117">Alertas</span><span class="sxs-lookup"><span data-stu-id="11f03-117">Alerts</span></span>
<span data-ttu-id="11f03-118">Você pode investigar os alertas e ver como eles foram vinculados em um incidente.</span><span class="sxs-lookup"><span data-stu-id="11f03-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="11f03-119">Os alertas são agrupados em incidentes com base nos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="11f03-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="11f03-120">Investigação automatizada - A investigação automatizada disparou o alerta vinculado ao investigar o alerta original</span><span class="sxs-lookup"><span data-stu-id="11f03-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="11f03-121">Características do arquivo - Os arquivos associados ao alerta têm características semelhantes</span><span class="sxs-lookup"><span data-stu-id="11f03-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="11f03-122">Associação manual - Um usuário vinculado manualmente aos alertas</span><span class="sxs-lookup"><span data-stu-id="11f03-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="11f03-123">Hora próxima - Os alertas foram disparados no mesmo dispositivo em um determinado período de tempo</span><span class="sxs-lookup"><span data-stu-id="11f03-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="11f03-124">Mesmo arquivo - Os arquivos associados ao alerta são exatamente os mesmos</span><span class="sxs-lookup"><span data-stu-id="11f03-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="11f03-125">Mesma URL - A URL que disparou o alerta é exatamente a mesma</span><span class="sxs-lookup"><span data-stu-id="11f03-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![Imagem da guia alertas com a página detalhes do incidente mostrando os motivos pelos quais os alertas foram vinculados juntos nesse incidente](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="11f03-127">Você também pode gerenciar um alerta e ver metadados de alerta junto com outras informações.</span><span class="sxs-lookup"><span data-stu-id="11f03-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="11f03-128">Para obter mais informações, consulte [Investigar alertas](investigate-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="11f03-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="11f03-129">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="11f03-129">Devices</span></span>
<span data-ttu-id="11f03-130">Você também pode investigar os dispositivos que fazem parte, ou relacionados a um determinado incidente.</span><span class="sxs-lookup"><span data-stu-id="11f03-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="11f03-131">Para obter mais informações, consulte [Investigar dispositivos](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="11f03-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![Guia Imagem dos dispositivos na página detalhes do incidente](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="11f03-133">Investigações</span><span class="sxs-lookup"><span data-stu-id="11f03-133">Investigations</span></span>
<span data-ttu-id="11f03-134">Selecione **Investigações** para ver todas as investigações automáticas lançadas pelo sistema em resposta aos alertas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="11f03-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![Guia Imagem de investigações na página detalhes do incidente](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="11f03-136">Passando pelas evidências</span><span class="sxs-lookup"><span data-stu-id="11f03-136">Going through the evidence</span></span>
<span data-ttu-id="11f03-137">O Microsoft Defender para Ponto de Extremidade investiga automaticamente todos os eventos com suporte dos incidentes e entidades suspeitas nos alertas, fornecendo a você autoresponse e informações sobre os arquivos importantes, processos, serviços e muito mais.</span><span class="sxs-lookup"><span data-stu-id="11f03-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="11f03-138">Cada uma das entidades analisadas será marcada como infectado, remediado ou suspeito.</span><span class="sxs-lookup"><span data-stu-id="11f03-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![Guia Imagem da evidência na página detalhes do incidente](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="11f03-140">Visualizando ameaças de segurança cibernética associadas</span><span class="sxs-lookup"><span data-stu-id="11f03-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="11f03-141">O Microsoft Defender for Endpoint agrega as informações de ameaça em um incidente para que você possa ver os padrões e as correlações provenientes de vários pontos de dados.</span><span class="sxs-lookup"><span data-stu-id="11f03-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="11f03-142">Você pode exibir essa correlação por meio do gráfico de incidentes.</span><span class="sxs-lookup"><span data-stu-id="11f03-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="11f03-143">Gráfico de incidentes</span><span class="sxs-lookup"><span data-stu-id="11f03-143">Incident graph</span></span>
<span data-ttu-id="11f03-144">O **Graph** conta a história do ataque de segurança cibernética.</span><span class="sxs-lookup"><span data-stu-id="11f03-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="11f03-145">Por exemplo, ele mostra qual foi o ponto de entrada, qual indicador de comprometimento ou atividade foi observado em qual dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11f03-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="11f03-146">etc.</span><span class="sxs-lookup"><span data-stu-id="11f03-146">etc.</span></span>

![Imagem do gráfico de incidentes](images/atp-incident-graph-tab.png)

<span data-ttu-id="11f03-148">Você pode clicar nos círculos no gráfico de incidentes para exibir os detalhes dos arquivos mal-intencionados, detecções de arquivo associados, quantas instâncias houveram em todo o mundo, se ela foi observada em sua organização, em caso afirmado, quantas instâncias.</span><span class="sxs-lookup"><span data-stu-id="11f03-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![Imagem dos detalhes do incidente](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="11f03-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="11f03-150">Related topics</span></span>
- [<span data-ttu-id="11f03-151">Fila de incidentes</span><span class="sxs-lookup"><span data-stu-id="11f03-151">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="11f03-152">Investigar incidentes no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="11f03-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="11f03-153">Gerenciar o Microsoft Defender para incidentes de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="11f03-153">Manage Microsoft Defender for Endpoint incidents</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
