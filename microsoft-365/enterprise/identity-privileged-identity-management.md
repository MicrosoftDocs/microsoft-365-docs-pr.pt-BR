---
title: 'Etapa 3: Configurar administradores globais sob demanda'
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
description: Entenda e configure o Azure AD Privileged Identity Management.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864870"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a><span data-ttu-id="afa5e-103">Etapa 3: Configurar administradores globais sob demanda</span><span class="sxs-lookup"><span data-stu-id="afa5e-103">Step 3: Set up on-demand global administrators</span></span>

<span data-ttu-id="afa5e-104">*Esta etapa é opcional e aplica-se apenas à versão E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="afa5e-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="afa5e-p101">Nesta etapa, você configurará o Azure AD Privileged Identity Management (PIM) para reduzir o tempo em que as contas de administradores globais ficam vulneráveis a ataques de usuários mal-intencionados. Quando necessário, o PIM fornece atribuição just-in-time sob demanda da função de administrador global.</span><span class="sxs-lookup"><span data-stu-id="afa5e-p101">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users. PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="afa5e-p102">Em vez das contas de administrador global serem um administrador permanente, elas se tornam administradores qualificados. A função de administrador global fica inativa até alguém precisar dela. Em seguida, você conclui um processo de ativação para adicionar a função de administrador global à conta de administrador global por um período de tempo específico. Quando o tempo expirar, o PIM remove a função de administrador global da conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="afa5e-p102">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="afa5e-p103">O PIM está disponível com o Azure Active Directory Premium P2, que está incluído no Microsoft 365 Enterprise E5. Como alternativa, você pode comprar licenças individuais do Azure Active Directory Premium P2 para contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="afa5e-p103">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="afa5e-113">Para habilitar o Azure PIM para seu locatário do Azure AD e as contas de administradores globais, confira as [etapas para configurar o PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="afa5e-113">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="afa5e-114">Para desenvolver um roteiro abrangente para proteger o acesso privilegiado contra invasores cibernéticos, confira [Proteger o acesso privilegiado para implantações híbridas e nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="afa5e-114">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="afa5e-115">Como um ponto de verificação provisório, é possível ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pim) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="afa5e-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="afa5e-116">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="afa5e-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="afa5e-117">Simplificar as redefinições de senha</span><span class="sxs-lookup"><span data-stu-id="afa5e-117">Simplify password resets</span></span>](identity-password-reset.md) |

