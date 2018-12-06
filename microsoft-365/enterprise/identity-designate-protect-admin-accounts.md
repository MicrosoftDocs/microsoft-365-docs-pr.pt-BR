---
title: 'Etapa 2: Proteger contas de administradores globais'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar as contas de administradores para uma máxima proteção.
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865316"
---
# <a name="step-2-protect-global-administrator-accounts"></a><span data-ttu-id="63628-103">Etapa 2: Proteger contas de administradores globais</span><span class="sxs-lookup"><span data-stu-id="63628-103">Step 2: Protect global administrator accounts</span></span>

<span data-ttu-id="63628-104">*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="63628-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="63628-p101">Nesta etapa, você vai ajudar a evitar ataques digitais à sua organização, garantindo que as contas de administradores estejam o mais seguras possíveis. Para fazer isso, você deve:</span><span class="sxs-lookup"><span data-stu-id="63628-p101">In Step 5, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span>

- <span data-ttu-id="63628-107">Criar contas dedicadas de administradores globais com [senhas muito fortes](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usá-las apenas quando necessário.</span><span class="sxs-lookup"><span data-stu-id="63628-107">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="63628-108">Realizar a administração diária atribuindo funções específicas de administrador, tais como administrador do Exchange ou Senha de administrador, a contas de usuário ou à equipe de TI, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="63628-108">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="63628-109">Para as contas dedicadas de administrador global, você também deve:</span><span class="sxs-lookup"><span data-stu-id="63628-109">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="63628-p102">Testar as configurações de autenticação multifator (MFA) baseada em acesso condicional ou conta por usuário para garantir que a MFA está funcionando de forma correta e previsível. A MFA requer uma segunda forma de autenticação, como um código de verificação enviado para um celular.</span><span class="sxs-lookup"><span data-stu-id="63628-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="63628-p103">Configurar a MFA para cada uma das contas dedicadas de administrador global do Office 365 e usar a forma mais forte de autenticação secundária disponível em sua organização. Consulte as informações sobre a [autenticação multifator](identity-multi-factor-authentication.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="63628-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md) for more information.</span></span>
2. <span data-ttu-id="63628-p104">Use uma política de acesso condicional para exigir a MFA para contas de administradores globais. Veja [Proteção de contas de administradores](identity-access-prerequisites.md#protecting-administrator-accounts) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="63628-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="63628-p105">Use uma política do Office 365 Cloud App Security para monitorar atividades da conta de administrador global. Veja [Configurar maior segurança no Office 365](infoprotect-configure-increased-security-office-365.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="63628-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Information protection for Microsoft 365 Enterprise](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="63628-118">Consulte as informações sobre como [proteger as contas de administradores globais do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) para saber mais sobre a configuração.</span><span class="sxs-lookup"><span data-stu-id="63628-118">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="63628-p106">As organizações devem usar identidades somente de nuvem para criar contas privilegiadas, como os administradores globais, para cenários de quebra de vidro em emergências como um ataque cibernético. Para saber mais, confira [Gerenciar contas administrativas de acesso de emergência no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="63628-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="63628-121">Os resultados desta etapa são:</span><span class="sxs-lookup"><span data-stu-id="63628-121">The results of this step are:</span></span>

- <span data-ttu-id="63628-p107"> As únicas contas de usuários em sua assinatura que possuem a função de administrador global serão o novo conjunto de contas dedicadas de administrador global. Verifique isso com o seguinte comando do Windows Azure AD V2 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="63628-p107">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="63628-124">Todas as outras contas de usuários comuns que gerenciam sua assinatura têm funções de administrador atribuídas que estão associadas às responsabilidades de trabalho deles.</span><span class="sxs-lookup"><span data-stu-id="63628-124">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="63628-125">Veja [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o módulo Azure AD V2 PowerShell e entrar.</span><span class="sxs-lookup"><span data-stu-id="63628-125">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="63628-127">Guia do Laboratório de Teste: proteger contas de administrador global</span><span class="sxs-lookup"><span data-stu-id="63628-127">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="63628-128">Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-global-admin) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="63628-128">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="63628-129">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="63628-129">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="63628-130">Configurar administradores globais sob demanda</span><span class="sxs-lookup"><span data-stu-id="63628-130">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |

