---
title: 'Fase 2: Critérios de saída da infraestrutura de identidade'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Garanta que a sua configuração atenda aos critérios do Microsoft 365 Enterprise para a infraestrutura e os serviços baseados em identidade.
ms.openlocfilehash: 49ba7801b740b2a1cfd77955517646ee80174712
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865283"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="5073c-103">Fase 2: Critérios de saída da infraestrutura de identidade</span><span class="sxs-lookup"><span data-stu-id="5073c-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5073c-p101">Antes de prosseguir para a Fase 3, verifique se a sua infraestrutura de identidade atende a estas condições. Confira também os [pré-requisitos](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) para obter recomendações adicionais sobre a infraestrutura de identidade.</span><span class="sxs-lookup"><span data-stu-id="5073c-p101">Before you move on to Phase 3, make sure that your identity infrastructure meets these conditions. Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-all-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="5073c-106">Obrigatório: Todos os usuários, grupos e membros de grupos terem sido criados</span><span class="sxs-lookup"><span data-stu-id="5073c-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="5073c-107">Você deve ter criado contas e grupos de usuários para que:</span><span class="sxs-lookup"><span data-stu-id="5073c-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="5073c-108">Os funcionários da sua organização e os fornecedores, prestadores de serviços e parceiros que trabalham para ou com a sua organização tenham uma conta de usuário correspondente no Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="5073c-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (AD).</span></span>
- <span data-ttu-id="5073c-109">Os grupos do Azure AD e seus membros tenham contas de usuários e outros grupos para diversos propósitos, como o provisionamento de configurações de segurança de serviços de nuvem da Microsoft, o licenciamento automático e outros usos.</span><span class="sxs-lookup"><span data-stu-id="5073c-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="5073c-110">Se necessário, a [Etapa 1](identity-plan-users-groups.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="5073c-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="5073c-111">Obrigatório: Usuários e grupos estarem sincronizados com o Azure AD</span><span class="sxs-lookup"><span data-stu-id="5073c-111">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="5073c-112">Se você tiver um provedor de identidade local existente, como o Windows Server Active Directory (AD), é necessário usar o Azure AD Connect para sincronizar contas de usuários e grupos do provedor de identidade local para seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5073c-112">If you have an existing on-premises identity provider, such as Windows Server Active Directory (AD), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="5073c-113">Com a sincronização de diretórios, seus usuários poderão entrar no Office 365 e em outros serviços de nuvem da Microsoft usando as mesmas credenciais que usam para entrar em seus computadores e acessar os recursos locais.</span><span class="sxs-lookup"><span data-stu-id="5073c-113">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="5073c-114">Se necessário, a [Etapa 7](identity-azure-ad-connect.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="5073c-114">If needed, [Step 7](identity-azure-ad-connect.md) can help you meet this requirement.</span></span>

<span data-ttu-id="5073c-115">Se ignorar esse requisito, você terá dois conjuntos de contas de usuários e grupos:</span><span class="sxs-lookup"><span data-stu-id="5073c-115">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="5073c-116">Contas de usuários e grupos existentes no seu provedor de identidade local</span><span class="sxs-lookup"><span data-stu-id="5073c-116">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="5073c-117">Contas de usuários e grupos existentes em seu locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="5073c-117">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="5073c-p102">Nesse estado, os dois conjuntos de contas de usuários e grupos devem ser mantidos manualmente pelos administradores de TI e os usuários. Isso inevitavelmente levará a contas, senhas e grupos não sincronizados.</span><span class="sxs-lookup"><span data-stu-id="5073c-p102">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5073c-120">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-120">How to test</span></span>
<span data-ttu-id="5073c-121">Para verificar se a autenticação com credenciais locais funciona corretamente, entre no portal do Office 365 com suas credenciais locais.</span><span class="sxs-lookup"><span data-stu-id="5073c-121">To verify that authentication with on-premises credentials works correctly, sign in to the Office 365 portal with your on-premises credentials.</span></span>

