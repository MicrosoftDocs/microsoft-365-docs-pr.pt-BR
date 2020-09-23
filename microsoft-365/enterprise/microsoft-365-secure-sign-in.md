---
title: Proteger as entradas do usuário ao locatário do seu Microsoft 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Exija que seus usuários se conectem com segurança usando a autenticação multifator (MFA) e outros recursos.
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132233"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Proteger as entradas do usuário ao locatário do seu Microsoft 365

Para aumentar a segurança das entradas do usuário:

- Use a Proteção por Senha do Azure Active Directory (Azure AD)
- Use a autenticação multifator (MFA)
- Implante políticas de identidade e acesso a dispositivos

## <a name="azure-ad-password-protection"></a>Proteção por Senha do Microsoft Azure AD

A Proteção por Senha do Microsoft Azure AD detecta e bloqueia senhas fracas conhecidas e suas variantes e também pode bloquear termos fracos adicionais específicos de sua organização. Listas de senhas globais proibidas padrão são aplicadas automaticamente a todos os usuários em um locatário do Microsoft Azure AD. Você pode definir entradas adicionais em uma lista de senhas proibidas personalizadas. Quando os usuários alteram ou redefinem suas senhas, essas listas de senhas proibidas são verificadas para garantir o uso de senhas fortes.

Para obter mais informações, confira [Configurar a proteção por senha do Microsoft Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).

## <a name="mfa"></a>MFA

A MFA exige que as entradas do usuário estejam sujeitas a uma verificação adicional, além da senha da conta do usuário. Mesmo que um usuário mal-intencionado determine uma senha de conta de usuário, ele também deverá responder a uma verificação adicional, como uma mensagem de texto enviada a um smartphone antes do acesso ser concedido.

