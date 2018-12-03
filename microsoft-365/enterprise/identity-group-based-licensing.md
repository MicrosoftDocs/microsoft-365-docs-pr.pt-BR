---
title: 'Etapa 12: Configurar o licenciamento automático'
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
description: Entender e configurar o licenciamento baseado em grupo para grupos do Azure AD.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864661"
---
# <a name="step-12-set-up-automatic-licensing"></a>Etapa 12: Configurar o licenciamento automático

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai configurar grupos de segurança no Azure AD para atribuir automaticamente licenças de um conjunto de assinaturas a todos os membros do grupo. Essa ação é conhecida como *licenciamento baseado em grupo*. Se uma conta de usuário for adicionada ou removida do grupo, as licenças para as assinaturas do grupo serão automaticamente atribuídas ou removidas da conta do usuário.

No Microsoft 365 Enterprise, você configura grupos de segurança do Azure AD para atribuir estas duas licenças:

- Office 365 Enterprise E3 ou E5
- Enterprise Mobility + Security (EMS) E3 ou E5

Usando os grupos que foram identificados na Etapa 2, procure aqueles com uma lista de contas em que todos os usuários precisem ter as licenças do Office 365 e do EMS. Verifique se você tem licenças suficientes para todos os membros do grupo. Se não houver licenças para todos, os novos usuários não receberão licenças até que estas estejam disponíveis.

>[!Note]
>Você não deve configurar o *licenciamento baseado em grupo* para grupos que contenham contas do Azure para empresas (B2B).
>

Consulte as [noções básicas sobre o licenciamento baseado em grupo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Consulte as [etapas para configurar o licenciamento baseado em grupo para um grupo de segurança do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

Os resultados desta etapa são:

- Você identificou quais grupos de segurança são adequados para o licenciamento baseado em grupo.
- Você configurou esses grupos para o licenciamento baseado em grupo.

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: automatizar licenças e associação a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-group-license) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [Monitorar a atividade de entrada e do locatário](identity-azure-ad-access-usage-reporting.md) |

