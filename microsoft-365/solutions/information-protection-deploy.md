---
title: Implantar a proteção de informações para regulamentações de privacidade de dados com o Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Configure a infraestrutura de segurança e serviço para proteger suas informações e aderir às regulamentações de privacidade de dados.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695098"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="cd503-103">Implantar a proteção de informações para regulamentações de privacidade de dados com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd503-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="cd503-104">Esta solução fornece orientações sobre como planejar e proteger dados pessoais armazenados nos serviços do Microsoft 365 e potencialmente sujeitas a regulamentações de privacidade de dados, como a regulamentação geral de proteção de dados da União Européia (RGPD).</span><span class="sxs-lookup"><span data-stu-id="cd503-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="cd503-105">Esta solução se concentra nos recursos de conformidade e proteção de informações da Microsoft, a pontuação de conformidade da Microsoft e as ferramentas de avaliação aplicáveis para ajudá-lo a saber seus dados.</span><span class="sxs-lookup"><span data-stu-id="cd503-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="cd503-106">Também são fornecidas informações adicionais sobre o uso de controles de proteção de identidade, dispositivo e ameaça da Microsoft para suas necessidades de privacidade de dados, bem como para descoberta de incidentes de dados e ferramentas de resposta.</span><span class="sxs-lookup"><span data-stu-id="cd503-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="cd503-107">Organização deste material de orientação</span><span class="sxs-lookup"><span data-stu-id="cd503-107">Organization of this guidance material</span></span>

