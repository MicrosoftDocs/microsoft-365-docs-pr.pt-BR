---
title: 'Etapa 4: Configurar o bypass de tráfego'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure os navegadores da web e os dispositivos de borda para executar bypass de tráfego dos locais confiáveis do Office 365.
ms.openlocfilehash: b04e16b249dccf8f2461189b8b47abdd252a75d8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2020
ms.locfileid: "43504074"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="f5f26-103">Etapa 4: Configurar o bypass de tráfego</span><span class="sxs-lookup"><span data-stu-id="f5f26-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="f5f26-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="f5f26-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1 – Rede](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="f5f26-106">Como o tráfego geral da Internet pode ser arriscado, as redes de organizações típicas reforçam a segurança com dispositivos de borda, como servidores proxy, Interrupção e Inspeção de SSL, dispositivos de inspeção de pacotes e sistemas de prevenção de perda de dados.</span><span class="sxs-lookup"><span data-stu-id="f5f26-106">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="f5f26-107">Leia sobre alguns dos problemas com dispositivos de interceptação de rede em [Usar soluções ou dispositivos de rede de terceiros em tráfego do Office 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="f5f26-107">Read about some of the issues with network interception devices at [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span></span>

<span data-ttu-id="f5f26-p102">No entanto, os endereços IP e nomes de domínio DNS usados pelos serviços de nuvem do Microsoft 365 são conhecidos. Além disso, o tráfego e os serviços por si só são protegidos por vários recursos de segurança. Como essa proteção e segurança já está em funcionamento, os dispositivos de borda não precisam duplicá-la. Os destinos intermediários e o processamento de segurança duplicado do tráfego do Microsoft 365 podem reduzir significativamente o desempenho.</span><span class="sxs-lookup"><span data-stu-id="f5f26-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="f5f26-p103">A primeira etapa para eliminar destinos intermediários e processamento de segurança duplicado é identificar o tráfego do Microsoft 365. A Microsoft definiu os seguintes intervalos de endereços IP e tipos de nomes de domínio de DNS, conhecidos como pontos de extremidade:</span><span class="sxs-lookup"><span data-stu-id="f5f26-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="f5f26-114">**Otimizar** - necessário para a conectividade com todos os serviços do Office 365 e representa mais de 75% da largura de banda, conexões e volume de dados do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5f26-114">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="f5f26-115">Esses pontos de extremidade representam os cenários do Microsoft 365 mais confidenciais para o desempenho, latência e disponibilidade da rede.</span><span class="sxs-lookup"><span data-stu-id="f5f26-115">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency, and availability.</span></span>
- <span data-ttu-id="f5f26-116">**Permitir** - necessário para a conectividade com os recursos e serviços específicos do Microsoft 365, mas não são tão sensíveis ao desempenho e à latência da rede quanto os da categoria Otimizar.</span><span class="sxs-lookup"><span data-stu-id="f5f26-116">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="f5f26-117">**Padrão** - representam os serviços e dependências do Microsoft 365 que não precisam de otimização.</span><span class="sxs-lookup"><span data-stu-id="f5f26-117">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization.</span></span> <span data-ttu-id="f5f26-118">Você pode considerar os pontos de extremidade de categoria padrão como tráfego normal da Internet.</span><span class="sxs-lookup"><span data-stu-id="f5f26-118">You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="f5f26-119">Você pode encontrar os intervalos de endereços IP e os nomes de domínio DNS em [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="f5f26-119">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="f5f26-120">A Microsoft recomenda que você:</span><span class="sxs-lookup"><span data-stu-id="f5f26-120">Microsoft recommends that you:</span></span>

- <span data-ttu-id="f5f26-121">Use scripts de Configuração Automática de Proxy (PAC) nos navegadores da Internet dos computadores no local para executar o bypass dos servidores proxy para os nomes de domínio DNS dos serviços baseados na nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5f26-121">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services.</span></span> <span data-ttu-id="f5f26-122">Para obter o script PAC mais recente do Microsoft 365, confira [Script Get-Pacfile do PowerShellt](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="f5f26-122">For the latest Microsoft 365 PAC script, see the [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

- <span data-ttu-id="f5f26-p107">Analise seus dispositivos de borda para determinar o processamento duplicado e configure-os para encaminhar o tráfego sem processamento para os pontos de extremidade Otimizar e Permitir, o que é conhecido como executar o bypass de tráfego.</span><span class="sxs-lookup"><span data-stu-id="f5f26-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="f5f26-125">Estas são as recomendações da sua infraestrutura de rede.</span><span class="sxs-lookup"><span data-stu-id="f5f26-125">Here are these recommendations in your network infrastructure.</span></span>

![Recomendações para otimizar o tráfego local](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

<span data-ttu-id="f5f26-127">Os dispositivos de borda incluem firewalls, Interrupção e Inspeção de SSL, dispositivos de inspeção de pacotes e sistemas de prevenção de perda de dados.</span><span class="sxs-lookup"><span data-stu-id="f5f26-127">Edge devices include firewalls, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="f5f26-128">Para configurar e atualizar as configurações de dispositivos de borda, é possível usar um script ou uma chamada REST para consumir uma lista estruturada de pontos de extremidade do serviço Web de pontos de extremidade do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5f26-128">To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service.</span></span> <span data-ttu-id="f5f26-129">Para obter mais informações, confira [Serviço Web de URL e Endereço IP do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span><span class="sxs-lookup"><span data-stu-id="f5f26-129">For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="f5f26-p109">Observe que você está apenas ignorando o processamento normal de segurança de rede e proxy do tráfego para os pontos de extremidade da categoria Otimizar e Permitir do Microsoft 365. Todo o outro tráfego geral da Internet será intermediado por proxy e estará sujeito ao processamento existente de segurança da rede.</span><span class="sxs-lookup"><span data-stu-id="f5f26-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>

## <a name="optimizing-traffic-for-remote-workers-that-use-vpn-connections"></a><span data-ttu-id="f5f26-132">Otimizando o tráfego para funcionários remotos que usam conexões VPN</span><span class="sxs-lookup"><span data-stu-id="f5f26-132">Optimizing traffic for remote workers that use VPN connections</span></span>

<span data-ttu-id="f5f26-133">As conexões VPN (rede virtual privada) são comumente usadas por funcionários remotos para acessar os recursos na intranet de uma organização.</span><span class="sxs-lookup"><span data-stu-id="f5f26-133">Virtual private network (VPN) connections are commonly used by remote workers to access resources on an organization intranet.</span></span> <span data-ttu-id="f5f26-134">Uma conexão VPN convencional roteia todo o tráfego, incluindo o tráfego da Internet, para a intranet da organização.</span><span class="sxs-lookup"><span data-stu-id="f5f26-134">A conventional VPN connection routes ALL traffic, including Internet traffic, to the organization intranet.</span></span> <span data-ttu-id="f5f26-135">O tráfego de Internet é encaminhado para a rede de borda da organização e dispositivos de processamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="f5f26-135">The Internet traffic gets routed to the organization's edge network and packet processing devices.</span></span> <span data-ttu-id="f5f26-136">Esse tráfego está sujeito a atrasos de viagens e processamentos que podem reduzir drasticamente o desempenho e afetar a produtividade dos funcionários remotos.</span><span class="sxs-lookup"><span data-stu-id="f5f26-136">This traffic is subject to travel and processing delays that can dramatically decrease performance and impact the productivity of your remote workers.</span></span> 

<span data-ttu-id="f5f26-137">O tunelamento dividido é a capacidade de uma conexão VPN para direcionar o tráfego especificado pela Internet, em vez de enviá-lo pela VPN para a sua intranet.</span><span class="sxs-lookup"><span data-stu-id="f5f26-137">Split tunneling is the capability of a VPN connection to route specified traffic over the Internet rather than sending it over the VPN connection to your intranet.</span></span> <span data-ttu-id="f5f26-138">Para obter o melhor desempenho para funcionários remotos a serviços essenciais do Microsoft 365, como Teams, SharePoint Online e Exchange Online, configure suas conexões VPN de túnel dividido para enviar o tráfego para otimizar os pontos de extremidade do Office 365 diretamente pela Internet.</span><span class="sxs-lookup"><span data-stu-id="f5f26-138">For the best performance for remote workers to critical Microsoft 365 services such as Teams, SharePoint Online, and Exchange Online, configure your split tunneling VPN connections to send traffic to Optimize category Office 365 endpoints directly over the Internet.</span></span> 

<span data-ttu-id="f5f26-139">Para informações mais detalhadas, confira [Otimizar a conectividade do Office 365 para usuários remotos usando a criação de túnel dividido de VPN](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="f5f26-139">For detailed information, see [Optimize Office 365 connectivity for remote users using VPN split tunnelling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

<span data-ttu-id="f5f26-140">Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step4) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f5f26-140">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5f26-141">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f5f26-141">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="f5f26-143">Otimizar o desempenho do serviço entre o cliente e o Office 365</span><span class="sxs-lookup"><span data-stu-id="f5f26-143">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



