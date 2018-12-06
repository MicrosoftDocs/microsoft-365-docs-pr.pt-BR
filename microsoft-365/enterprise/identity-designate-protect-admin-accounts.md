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
# <a name="step-2-protect-global-administrator-accounts"></a>Etapa 2: Proteger contas de administradores globais

*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai ajudar a evitar ataques digitais à sua organização, garantindo que as contas de administradores estejam o mais seguras possíveis. Para fazer isso, você deve:

- Criar contas dedicadas de administradores globais com [senhas muito fortes](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usá-las apenas quando necessário.
- Realizar a administração diária atribuindo funções específicas de administrador, tais como administrador do Exchange ou Senha de administrador, a contas de usuário ou à equipe de TI, conforme necessário.

Para as contas dedicadas de administrador global, você também deve:

1. Testar as configurações de autenticação multifator (MFA) baseada em acesso condicional ou conta por usuário para garantir que a MFA está funcionando de forma correta e previsível. A MFA requer uma segunda forma de autenticação, como um código de verificação enviado para um celular.
2. Configurar a MFA para cada uma das contas dedicadas de administrador global do Office 365 e usar a forma mais forte de autenticação secundária disponível em sua organização. Consulte as informações sobre a [autenticação multifator](identity-multi-factor-authentication.md) para saber mais.
2. Use uma política de acesso condicional para exigir a MFA para contas de administradores globais. Veja [Proteção de contas de administradores](identity-access-prerequisites.md#protecting-administrator-accounts) para saber mais.
4. Use uma política do Office 365 Cloud App Security para monitorar atividades da conta de administrador global. Veja [Configurar maior segurança no Office 365](infoprotect-configure-increased-security-office-365.md) para saber mais.

Consulte as informações sobre como [proteger as contas de administradores globais do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) para saber mais sobre a configuração.

> [!Note]
> As organizações devem usar identidades somente de nuvem para criar contas privilegiadas, como os administradores globais, para cenários de quebra de vidro em emergências como um ataque cibernético. Para saber mais, confira [Gerenciar contas administrativas de acesso de emergência no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Os resultados desta etapa são:

-  As únicas contas de usuários em sua assinatura que possuem a função de administrador global serão o novo conjunto de contas dedicadas de administrador global. Verifique isso com o seguinte comando do Windows Azure AD V2 PowerShell: 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- Todas as outras contas de usuários comuns que gerenciam sua assinatura têm funções de administrador atribuídas que estão associadas às responsabilidades de trabalho deles.

> [!Note]
> Veja [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o módulo Azure AD V2 PowerShell e entrar.

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: proteger contas de administrador global](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-global-admin) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [Configurar administradores globais sob demanda](identity-privileged-identity-management.md) |

