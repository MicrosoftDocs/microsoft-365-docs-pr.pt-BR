---
title: 'Etapa 3: Evitar hairpins de rede'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e remova hairpins de rede para melhorar o desempenho.
ms.openlocfilehash: 7277b8f5c07bc156599f946e032c3345da3316e9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865318"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="1d3a5-103">Etapa 3: Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="1d3a5-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="1d3a5-104">*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="1d3a5-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="1d3a5-p101">Um [hairpin de rede](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) ocorre quando o tráfego vinculado a um destino é direcionado primeiro para outro local intermediário, como uma pilha de segurança local, um agente de acesso à nuvem ou um gateway da Web baseado em nuvem. Um hairpin de rede também pode ser causado por mau roteamento na Internet devido a provedores de serviços de rede. O hairpin adiciona latência e pode redirecionar potencialmente o tráfego para um local geograficamente distante.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-p101">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway. A network hairpin could also be caused by poor routing on the Internet due to network service providers. A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="1d3a5-p102">Para otimizar o desempenho do tráfego para serviços baseados em nuvem do Microsoft 365, verifique se o provedor que fornece a conexão local com a Internet tem um relacionamento de emparelhamento direto com a Rede Global da Microsoft bem próxima a esse local. Essas conexões não possuem hairpins.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="1d3a5-p103">Se você usa serviços de rede ou segurança baseados em nuvem para o tráfego do Microsoft 365, certifique-se de que o efeito do hairpin seja avaliado e seu impacto no desempenho seja compreendido. Analise o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1d3a5-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="1d3a5-112">O número e a localização dos provedores de serviços através dos quais o tráfego é encaminhado em relação às suas filiais e aos pontos de emparelhamento da Rede Global da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1d3a5-112">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="1d3a5-113">A qualidade da relação de emparelhamento de rede do provedor de serviços com seu ISP e a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1d3a5-113">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="1d3a5-114">O impacto no desempenho de backhaul na infraestrutura do provedor de serviços</span><span class="sxs-lookup"><span data-stu-id="1d3a5-114">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="1d3a5-115">Sempre que possível, configure seus roteadores de borda para enviar tráfego confiável do Microsoft 365 diretamente, em vez de fazer proxy ou encapsulamento por meio de um fornecedor terceirizado de segurança de rede baseado em nuvem ou na nuvem que processa o tráfego da Internet.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-115">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

<span data-ttu-id="1d3a5-116">Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step3) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="1d3a5-117">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1d3a5-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="1d3a5-118">Configurar o bypass de tráfego</span><span class="sxs-lookup"><span data-stu-id="1d3a5-118">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
