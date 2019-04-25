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
# <a name="step-2-secure-your-privileged-identities"></a>Etapa 2: Proteger suas identidades privilegiadas

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Proteger contas de administradores locais

*Isso é obrigatório e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você vai ajudar a evitar ataques digitais à sua organização, garantindo que as contas de administradores estejam tão seguras quanto possível. Para fazer isso, você deve:

- Criar contas dedicadas de administradores globais com [senhas muito fortes](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usá-las apenas quando necessário.
- Realizar a administração diária atribuindo funções específicas de administrador, tais como administrador do Exchange ou Senha de administrador, a contas de usuário ou à equipe de TI, conforme necessário.

Para as contas dedicadas de administrador global, você também deve:

1. Testar as configurações de autenticação multifator (MFA) baseada em acesso condicional ou conta por usuário para garantir que a MFA está funcionando de forma correta e previsível. A MFA requer uma segunda forma de autenticação, como um código de verificação enviado para um celular.
2. Configurar a MFA para cada uma das contas dedicadas de administrador global do Office 365 e usar a forma mais forte de autenticação secundária disponível em sua organização. Consulte as informações sobre a [autenticação multifator](identity-multi-factor-authentication.md#identity-mfa) para saber mais.
2. Use uma política de acesso condicional para exigir a MFA para contas de administradores globais. Veja [Proteção de contas de administradores](identity-access-prerequisites.md#protecting-administrator-accounts) para saber mais.
4. Use uma política do Office 365 Cloud App Security para monitorar atividades da conta de administrador global. Veja [Configurar maior segurança no Office 365](infoprotect-configure-increased-security-office-365.md) para saber mais.

Consulte as informações sobre como [proteger as contas de administradores globais do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) para saber mais sobre a configuração.

> [!Note]
> As organizações devem usar identidades somente de nuvem para criar contas privilegiadas, como os administradores globais, para cenários de quebra de vidro em emergências como um ataque cibernético. Para saber mais, confira [Gerenciar contas administrativas de acesso de emergência no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Os resultados desta seção são:

- As únicas contas de usuários que possuem a função de administrador global em sua assinatura fazem parte do novo conjunto de contas de administradores globais dedicadas. Verifique isso com o seguinte comando do PowerShell do Azure Active Directory para Graph: 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- Todas as outras contas de usuários comuns que gerenciam sua assinatura têm funções de administrador atribuídas que estão associadas às responsabilidades de trabalho deles.

> [!Note]
> Confira [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o módulo PowerShell do Azure Active Directory para Graph e entrar.

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: proteger contas de administrador global](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-global-admin) para esta seção.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a>Configurar administradores globais sob demanda

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você vai configurar o Azure AD Privileged Identity Management (PIM) para reduzir o tempo em que as contas de administradores globais ficam vulneráveis a ataques de usuários mal-intencionados.  Quando necessário, o PIM fornece atribuição just-in-time sob demanda da função de administrador global.  

Em vez das contas de administrador global serem um administrador permanente, elas se tornam administradores qualificados. A função de administrador global fica inativa até alguém precisar dela. Em seguida, você conclui um processo de ativação para adicionar a função de administrador global à conta de administrador global por um período de tempo específico. Quando o tempo expirar, o PIM remove a função de administrador global da conta de administrador global.

O PIM está disponível com o Azure Active Directory Premium P2, que está incluído no Microsoft 365 Enterprise E5. Como alternativa, você pode comprar licenças individuais do Azure Active Directory Premium P2 para contas de administrador global.

Para habilitar o Azure PIM para seu locatário do Azure AD e as contas de administradores globais, confira as [etapas para configurar o PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desenvolver um roteiro abrangente para proteger o acesso privilegiado contra invasores cibernéticos, confira [Proteger o acesso privilegiado para implantações híbridas e nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pim) para esta seção.


## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [Configurar identidade híbrida](identity-azure-ad-connect.md) |

