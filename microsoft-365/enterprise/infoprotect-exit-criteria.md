---
title: Critérios de saída da infraestrutura de proteção de informações
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
ms.openlocfilehash: 02e972a80d4b42ae66193bbbc55d0f1e63be5ba6
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047234"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="3a7da-103">Critérios de saída da infraestrutura de proteção de informações</span><span class="sxs-lookup"><span data-stu-id="3a7da-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="3a7da-104">Verifique se a sua infraestrutura de proteção de informações atende aos seguintes critérios necessários e que você considerou aqueles que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="3a7da-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="3a7da-105">Obrigatório: os níveis de segurança e proteção de informações foram definidos em para a sua organização</span><span class="sxs-lookup"><span data-stu-id="3a7da-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="3a7da-p101">Você planejou e determinou os níveis de segurança necessários para a sua organização. Esses níveis definem o patamar mínimo de segurança e outros níveis para informações cuja confidencialidade aumenta gradualmente, assim como a segurança de dados exigida para cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="3a7da-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="3a7da-108">No mínimo, você está usando três níveis de segurança:</span><span class="sxs-lookup"><span data-stu-id="3a7da-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="3a7da-109">Linha de base</span><span class="sxs-lookup"><span data-stu-id="3a7da-109">Baseline</span></span>
- <span data-ttu-id="3a7da-110">Confidencial</span><span class="sxs-lookup"><span data-stu-id="3a7da-110">Sensitive</span></span>
- <span data-ttu-id="3a7da-111">Altamente controlada</span><span class="sxs-lookup"><span data-stu-id="3a7da-111">Highly regulated</span></span>

