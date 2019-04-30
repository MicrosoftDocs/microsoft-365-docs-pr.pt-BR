---
title: Critérios de saída da infraestrutura de proteção de informações
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Examinar os critérios da infraestrutura e dos serviços com base na proteção de informações a fim de garantir que sua configuração atenda aos requisitos do Microsoft 365 Enterprise.
ms.openlocfilehash: 9c74a3994a1a404583326f65f1cec579fccbe659
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400035"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="58f11-103">Critérios de saída da infraestrutura de proteção de informações</span><span class="sxs-lookup"><span data-stu-id="58f11-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="58f11-104">Verifique se a sua infraestrutura de proteção de informações atende aos seguintes critérios necessários e que você considerou aqueles que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="58f11-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="58f11-105">Obrigatório: os níveis de segurança e proteção de informações foram definidos em para a sua organização</span><span class="sxs-lookup"><span data-stu-id="58f11-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="58f11-p101">Você planejou e determinou os níveis de segurança necessários para a sua organização. Esses níveis definem o patamar mínimo de segurança e outros níveis para informações cuja confidencialidade aumenta gradualmente, assim como a segurança de dados exigida para cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="58f11-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="58f11-108">No mínimo, você está usando três níveis de segurança:</span><span class="sxs-lookup"><span data-stu-id="58f11-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="58f11-109">Linha de base</span><span class="sxs-lookup"><span data-stu-id="58f11-109">Baseline</span></span>
- <span data-ttu-id="58f11-110">Confidencial</span><span class="sxs-lookup"><span data-stu-id="58f11-110">Sensitive</span></span>
- <span data-ttu-id="58f11-111">Altamente controlada</span><span class="sxs-lookup"><span data-stu-id="58f11-111">Highly regulated</span></span>

<span data-ttu-id="58f11-112">Se necessário, a [Etapa 1](infoprotect-define-sec-infoprotect-levels.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="58f11-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="58f11-113">Obrigatório: configuração de segurança aprimorada para Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="58f11-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="58f11-114">As seguintes configurações foram habilitadas para a [segurança aprimorada do Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="58f11-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="58f11-115">Políticas de gerenciamento de ameaças na Central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58f11-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="58f11-116">Configurações adicionais para todos os locatários do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="58f11-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="58f11-117">Políticas de compartilhamento de todos os locatários no centro de administração do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="58f11-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="58f11-118">Configurações do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="58f11-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="58f11-119">Você também [habilitou a Proteção Avançada contra Ameaças (ATP) do Office 365 para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="58f11-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="58f11-120">Se necessário, a [Etapa 3](infoprotect-configure-increased-security-office-365.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="58f11-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="58f11-121">Opcional: a classificação está configurada em seu ambiente</span><span class="sxs-lookup"><span data-stu-id="58f11-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="58f11-122">Você trabalhou com o seu departamento jurídico e de conformidade para desenvolver uma classificação apropriada e um esquema de identificação de governança de dados e políticas de segurança para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="58f11-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="58f11-123">Essa políticas correspondem a configuração e implantação de:</span><span class="sxs-lookup"><span data-stu-id="58f11-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="58f11-124">Tipos de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="58f11-124">Sensitive data types</span></span>
- <span data-ttu-id="58f11-125">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="58f11-125">Retention labels</span></span>
- <span data-ttu-id="58f11-126">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="58f11-126">Sensitivity labels</span></span>
- <span data-ttu-id="58f11-127">Rótulos da Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="58f11-127">Azure Information Protection labels</span></span>

<span data-ttu-id="58f11-128">Se necessário, a [Etapa 2](infoprotect-configure-classification.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="58f11-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="58f11-129">Opcional: Proteção de Informações do Windows implementada em todo o seu ambiente</span><span class="sxs-lookup"><span data-stu-id="58f11-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="58f11-130">Seus dispositivos Windows 10 Enterprise registrados têm uma política do Intune implementada e aplicada que define:</span><span class="sxs-lookup"><span data-stu-id="58f11-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="58f11-131">Quais apps para proteger.</span><span class="sxs-lookup"><span data-stu-id="58f11-131">Which apps to protect.</span></span>
- <span data-ttu-id="58f11-132">O nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="58f11-132">The level of protection.</span></span>
- <span data-ttu-id="58f11-133">Onde a proteção se estende.</span><span class="sxs-lookup"><span data-stu-id="58f11-133">Where the protection extends.</span></span>

<span data-ttu-id="58f11-134">Se necessário, a [Etapa 4](infoprotect-deploy-windows-information-protection.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="58f11-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="58f11-135">Opcional: o DLP (Data Loss Prevention) do Office 365 está implantado</span><span class="sxs-lookup"><span data-stu-id="58f11-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="58f11-136">Você analisou, testou e depois lançou o conjunto de políticas de DLP - com locais e regras com condições e ações - que sua organização exige para proteger os clientes e outros tipos de dados privados e aderir aos regulamentos e requisitos do setor e regionais.</span><span class="sxs-lookup"><span data-stu-id="58f11-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="58f11-137">Sua equipe de conformidade e segurança de dados está usando o Office 365 Security & amp; Painel de conformidade para monitorar incidentes de DLP.</span><span class="sxs-lookup"><span data-stu-id="58f11-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="58f11-138">Se necessário, a [Etapa 5](infoprotect-data-loss-prevention.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="58f11-138">If needed, [Step 4](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step6"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="58f11-139">Opcional: configurar o gerenciamento de acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="58f11-139">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="58f11-140">Você usou as informações do tópico [Configurar gerenciamento de acesso privilegiado do Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar uma ou mais políticas de acesso privilegiado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="58f11-140">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="58f11-141">Você configurou essas políticas e o acesso just-in-time está habilitado para acessar dados confidenciais ou configurações críticas.</span><span class="sxs-lookup"><span data-stu-id="58f11-141">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="58f11-142">Se necessária, a [Etapa 6](infoprotect-configure-privileged-access-management.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="58f11-142">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="58f11-143">Resultados e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="58f11-143">Results and next steps</span></span>

<span data-ttu-id="58f11-144">Sua infra-estrutura de proteção de informações para o Microsoft 365 Enterprise usa níveis de segurança definidos, maior segurança para o Office 365, classificação usando rótulos e tipos de dados confidenciais, Proteção de Informações do Windows, Prevenção de Perda de Dados e gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="58f11-144">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, and privileged access management.</span></span>

<span data-ttu-id="58f11-145">Se você está seguindo a implantação de ponta a ponta do Microsoft 365 Enterprise, você está pronto para fazer suas [cargas de trabalho e seus cenários](deploy-workloads.md) aproveitarem todos os recursos e configurações de sua infraestrutura de base.</span><span class="sxs-lookup"><span data-stu-id="58f11-145">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
