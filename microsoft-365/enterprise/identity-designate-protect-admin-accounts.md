---
title: 'Etapa 2: Proteger suas identidades privilegiadas'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar as contas de administradores para uma máxima proteção.
ms.openlocfilehash: 4b4a8d01cdf71e30139fa448813a3ff7c43855c7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285151"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="b39e6-103">Etapa 2: Proteger suas identidades privilegiadas</span><span class="sxs-lookup"><span data-stu-id="b39e6-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="b39e6-104">Proteger contas de administradores locais</span><span class="sxs-lookup"><span data-stu-id="b39e6-104">Protect global administrator accounts</span></span>

<span data-ttu-id="b39e6-105">*Isso é obrigatório e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b39e6-105">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b39e6-106">Nesta seção, você vai ajudar a evitar ataques digitais à sua organização, garantindo que as contas de administradores estejam tão seguras quanto possível.</span><span class="sxs-lookup"><span data-stu-id="b39e6-106">In this step, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span> <span data-ttu-id="b39e6-107">Para fazer isso, você deve:</span><span class="sxs-lookup"><span data-stu-id="b39e6-107">To do this, you must:</span></span>

- <span data-ttu-id="b39e6-108">Criar contas dedicadas de administradores globais com [senhas muito fortes](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usá-las apenas quando necessário.</span><span class="sxs-lookup"><span data-stu-id="b39e6-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="b39e6-109">Realizar a administração diária atribuindo funções específicas de administrador, tais como administrador do Exchange ou Senha de administrador, a contas de usuário ou à equipe de TI, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b39e6-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="b39e6-110">Para as contas dedicadas de administrador global, você também deve:</span><span class="sxs-lookup"><span data-stu-id="b39e6-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="b39e6-p102">Testar as configurações de autenticação multifator (MFA) baseada em acesso condicional ou conta por usuário para garantir que a MFA está funcionando de forma correta e previsível. A MFA requer uma segunda forma de autenticação, como um código de verificação enviado para um celular.</span><span class="sxs-lookup"><span data-stu-id="b39e6-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="b39e6-p103">Configurar a MFA para cada uma das contas dedicadas de administrador global do Office 365 e usar a forma mais forte de autenticação secundária disponível em sua organização. Consulte as informações sobre a [autenticação multifator](identity-multi-factor-authentication.md#identity-mfa) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="b39e6-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) for more information.</span></span>
2. <span data-ttu-id="b39e6-p104">Use uma política de acesso condicional para exigir a MFA para contas de administradores globais. Veja [Proteção de contas de administradores](identity-access-prerequisites.md#protecting-administrator-accounts) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="b39e6-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="b39e6-p105">Use uma política do Office 365 Cloud App Security para monitorar atividades da conta de administrador global. Veja [Configurar maior segurança no Office 365](infoprotect-configure-increased-security-office-365.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="b39e6-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Configure increased security for Office 365](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="b39e6-119">Consulte as informações sobre como [proteger as contas de administradores globais do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) para saber mais sobre a configuração.</span><span class="sxs-lookup"><span data-stu-id="b39e6-119">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="b39e6-p106">As organizações devem usar identidades somente de nuvem para criar contas privilegiadas, como os administradores globais, para cenários de quebra de vidro em emergências como um ataque cibernético. Para saber mais, confira [Gerenciar contas administrativas de acesso de emergência no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="b39e6-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="b39e6-122">Os resultados desta seção são:</span><span class="sxs-lookup"><span data-stu-id="b39e6-122">The results of this step are:</span></span>

- <span data-ttu-id="b39e6-123">As únicas contas de usuários que possuem a função de administrador global em sua assinatura fazem parte do novo conjunto de contas de administradores globais dedicadas.</span><span class="sxs-lookup"><span data-stu-id="b39e6-123">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> <span data-ttu-id="b39e6-124">Verifique isso com o seguinte comando do PowerShell do Azure Active Directory para Graph:</span><span class="sxs-lookup"><span data-stu-id="b39e6-124">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="b39e6-125">Todas as outras contas de usuários comuns que gerenciam sua assinatura têm funções de administrador atribuídas que estão associadas às responsabilidades de trabalho deles.</span><span class="sxs-lookup"><span data-stu-id="b39e6-125">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="b39e6-126">Confira [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o módulo PowerShell do Azure Active Directory para Graph e entrar.</span><span class="sxs-lookup"><span data-stu-id="b39e6-126">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b39e6-128">Guia do Laboratório de Teste: proteger contas de administrador global</span><span class="sxs-lookup"><span data-stu-id="b39e6-128">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="b39e6-129">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-global-admin) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="b39e6-129">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="b39e6-130">Configurar administradores globais sob demanda</span><span class="sxs-lookup"><span data-stu-id="b39e6-130">Set up on-demand global administrators</span></span>

<span data-ttu-id="b39e6-131">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b39e6-131">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b39e6-132">Nesta seção, você vai configurar o Azure AD Privileged Identity Management (PIM) para reduzir o tempo em que as contas de administradores globais ficam vulneráveis a ataques de usuários mal-intencionados. </span><span class="sxs-lookup"><span data-stu-id="b39e6-132">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users. PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span> <span data-ttu-id="b39e6-133">Quando necessário, o PIM fornece atribuição just-in-time sob demanda da função de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b39e6-133">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="b39e6-p109">Em vez das contas de administrador global serem um administrador permanente, elas se tornam administradores qualificados. A função de administrador global fica inativa até alguém precisar dela. Em seguida, você conclui um processo de ativação para adicionar a função de administrador global à conta de administrador global por um período de tempo específico. Quando o tempo expirar, o PIM remove a função de administrador global da conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b39e6-p109">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="b39e6-p110">O PIM está disponível com o Azure Active Directory Premium P2, que está incluído no Microsoft 365 Enterprise E5. Como alternativa, você pode comprar licenças individuais do Azure Active Directory Premium P2 para contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b39e6-p110">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="b39e6-140">Para habilitar o Azure PIM para seu locatário do Azure AD e as contas de administradores globais, confira as [etapas para configurar o PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="b39e6-140">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="b39e6-141">Para desenvolver um roteiro abrangente para proteger o acesso privilegiado contra invasores cibernéticos, confira [Proteger o acesso privilegiado para implantações híbridas e nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="b39e6-141">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="b39e6-142">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pim) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="b39e6-142">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="b39e6-143">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b39e6-143">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="b39e6-144">Configurar identidade híbrida</span><span class="sxs-lookup"><span data-stu-id="b39e6-144">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