<span data-ttu-id="3a7da-112">Se necessário, a [Etapa 1](infoprotect-define-sec-infoprotect-levels.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="3a7da-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="3a7da-113">Obrigatório: configuração de segurança aprimorada para Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="3a7da-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="3a7da-114">As seguintes configurações foram habilitadas para a [segurança aprimorada do Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="3a7da-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="3a7da-115">Políticas de gerenciamento de ameaças na Central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3a7da-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="3a7da-116">Configurações adicionais para todos os locatários do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3a7da-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="3a7da-117">Políticas de compartilhamento de todos os locatários no centro de administração do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3a7da-117">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="3a7da-118">Configurações do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3a7da-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="3a7da-119">Você também [habilitou a Proteção Avançada contra Ameaças (ATP) do Office 365 para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="3a7da-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="3a7da-120">Se necessário, a [Etapa 3](infoprotect-configure-increased-security-office-365.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="3a7da-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="3a7da-121">Opcional: a classificação está configurada em seu ambiente</span><span class="sxs-lookup"><span data-stu-id="3a7da-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="3a7da-122">Você trabalhou com o seu departamento jurídico e de conformidade para desenvolver uma classificação apropriada e um esquema de identificação de governança de dados e políticas de segurança para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="3a7da-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="3a7da-123">Essa políticas correspondem a configuração e implantação de:</span><span class="sxs-lookup"><span data-stu-id="3a7da-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="3a7da-124">Tipos de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="3a7da-124">Sensitive data types</span></span>
- <span data-ttu-id="3a7da-125">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="3a7da-125">Retention labels</span></span>
- <span data-ttu-id="3a7da-126">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="3a7da-126">Sensitivity labels</span></span>
- <span data-ttu-id="3a7da-127">Rótulos da Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="3a7da-127">Azure Information Protection labels</span></span>

<span data-ttu-id="3a7da-128">Se necessário, a [Etapa 2](infoprotect-configure-classification.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="3a7da-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="3a7da-129">Opcional: Proteção de Informações do Windows implementada em todo o seu ambiente</span><span class="sxs-lookup"><span data-stu-id="3a7da-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="3a7da-130">Seus dispositivos Windows 10 Enterprise registrados têm uma política do Intune implementada e aplicada que define:</span><span class="sxs-lookup"><span data-stu-id="3a7da-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="3a7da-131">Quais apps para proteger.</span><span class="sxs-lookup"><span data-stu-id="3a7da-131">Which apps to protect.</span></span>
- <span data-ttu-id="3a7da-132">O nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="3a7da-132">The level of protection.</span></span>
- <span data-ttu-id="3a7da-133">Onde a proteção se estende.</span><span class="sxs-lookup"><span data-stu-id="3a7da-133">Where the protection extends.</span></span>

<span data-ttu-id="3a7da-134">Se necessário, a [Etapa 4](infoprotect-deploy-windows-information-protection.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="3a7da-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="3a7da-135">Opcional: o DLP (Data Loss Prevention) do Office 365 está implantado</span><span class="sxs-lookup"><span data-stu-id="3a7da-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="3a7da-136">Você analisou, testou e depois lançou o conjunto de políticas de DLP - com locais e regras com condições e ações - que sua organização exige para proteger os clientes e outros tipos de dados privados e aderir aos regulamentos e requisitos do setor e regionais.</span><span class="sxs-lookup"><span data-stu-id="3a7da-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="3a7da-137">Sua equipe de conformidade e segurança de dados está usando o Office 365 Security & amp; Painel de conformidade para monitorar incidentes de DLP.</span><span class="sxs-lookup"><span data-stu-id="3a7da-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="3a7da-138">Se necessário, a [Etapa 5](infoprotect-data-loss-prevention.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="3a7da-138">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="3a7da-139">Opcional: a criptografia de email está configurada</span><span class="sxs-lookup"><span data-stu-id="3a7da-139">Optional: Email encryption is configured</span></span>

<span data-ttu-id="3a7da-140">Você configurou a seguinte criptografia de email conforme necessário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="3a7da-140">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="3a7da-141">**Método de criptografia**</span><span class="sxs-lookup"><span data-stu-id="3a7da-141">**Encryption method**</span></span> | <span data-ttu-id="3a7da-142">**Para email enviado**</span><span class="sxs-lookup"><span data-stu-id="3a7da-142">**For email sent**</span></span> |
| [<span data-ttu-id="3a7da-143">Criptografia de Mensagens do Office 365 (OME)</span><span class="sxs-lookup"><span data-stu-id="3a7da-143">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="3a7da-144">Fora da sua organização com criptografia</span><span class="sxs-lookup"><span data-stu-id="3a7da-144">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="3a7da-145">Gerenciamento de Direitos de Informação (IRM)</span><span class="sxs-lookup"><span data-stu-id="3a7da-145">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="3a7da-146">Com criptografia e permissões</span><span class="sxs-lookup"><span data-stu-id="3a7da-146">With both encryption and permissions</span></span> |
| [<span data-ttu-id="3a7da-147">Extensões para Mensagens de Internet Multifunção/Seguras (S/ MIME)</span><span class="sxs-lookup"><span data-stu-id="3a7da-147">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="3a7da-148">Com criptografia e assinaturas digitais usando criptografia de chave pública</span><span class="sxs-lookup"><span data-stu-id="3a7da-148">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="3a7da-149">Se necessária, a [Etapa 6](infoprotect-email-encryption.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="3a7da-149">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="3a7da-150">Opcional: configurar o gerenciamento de acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="3a7da-150">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="3a7da-151">Você usou as informações do tópico [Configurar gerenciamento de acesso privilegiado do Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar uma ou mais políticas de acesso privilegiado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3a7da-151">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="3a7da-152">Você configurou essas políticas e o acesso just-in-time está habilitado para acessar dados confidenciais ou configurações críticas.</span><span class="sxs-lookup"><span data-stu-id="3a7da-152">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="3a7da-153">Se necessário, a [Etapa 7](infoprotect-configure-privileged-access-management.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="3a7da-153">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="3a7da-154">Resultados e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3a7da-154">Results and next steps</span></span>

<span data-ttu-id="3a7da-155">Sua infraestrutura de proteção de informações para o Microsoft 365 Enterprise usa níveis de segurança definidos, maior segurança para o Office 365, classificação usando tipos e rótulos de dados confidenciais, Proteção de Informações do Windows, Prevenção de Perda de Dados, criptografia de email e gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="3a7da-155">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, and privileged access management.</span></span>

<span data-ttu-id="3a7da-156">Se você está seguindo a implantação de ponta a ponta do Microsoft 365 Enterprise, você está pronto para fazer suas [cargas de trabalho e seus cenários](deploy-workloads.md) aproveitarem todos os recursos e configurações de sua infraestrutura de base.</span><span class="sxs-lookup"><span data-stu-id="3a7da-156">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
