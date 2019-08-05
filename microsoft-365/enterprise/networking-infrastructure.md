---
title: 'Fase 1: Infraestrutura de rede para o Microsoft 365 Enterprise'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura de rede do Microsoft 365 Enterprise.
ms.openlocfilehash: 4c1ea87e243d72920a3a56df270fab33bd722834
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074311"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="56f44-103">Fase 1: Infraestrutura de rede para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="56f44-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="56f44-104">O Microsoft 365 Enterprise inclui o Office 365 e o Microsoft Intune como parte do EMS (Gerenciamento + Segurança do Enterprise).</span><span class="sxs-lookup"><span data-stu-id="56f44-104">Microsoft 365 Enterprise includes Office 365 and Microsoft Intune as part of Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="56f44-105">Ambos os serviços baseados em nuvem dependem da segurança, desempenho e confiabilidade das conexões de dispositivos clientes pela Internet ou circuitos dedicados.</span><span class="sxs-lookup"><span data-stu-id="56f44-105">Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="56f44-106">Para hospedar esses serviços e disponibilizá-los para clientes em todo o mundo, a Microsoft desenvolveu uma infraestrutura de rede que enfatiza o desempenho e a integração.</span><span class="sxs-lookup"><span data-stu-id="56f44-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="56f44-p102">Nesta fase, você vai examinar as principais considerações para criar uma conexão eficaz com os serviços de nuvem do Microsoft 365 Enterprise. Para obter uma visão geral, consulte os [princípios de rede do Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="56f44-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="56f44-109">Se você já tem uma infraestrutura de rede implantada, consulte os [critérios de saída](networking-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="56f44-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="56f44-110">Planejar e implantar a infraestrutura de rede do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="56f44-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="56f44-111">Siga as etapas a seguir para criar sua infraestrutura de rede de acordo com os requisitos e recursos do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="56f44-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="56f44-112">Preparar sua rede para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56f44-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="56f44-113">Configurar conexões locais com a Internet para cada escritório</span><span class="sxs-lookup"><span data-stu-id="56f44-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="56f44-114">Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="56f44-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="56f44-115">Configurar o bypass de tráfego</span><span class="sxs-lookup"><span data-stu-id="56f44-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="56f44-116">Otimizar o desempenho do serviço entre o cliente e o Office 365</span><span class="sxs-lookup"><span data-stu-id="56f44-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="56f44-117">Após concluir essas etapas, consulte os [critérios de saída](networking-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="56f44-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="56f44-118">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="56f44-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="56f44-119">Dê uma olhada na Microsoft e saiba como a empresa [otimizou a rede da Microsoft para serviços de nuvem](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span><span class="sxs-lookup"><span data-stu-id="56f44-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="56f44-120">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="56f44-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="56f44-121">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [otimizou seus dispositivos de rede e a conexão à internet](contoso-networking.md) para os serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56f44-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="56f44-122">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="56f44-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="56f44-123">Preparar sua rede para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56f44-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

