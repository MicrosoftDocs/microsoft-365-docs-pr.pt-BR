---
title: Critérios de saída da infraestrutura de proteção de informações
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
description: Examinar os critérios da infraestrutura e dos serviços com base na proteção de informações a fim de garantir que sua configuração atenda aos requisitos do Microsoft 365 Enterprise.
ms.openlocfilehash: 19f4fc4ae93c00e33a2f58d8c23582e6e49cf887
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268216"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="539e4-103">Critérios de saída da infraestrutura de proteção de informações</span><span class="sxs-lookup"><span data-stu-id="539e4-103">Information protection infrastructure exit criteria</span></span>

![Fase 6: Proteção de Informações](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="539e4-105">Verifique se a sua infraestrutura de proteção de informações atende aos seguintes critérios necessários e que você considerou aqueles que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="539e4-105">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="539e4-106">Obrigatório: os níveis de segurança e proteção de informações foram definidos em para a sua organização</span><span class="sxs-lookup"><span data-stu-id="539e4-106">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="539e4-p101">Você planejou e determinou os níveis de segurança necessários para a sua organização. Esses níveis definem o patamar mínimo de segurança e outros níveis para informações cuja confidencialidade aumenta gradualmente, assim como a segurança de dados exigida para cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="539e4-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="539e4-109">No mínimo, você está usando três níveis de segurança:</span><span class="sxs-lookup"><span data-stu-id="539e4-109">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="539e4-110">Linha de base</span><span class="sxs-lookup"><span data-stu-id="539e4-110">Baseline</span></span>
- <span data-ttu-id="539e4-111">Confidencial</span><span class="sxs-lookup"><span data-stu-id="539e4-111">Sensitive</span></span>
- <span data-ttu-id="539e4-112">Altamente controlada</span><span class="sxs-lookup"><span data-stu-id="539e4-112">Highly regulated</span></span>

<span data-ttu-id="539e4-113">Se necessário, a [Etapa 1](infoprotect-define-sec-infoprotect-levels.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="539e4-113">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="539e4-114">Obrigatório: configuração de segurança aprimorada para Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="539e4-114">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="539e4-115">Você definiu as configurações a seguir para [segurança aprimorada do Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="539e4-115">You've configured the following settings for [Microsoft 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="539e4-116">Políticas de gerenciamento de ameaças na Central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="539e4-116">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="539e4-117">Configurações adicionais para todos os locatários do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="539e4-117">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="539e4-118">Políticas de compartilhamento de todos os locatários no centro de administração do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="539e4-118">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="539e4-119">Configurações do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="539e4-119">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="539e4-120">Você também [habilitou a Proteção Avançada contra Ameaças (ATP) do Office 365 para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="539e4-120">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="539e4-121">Se necessário, a [Etapa 3](infoprotect-configure-increased-security-office-365.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="539e4-121">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="539e4-122">Opcional: a classificação está configurada em seu ambiente</span><span class="sxs-lookup"><span data-stu-id="539e4-122">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="539e4-123">Você trabalhou com suas equipes jurídicas e de conformidade para desenvolver um esquema de classificação e rotulagem apropriado para suas políticas de governança e segurança de dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="539e4-123">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization's data governance and security policies.</span></span> 

<span data-ttu-id="539e4-124">Essa políticas correspondem a configuração e implantação de:</span><span class="sxs-lookup"><span data-stu-id="539e4-124">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="539e4-125">Tipos de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="539e4-125">Sensitive data types</span></span>
- <span data-ttu-id="539e4-126">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="539e4-126">Retention labels</span></span>
- <span data-ttu-id="539e4-127">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="539e4-127">Sensitivity labels</span></span>
- <span data-ttu-id="539e4-128">Rótulos da Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="539e4-128">Azure Information Protection labels</span></span>

<span data-ttu-id="539e4-129">Se necessário, a [Etapa 2](infoprotect-configure-classification.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="539e4-129">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="539e4-130">Opcional: Proteção de Informações do Windows implementada em todo o seu ambiente</span><span class="sxs-lookup"><span data-stu-id="539e4-130">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="539e4-131">Seus dispositivos Windows 10 Enterprise registrados têm uma política do Intune implementada e aplicada que define:</span><span class="sxs-lookup"><span data-stu-id="539e4-131">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="539e4-132">Quais apps para proteger.</span><span class="sxs-lookup"><span data-stu-id="539e4-132">Which apps to protect.</span></span>
- <span data-ttu-id="539e4-133">O nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="539e4-133">The level of protection.</span></span>
- <span data-ttu-id="539e4-134">Onde a proteção se estende.</span><span class="sxs-lookup"><span data-stu-id="539e4-134">Where the protection extends.</span></span>

<span data-ttu-id="539e4-135">Se necessário, a [Etapa 4](infoprotect-deploy-windows-information-protection.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="539e4-135">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="539e4-136">Opcional: a Prevenção contra Perda de Dados (DLP) está implementada</span><span class="sxs-lookup"><span data-stu-id="539e4-136">Optional: Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="539e4-137">Você analisou, testou e depois lançou o conjunto de políticas de DLP - com locais e regras com condições e ações - que sua organização exige para proteger os clientes e outros tipos de dados privados e aderir aos regulamentos e requisitos do setor e regionais.</span><span class="sxs-lookup"><span data-stu-id="539e4-137">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="539e4-138">Sua equipe de conformidade e segurança de dados está usando o painel Segurança e Conformidade para monitorar incidentes da DLP.</span><span class="sxs-lookup"><span data-stu-id="539e4-138">Your data compliance and security staff are using the Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="539e4-139">Se necessário, a [Etapa 5](infoprotect-data-loss-prevention.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="539e4-139">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="539e4-140">Opcional: a criptografia de email está configurada</span><span class="sxs-lookup"><span data-stu-id="539e4-140">Optional: Email encryption is configured</span></span>

<span data-ttu-id="539e4-141">Você configurou a seguinte criptografia de email conforme necessário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="539e4-141">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="539e4-142">**Método de criptografia**</span><span class="sxs-lookup"><span data-stu-id="539e4-142">**Encryption method**</span></span> | <span data-ttu-id="539e4-143">**Para email enviado**</span><span class="sxs-lookup"><span data-stu-id="539e4-143">**For email sent**</span></span> |
| [<span data-ttu-id="539e4-144">Criptografia de Mensagens do Office 365 (OME)</span><span class="sxs-lookup"><span data-stu-id="539e4-144">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="539e4-145">Fora da sua organização com criptografia</span><span class="sxs-lookup"><span data-stu-id="539e4-145">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="539e4-146">Gerenciamento de Direitos de Informação (IRM)</span><span class="sxs-lookup"><span data-stu-id="539e4-146">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="539e4-147">Com criptografia e permissões</span><span class="sxs-lookup"><span data-stu-id="539e4-147">With both encryption and permissions</span></span> |
| [<span data-ttu-id="539e4-148">Extensões para Mensagens de Internet Multifunção/Seguras (S/ MIME)</span><span class="sxs-lookup"><span data-stu-id="539e4-148">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="539e4-149">Com criptografia e assinaturas digitais usando criptografia de chave pública</span><span class="sxs-lookup"><span data-stu-id="539e4-149">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="539e4-150">Se necessária, a [Etapa 6](infoprotect-email-encryption.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="539e4-150">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="539e4-151">Opcional: configurar o gerenciamento de acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="539e4-151">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="539e4-152">Você usou as informações do tópico [Configurar gerenciamento de acesso privilegiado do Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar uma ou mais políticas de acesso privilegiado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="539e4-152">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="539e4-153">Você configurou essas políticas e o acesso just-in-time está habilitado para acessar dados confidenciais ou configurações críticas.</span><span class="sxs-lookup"><span data-stu-id="539e4-153">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="539e4-154">Se necessário, a [Etapa 7](infoprotect-configure-privileged-access-management.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="539e4-154">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="539e4-155">Resultados e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="539e4-155">Results and next steps</span></span>

<span data-ttu-id="539e4-156">Sua infraestrutura de proteção de informações para o Microsoft 365 Enterprise usa níveis de segurança definidos, maior segurança para o Office 365, classificação usando tipos e rótulos de dados confidenciais, Proteção de Informações do Windows, Prevenção de Perda de Dados, criptografia de email e gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="539e4-156">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, email encryption, and privileged access management.</span></span>

<span data-ttu-id="539e4-157">Se você estiver seguindo a implantação de ponta a ponta do Microsoft 365 Enterprise, já está pronto para fazer com que suas [cargas de trabalho](deploy-workloads.md) aproveitem todos os recursos e configurações da infraestrutura da sua fundação.</span><span class="sxs-lookup"><span data-stu-id="539e4-157">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
