---
title: 'Etapa 10: Simplificar entrada de usuários'
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
description: Entenda e configure o logon único contínuo (SSO Contínuo) do Azure Active Directory.
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865222"
---
# <a name="step-10-simplify-user-sign-in"></a>Etapa 10: Simplificar entrada de usuários

*Esta etapa é opcional para ambientes híbridos e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai configurar o logon único contínuo do Azure Active Directory (SSO Contínuo do Azure Active Directory) para permitir que os usuários entrem em serviços que usam as contas de usuário do Azure Active Directory sem precisar digitar as senhas e, em muitos casos, os nomes de usuário. Isso facilita o acesso dos usuários aos aplicativos baseados em nuvem, como o Office 365, sem precisar adicionar componentes locais, como servidores de federação de identidades.

Você configurará o SSO Contínuo do Azure Active Directory com a ferramenta Azure AD Connect.

Confira as [instruções para configurar o SSO Contínuo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: Logon Único Contínuo do Azure Active Directory](single-sign-on-m365-ent-test-environment.md) |
|||

Como um ponto de verificação provisório, é possível ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sso) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [Personalizar páginas de entrada do Office 365](identity-customize-office-365-sign-in.md) |

