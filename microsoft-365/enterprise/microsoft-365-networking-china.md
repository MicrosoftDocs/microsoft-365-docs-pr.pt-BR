---
title: Otimização de desempenho de locatário global do Microsoft 365 para usuários da China
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artigo fornece orientações para otimizar o desempenho da rede para usuários da China de locatários do Microsoft 365 global.
ms.openlocfilehash: 94de83a94bf6cdf5470b66970efb62094bdc4343
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687056"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a><span data-ttu-id="59f8a-103">Otimização de desempenho de locatário global do Microsoft 365 para usuários da China</span><span class="sxs-lookup"><span data-stu-id="59f8a-103">Microsoft 365 global tenant performance optimization for China users</span></span>

>[!IMPORTANT]
><span data-ttu-id="59f8a-104">Esta orientação é específica dos cenários de uso nos quais **os usuários do microsoft 365 Enterprise localizados na China** se conectam a um **locatário global do Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="59f8a-104">This guidance is specific to usage scenarios in which **enterprise Microsoft 365 users located in China** connect to a **global Microsoft 365 tenant**.</span></span> <span data-ttu-id="59f8a-105">Este guia não **se aplica** a locatários no Office 365 operado pela 21vianet.</span><span class="sxs-lookup"><span data-stu-id="59f8a-105">This guidance does **not** apply to tenants in Office 365 operated by 21Vianet.</span></span>

<span data-ttu-id="59f8a-106">Para empresas com locatários do Microsoft 365 globais e uma presença corporativa na China, o desempenho do cliente da Microsoft 365 para usuários baseados em China pode ser complicado por fatores exclusivos da arquitetura de Internet da Telco da China.</span><span class="sxs-lookup"><span data-stu-id="59f8a-106">For enterprises with global Microsoft 365 tenants and a corporate presence in China, Microsoft 365 client performance for China-based users can be complicated by factors unique to China Telco's Internet architecture.</span></span>

<span data-ttu-id="59f8a-107">Os ISPs da China têm regulamentados as conexões do exterior à Internet pública global que passam por dispositivos de perímetro que estão sujeitos a altos níveis de congestionamento de rede entre bordas.</span><span class="sxs-lookup"><span data-stu-id="59f8a-107">China ISPs have regulated offshore connections to the global public Internet that go through perimeter devices which are prone to high-levels of cross-border network congestion.</span></span> <span data-ttu-id="59f8a-108">Esse congestionamento cria perda de pacotes e latência para todo o tráfego da Internet entrando e saindo da China.</span><span class="sxs-lookup"><span data-stu-id="59f8a-108">This congestion creates packet loss and latency for all Internet traffic going into and out of China.</span></span>

![Tráfego Microsoft 365-não otimizado](../media/O365-networking/China-O365-unoptimized.png)

<span data-ttu-id="59f8a-110">A perda de pacotes e a latência são prejudiciais ao desempenho de serviços de rede, especialmente serviços que exigem grandes trocas de dados (como grandes transferências de arquivos) ou que exigem desempenho quase em tempo real (aplicativos de áudio e vídeo).</span><span class="sxs-lookup"><span data-stu-id="59f8a-110">Packet loss and latency is detrimental to the performance of network services, especially services that require large data exchanges (such as large file transfers) or requiring near real-time performance (audio and video applications).</span></span>

<span data-ttu-id="59f8a-111">O objetivo deste tópico é fornecer práticas recomendadas para reduzir o impacto do congestionamento da rede entre bordas da China nos serviços 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59f8a-111">The goal of this topic is to provide best practices for mitigating the impact of China cross-border network congestion on Microsoft 365 services.</span></span> <span data-ttu-id="59f8a-112">Este tópico não aborda outros problemas comuns de desempenho da última vista, como problemas de alta latência de pacote devido ao roteamento complexo dentro de operadoras da China.</span><span class="sxs-lookup"><span data-stu-id="59f8a-112">This topic does not address other common last-mile performance issues such as issues of high packet latency due to complex routing within China carriers.</span></span>

