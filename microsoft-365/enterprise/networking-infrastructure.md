---
title: 'Fase 1: Infraestrutura de rede para o Microsoft 365 Enterprise'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura de rede do Microsoft 365 Enterprise.
ms.openlocfilehash: 341e5530b159d4ba78b94001d92427e36224ab04
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631472"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="7b9f9-103">Fase 1: Infraestrutura de rede para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7b9f9-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![Fase 1: Rede](../media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="7b9f9-105">O Microsoft 365 Enterprise inclui o Office 365, o Microsoft Intune e vários serviços de identidade e segurança do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-105">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="7b9f9-106">Todos esses serviços baseados em nuvem dependem da segurança, desempenho e confiabilidade das conexões de dispositivos clientes pela Internet ou circuitos dedicados.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-106">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="7b9f9-107">Para hospedar esses serviços e disponibilizá-los para clientes em todo o mundo, a Microsoft desenvolveu uma infraestrutura de rede que enfatiza o desempenho e a integração.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-107">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="7b9f9-p102">Nesta fase, você percorre as principais considerações para criar uma conexão de alto desempenho com os serviços em nuvem do Microsoft 365 Enterprise. Para uma visão geral, consulte os [Princípios de rede do Microsoft 365.](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="7b9f9-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Microsoft 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="7b9f9-110">Se você já tem uma infraestrutura de rede implantada, consulte os [critérios de saída](networking-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-110">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="7b9f9-111">Planejar e implantar a infraestrutura de rede do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7b9f9-111">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="7b9f9-112">Siga as etapas a seguir para criar sua infraestrutura de rede de acordo com os requisitos e recursos do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-112">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Etapa 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="7b9f9-114">Preparar sua rede para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b9f9-114">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![Etapa 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="7b9f9-116">Configurar conexões locais com a Internet para cada escritório</span><span class="sxs-lookup"><span data-stu-id="7b9f9-116">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![Etapa 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="7b9f9-118">Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="7b9f9-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![Etapa 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="7b9f9-120">Configurar o bypass de tráfego</span><span class="sxs-lookup"><span data-stu-id="7b9f9-120">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![Etapa 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="7b9f9-122">Otimizar o desempenho do cliente e do serviço</span><span class="sxs-lookup"><span data-stu-id="7b9f9-122">Optimize client and service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="7b9f9-123">Após concluir essas etapas, consulte os [critérios de saída](networking-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-123">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="7b9f9-124">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7b9f9-124">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7b9f9-125">Dê uma olhada na Microsoft e saiba como a empresa [otimizou a rede da Microsoft para serviços de nuvem](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span><span class="sxs-lookup"><span data-stu-id="7b9f9-125">Peek inside Microsoft and learn how the company [optimized the Microsoft network for cloud services](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="7b9f9-126">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7b9f9-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7b9f9-127">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [otimizou seus dispositivos de rede e conexões com a internet](contoso-networking.md) para os serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-127">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![A Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="7b9f9-129">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7b9f9-129">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="7b9f9-131">Preparar sua rede para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b9f9-131">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

