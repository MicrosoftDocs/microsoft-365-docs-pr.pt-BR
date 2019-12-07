---
title: Diretrizes de Acessibilidade para Conteúdo da Web 2.1
description: A Microsoft publica os relatórios WCAG 2.1 AA que refletem o produto ou serviço completo, ou partes do produto que podem ser instaladas separadamente.
keywords: Microsoft 365, conformidade, ofertas
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: a1887bd2b6c04836ebb11d224fcc59debcd88e55
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859441"
---
# <a name="web-content-accessibility-guidelines-21"></a><span data-ttu-id="d340a-104">Diretrizes de Acessibilidade para Conteúdo da Web 2.1</span><span class="sxs-lookup"><span data-stu-id="d340a-104">Web Content Accessibility Guidelines 2.1</span></span>

## <a name="about-wcag-21"></a><span data-ttu-id="d340a-105">Sobre as WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="d340a-105">About WCAG 2.1</span></span>

<span data-ttu-id="d340a-106">As WCAG 2.1 fornecem uma estrutura para o desenvolvimento de conteúdo da Web que melhora a acessibilidade para pessoas com deficiência, além de usuários de dispositivos com recursos gráficos limitados.</span><span class="sxs-lookup"><span data-stu-id="d340a-106">WCAG 2.1 provides a framework for developing web content that improves accessibility for people with disabilities, in addition to users of devices with limited graphical abilities.</span></span> <span data-ttu-id="d340a-107">As WCAG 2.0 foram publicadas em 2008 pelo World Wide Web Consortium (W3C), uma organização internacional dedicada à criação de padrões da Web e atualizadas para as WCAG 2.1 em junho de 2018.</span><span class="sxs-lookup"><span data-stu-id="d340a-107">WCAG 2.0 was published in 2008 by the World Wide Web Consortium (W3C), an international organization dedicated to creating web standards, and updated to WCAG 2.1 in June 2018.</span></span> <span data-ttu-id="d340a-108">Em 2012, as WCAG 2.0 também foram publicadas pela ISO (Organização Internacional de Normalização) como ISO/IEC 40500:2012.</span><span class="sxs-lookup"><span data-stu-id="d340a-108">In 2012, WCAG 2.0 was also published by the International Organization for Standardization (ISO) as ISO/IEC 40500:2012.</span></span>  
  
<span data-ttu-id="d340a-109">O conteúdo em conformidade com as WCAG 2.1 também está em conformidade com as WCAG 2.0.</span><span class="sxs-lookup"><span data-stu-id="d340a-109">Content that conforms to WCAG 2.1 also conforms to WCAG 2.0.</span></span> <span data-ttu-id="d340a-110">Para políticas que exigem conformidade com as WCAG 2.0, as WCAG 2.1 podem fornecer um meio alternativo de conformidade.</span><span class="sxs-lookup"><span data-stu-id="d340a-110">For policies requiring conformance to WCAG 2.0, WCAG 2.1 can provide an alternate means of conformance.</span></span>  
  
