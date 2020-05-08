---
title: Etapa 1. Aumentar a segurança de entrada para funcionários remotos com a MFA
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Exigir que seus funcionários remotos entrem com autenticação multifator (MFA).
ms.openlocfilehash: dfb4262c05399e1c5add9b151c42c143ac723a7d
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066122"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>Etapa 1. Aumentar a segurança de entrada para funcionários remotos com a MFA

Para aumentar a segurança das entradas dos seus trabalhadores remotos, use a autenticação multifator (MFA). A MFA exige que as entradas do usuário estejam sujeitas a uma verificação adicional, além da senha da conta do usuário. Mesmo que um usuário mal-intencionado determine uma senha de conta de usuário, ele também deverá responder a uma verificação adicional, como uma mensagem de texto enviada a um smartphone antes do acesso ser concedido.

![A senha correta, mais uma verificação adicional, resulta em uma entrada bem-sucedida](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Para todos os usuários, incluindo trabalhadores remotos e especialmente administradores, a Microsoft recomenda a MFA.

Há três maneiras de exigir que seus usuários usem a MFA com base no seu plano do Microsoft 365.

|Plano  |Recomendação  |
|---------|---------|
|Planos do Microsoft 365 (sem o Microsoft Azure Active Directory Premium P1 ou P2)     |[Habilitar os padrões de segurança no Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Os padrões de segurança no Microsoft Azure Active Directory incluem a MFA para usuários e administradores.   |
|Microsoft 365 E3 (com o Microsoft Azure Active Directory Premium P1)     | Use [políticas de Acesso Condicional Comuns](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar as seguintes políticas: <br>- [Exigir MFA para administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Bloquear autenticação herdada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (com o Microsoft Azure Active Directory Premium P2)     | Aproveitando a Azure Active Directory Identity Protection, comece a implementar o [conjunto recomendado de acesso condicional e políticas relacionadas](../enterprise/identity-access-policies.md) da Microsoft, criando estas duas políticas:<br> - [Exigir MFA quando o risco de entrada for médio ou alto](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Bloquear clientes sem suporte para a autenticação moderna](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Usuários de alto risco devem alterar a senha](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Padrões de segurança

Os padrões de segurança são um novo recurso para assinaturas pagas ou de avaliação do Microsoft 365 e Office 365 criadas após 21 de outubro de 2019. Essas assinaturas têm padrões de segurança ativados, o que ***exige que todos os seus usuários usem a MFA com o aplicativo Microsoft Authenticator***.
 
Os usuários têm 14 dias para se registrar na MFA com o aplicativo Microsoft Authenticator em seus smartphones, que começa na primeira vez em que eles entram depois de os padrões de segurança terem sido habilitados. Após 14 dias, o usuário não poderá entrar até que o registro da MFA seja concluído.

Os padrões de segurança garantem que todas as organizações tenham um nível básico de segurança para a entrada do usuário, que é habilitado por padrão. Você pode desativar os padrões de segurança em favor da MFA com políticas de Acesso Condicional ou para contas individuais.

Para obter mais informações, confira esta [visão geral dos padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

## <a name="conditional-access-policies"></a>Políticas de Acesso Condicional

As políticas de acesso condicional são um conjunto de regras que especificam as condições sob as quais as entradas são avaliadas e permitidas. Por exemplo, você pode criar uma política de acesso condicional que declare:

- Se o nome da conta do usuário for para um usuário que for um administrador do Exchange, de usuário, de senha, de segurança, do Microsoft Office SharePoint Online ou global, exija a MFA antes de permitir o acesso.

Essa política é mais fácil do que tentar lembrar de configurar contas de usuário individuais para a MFA quando elas são adicionadas ou removidas dessas funções de administrador.

Você também pode usar políticas de Acesso Condicional para recursos mais avançados, como exigir que a entrada seja feita a partir de um dispositivo compatível, como o seu laptop executando o Windows 10.

O Acesso Condicional requer o Microsoft Azure Active Directory Premium P1, incluído no Microsoft 365 E3 e E5.

Para mais informações, confira esta [visão geral do Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

## <a name="azure-ad-identity-protection-policies"></a>Políticas da Azure Active Directory Identity Protection

As políticas da Azure Active Directory Identity Protection são regras que especificam as condições sob as quais as entradas são avaliadas e permitidas. Por exemplo, você pode criar uma política da Azure Active Directory Identity Protection que declare:

- Se o risco de entrada for determinado como médio ou alto, o usuário deverá usar a MFA para entrar.

A Azure Active Directory Identity Protection requer o Microsoft Azure Active Directory Premium P2, incluído no Microsoft 365 E5.

Para obter mais informações, confira esta [visão geral da Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

## <a name="using-these-methods-together"></a>Usando esses métodos juntos

Lembre-se do seguinte:

- Você não pode habilitar os padrões de segurança se tiver alguma política de Acesso Condicional ativada.
- Você não pode habilitar nenhuma política de Acesso Condicional se tiver os padrões de segurança habilitados.

Se os padrões de segurança estiverem ativados, todos os novos usuários serão solicitados a fazer o registro da MFA e usar o aplicativo Microsoft Authenticator. 

Esta tabela mostra os resultados da ativação da MFA com padrões de segurança, políticas de Acesso Condicional e configurações de conta por usuário.

|| Habilitado | Desabilitado | Método de autenticação secundária |
|:-------|:-----|:-------|:-------|
| **Padrões de segurança**  | Não é possível usar políticas de Acesso Condicional | Pode usar políticas de Acesso Condicional | Aplicativo Microsoft Authenticator |
| **Políticas de Acesso Condicional** | Se alguma delas estiver habilitada, você não poderá habilitar os padrões de segurança | Se nenhuma estiver habilitada, você poderá habilitar os padrões de segurança  | Especificado pelo usuário durante o registro da MFA  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>Treinamento de administrador e recursos técnicos para MFA e identidade

- [Planejamento de MFA para Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [As 5 principais formas como o Microsoft Azure Active Directory pode ajudar você a habilitar o trabalho remoto](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Planejar e implantar sua infraestrutura de identidade do Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Vídeos de treinamento do Microsoft Azure Active Directory da Azure Academy](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Configurar a política de registro da Autenticação Multifator do Azure](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>Resultados da Etapa 1

Após a implantação da MFA, seus usuários:

- Necessitam usar a MFA para entradas.
- Concluíram o processo de registro da MFA e estão usando a MFA para todas as entradas.

## <a name="next-step"></a>Próxima etapa

Continue com a [Etapa 2](empower-people-to-work-remotely-remote-access.md) para fornecer acesso remoto a aplicativos e serviços locais.