![A senha correta, mais uma verificação adicional, resulta em uma entrada bem-sucedida](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

A primeira etapa para usar a MFA é ***exigi-lo para todas as contas de administrador***, também conhecidas como contas privilegiadas.

Além dessa primeira etapa, a Microsoft recomenda a MFA para todos os usuários.

Há três maneiras de exigir que seus administradores ou usuários usem a MFA com base no seu plano do Microsoft 365.

| Planejar | Recomendação |
|---------|---------|
|Planos do Microsoft 365 (sem licenças do Microsoft Azure AD Premium P1 ou P2)     |[Habilitar os padrões de segurança no Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Os padrões de segurança no Microsoft Azure Active Directory incluem a MFA para usuários e administradores.   |
|Microsoft 365 E3 (inclui licenças do Azure AD Premium P1)     | Use [políticas de Acesso Condicional Comuns](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar as seguintes políticas: <br>- [Exigir MFA para administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Bloquear autenticação herdada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (inclui licenças do Azure AD Premium P2)     | Aproveitando a Azure Active Directory Identity Protection, comece a implementar o [conjunto recomendado de acesso condicional e políticas relacionadas](../enterprise/identity-access-policies.md) da Microsoft, criando estas duas políticas:<br> - [Exigir MFA quando o risco de entrada for médio ou alto](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Usuários de alto risco devem alterar a senha](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>Padrões de segurança

Os padrões de segurança são um novo recurso para assinaturas pagas ou de avaliação do Microsoft 365 e Office 365 criadas após 21 de outubro de 2019. Essas assinaturas têm padrões de segurança ativados, o que ***exige que todos os seus usuários usem a MFA com o aplicativo Microsoft Authenticator***.
 
Os usuários têm 14 dias para se registrar na MFA com o aplicativo Microsoft Authenticator em seus smartphones, que começa na primeira vez em que eles entram depois de os padrões de segurança terem sido habilitados. Após 14 dias, o usuário não poderá entrar até que o registro da MFA seja concluído.

Os padrões de segurança garantem que todas as organizações tenham um nível básico de segurança para a entrada do usuário, que é habilitado por padrão. Você pode desativar os padrões de segurança em favor da MFA com políticas de Acesso Condicional ou para contas individuais.

Para obter mais informações, confira esta [visão geral dos padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Políticas de Acesso Condicional

As políticas de Acesso Condicional são um conjunto de regras que especificam as condições sob as quais as entradas são avaliadas e o acesso é concedido. Por exemplo, você pode criar uma política de acesso condicional que declare:

- Se o nome da conta de usuário for membro de um grupo para usuários a quem são atribuídas as funções de administrador do Exchange, de usuário, de senha, de segurança, do SharePoint ou global, exija a MFA antes de permitir o acesso.

Essa política permite exigir a MFA com base na associação ao grupo, em vez de tentar configurar contas de usuário individuais para a MFA quando elas são atribuídas ou não a essas funções de administrador.

Você também pode usar políticas de Acesso Condicional para recursos mais avançados, como exigir que a entrada seja feita a partir de um dispositivo compatível, como o seu laptop executando o Windows 10.

O Acesso Condicional requer as licenças do Microsoft Azure AD Premium P1, incluídas no Microsoft 365 E3 e E5.

Para mais informações, confira esta [visão geral do Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="using-these-methods-together"></a>Usando esses métodos juntos

Lembre-se do seguinte:

- Você não pode habilitar os padrões de segurança se tiver alguma política de Acesso Condicional ativada.
- Você não pode habilitar nenhuma política de Acesso Condicional se tiver os padrões de segurança habilitados.

Se os padrões de segurança estiverem ativados, todos os novos usuários serão solicitados a fazer o registro da MFA e usar o aplicativo Microsoft Authenticator. 

Esta tabela mostra os resultados da habilitação da MFA com padrões de segurança e políticas de Acesso Condicional.

| Método | Habilitado | Desabilitado | Método de autenticação adicional |
|:-------|:-----|:-------|:-------|
| **Padrões de segurança**  | Não é possível usar políticas de Acesso Condicional | Pode usar políticas de Acesso Condicional | Aplicativo Microsoft Authenticator |
| **Políticas de Acesso Condicional** | Se alguma delas estiver habilitada, você não poderá habilitar os padrões de segurança | Se todas estiverem desabilitadas, você poderá habilitar os padrões de segurança  | Especificado pelo usuário durante o registro da MFA  |
||||

## <a name="identity-and-device-access-policies"></a>Políticas de identidade e acesso a dispositivos

As configurações e políticas de identidade e acesso a dispositivos são recursos de pré-requisito recomendados e suas configurações combinadas com as políticas de Acesso Condicional, Intune e Azure AD Identity Protection que determinam se uma determinada solicitação de acesso deve ser concedida e sob quais condições. Essa determinação é baseada na conta do usuário da entrada, no dispositivo que está sendo usado, no aplicativo que o usuário está usando para acessar, no local a partir do qual a solicitação de acesso é feita e em uma avaliação do risco da solicitação. Esse recurso ajuda a garantir que apenas usuários e dispositivos aprovados possam acessar os recursos críticos.

>[!Note]
>A Azure AD Identity Protection exige as licenças do Microsoft Azure AD Premium P2, incluídas no Microsoft 365 E5.
>

As políticas de identidade e acesso a dispositivos são definidas para serem usadas em três camadas: 

- A proteção de linha de base é um nível mínimo de segurança para suas identidades e dispositivos que acessam seus aplicativos e dados.
- A proteção confidencial fornece segurança adicional para dados específicos. Identidades e dispositivos estão sujeitos a níveis mais altos de requisitos de segurança e integridade do dispositivo.
- A proteção para ambientes com dados altamente regulamentados ou confidenciais é geralmente destinada para pequenas quantidades de dados extremamente confidenciais, contêm segredos comerciais ou estão sujeitos a regulamentações de dados. Identidades e dispositivos estão sujeitos a níveis muito mais altos de requisitos de segurança e integridade do dispositivo. 

Essas camadas e suas configurações correspondentes fornecem níveis consistentes de proteção em seus dados, identidades e dispositivos.

A Microsoft recomenda a configuração e distribuição de políticas de identidade de acesso a dispositivos em sua organização, incluindo configurações específicas para o Microsoft Teams, Exchange Online e SharePoint. Para obter mais informações, confira [Configurações de identidade e acesso a dispositivos](microsoft-365-policies-configurations.md).

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>Recursos técnicos de administração para MFA e entradas seguras

- [MFA do Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Roteiro da identidade do Microsoft 365](identity-roadmap-microsoft-365.md)
- [Vídeos de treinamento do Microsoft Azure Active Directory da Azure Academy](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Configurar a política de registro da Autenticação Multifator do Azure](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [Configurações de identidade e acesso a dispositivos](microsoft-365-policies-configurations.md)

