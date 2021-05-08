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
ms.openlocfilehash: ca665f4e492b071e5a387ffde0efae8336bd96bc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245775"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="dce07-103">Microsoft 365 Network Insights (visualização)</span><span class="sxs-lookup"><span data-stu-id="dce07-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="dce07-104">**As percepções de** rede são métricas de desempenho coletadas do seu locatário Microsoft 365 e disponíveis para exibição somente por usuários administrativos em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="dce07-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="dce07-105">Insights são exibidos no Centro de administração Microsoft 365 em <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="dce07-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="dce07-106">Os insights destinam-se a ajudar a projetar perímetros de rede para seus locais de escritório.</span><span class="sxs-lookup"><span data-stu-id="dce07-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="dce07-107">Cada insight fornece detalhes ao vivo sobre as características de desempenho para um problema comum específico para cada local geográfico em que os usuários estão acessando seu locatário.</span><span class="sxs-lookup"><span data-stu-id="dce07-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="dce07-108">Há seis percepções de rede específicas que podem ser mostradas para cada local do escritório:</span><span class="sxs-lookup"><span data-stu-id="dce07-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="dce07-109">Saída de rede com backhauled</span><span class="sxs-lookup"><span data-stu-id="dce07-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="dce07-110">Dispositivo intermediário de rede</span><span class="sxs-lookup"><span data-stu-id="dce07-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="dce07-111">Melhor desempenho detectado para clientes próximos a você</span><span class="sxs-lookup"><span data-stu-id="dce07-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="dce07-112">Uso de uma porta de Exchange Online de serviço não ideal</span><span class="sxs-lookup"><span data-stu-id="dce07-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="dce07-113">Uso de uma porta de entrada de serviço SharePoint Online não ideal</span><span class="sxs-lookup"><span data-stu-id="dce07-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="dce07-114">Baixa velocidade de download SharePoint porta da frente</span><span class="sxs-lookup"><span data-stu-id="dce07-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="dce07-115">Saída de rede ideal do usuário da China</span><span class="sxs-lookup"><span data-stu-id="dce07-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="dce07-116">Há duas percepções de rede de nível de locatário que podem ser mostradas para o locatário.</span><span class="sxs-lookup"><span data-stu-id="dce07-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="dce07-117">Elas também aparecem nas páginas de pontuação de produtividade:</span><span class="sxs-lookup"><span data-stu-id="dce07-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="dce07-118">Exchange conexões amostradas impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="dce07-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="dce07-119">SharePoint conexões amostradas impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="dce07-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="dce07-120">Percepções de rede, recomendações de desempenho e avaliações no Centro de Administração do Microsoft 365 está atualmente em status de visualização e está disponível apenas para locatários de Microsoft 365 que foram inscritos no programa de visualização de recursos.</span><span class="sxs-lookup"><span data-stu-id="dce07-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="dce07-121">Saída de rede com backhauled</span><span class="sxs-lookup"><span data-stu-id="dce07-121">Backhauled network egress</span></span>

<span data-ttu-id="dce07-122">Esse insight será exibido se o serviço de insights de rede detectar que a distância de um determinado local do usuário para a saída da rede é maior do que 800 milhas (800 km), indicando que o tráfego Microsoft 365 está sendo reagredido para um dispositivo ou proxy de borda da Internet comum.</span><span class="sxs-lookup"><span data-stu-id="dce07-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="dce07-123">Esse insight é abreviado como "Egress" em alguns exibições de resumo.</span><span class="sxs-lookup"><span data-stu-id="dce07-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dce07-124">![Saída de rede com backhauled](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="dce07-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="dce07-125">O que isso significa?</span><span class="sxs-lookup"><span data-stu-id="dce07-125">What does this mean?</span></span>