<span data-ttu-id="d340a-111">Os requisitos de conformidade de cada diretriz são medidos em três níveis: A, AA e AAA.</span><span class="sxs-lookup"><span data-stu-id="d340a-111">Conformance requirements for each guideline are measured in three levels: A, AA, and AAA.</span></span> <span data-ttu-id="d340a-112">Como a Microsoft é um importante provedor de serviços de software e nuvem para Estados e governos em todo o mundo, ela está comprometida em seguir todos os [padrões internacionais e controles de conformidade](https://go.microsoft.com/fwlink/p/?linkid=2052226) relevantes.</span><span class="sxs-lookup"><span data-stu-id="d340a-112">Because Microsoft is a major software and cloud-services provider to states and governments around the world, it is committed to complying with all relevant [international standards and compliance controls](https://go.microsoft.com/fwlink/p/?linkid=2052226).</span></span> <span data-ttu-id="d340a-113">Ao cumprir esses amplos padrões de acessibilidade, a Microsoft garante que todos os clientes, dentro e fora do governo, possam usar os serviços e produtos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d340a-113">By adhering to these wide-ranging accessibility standards, Microsoft ensures that all customers — both inside and outside of government — can use Microsoft services and products.</span></span>  

## <a name="microsoft-and-wcag-21"></a><span data-ttu-id="d340a-114">Microsoft e WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="d340a-114">Microsoft and WCAG 2.1</span></span>

<span data-ttu-id="d340a-115">A adesão da Microsoft ao padrão das WCAG 2.1 (ISO/IEC 40500) indica seu compromisso de tornar a tecnologia e os dados acessíveis a todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="d340a-115">Microsoft’s adherence to the WCAG 2.1 (ISO/IEC 40500) standard points to its commitment to making technology and data accessible for all customers.</span></span> <span data-ttu-id="d340a-116">As WCAG 2.1 (ISO/IEC 40500) são os requisitos de acessibilidade internacional que complementam a EN 301 549 (Europa) e a Seção 508 (EUA).</span><span class="sxs-lookup"><span data-stu-id="d340a-116">WCAG 2.1 (ISO/IEC 40500) is the international accessibility requirement that complements EN 301 549 (Europe) and Section 508 (U.S.).</span></span>  
  
<span data-ttu-id="d340a-117">A Microsoft publica os relatórios WCAG 2.1 que refletem o produto ou serviço completo.</span><span class="sxs-lookup"><span data-stu-id="d340a-117">Microsoft publishes WCAG 2.1 reports that reflect the complete product or service.</span></span> <span data-ttu-id="d340a-118">Geralmente, ela não cria relatórios para componentes ou recursos individuais.</span><span class="sxs-lookup"><span data-stu-id="d340a-118">It generally does not create reports for individual features or components.</span></span> <span data-ttu-id="d340a-119">Às vezes, a Microsoft pode lançar um novo componente para um produto existente ou uma nova versão de um componente existente, que os usuários podem optar por instalar separadamente, e a Microsoft também pode publicar um relatório WCAG 2.1 para esse componente.</span><span class="sxs-lookup"><span data-stu-id="d340a-119">Sometimes, Microsoft might release a new component for an existing product, or a new version of an existing component, which users can choose to install separately, and Microsoft might also publish a WCAG 2.1 report for that component.</span></span>  
  
[<span data-ttu-id="d340a-120">Baixe os padrões de acessibilidade WCAG 2.1 (ISO/IEC 40500)</span><span class="sxs-lookup"><span data-stu-id="d340a-120">Download the WCAG 2.1 (ISO/IEC 40500) accessibility standards</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2052226)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="d340a-121">Serviços de nuvem no escopo da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d340a-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="d340a-122">Azure e Azure Government</span><span class="sxs-lookup"><span data-stu-id="d340a-122">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="d340a-123">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="d340a-123">Azure DevOps Services</span></span>
- <span data-ttu-id="d340a-124">Dynamics 365 e Dynamics 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="d340a-124">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="d340a-125">Intune</span><span class="sxs-lookup"><span data-stu-id="d340a-125">Intune</span></span>
- <span data-ttu-id="d340a-126">Office 365 e Office 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="d340a-126">Office 365 and Office 365 U.S. Government</span></span>
- <span data-ttu-id="d340a-127">Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="d340a-127">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="d340a-128">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d340a-128">Windows Server 2016</span></span>

## <a name="microsoft-accessibility-conformance-reports"></a><span data-ttu-id="d340a-129">Relatórios de Conformidade de Acessibilidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d340a-129">Microsoft accessibility conformance reports</span></span>

<span data-ttu-id="d340a-130">Encontre relatórios das WCAG para todos os nossos produtos e serviços.</span><span class="sxs-lookup"><span data-stu-id="d340a-130">Find WCAG reports for all our products and services.</span></span>

[<span data-ttu-id="d340a-131">**Saiba mais**</span><span class="sxs-lookup"><span data-stu-id="d340a-131">**Learn more**</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050974)

## <a name="resources"></a><span data-ttu-id="d340a-132">Recursos</span><span class="sxs-lookup"><span data-stu-id="d340a-132">Resources</span></span>

<span data-ttu-id="d340a-133">[Site de acessibilidade da Microsoft: obtenha informações sobre o uso dos recursos de acessibilidade e explore as maneiras pelas quais a Microsoft inova para ajudar todas as pessoas a fazer mais.</span><span class="sxs-lookup"><span data-stu-id="d340a-133">[Microsoft accessibility site — Get information on using accessibility features and explore the ways Microsoft innovates to help everyone achieve more.</span></span>

[<span data-ttu-id="d340a-134">Centro de Acessibilidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="d340a-134">Office 365 Accessibility Center</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051801)
    - <span data-ttu-id="d340a-135">Recursos do Office 365 para pessoas com deficiências.</span><span class="sxs-lookup"><span data-stu-id="d340a-135">Office 365 resources for people with disabilities.</span></span>

[<span data-ttu-id="d340a-136">Enterprise Disability Answer Desk</span><span class="sxs-lookup"><span data-stu-id="d340a-136">Enterprise Disability Answer Desk</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050890)
    - <span data-ttu-id="d340a-137">Suporte dedicado para clientes corporativos com questões de acessibilidade sobre nossos produtos e serviços ou conformidade.</span><span class="sxs-lookup"><span data-stu-id="d340a-137">Dedicated support for enterprise customers with accessibility questions about our products and services or compliance.</span></span>

[<span data-ttu-id="d340a-138">Conformidade com o Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="d340a-138">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="d340a-139">Baixar informações de oferta</span><span class="sxs-lookup"><span data-stu-id="d340a-139">Download the offering backgrounder</span></span>

<span data-ttu-id="d340a-140">Precisa do documento informativo desta oferta?</span><span class="sxs-lookup"><span data-stu-id="d340a-140">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="d340a-141">Baixe o [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span><span class="sxs-lookup"><span data-stu-id="d340a-141">Download the [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span></span>
