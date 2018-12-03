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
# <a name="step-3-set-up-on-demand-global-administrators"></a>Etapa 3: Configurar administradores globais sob demanda

*Esta etapa é opcional e aplica-se apenas à versão E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você configurará o Azure AD Privileged Identity Management (PIM) para reduzir o tempo em que as contas de administradores globais ficam vulneráveis a ataques de usuários mal-intencionados. Quando necessário, o PIM fornece atribuição just-in-time sob demanda da função de administrador global.  

Em vez das contas de administrador global serem um administrador permanente, elas se tornam administradores qualificados. A função de administrador global fica inativa até alguém precisar dela. Em seguida, você conclui um processo de ativação para adicionar a função de administrador global à conta de administrador global por um período de tempo específico. Quando o tempo expirar, o PIM remove a função de administrador global da conta de administrador global.

O PIM está disponível com o Azure Active Directory Premium P2, que está incluído no Microsoft 365 Enterprise E5. Como alternativa, você pode comprar licenças individuais do Azure Active Directory Premium P2 para contas de administrador global.

Para habilitar o Azure PIM para seu locatário do Azure AD e as contas de administradores globais, confira as [etapas para configurar o PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desenvolver um roteiro abrangente para proteger o acesso privilegiado contra invasores cibernéticos, confira [Proteger o acesso privilegiado para implantações híbridas e nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Como um ponto de verificação provisório, é possível ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pim) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [Simplificar as redefinições de senha](identity-password-reset.md) |

