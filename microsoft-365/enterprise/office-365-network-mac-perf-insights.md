---
title: Microsoft 365 Network Insights (visualização)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (visualização)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055468"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="d94e6-103">Microsoft 365 Network Insights (visualização)</span><span class="sxs-lookup"><span data-stu-id="d94e6-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="d94e6-104">**As informações de** rede são métricas de desempenho coletadas do locatário do Microsoft 365 e estão disponíveis somente para exibição por usuários administrativos em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="d94e6-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="d94e6-105">Insights são exibidos no Centro de administração do Microsoft 365 em <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="d94e6-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="d94e6-106">As informações se destinam a ajudar a projetar perímetros de rede para seus locais de escritório.</span><span class="sxs-lookup"><span data-stu-id="d94e6-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="d94e6-107">Cada insight fornece detalhes ao vivo sobre as características de desempenho de um problema comum específico para cada local geográfico onde os usuários estão acessando seu locatário.</span><span class="sxs-lookup"><span data-stu-id="d94e6-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="d94e6-108">Há seis informações de rede específicas que podem ser mostradas para cada local do escritório:</span><span class="sxs-lookup"><span data-stu-id="d94e6-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="d94e6-109">Saída de rede em backhaul</span><span class="sxs-lookup"><span data-stu-id="d94e6-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="d94e6-110">Dispositivo intermediário de rede</span><span class="sxs-lookup"><span data-stu-id="d94e6-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="d94e6-111">Melhor desempenho detectado para clientes próximos a você</span><span class="sxs-lookup"><span data-stu-id="d94e6-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="d94e6-112">Uso de uma porta frontal de serviço do Exchange Online não ideal</span><span class="sxs-lookup"><span data-stu-id="d94e6-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="d94e6-113">Uso de uma porta frontal de serviço do SharePoint Online não ideal</span><span class="sxs-lookup"><span data-stu-id="d94e6-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="d94e6-114">Baixa velocidade de download da porta frontal do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d94e6-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="d94e6-115">Saída de rede ideal do usuário da China</span><span class="sxs-lookup"><span data-stu-id="d94e6-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="d94e6-116">Há duas percepções de rede no nível do locatário que podem ser mostradas para o locatário.</span><span class="sxs-lookup"><span data-stu-id="d94e6-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="d94e6-117">Eles também aparecem nas páginas de pontuação producvitivy:</span><span class="sxs-lookup"><span data-stu-id="d94e6-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="d94e6-118">Conexões amostradas do Exchange impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="d94e6-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="d94e6-119">Conexões amostradas do SharePoint impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="d94e6-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="d94e6-120">Insights de rede, recomendações de desempenho e avaliações no Centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para locatários do Microsoft 365 que foram inscritos no programa de visualização de recursos.</span><span class="sxs-lookup"><span data-stu-id="d94e6-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="d94e6-121">Saída de rede em backhaul</span><span class="sxs-lookup"><span data-stu-id="d94e6-121">Backhauled network egress</span></span>

