---
title: 'Fase 2: Critérios de saída da infraestrutura de identidade'
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 3fd4d0a1df50d55cb7a21668b609341d0c01aa35
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544060"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="4856a-103">Fase 2: Critérios de saída da infraestrutura de identidade</span><span class="sxs-lookup"><span data-stu-id="4856a-103">Phase 2: Identity infrastructure exit criteria</span></span>

![Fase 2 – Identidade](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="4856a-105">Verifique se a sua infraestrutura de identidade atende aos seguintes critérios necessários e que você considerou os que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="4856a-105">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="4856a-106">Confira também os [pré-requisitos](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) para obter outras recomendações de infraestrutura de identidade.</span><span class="sxs-lookup"><span data-stu-id="4856a-106">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="4856a-107">Obrigatório: as contas de administrador global estarem protegidas</span><span class="sxs-lookup"><span data-stu-id="4856a-107">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="4856a-108">Você [protegeu suas contas de administrador global do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) para impedir o comprometimento das credenciais por invasores, o que poderia levar a violações da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4856a-108">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="4856a-109">Se você ignorar esse requisito, suas contas de administrador global podem ficar suscetíveis a ataques e a serem comprometidas, permitindo que um invasor obtenha acesso a todo o sistema e colete, destrua ou utilize seus dados como colateral para pedir um resgate.</span><span class="sxs-lookup"><span data-stu-id="4856a-109">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="4856a-110">Se necessário, a [Etapa 1](identity-create-protect-global-admins.md#identity-global-admin) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="4856a-110">If needed, [Step 1](identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4856a-111">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-111">How to test</span></span>

<span data-ttu-id="4856a-112">Use estas etapas para verificar se você protegeu suas contas de administrador global:</span><span class="sxs-lookup"><span data-stu-id="4856a-112">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="4856a-113">Execute o comando a seguir do PowerShell do Azure Active Directory para Graph no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4856a-113">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="4856a-114">Você deverá ver apenas a lista de contas dedicadas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="4856a-114">You should see only the list of dedicated global administrator accounts.</span></span>
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="4856a-115">Entre no Office 365 usando cada uma das contas da Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="4856a-115">Sign in to Office 365 using each of the accounts from step 1.</span></span> <span data-ttu-id="4856a-116">Cada entrada deve exigir a Autenticação Multifator do Azure e a forma mais segura de autenticação secundária disponível em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4856a-116">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="4856a-117">Confira [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o Azure Active Directory PowerShell para o módulo do Graph e entrar no Office 365.</span><span class="sxs-lookup"><span data-stu-id="4856a-117">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="4856a-118">Opcional: você configurou o Privileged Identity Management para dar suporte à atribuição sob demanda da função de administrador global</span><span class="sxs-lookup"><span data-stu-id="4856a-118">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="4856a-119">Você usou as instruções em [Configurar o Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) para habilitar o PIM em seu locatário do Azure AD e configurou suas contas de administrador global como administradores qualificados.</span><span class="sxs-lookup"><span data-stu-id="4856a-119">You've used the instructions in [Configure Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="4856a-120">Você também deve usar as recomendações em [Proteger o acesso privilegiado para implantações híbridas e de nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para desenvolver um roteiro que proteja o acesso privilegiado contra ataques cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="4856a-120">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="4856a-121">Se você ignorar essa opção, as contas de administrador global estarão sujeitas a contínuos ataques cibernéticos e, se forem comprometidas, poderão permitir que um invasor colete, destrua ou use suas informações confidenciais para obter um resgate.</span><span class="sxs-lookup"><span data-stu-id="4856a-121">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="4856a-122">Se necessário, a [Etapa 1](identity-create-protect-global-admins.md#identity-pim) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-122">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="4856a-123">Opcional: ter configurado o gerenciamento de acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="4856a-123">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="4856a-124">Você usou as informações do tópico [Configurar gerenciamento de acesso privilegiado do Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar uma ou mais políticas de acesso privilegiado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4856a-124">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="4856a-125">Você configurou essas políticas e o acesso just-in-time está habilitado para acessar dados confidenciais ou configurações críticas.</span><span class="sxs-lookup"><span data-stu-id="4856a-125">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="4856a-126">Se necessário, a [Etapa 1](identity-create-protect-global-admins.md#identity-pam) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="4856a-126">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="4856a-127">Opcional: a proteção por senha do Azure AD estar proibindo o uso de senhas fracas</span><span class="sxs-lookup"><span data-stu-id="4856a-127">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="4856a-128">Você ativou a proibição de senhas ruins [na nuvem](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e para o [Active Directory Domain Services (AD DS) local](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) com base em senhas proibidas em geral e, opcionalmente, termos personalizados.</span><span class="sxs-lookup"><span data-stu-id="4856a-128">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="4856a-129">Se necessário, a [Etapa 2](identity-secure-your-passwords.md#identity-password-prot) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-129">If needed, [Step 2](identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="4856a-130">Opcional: os usuários podem redefinir suas próprias senhas</span><span class="sxs-lookup"><span data-stu-id="4856a-130">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="4856a-131">Você usou o artigo [Implantação rápida da redefinição da senha autoatendimento do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para configurar a redefinição de senha para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="4856a-131">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="4856a-132">Se você não atender a essa condição, os usuários dependerão dos administradores de contas de usuários para redefinir suas senhas, resultando em esforços adicionais para a administração de TI.</span><span class="sxs-lookup"><span data-stu-id="4856a-132">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="4856a-133">Se necessário, a [Etapa 2](identity-secure-your-passwords.md#identity-pw-reset) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-133">If needed, [Step 2](identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="4856a-134">Opcional: os usuários podem entrar usando o logon único contínuo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4856a-134">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="4856a-135">Você deve habilitar o [Azure AD Connect: Logon Único Simplificado](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) para sua organização para simplificar como os usuários entram em aplicativos baseados na nuvem, como o Office 365.</span><span class="sxs-lookup"><span data-stu-id="4856a-135">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="4856a-136">Se você ignorar essa opção, é possível que seus usuários sejam solicitados a fornecer credenciais quando acessarem outros aplicativos que usam seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4856a-136">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use you Azure AD tenant.</span></span>

<span data-ttu-id="4856a-137">Se necessário, a [Etapa 2](identity-secure-your-passwords.md#identity-sso) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-137">If needed, [Step 2](identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="4856a-138">Opcional: A tela de entrada do Office 365 ser personalizada para sua organização</span><span class="sxs-lookup"><span data-stu-id="4856a-138">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="4856a-139">Você deve usar o artigo [Adicionar a identidade visual da sua empresa às suas páginas de entrada e do Painel de Acesso](https://aka.ms/aadpaddbranding) para adicionar a identidade visual da sua organização à página de entrada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4856a-139">You have used [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="4856a-140">Se você ignorar essa opção, os usuários verão uma tela genérica de entrada do Office 365 e poderão não ter a confiança de que estão entrando no site da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4856a-140">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="4856a-141">Se necessário, a [Etapa 2](identity-secure-your-passwords.md#identity-custom-sign-in) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-141">If needed, [Step 2](identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="4856a-142">Opcional: a Autenticação Multifator do Azure estar habilitada para seus usuários</span><span class="sxs-lookup"><span data-stu-id="4856a-142">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="4856a-143">Você usou o [Plano para Autenticação Multifator do Azure](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) e [Políticas de Acesso Condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) para habilitar a MFA (Autenticação Multifator) do Azure em suas contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="4856a-143">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="4856a-p104">Se você ignorar essa opção, as contas de usuários ficarão vulneráveis a terem suas credenciais comprometidas por invasores cibernéticos. Se a senha de uma conta de usuário for comprometida, todos os recursos dessa conta, como funções de administrador, estarão disponíveis para o invasor. Isso permitirá que invasor copie, destrua ou use seus documentos internos e outros dados para pedir resgate.</span><span class="sxs-lookup"><span data-stu-id="4856a-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="4856a-147">Se necessário, a [Etapa 3](identity-secure-user-sign-ins.md#identity-mfa) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-147">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4856a-148">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-148">How to test</span></span>

1.  <span data-ttu-id="4856a-149">Crie uma conta de usuário de teste e atribua uma licença a ela.</span><span class="sxs-lookup"><span data-stu-id="4856a-149">Create a test user account and assign them a license.</span></span> 
2.  <span data-ttu-id="4856a-150">Configure a Autenticação Multifator do Azure para essa conta de usuário de teste com o método de verificação adicional que você estiver usando para as contas de usuário reais, como enviar uma mensagem de texto para um celular.</span><span class="sxs-lookup"><span data-stu-id="4856a-150">Configure Azure Multi-Factor Authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a text message to your phone.</span></span> 
3.  <span data-ttu-id="4856a-151">Entre no portal do Office 365 com a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-151">Sign in to the Office 36 portal with the test user account.</span></span>
4.  <span data-ttu-id="4856a-152">Confira se a MFA solicita informações adicionais de verificação e resulta em uma autenticação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="4856a-152">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="4856a-153">Exclua a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-153">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-e5-only"></a><span data-ttu-id="4856a-154">Opcional: a Proteção de Identidade do Azure AD ser ativada para proteger você contra o comprometimento de credenciais (Microsoft 365 Enterprise E5 apenas)</span><span class="sxs-lookup"><span data-stu-id="4856a-154">Optional: Azure AD Identity Protection is enabled to protect against credential compromise (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="4856a-155">Você ativou o Azure AD Identity Protection para:</span><span class="sxs-lookup"><span data-stu-id="4856a-155">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="4856a-156">Solucionar possíveis vulnerabilidades de identidade.</span><span class="sxs-lookup"><span data-stu-id="4856a-156">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="4856a-157">Detectar possíveis tentativas de ataque à credencial.</span><span class="sxs-lookup"><span data-stu-id="4856a-157">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="4856a-158">Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.</span><span class="sxs-lookup"><span data-stu-id="4856a-158">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="4856a-p105">Se você ignorar essa opção, não poderá detectar ou automaticamente eliminar tentativas de comprometer a identidade ou investigar incidentes de segurança relacionado à identidade. Isso possivelmente deixa sua organização vulnerável a ter sua identidade comprometida e à ameaça resultante aos dados confidenciais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4856a-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="4856a-161">Se necessário, a [Etapa 3](identity-secure-user-sign-ins.md#identity-ident-prot) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-161">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="4856a-162">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-162">How to test</span></span>

1. <span data-ttu-id="4856a-163">Crie uma conta de usuário de teste com uma senha inicial.</span><span class="sxs-lookup"><span data-stu-id="4856a-163">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="4856a-164">Use as etapas em [Permitir que os usuários redefinam suas próprias senhas no Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) para redefinir a senha da conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-164">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="4856a-165">Saia e entre novamente na conta de usuário de teste usando a senha redefinida.</span><span class="sxs-lookup"><span data-stu-id="4856a-165">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="4856a-166">Exclua a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-166">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="4856a-167">Obrigatório para a identidade híbrida: os usuários e os grupos devem estar sincronizados com o Azure AD</span><span class="sxs-lookup"><span data-stu-id="4856a-167">Required for hybrid identity: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="4856a-168">Se você tiver um Active Directory Domain Services (AD DS) local, é porque você usou o Azure AD Connect para sincronizar as contas de usuário e os grupos de seu AD DS local com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4856a-168">If you have an existing on-premises Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises AD DS to your Azure AD tenant.</span></span>

<span data-ttu-id="4856a-169">Com a sincronização de diretórios, seus usuários poderão entrar no Office 365 e em outros serviços de nuvem da Microsoft usando as mesmas credenciais que usam para entrar em seus computadores e acessar os recursos locais.</span><span class="sxs-lookup"><span data-stu-id="4856a-169">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="4856a-170">Se necessário, a [Etapa 4](identity-add-user-accounts.md#identity-sync) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="4856a-170">If needed, [Step 4](identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="4856a-171">Se ignorar esse requisito, você terá dois conjuntos de contas de usuários e grupos:</span><span class="sxs-lookup"><span data-stu-id="4856a-171">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="4856a-172">Contas de usuários e grupos existentes no seu AD DS local</span><span class="sxs-lookup"><span data-stu-id="4856a-172">User accounts and groups that exist in your on-premises AD DS</span></span>
- <span data-ttu-id="4856a-173">Contas de usuários e grupos existentes em seu locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="4856a-173">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="4856a-p106">Nesse estado, os dois conjuntos de contas de usuários e grupos devem ser mantidos manualmente pelos administradores de TI e os usuários. Isso inevitavelmente levará a contas, senhas e grupos não sincronizados.</span><span class="sxs-lookup"><span data-stu-id="4856a-p106">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4856a-176">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-176">How to test</span></span>
<span data-ttu-id="4856a-177">Para verificar se a autenticação com credenciais locais funciona corretamente, entre no portal do Office com suas credenciais locais.</span><span class="sxs-lookup"><span data-stu-id="4856a-177">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="4856a-178">Para verificar se a sincronização de diretórios está funcionando corretamente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4856a-178">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="4856a-179">Crie um novo grupo de teste no AD DS.</span><span class="sxs-lookup"><span data-stu-id="4856a-179">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="4856a-180">Aguarde o tempo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="4856a-180">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="4856a-181">Confira se o nome do novo grupo de teste aparece no seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4856a-181">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="4856a-182">Opcional: A sincronização de diretórios ser monitorada</span><span class="sxs-lookup"><span data-stu-id="4856a-182">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="4856a-183">Você deve usar o artigo [Azure AD Connect Health com sincronização](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (para sincronização de senhas) ou [Usar o Azure AD Connect Health com o AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (para autenticação federada) e implantar o Azure AD Connect Health, que envolve:</span><span class="sxs-lookup"><span data-stu-id="4856a-183">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="4856a-184">Instalar o agente do Azure AD Connect Health em cada servidor de identidade local.</span><span class="sxs-lookup"><span data-stu-id="4856a-184">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="4856a-185">Usar o portal do Azure AD Connect Health para monitorar o estado da sincronização em andamento.</span><span class="sxs-lookup"><span data-stu-id="4856a-185">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="4856a-186">Se ignorar essa opção, você poderá avaliar com mais precisão o estado da sua infraestrutura de identidade de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4856a-186">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="4856a-187">Se necessário, a [Etapa 4](identity-add-user-accounts.md#identity-sync-health) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-187">If needed, [Step 4](identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4856a-188">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-188">How to test</span></span>
<span data-ttu-id="4856a-189">O portal do Azure AD Connect Health mostra o estado atual e correto dos seus controladores de domínio locais e da sincronização em andamento.</span><span class="sxs-lookup"><span data-stu-id="4856a-189">The Azure AD Connect Health portal shows the current and correct state of your on-premises domain controllers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="4856a-190">Opcional: O write-back de senha estar habilitado para seus usuários</span><span class="sxs-lookup"><span data-stu-id="4856a-190">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="4856a-191">Você usou as instruções em [Azure AD SSPR com write-back de senha](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para habilitar o write-back de senha para o locatário do Azure AD da sua assinatura do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4856a-191">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="4856a-192">Se você ignorar essa opção, os usuários que não estiverem conectados à sua rede local deverão redefinir ou desbloquear as senhas do AD DS por meio do administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="4856a-192">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="4856a-193">Se necessário, a [Etapa 4](identity-add-user-accounts.md#identity-pw-writeback) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-193">If needed, [Step 4](identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="4856a-194">O write-back de senha é necessário para utilizar por completo os recursos do Azure AD Identity Protection, por exemplo, para solicitar que os usuários alterem suas senhas locais quando o Azure AD detectar um comprometimento de conta de alto risco.</span><span class="sxs-lookup"><span data-stu-id="4856a-194">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="4856a-195">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-195">How to test</span></span>

<span data-ttu-id="4856a-196">Para testar o write-back de senha, você deverá alterar sua senha no Office 365.</span><span class="sxs-lookup"><span data-stu-id="4856a-196">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="4856a-197">Você deve conseguir usar sua conta e a nova senha para acessar os recursos do AD DS local.</span><span class="sxs-lookup"><span data-stu-id="4856a-197">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="4856a-198">Crie uma conta de usuário de teste no AD DS local, permita que a sincronização de diretórios ocorra e, em seguida, conceda uma licença do Microsoft 365 Enterprise no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4856a-198">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it a Microsoft 365 Enterprise license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="4856a-199">Em um computador remoto ingressado no domínio do AD DS local, entre no computador e no portal do Office usando as credenciais da conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-199">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="4856a-200">Selecione **Configurações > Configurações do Office 365 > Senha > Alterar senha**.</span><span class="sxs-lookup"><span data-stu-id="4856a-200">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="4856a-201">Digite a senha atual, digite uma nova senha e a confirme.</span><span class="sxs-lookup"><span data-stu-id="4856a-201">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="4856a-202">Saia do portal do Office e do computador remoto e, em seguida, entre no computador usando a conta de usuário de teste e a nova senha.</span><span class="sxs-lookup"><span data-stu-id="4856a-202">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="4856a-203">Isso prova que você conseguiu mudar a senha de uma conta de usuário do AD DS local usando o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4856a-203">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4856a-204">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-204">How to test</span></span>

<span data-ttu-id="4856a-205">Entre no portal do Office 365 com o nome da sua conta de usuário e a Autenticação Multifator do Azure.</span><span class="sxs-lookup"><span data-stu-id="4856a-205">Sign in to the Office 365 portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="4856a-206">Você deverá ver seus elementos personalizados com identidade visual na página de entrada.</span><span class="sxs-lookup"><span data-stu-id="4856a-206">You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="4856a-207">Opcional: O gerenciamento de grupos por autoatendimento estar habilitado para grupos específicos de segurança do Azure AD e do Office 365</span><span class="sxs-lookup"><span data-stu-id="4856a-207">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="4856a-208">Você deve determinar quais grupos são adequados para o gerenciamento por autoatendimento, instruir seus proprietários sobre o fluxo de trabalho e as responsabilidades do gerenciamento de grupos e [configurar o gerenciamento por autoatendimento no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) para esses grupos.</span><span class="sxs-lookup"><span data-stu-id="4856a-208">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="4856a-209">Se você ignorar essa opção, todas as tarefas de gerenciamento de grupos do Azure AD deverão ser realizadas por administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="4856a-209">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="4856a-210">Se necessário, a [Etapa 5](identity-use-group-management.md#identity-self-service-groups) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-210">If needed, [Step 5](identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4856a-211">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-211">How to test</span></span>
1.  <span data-ttu-id="4856a-212">Crie uma conta de usuário de teste no Azure AD com o portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="4856a-212">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="4856a-213">Entre como com a conta de usuário de teste e crie um grupo de segurança de teste do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4856a-213">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="4856a-214">Saia e, em seguida, entre novamente com sua conta de administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="4856a-214">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="4856a-215">Configure o grupo de segurança de teste para o gerenciamento por autoatendimento para a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-215">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="4856a-216">Saia e, em seguida, entre novamente com sua conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-216">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="4856a-217">Use o portal do Azure para adicionar membros ao grupo de segurança de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-217">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="4856a-218">Exclua o grupo de segurança de teste e a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-218">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="4856a-219">Opcional: As configurações de associação de grupo dinâmicas automaticamente adicionarem contas de usuário a grupos com base nos atributos da conta de usuário</span><span class="sxs-lookup"><span data-stu-id="4856a-219">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="4856a-220">Você deve determinar o conjunto de grupos dinâmicos do Azure AD e usar as instruções no artigo [Associação em grupo dinâmica com base em atributos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) para criar os grupos e as regras que determinam o conjunto de atributos de conta de usuário e os grupos e valores de associação em grupos.</span><span class="sxs-lookup"><span data-stu-id="4856a-220">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="4856a-p110">Se você ignorar essa opção, a associação em grupos deverá ser feita manualmente conforme novas contas forem adicionadas ou conforme os atributos de contas de usuários mudarem ao longo do tempo. Por exemplo, se alguém passar do departamento de vendas para o departamento de contabilidade, você deverá:</span><span class="sxs-lookup"><span data-stu-id="4856a-p110">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="4856a-223">Atualizar o valor do atributo Departamento dessa conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="4856a-223">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="4856a-224">Remover o usuário manualmente do grupo Vendas.</span><span class="sxs-lookup"><span data-stu-id="4856a-224">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="4856a-225">Adicionar o usuário manualmente ao grupo Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="4856a-225">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="4856a-226">Se os grupos Vendas e Contabilidade fossem dinâmicos, você só precisaria alterar o valor Departamento da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="4856a-226">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="4856a-227">Se necessário, a [Etapa 5](identity-use-group-management.md#identity-dyn-groups) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-227">If needed, [Step 5](identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4856a-228">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-228">How to test</span></span>

1. <span data-ttu-id="4856a-229">Crie um grupo dinâmico de teste no Azure AD com o portal do Azure e configure uma regra para o Departamento igual a "teste1".</span><span class="sxs-lookup"><span data-stu-id="4856a-229">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="4856a-230">Crie uma conta de usuário de teste no Azure AD e defina a propriedade Departamento como "teste1".</span><span class="sxs-lookup"><span data-stu-id="4856a-230">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="4856a-231">Examine as propriedades da conta do usuário para garantir que ele tenha se tornado membro do grupo dinâmico de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-231">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="4856a-232">Altere o valor da propriedade Departamento da conta de usuário de teste para "teste2".</span><span class="sxs-lookup"><span data-stu-id="4856a-232">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="4856a-233">Examine as propriedades da conta do usuário para garantir que ele não seja mais membro do grupo dinâmico de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-233">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="4856a-234">Exclua o grupo dinâmico de teste e a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-234">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="4856a-235">Opcional: licenciamento baseado em grupo para automaticamente atribuir e remover licenças a contas de usuário de acordo com sua associação em grupos</span><span class="sxs-lookup"><span data-stu-id="4856a-235">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="4856a-236">Você [habilitou o licenciamento baseado em grupos](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) para os grupos de segurança apropriados do Azure AD para que as licenças do Microsoft Office 365 Enterprise sejam atribuídas ou tenham a atribuição cancelada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4856a-236">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that your Microsoft 365 Enterprise licenses are automatically assigned or unassigned.</span></span>

<span data-ttu-id="4856a-237">Se você ignorar essa opção, será preciso realizar as seguintes tarefas manualmente:</span><span class="sxs-lookup"><span data-stu-id="4856a-237">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="4856a-238">Atribuir licenças a novos usuários para os quais você pretende conceder acesso.</span><span class="sxs-lookup"><span data-stu-id="4856a-238">Assign licenses to new users whom you intend to have access.</span></span>
- <span data-ttu-id="4856a-239">Cancelar a atribuição de licenças de usuários que não estejam mais trabalhando com sua organização ou que não tenham acesso.</span><span class="sxs-lookup"><span data-stu-id="4856a-239">Unassign licenses from users who are no longer with your organization or do not have access.</span></span>

<span data-ttu-id="4856a-240">Se necessário, a [Etapa 5](identity-use-group-management.md#identity-group-license) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-240">If needed, [Step 5](identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4856a-241">Como testar</span><span class="sxs-lookup"><span data-stu-id="4856a-241">How to test</span></span>

1. <span data-ttu-id="4856a-242">Crie um grupo de segurança de teste no Azure AD com o portal do Azure e configure o licenciamento baseado em grupo para atribuir licenças do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4856a-242">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Microsoft 365 Enterprise license.</span></span>
2. <span data-ttu-id="4856a-243">Crie uma conta de usuário de teste no Azure AD e adicione-a ao grupo de segurança de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-243">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="4856a-244">Examine as propriedades da conta de usuário no centro de administração do Microsoft 365 para garantir que a licença do Microsoft 365 Enterprise tenha sido atribuída a ela.</span><span class="sxs-lookup"><span data-stu-id="4856a-244">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Microsoft 365 Enterprise license.</span></span>
4. <span data-ttu-id="4856a-245">Remova a conta de usuário de teste do grupo de segurança de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-245">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="4856a-246">Examine as propriedades da conta de usuário para garantir que a licença do Microsoft 365 Enterprise não esteja mais atribuída a ela.</span><span class="sxs-lookup"><span data-stu-id="4856a-246">Examine the properties of the user account to ensure that it no longer has the Microsoft 365 Enterprise license assigned.</span></span>
6. <span data-ttu-id="4856a-247">Exclua o grupo de segurança de teste e a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="4856a-247">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="4856a-248">Opcional: revisões de acesso configuradas e usadas para monitorar o acesso</span><span class="sxs-lookup"><span data-stu-id="4856a-248">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="4856a-249">Você usou esses artigos para configurar diferentes tipos de revisões de acesso para monitorar associações a grupos, acesso a aplicativos corporativos e atribuições de funções:</span><span class="sxs-lookup"><span data-stu-id="4856a-249">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="4856a-250">Grupos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="4856a-250">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="4856a-251">Funções do Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4856a-251">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="4856a-252">Funções de recurso do Azure</span><span class="sxs-lookup"><span data-stu-id="4856a-252">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="4856a-253">Se necessário, a [Etapa 6](identity-configure-identity-governance.md#identity-access-reviews) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="4856a-253">If needed, [Step 6](identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>


## <a name="results-and-next-steps"></a><span data-ttu-id="4856a-254">Resultados e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4856a-254">Results and next steps</span></span>

<span data-ttu-id="4856a-255">Sua infraestrutura de identidade na nuvem do Microsoft 365 usa autenticação forte, contas de administrador protegidas e acesso de usuário e gerenciamento simplificados.</span><span class="sxs-lookup"><span data-stu-id="4856a-255">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="4856a-257">Se você está seguindo as fases para a implantação de ponta a ponta do Microsoft 365 Enterprise, sua próxima fase é [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="4856a-257">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