<span data-ttu-id="dce07-126">Isso identifica que a distância entre o local do escritório e a saída de rede é de mais de 800 km (800 km).</span><span class="sxs-lookup"><span data-stu-id="dce07-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="dce07-127">O local do escritório é identificado por um local do computador cliente ofuscado e o local de saída de rede é identificado usando o Endereço IP reverso para bancos de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="dce07-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="dce07-128">O local do escritório pode ser impreciso se Windows Serviços de Localização estiver desabilitado em máquinas.</span><span class="sxs-lookup"><span data-stu-id="dce07-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="dce07-129">O local de saída de rede pode ser impreciso se as informações do banco de dados de endereço IP reverso não são imprecisas.</span><span class="sxs-lookup"><span data-stu-id="dce07-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="dce07-130">Os detalhes desse insight incluem o local do escritório, a porcentagem estimada do total de usuários do locatário no local, o local de saída de rede atual, a relevância do local de saída, a distância entre o local e o ponto de saída atual, a data em que a condição foi detectada pela primeira vez e a data em que a condição foi resolvida.</span><span class="sxs-lookup"><span data-stu-id="dce07-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="dce07-131">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="dce07-131">What should I do?</span></span>

<span data-ttu-id="dce07-132">Para esse insight, recomendamos a saída de rede mais perto do local do office para que a conectividade possa roteá-lo de forma ideal para a rede global da Microsoft e para a porta de entrada de serviço de Microsoft 365 mais próxima.</span><span class="sxs-lookup"><span data-stu-id="dce07-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="dce07-133">Ter uma saída de rede próxima aos locais de escritório dos usuários também permite melhorar o desempenho no futuro, à medida que a Microsoft expande os pontos de presença da rede e Microsoft 365 portas de frente do serviço no futuro.</span><span class="sxs-lookup"><span data-stu-id="dce07-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="dce07-134">Para obter mais informações sobre como resolver esse problema, consulte [Egress conexões](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) de rede localmente Office 365 Princípios de Conectividade [de Rede.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="dce07-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="dce07-135">Dispositivo intermediário de rede</span><span class="sxs-lookup"><span data-stu-id="dce07-135">Network intermediary device</span></span>

<span data-ttu-id="dce07-136">Esse insight será exibido se detectarmos dispositivos entre seus usuários e a rede da Microsoft, o que pode afetar a experiência Office 365 usuário.</span><span class="sxs-lookup"><span data-stu-id="dce07-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="dce07-137">É recomendável que eles sejam ignorados para tráfego de rede Microsoft 365 específico destinado a datacenters da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dce07-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="dce07-138">Esta recomendação é descrita adicionalmente em [Microsoft 365 Princípios de Conectividade de Rede.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="dce07-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="dce07-139">Um insight intermediário de rede que mostramos é a quebra e a inspeção de SS Office 365 L quando pontos de extremidade de rede críticos para Exchange, SharePoint e Teams são interceptados e descriptografados por dispositivos intermediários de rede.</span><span class="sxs-lookup"><span data-stu-id="dce07-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="dce07-140">O que isso significa?</span><span class="sxs-lookup"><span data-stu-id="dce07-140">What does this mean?</span></span>

<span data-ttu-id="dce07-141">Dispositivos intermediários de rede, como servidores proxy, VPNs e dispositivos de prevenção contra perda de dados, podem afetar o desempenho e a estabilidade Microsoft 365 clientes em que o tráfego é intermediário.</span><span class="sxs-lookup"><span data-stu-id="dce07-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="dce07-142">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="dce07-142">What should I do?</span></span>

<span data-ttu-id="dce07-143">Configure o dispositivo intermediário de rede detectado para ignorar o processamento para Microsoft 365 de rede.</span><span class="sxs-lookup"><span data-stu-id="dce07-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="dce07-144">Melhor desempenho detectado para clientes próximos a você</span><span class="sxs-lookup"><span data-stu-id="dce07-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="dce07-145">Esse insight será exibido se o serviço de insights de rede detectar que um número significativo de clientes em sua área de metro tem melhor desempenho do que os usuários em sua organização neste local do escritório.</span><span class="sxs-lookup"><span data-stu-id="dce07-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="dce07-146">Esse insight é abreviado como "Pares" em alguns pontos de exibição de resumo.</span><span class="sxs-lookup"><span data-stu-id="dce07-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dce07-147">![Desempenho relativo da rede](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="dce07-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="dce07-148">O que isso significa?</span><span class="sxs-lookup"><span data-stu-id="dce07-148">What does this mean?</span></span>

<span data-ttu-id="dce07-149">Essa visão examina o desempenho agregado dos clientes Microsoft 365 na mesma cidade que esse local do escritório.</span><span class="sxs-lookup"><span data-stu-id="dce07-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="dce07-150">Esse insight será exibido se a latência média de seus usuários for 10% maior do que a latência média de locatários vizinhos.</span><span class="sxs-lookup"><span data-stu-id="dce07-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="dce07-151">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="dce07-151">What should I do?</span></span>

<span data-ttu-id="dce07-152">Pode haver muitos motivos para essa condição, incluindo latência em sua rede corporativa ou ISP, gargalos ou problemas de design de arquitetura.</span><span class="sxs-lookup"><span data-stu-id="dce07-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="dce07-153">Examine a latência entre cada salto na rota entre sua rede do office e a porta Microsoft 365 atual.</span><span class="sxs-lookup"><span data-stu-id="dce07-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="dce07-154">Para obter mais informações, [consulte Microsoft 365 Princípios de Conectividade de Rede](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="dce07-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="dce07-155">Uso de uma porta de Exchange Online de serviço não ideal</span><span class="sxs-lookup"><span data-stu-id="dce07-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="dce07-156">Esse insight será exibido se o serviço de insights de rede detectar que os usuários em um local específico não estão se conectando a uma porta de Exchange Online de serviço ideal.</span><span class="sxs-lookup"><span data-stu-id="dce07-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="dce07-157">Esse insight é abreviado como "Roteamento" em alguns exibições de resumo.</span><span class="sxs-lookup"><span data-stu-id="dce07-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dce07-158">![Porta frontal EXO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="dce07-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="dce07-159">O que isso significa?</span><span class="sxs-lookup"><span data-stu-id="dce07-159">What does this mean?</span></span>

<span data-ttu-id="dce07-160">Listamos Exchange Online de serviço que são adequadas para uso na cidade de local do escritório com bom desempenho.</span><span class="sxs-lookup"><span data-stu-id="dce07-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="dce07-161">Se o teste atual mostrar o uso de uma porta de Exchange Online de serviço não nesta lista, então chamaremos essa recomendação.</span><span class="sxs-lookup"><span data-stu-id="dce07-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="dce07-162">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="dce07-162">What should I do?</span></span>

<span data-ttu-id="dce07-163">O uso de uma porta de entrada de serviço não ideal Exchange Online pode ser causado por backhaul de rede antes da saída da rede corporativa, nesse caso, recomendamos saída de rede local e direta.</span><span class="sxs-lookup"><span data-stu-id="dce07-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="dce07-164">Ele também pode ser causado pelo uso de um servidor de Resolver Recursivo DNS remoto, nesse caso, recomendamos alinhar o servidor resolvedor recursivo DNS com a saída de rede.</span><span class="sxs-lookup"><span data-stu-id="dce07-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="dce07-165">Uso de uma porta de entrada de serviço SharePoint Online não ideal</span><span class="sxs-lookup"><span data-stu-id="dce07-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="dce07-166">Esse insight será exibido se o serviço de insights de rede detectar que os usuários em um local específico não estão se conectando à porta de entrada de serviço mais próxima SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dce07-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="dce07-167">Esse insight é abreviado como "Afd" em alguns pontos de exibição de resumo.</span><span class="sxs-lookup"><span data-stu-id="dce07-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dce07-168">![Porta da frente do SPO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="dce07-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="dce07-169">O que isso significa?</span><span class="sxs-lookup"><span data-stu-id="dce07-169">What does this mean?</span></span>

<span data-ttu-id="dce07-170">Identificamos a porta SharePoint de serviço Online à qual o cliente de teste está se conectando.</span><span class="sxs-lookup"><span data-stu-id="dce07-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="dce07-171">Em seguida, para a cidade de localização do escritório, comparamos isso com a porta de SharePoint de serviço online esperada para essa cidade.</span><span class="sxs-lookup"><span data-stu-id="dce07-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="dce07-172">Se ele não corresponder, faremos essa recomendação.</span><span class="sxs-lookup"><span data-stu-id="dce07-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="dce07-173">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="dce07-173">What should I do?</span></span>

<span data-ttu-id="dce07-174">O SharePoint uso de uma porta de entrada de serviço online não ideal pode ser causado por backhaul de rede antes da saída da rede corporativa, nesse caso, recomendamos saída de rede local e direta.</span><span class="sxs-lookup"><span data-stu-id="dce07-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="dce07-175">Ele também pode ser causado pelo uso de um servidor de Resolver Recursivo DNS remoto, nesse caso, recomendamos alinhar o servidor resolvedor recursivo DNS com a saída de rede.</span><span class="sxs-lookup"><span data-stu-id="dce07-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="dce07-176">Baixa velocidade de download SharePoint porta da frente</span><span class="sxs-lookup"><span data-stu-id="dce07-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="dce07-177">Esse insight será exibido se o serviço de insights de rede detectar que a largura de banda entre o local do escritório específico e o SharePoint Online é inferior a 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="dce07-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="dce07-178">Esse insight é abreviado como "Produtividade" em alguns pontos de exibição de resumo.</span><span class="sxs-lookup"><span data-stu-id="dce07-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="dce07-179">O que isso significa?</span><span class="sxs-lookup"><span data-stu-id="dce07-179">What does this mean?</span></span>

<span data-ttu-id="dce07-180">A velocidade de download que um usuário pode obter do SharePoint Online e OneDrive for Business de serviço é medida em megabytes por segundo (MBps).</span><span class="sxs-lookup"><span data-stu-id="dce07-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="dce07-181">Se esse valor for menor que 1 MBps, forneceremos esse insight.</span><span class="sxs-lookup"><span data-stu-id="dce07-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="dce07-182">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="dce07-182">What should I do?</span></span>

<span data-ttu-id="dce07-183">Para melhorar as velocidades de download, a largura de banda pode precisar ser aumentada.</span><span class="sxs-lookup"><span data-stu-id="dce07-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="dce07-184">Como alternativa, pode haver congestionamento de rede entre máquinas de usuário no local do escritório e a porta de entrada do serviço SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dce07-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="dce07-185">Isso às vezes é chamado de perda congestiva e restringe a velocidade de download disponível para os usuários, mesmo se a largura de banda suficiente estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="dce07-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="dce07-186">Saída de rede ideal do usuário da China</span><span class="sxs-lookup"><span data-stu-id="dce07-186">China user optimal network egress</span></span>

<span data-ttu-id="dce07-187">Essa visão será exibida se sua organização tiver usuários na China se conectando ao seu locatário Microsoft 365 locatário em outras localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="dce07-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="dce07-188">O que isso significa?</span><span class="sxs-lookup"><span data-stu-id="dce07-188">What does this mean?</span></span>

<span data-ttu-id="dce07-189">Se sua organização tiver conectividade WAN privada, recomendamos configurar um circuito WAN de rede de seus locais de escritório na China que tenha saída de rede para a Internet em qualquer um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="dce07-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="dce07-190">Hong-Kong</span><span class="sxs-lookup"><span data-stu-id="dce07-190">Hong Kong</span></span>
- <span data-ttu-id="dce07-191">Japão</span><span class="sxs-lookup"><span data-stu-id="dce07-191">Japan</span></span>
- <span data-ttu-id="dce07-192">Taiwan</span><span class="sxs-lookup"><span data-stu-id="dce07-192">Taiwan</span></span>
- <span data-ttu-id="dce07-193">Coreia do Sul</span><span class="sxs-lookup"><span data-stu-id="dce07-193">South Korea</span></span>
- <span data-ttu-id="dce07-194">Cingapura</span><span class="sxs-lookup"><span data-stu-id="dce07-194">Singapore</span></span>
- <span data-ttu-id="dce07-195">Malásia</span><span class="sxs-lookup"><span data-stu-id="dce07-195">Malaysia</span></span>

<span data-ttu-id="dce07-196">A Saída da Internet mais longe dos usuários do que esses locais reduzirá o desempenho, e a saída na China pode causar problemas de alta latência e conectividade devido ao congestionamento entre fronteiras.</span><span class="sxs-lookup"><span data-stu-id="dce07-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="dce07-197">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="dce07-197">What should I do?</span></span>

<span data-ttu-id="dce07-198">Para obter mais informações sobre como mitigar problemas de desempenho relacionados a esse insight, consulte Microsoft 365 otimização de desempenho do locatário [global para usuários da China.](microsoft-365-networking-china.md)</span><span class="sxs-lookup"><span data-stu-id="dce07-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="dce07-199">Exchange conexões amostradas impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="dce07-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="dce07-200">Esse insight mostrará quando 50% ou mais das conexões amostradas são impactadas.</span><span class="sxs-lookup"><span data-stu-id="dce07-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="dce07-201">O impacto é definido pela avaliação Exchange inferior a 60% para cada amostra.</span><span class="sxs-lookup"><span data-stu-id="dce07-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="dce07-202">O que isso significa?</span><span class="sxs-lookup"><span data-stu-id="dce07-202">What does this mean?</span></span>

<span data-ttu-id="dce07-203">É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com Outlook se conectar ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dce07-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="dce07-204">A porcentagem de amostras provavelmente representa a porcentagem de usuários que mostram abaixo de 60 pontos.</span><span class="sxs-lookup"><span data-stu-id="dce07-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="dce07-205">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="dce07-205">What should I do?</span></span>

<span data-ttu-id="dce07-206">Habilita a visibilidade de conectividade de rede de localização do escritório se você ainda não tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="dce07-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="dce07-207">Você deseja identificar quais escritórios são afetados pela conectividade de rede ruim que está afetando Exchange e encontrar maneiras de melhorar o perímetro de rede em cada um que conecta os usuários à rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dce07-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="dce07-208">SharePoint conexões amostradas impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="dce07-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="dce07-209">Esse insight mostrará quando 50% ou mais das conexões amostradas são impactadas.</span><span class="sxs-lookup"><span data-stu-id="dce07-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="dce07-210">O impacto é definido pela avaliação SharePoint inferior a 40% para cada amostra.</span><span class="sxs-lookup"><span data-stu-id="dce07-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="dce07-211">O que isso significa?</span><span class="sxs-lookup"><span data-stu-id="dce07-211">What does this mean?</span></span>

<span data-ttu-id="dce07-212">É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="dce07-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="dce07-213">A porcentagem de amostras provavelmente representa a porcentagem de usuários que mostram abaixo de 40 pontos.</span><span class="sxs-lookup"><span data-stu-id="dce07-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="dce07-214">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="dce07-214">What should I do?</span></span>

<span data-ttu-id="dce07-215">Habilita a visibilidade de conectividade de rede de localização do escritório se você ainda não tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="dce07-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="dce07-216">Você deseja identificar quais escritórios são afetados pela conectividade de rede ruim que está afetando SharePoint e encontrar maneiras de melhorar o perímetro de rede em cada um que conecta os usuários à rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dce07-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dce07-217">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="dce07-217">Related topics</span></span>

[<span data-ttu-id="dce07-218">Conectividade de rede no Microsoft 365 Admin Center (visualização)</span><span class="sxs-lookup"><span data-stu-id="dce07-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="dce07-219">Microsoft 365 de rede (visualização)</span><span class="sxs-lookup"><span data-stu-id="dce07-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="dce07-220">Microsoft 365 de teste de conectividade de rede (visualização)</span><span class="sxs-lookup"><span data-stu-id="dce07-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="dce07-221">Microsoft 365 Serviços de Localização de Conectividade de Rede (visualização)</span><span class="sxs-lookup"><span data-stu-id="dce07-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