<span data-ttu-id="d94e6-122">Esse insight será exibido se o serviço de informações de rede detectar que a distância de um determinado local do usuário até a saída da rede é maior que 500 km (800 km) de distância, indicando que o tráfego do Microsoft 365 está sendo reformulado para um proxy ou dispositivo de borda da Internet comum.</span><span class="sxs-lookup"><span data-stu-id="d94e6-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="d94e6-123">Esse insight é abreviado como "Saída" em algumas exibições resumidas.</span><span class="sxs-lookup"><span data-stu-id="d94e6-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Saída de rede em backhaul](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="d94e6-125">Cenário</span><span class="sxs-lookup"><span data-stu-id="d94e6-125">What does this mean?</span></span>

<span data-ttu-id="d94e6-126">Isso identifica que a distância entre o local do escritório e a saída da rede é de mais de 500 milhas (800 km).</span><span class="sxs-lookup"><span data-stu-id="d94e6-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="d94e6-127">O local do escritório é identificado por um local de máquina cliente ofuscado e o local de saída de rede é identificado usando o Endereço IP reverso para os bancos de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="d94e6-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="d94e6-128">O local do escritório pode ser impreciso se os Serviços de Localização do Windows estão desabilitados nos computadores.</span><span class="sxs-lookup"><span data-stu-id="d94e6-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="d94e6-129">O local de saída de rede pode ser impreciso se as informações do banco de dados de endereço IP reverso não são imprecisas.</span><span class="sxs-lookup"><span data-stu-id="d94e6-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="d94e6-130">Os detalhes desse insight incluem o local do escritório, a porcentagem estimada do total de usuários do locatário no local, o local de saída da rede atual, a relevância do local de saída, a distância entre o local e o ponto de saída atual, a data em que a condição foi detectada pela primeira vez e a data em que a condição foi resolvida.</span><span class="sxs-lookup"><span data-stu-id="d94e6-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="d94e6-131">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="d94e6-131">What should I do?</span></span>

<span data-ttu-id="d94e6-132">Para esse insight, recomendamos que a rede se aproxima do local do escritório para que a conectividade possa ser a melhor rota para a rede global da Microsoft e para a porta de entrada de serviço do Microsoft 365 mais próxima.</span><span class="sxs-lookup"><span data-stu-id="d94e6-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="d94e6-133">Ter uma saída de rede próxima aos locais de escritório dos usuários também permite melhorar o desempenho no futuro, à medida que a Microsoft expande os pontos de presença da rede e as portas frontales do serviço do Microsoft 365 no futuro.</span><span class="sxs-lookup"><span data-stu-id="d94e6-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="d94e6-134">Para saber mais sobre como resolver esse problema, confira [conexões](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) de rede de Saída localmente nos Princípios de Conectividade de Rede do [Office 365.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="d94e6-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="d94e6-135">Dispositivo intermediário de rede</span><span class="sxs-lookup"><span data-stu-id="d94e6-135">Network intermediary device</span></span>

<span data-ttu-id="d94e6-136">Essa informação será exibida se detectarmos dispositivos entre seus usuários e a rede da Microsoft, o que pode afetar a experiência do usuário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d94e6-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="d94e6-137">É recomendável que eles sejam ignorados para o tráfego de rede específico do Microsoft 365 destinado a datacenters da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d94e6-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="d94e6-138">Essa recomendação também é descrita nos Princípios de Conectividade de Rede do [Microsoft 365](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="d94e6-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="d94e6-139">Cenário</span><span class="sxs-lookup"><span data-stu-id="d94e6-139">What does this mean?</span></span>

<span data-ttu-id="d94e6-140">Dispositivos intermediários de rede, como servidores proxy, VPNs e dispositivos de prevenção contra perda de dados, podem afetar o desempenho e a estabilidade dos clientes do Microsoft 365 onde o tráfego está intermediário.</span><span class="sxs-lookup"><span data-stu-id="d94e6-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="d94e6-141">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="d94e6-141">What should I do?</span></span>

<span data-ttu-id="d94e6-142">Configure o dispositivo intermediário de rede detectado para ignorar o processamento do tráfego de rede do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d94e6-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="d94e6-143">Melhor desempenho detectado para clientes próximos a você</span><span class="sxs-lookup"><span data-stu-id="d94e6-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="d94e6-144">Esse insight será exibido se o serviço de informações de rede detectar que um número significativo de clientes em sua área de transporte tem melhor desempenho do que os usuários em sua organização neste local do escritório.</span><span class="sxs-lookup"><span data-stu-id="d94e6-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="d94e6-145">Esse insight é abreviado como "Pares" em algumas exibições resumidas.</span><span class="sxs-lookup"><span data-stu-id="d94e6-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Desempenho relativo da rede](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="d94e6-147">Cenário</span><span class="sxs-lookup"><span data-stu-id="d94e6-147">What does this mean?</span></span>

<span data-ttu-id="d94e6-148">Este insight examina o desempenho agregado dos clientes do Microsoft 365 na mesma cidade que esse local de escritório.</span><span class="sxs-lookup"><span data-stu-id="d94e6-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="d94e6-149">Esse insight será exibido se a latência média de seus usuários for 10% maior do que a latência média de locatários vizinhos.</span><span class="sxs-lookup"><span data-stu-id="d94e6-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="d94e6-150">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="d94e6-150">What should I do?</span></span>

<span data-ttu-id="d94e6-151">Pode haver muitos motivos para essa condição, incluindo latência em sua rede corporativa ou ISP, gargalos ou problemas de design da arquitetura.</span><span class="sxs-lookup"><span data-stu-id="d94e6-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="d94e6-152">Examine a latência entre cada salto na rota entre a rede do office e a porta frontal atual do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d94e6-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="d94e6-153">Para saber mais, confira Os Princípios de Conectividade de Rede do [Microsoft 365.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="d94e6-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="d94e6-154">Uso de uma porta frontal de serviço do Exchange Online não ideal</span><span class="sxs-lookup"><span data-stu-id="d94e6-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="d94e6-155">Esse insight será exibido se o serviço de informações de rede detectar que os usuários em um local específico não estão se conectando a uma porta frontal de serviço do Exchange Online ideal.</span><span class="sxs-lookup"><span data-stu-id="d94e6-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="d94e6-156">Esse insight é abreviado como "Roteamento" em algumas exibições resumidas.</span><span class="sxs-lookup"><span data-stu-id="d94e6-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Porta frontal EXO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="d94e6-158">Cenário</span><span class="sxs-lookup"><span data-stu-id="d94e6-158">What does this mean?</span></span>

<span data-ttu-id="d94e6-159">Listamos portas frontales de serviço do Exchange Online que são adequadas para uso na cidade do local do escritório com bom desempenho.</span><span class="sxs-lookup"><span data-stu-id="d94e6-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="d94e6-160">Se o teste atual mostrar o uso de uma porta frontal de serviço do Exchange Online que não está nessa lista, nós destacamos essa recomendação.</span><span class="sxs-lookup"><span data-stu-id="d94e6-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="d94e6-161">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="d94e6-161">What should I do?</span></span>

<span data-ttu-id="d94e6-162">O uso de uma porta frontal de serviço do Exchange Online que não seja ideal pode ser causado por backhaul de rede antes da saída da rede corporativa. Nesse caso, recomendamos a saída de rede local e direta.</span><span class="sxs-lookup"><span data-stu-id="d94e6-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="d94e6-163">Ele também pode ser causado pelo uso de um servidor Resolvedor Recursivo de DNS remoto. Nesse caso, recomendamos alinhar o servidor resolvedor recursivo dns com a saída de rede.</span><span class="sxs-lookup"><span data-stu-id="d94e6-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="d94e6-164">Uso de uma porta frontal de serviço do SharePoint Online não ideal</span><span class="sxs-lookup"><span data-stu-id="d94e6-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="d94e6-165">Esse insight será exibido se o serviço de informações de rede detectar que os usuários em um local específico não estão se conectando à porta de entrada de serviço do SharePoint Online mais próxima.</span><span class="sxs-lookup"><span data-stu-id="d94e6-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="d94e6-166">Esse insight é abreviado como "Afd" em alguns visualizações resumidas.</span><span class="sxs-lookup"><span data-stu-id="d94e6-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Porta frontal do SPO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="d94e6-168">Cenário</span><span class="sxs-lookup"><span data-stu-id="d94e6-168">What does this mean?</span></span>

<span data-ttu-id="d94e6-169">Identificamos a porta de entrada do serviço do SharePoint Online ao qual o cliente de teste está se conectando.</span><span class="sxs-lookup"><span data-stu-id="d94e6-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="d94e6-170">Em seguida, para a cidade do local do escritório, comparamos isso com a porta de frente esperada do serviço do SharePoint Online para essa cidade.</span><span class="sxs-lookup"><span data-stu-id="d94e6-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="d94e6-171">Se ele não corresponder, faremos essa recomendação.</span><span class="sxs-lookup"><span data-stu-id="d94e6-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="d94e6-172">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="d94e6-172">What should I do?</span></span>

<span data-ttu-id="d94e6-173">O uso de uma porta frontal de serviço do SharePoint Online que não seja ideal pode ser causado por backhaul de rede antes da saída da rede corporativa. Nesse caso, recomendamos a saída de rede local e direta.</span><span class="sxs-lookup"><span data-stu-id="d94e6-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="d94e6-174">Ele também pode ser causado pelo uso de um servidor Resolvedor Recursivo de DNS remoto. Nesse caso, recomendamos alinhar o servidor resolvedor recursivo dns com a saída de rede.</span><span class="sxs-lookup"><span data-stu-id="d94e6-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="d94e6-175">Baixa velocidade de download da porta frontal do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d94e6-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="d94e6-176">Essa informação será exibida se o serviço de informações de rede detectar que a largura de banda entre o local específico do escritório e o SharePoint Online é inferior a 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="d94e6-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="d94e6-177">Esse insight é abreviado como "Produtividade" em algumas exibições resumidas.</span><span class="sxs-lookup"><span data-stu-id="d94e6-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="d94e6-178">Cenário</span><span class="sxs-lookup"><span data-stu-id="d94e6-178">What does this mean?</span></span>

<span data-ttu-id="d94e6-179">A velocidade de download que um usuário pode obter do SharePoint Online e das portas de serviço do OneDrive for Business é medida em megabytes por segundo (MBps).</span><span class="sxs-lookup"><span data-stu-id="d94e6-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="d94e6-180">Se esse valor for menor que 1 MBps, forneceremos esse insight.</span><span class="sxs-lookup"><span data-stu-id="d94e6-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="d94e6-181">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="d94e6-181">What should I do?</span></span>

<span data-ttu-id="d94e6-182">Para melhorar as velocidades de download, a largura de banda pode precisar ser aumentada.</span><span class="sxs-lookup"><span data-stu-id="d94e6-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="d94e6-183">Como alternativa, pode haver congestionamento de rede entre os máquinas do usuário no local do escritório e a porta frontal do serviço do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d94e6-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="d94e6-184">Isso algumas vezes é chamado de perda congestionada e restringe a velocidade de download disponível para os usuários, mesmo se a largura de banda suficiente estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="d94e6-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="d94e6-185">Saída de rede ideal do usuário da China</span><span class="sxs-lookup"><span data-stu-id="d94e6-185">China user optimal network egress</span></span>

<span data-ttu-id="d94e6-186">Essa informação será exibida se sua organização tiver usuários na China se conectando ao locatário do Microsoft 365 em outras localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="d94e6-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="d94e6-187">Cenário</span><span class="sxs-lookup"><span data-stu-id="d94e6-187">What does this mean?</span></span>

<span data-ttu-id="d94e6-188">Se sua organização tiver conectividade WAN privada, recomendamos configurar um circuito WAN de rede de seus locais de escritório na China que tenha saída de rede para a Internet em qualquer um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="d94e6-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="d94e6-189">Hong-Kong</span><span class="sxs-lookup"><span data-stu-id="d94e6-189">Hong Kong</span></span>
- <span data-ttu-id="d94e6-190">Japão</span><span class="sxs-lookup"><span data-stu-id="d94e6-190">Japan</span></span>
- <span data-ttu-id="d94e6-191">Taiwan</span><span class="sxs-lookup"><span data-stu-id="d94e6-191">Taiwan</span></span>
- <span data-ttu-id="d94e6-192">Coreia do Sul</span><span class="sxs-lookup"><span data-stu-id="d94e6-192">South Korea</span></span>
- <span data-ttu-id="d94e6-193">Cingapura</span><span class="sxs-lookup"><span data-stu-id="d94e6-193">Singapore</span></span>
- <span data-ttu-id="d94e6-194">Malásia</span><span class="sxs-lookup"><span data-stu-id="d94e6-194">Malaysia</span></span>

<span data-ttu-id="d94e6-195">A saída da Internet mais longe dos usuários do que esses locais reduzirá o desempenho, e a saída na China pode causar problemas de alta latência e conectividade devido ao congestionamento entre fronteiras.</span><span class="sxs-lookup"><span data-stu-id="d94e6-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="d94e6-196">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="d94e6-196">What should I do?</span></span>

<span data-ttu-id="d94e6-197">Para obter mais informações sobre como mitigar problemas de desempenho relacionados a esse insight, confira a otimização de desempenho de locatário global do [Microsoft 365](microsoft-365-networking-china.md)para usuários da China.</span><span class="sxs-lookup"><span data-stu-id="d94e6-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="d94e6-198">Conexões amostradas do Exchange impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="d94e6-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="d94e6-199">Esse insight mostrará quando 50% ou mais das conexões amostradas são impactadas.</span><span class="sxs-lookup"><span data-stu-id="d94e6-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="d94e6-200">O impacto é definido pela avaliação do Exchange ser inferior a 60% para cada amostra.</span><span class="sxs-lookup"><span data-stu-id="d94e6-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="d94e6-201">Cenário</span><span class="sxs-lookup"><span data-stu-id="d94e6-201">What does this mean?</span></span>

<span data-ttu-id="d94e6-202">É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com a conexão do Outlook com o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d94e6-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="d94e6-203">A porcentagem de amostras provavelmente representa a porcentagem de usuários que aparecem abaixo de 60 pontos.</span><span class="sxs-lookup"><span data-stu-id="d94e6-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="d94e6-204">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="d94e6-204">What should I do?</span></span>

<span data-ttu-id="d94e6-205">Habilita a visibilidade da conectividade de rede de localização do escritório se você ainda não tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="d94e6-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="d94e6-206">Você deseja identificar quais escritórios são afetados pela conectividade de rede ruim que está afetando o Exchange e encontrar maneiras de melhorar o perímetro de rede em cada um que conecte os usuários à rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d94e6-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="d94e6-207">Conexões amostradas do SharePoint impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="d94e6-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="d94e6-208">Esse insight mostrará quando 50% ou mais das conexões amostradas são impactadas.</span><span class="sxs-lookup"><span data-stu-id="d94e6-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="d94e6-209">O impacto é definido pela avaliação do SharePoint ser inferior a 40% para cada amostra.</span><span class="sxs-lookup"><span data-stu-id="d94e6-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="d94e6-210">Cenário</span><span class="sxs-lookup"><span data-stu-id="d94e6-210">What does this mean?</span></span>

<span data-ttu-id="d94e6-211">É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com o SharePoint e o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d94e6-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="d94e6-212">A porcentagem de amostras provavelmente representa a porcentagem de usuários que aparecem abaixo de 40 pontos.</span><span class="sxs-lookup"><span data-stu-id="d94e6-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="d94e6-213">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="d94e6-213">What should I do?</span></span>

<span data-ttu-id="d94e6-214">Habilita a visibilidade da conectividade de rede de localização do escritório se você ainda não tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="d94e6-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="d94e6-215">Você deseja identificar quais escritórios são afetados pela conectividade de rede ruim que está afetando o SharePoint e encontrar maneiras de melhorar o perímetro de rede em cada um que conecte os usuários à rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d94e6-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d94e6-216">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d94e6-216">Related topics</span></span>

[<span data-ttu-id="d94e6-217">Conectividade de rede no Centro de administração do Microsoft 365 (visualização)</span><span class="sxs-lookup"><span data-stu-id="d94e6-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="d94e6-218">Avaliação de rede do Microsoft 365 (visualização)</span><span class="sxs-lookup"><span data-stu-id="d94e6-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="d94e6-219">Ferramenta de teste de conectividade de rede do Microsoft 365 (visualização)</span><span class="sxs-lookup"><span data-stu-id="d94e6-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="d94e6-220">Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)</span><span class="sxs-lookup"><span data-stu-id="d94e6-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
