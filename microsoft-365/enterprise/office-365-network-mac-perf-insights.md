---
title: Microsoft 365 Network insights (versão prévia)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network insights (versão prévia)
ms.openlocfilehash: 682c888fefb9bec9725e470d62019c857fc2de07
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171333"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="526db-103">Microsoft 365 Network insights (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="526db-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="526db-104">As **informações de rede** são métricas de desempenho coletadas do seu locatário do Microsoft 365 e disponíveis para visualização apenas por usuários administrativos em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="526db-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="526db-105">As ideias são exibidas no centro de administração do Microsoft 365 em <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="526db-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="526db-106">As ideias destinam-se a ajudar na criação de perímetros de rede para seus locais do Office.</span><span class="sxs-lookup"><span data-stu-id="526db-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="526db-107">Cada informação fornece detalhes ao vivo sobre as características de desempenho para um problema comum específico para cada localização geográfica onde os usuários acessam seu locatário.</span><span class="sxs-lookup"><span data-stu-id="526db-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="526db-108">Há seis insights de rede específicos que podem ser mostradas para cada local do escritório:</span><span class="sxs-lookup"><span data-stu-id="526db-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="526db-109">Saída de rede de rebocada</span><span class="sxs-lookup"><span data-stu-id="526db-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="526db-110">Melhor desempenho detectado para clientes próximos de você</span><span class="sxs-lookup"><span data-stu-id="526db-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="526db-111">Uso de uma porta frontal de serviço do Exchange Online não ideal</span><span class="sxs-lookup"><span data-stu-id="526db-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="526db-112">Uso de uma porta frontal não ideal do SharePoint Online Service</span><span class="sxs-lookup"><span data-stu-id="526db-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="526db-113">Baixa velocidade de download da porta frontal do SharePoint</span><span class="sxs-lookup"><span data-stu-id="526db-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="526db-114">Saída de rede ideal para o usuário da China</span><span class="sxs-lookup"><span data-stu-id="526db-114">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="526db-115">Há dois insights de rede de nível de locatário que podem ser mostrados para o locatário.</span><span class="sxs-lookup"><span data-stu-id="526db-115">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="526db-116">Eles também aparecem nas páginas de Pontuação producvitivy:</span><span class="sxs-lookup"><span data-stu-id="526db-116">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="526db-117">Conexões de amostra do Exchange impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="526db-117">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="526db-118">Exemplos de conexões do SharePoint impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="526db-118">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="526db-119">Os insights de rede, as recomendações de desempenho e as avaliações no centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para os locatários do Microsoft 365 que foram registrados no programa de visualização de recurso.</span><span class="sxs-lookup"><span data-stu-id="526db-119">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="526db-120">Saída de rede de rebocada</span><span class="sxs-lookup"><span data-stu-id="526db-120">Backhauled network egress</span></span>

