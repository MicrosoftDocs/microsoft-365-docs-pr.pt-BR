---
title: 'Etapa 3: proteger e gerenciar as entradas do seu usuário'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Você pode deixar as entradas dos usuários no Windows e no Microsoft 365 mais seguras.
ms.openlocfilehash: edf51b344ed8f9c8e13587cc2ccf0ba1ed081da6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073206"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="36ed6-103">Etapa 3: proteger e gerenciar as entradas do seu usuário</span><span class="sxs-lookup"><span data-stu-id="36ed6-103">Step 3: Secure and manage your user sign-ins</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="36ed6-104">Usar o Windows Hello para Empresas</span><span class="sxs-lookup"><span data-stu-id="36ed6-104">Windows Hello for Business</span></span>

<span data-ttu-id="36ed6-105">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="36ed6-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="36ed6-106">O Windows Hello para Empresas no Windows 10 Enterprise substitui senhas com autenticação forte de dois fatores ao entrar em um dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="36ed6-106">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="36ed6-107">O recurso de dois fatores é um novo tipo de credencial de usuário vinculado a um dispositivo e a uma leitura biométrica ou a um PIN.</span><span class="sxs-lookup"><span data-stu-id="36ed6-107">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="36ed6-108">Para obter mais informações, consulte [Visão geral do Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span><span class="sxs-lookup"><span data-stu-id="36ed6-108">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="36ed6-109">Configurar a Autenticação Multifator do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="36ed6-109">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="36ed6-110">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="36ed6-110">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="36ed6-111">Nesta etapa, você configurará a MFA (Autenticação Multifator) para adicionar uma segunda camada de segurança a entradas e transações de usuários.</span><span class="sxs-lookup"><span data-stu-id="36ed6-111">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="36ed6-112">A MFA exige um método de verificação adicional depois que os usuários tiverem digitado a senha corretamente.</span><span class="sxs-lookup"><span data-stu-id="36ed6-112">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="36ed6-113">Sem a MFA, a senha é o único método de verificação.</span><span class="sxs-lookup"><span data-stu-id="36ed6-113">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="36ed6-114">O problema de usar senhas é que muitas delas são facilmente adivinhadas por um invasor ou são compartilhadas inconscientemente com pessoas não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="36ed6-114">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="36ed6-115">Com a MFA, a segunda camada de segurança pode ser:</span><span class="sxs-lookup"><span data-stu-id="36ed6-115">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="36ed6-116">Um dispositivo pessoal de confiança que não seja facilmente forjado ou duplicado, como um smartphone.</span><span class="sxs-lookup"><span data-stu-id="36ed6-116">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="36ed6-117">Um atributo biométrico, como uma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="36ed6-117">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="36ed6-118">Você habilitará a MFA e configurará o método de autenticação secundária com [Políticas de Acesso Condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), as quais permitem o uso de grupos do Azure Active Directory (Azure AD) para implementar a MFA em conjuntos de usuários específicos, como usuários piloto, em regiões geográficas ou em departamentos.</span><span class="sxs-lookup"><span data-stu-id="36ed6-118">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="36ed6-119">Avise seus usuários que a MFA será ativada para que eles compreendam os requisitos, como o uso obrigatório de um Smartphone para acesso, e possam entrar na rede com êxito.</span><span class="sxs-lookup"><span data-stu-id="36ed6-119">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="36ed6-120">Para obter mais informações, confira [Planejando uma implantação da Autenticação Multifator do Azure baseada em nuvem](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="36ed6-120">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="36ed6-122">Guia do Laboratório de Teste: Autenticação Multifator do Azure</span><span class="sxs-lookup"><span data-stu-id="36ed6-122">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="36ed6-123">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-mfa) desta seção.</span><span class="sxs-lookup"><span data-stu-id="36ed6-123">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="36ed6-124">Proteger-se contra o comprometimento de credenciais</span><span class="sxs-lookup"><span data-stu-id="36ed6-124">Protect against credential compromise</span></span>

