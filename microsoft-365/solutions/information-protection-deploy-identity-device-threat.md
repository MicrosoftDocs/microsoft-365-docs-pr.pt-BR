---
title: Usar identidade, dispositivo e proteção contra ameaças para regulamentação de privacidade de dados
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
description: Impedir violações de dados pessoais com os serviços de identidade, dispositivo e proteção contra ameaças do Microsoft 365.
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847173"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="7589b-103">Usar identidade, dispositivo e proteção contra ameaças para regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="7589b-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="7589b-104">O Microsoft 365 fornece vários recursos de proteção contra ameaças, dispositivos e identidades que as organizações podem empregar para ajudar a cumprir os regulamentos de conformidade relacionados à privacidade de dados.</span><span class="sxs-lookup"><span data-stu-id="7589b-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="7589b-105">Este artigo descreve o que as regulamentações de privacidade de dados exigem nessas áreas e fornece uma lista de recursos e serviços relacionados do Microsoft 365 com links para obter mais informações para ajudá-lo a atender aos requisitos de implementação.</span><span class="sxs-lookup"><span data-stu-id="7589b-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="7589b-106">Como a identidade, o dispositivo e a proteção contra ameaças se relacionam com a regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="7589b-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="7589b-107">Embora as regulamentações de privacidade de dados variem em sua especificidade, a essência do que eles chamam é embodiada no Artigo 5(1)(f) do RGPD, que declara que:</span><span class="sxs-lookup"><span data-stu-id="7589b-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="7589b-108">Os dados pessoais devem ser processados de maneira a garantir a segurança adequada dos dados pessoais, incluindo proteção contra processamento não autorizado ou ilegal e contra perda, destruição ou danos acidentais, usando medidas técnicas ou organizacionais apropriadas ('integridade e confidencialidade').</span><span class="sxs-lookup"><span data-stu-id="7589b-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="7589b-109">Como as violações de dados pessoais geralmente são causadas por comprometimento da conta de usuário final ou administrativa e acesso ao sistema mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="7589b-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="7589b-110">Por exemplo, um hackers de conta de administrador pode resultar em exfiltração de números de cartão de crédito do cliente ou outras informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="7589b-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="7589b-111">Todas as identidades, dispositivos e proteção contra ameaças geralmente aconselháveis disponíveis no Microsoft 365 devem ser implementadas, o que será refletido na sua pontuação de conformidade, encontrada no Gerenciador de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="7589b-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="7589b-112">Usando os resultados do trabalho de avaliação e do Gerenciador de Conformidade</span><span class="sxs-lookup"><span data-stu-id="7589b-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="7589b-113">O Gerenciador de Conformidade inclui identidade, dispositivo e proteção contra ameaças usando estas categorias:</span><span class="sxs-lookup"><span data-stu-id="7589b-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="7589b-114">A identidade corresponde à categoria **Acesso ao** Controle</span><span class="sxs-lookup"><span data-stu-id="7589b-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="7589b-115">O dispositivo corresponde à categoria **Gerenciar Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="7589b-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="7589b-116">A proteção contra ameaças corresponde à categoria **Proteger Contra Ameaças**</span><span class="sxs-lookup"><span data-stu-id="7589b-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="7589b-117">Se eles forem selecionados em nosso conjunto de amostra de quatro regulamentos de privacidade de dados principais, o Gerenciador de Conformidade especificará 90 ações de melhoria, a maioria delas com pontuação "27".</span><span class="sxs-lookup"><span data-stu-id="7589b-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="7589b-118">Como um número tão grande é chamado pelo Gerenciador de Conformidade para essas categorias, algumas das mais comuns são listadas aqui, para referência.</span><span class="sxs-lookup"><span data-stu-id="7589b-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="7589b-119">Use [o Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para identidade e a categoria acesso **de** controle, com a qual você pode:</span><span class="sxs-lookup"><span data-stu-id="7589b-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="7589b-120">Implementar a autenticação resistente a repetição (para evitar ataques "Man in the middle")</span><span class="sxs-lookup"><span data-stu-id="7589b-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="7589b-121">Bloquear a autenticação herdada.</span><span class="sxs-lookup"><span data-stu-id="7589b-121">Block legacy authentication.</span></span>
- <span data-ttu-id="7589b-122">Configure as políticas de risco do usuário e de risco de login do usuário.</span><span class="sxs-lookup"><span data-stu-id="7589b-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="7589b-123">Habilitar o Acesso Condicional e a MFA (autenticação multifacional) para administradores e não administradores.</span><span class="sxs-lookup"><span data-stu-id="7589b-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="7589b-124">Configurar e impor políticas de senha.</span><span class="sxs-lookup"><span data-stu-id="7589b-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="7589b-125">Restringir o acesso a contas privilegiadas com o Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="7589b-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="7589b-126">Desabilitar o acesso após o término.</span><span class="sxs-lookup"><span data-stu-id="7589b-126">Disable access upon termination.</span></span>
- <span data-ttu-id="7589b-127">Auditoria de contas de usuário e alterações de status.</span><span class="sxs-lookup"><span data-stu-id="7589b-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="7589b-128">Revise o grupo de funções e as alterações administrativas.</span><span class="sxs-lookup"><span data-stu-id="7589b-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="7589b-129">Use [o Microsoft Endpoint Manager para](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) dispositivos e a categoria **Gerenciar** Dispositivos, com a qual você pode:</span><span class="sxs-lookup"><span data-stu-id="7589b-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="7589b-130">Bloqueie a cadeia de dispositivos móveis quebrados e com raiz.</span><span class="sxs-lookup"><span data-stu-id="7589b-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="7589b-131">Configurar o Intune para gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="7589b-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="7589b-132">Crie políticas de conformidade para dispositivos Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="7589b-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="7589b-133">Crie um perfil de configuração de dispositivo para dispositivos Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="7589b-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="7589b-134">Crie políticas de proteção de aplicativos para iOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="7589b-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="7589b-135">Ocultar informações com a tela de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="7589b-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="7589b-136">Implementar políticas de senha para dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="7589b-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="7589b-137">Exigir que os dispositivos móveis bloqueiem a inatividade.</span><span class="sxs-lookup"><span data-stu-id="7589b-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="7589b-138">Exigir que os dispositivos móveis limpem várias falhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="7589b-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="7589b-139">Use [a Proteção do Exchange Online e o Microsoft Defender para Office 365](../security/office-365-security/office-365-atp.md) para a categoria Proteger **Contra** Ameaças, com a qual você pode:</span><span class="sxs-lookup"><span data-stu-id="7589b-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="7589b-140">Habilitar a autenticação de remetente (SPF, DMARC e DKIM).</span><span class="sxs-lookup"><span data-stu-id="7589b-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="7589b-141">Configurar o Microsoft Defender para políticas anti-phishing do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7589b-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="7589b-142">Implementar Anexos Seguros.</span><span class="sxs-lookup"><span data-stu-id="7589b-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="7589b-143">Implementar Links seguros.</span><span class="sxs-lookup"><span data-stu-id="7589b-143">Implement Safe Links.</span></span>
- <span data-ttu-id="7589b-144">Implementar políticas de detecção e resposta de malware.</span><span class="sxs-lookup"><span data-stu-id="7589b-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="7589b-145">Implementar políticas de spam de saída e de entrada.</span><span class="sxs-lookup"><span data-stu-id="7589b-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="7589b-146">Referências:</span><span class="sxs-lookup"><span data-stu-id="7589b-146">References:</span></span>

- [<span data-ttu-id="7589b-147">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="7589b-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="7589b-148">Proteger contra ameaças no Office 365</span><span class="sxs-lookup"><span data-stu-id="7589b-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="7589b-149">Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="7589b-149">Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="7589b-150">Links Seguros</span><span class="sxs-lookup"><span data-stu-id="7589b-150">Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="7589b-151">Documentos Seguros</span><span class="sxs-lookup"><span data-stu-id="7589b-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
