---
title: Usar identidade, dispositivo e proteção contra ameaças para a regulamentação de privacidade de dados
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
description: Impedir violações de dados pessoais com os serviços de proteção de identidade, dispositivo e ameaças do Microsoft 365.
ms.openlocfilehash: 145b8a59f7eafb95adf71dc24613ee15ef1c2cca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052345"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="c47dd-103">Usar identidade, dispositivo e proteção contra ameaças para a regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="c47dd-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="c47dd-104">O Microsoft 365 fornece vários recursos de proteção contra ameaças, dispositivos e identidades que as organizações podem empregar para ajudar a cumprir os regulamentos de conformidade relacionados à privacidade de dados.</span><span class="sxs-lookup"><span data-stu-id="c47dd-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="c47dd-105">Este artigo descreve o que os regulamentos de privacidade de dados exigem nessas áreas e fornece uma listagem de recursos e serviços relacionados do Microsoft 365 com links para mais informações para ajudá-lo a lidar com os requisitos de implementação.</span><span class="sxs-lookup"><span data-stu-id="c47dd-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="c47dd-106">Como a identidade, o dispositivo e a proteção contra ameaças se relacionam com a regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="c47dd-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="c47dd-107">Embora os regulamentos de privacidade de dados variem em sua especificidade, a essência do que eles chamam é personificação no Artigo 5(1)(f) do RGPD, que diz que:</span><span class="sxs-lookup"><span data-stu-id="c47dd-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="c47dd-108">Os dados pessoais devem ser processados de maneira que garanta a segurança apropriada dos dados pessoais, incluindo a proteção contra o processamento não autorizado ou ilegal e contra perdas acidentais, destruição ou danos, usando medidas técnicas ou organizacionais apropriadas ('integridade e confidencialidade').</span><span class="sxs-lookup"><span data-stu-id="c47dd-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="c47dd-109">Como violações de dados pessoais geralmente são causadas por comprometimento da conta de usuário final ou administrativa e acesso mal-intencionado ao sistema.</span><span class="sxs-lookup"><span data-stu-id="c47dd-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="c47dd-110">Por exemplo, um hack de conta de administrador pode resultar em exfiltração de números de cartão de crédito do cliente ou outras informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="c47dd-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="c47dd-111">Toda a identidade, dispositivo e proteção contra ameaças geralmente aconselháveis disponíveis com o Microsoft 365 potencialmente deve ser implementada, o que será refletido na sua pontuação de conformidade, encontrada no Gerenciador de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="c47dd-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="c47dd-112">Usando os resultados do trabalho de avaliação e do Gerenciador de Conformidade</span><span class="sxs-lookup"><span data-stu-id="c47dd-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="c47dd-113">O Gerenciador de Conformidade inclui identidade, dispositivo e proteção contra ameaças usando estas categorias:</span><span class="sxs-lookup"><span data-stu-id="c47dd-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="c47dd-114">A identidade corresponde à categoria **Acesso para** Controle</span><span class="sxs-lookup"><span data-stu-id="c47dd-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="c47dd-115">O dispositivo corresponde à categoria **Gerenciar Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="c47dd-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="c47dd-116">Proteção contra ameaças corresponde à categoria **Proteger Contra Ameaças**</span><span class="sxs-lookup"><span data-stu-id="c47dd-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="c47dd-117">Se eles forem selecionados em nosso conjunto de exemplos de quatro regulamentos principais de privacidade de dados, o Gerenciador de Conformidade especificará 90 ações de melhoria, a maioria delas pontuadas como "27".</span><span class="sxs-lookup"><span data-stu-id="c47dd-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="c47dd-118">Como um número tão grande é chamado pelo Gerenciador de Conformidade para essas categorias, algumas das mais comuns são listadas aqui, para referência.</span><span class="sxs-lookup"><span data-stu-id="c47dd-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="c47dd-119">Use [o Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para identidade e a categoria **Acesso para** Controle, com a qual você pode:</span><span class="sxs-lookup"><span data-stu-id="c47dd-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="c47dd-120">Implementar autenticação resistente a repetição (para evitar ataques "homem no meio" )</span><span class="sxs-lookup"><span data-stu-id="c47dd-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="c47dd-121">Bloquear a autenticação herdada.</span><span class="sxs-lookup"><span data-stu-id="c47dd-121">Block legacy authentication.</span></span>
- <span data-ttu-id="c47dd-122">Configure as políticas de risco de usuário e de login do usuário.</span><span class="sxs-lookup"><span data-stu-id="c47dd-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="c47dd-123">Habilita o Acesso Condicional e a autenticação multifacional (MFA) para administradores e não administradores.</span><span class="sxs-lookup"><span data-stu-id="c47dd-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="c47dd-124">Configurar e impor políticas de senha.</span><span class="sxs-lookup"><span data-stu-id="c47dd-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="c47dd-125">Restringir o acesso a contas privilegiadas com o Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="c47dd-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="c47dd-126">Desabilitar o acesso ao término.</span><span class="sxs-lookup"><span data-stu-id="c47dd-126">Disable access upon termination.</span></span>
- <span data-ttu-id="c47dd-127">Auditar contas de usuário e alterações de status.</span><span class="sxs-lookup"><span data-stu-id="c47dd-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="c47dd-128">Revise o grupo de funções e as alterações administrativas.</span><span class="sxs-lookup"><span data-stu-id="c47dd-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="c47dd-129">Use [o Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) para dispositivos e a categoria Gerenciar **Dispositivos,** com a qual você pode:</span><span class="sxs-lookup"><span data-stu-id="c47dd-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="c47dd-130">Bloqueie a cadeia de dispositivos móveis quebrados e enraizado.</span><span class="sxs-lookup"><span data-stu-id="c47dd-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="c47dd-131">Configure o Intune para gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="c47dd-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="c47dd-132">Crie políticas de conformidade para dispositivos Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="c47dd-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="c47dd-133">Crie um perfil de configuração de dispositivo para dispositivos Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="c47dd-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="c47dd-134">Crie políticas de proteção de aplicativos para iOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="c47dd-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="c47dd-135">Ocultar informações com a tela de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="c47dd-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="c47dd-136">Implemente políticas de senha para dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="c47dd-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="c47dd-137">Exigir que os dispositivos móveis bloqueiem na inatividade.</span><span class="sxs-lookup"><span data-stu-id="c47dd-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="c47dd-138">Exigir que os dispositivos móveis limpem várias falhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="c47dd-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="c47dd-139">Use [a Proteção do Exchange Online e o Microsoft Defender para Office 365](../security/defender-365-security/defender-for-office-365.md) para a categoria **Proteger Contra Ameaças,** com a qual você pode:</span><span class="sxs-lookup"><span data-stu-id="c47dd-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/defender-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="c47dd-140">Habilitar autenticação de remetente (SPF, DMARC e DKIM).</span><span class="sxs-lookup"><span data-stu-id="c47dd-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="c47dd-141">Configurar políticas anti-phishing do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="c47dd-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="c47dd-142">Implementar anexos seguros.</span><span class="sxs-lookup"><span data-stu-id="c47dd-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="c47dd-143">Implementar Links Seguros.</span><span class="sxs-lookup"><span data-stu-id="c47dd-143">Implement Safe Links.</span></span>
- <span data-ttu-id="c47dd-144">Implemente políticas de detecção e resposta de malware.</span><span class="sxs-lookup"><span data-stu-id="c47dd-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="c47dd-145">Implemente políticas de spam de saída e de entrada.</span><span class="sxs-lookup"><span data-stu-id="c47dd-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="c47dd-146">Referências:</span><span class="sxs-lookup"><span data-stu-id="c47dd-146">References:</span></span>

- [<span data-ttu-id="c47dd-147">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="c47dd-147">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)
- [<span data-ttu-id="c47dd-148">Proteger contra ameaças no Office 365</span><span class="sxs-lookup"><span data-stu-id="c47dd-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="c47dd-149">Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="c47dd-149">Safe Attachments</span></span>](../security/defender-365-security/safe-attachments.md)
- [<span data-ttu-id="c47dd-150">Links Seguros</span><span class="sxs-lookup"><span data-stu-id="c47dd-150">Safe Links</span></span>](../security/defender-365-security/safe-links.md)
- [<span data-ttu-id="c47dd-151">Documentos Seguros</span><span class="sxs-lookup"><span data-stu-id="c47dd-151">Safe Documents</span></span>](../security/defender-365-security/safe-docs.md)