<span data-ttu-id="cd503-108">Para ajudá-lo a entender as ferramentas do Microsoft 365 disponíveis para identificar, gerenciar, controlar e monitorar dados pessoais sujeitos a uma ou mais normas relacionadas à privacidade, esta orientação é organizada em seções.</span><span class="sxs-lookup"><span data-stu-id="cd503-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![Implantar a proteção de informações para regulamentações de privacidade de dados](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="cd503-110">Cada uma dessas seções corresponde a um artigo separado nesta solução.</span><span class="sxs-lookup"><span data-stu-id="cd503-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="cd503-111">Se você já estiver familiarizado com suas obrigações de privacidade de dados e estiver em execução em um plano existente, convém se concentrar nas diretrizes de prevenção, proteção, retenção e investigação.</span><span class="sxs-lookup"><span data-stu-id="cd503-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="cd503-112">Seguir estas orientações não o fará necessariamente em conformidade com qualquer regulamentação de privacidade de dados, especialmente considerando o número de etapas necessárias que estão fora do contexto dos recursos.</span><span class="sxs-lookup"><span data-stu-id="cd503-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="cd503-113">Você é responsável por garantir sua conformidade e consultar suas equipes jurídicas e de conformidade ou para buscar orientações e conselhos de terceiros especializados em conformidade.</span><span class="sxs-lookup"><span data-stu-id="cd503-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="cd503-114">Plano: avaliar os riscos de privacidade de dados e identificar itens confidenciais</span><span class="sxs-lookup"><span data-stu-id="cd503-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="cd503-115">Avaliar as normas e os riscos de privacidade de dados em que sua organização está sujeita é uma primeira etapa a ser executada antes de começar a implementar melhorias, incluindo as obtidas por meio da configuração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd503-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="cd503-116">Isso pode incluir uma avaliação geral da prontidão ou identificação de tipos de informações confidenciais particulares que estão sujeitos aos controles normativos de que sua organização precisa estar em conformidade, bem como a ocorrência deles no seu ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd503-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="cd503-117">Para obter mais informações, consulte [avaliar riscos de privacidade de dados e identificar itens confidenciais](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="cd503-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="cd503-118">Track: usar a pontuação de conformidade e o gerente de conformidade</span><span class="sxs-lookup"><span data-stu-id="cd503-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="cd503-119">A pontuação de conformidade e o gerente de conformidade oferecem um conjunto integrado de ferramentas disponíveis no portal de confiança do centro de administração de conformidade e serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd503-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="cd503-120">Juntas, essas ferramentas oferecem uma capacidade interna de rastrear e gerenciar ações de melhorias gerais, bem como aquelas relacionadas a diversas regulamentações de privacidade de dados às quais você está sujeito.</span><span class="sxs-lookup"><span data-stu-id="cd503-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="cd503-121">As ferramentas também permitem que você utilize modelos de avaliação internos específicos para cada regulamentação, onde você pode rastrear itens de ação para cada modelo de avaliação selecionado, bem como exibir controles regulatórios específicos e relacioná-los a ações específicas.</span><span class="sxs-lookup"><span data-stu-id="cd503-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="cd503-122">Para saber mais, confira [usar o placar de conformidade e o Gerenciador de conformidade para gerenciar ações de melhoria](information-protection-deploy-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="cd503-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="cd503-123">Impedir: usar a proteção de identidade, dispositivo e ameaça para a regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="cd503-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="cd503-124">A Microsoft 365 fornece vários recursos de proteção de identidade, dispositivo e ameaça que você pode usar para ajudar a cumprir a conformidade normativa da privacidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="cd503-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="cd503-125">Para obter mais informações, consulte [usar identidade, dispositivo e proteção contra ameaças para regulamentação de privacidade de dados](information-protection-deploy-identity-device-threat.md).</span><span class="sxs-lookup"><span data-stu-id="cd503-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="cd503-126">Este artigo descreve brevemente o que os regulamentos de privacidade de dados geralmente chamam nessas áreas e fornece uma lista de soluções do Microsoft 365 relacionadas, com links para mais informações para ajudá-lo a lidar com os requisitos de implementação.</span><span class="sxs-lookup"><span data-stu-id="cd503-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="cd503-127">Proteger informações sujeitas à regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="cd503-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="cd503-128">As regulamentações de privacidade de dados ditam vários controles de proteção de informações pessoais que podem ser empregados em seu ambiente, incluindo mais de 40 proteger os controles de informações entre apenas as quatro regulamentações de privacidade de dados em nosso conjunto de amostra de RGPD, lei de proteção para consumidores da Califórnia (CCPA), HIPAA-alta (lei de privacidade de assistência médica Estados Unidos) e o decreto de proteção</span><span class="sxs-lookup"><span data-stu-id="cd503-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="cd503-129">Para obter mais informações, consulte [proteger informações sujeitas à regulamentação de privacidade de dados em sua organização](information-protection-deploy-protect-information.md).</span><span class="sxs-lookup"><span data-stu-id="cd503-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="cd503-130">Este artigo apresenta os principais esquemas de controle que podem ser usados para atender às necessidades de proteção de informações para privacidade de dados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cd503-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="cd503-131">Reter: controlar informações sujeitas à regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="cd503-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="cd503-132">Os regulamentos de privacidade de dados chamam os controles de governança de informações pessoais que podem ser empregados no seu ambiente, incluindo mais de vinte e quatro controles nas quatro regulamentações de privacidade de dados em nosso conjunto de exemplos de RGPD, CCPA, HIPAA-alta e LGPD.</span><span class="sxs-lookup"><span data-stu-id="cd503-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="cd503-133">Para obter mais informações, consulte [governar informações sujeitas à regulamentação de privacidade de dados em sua organização](information-protection-deploy-govern.md).</span><span class="sxs-lookup"><span data-stu-id="cd503-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="cd503-134">Embora as regulamentações de privacidade de dados possam ser vagas em relação à governança de informações, &mdash; como retenção proposital, exclusão e arquivamento &mdash; Este artigo apresenta os esquemas de controle principal que você pode usar para a privacidade de dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cd503-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="cd503-135">Investigue: monitorar e responder ao assunto para a regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="cd503-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="cd503-136">Há recursos do Microsoft 365 disponíveis para ajudá-lo a monitorar, investigar e responder a incidentes de privacidade de dados em sua organização à medida que você opera recursos relacionados.</span><span class="sxs-lookup"><span data-stu-id="cd503-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="cd503-137">Ter processos, procedimentos e outras documentações para cada um deles pode ser importante para demonstrar a conformidade com órgãos regulamentares.</span><span class="sxs-lookup"><span data-stu-id="cd503-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="cd503-138">Para obter mais informações, consulte [monitorar e responder a incidentes de privacidade de dados em sua organização](information-protection-deploy-monitor-respond.md).</span><span class="sxs-lookup"><span data-stu-id="cd503-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