<span data-ttu-id="526db-121">Esta percepção será exibida se o serviço de insights de rede detectar que a distância de um determinado local de usuário para a saída da rede é maior que 500 milhas (800 quilômetros), indicando que o tráfego da Microsoft 365 está sendo repassado para um dispositivo ou proxy de borda Internet comum.</span><span class="sxs-lookup"><span data-stu-id="526db-121">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="526db-122">Esta percepção é abreviada como "egresso" em alguns modos de exibição de resumo.</span><span class="sxs-lookup"><span data-stu-id="526db-122">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Saída de rede de rebocada](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="526db-124">Cenário</span><span class="sxs-lookup"><span data-stu-id="526db-124">What does this mean?</span></span>

<span data-ttu-id="526db-125">Isso identifica que a distância entre o local do escritório e a egresso da rede é maior que 500 milhas (800 quilômetros).</span><span class="sxs-lookup"><span data-stu-id="526db-125">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="526db-126">O local do Office é identificado por um local de máquina cliente ofuscado e o local de egresso de rede é identificado usando o endereço IP reverso para os bancos de dados de local.</span><span class="sxs-lookup"><span data-stu-id="526db-126">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="526db-127">O local do escritório pode ser impreciso se os serviços de localização do Windows estiverem desabilitados nos computadores.</span><span class="sxs-lookup"><span data-stu-id="526db-127">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="526db-128">O local de egresso de rede pode ser impreciso se as informações do banco de dados de endereço IP reverso não forem precisas.</span><span class="sxs-lookup"><span data-stu-id="526db-128">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="526db-129">Os detalhes desta percepção incluem o local do escritório, porcentagem estimada do usuário do locatário total no local, o local de egresso da rede atual, relevância do local de egresso, a distância entre o local e o ponto de saída atual, a data em que a condição foi detectada pela primeira vez e a data em que a condição foi resolvida.</span><span class="sxs-lookup"><span data-stu-id="526db-129">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="526db-130">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="526db-130">What should I do?</span></span>

<span data-ttu-id="526db-131">Para esta percepção, recomendamos que a saída da rede fique mais próxima do local do escritório, para que a conectividade possa ser roteada de maneira ideal para a rede global da Microsoft e para a porta mais próxima do serviço do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="526db-131">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="526db-132">Após o fechamento de egresso da rede para usuários, os locais do Office também permitem um desempenho aprimorado no futuro, já que a Microsoft expande tanto os pontos de presença de rede quanto as portas frontais de serviço do Microsoft 365 no futuro.</span><span class="sxs-lookup"><span data-stu-id="526db-132">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="526db-133">Para obter mais informações sobre como resolver esse problema, confira [conexões de rede de saída localmente](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) nos [princípios de conectividade de rede do Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="526db-133">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="526db-134">Melhor desempenho detectado para clientes próximos de você</span><span class="sxs-lookup"><span data-stu-id="526db-134">Better performance detected for customers near you</span></span>

<span data-ttu-id="526db-135">Esta percepção será exibida se o serviço de insights de rede detectar que um número significativo de clientes em sua área de metrô tem melhor desempenho do que os usuários em sua organização nesse local do escritório.</span><span class="sxs-lookup"><span data-stu-id="526db-135">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="526db-136">Esta percepção é abreviada como "pares" em alguns modos de exibição de resumo.</span><span class="sxs-lookup"><span data-stu-id="526db-136">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Desempenho de rede relativo](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="526db-138">Cenário</span><span class="sxs-lookup"><span data-stu-id="526db-138">What does this mean?</span></span>

<span data-ttu-id="526db-139">Essa percepção examina o desempenho agregado dos clientes do Microsoft 365 na mesma cidade que este local do escritório.</span><span class="sxs-lookup"><span data-stu-id="526db-139">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="526db-140">Esta percepção será exibida se a latência média de seus usuários for 10% maior do que a latência média dos locatários vizinhos.</span><span class="sxs-lookup"><span data-stu-id="526db-140">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="526db-141">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="526db-141">What should I do?</span></span>

<span data-ttu-id="526db-142">Pode haver vários motivos para esta condição, incluindo latência na rede corporativa ou no provedor de Internet, afunilamentos ou problemas de design de arquitetura.</span><span class="sxs-lookup"><span data-stu-id="526db-142">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="526db-143">Examine a latência entre cada salto na rota entre a rede do Office e a porta frontal do Microsoft 365 atual.</span><span class="sxs-lookup"><span data-stu-id="526db-143">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="526db-144">Para obter mais informações, consulte [princípios de conectividade de rede do Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="526db-144">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="526db-145">Uso de uma porta frontal de serviço do Exchange Online não ideal</span><span class="sxs-lookup"><span data-stu-id="526db-145">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="526db-146">Esta percepção será exibida se o serviço de insights de rede detectar que os usuários em um local específico não estão se conectando a uma porta de entrada ideal do Exchange Online Service.</span><span class="sxs-lookup"><span data-stu-id="526db-146">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="526db-147">Esta percepção é abreviada como "roteamento" em alguns modos de exibição de resumo.</span><span class="sxs-lookup"><span data-stu-id="526db-147">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Porta frontal EXO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="526db-149">Cenário</span><span class="sxs-lookup"><span data-stu-id="526db-149">What does this mean?</span></span>

<span data-ttu-id="526db-150">Listamos as portas frontais do serviço do Exchange Online que são adequadas para uso da cidade de local do escritório com bom desempenho.</span><span class="sxs-lookup"><span data-stu-id="526db-150">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="526db-151">Se o teste atual mostrar o uso de uma porta frontal do serviço do Exchange Online que não está nessa lista, chamamos essa recomendação.</span><span class="sxs-lookup"><span data-stu-id="526db-151">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="526db-152">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="526db-152">What should I do?</span></span>

<span data-ttu-id="526db-153">O uso de uma porta de entrada de serviço do Exchange Online não ideal pode ser causado pelo backhaul de rede antes da saída da rede corporativa, caso recomendamos a saída de rede local e direta.</span><span class="sxs-lookup"><span data-stu-id="526db-153">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="526db-154">Também pode ser causado pelo uso de um servidor de resolvedor de DNS recursivo remoto, caso recomendamos alinhar o servidor do resolvedor de DNS recursivo com a saída da rede.</span><span class="sxs-lookup"><span data-stu-id="526db-154">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="526db-155">Uso de uma porta frontal não ideal do SharePoint Online Service</span><span class="sxs-lookup"><span data-stu-id="526db-155">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="526db-156">Esta percepção será exibida se o serviço de insights de rede detectar que os usuários em um local específico não estão se conectando à porta frontal mais próxima do SharePoint Online Service.</span><span class="sxs-lookup"><span data-stu-id="526db-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="526db-157">Esta percepção é abreviada como "AFD" em alguns modos de exibição de resumo.</span><span class="sxs-lookup"><span data-stu-id="526db-157">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Porta frontal SPO não ideal](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="526db-159">Cenário</span><span class="sxs-lookup"><span data-stu-id="526db-159">What does this mean?</span></span>

<span data-ttu-id="526db-160">Identificamos a porta frontal do serviço do SharePoint Online à qual o cliente de teste está se conectando.</span><span class="sxs-lookup"><span data-stu-id="526db-160">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="526db-161">Em seguida, para a cidade do local do escritório, comparamos isso à porta frontal do serviço do SharePoint Online esperado para essa cidade.</span><span class="sxs-lookup"><span data-stu-id="526db-161">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="526db-162">Se não coincidir, fazemos essa recomendação.</span><span class="sxs-lookup"><span data-stu-id="526db-162">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="526db-163">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="526db-163">What should I do?</span></span>

<span data-ttu-id="526db-164">O uso de uma porta de entrada de serviço do SharePoint Online não ideal pode ser causado pelo backhaul de rede antes da saída da rede corporativa, caso recomendamos a saída de rede local e direta.</span><span class="sxs-lookup"><span data-stu-id="526db-164">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="526db-165">Também pode ser causado pelo uso de um servidor de resolvedor de DNS recursivo remoto, caso recomendamos alinhar o servidor do resolvedor de DNS recursivo com a saída da rede.</span><span class="sxs-lookup"><span data-stu-id="526db-165">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="526db-166">Baixa velocidade de download da porta frontal do SharePoint</span><span class="sxs-lookup"><span data-stu-id="526db-166">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="526db-167">Esta percepção será exibida se o serviço de insights de rede detectar essa largura de banda entre o local específico do Office e o SharePoint Online for menor que 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="526db-167">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="526db-168">Esta percepção é abreviada como "throughput" em alguns modos de exibição de resumo.</span><span class="sxs-lookup"><span data-stu-id="526db-168">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="526db-169">Cenário</span><span class="sxs-lookup"><span data-stu-id="526db-169">What does this mean?</span></span>

<span data-ttu-id="526db-170">A velocidade de download que um usuário pode obter do SharePoint Online e do OneDrive for Business Service Doors é medida em megabytes por segundo (MBps).</span><span class="sxs-lookup"><span data-stu-id="526db-170">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="526db-171">Se esse valor for menor que 1 MBps, forneceremos esta percepção.</span><span class="sxs-lookup"><span data-stu-id="526db-171">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="526db-172">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="526db-172">What should I do?</span></span>

<span data-ttu-id="526db-173">Para melhorar as velocidades de download, a largura de banda pode precisar ser aumentada.</span><span class="sxs-lookup"><span data-stu-id="526db-173">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="526db-174">Como alternativa, pode haver congestionamento de rede entre máquinas de usuário no local do escritório e na porta frontal do serviço do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="526db-174">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="526db-175">Isso às vezes é chamado de perda congestionada e restringe a velocidade de download disponível para os usuários, mesmo se houver largura de banda suficiente disponível.</span><span class="sxs-lookup"><span data-stu-id="526db-175">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="526db-176">Saída de rede ideal para o usuário da China</span><span class="sxs-lookup"><span data-stu-id="526db-176">China user optimal network egress</span></span>

<span data-ttu-id="526db-177">Esta percepção será exibida se sua organização tiver usuários na China se conectarem ao seu locatário do Microsoft 365 em outros locais geográficos.</span><span class="sxs-lookup"><span data-stu-id="526db-177">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="526db-178">Cenário</span><span class="sxs-lookup"><span data-stu-id="526db-178">What does this mean?</span></span>

<span data-ttu-id="526db-179">Se sua organização tem conectividade de WAN privada, recomendamos configurar um circuito de WAN de rede de seus locais do Office na China que têm a saída da rede para a Internet em qualquer um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="526db-179">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="526db-180">Hong Kong</span><span class="sxs-lookup"><span data-stu-id="526db-180">Hong Kong</span></span>
- <span data-ttu-id="526db-181">Japão</span><span class="sxs-lookup"><span data-stu-id="526db-181">Japan</span></span>
- <span data-ttu-id="526db-182">Taiwan</span><span class="sxs-lookup"><span data-stu-id="526db-182">Taiwan</span></span>
- <span data-ttu-id="526db-183">Coreia do Sul</span><span class="sxs-lookup"><span data-stu-id="526db-183">South Korea</span></span>
- <span data-ttu-id="526db-184">Cingapura</span><span class="sxs-lookup"><span data-stu-id="526db-184">Singapore</span></span>
- <span data-ttu-id="526db-185">Malásia</span><span class="sxs-lookup"><span data-stu-id="526db-185">Malaysia</span></span>

<span data-ttu-id="526db-186">O egresso de Internet mais distante dos usuários do que esses locais reduzirá o desempenho e o egresso na China pode causar problemas de alta latência e conectividade devido a um congestionamento entre bordas.</span><span class="sxs-lookup"><span data-stu-id="526db-186">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="526db-187">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="526db-187">What should I do?</span></span>

<span data-ttu-id="526db-188">Para obter mais informações sobre como reduzir problemas de desempenho relacionados a essa percepção, consulte [Office 365 global locatário Performance Optimization for China Users](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="526db-188">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="526db-189">Conexões de amostra do Exchange impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="526db-189">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="526db-190">Esta percepção mostrará quando 50% ou mais das conexões de amostra são impactadas.</span><span class="sxs-lookup"><span data-stu-id="526db-190">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="526db-191">O impacto é definido pela avaliação do Exchange abaixo de 60% para cada exemplo.</span><span class="sxs-lookup"><span data-stu-id="526db-191">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="526db-192">Cenário</span><span class="sxs-lookup"><span data-stu-id="526db-192">What does this mean?</span></span>

<span data-ttu-id="526db-193">É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com o Outlook se conectando ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="526db-193">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="526db-194">A porcentagem de amostras provavelmente representa a porcentagem de usuários que mostram abaixo de 60 pontos.</span><span class="sxs-lookup"><span data-stu-id="526db-194">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="526db-195">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="526db-195">What should I do?</span></span>

<span data-ttu-id="526db-196">Habilitar a visibilidade da conectividade de rede do Office local, se você ainda não tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="526db-196">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="526db-197">Você deseja identificar quais escritórios são impactados pela baixa conectividade de rede que está afetando o Exchange e encontre maneiras de melhorar o perímetro de rede em cada um que conecte os usuários à rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="526db-197">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="526db-198">Exemplos de conexões do SharePoint impactadas por problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="526db-198">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="526db-199">Esta percepção mostrará quando 50% ou mais das conexões de amostra são impactadas.</span><span class="sxs-lookup"><span data-stu-id="526db-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="526db-200">O impacto é definido pela avaliação do SharePoint que está abaixo de 40% para cada exemplo.</span><span class="sxs-lookup"><span data-stu-id="526db-200">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="526db-201">Cenário</span><span class="sxs-lookup"><span data-stu-id="526db-201">What does this mean?</span></span>

<span data-ttu-id="526db-202">É uma indicação de que a maioria dos seus usuários provavelmente está enfrentando problemas de experiência do usuário com o SharePoint e o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="526db-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="526db-203">A porcentagem de amostras provavelmente representa a porcentagem de usuários que mostram abaixo de 40 pontos.</span><span class="sxs-lookup"><span data-stu-id="526db-203">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="526db-204">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="526db-204">What should I do?</span></span>

<span data-ttu-id="526db-205">Habilitar a visibilidade da conectividade de rede do Office local, se você ainda não tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="526db-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="526db-206">Você deseja identificar quais escritórios são impactados pela baixa conectividade de rede que está afetando o SharePoint e encontre maneiras de melhorar o perímetro de rede em cada um que conecte os usuários à rede da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="526db-206">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="526db-207">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="526db-207">Related topics</span></span>

[<span data-ttu-id="526db-208">Conectividade de rede no centro de administração do Microsoft 365 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="526db-208">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="526db-209">Avaliação de rede do Microsoft 365 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="526db-209">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="526db-210">Ferramenta de teste de conectividade de rede 365 da Microsoft (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="526db-210">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="526db-211">Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="526db-211">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
