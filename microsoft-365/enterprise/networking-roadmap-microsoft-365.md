---
title: Mapa de rede para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: O mapa para implementar a rede Microsoft 365.
ms.openlocfilehash: 93d0f253e098815139b431a826f7e5e7a0410b37
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687212"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="ddcc3-103">Mapa de rede para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddcc3-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="ddcc3-104">O Microsoft 365 for Enterprise inclui serviços em nuvem de colaboração e produtividade, Microsoft Intune e muitos serviços de identidade e segurança do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="ddcc3-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="ddcc3-105">Todos esses serviços baseados em nuvem dependem da segurança, desempenho e confiabilidade das conexões de dispositivos clientes pela Internet ou circuitos dedicados.</span><span class="sxs-lookup"><span data-stu-id="ddcc3-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="ddcc3-106">Para hospedar esses serviços e disponibilizá-los para clientes em todo o mundo, a Microsoft desenvolveu uma infraestrutura de rede que enfatiza o desempenho e a integração.</span><span class="sxs-lookup"><span data-stu-id="ddcc3-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="ddcc3-107">Uma parte crucial da integração do Microsoft 365 é garantir que as conexões de rede e Internet estejam configuradas para acesso otimizado.</span><span class="sxs-lookup"><span data-stu-id="ddcc3-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="ddcc3-108">Configurar sua rede local para acessar uma nuvem de software (SaaS) distribuída globalmente é diferente de uma rede tradicional que é otimizada para o tráfego para os datacenters locais e uma conexão central com a Internet.</span><span class="sxs-lookup"><span data-stu-id="ddcc3-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="ddcc3-109">Use estes artigos para entender as principais diferenças e modificar seus dispositivos de borda, computadores clientes e rede local para obter o melhor desempenho para seus usuários locais.</span><span class="sxs-lookup"><span data-stu-id="ddcc3-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="ddcc3-110">Plano</span><span class="sxs-lookup"><span data-stu-id="ddcc3-110">Plan</span></span>

<span data-ttu-id="ddcc3-111">Na fase de planejamento da implementação de sua rede:</span><span class="sxs-lookup"><span data-stu-id="ddcc3-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="ddcc3-112">Entender como funciona a rede Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddcc3-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="ddcc3-113">Avaliar sua conectividade de rede atual</span><span class="sxs-lookup"><span data-stu-id="ddcc3-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="ddcc3-114">Determine se o ExpressRoute é ideal para a sua organização</span><span class="sxs-lookup"><span data-stu-id="ddcc3-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="ddcc3-115">Planejar seus dispositivos de rede</span><span class="sxs-lookup"><span data-stu-id="ddcc3-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="ddcc3-116">Configurar sua rede para migração</span><span class="sxs-lookup"><span data-stu-id="ddcc3-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="ddcc3-117">Implantar</span><span class="sxs-lookup"><span data-stu-id="ddcc3-117">Deploy</span></span>

<span data-ttu-id="ddcc3-118">Na fase de implantação de sua implementação de rede:</span><span class="sxs-lookup"><span data-stu-id="ddcc3-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="ddcc3-119">Garantir que sua rede corporativa seja otimizada para conectividade Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddcc3-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="ddcc3-120">Adicionar os domínios DNS para sua organização</span><span class="sxs-lookup"><span data-stu-id="ddcc3-120">Add the DNS domains for your organization</span></span>](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [<span data-ttu-id="ddcc3-121">Otimize sua conectividade para os pontos de extremidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddcc3-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="ddcc3-122">Otimizar a conectividade para funcionários remotos</span><span class="sxs-lookup"><span data-stu-id="ddcc3-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="ddcc3-123">Se necessário, [Configure o ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="ddcc3-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="ddcc3-124">Gerenciar</span><span class="sxs-lookup"><span data-stu-id="ddcc3-124">Manage</span></span>

<span data-ttu-id="ddcc3-125">Na fase de gerenciamento da implementação de sua rede:</span><span class="sxs-lookup"><span data-stu-id="ddcc3-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="ddcc3-126">Verifique se os dispositivos de rede estão usando os pontos de extremidade mais recentes do Office 365</span><span class="sxs-lookup"><span data-stu-id="ddcc3-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="ddcc3-127">Monitorar e ajustar o desempenho da rede</span><span class="sxs-lookup"><span data-stu-id="ddcc3-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="ddcc3-128">Monitorar suas conexões ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="ddcc3-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="ddcc3-129">Fornecedores de equipamento de rede</span><span class="sxs-lookup"><span data-stu-id="ddcc3-129">Network equipment vendors</span></span>

<span data-ttu-id="ddcc3-130">Se você for um fornecedor de equipamento de rede, ingresse no programa de parceria de rede [365 da Microsoft](microsoft-365-networking-partner-program.md).</span><span class="sxs-lookup"><span data-stu-id="ddcc3-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="ddcc3-131">Registre-se no programa para criar os princípios de conectividade de rede do Microsoft 365 em seus produtos e soluções.</span><span class="sxs-lookup"><span data-stu-id="ddcc3-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="ddcc3-132">Como a contoso realizou a rede para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddcc3-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="ddcc3-133">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [otimizou seus dispositivos de rede e conexões com a internet](contoso-networking.md) para os serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ddcc3-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![A Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="ddcc3-135">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ddcc3-135">Next step</span></span>

<span data-ttu-id="ddcc3-136">Inicie o planejamento de rede com a [visão geral da conectividade de rede do Microsoft 365](microsoft-365-networking-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ddcc3-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>
