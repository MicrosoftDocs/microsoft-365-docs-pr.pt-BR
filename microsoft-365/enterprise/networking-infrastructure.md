---
title: 'Fase 1: Infraestrutura de rede para o Microsoft 365 Enterprise'
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
description: Etapas para implantar a infraestrutura de rede do Microsoft 365 Enterprise.
ms.openlocfilehash: d575d8c3156ac1fc1a8a2bca96c875d4587ebf05
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864940"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="6d4f6-103">Fase 1: Infraestrutura de rede para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6d4f6-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="6d4f6-p101">O Microsoft 365 Enterprise inclui o Office 365 e o Windows Intune como parte do Enterprise Management + Security (EMS). Esses dois serviços baseados na nuvem dependem da segurança, do desempenho e da confiabilidade das conexões dos dispositivos-cliente com a Internet ou por circuitos dedicados. Para hospedar esses serviços e disponibilizá-los para clientes de todo o mundo, a Microsoft desenvolveu uma infraestrutura de rede que enfatiza a integração e o desempenho.</span><span class="sxs-lookup"><span data-stu-id="6d4f6-p101">Microsoft 365 Enterprise includes Office 365 and Windows Intune as part of Enterprise Management + Security (EMS). Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits. To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="6d4f6-p102">Nesta fase, você vai examinar as principais considerações para criar uma conexão eficaz com os serviços de nuvem do Microsoft 365 Enterprise. Para obter uma visão geral, consulte os [princípios de rede do Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="6d4f6-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="6d4f6-109">Se você já tem uma infraestrutura de rede implantada, consulte os [critérios de saída](networking-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6d4f6-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="6d4f6-110">Planejar e implantar a infraestrutura de rede do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6d4f6-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="6d4f6-111">Siga as etapas a seguir para criar sua infraestrutura de rede de acordo com os requisitos e recursos do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6d4f6-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="6d4f6-112">Preparar sua rede para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d4f6-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="6d4f6-113">Configurar conexões locais com a Internet para cada escritório</span><span class="sxs-lookup"><span data-stu-id="6d4f6-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="6d4f6-114">Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="6d4f6-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="6d4f6-115">Configurar o bypass de tráfego</span><span class="sxs-lookup"><span data-stu-id="6d4f6-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="6d4f6-116">Otimizar o desempenho do serviço entre o cliente e o Office 365</span><span class="sxs-lookup"><span data-stu-id="6d4f6-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="6d4f6-117">Após concluir essas etapas, consulte os [critérios de saída](networking-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6d4f6-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="6d4f6-118">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6d4f6-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6d4f6-119">Para conhecer a Microsoft em detalhes e saber como a empresa se preparou e otimizou a rede para os serviços de nuvem do Office 365, confira o artigo [Otimizar o desempenho da rede para o Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span><span class="sxs-lookup"><span data-stu-id="6d4f6-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="6d4f6-120">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6d4f6-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6d4f6-121">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [otimizou a rede](contoso-networking.md) dos serviços em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d4f6-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="6d4f6-122">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6d4f6-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="6d4f6-123">Preparar sua rede para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d4f6-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

