---
title: 'Etapa 1: criar e proteger contas de administrador global'
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
description: As contas de administrador global precisam de um tratamento especial para ajudar a mantê-las protegidas contra o comprometimento de credenciais.
ms.openlocfilehash: a32781686cd972ca96f6bb08f31c15ede016c4cd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073207"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="59696-103">Etapa 1: criar e proteger contas de administrador global</span><span class="sxs-lookup"><span data-stu-id="59696-103">Step 1: Create and protect your global admin accounts</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="59696-104">Proteger contas de administradores locais</span><span class="sxs-lookup"><span data-stu-id="59696-104">Protect global administrator accounts</span></span>

<span data-ttu-id="59696-105">*Isso é obrigatório e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="59696-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="59696-106">Nesta seção, você vai ajudar a evitar ataques digitais à sua organização, garantindo que as contas de administradores estejam tão seguras quanto possível.</span><span class="sxs-lookup"><span data-stu-id="59696-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="59696-107">Para fazer isso, você deve:</span><span class="sxs-lookup"><span data-stu-id="59696-107">To do this, you must:</span></span>

- <span data-ttu-id="59696-108">Criar mais de uma conta dedicada de administrador global com [senhas muito fortes](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usá-las apenas quando necessário.</span><span class="sxs-lookup"><span data-stu-id="59696-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="59696-109">Realizar a administração diária atribuindo funções específicas de administrador, como administrador do Exchange ou administrador de senhas, para outras contas dedicadas para funções ou contas de usuários da equipe de TI conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="59696-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="59696-110">Para as contas dedicadas de administrador global, você também deve:</span><span class="sxs-lookup"><span data-stu-id="59696-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="59696-111">Testar as configurações por conta de usuário ou de MFA (Autenticação Multifator) do Azure baseadas no Acesso Condicional em uma conta de usuário de testes para garantir que a MFA esteja funcionando de modo correto e previsível.</span><span class="sxs-lookup"><span data-stu-id="59696-111">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="59696-112">A MFA requer uma segunda forma de autenticação, como um código de verificação enviado para um celular.</span><span class="sxs-lookup"><span data-stu-id="59696-112">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="59696-113">Criar e habilitar uma política de Acesso Condicional para as contas de administrador global com MFA obrigatória e que use a forma mais segura de autenticação secundária disponível em sua organização.</span><span class="sxs-lookup"><span data-stu-id="59696-113">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="59696-114">Para obter mais informações, confira [Autenticação Multifatorial do Azure](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="59696-114">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="59696-115">Para obter outras proteções, confira [Proteger as contas de administrador global do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="59696-115">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="59696-116">As contas de emergência para cenários de resposta a emergências, como um ataque cibernético, devem ser contas do tipo somente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="59696-116">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="59696-117">Você também pode ter contas de administrador global (elegíveis ou permanentes) que não sejam do tipo somente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="59696-117">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="59696-118">Para obter mais informações, consulte [Gerenciar contas administrativas de acesso de emergência no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="59696-118">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="59696-119">Os resultados desta seção são:</span><span class="sxs-lookup"><span data-stu-id="59696-119">The results of this section are:</span></span>

- <span data-ttu-id="59696-120">As únicas contas de usuário com a função de administrador global na sua assinatura são as contas de administradores globais dedicadas.</span><span class="sxs-lookup"><span data-stu-id="59696-120">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="59696-121">Verifique isso com o seguinte comando do PowerShell do Azure Active Directory para Graph:</span><span class="sxs-lookup"><span data-stu-id="59696-121">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="59696-122">Todas as outras contas de usuários que gerenciam seus serviços de assinatura têm funções de administrador atribuídas que estão associadas às responsabilidades de trabalho deles.</span><span class="sxs-lookup"><span data-stu-id="59696-122">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="59696-123">Confira [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o módulo PowerShell do Azure Active Directory para Graph e entrar.</span><span class="sxs-lookup"><span data-stu-id="59696-123">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="59696-125">Para praticar essa configuração em um ambiente de laboratório de testes, confira o [Guia de laboratório de testes de proteção de contas de administradores globais](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="59696-125">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="59696-126">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-global-admin) desta seção.</span><span class="sxs-lookup"><span data-stu-id="59696-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="59696-127">Configurar administradores sob demanda</span><span class="sxs-lookup"><span data-stu-id="59696-127">Set up on-demand global administrators</span></span>

<span data-ttu-id="59696-128">*Isso é opcional e se aplica somente às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="59696-128">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="59696-129">Nesta seção, você vai configurar o Azure AD Privileged Identity Management (PIM) para reduzir o tempo em que as contas de administrador ficam vulneráveis a ataques de usuários mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="59696-129">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="59696-130">Quando necessário, o PIM fornece atribuição just-in-time sob demanda da função de administrador.</span><span class="sxs-lookup"><span data-stu-id="59696-130">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="59696-131">Em vez de suas contas de administrador serem de administradores permanentes, elas se tornam de administradores qualificados.</span><span class="sxs-lookup"><span data-stu-id="59696-131">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="59696-132">A função de administrador ficará inativa até que alguém precise dela.</span><span class="sxs-lookup"><span data-stu-id="59696-132">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="59696-133">Em seguida, você concluirá um processo de ativação para adicionar a função de administrador à conta de administrador por um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="59696-133">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="59696-134">Quando o tempo expirar, o PIM removerá a função de administrador da conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="59696-134">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="59696-135">O PIM está disponível com o Azure Active Directory Premium P2, que acompanha o Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="59696-135">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span> <span data-ttu-id="59696-136">Como alternativa, você pode adquirir licenças do Azure Active Directory Premium P2 individuais para suas contas de administrador.</span><span class="sxs-lookup"><span data-stu-id="59696-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="59696-137">Para habilitar o Azure PIM para seu locatário do Azure AD e as contas de administrador global, confira as [etapas para configurar o PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="59696-137">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="59696-138">Para desenvolver um roteiro abrangente para proteger o acesso privilegiado contra invasores cibernéticos, confira [Proteger o acesso privilegiado para implantações híbridas e nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="59696-138">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="59696-139">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pim) desta seção.</span><span class="sxs-lookup"><span data-stu-id="59696-139">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="59696-140">Gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="59696-140">Privileged access management</span></span>

<span data-ttu-id="59696-p109">O gerenciamento do acesso privilegiado é habilitado pela configuração de políticas que especificam o acesso just-in-time a atividades baseadas em tarefas em seu locatário do Office 365. Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador existentes com acesso permanente a dados confidenciais ou acesso a definições críticas de configuração. Por exemplo, você pode configurar uma política de gerenciamento de acesso privilegiado que requer a aprovação explícita para acessar e alterar configurações de caixas de correio da organização em seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="59696-p109">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="59696-p110">Nesta etapa, você vai habilitar o gerenciamento do acesso privilegiado em seu locatário do Office 365 e configurar políticas de acesso privilegiado que proporcionam segurança adicionar para o acesso baseado em tarefas nos dados e definições de configuração do Office 365 em sua organização. Existem três etapas básicas para iniciar o acesso privilegiado em sua organização do Office 365:</span><span class="sxs-lookup"><span data-stu-id="59696-p110">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="59696-146">Criar um grupo de aprovadores</span><span class="sxs-lookup"><span data-stu-id="59696-146">Creating an approver's group</span></span>
- <span data-ttu-id="59696-147">Habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="59696-147">Enabling privileged access</span></span>
- <span data-ttu-id="59696-148">Criar políticas de aprovação</span><span class="sxs-lookup"><span data-stu-id="59696-148">Creating approval policies</span></span>

<span data-ttu-id="59696-p111">Depois de configurado, o gerenciamento do acesso privilegiado possibilitará que sua organização opere com zero privilégios permanentes e proporcionará uma camada de defesa contra vulnerabilidades surgidas por causa deste acesso administrativo permanente. O acesso privilegiado requer aprovações para executar qualquer tarefa que tem uma política de aprovação associada definida. Os usuários que precisam executar tarefas incluídas em uma política de aprovação deve solicitar e receber aprovação de acesso para ter as permissões necessárias para executar as tarefas definidas na política.</span><span class="sxs-lookup"><span data-stu-id="59696-p111">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="59696-152">Para habilitar o gerenciamento do acesso privilegiado no Office 365, confira o tópico [Configurar o gerenciamento do acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="59696-152">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="59696-153">Para saber mais, confira o tópico [Gerenciamento do acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="59696-153">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="59696-155">Para praticar essa configuração em um ambiente de laboratório de testes, confira o [Guia de laboratório de testes de gerenciamento de acesso privilegiado](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="59696-155">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="59696-156">Como um ponto de verificação provisório, confira o [Critério de saída](identity-exit-criteria.md#crit-identity-pam) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="59696-156">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="59696-157">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="59696-157">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="59696-158">Proteger suas senhas</span><span class="sxs-lookup"><span data-stu-id="59696-158">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

