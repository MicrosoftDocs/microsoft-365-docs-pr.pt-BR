---
title: 'Fase 6: proteção de informações'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura de proteção de informações do Microsoft 365 Enterprise.
ms.openlocfilehash: a0d2c485b05e0969fe45cfd79c86e4e7dcb1d5ff
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399995"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="edb22-103">Fase 6: proteção de informações</span><span class="sxs-lookup"><span data-stu-id="edb22-103">Phase 6: Information protection</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="edb22-p101">A proteção de informações é um conjunto de políticas e tecnologias que definem como transmitir, armazenar e processar informações confidenciais. Na fase 6, você examinará as configurações e os recursos de proteção de informações do Microsoft 365 Enterprise que lhe ajudam a proteger os dados dos cenários e das cargas de trabalho na nuvem.</span><span class="sxs-lookup"><span data-stu-id="edb22-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="edb22-106">Se você já tiver implantado a proteção de informações, consulte os [critérios de saída](infoprotect-exit-criteria.md) para esta fase para garantir que eles atendem às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="edb22-106">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="edb22-107">Planejar e implantar a infraestrutura de proteção de informações do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="edb22-107">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="edb22-p102">É importante trabalhar em conjunto com o departamento jurídico e de conformidade para determinar se sua organização deve atender a padrões de conformidade como HIPAA, CJIS ou RGPD. Você deve trabalhar também com seu grupo de segurança para determinar os objetivos da proteção de informações para sua organização e para os departamentos ou grupos que precisam de segurança adicional.</span><span class="sxs-lookup"><span data-stu-id="edb22-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="edb22-110">Em seguida, siga estas etapas para criar a proteção de informações para o Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="edb22-110">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="edb22-111">Definir níveis de segurança e proteção de informações</span><span class="sxs-lookup"><span data-stu-id="edb22-111">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="edb22-112">Configurar classificações de ambiente</span><span class="sxs-lookup"><span data-stu-id="edb22-112">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="edb22-113">Configurar a segurança aprimorada para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="edb22-113">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![](./media/stepnumbers/Step4.png)|<span data-ttu-id="edb22-114">[Configurar Proteção de Informações do Windows](infoprotect-deploy-windows-information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="edb22-114">[](infoprotect-deploy-windows-information-protection.md)Configure Azure Information Protection</span></span>|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="edb22-115">Configurar a Prevenção de Perda de Dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="edb22-115">Office 365 Data Loss Prevention (DLP)</span></span>](infoprotect-data-loss-prevention.md)|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="edb22-116">Configurar o gerenciamento de acesso privilegiado do Office 365</span><span class="sxs-lookup"><span data-stu-id="edb22-116">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


<span data-ttu-id="edb22-117">Após concluir essas etapas, consulte os [critérios de saída](infoprotect-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="edb22-117">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="edb22-118">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="edb22-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="edb22-119">Saiba como os especialistas de TI da Microsoft usam os recursos de proteção de informações do Microsoft 356 Enterprise para proteger as informações e se defender contra ataques cibernéticos:</span><span class="sxs-lookup"><span data-stu-id="edb22-119">Learn how IT experts at Microsoft use the information protection capabilities of Microsoft 356 Enterprise to protect information and defend against cyber attacks:</span></span>

- [<span data-ttu-id="edb22-120">Protegendo arquivos na nuvem com a Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="edb22-120">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="edb22-121">A Microsoft usa inteligência contra ameaças para proteger, detectar e responder a ameaças</span><span class="sxs-lookup"><span data-stu-id="edb22-121">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="edb22-122">A Microsoft impede tentativas de phishing com o Office 365</span><span class="sxs-lookup"><span data-stu-id="edb22-122">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="edb22-123">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="edb22-123">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="edb22-124">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implementou a proteção de informações](contoso-info-protect.md) com os serviços em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="edb22-124">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="edb22-125">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="edb22-125">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="edb22-126">Definir níveis de segurança e proteção de informações</span><span class="sxs-lookup"><span data-stu-id="edb22-126">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

