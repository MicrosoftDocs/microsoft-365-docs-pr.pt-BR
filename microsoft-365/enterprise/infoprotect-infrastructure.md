---
title: 'Fase 6: proteção de informações'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura de proteção de informações do Microsoft 365 Enterprise.
ms.openlocfilehash: 418506927885948cd917061d99bb69163b1e44a5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067121"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="487ef-103">Fase 6: proteção de informações</span><span class="sxs-lookup"><span data-stu-id="487ef-103">Phase 6: Information protection</span></span>

![Fase 6: proteção de informações](../media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="487ef-p101">A proteção de informações é um conjunto de políticas e tecnologias que definem como transmitir, armazenar e processar informações confidenciais. Na fase 6, você examinará as configurações e os recursos de proteção de informações do Microsoft 365 Enterprise que lhe ajudam a proteger os dados dos cenários e das cargas de trabalho na nuvem.</span><span class="sxs-lookup"><span data-stu-id="487ef-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="487ef-107">Se você já tiver implantado a proteção de informações, consulte os [critérios de saída](infoprotect-exit-criteria.md) para esta fase para garantir que eles atendem às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="487ef-107">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="487ef-108">Planejar e implantar a infraestrutura de proteção de informações do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="487ef-108">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="487ef-p102">É importante trabalhar em conjunto com o departamento jurídico e de conformidade para determinar se sua organização deve atender a padrões de conformidade como HIPAA, CJIS ou RGPD. Você deve trabalhar também com seu grupo de segurança para determinar os objetivos da proteção de informações para sua organização e para os departamentos ou grupos que precisam de segurança adicional.</span><span class="sxs-lookup"><span data-stu-id="487ef-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="487ef-111">Em seguida, siga estas etapas para criar a proteção de informações para o Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="487ef-111">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Etapa 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="487ef-113">Definir níveis de segurança e proteção de informações</span><span class="sxs-lookup"><span data-stu-id="487ef-113">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![Etapa 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="487ef-115">Configurar classificações de ambiente</span><span class="sxs-lookup"><span data-stu-id="487ef-115">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![Etapa 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="487ef-117">Configurar a segurança aprimorada para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="487ef-117">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![Etapa 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="487ef-119">Configurar Proteção de Informações do Windows</span><span class="sxs-lookup"><span data-stu-id="487ef-119">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![Etapa 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="487ef-121">Configurar a Prevenção de Perda de Dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="487ef-121">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![Etapa 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="487ef-123">Configurar criptografia de email</span><span class="sxs-lookup"><span data-stu-id="487ef-123">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![Etapa 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="487ef-125">Configurar o gerenciamento de acesso privilegiado do Office 365</span><span class="sxs-lookup"><span data-stu-id="487ef-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="487ef-126">Após concluir essas etapas, consulte os [critérios de saída](infoprotect-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="487ef-126">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="487ef-127">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="487ef-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="487ef-128">Saiba como os especialistas de TI da Microsoft usam a [Proteção de Informações do Azure e proteção dos dados.](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9)</span><span class="sxs-lookup"><span data-stu-id="487ef-128">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="487ef-129">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="487ef-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="487ef-130">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implementou a proteção de informações](contoso-info-protect.md) com os serviços em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="487ef-130">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![A Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="487ef-132">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="487ef-132">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="487ef-134">Definir níveis de segurança e proteção de informações</span><span class="sxs-lookup"><span data-stu-id="487ef-134">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

