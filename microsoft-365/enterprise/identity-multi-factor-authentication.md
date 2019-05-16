---
title: 'Etapa 4: Configurar autenticação de usuário segura'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar a autenticação multifator nas contas de usuário.
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072081"
---
# <a name="step-4-configure-secure-user-authentication"></a>Etapa 4: Configurar autenticação de usuário segura

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a>Configurar a autenticação multifator

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta etapa, você vai configurar a autenticação multifator (MFA) para adicionar uma segunda camada de segurança nas transações e entradas de usuário. A MFA requer um método de verificação adicional após os usuários inserirem corretamente a sua senha. Sem a MFA, a senha é o único método de verificação. O problema com as senhas é que muitas delas são facilmente decifradas por invasores ou compartilhadas sem intenção com terceiros não confiáveis.

Com a MFA, a segunda camada de segurança pode ser:

- Um dispositivo pessoal de confiança que não seja facilmente forjado ou duplicado, como um smartphone.
- Um atributo biométrico, como uma impressão digital.

Você vai habilitar a MFA e configurar o método de autenticação secundária em cada conta de usuário. Avise os usuários que a MFA será ativada para que eles compreendam os requisitos, como o uso obrigatório de um Smartphone para acesso, e possam entrar na rede com êxito.

Para saber mais, confira [Planejar autenticações multifatoriais](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

>[!Note]
>Em alguns aplicativos, como o Microsoft Office 2010 ou mais antigos e o Apple Mail, não é possível usar a MFA. Para usar esses aplicativos, é necessário usar "senhas de aplicativo" em vez da sua senha tradicional. A senha de aplicativo permite que o aplicativo ignore a MFA e continue funcionando. Para saber mais sobre as senhas de aplicativo, consulte as informações sobre como [criar uma senha de aplicativo para o Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).
>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: autenticação multifator](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-mfa) para esta seção.



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Proteger-se contra o comprometimento de credenciais

*Isso é opcional e se aplica somente às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você aprenderá a configurar políticas de proteção contra o comprometimento de credenciais, onde um invasor determina o nome e senha da conta de um usuário para obter acesso aos serviços de nuvem e dados de uma organização. O Azure AD Identity Protection fornece várias maneiras de ajudar a evitar que um invasor se mova lateralmente por suas contas e grupos e posteriormente, até seus dados mais valiosos.

Com a Azure AD Identity Protection, você pode:

|||
|:---------|:---------|
|Determinar e administrar possíveis vulnerabilidades nas identidades da organização|O Azure AD utiliza o aprendizado de máquina para detectar anomalias e atividades suspeitas, como atividades de entrada e pós-entrada. Usando esses dados, a Proteção de Identidade gera relatórios e alertas que lhe ajudarão a avaliar os problemas e a tomar as medidas necessárias.|
|Detectar ações suspeitas relacionadas às identidades da organização e responder a essas suspeitas automaticamente|Você pode configurar as políticas baseadas em risco que são acionadas automaticamente para detectar problemas quando um nível de risco específico é atingido. Essas políticas, além de outros controles de acesso condicional fornecidos pelo Azure Active Directory e pelo Enterprise Mobility + Security EMS (), podem bloquear automaticamente o acesso ou realizar ações corretivas, incluindo a redefinição de senha e exigindo a autenticação multifator para entradas subsequentes.|
|Investigar incidentes suspeitos e resolvê-los com medidas administrativas|Você pode investigar eventos de risco usando informações sobre o incidente de segurança. Fluxos básicos de trabalho estão disponíveis para controlar investigações e iniciar ações de correção, como a redefinição de senhas.|

Consulte mais [informações sobre a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Consulte as [etapas para habilitar a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Os resultados desta etapa incluem a habilitação da Azure AD Identity Protection e o uso dessa para:

- Solucionar possíveis vulnerabilidades de identidade.
- Detectar possíveis tentativas de ataque à credencial.
- Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-ident-prot) para esta seção.

## <a name="monitor-tenant-and-sign-in-activity"></a>Monitorar a atividade de entrada e do locatário

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta etapa, você vai revisar os logs de auditoria e a atividade de entrada usando os relatórios do Azure AD. Estão disponíveis dois tipos de relatório.

O **relatório de atividade de logs de auditoria** registra o histórico de todas as tarefas realizadas em seu locatário do Azure AD. Esse relatório responde a perguntas como:

- Quem adicionou uma pessoa a um grupo de administração?
- Que usuários estão se conectando em um aplicativo específico?
- Quantas redefinições de senhas estão ocorrendo?

O **relatório de atividade de entradas** registra quem executou as tarefas relatadas pelo relatório de logs de auditoria. Esse relatório responde a perguntas como:

- Qual é o padrão de entrada de um usuário específico que está sob investigação?
- Qual é o volume de entradas em um dia, uma semana ou um mês?
- Quantas dessas tentativas de entrada não foram bem-sucedidas, e em que contas ocorreram?

Para saber mais sobre os relatórios e como acessá-los, consulte as informações sobre os [relatórios do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).

Como resultado desta etapa, você ficará ciente desses relatórios e saberá como usá-los para obter informações de atividades e eventos ocorridos no Azure AD para poder planejar a segurança.



## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [Simplificar o acesso para usuários](identity-password-reset.md) |