<span data-ttu-id="5073c-122">Para verificar se a sincronização de diretórios está funcionando corretamente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5073c-122">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="5073c-123">Crie um novo grupo de teste no Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="5073c-123">Create a new test group in Windows Server AD.</span></span>
2.  <span data-ttu-id="5073c-124">Aguarde o tempo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="5073c-124">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="5073c-125">Confira se o nome do novo grupo de teste aparece no seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5073c-125">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="5073c-126">Obrigatório: As contas de administrador global estarem protegidas</span><span class="sxs-lookup"><span data-stu-id="5073c-126">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="5073c-127">Você [protegeu suas contas de administrador global do Office 365](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) para evitar credenciais comprometidas que podem causar violações de uma assinatura do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5073c-127">You've [protected your Office 365 global administrator accounts](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) to avoid compromising credentials that can lead to breaches of an Office 365 subscription.</span></span>

<span data-ttu-id="5073c-128">Se você ignorar esse requisito, suas contas de administrador global podem ficar suscetíveis a ataques e a serem comprometidas, permitindo que um invasor obtenha acesso a todo o sistema e colete, destrua ou utilize seus dados como colateral para pedir um resgate.</span><span class="sxs-lookup"><span data-stu-id="5073c-128">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="5073c-129">Se necessário, a [Etapa 2](identity-designate-protect-admin-accounts.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="5073c-129">If needed, [Step 2](identity-designate-protect-admin-accounts.md) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5073c-130">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-130">How to test</span></span>

<span data-ttu-id="5073c-131">Use estas etapas para verificar se você protegeu suas contas de administrador global:</span><span class="sxs-lookup"><span data-stu-id="5073c-131">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="5073c-p103">Execute o seguinte comando do Azure AD V2 no prompt de comando do PowerShell. Você verá somente a lista de contas de administradores globais dedicados.</span><span class="sxs-lookup"><span data-stu-id="5073c-p103">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="5073c-p104">Entre no Office 365 usando a cada uma das contas da etapa 1. Cada entrada deve exigir a autenticação multifator e a forma mais segura de autenticação secundária disponível em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5073c-p104">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="5073c-136">Veja [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o módulo Azure AD V2 PowerShell e entrar no Office 365.</span><span class="sxs-lookup"><span data-stu-id="5073c-136">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in to Office 365.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="5073c-137">Opcional: A tela de entrada do Office 365 ser personalizada para sua organização</span><span class="sxs-lookup"><span data-stu-id="5073c-137">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="5073c-138">Você deve usar o artigo [Adicionar a identidade visual da sua empresa às suas páginas de entrada e do Painel de Acesso](http://aka.ms/aadpaddbranding) para adicionar a identidade visual da sua organização à página de entrada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5073c-138">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="5073c-139">Se você ignorar essa opção, os usuários verão uma tela genérica de entrada do Office 365 e poderão não ter a confiança de que estão entrando no site da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5073c-139">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="5073c-140">Se necessário, a [Etapa 11](identity-customize-office-365-sign-in.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-140">If needed, [Step 11](identity-customize-office-365-sign-in.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5073c-141">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-141">How to test</span></span>

<span data-ttu-id="5073c-p105">Entre no portal do Office 365 com o nome da sua conta de usuário e a autenticação multifator. Você verá seus elementos de identidade visual personalizados na página de entrada.</span><span class="sxs-lookup"><span data-stu-id="5073c-p105">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="5073c-144">Opcional: A autenticação multifator estar habilitada para seus usuários</span><span class="sxs-lookup"><span data-stu-id="5073c-144">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="5073c-145">Você deve usar os artigos [Planejar a autenticação multifator para implantações do Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) e [Configurar a autenticação multifator para usuários do Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) para habilitar a autenticação multifator (MFA) para suas contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="5073c-145">You used [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) and [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) to enable multifactor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="5073c-p106">Se você ignorar essa opção, as contas de usuários ficarão vulneráveis a terem suas credenciais comprometidas por invasores cibernéticos. Se a senha de uma conta de usuário for comprometida, todos os recursos dessa conta, como funções de administrador, estarão disponíveis para o invasor. Isso permitirá que invasor copie, destrua ou use seus documentos internos e outros dados para pedir resgate.</span><span class="sxs-lookup"><span data-stu-id="5073c-p106">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="5073c-149">Se necessário, a [Etapa 5](identity-multi-factor-authentication.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-149">If needed, [Step 5](identity-multi-factor-authentication.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5073c-150">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-150">How to test</span></span>

1.  <span data-ttu-id="5073c-151">Crie uma conta de usuário de teste no portal do administrador do Office 365 e atribua uma licença a ela.</span><span class="sxs-lookup"><span data-stu-id="5073c-151">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="5073c-152">Configure a autenticação multifator para essa conta de usuário de teste com o método de verificação adicional que você estiver usando para as contas de usuário reais, como enviar uma mensagem para um celular.</span><span class="sxs-lookup"><span data-stu-id="5073c-152">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="5073c-153">Entre no portal do Office 365 ou do Azure com a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-153">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="5073c-154">Confira se a MFA solicita informações adicionais de verificação e resulta em uma autenticação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="5073c-154">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="5073c-155">Exclua a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-155">Delete the test user account.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="5073c-156">Opcional: A sincronização de diretórios ser monitorada</span><span class="sxs-lookup"><span data-stu-id="5073c-156">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="5073c-157">Você deve usar o artigo [Azure AD Connect Health com sincronização](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (para sincronização de senhas) ou [Usar o Azure AD Connect Health com o AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (para autenticação federada) e implantar o Azure AD Connect Health, que envolve:</span><span class="sxs-lookup"><span data-stu-id="5073c-157">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="5073c-158">Instalar o agente do Azure AD Connect Health em cada servidor de identidade local.</span><span class="sxs-lookup"><span data-stu-id="5073c-158">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="5073c-159">Usar o portal do Azure AD Connect Health para monitorar o estado da sincronização em andamento.</span><span class="sxs-lookup"><span data-stu-id="5073c-159">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="5073c-160">Se ignorar essa opção, você poderá avaliar com mais precisão o estado da sua infraestrutura de identidade de nuvem.</span><span class="sxs-lookup"><span data-stu-id="5073c-160">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="5073c-161">Se necessário, a [Etapa 8](identity-azure-ad-connect-health.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-161">If needed, [Step 8](identity-azure-ad-connect-health.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5073c-162">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-162">How to test</span></span>
<span data-ttu-id="5073c-163">O portal do Azure AD Connect Health mostra o estado atual e correto dos seus servidores de identidade locais e da sincronização em andamento.</span><span class="sxs-lookup"><span data-stu-id="5073c-163">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="5073c-164">Opcional: os usuários podem redefinir suas próprias senhas</span><span class="sxs-lookup"><span data-stu-id="5073c-164">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="5073c-165">Você usou o artigo [Implantação rápida da redefinição da senha autoatendimento do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para configurar a redefinição de senha para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="5073c-165">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="5073c-166">Se você não atender a essa condição, os usuários dependerão dos administradores de contas de usuários para redefinir suas senhas, resultando em esforços adicionais para a administração de TI.</span><span class="sxs-lookup"><span data-stu-id="5073c-166">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="5073c-167">Se necessário, a [Etapa 4](identity-password-reset.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-167">If needed, [Step 4](identity-password-reset.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5073c-168">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-168">How to test</span></span>

1. <span data-ttu-id="5073c-169">Crie uma conta de usuário de teste com uma senha inicial.</span><span class="sxs-lookup"><span data-stu-id="5073c-169">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="5073c-170">Use as etapas em [Permitir que os usuários redefinam suas próprias senhas no Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) para redefinir a senha da conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-170">Use the steps in [Let users reset their own passwords in Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="5073c-171">Saia e entre novamente na conta de usuário de teste usando a senha redefinida.</span><span class="sxs-lookup"><span data-stu-id="5073c-171">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="5073c-172">Exclua a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-172">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="5073c-173">Opcional: O write-back de senha estar habilitado para seus usuários</span><span class="sxs-lookup"><span data-stu-id="5073c-173">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="5073c-174">Você usou as instruções em [Azure AD SSPR com write-back de senha](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para habilitar o write-back de senha para o locatário do Azure AD da sua assinatura do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5073c-174">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="5073c-175">Se você ignorar essa opção, os usuários que não estiverem conectados à sua rede local deverão redefinir ou desbloquear suas senhas do Windows Server AD por intermédio de um administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="5073c-175">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their Windows Server AD passwords through an IT administrator.</span></span>

<span data-ttu-id="5073c-176">Se necessário, a [Etapa 9](identity-password-writeback.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-176">If needed, [Step 9](identity-password-writeback.md) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="5073c-177">O write-back de senha é necessário para utilizar por completo os recursos do Azure AD Identity Protection, por exemplo, para solicitar que os usuários alterem suas senhas locais quando o Azure AD detectar um comprometimento de conta de alto risco.</span><span class="sxs-lookup"><span data-stu-id="5073c-177">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="5073c-178">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-178">How to test</span></span>

<span data-ttu-id="5073c-p107">Teste o write-back de senha alterando sua senha no Office 365. Você deve poder usar sua conta e a nova senha para acessar os recursos do Windows Server AD local.</span><span class="sxs-lookup"><span data-stu-id="5073c-p107">You test password writeback by changing your password in Office 365. You should be able to use your account and new password to access on-premises Windows Server AD resources.</span></span>

1. <span data-ttu-id="5073c-181">Crie uma conta de usuário de teste no seu Windows Server AD local, permita a sincronização de diretórios e conceda a essa conta uma licença do Office 365 no portal de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5073c-181">Create a test user account in your on-premises Windows Server AD, allow directory synchronization to occur, and then grant it an Office 365 license in the Office 365 admin portal.</span></span>
2. <span data-ttu-id="5073c-182">Em um computador remoto associado ao domínio do Windows Server AD local, entre no computador e no portal do Office 365 usando as credenciais da conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-182">From a remote computer that is joined to your on-premises Windows Server AD domain, sign in to the computer and the Office 365 portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="5073c-183">Selecione **Configurações > Configurações do Office 365 > Senha > Alterar senha**.</span><span class="sxs-lookup"><span data-stu-id="5073c-183">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="5073c-184">Digite a senha atual, digite uma nova senha e a confirme.</span><span class="sxs-lookup"><span data-stu-id="5073c-184">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="5073c-p108">Saia do portal do Office 365 e do computador remoto e, em seguida, entre no computador usando a conta de usuário de teste e a nova senha. Isso prova que você conseguiu alterar a senha de uma conta de usuário do Windows Server AD usando o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5073c-p108">Sign out of the Office 365 portal and the remote computer and then sign in to the computer using the test user account and its new password. This proves that you were able to change the password of an on-premises Windows Server AD user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-single-sign-on"></a><span data-ttu-id="5073c-187">Opcional: Os usuários poderem entrar usando logon único</span><span class="sxs-lookup"><span data-stu-id="5073c-187">Optional: Users can sign in using single sign-on</span></span>

<span data-ttu-id="5073c-188">Você deve habilitar o [Azure AD Connect: Logon Único Simplificado](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) para sua organização para simplificar como os usuários entram em aplicativos baseados na nuvem, como o Office 365.</span><span class="sxs-lookup"><span data-stu-id="5073c-188">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="5073c-189">Se você ignorar essa opção, seus usuários poderão ser solicitados a fornecer credenciais quando acessarem outros aplicativos que usam o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5073c-189">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="5073c-190">Se necessário, a [Etapa 10](identity-single-sign-on.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-190">If needed, [Step 10](identity-single-sign-on.md) can help you with this option.</span></span>


<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="5073c-191">Opcional: licenciamento baseado em grupo para automaticamente atribuir e remover licenças a contas de usuário de acordo com sua associação em grupos</span><span class="sxs-lookup"><span data-stu-id="5073c-191">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="5073c-192">Você deve [habilitar o licenciamento baseado em grupos](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) para os grupos de segurança apropriados do Azure AD para que as licenças do Office 365 e EMS sejam atribuídas ou removidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5073c-192">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="5073c-193">Se você ignorar essa opção, será preciso realizar as seguintes tarefas manualmente:</span><span class="sxs-lookup"><span data-stu-id="5073c-193">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="5073c-194">Atribuir licenças a novos usuários para os quais você pretende conceder acesso ao Office 365 e EMS.</span><span class="sxs-lookup"><span data-stu-id="5073c-194">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="5073c-195">Remover licenças de usuários que não estejam mais trabalhando com sua organização ou que não tenham acesso ao Office 365 e EMS.</span><span class="sxs-lookup"><span data-stu-id="5073c-195">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="5073c-196">Se necessário, a [Etapa 12](identity-group-based-licensing.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-196">If needed, [Step 12](identity-group-based-licensing.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5073c-197">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-197">How to test</span></span>

1. <span data-ttu-id="5073c-198">Crie um grupo de segurança de teste no Azure AD com o portal do Azure e configure o licenciamento baseado em grupo para atribuir licenças do Office 365 e do EMS.</span><span class="sxs-lookup"><span data-stu-id="5073c-198">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="5073c-199">Crie uma conta de usuário de teste no Azure AD e adicione-o ao grupo de segurança de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-199">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="5073c-200">Examine as propriedades da conta de usuário no portal de administração do Office 365 para garantir que ela tenha recebido as licenças do Office 365 e do EMS.</span><span class="sxs-lookup"><span data-stu-id="5073c-200">Examine the properties of the user account in the Office 365 admin portal to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="5073c-201">Remova a conta de usuário de teste do grupo de segurança de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-201">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="5073c-202">Examine as propriedades da conta de usuário para garantir que ela não tenha mais as licenças do Office 365 e do EMS.</span><span class="sxs-lookup"><span data-stu-id="5073c-202">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="5073c-203">Exclua o grupo de segurança de teste e a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-203">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="5073c-204">Opcional: As configurações de associação de grupo dinâmicas automaticamente adicionarem contas de usuário a grupos com base nos atributos da conta de usuário</span><span class="sxs-lookup"><span data-stu-id="5073c-204">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="5073c-205">Você deve determinar o conjunto de grupos dinâmicos do Azure AD e usar as instruções no artigo [Associação em grupo dinâmica com base em atributos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) para criar os grupos e as regras que determinam o conjunto de atributos de conta de usuário e os grupos e valores de associação em grupos.</span><span class="sxs-lookup"><span data-stu-id="5073c-205">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="5073c-p109">Se você ignorar essa opção, a associação em grupos deverá ser feita manualmente conforme novas contas forem adicionadas ou conforme os atributos de contas de usuários mudarem ao longo do tempo. Por exemplo, se alguém passar do departamento de vendas para o departamento de contabilidade, você deverá:</span><span class="sxs-lookup"><span data-stu-id="5073c-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="5073c-208">Atualizar o valor do atributo Departamento dessa conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="5073c-208">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="5073c-209">Remover o usuário manualmente do grupo Vendas.</span><span class="sxs-lookup"><span data-stu-id="5073c-209">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="5073c-210">Adicionar o usuário manualmente ao grupo Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="5073c-210">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="5073c-211">Se os grupos Vendas e Contabilidade fossem dinâmicos, você só precisaria alterar o valor Departamento da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="5073c-211">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="5073c-212">Se necessário, a [Etapa 15](identity-automatic-group-membership.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-212">If needed, [Step 15](identity-automatic-group-membership.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5073c-213">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-213">How to test</span></span>

1. <span data-ttu-id="5073c-214">Crie um grupo dinâmico de teste no Azure AD com o portal do Azure e configure uma regra para o Departamento igual a "teste1".</span><span class="sxs-lookup"><span data-stu-id="5073c-214">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="5073c-215">Crie uma conta de usuário de teste no Azure AD e defina a propriedade Departamento como "teste1".</span><span class="sxs-lookup"><span data-stu-id="5073c-215">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="5073c-216">Examine as propriedades da conta do usuário para garantir que ele tenha se tornado membro do grupo dinâmico de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-216">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="5073c-217">Altere o valor da propriedade Departamento da conta de usuário de teste para "teste2".</span><span class="sxs-lookup"><span data-stu-id="5073c-217">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="5073c-218">Examine as propriedades da conta do usuário para garantir que ele não seja mais membro do grupo dinâmico de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-218">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="5073c-219">Exclua o grupo dinâmico de teste e a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-219">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="5073c-220">Opcional: O gerenciamento de grupos por autoatendimento estar habilitado para grupos específicos de segurança do Azure AD e do Office 365</span><span class="sxs-lookup"><span data-stu-id="5073c-220">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="5073c-221">Você deve determinar quais grupos são adequados para o gerenciamento por autoatendimento, instruir seus proprietários sobre o fluxo de trabalho e as responsabilidades do gerenciamento de grupos e [configurar o gerenciamento por autoatendimento no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) para esses grupos.</span><span class="sxs-lookup"><span data-stu-id="5073c-221">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="5073c-222">Se você ignorar essa opção, todas as tarefas de gerenciamento de grupos do Azure AD deverão ser realizadas por administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="5073c-222">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="5073c-223">Se necessário, a [Etapa 14](identity-self-service-group-management.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-223">If needed, [Step 14](identity-self-service-group-management.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5073c-224">Como testar</span><span class="sxs-lookup"><span data-stu-id="5073c-224">How to test</span></span>
1.  <span data-ttu-id="5073c-225">Crie uma conta de usuário de teste no Azure AD com o portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="5073c-225">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="5073c-226">Entre como com a conta de usuário de teste e crie um grupo de segurança de teste do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5073c-226">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="5073c-227">Saia e, em seguida, entre novamente com sua conta de administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="5073c-227">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="5073c-228">Configure o grupo de segurança de teste para o gerenciamento por autoatendimento para a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-228">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="5073c-229">Saia e, em seguida, entre novamente com sua conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-229">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="5073c-230">Use o portal do Azure para adicionar membros ao grupo de segurança de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-230">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="5073c-231">Exclua o grupo de segurança de teste e a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="5073c-231">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a><span data-ttu-id="5073c-232">Opcional: O Azure AD Identity Protection estar ativado para proteger você contra o comprometimento de credenciais</span><span class="sxs-lookup"><span data-stu-id="5073c-232">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="5073c-233">Você ativou o Azure AD Identity Protection para:</span><span class="sxs-lookup"><span data-stu-id="5073c-233">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="5073c-234">Solucionar possíveis vulnerabilidades de identidade.</span><span class="sxs-lookup"><span data-stu-id="5073c-234">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="5073c-235">Detectar possíveis tentativas de ataque à credencial.</span><span class="sxs-lookup"><span data-stu-id="5073c-235">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="5073c-236">Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.</span><span class="sxs-lookup"><span data-stu-id="5073c-236">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="5073c-p110">Se você ignorar essa opção, não poderá detectar ou automaticamente eliminar tentativas de comprometer a identidade ou investigar incidentes de segurança relacionado à identidade. Isso possivelmente deixa sua organização vulnerável a ter sua identidade comprometida e à ameaça resultante aos dados confidenciais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5073c-p110">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="5073c-239">Se necessário, a [Etapa 6](identity-azure-ad-identity-protection.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-239">If needed, [Step 6](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="5073c-240">Opcional: você configurou o Privileged Identity Management para dar suporte à atribuição sob demanda da função de administrador global</span><span class="sxs-lookup"><span data-stu-id="5073c-240">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="5073c-241">Você deve usar as instruções em [Configurar o Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) para habilitar o PIM em seu locatário do Azure AD e configurar suas contas de administrador global como administradores qualificados.</span><span class="sxs-lookup"><span data-stu-id="5073c-241">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="5073c-242">Você também deve usar as recomendações em [Proteger o acesso privilegiado para implantações híbridas e de nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para desenvolver um roteiro que proteja o acesso privilegiado contra ataques cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="5073c-242">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="5073c-243">Se você ignorar essa opção, as contas de administrador global estarão sujeitas a contínuos ataques cibernéticos e, se forem comprometidas, poderão permitir que um invasor colete, destrua ou use suas informações confidenciais para obter um resgate.</span><span class="sxs-lookup"><span data-stu-id="5073c-243">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="5073c-244">Se necessário, a [Etapa 3](identity-azure-ad-identity-protection.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="5073c-244">If needed, [Step 3](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>


## <a name="next-phase"></a><span data-ttu-id="5073c-245">Próxima fase</span><span class="sxs-lookup"><span data-stu-id="5073c-245">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="5073c-246">A sua próxima fase do processo de implantação de ponta a ponta para o Microsoft 365 Enterprise é o [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="5073c-246">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

