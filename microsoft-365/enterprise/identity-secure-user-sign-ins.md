---
title: 'Etapa 3: proteger e gerenciar as entradas do seu usuário'
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
description: Você pode deixar as entradas dos usuários no Windows e no Microsoft 365 mais seguras.
ms.openlocfilehash: edf51b344ed8f9c8e13587cc2ccf0ba1ed081da6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073206"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>Etapa 3: proteger e gerenciar as entradas do seu usuário

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>Usar o Windows Hello para Empresas

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

O Windows Hello para Empresas no Windows 10 Enterprise substitui senhas com autenticação forte de dois fatores ao entrar em um dispositivo Windows. O recurso de dois fatores é um novo tipo de credencial de usuário vinculado a um dispositivo e a uma leitura biométrica ou a um PIN.

Para obter mais informações, consulte [Visão geral do Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>Configurar a Autenticação Multifator do Microsoft Azure

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta etapa, você configurará a MFA (Autenticação Multifator) para adicionar uma segunda camada de segurança a entradas e transações de usuários. A MFA exige um método de verificação adicional depois que os usuários tiverem digitado a senha corretamente. Sem a MFA, a senha é o único método de verificação. O problema de usar senhas é que muitas delas são facilmente adivinhadas por um invasor ou são compartilhadas inconscientemente com pessoas não confiáveis.

Com a MFA, a segunda camada de segurança pode ser:

- Um dispositivo pessoal de confiança que não seja facilmente forjado ou duplicado, como um smartphone.
- Um atributo biométrico, como uma impressão digital.

Você habilitará a MFA e configurará o método de autenticação secundária com [Políticas de Acesso Condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), as quais permitem o uso de grupos do Azure Active Directory (Azure AD) para implementar a MFA em conjuntos de usuários específicos, como usuários piloto, em regiões geográficas ou em departamentos. Avise seus usuários que a MFA será ativada para que eles compreendam os requisitos, como o uso obrigatório de um Smartphone para acesso, e possam entrar na rede com êxito. 

Para obter mais informações, confira [Planejando uma implantação da Autenticação Multifator do Azure baseada em nuvem](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

|||
|:-------|:-----|
|![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: Autenticação Multifator do Azure](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-mfa) desta seção.

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Proteger-se contra o comprometimento de credenciais

*Isso é opcional e se aplica somente às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você aprenderá a configurar políticas de proteção contra o comprometimento de credenciais, onde um invasor determina o nome e senha da conta de um usuário para obter acesso aos serviços de nuvem e dados de uma organização. O Azure AD Identity Protection oferece várias maneiras de ajudar a impedir que um invasor comprometa as credenciais da conta de um usuário.

Com a Azure AD Identity Protection, você pode:

|||
|:---------|:---------|
|Determinar e administrar possíveis vulnerabilidades nas identidades da organização|O Azure AD usa o aprendizado de máquina para detectar anomalias e atividades suspeitas, como entrada e pós-entradas. Ao usar esses dados, o Azure AD Identity Protection gera relatórios e alertas que ajudam você a avaliar os problemas e a tomar medidas.|
|Detectar ações suspeitas relacionadas às identidades da organização e responder a essas suspeitas automaticamente|Você pode configurar políticas de risco que respondem automaticamente a problemas detectados quando um nível de risco específico tiver sido alcançado. Essas políticas, além de outros controles de Acesso Condicional fornecidos pelo Azure AD e pelo Microsoft Intune, podem bloquear automaticamente o acesso ou tomar ações corretivas, como redefinições de senha e a imposição de Autenticação Multifator do Azure para as próximas entradas.|
|Investigar incidentes suspeitos e resolvê-los com medidas administrativas|Você pode investigar eventos de risco usando informações sobre o incidente de segurança. Fluxos básicos de trabalho estão disponíveis para controlar investigações e iniciar ações de correção, como a redefinição de senhas.|

Consulte mais [informações sobre a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Consulte as [etapas para habilitar a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Como resultados desta etapa, você habilitou o Azure AD Identity Protection e está o usando para:

- Solucionar possíveis vulnerabilidades de identidade.
- Detectar possíveis tentativas de ataque à credencial.
- Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-ident-prot) desta seção.

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [Adicionar suas contas de usuário](identity-add-user-accounts.md) |
