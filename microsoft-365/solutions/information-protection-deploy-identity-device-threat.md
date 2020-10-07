---
title: Usar a proteção de identidade, dispositivo e ameaça para a regulamentação de privacidade de dados
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
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Evitar violações de dados pessoais com serviços de proteção de identidade, dispositivo e ameaça do Microsoft 365.
ms.openlocfilehash: 681ff807b734430ae864334b409fe11397f3089e
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377052"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="74e05-103">Usar a proteção de identidade, dispositivo e ameaça para a regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="74e05-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="74e05-104">A Microsoft 365 fornece vários recursos de proteção de identidade, dispositivo e ameaça que as organizações podem empregar para ajudar a cumprir as normas de conformidade relacionadas à privacidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="74e05-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="74e05-105">Este artigo descreve o que as normas de privacidade de dados exigem nessas áreas e fornece uma lista de recursos e serviços do Microsoft 365 relacionados com links para mais informações para ajudá-lo a lidar com os requisitos de implementação.</span><span class="sxs-lookup"><span data-stu-id="74e05-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="74e05-106">Como a proteção de identidade, dispositivo e ameaça se relaciona à regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="74e05-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="74e05-107">Embora as leis de privacidade dos dados variem em sua especificidade, a essência do que eles chamam é incorporada no artigo da RGPD 5 (1) (f), que afirma que:</span><span class="sxs-lookup"><span data-stu-id="74e05-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="74e05-108">Os dados pessoais devem ser processados de forma a garantir a segurança adequada dos dados pessoais, incluindo proteção contra processamento não autorizado ou não ilegal e contra perda acidental, destruição ou danos, usando medidas técnicas ou organizacionais apropriadas (' integridade e confidencialidade ').</span><span class="sxs-lookup"><span data-stu-id="74e05-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="74e05-109">Como as violações de dados pessoais são freqüentemente causadas por comprometimento de conta de usuário ou administrador e acesso de sistema mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="74e05-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="74e05-110">Por exemplo, uma conta de administrador atacante pode resultar em exfiltration de números de cartão de crédito do cliente ou outras informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="74e05-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="74e05-111">Toda a proteção de identidade, dispositivo e ameaça do recomendável disponível com o Microsoft 365 pode ser implementada, que será refletida em sua pontuação de conformidade, encontrada no gerente de conformidade.</span><span class="sxs-lookup"><span data-stu-id="74e05-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="74e05-112">Usando os resultados do trabalho de avaliação e do gerente de conformidade</span><span class="sxs-lookup"><span data-stu-id="74e05-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="74e05-113">O Gerenciador de conformidade inclui a proteção de identidade, dispositivo e ameaça usando estas categorias:</span><span class="sxs-lookup"><span data-stu-id="74e05-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="74e05-114">Identity corresponde à categoria de **acesso de controle**</span><span class="sxs-lookup"><span data-stu-id="74e05-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="74e05-115">O dispositivo corresponde à categoria **gerenciar dispositivos**</span><span class="sxs-lookup"><span data-stu-id="74e05-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="74e05-116">Proteção contra ameaças corresponde à categoria **proteger contra ameaças**</span><span class="sxs-lookup"><span data-stu-id="74e05-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="74e05-117">Se eles forem selecionados em nosso conjunto de exemplos de quatro principais regulamentações de privacidade de dados, o Gerenciador de conformidade especificará 90 ações aprimoradas, a maioria delas será classificada como "27".</span><span class="sxs-lookup"><span data-stu-id="74e05-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="74e05-118">Como um grande número é chamado de Gerenciador de conformidade para essas categorias, algumas das mais comuns estão listadas aqui, para referência.</span><span class="sxs-lookup"><span data-stu-id="74e05-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="74e05-119">Use o [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para identidade e a categoria **acesso de controle** , com a qual você pode:</span><span class="sxs-lookup"><span data-stu-id="74e05-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="74e05-120">Implementar a autenticação resistente à repetição (para evitar ataques de interceptação)</span><span class="sxs-lookup"><span data-stu-id="74e05-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="74e05-121">Bloquear a autenticação herdada.</span><span class="sxs-lookup"><span data-stu-id="74e05-121">Block legacy authentication.</span></span>
- <span data-ttu-id="74e05-122">Configure o risco do usuário e as políticas de risco de entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="74e05-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="74e05-123">Habilitar o acesso condicional e a MFA (autenticação multifator) para administradores e não administradores.</span><span class="sxs-lookup"><span data-stu-id="74e05-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="74e05-124">Configurar e impor diretivas de senha.</span><span class="sxs-lookup"><span data-stu-id="74e05-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="74e05-125">Restringir o acesso a contas privilegiadas com o Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="74e05-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="74e05-126">Desabilitar o acesso ao término.</span><span class="sxs-lookup"><span data-stu-id="74e05-126">Disable access upon termination.</span></span>
- <span data-ttu-id="74e05-127">Auditar contas de usuário e alterações de status.</span><span class="sxs-lookup"><span data-stu-id="74e05-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="74e05-128">Revise as alterações administrativas e grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="74e05-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="74e05-129">Use o [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) para dispositivos e a categoria **gerenciar dispositivos** , com a qual você pode:</span><span class="sxs-lookup"><span data-stu-id="74e05-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="74e05-130">Bloquear desbloqueado dispositivos móveis quebrados e com raiz.</span><span class="sxs-lookup"><span data-stu-id="74e05-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="74e05-131">Configure o Intune para gerenciamento de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="74e05-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="74e05-132">Criar políticas de conformidade para dispositivos Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="74e05-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="74e05-133">Criar um perfil de configuração de dispositivo para dispositivos Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="74e05-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="74e05-134">Criar políticas de proteção de aplicativos para iOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="74e05-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="74e05-135">Oculta as informações com tela de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="74e05-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="74e05-136">Implementar diretivas de senha para dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="74e05-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="74e05-137">Exigir dispositivos móveis para bloqueio na inatividade.</span><span class="sxs-lookup"><span data-stu-id="74e05-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="74e05-138">Exigir dispositivos móveis para apagar em várias falhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="74e05-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="74e05-139">Use o [Exchange Online Protection e a proteção avançada contra ameaças do Office 365 (ATP)](../security/office-365-security/office-365-atp.md) para a categoria **proteger contra ameaças** , com a qual você pode:</span><span class="sxs-lookup"><span data-stu-id="74e05-139">Use [Exchange Online Protection and Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="74e05-140">Habilitar autenticação de remetente (SPF, DMARC e DKIM).</span><span class="sxs-lookup"><span data-stu-id="74e05-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="74e05-141">Configure as políticas anti-phishing da proteção avançada contra ameaças (ATP) do Office 365.</span><span class="sxs-lookup"><span data-stu-id="74e05-141">Set up Office 365 Advanced Threat Protection (ATP) anti-phishing policies.</span></span>
- <span data-ttu-id="74e05-142">Implementar anexos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="74e05-142">Implement ATP Safe Attachments.</span></span>
- <span data-ttu-id="74e05-143">Implementar links de ATP seguros.</span><span class="sxs-lookup"><span data-stu-id="74e05-143">Implement ATP Safe Links.</span></span>
- <span data-ttu-id="74e05-144">Implementar políticas de detecção e resposta de malware.</span><span class="sxs-lookup"><span data-stu-id="74e05-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="74e05-145">Implementar políticas de spam de saída e de entrada.</span><span class="sxs-lookup"><span data-stu-id="74e05-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="74e05-146">Referencie</span><span class="sxs-lookup"><span data-stu-id="74e05-146">References:</span></span>

- [<span data-ttu-id="74e05-147">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="74e05-147">Common identity and device access policies</span></span>](../enterprise/identity-access-policies.md)
- [<span data-ttu-id="74e05-148">Proteção contra ameaças no Office 365</span><span class="sxs-lookup"><span data-stu-id="74e05-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="74e05-149">Anexos Seguros da ATP</span><span class="sxs-lookup"><span data-stu-id="74e05-149">ATP Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="74e05-150">Links Seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="74e05-150">ATP Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="74e05-151">Documentos Seguros da ATP</span><span class="sxs-lookup"><span data-stu-id="74e05-151">ATP Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