<span data-ttu-id="36ed6-125">*Isso é opcional e se aplica somente às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="36ed6-125">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="36ed6-126">Nesta seção, você aprenderá a configurar políticas de proteção contra o comprometimento de credenciais, onde um invasor determina o nome e senha da conta de um usuário para obter acesso aos serviços de nuvem e dados de uma organização.</span><span class="sxs-lookup"><span data-stu-id="36ed6-126">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="36ed6-127">O Azure AD Identity Protection oferece várias maneiras de ajudar a impedir que um invasor comprometa as credenciais da conta de um usuário.</span><span class="sxs-lookup"><span data-stu-id="36ed6-127">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="36ed6-128">Com a Azure AD Identity Protection, você pode:</span><span class="sxs-lookup"><span data-stu-id="36ed6-128">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="36ed6-129">Determinar e administrar possíveis vulnerabilidades nas identidades da organização</span><span class="sxs-lookup"><span data-stu-id="36ed6-129">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="36ed6-130">O Azure AD usa o aprendizado de máquina para detectar anomalias e atividades suspeitas, como entrada e pós-entradas.</span><span class="sxs-lookup"><span data-stu-id="36ed6-130">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span> <span data-ttu-id="36ed6-131">Ao usar esses dados, o Azure AD Identity Protection gera relatórios e alertas que ajudam você a avaliar os problemas e a tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="36ed6-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="36ed6-132">Detectar ações suspeitas relacionadas às identidades da organização e responder a essas suspeitas automaticamente</span><span class="sxs-lookup"><span data-stu-id="36ed6-132">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="36ed6-133">Você pode configurar políticas de risco que respondem automaticamente a problemas detectados quando um nível de risco específico tiver sido alcançado.</span><span class="sxs-lookup"><span data-stu-id="36ed6-133">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="36ed6-134">Essas políticas, além de outros controles de Acesso Condicional fornecidos pelo Azure AD e pelo Microsoft Intune, podem bloquear automaticamente o acesso ou tomar ações corretivas, como redefinições de senha e a imposição de Autenticação Multifator do Azure para as próximas entradas.</span><span class="sxs-lookup"><span data-stu-id="36ed6-134">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="36ed6-135">Investigar incidentes suspeitos e resolvê-los com medidas administrativas</span><span class="sxs-lookup"><span data-stu-id="36ed6-135">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="36ed6-p107">Você pode investigar eventos de risco usando informações sobre o incidente de segurança. Fluxos básicos de trabalho estão disponíveis para controlar investigações e iniciar ações de correção, como a redefinição de senhas.</span><span class="sxs-lookup"><span data-stu-id="36ed6-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="36ed6-138">Consulte mais [informações sobre a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="36ed6-138">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="36ed6-139">Consulte as [etapas para habilitar a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="36ed6-139">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="36ed6-140">Como resultados desta etapa, você habilitou o Azure AD Identity Protection e está o usando para:</span><span class="sxs-lookup"><span data-stu-id="36ed6-140">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="36ed6-141">Solucionar possíveis vulnerabilidades de identidade.</span><span class="sxs-lookup"><span data-stu-id="36ed6-141">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="36ed6-142">Detectar possíveis tentativas de ataque à credencial.</span><span class="sxs-lookup"><span data-stu-id="36ed6-142">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="36ed6-143">Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.</span><span class="sxs-lookup"><span data-stu-id="36ed6-143">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="36ed6-145">Guia do Laboratório de Teste: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="36ed6-145">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="36ed6-146">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-ident-prot) desta seção.</span><span class="sxs-lookup"><span data-stu-id="36ed6-146">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="36ed6-147">Adicionar suas contas de usuário</span><span class="sxs-lookup"><span data-stu-id="36ed6-147">Add your user accounts</span></span>](identity-add-user-accounts.md) |
