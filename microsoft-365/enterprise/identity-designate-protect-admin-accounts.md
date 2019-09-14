---
title: 'Etapa 2: Proteger suas identidades privilegiadas'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar as contas de administradores para uma máxima proteção.
ms.openlocfilehash: b9c645d597dfeb2bdc42e2b0b7615252dc1f5ecb
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981902"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="cfd7b-103">Etapa 2: Proteger suas identidades privilegiadas</span><span class="sxs-lookup"><span data-stu-id="cfd7b-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="cfd7b-104">Proteger contas de administradores locais</span><span class="sxs-lookup"><span data-stu-id="cfd7b-104">Protect global administrator accounts</span></span>

<span data-ttu-id="cfd7b-105">*Isso é obrigatório e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="cfd7b-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="cfd7b-106">Nesta seção, você vai ajudar a evitar ataques digitais à sua organização, garantindo que as contas de administradores estejam tão seguras quanto possível.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="cfd7b-107">Para fazer isso, você deve:</span><span class="sxs-lookup"><span data-stu-id="cfd7b-107">To do this, you must:</span></span>

- <span data-ttu-id="cfd7b-108">Criar contas dedicadas de administradores globais com [senhas muito fortes](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usá-las apenas quando necessário.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="cfd7b-109">Realizar a administração diária atribuindo funções específicas de administrador, tais como administrador do Exchange ou Senha de administrador, a contas de usuário ou à equipe de TI, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="cfd7b-110">Para as contas dedicadas de administrador global, você também deve:</span><span class="sxs-lookup"><span data-stu-id="cfd7b-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="cfd7b-p102">Testar as configurações de autenticação multifator (MFA) baseada em acesso condicional ou conta por usuário para garantir que a MFA está funcionando de forma correta e previsível. A MFA requer uma segunda forma de autenticação, como um código de verificação enviado para um celular.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="cfd7b-113">Habilitar a política de acesso condicional **Política de linha de base: exige a MFA de administradores** para suas contas de administradores globais e usar a forma mais segura de autenticação secundária disponível na sua organização.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-113">Enable the **Baseline policy: Require MFA for admins** conditional access policy for your global administrator accounts and use the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="cfd7b-114">Para obter mais informações, confira [Autenticação multifatorial](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="cfd7b-114">See [Multi-factor authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="cfd7b-115">Para obter outras proteções, confira [Proteger as contas de administradores globais do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="cfd7b-115">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="cfd7b-p104">As organizações devem usar identidades somente de nuvem para criar contas privilegiadas, como os administradores globais, para cenários de quebra de vidro em emergências como um ataque cibernético. Para saber mais, confira [Gerenciar contas administrativas de acesso de emergência no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="cfd7b-p104">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="cfd7b-118">Os resultados desta seção são:</span><span class="sxs-lookup"><span data-stu-id="cfd7b-118">The results of this section are:</span></span>

- <span data-ttu-id="cfd7b-119">As únicas contas de usuário com a função de administrador global na sua assinatura são as contas de administradores globais dedicadas.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-119">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="cfd7b-120">Verifique isso com o seguinte comando do PowerShell do Azure Active Directory para Graph:</span><span class="sxs-lookup"><span data-stu-id="cfd7b-120">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="cfd7b-121">Todas as outras contas de usuários que gerenciam seus serviços de assinatura têm funções de administrador atribuídas que estão associadas às responsabilidades de trabalho deles.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-121">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="cfd7b-122">Confira [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o módulo PowerShell do Azure Active Directory para Graph e entrar.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-122">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="cfd7b-124">Para praticar essa configuração em um ambiente de laboratório de testes, confira o [Guia de laboratório de testes de proteção de contas de administradores globais](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cfd7b-124">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="cfd7b-125">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-global-admin) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="cfd7b-126">Configurar administradores globais sob demanda</span><span class="sxs-lookup"><span data-stu-id="cfd7b-126">Set up on-demand global administrators</span></span>

<span data-ttu-id="cfd7b-127">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="cfd7b-127">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="cfd7b-128">Nesta seção, você vai configurar o Azure AD Privileged Identity Management (PIM) para reduzir o tempo em que as contas de administradores globais ficam vulneráveis a ataques de usuários mal-intencionados. </span><span class="sxs-lookup"><span data-stu-id="cfd7b-128">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="cfd7b-129">Quando necessário, o PIM fornece atribuição just-in-time sob demanda da função de administrador global.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-129">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="cfd7b-p107">Em vez das contas de administrador global serem um administrador permanente, elas se tornam administradores qualificados. A função de administrador global fica inativa até alguém precisar dela. Em seguida, você conclui um processo de ativação para adicionar a função de administrador global à conta de administrador global por um período de tempo específico. Quando o tempo expirar, o PIM remove a função de administrador global da conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-p107">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="cfd7b-p108">O PIM está disponível com o Azure Active Directory Premium P2, que está incluído no Microsoft 365 Enterprise E5. Como alternativa, você pode comprar licenças individuais do Azure Active Directory Premium P2 para contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-p108">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="cfd7b-136">Para habilitar o Azure PIM para seu locatário do Azure AD e as contas de administradores globais, confira as [etapas para configurar o PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="cfd7b-136">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="cfd7b-137">Para desenvolver um roteiro abrangente para proteger o acesso privilegiado contra invasores cibernéticos, confira [Proteger o acesso privilegiado para implantações híbridas e nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="cfd7b-137">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="cfd7b-138">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pim) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-138">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="cfd7b-139">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="cfd7b-139">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="cfd7b-140">Configurar identidade híbrida</span><span class="sxs-lookup"><span data-stu-id="cfd7b-140">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

