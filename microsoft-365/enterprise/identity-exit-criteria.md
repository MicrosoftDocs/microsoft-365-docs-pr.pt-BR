---
title: 'Fase 2: Critérios de saída da infraestrutura de identidade'
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
description: Garanta que a sua configuração atenda aos critérios do Microsoft 365 Enterprise para a infraestrutura e os serviços baseados em identidade.
ms.openlocfilehash: 880bfa2b71158a2fa5c64fb09af2e8a34428a7a8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071680"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="810e0-103">Fase 2: Critérios de saída da infraestrutura de identidade</span><span class="sxs-lookup"><span data-stu-id="810e0-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="810e0-104">Verifique se a sua infraestrutura de identidade atende aos seguintes critérios necessários e que você considerou os que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="810e0-104">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="810e0-105">Confira também os [pré-requisitos](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) para obter outras recomendações de infraestrutura de identidade.</span><span class="sxs-lookup"><span data-stu-id="810e0-105">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="810e0-106">Obrigatório: as contas de administrador global estarem protegidas</span><span class="sxs-lookup"><span data-stu-id="810e0-106">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="810e0-107">Você [protegeu suas contas de administrador global do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) para impedir o comprometimento das credenciais por invasores, o que poderia levar a violações da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="810e0-107">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="810e0-108">Se você ignorar esse requisito, suas contas de administrador global podem ficar suscetíveis a ataques e a serem comprometidas, permitindo que um invasor obtenha acesso a todo o sistema e colete, destrua ou utilize seus dados como colateral para pedir um resgate.</span><span class="sxs-lookup"><span data-stu-id="810e0-108">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="810e0-109">Se necessário, a [Etapa 1](identity-create-protect-global-admins.md#identity-global-admin) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="810e0-109">If needed, [Step 1](identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="810e0-110">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-110">How to test</span></span>

<span data-ttu-id="810e0-111">Use estas etapas para verificar se você protegeu suas contas de administrador global:</span><span class="sxs-lookup"><span data-stu-id="810e0-111">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="810e0-112">Execute o comando a seguir do PowerShell do Azure Active Directory para Graph no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="810e0-112">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="810e0-113">Você deverá ver apenas a lista de contas dedicadas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="810e0-113">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="810e0-114">Entre no Office 365 usando cada uma das contas da Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="810e0-114">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="810e0-115">Cada entrada deve exigir a Autenticação Multifator do Azure e a forma mais segura de autenticação secundária disponível em sua organização.</span><span class="sxs-lookup"><span data-stu-id="810e0-115">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="810e0-116">Confira [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o Azure Active Directory PowerShell para o módulo do Graph e entrar no Office 365.</span><span class="sxs-lookup"><span data-stu-id="810e0-116">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="810e0-117">Opcional: você configurou o Privileged Identity Management para dar suporte à atribuição sob demanda da função de administrador global</span><span class="sxs-lookup"><span data-stu-id="810e0-117">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="810e0-118">Você usou as instruções em [Configurar o Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) para habilitar o PIM em seu locatário do Azure AD e configurou suas contas de administrador global como administradores qualificados.</span><span class="sxs-lookup"><span data-stu-id="810e0-118">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="810e0-119">Você também deve usar as recomendações em [Proteger o acesso privilegiado para implantações híbridas e de nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para desenvolver um roteiro que proteja o acesso privilegiado contra ataques cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="810e0-119">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="810e0-120">Se você ignorar essa opção, as contas de administrador global estarão sujeitas a contínuos ataques cibernéticos e, se forem comprometidas, poderão permitir que um invasor colete, destrua ou use suas informações confidenciais para obter um resgate.</span><span class="sxs-lookup"><span data-stu-id="810e0-120">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="810e0-121">Se necessário, a [Etapa 1](identity-create-protect-global-admins.md#identity-pim) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-121">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="810e0-122">Opcional: ter configurado o gerenciamento de acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="810e0-122">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="810e0-123">Você usou as informações do tópico [Configurar gerenciamento de acesso privilegiado do Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar uma ou mais políticas de acesso privilegiado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="810e0-123">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="810e0-124">Você configurou essas políticas e o acesso just-in-time está habilitado para acessar dados confidenciais ou configurações críticas.</span><span class="sxs-lookup"><span data-stu-id="810e0-124">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="810e0-125">Se necessário, a [Etapa 1](identity-create-protect-global-admins.md#identity-pam) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="810e0-125">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="810e0-126">Opcional: a proteção por senha do Azure AD estar proibindo o uso de senhas fracas</span><span class="sxs-lookup"><span data-stu-id="810e0-126">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="810e0-127">Você ativou a proibição de senhas ruins [na nuvem](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e para o [Active Directory Domain Services (AD DS) local](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) com base em senhas proibidas em geral e, opcionalmente, termos personalizados.</span><span class="sxs-lookup"><span data-stu-id="810e0-127">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="810e0-128">Se necessário, a [Etapa 2](identity-secure-your-passwords.md#identity-password-prot) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-128">If needed, [Step 2](identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="810e0-129">Opcional: os usuários podem redefinir suas próprias senhas</span><span class="sxs-lookup"><span data-stu-id="810e0-129">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="810e0-130">Você usou o artigo [Implantação rápida da redefinição da senha autoatendimento do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para configurar a redefinição de senha para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="810e0-130">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="810e0-131">Se você não atender a essa condição, os usuários dependerão dos administradores de contas de usuários para redefinir suas senhas, resultando em esforços adicionais para a administração de TI.</span><span class="sxs-lookup"><span data-stu-id="810e0-131">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="810e0-132">Se necessário, a [Etapa 2](identity-secure-your-passwords.md#identity-pw-reset) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-132">If needed, [Step 2](identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="810e0-133">Opcional: os usuários podem entrar usando o logon único contínuo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="810e0-133">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="810e0-134">Você deve habilitar o [Azure AD Connect: Logon Único Simplificado](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) para sua organização para simplificar como os usuários entram em aplicativos baseados na nuvem, como o Office 365.</span><span class="sxs-lookup"><span data-stu-id="810e0-134">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="810e0-135">Se você ignorar essa opção, é possível que seus usuários sejam solicitados a fornecer credenciais quando acessarem outros aplicativos que usam seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="810e0-135">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="810e0-136">Se necessário, a [Etapa 2](identity-secure-your-passwords.md#identity-sso) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-136">If needed, [Step 2](identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="810e0-137">Opcional: A tela de entrada do Office 365 ser personalizada para sua organização</span><span class="sxs-lookup"><span data-stu-id="810e0-137">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="810e0-138">Você deve usar o artigo [Adicionar a identidade visual da sua empresa às suas páginas de entrada e do Painel de Acesso](http://aka.ms/aadpaddbranding) para adicionar a identidade visual da sua organização à página de entrada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="810e0-138">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="810e0-139">Se você ignorar essa opção, os usuários verão uma tela genérica de entrada do Office 365 e poderão não ter a confiança de que estão entrando no site da sua organização.</span><span class="sxs-lookup"><span data-stu-id="810e0-139">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="810e0-140">Se necessário, a [Etapa 2](identity-secure-your-passwords.md#identity-custom-sign-in) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-140">If needed, [Step 2](identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="810e0-141">Opcional: a Autenticação Multifator do Azure estar habilitada para seus usuários</span><span class="sxs-lookup"><span data-stu-id="810e0-141">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="810e0-142">Você usou o [Plano para Autenticação Multifator do Azure](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) e [Políticas de Acesso Condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) para habilitar a MFA (Autenticação Multifator) do Azure em suas contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="810e0-142">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="810e0-p104">Se você ignorar essa opção, as contas de usuários ficarão vulneráveis a terem suas credenciais comprometidas por invasores cibernéticos. Se a senha de uma conta de usuário for comprometida, todos os recursos dessa conta, como funções de administrador, estarão disponíveis para o invasor. Isso permitirá que invasor copie, destrua ou use seus documentos internos e outros dados para pedir resgate.</span><span class="sxs-lookup"><span data-stu-id="810e0-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="810e0-146">Se necessário, a [Etapa 3](identity-secure-user-sign-ins.md#identity-mfa) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-146">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="810e0-147">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-147">How to test</span></span>

1.  <span data-ttu-id="810e0-148">Crie uma conta de usuário de teste e atribua uma licença a ela.</span><span class="sxs-lookup"><span data-stu-id="810e0-148">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="810e0-149">Configure a Autenticação Multifator do Azure para essa conta de usuário de teste com o método de verificação adicional que você estiver usando para as contas de usuário reais, como enviar uma mensagem de texto para um celular.</span><span class="sxs-lookup"><span data-stu-id="810e0-149">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="810e0-150">Entre no portal do Office 365 com a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-150">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="810e0-151">Confira se a MFA solicita informações adicionais de verificação e resulta em uma autenticação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="810e0-151">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="810e0-152">Exclua a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-152">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="810e0-153">Opcional: o Azure AD Identity Protection estar ativado para proteger você contra o comprometimento de credenciais (Microsoft 365 Enterprise E5 apenas)</span><span class="sxs-lookup"><span data-stu-id="810e0-153">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="810e0-154">Você ativou o Azure AD Identity Protection para:</span><span class="sxs-lookup"><span data-stu-id="810e0-154">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="810e0-155">Solucionar possíveis vulnerabilidades de identidade.</span><span class="sxs-lookup"><span data-stu-id="810e0-155">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="810e0-156">Detectar possíveis tentativas de ataque à credencial.</span><span class="sxs-lookup"><span data-stu-id="810e0-156">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="810e0-157">Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.</span><span class="sxs-lookup"><span data-stu-id="810e0-157">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="810e0-p105">Se você ignorar essa opção, não poderá detectar ou automaticamente eliminar tentativas de comprometer a identidade ou investigar incidentes de segurança relacionado à identidade. Isso possivelmente deixa sua organização vulnerável a ter sua identidade comprometida e à ameaça resultante aos dados confidenciais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="810e0-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="810e0-160">Se necessário, a [Etapa 3](identity-secure-user-sign-ins.md#identity-ident-prot) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-160">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="810e0-161">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-161">How to test</span></span>

1. <span data-ttu-id="810e0-162">Crie uma conta de usuário de teste com uma senha inicial.</span><span class="sxs-lookup"><span data-stu-id="810e0-162">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="810e0-163">Use as etapas em [Permitir que os usuários redefinam suas próprias senhas no Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) para redefinir a senha da conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-163">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="810e0-164">Saia e entre novamente na conta de usuário de teste usando a senha redefinida.</span><span class="sxs-lookup"><span data-stu-id="810e0-164">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="810e0-165">Exclua a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-165">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="810e0-166">Obrigatório para a identidade híbrida: os usuários e os grupos devem estar sincronizados com o Azure AD</span><span class="sxs-lookup"><span data-stu-id="810e0-166">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="810e0-167">Se você tiver um Active Directory Domain Services (AD DS) local, é porque você usou o Azure AD Connect para sincronizar as contas de usuário e os grupos de seu AD DS local com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="810e0-167">If you have an existing on-premises identity provider, such as Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="810e0-168">Com a sincronização de diretórios, seus usuários poderão entrar no Office 365 e em outros serviços de nuvem da Microsoft usando as mesmas credenciais que usam para entrar em seus computadores e acessar os recursos locais.</span><span class="sxs-lookup"><span data-stu-id="810e0-168">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="810e0-169">Se necessário, a [Etapa 4](identity-add-user-accounts.md#identity-sync) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="810e0-169">If needed, [Step 4](identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="810e0-170">Se ignorar esse requisito, você terá dois conjuntos de contas de usuários e grupos:</span><span class="sxs-lookup"><span data-stu-id="810e0-170">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="810e0-171">Contas de usuários e grupos existentes no seu AD DS local</span><span class="sxs-lookup"><span data-stu-id="810e0-171">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="810e0-172">Contas de usuários e grupos existentes em seu locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="810e0-172">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="810e0-p106">Nesse estado, os dois conjuntos de contas de usuários e grupos devem ser mantidos manualmente pelos administradores de TI e os usuários. Isso inevitavelmente levará a contas, senhas e grupos não sincronizados.</span><span class="sxs-lookup"><span data-stu-id="810e0-p106">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="810e0-175">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-175">How to test</span></span>
<span data-ttu-id="810e0-176">Para verificar se a autenticação com credenciais locais funciona corretamente, entre no portal do Office com suas credenciais locais.</span><span class="sxs-lookup"><span data-stu-id="810e0-176">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="810e0-177">Para verificar se a sincronização de diretórios está funcionando corretamente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="810e0-177">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="810e0-178">Crie um novo grupo de teste no AD DS.</span><span class="sxs-lookup"><span data-stu-id="810e0-178">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="810e0-179">Aguarde o tempo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="810e0-179">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="810e0-180">Confira se o nome do novo grupo de teste aparece no seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="810e0-180">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="810e0-181">Opcional: A sincronização de diretórios ser monitorada</span><span class="sxs-lookup"><span data-stu-id="810e0-181">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="810e0-182">Você deve usar o artigo [Azure AD Connect Health com sincronização](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (para sincronização de senhas) ou [Usar o Azure AD Connect Health com o AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (para autenticação federada) e implantar o Azure AD Connect Health, que envolve:</span><span class="sxs-lookup"><span data-stu-id="810e0-182">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="810e0-183">Instalar o agente do Azure AD Connect Health em cada servidor de identidade local.</span><span class="sxs-lookup"><span data-stu-id="810e0-183">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="810e0-184">Usar o portal do Azure AD Connect Health para monitorar o estado da sincronização em andamento.</span><span class="sxs-lookup"><span data-stu-id="810e0-184">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="810e0-185">Se ignorar essa opção, você poderá avaliar com mais precisão o estado da sua infraestrutura de identidade de nuvem.</span><span class="sxs-lookup"><span data-stu-id="810e0-185">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="810e0-186">Se necessário, a [Etapa 4](identity-add-user-accounts.md#identity-sync-health) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-186">If needed, [Step 4](identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="810e0-187">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-187">How to test</span></span>
<span data-ttu-id="810e0-188">O portal do Azure AD Connect Health mostra o estado atual e correto dos seus controladores de domínio locais e da sincronização em andamento.</span><span class="sxs-lookup"><span data-stu-id="810e0-188">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="810e0-189">Opcional: O write-back de senha estar habilitado para seus usuários</span><span class="sxs-lookup"><span data-stu-id="810e0-189">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="810e0-190">Você usou as instruções em [Azure AD SSPR com write-back de senha](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para habilitar o write-back de senha para o locatário do Azure AD da sua assinatura do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="810e0-190">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="810e0-191">Se você ignorar essa opção, os usuários que não estiverem conectados à sua rede local deverão redefinir ou desbloquear as senhas do AD DS por meio do administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="810e0-191">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="810e0-192">Se necessário, a [Etapa 4](identity-add-user-accounts.md#identity-pw-writeback) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-192">If needed, [Step 4](identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="810e0-193">O write-back de senha é necessário para utilizar por completo os recursos do Azure AD Identity Protection, por exemplo, para solicitar que os usuários alterem suas senhas locais quando o Azure AD detectar um comprometimento de conta de alto risco.</span><span class="sxs-lookup"><span data-stu-id="810e0-193">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="810e0-194">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-194">How to test</span></span>

<span data-ttu-id="810e0-195">Para testar o write-back de senha, você deverá alterar sua senha no Office 365.</span><span class="sxs-lookup"><span data-stu-id="810e0-195">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="810e0-196">Você deve conseguir usar sua conta e a nova senha para acessar os recursos do AD DS local.</span><span class="sxs-lookup"><span data-stu-id="810e0-196">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="810e0-197">Crie uma conta de usuário de teste no AD DS local, permita que a sincronização de diretórios ocorra e, em seguida, conceda uma licença do Microsoft 365 Enterprise no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="810e0-197">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it an Office 365 license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="810e0-198">Em um computador remoto ingressado no domínio do AD DS local, entre no computador e no portal do Office usando as credenciais da conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-198">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="810e0-199">Selecione **Configurações > Configurações do Office 365 > Senha > Alterar senha**.</span><span class="sxs-lookup"><span data-stu-id="810e0-199">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="810e0-200">Digite a senha atual, digite uma nova senha e a confirme.</span><span class="sxs-lookup"><span data-stu-id="810e0-200">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="810e0-201">Saia do portal do Office e do computador remoto e, em seguida, entre no computador usando a conta de usuário de teste e a nova senha.</span><span class="sxs-lookup"><span data-stu-id="810e0-201">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="810e0-202">Isso prova que você conseguiu mudar a senha de uma conta de usuário do AD DS local usando o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="810e0-202">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="810e0-203">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-203">How to test</span></span>

<span data-ttu-id="810e0-204">Entre no portal do Office 365 com o nome da sua conta de usuário e a Autenticação Multifator do Azure.</span><span class="sxs-lookup"><span data-stu-id="810e0-204">Sign in to the Office 365 portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="810e0-205">Você deverá ver seus elementos personalizados com identidade visual na página de entrada.</span><span class="sxs-lookup"><span data-stu-id="810e0-205">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="810e0-206">Opcional: O gerenciamento de grupos por autoatendimento estar habilitado para grupos específicos de segurança do Azure AD e do Office 365</span><span class="sxs-lookup"><span data-stu-id="810e0-206">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="810e0-207">Você deve determinar quais grupos são adequados para o gerenciamento por autoatendimento, instruir seus proprietários sobre o fluxo de trabalho e as responsabilidades do gerenciamento de grupos e [configurar o gerenciamento por autoatendimento no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) para esses grupos.</span><span class="sxs-lookup"><span data-stu-id="810e0-207">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="810e0-208">Se você ignorar essa opção, todas as tarefas de gerenciamento de grupos do Azure AD deverão ser realizadas por administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="810e0-208">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="810e0-209">Se necessário, a [Etapa 5](identity-use-group-management.md#identity-self-service-groups) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-209">If needed, [Step 5](identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="810e0-210">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-210">How to test</span></span>
1.  <span data-ttu-id="810e0-211">Crie uma conta de usuário de teste no Azure AD com o portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="810e0-211">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="810e0-212">Entre como com a conta de usuário de teste e crie um grupo de segurança de teste do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="810e0-212">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="810e0-213">Saia e, em seguida, entre novamente com sua conta de administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="810e0-213">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="810e0-214">Configure o grupo de segurança de teste para o gerenciamento por autoatendimento para a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-214">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="810e0-215">Saia e, em seguida, entre novamente com sua conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-215">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="810e0-216">Use o portal do Azure para adicionar membros ao grupo de segurança de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-216">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="810e0-217">Exclua o grupo de segurança de teste e a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-217">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="810e0-218">Opcional: As configurações de associação de grupo dinâmicas automaticamente adicionarem contas de usuário a grupos com base nos atributos da conta de usuário</span><span class="sxs-lookup"><span data-stu-id="810e0-218">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="810e0-219">Você deve determinar o conjunto de grupos dinâmicos do Azure AD e usar as instruções no artigo [Associação em grupo dinâmica com base em atributos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) para criar os grupos e as regras que determinam o conjunto de atributos de conta de usuário e os grupos e valores de associação em grupos.</span><span class="sxs-lookup"><span data-stu-id="810e0-219">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="810e0-p110">Se você ignorar essa opção, a associação em grupos deverá ser feita manualmente conforme novas contas forem adicionadas ou conforme os atributos de contas de usuários mudarem ao longo do tempo. Por exemplo, se alguém passar do departamento de vendas para o departamento de contabilidade, você deverá:</span><span class="sxs-lookup"><span data-stu-id="810e0-p110">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="810e0-222">Atualizar o valor do atributo Departamento dessa conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="810e0-222">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="810e0-223">Remover o usuário manualmente do grupo Vendas.</span><span class="sxs-lookup"><span data-stu-id="810e0-223">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="810e0-224">Adicionar o usuário manualmente ao grupo Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="810e0-224">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="810e0-225">Se os grupos Vendas e Contabilidade fossem dinâmicos, você só precisaria alterar o valor Departamento da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="810e0-225">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="810e0-226">Se necessário, a [Etapa 5](identity-use-group-management.md#identity-dyn-groups) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-226">If needed, [Step 5](identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="810e0-227">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-227">How to test</span></span>

1. <span data-ttu-id="810e0-228">Crie um grupo dinâmico de teste no Azure AD com o portal do Azure e configure uma regra para o Departamento igual a "teste1".</span><span class="sxs-lookup"><span data-stu-id="810e0-228">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="810e0-229">Crie uma conta de usuário de teste no Azure AD e defina a propriedade Departamento como "teste1".</span><span class="sxs-lookup"><span data-stu-id="810e0-229">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="810e0-230">Examine as propriedades da conta do usuário para garantir que ele tenha se tornado membro do grupo dinâmico de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-230">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="810e0-231">Altere o valor da propriedade Departamento da conta de usuário de teste para "teste2".</span><span class="sxs-lookup"><span data-stu-id="810e0-231">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="810e0-232">Examine as propriedades da conta do usuário para garantir que ele não seja mais membro do grupo dinâmico de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-232">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="810e0-233">Exclua o grupo dinâmico de teste e a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-233">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="810e0-234">Opcional: licenciamento baseado em grupo para automaticamente atribuir e remover licenças a contas de usuário de acordo com sua associação em grupos</span><span class="sxs-lookup"><span data-stu-id="810e0-234">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="810e0-235">Você [habilitou o licenciamento baseado em grupos](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) para os grupos de segurança apropriados do Azure AD para que as licenças do Microsoft Office 365 Enterprise sejam atribuídas ou tenham a atribuição cancelada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="810e0-235">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="810e0-236">Se você ignorar essa opção, será preciso realizar as seguintes tarefas manualmente:</span><span class="sxs-lookup"><span data-stu-id="810e0-236">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="810e0-237">Atribuir licenças a novos usuários para os quais você pretende conceder acesso.</span><span class="sxs-lookup"><span data-stu-id="810e0-237">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="810e0-238">Cancelar a atribuição de licenças de usuários que não estejam mais trabalhando com sua organização ou que não tenham acesso.</span><span class="sxs-lookup"><span data-stu-id="810e0-238">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="810e0-239">Se necessário, a [Etapa 5](identity-use-group-management.md#identity-group-license) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-239">If needed, [Step 5](identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="810e0-240">Como testar</span><span class="sxs-lookup"><span data-stu-id="810e0-240">How to test</span></span>

1. <span data-ttu-id="810e0-241">Crie um grupo de segurança de teste no Azure AD com o portal do Azure e configure o licenciamento baseado em grupo para atribuir licenças do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="810e0-241">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="810e0-242">Crie uma conta de usuário de teste no Azure AD e adicione-a ao grupo de segurança de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-242">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="810e0-243">Examine as propriedades da conta de usuário no centro de administração do Microsoft 365 para garantir que a licença do Microsoft 365 Enterprise tenha sido atribuída a ela.</span><span class="sxs-lookup"><span data-stu-id="810e0-243">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="810e0-244">Remova a conta de usuário de teste do grupo de segurança de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-244">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="810e0-245">Examine as propriedades da conta de usuário para garantir que a licença do Microsoft 365 Enterprise não esteja mais atribuída a ela.</span><span class="sxs-lookup"><span data-stu-id="810e0-245">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="810e0-246">Exclua o grupo de segurança de teste e a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="810e0-246">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="810e0-247">Opcional: revisões de acesso configuradas e usadas para monitorar o acesso</span><span class="sxs-lookup"><span data-stu-id="810e0-247">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="810e0-248">Você usou esses artigos para configurar diferentes tipos de revisões de acesso para monitorar associações a grupos, acesso a aplicativos corporativos e atribuições de funções:</span><span class="sxs-lookup"><span data-stu-id="810e0-248">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="810e0-249">Grupos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="810e0-249">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="810e0-250">Funções do Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="810e0-250">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="810e0-251">Funções de recurso do Azure</span><span class="sxs-lookup"><span data-stu-id="810e0-251">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="810e0-252">Se necessário, a [Etapa 6](identity-configure-identity-governance.md#identity-access-reviews) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="810e0-252">If needed, [Step 6](identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>


## <a name="results-and-next-steps"></a><span data-ttu-id="810e0-253">Resultados e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="810e0-253">Results and next steps</span></span>

<span data-ttu-id="810e0-254">Sua infraestrutura de identidade na nuvem do Microsoft 365 usa autenticação forte, contas de administrador protegidas e acesso de usuário e gerenciamento simplificados.</span><span class="sxs-lookup"><span data-stu-id="810e0-254">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="810e0-255">Se você está seguindo as fases para a implantação de ponta a ponta do Microsoft 365 Enterprise, sua próxima fase é [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="810e0-255">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

