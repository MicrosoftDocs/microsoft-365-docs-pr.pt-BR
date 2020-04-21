---
title: 'Etapa 3: Evitar hairpins de rede'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e remova hairpins de rede para melhorar o desempenho.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583420"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="0b8bb-103">Etapa 3: Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="0b8bb-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="0b8bb-104">*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0b8bb-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1 – Rede](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="0b8bb-106">Um [hairpin de rede](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) acontece quando o tráfego vinculado a um destino é direcionado primeiro para outro local intermediário, como uma pilha de segurança local, um agente de acesso à nuvem ou um gateway Web baseado em nuvem.</span><span class="sxs-lookup"><span data-stu-id="0b8bb-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="0b8bb-107">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="0b8bb-107">Here is an example.</span></span>

![Exemplo de um hairpin de rede](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="0b8bb-109">Um hairpin de rede também pode ser causado por um roteamento insatisfatório na Internet, devido aos provedores de serviços de rede.</span><span class="sxs-lookup"><span data-stu-id="0b8bb-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="0b8bb-110">Um hairpin adiciona latência e pode redirecionar o tráfego para um local distante geograficamente.</span><span class="sxs-lookup"><span data-stu-id="0b8bb-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="0b8bb-p102">Para otimizar o desempenho do tráfego para serviços baseados em nuvem do Microsoft 365, verifique se o provedor que fornece a conexão local com a Internet tem um relacionamento de emparelhamento direto com a Rede Global da Microsoft bem próxima a esse local. Essas conexões não possuem hairpins.</span><span class="sxs-lookup"><span data-stu-id="0b8bb-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="0b8bb-p103">Se você usa serviços de rede ou segurança baseados em nuvem para o tráfego do Microsoft 365, certifique-se de que o efeito do hairpin seja avaliado e seu impacto no desempenho seja compreendido. Analise o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0b8bb-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="0b8bb-115">O número e a localização dos provedores de serviços através dos quais o tráfego é encaminhado em relação às suas filiais e aos pontos de emparelhamento da Rede Global da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0b8bb-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="0b8bb-116">A qualidade da relação de emparelhamento de rede do provedor de serviços com seu ISP e a Microsoft</span><span class="sxs-lookup"><span data-stu-id="0b8bb-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="0b8bb-117">O impacto no desempenho de backhaul na infraestrutura do provedor de serviços</span><span class="sxs-lookup"><span data-stu-id="0b8bb-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="0b8bb-118">Sempre que possível, configure seus roteadores de borda para enviar tráfego confiável do Microsoft 365 diretamente, em vez de fazer proxy ou encapsulamento por meio de um fornecedor terceirizado de segurança de rede baseado em nuvem ou na nuvem que processa o tráfego da Internet.</span><span class="sxs-lookup"><span data-stu-id="0b8bb-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![Exemplo de um hairpin de rede sendo ignorado](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="0b8bb-120">Para testar o quão perto você está de um ponto de entrada da rede global da Microsoft e o quão perto você está do ponto em que a rede da sua organização se conecta ao seu ISP, use a [ferramenta de Integração de Rede do Office 365](https://connectivity.office.com/).</span><span class="sxs-lookup"><span data-stu-id="0b8bb-120">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="0b8bb-121">Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step3) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="0b8bb-121">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="0b8bb-122">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="0b8bb-122">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="0b8bb-124">Configurar o bypass de tráfego</span><span class="sxs-lookup"><span data-stu-id="0b8bb-124">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
