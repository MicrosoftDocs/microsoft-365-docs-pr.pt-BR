---
title: Critérios de saída da infraestrutura de proteção de informações
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Examinar os critérios da infraestrutura e dos serviços com base na proteção de informações a fim de garantir que sua configuração atenda aos requisitos do Microsoft 365 Enterprise.
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283688"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="dcdaf-103">Critérios de saída da infraestrutura de proteção de informações</span><span class="sxs-lookup"><span data-stu-id="dcdaf-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="dcdaf-104">Verifique se a sua infraestrutura de proteção de informações atende aos seguintes critérios necessários e que você considerou aqueles que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="dcdaf-105">Obrigatório: os níveis de segurança e proteção de informações foram definidos em para a sua organização</span><span class="sxs-lookup"><span data-stu-id="dcdaf-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="dcdaf-p101">Você planejou e determinou os níveis de segurança necessários para a sua organização. Esses níveis definem o patamar mínimo de segurança e outros níveis para informações cuja confidencialidade aumenta gradualmente, assim como a segurança de dados exigida para cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="dcdaf-108">No mínimo, você está usando três níveis de segurança:</span><span class="sxs-lookup"><span data-stu-id="dcdaf-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="dcdaf-109">Linha de base</span><span class="sxs-lookup"><span data-stu-id="dcdaf-109">Baseline</span></span>
- <span data-ttu-id="dcdaf-110">Confidencial</span><span class="sxs-lookup"><span data-stu-id="dcdaf-110">Sensitive</span></span>
- <span data-ttu-id="dcdaf-111">Altamente controlada</span><span class="sxs-lookup"><span data-stu-id="dcdaf-111">Highly regulated</span></span>

<span data-ttu-id="dcdaf-112">Se necessário, a [Etapa 1](infoprotect-define-sec-infoprotect-levels.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="dcdaf-113">Obrigatório: configuração de segurança aprimorada para Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="dcdaf-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="dcdaf-114">As seguintes configurações foram habilitadas para a [segurança aprimorada do Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="dcdaf-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="dcdaf-115">Políticas de gerenciamento de ameaças na Central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dcdaf-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="dcdaf-116">Configurações adicionais para todos os locatários do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dcdaf-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="dcdaf-117">Políticas de compartilhamento de todos os locatários no SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="dcdaf-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="dcdaf-118">Configurações do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="dcdaf-118">CORS support in Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="dcdaf-119">Você também [habilitou a Proteção Avançada contra Ameaças (ATP) do Office 365 para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/pt-BR/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="dcdaf-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/pt-BR/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="dcdaf-120">Se necessário, a [Etapa 3](infoprotect-configure-increased-security-office-365.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="dcdaf-121">Opcional: a classificação está configurada em seu ambiente</span><span class="sxs-lookup"><span data-stu-id="dcdaf-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="dcdaf-122">Você trabalhou com o seu departamento jurídico e de conformidade para desenvolver uma classificação apropriada e um esquema de identificação de governança de dados e políticas de segurança para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span> 

<span data-ttu-id="dcdaf-123">Essa políticas correspondem a configuração e implantação de:</span><span class="sxs-lookup"><span data-stu-id="dcdaf-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="dcdaf-124">Tipos de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="dcdaf-124">Sensitive data types</span></span>
- <span data-ttu-id="dcdaf-125">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="dcdaf-125">Retention labels</span></span>
- <span data-ttu-id="dcdaf-126">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="dcdaf-126">Sensitivity labels</span></span>
- <span data-ttu-id="dcdaf-127">Rótulos da Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="dcdaf-127">Azure Information Protection labels</span></span>

<span data-ttu-id="dcdaf-128">Se necessário, a [Etapa 2](infoprotect-configure-classification.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="dcdaf-129">Opcional: configurar o gerenciamento de acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="dcdaf-129">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="dcdaf-130">Você usou as informações do tópico [Configurar gerenciamento de acesso privilegiado do Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar uma ou mais políticas de acesso privilegiado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-130">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="dcdaf-131">Você configurou essas políticas e o acesso just-in-time está habilitado para acessar dados confidenciais ou configurações críticas.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-131">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="dcdaf-132">Se necessário, a [Etapa 4](infoprotect-configure-privileged-access-management.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-132">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="dcdaf-133">Resultados e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dcdaf-133">Validation and next steps</span></span>

<span data-ttu-id="dcdaf-134">Sua infraestrutura de proteção de informações para o Microsoft 365 Enterprise usa níveis de segurança definidos, segurança aprimorada para o Office 365, classificação usando tipos de dados e rótulos confidenciais e gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-134">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, and privileged access management.</span></span>

<span data-ttu-id="dcdaf-135">Se você está seguindo a implantação de ponta a ponta do Microsoft 365 Enterprise, você está pronto para fazer suas [cargas de trabalho e seus cenários](deploy-workloads.md) aproveitarem todos os recursos e configurações de sua infraestrutura de base.</span><span class="sxs-lookup"><span data-stu-id="dcdaf-135">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
