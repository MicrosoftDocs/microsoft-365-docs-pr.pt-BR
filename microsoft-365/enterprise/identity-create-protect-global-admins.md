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
ms.openlocfilehash: 1a0274967798e6c2ba6048e5a2cfd70e73cb0671
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801826"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>Etapa 1: criar e proteger contas de administrador global

![Fase 2 – Identidade](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Proteger contas de administradores locais

*Isso é obrigatório e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você vai ajudar a evitar ataques digitais à sua organização, garantindo que as contas de administradores estejam tão seguras quanto possível. Para fazer isso, você deve:

- Criar mais de uma conta dedicada de administrador global com [senhas muito fortes](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usá-las apenas quando necessário.
- Realizar a administração diária atribuindo funções específicas de administrador, como administrador do Exchange ou administrador de senhas, para outras contas dedicadas para funções ou contas de usuários da equipe de TI conforme o necessário.

Para as contas dedicadas de administrador global, você também deve:

1. Testar as configurações por conta de usuário ou de MFA (Autenticação Multifator) do Azure baseadas no Acesso Condicional em uma conta de usuário de testes para garantir que a MFA esteja funcionando de modo correto e previsível. A MFA requer uma segunda forma de autenticação, como um código de verificação enviado para um celular.
2. Criar e habilitar uma política de Acesso Condicional para as contas de administrador global com MFA obrigatória e que use a forma mais segura de autenticação secundária disponível em sua organização. Para obter mais informações, confira [Autenticação Multifatorial do Azure](identity-access-prerequisites.md#protecting-administrator-accounts).

Para obter outras proteções, confira [Proteger as contas de administrador global do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).

> [!Note]
> As contas de emergência para cenários de resposta a emergências, como um ataque cibernético, devem ser contas do tipo somente na nuvem. Você também pode ter contas de administrador global (elegíveis ou permanentes) que não sejam do tipo somente na nuvem. Para obter mais informações, consulte [Gerenciar contas administrativas de acesso de emergência no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Os resultados desta seção são:

- As únicas contas de usuário com a função de administrador global na sua assinatura são as contas de administradores globais dedicadas. Verifique isso com o seguinte comando do PowerShell do Azure Active Directory para Graph: 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- Todas as outras contas de usuários que gerenciam seus serviços de assinatura têm funções de administrador atribuídas que estão associadas às responsabilidades de trabalho deles.

> [!Note]
> Confira [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o módulo PowerShell do Azure Active Directory para Graph e entrar.

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Para praticar essa configuração em um ambiente de laboratório de testes, confira o [Guia de laboratório de testes de proteção de contas de administradores globais](protect-global-administrator-accounts-microsoft-365-test-environment.md). |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-global-admin) desta seção.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>Configurar administradores sob demanda

*Isso é opcional e se aplica somente às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você vai configurar o Azure AD Privileged Identity Management (PIM) para reduzir o tempo em que as contas de administrador ficam vulneráveis a ataques de usuários mal-intencionados. Quando necessário, o PIM fornece atribuição just-in-time sob demanda da função de administrador.  

Em vez de suas contas de administrador serem de administradores permanentes, elas se tornam de administradores qualificados. A função de administrador ficará inativa até que alguém precise dela. Em seguida, você concluirá um processo de ativação para adicionar a função de administrador à conta de administrador por um determinado período de tempo. Quando o tempo expirar, o PIM removerá a função de administrador da conta de administrador.

O PIM está disponível com o Azure Active Directory Premium P2, que vem incluso no Microsoft 365 Enterprise E5. Como alternativa, você pode adquirir licenças do Azure Active Directory Premium P2 individuais para suas contas de administrador.

Para habilitar o Azure PIM para seu locatário do Azure AD e as contas de administrador global, confira as [etapas para configurar o PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desenvolver um roteiro abrangente para proteger o acesso privilegiado contra invasores cibernéticos, confira [Proteger o acesso privilegiado para implantações híbridas e nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pim) desta seção.


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>Gerenciamento de acesso privilegiado

O gerenciamento do acesso privilegiado é habilitado pela configuração de políticas que especificam o acesso just-in-time a atividades baseadas em tarefas em seu locatário do Office 365. Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador existentes com acesso permanente a dados confidenciais ou acesso a definições críticas de configuração. Por exemplo, você pode configurar uma política de gerenciamento de acesso privilegiado que requer a aprovação explícita para acessar e alterar configurações de caixas de correio da organização em seu locatário do Office 365.

Nesta etapa, você vai habilitar o gerenciamento do acesso privilegiado em seu locatário do Office 365 e configurar políticas de acesso privilegiado que proporcionam segurança adicionar para o acesso baseado em tarefas nos dados e definições de configuração do Office 365 em sua organização. Existem três etapas básicas para iniciar o acesso privilegiado em sua organização do Office 365:

- Criar um grupo de aprovadores
- Habilitar o acesso privilegiado
- Criar políticas de aprovação

Depois de configurado, o gerenciamento do acesso privilegiado possibilitará que sua organização opere com zero privilégios permanentes e proporcionará uma camada de defesa contra vulnerabilidades surgidas por causa deste acesso administrativo permanente. O acesso privilegiado requer aprovações para executar qualquer tarefa que tem uma política de aprovação associada definida. Os usuários que precisam executar tarefas incluídas em uma política de aprovação deve solicitar e receber aprovação de acesso para ter as permissões necessárias para executar as tarefas definidas na política.

Para habilitar o gerenciamento do acesso privilegiado no Office 365, confira o tópico [Configurar o gerenciamento do acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Para saber mais, confira o tópico [Gerenciamento do acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).


|||
|:-------|:-----|
|![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Para praticar essa configuração em um ambiente de laboratório de testes, confira o [Guia de laboratório de testes de gerenciamento de acesso privilegiado](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Como um ponto de verificação provisório, confira o [Critério de saída](identity-exit-criteria.md#crit-identity-pam) correspondente desta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![Etapa 2](./media/stepnumbers/Step2.png)| [Proteger suas senhas](identity-secure-your-passwords.md) |