## <a name="corporate-network-best-practices"></a><span data-ttu-id="59f8a-113">Práticas recomendadas de rede corporativa</span><span class="sxs-lookup"><span data-stu-id="59f8a-113">Corporate network best practices</span></span>

<span data-ttu-id="59f8a-114">Muitas empresas com locatários e usuários globais da Microsoft 365 na China implementaram redes privadas que carregam tráfego de rede corporativa entre escritórios da China e locais do exterior no mundo todo.</span><span class="sxs-lookup"><span data-stu-id="59f8a-114">Many enterprises with global Microsoft 365 tenants and users in China have implemented private networks that carry corporate network traffic between China office locations and offshore locations around the world.</span></span> <span data-ttu-id="59f8a-115">Essas empresas podem aproveitar essa infraestrutura de rede para evitar o congestionamento de rede entre bordas e otimizar o desempenho do serviço Microsoft 365 na China.</span><span class="sxs-lookup"><span data-stu-id="59f8a-115">These enterprises can leverage this network infrastructure to avoid cross-border network congestion and optimize their Microsoft 365 service performance in China.</span></span>

>[!IMPORTANT]
><span data-ttu-id="59f8a-116">Assim como ocorre com todas as implementações de WAN privadas, você deve sempre consultar requisitos normativos para o seu país e/ou região para garantir que sua configuração de rede esteja em conformidade.</span><span class="sxs-lookup"><span data-stu-id="59f8a-116">As with all private WAN implementations, you should always consult regulatory requirements for your country and/or region to ensure that your network configuration is in compliance.</span></span>

