---
title: Configurar sua rede para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Encontre links para artigos com informações para ajudá-lo a configurar sua rede para o Microsoft 365, incluindo uma visão geral da conectividade de rede e uma lista de pontos de extremidade.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686976"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="e0197-103">Configurar sua rede para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0197-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="e0197-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e0197-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e0197-105">Uma parte importante da integração com o Microsoft 365 é garantir que as conexões de rede e Internet sejam configuradas para acesso otimizado.</span><span class="sxs-lookup"><span data-stu-id="e0197-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="e0197-106">Configurar sua rede local para acessar uma nuvem de software (SaaS) distribuída globalmente é diferente de uma rede tradicional que é otimizada para o tráfego para os datacenters locais e uma conexão central com a Internet.</span><span class="sxs-lookup"><span data-stu-id="e0197-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="e0197-107">Use estes artigos para entender as principais diferenças e modificar seus dispositivos de borda, computadores clientes e rede local para obter o melhor desempenho para seus usuários locais.</span><span class="sxs-lookup"><span data-stu-id="e0197-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="e0197-108">Como funciona a rede Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0197-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="e0197-109">Consulte estes artigos para obter uma visão geral da conectividade do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e0197-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="e0197-110">Visão geral da conectividade de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0197-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="e0197-111">Princípios de conectividade de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0197-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="e0197-112">Avaliando a conectividade de rede do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0197-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="e0197-113">Para obter conselhos sobre como melhorar o desempenho, consulte [planejamento de rede e ajuste de desempenho para o Microsoft 365](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="e0197-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="e0197-114">Suporte para redes Microsoft 365 como um fornecedor de equipamento de rede</span><span class="sxs-lookup"><span data-stu-id="e0197-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="e0197-p102">Se você é um fornecedor de equipamentos de rede, junte-se ao [Programa de Parceiros de Rede do Office 365](microsoft-365-networking-partner-program.md). Inscreva-se no programa para integrar princípios de conectividade de rede do Office 365 aos seus produtos e soluções.</span><span class="sxs-lookup"><span data-stu-id="e0197-p102">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md). Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="e0197-117">Pontos de extremidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="e0197-117">Office 365 endpoints</span></span>

<span data-ttu-id="e0197-118">Pontos de extremidade são o conjunto de endereços IP de destino, nomes de domínio do DNS e URLs do tráfego do Office 365 na Internet.</span><span class="sxs-lookup"><span data-stu-id="e0197-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="e0197-p103">Para otimizar o desempenho dos serviços baseados em nuvem do Office 365, alguns pontos de extremidade precisam de tratamento especial pelos navegadores clientes e pelos dispositivos da rede de borda. Esses dispositivos incluem firewalls, SSL Break and Inspect e dispositivos de inspeção de pacotes e sistemas de prevenção de perda de dados.</span><span class="sxs-lookup"><span data-stu-id="e0197-p103">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network. These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="e0197-121">Confira [Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="e0197-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="e0197-p104">Atualmente, há cinco nuvens diferentes do Office 365. Esta tabela leva você à lista de pontos de extremidade de cada um deles.</span><span class="sxs-lookup"><span data-stu-id="e0197-p104">There are currently five different Office 365 clouds. This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="e0197-124">Pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="e0197-124">Endpoints</span></span> | <span data-ttu-id="e0197-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0197-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="e0197-126">Pontos de extremidade mundiais</span><span class="sxs-lookup"><span data-stu-id="e0197-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="e0197-127">Os pontos de extremidade das assinaturas do Office 365 em todo o mundo, que incluem a United States Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="e0197-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="e0197-128">Pontos de extremidade do US Government DoD</span><span class="sxs-lookup"><span data-stu-id="e0197-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="e0197-129">Os pontos de extremidade das assinaturas do Departamento de Defesa dos Estados Unidos (DoD).</span><span class="sxs-lookup"><span data-stu-id="e0197-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="e0197-130">Pontos de extremidade do US Government GCC High</span><span class="sxs-lookup"><span data-stu-id="e0197-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="e0197-131">Os pontos de extremidade das assinaturas da United States Government Community Cloud High (GCC alto).</span><span class="sxs-lookup"><span data-stu-id="e0197-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="e0197-132">Pontos de extremidade do Office 365 operado pela 21Vianet</span><span class="sxs-lookup"><span data-stu-id="e0197-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="e0197-133">Os pontos de extremidade do Office 365 operado pela 21Vianet, que são projetados para atender às necessidades do Office 365 na China.</span><span class="sxs-lookup"><span data-stu-id="e0197-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="e0197-134">Pontos de extremidade do Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="e0197-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="e0197-135">Os pontos de extremidade uma nuvem separada na Europa para a maioria dos clientes regulamentados na Alemanha, União Europeia (UE) e Associação Europeia de Livre Comércio (EFTA).</span><span class="sxs-lookup"><span data-stu-id="e0197-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="e0197-136">Para obter automaticamente a lista mais recente de pontos de extremidade de sua nuvem do Office 365, confira o [Serviços de Endereços IP e URLs da Web do Office 365](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="e0197-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="e0197-137">Para pontos de extremidade adicionais, confira estes artigos:</span><span class="sxs-lookup"><span data-stu-id="e0197-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="e0197-138">Pontos de extremidade adicionais não incluídos nos serviços Web</span><span class="sxs-lookup"><span data-stu-id="e0197-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="e0197-139">Solicitações de rede do Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="e0197-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="e0197-140">Tópicos adicionais para a rede 365 da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0197-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="e0197-141">Consulte estes artigos sobre tópicos especializados na rede Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e0197-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="e0197-142">Redes de distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="e0197-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="e0197-143">Suporte a IPv6 nos serviços do Office 365</span><span class="sxs-lookup"><span data-stu-id="e0197-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="e0197-144">Suporte a NAT com o Office 365</span><span class="sxs-lookup"><span data-stu-id="e0197-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="e0197-145">ExpressRoute para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0197-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="e0197-146">Confira estes artigos para obter informações sobre o uso do ExpressRoute para tráfego do Office 365:</span><span class="sxs-lookup"><span data-stu-id="e0197-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="e0197-147">Microsoft Azure ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0197-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="e0197-148">Como implementar o ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0197-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="e0197-149">Planejamento de rede com o ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0197-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="e0197-150">Como rotear com o ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0197-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