<span data-ttu-id="59f8a-117">Como primeira etapa, é crucial que você siga as orientações da nossa rede de benchmark em [planejamento de rede e ajuste de desempenho para o Microsoft 365](https://aka.ms/tune).</span><span class="sxs-lookup"><span data-stu-id="59f8a-117">As a first step, it is crucial that you follow our benchmark network guidance at [Network planning and performance tuning for Microsoft 365](https://aka.ms/tune).</span></span> <span data-ttu-id="59f8a-118">O objetivo principal deve ser evitar acessar serviços globais da Microsoft 365 da Internet na China, se possível.</span><span class="sxs-lookup"><span data-stu-id="59f8a-118">The primary goal should be to avoid accessing global Microsoft 365 services from the Internet in China if possible.</span></span>

- <span data-ttu-id="59f8a-119">Aproveite a rede privada existente para transportar o tráfego de rede do Microsoft 365 entre as redes do Office da China e locais do exterior que egressom na Internet pública fora da China.</span><span class="sxs-lookup"><span data-stu-id="59f8a-119">Leverage your existing private network to carry Microsoft 365 network traffic between China office networks and offshore locations that egress on the public Internet outside China.</span></span> <span data-ttu-id="59f8a-120">Praticamente qualquer local fora da China oferecerá um benefício claro.</span><span class="sxs-lookup"><span data-stu-id="59f8a-120">Almost any location outside China will provide a clear benefit.</span></span> <span data-ttu-id="59f8a-121">Os administradores de rede podem otimizar ainda mais por egresso em áreas com interconexão de baixa latência com a [rede global da Microsoft](https://docs.microsoft.com/azure/networking/microsoft-global-network).</span><span class="sxs-lookup"><span data-stu-id="59f8a-121">Network administrators can further optimize by egressing in areas with low-latency interconnect with the [Microsoft global network](https://docs.microsoft.com/azure/networking/microsoft-global-network).</span></span> <span data-ttu-id="59f8a-122">Hong Kong, Japão e Coréia do Sul são exemplos.</span><span class="sxs-lookup"><span data-stu-id="59f8a-122">Hong Kong, Japan, and South Korea are examples.</span></span>
- <span data-ttu-id="59f8a-123">Configure os dispositivos de usuário para acessar a rede corporativa através de uma conexão VPN para permitir que o tráfego da Microsoft 365 seja transmitido ao link exterior privado da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="59f8a-123">Configure user devices to access the corporate network over a VPN connection to allow Microsoft 365 traffic to transit the corporate network's private offshore link.</span></span> <span data-ttu-id="59f8a-124">Verifique se os clientes VPN não estão configurados para usar o túnel de divisão ou se os dispositivos de usuário estão configurados para ignorar o túnel de divisão para o tráfego do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59f8a-124">Ensure that VPN clients are either not configured to use split tunneling, or that user devices are configured to ignore split tunneling for Microsoft 365 traffic.</span></span>
- <span data-ttu-id="59f8a-125">Configure sua rede para rotear todo o tráfego do Microsoft 365 em seu link exterior privado.</span><span class="sxs-lookup"><span data-stu-id="59f8a-125">Configure your network to route all Microsoft 365 traffic across your private offshore link.</span></span> <span data-ttu-id="59f8a-126">Se for necessário minimizar o volume de tráfego no seu link privado, você poderá optar por direcionar somente os pontos de extremidade na categoria **otimizar** e permitir que as solicitações para **permitir** e os pontos de extremidade **padrão** sejam de trânsito à Internet.</span><span class="sxs-lookup"><span data-stu-id="59f8a-126">If you must minimize the volume of traffic on your private link, you can choose to only route endpoints in the **Optimize** category, and allow requests to **Allow** and **Default** endpoints to transit the Internet.</span></span> <span data-ttu-id="59f8a-127">Isso melhorará o desempenho e minimizará o consumo de largura de banda, limitando o tráfego otimizado aos serviços críticos que são mais confidenciais à alta latência e perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="59f8a-127">This will improve performance and minimize bandwidth consumption by limiting optimized traffic to critical services that are most sensitive to high latency and packet loss.</span></span>
- <span data-ttu-id="59f8a-128">Se possível, use UDP em vez do TCP para tráfego de fluxo de mídias do Live, como o para Teams.</span><span class="sxs-lookup"><span data-stu-id="59f8a-128">If possible, use UDP instead of TCP for live media streaming traffic, such as for Teams.</span></span> <span data-ttu-id="59f8a-129">O UDP oferece melhor desempenho de fluxo contínuo de mídia do Live do que o TCP.</span><span class="sxs-lookup"><span data-stu-id="59f8a-129">UDP offers better live media streaming performance than TCP.</span></span>

<span data-ttu-id="59f8a-130">Para obter informações sobre como encaminhar seletivamente o tráfego do Microsoft 365, consulte [Managing Office 365 Endpoints](managing-office-365-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="59f8a-130">For information about how to selectively route Microsoft 365 traffic, see [Managing Office 365 endpoints](managing-office-365-endpoints.md).</span></span> <span data-ttu-id="59f8a-131">Para obter uma lista de todos os endereços IP e URLs do Office 365 em todo o mundo, confira [URLs e intervalos de endereços IP do office 365](urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="59f8a-131">For a list of all worldwide Office 365 URLs and IP addresses, see [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>

![Microsoft 365 com otimização de tráfego](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a><span data-ttu-id="59f8a-133">Práticas recomendadas do usuário</span><span class="sxs-lookup"><span data-stu-id="59f8a-133">User best practices</span></span>

<span data-ttu-id="59f8a-134">Os usuários na China que se conectam aos locatários globais do Microsoft 365 de locais remotos, como residências, lanchonetes, hotéis e filiais sem conexão com redes corporativas podem experimentar um desempenho de rede ruim, pois o tráfego entre seus dispositivos e a Microsoft 365 devem ter circuitos de rede entre bordas congestionadas da China.</span><span class="sxs-lookup"><span data-stu-id="59f8a-134">Users in China who connect to global Microsoft 365 tenants from remote locations such as homes, coffee shops, hotels and branch offices with no connection to enterprise networks can experience poor network performance because traffic between their devices and Microsoft 365 must transit China's congested cross-border network circuits.</span></span>

<span data-ttu-id="59f8a-135">Se as redes privadas e/ou o acesso VPN na rede corporativa não forem uma opção, os problemas de desempenho por usuário ainda poderão ser atenuados ao treinar os usuários baseados na China para seguir estas práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="59f8a-135">If cross-border private networks and/or VPN access into the corporate network are not an option, per-user performance issues can still be mitigated by training your China-based users to follow these best practices.</span></span>

- <span data-ttu-id="59f8a-136">Use clientes do Office avançados que oferecem suporte a cache (por exemplo, Outlook, Teams, OneDrive, etc.) e evite clientes baseados na Web.</span><span class="sxs-lookup"><span data-stu-id="59f8a-136">Utilize rich Office clients that support caching (e.g. Outlook, Teams, OneDrive, etc.), and avoid web-based clients.</span></span> <span data-ttu-id="59f8a-137">Os recursos de cache de cliente do Office e acesso offline podem reduzir drasticamente o impacto do congestionamento da rede e da latência.</span><span class="sxs-lookup"><span data-stu-id="59f8a-137">Office client caching and offline access features can dramatically reduce the impact of network congestion and latency.</span></span>
- <span data-ttu-id="59f8a-138">Se o seu locatário do Microsoft 365 tiver sido configurado com o recurso de _audioconferência_ , os usuários do teams poderão ingressar em reuniões através da rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="59f8a-138">If your Microsoft 365 tenant has been configured with the _Audio Conferencing_ feature, Teams users can join meetings via the public switched telephone network (PSTN).</span></span> <span data-ttu-id="59f8a-139">Para obter mais informações, consulte [audioconferência no Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="59f8a-139">For more information, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span>
- <span data-ttu-id="59f8a-140">Se os usuários experimentarem problemas de desempenho de rede, eles deverão relatar ao seu departamento de ti para solução de problemas e escalonar para o suporte da Microsoft se houver suspeita de problemas com os serviços 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59f8a-140">If users experience network performance issues, they should report to their IT department for troubleshooting, and escalate to Microsoft support if trouble with Microsoft 365 services is suspected.</span></span> <span data-ttu-id="59f8a-141">Nem todos os problemas são causados pelo desempenho da rede entre bordas.</span><span class="sxs-lookup"><span data-stu-id="59f8a-141">Not all issues are caused by cross-border network performance.</span></span>

<span data-ttu-id="59f8a-142">A Microsoft está sempre trabalhando para melhorar a experiência do usuário da Microsoft 365 e o desempenho de clientes sobre a maior variedade possível de arquiteturas e características de rede.</span><span class="sxs-lookup"><span data-stu-id="59f8a-142">Microsoft is continually working to improve the Microsoft 365 user experience and the performance of clients over the widest possible range of network architectures and characteristics.</span></span> <span data-ttu-id="59f8a-143">Visite a [comunidade de tecnologia do Office 365](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) para iniciar ou ingressar em uma conversa, localizar recursos e enviar solicitações de recurso e sugestões.</span><span class="sxs-lookup"><span data-stu-id="59f8a-143">Visit the [Office 365 Tech Community](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) to start or join a conversation, find resources, and submit feature requests and suggestions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="59f8a-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="59f8a-144">Related topics</span></span>

[<span data-ttu-id="59f8a-145">Planejamento de rede e ajuste de desempenho para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59f8a-145">Network planning and performance tuning for Microsoft 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="59f8a-146">Princípios de conectividade de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59f8a-146">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="59f8a-147">Gerenciar pontos de extremidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="59f8a-147">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="59f8a-148">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="59f8a-148">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="59f8a-149">Rede global da Microsoft</span><span class="sxs-lookup"><span data-stu-id="59f8a-149">Microsoft global network</span></span>](https://docs.microsoft.com/azure/networking/microsoft-global-network)