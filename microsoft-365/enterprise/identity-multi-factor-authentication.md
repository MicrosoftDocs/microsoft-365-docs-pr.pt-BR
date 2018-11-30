---
title: 'Etapa 5: Configurar a autenticação multifator'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar a autenticação multifator nas contas de usuário.
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865163"
---
# <a name="step-5-set-up-multi-factor-authentication"></a>Etapa 5: Configurar a autenticação multifator

*Esta etapa é opcional e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai configurar a autenticação multifator (MFA) para adicionar uma segunda camada de segurança nas transações e entradas de usuário. A MFA requer um método de verificação adicional após os usuários inserirem corretamente a sua senha. Sem a MFA, a senha é o único método de verificação. O problema com as senhas é que muitas delas são facilmente decifradas por invasores ou compartilhadas sem intenção com terceiros não confiáveis.

Com a MFA, a segunda camada de segurança pode ser:

- Um dispositivo pessoal de confiança que não seja facilmente forjado ou duplicado, como um smartphone.
- Um atributo biométrico, como uma impressão digital.

Você vai habilitar a MFA e configurar o método de autenticação secundária em cada conta de usuário. Avise os usuários que a MFA será ativada para que eles compreendam os requisitos, como o uso obrigatório de um Smartphone para acesso, e possam entrar na rede com êxito.

Para saber mais, consulte as informações sobre como [planejar a autenticação multifator para implantações do Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).

Para saber mais, consulte o artigo sobre como [configurar a autenticação multifator para usuários do Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).

Você pode exigir a MFA com políticas de acesso condicional. Por exemplo, é possível configurar uma política que exige a MFA quando a autenticação for considerada de médio ou alto risco. Para saber mais, confira [Políticas de acesso de dispositivo e identidade comuns](identity-access-policies.md#require-mfa-based-on-sign-in-risk).

>[!Note]
>Em alguns aplicativos, como o Microsoft Office 2010 ou mais antigos e o Apple Mail, não é possível usar a MFA. Para usar esses aplicativos, é necessário usar "senhas de aplicativo" em vez da sua senha tradicional. A senha de aplicativo permite que o aplicativo ignore a MFA e continue funcionando. Para saber mais sobre as senhas de aplicativo, consulte as informações sobre como [criar uma senha de aplicativo para o Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).
>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: autenticação multifator](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-mfa) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [Proteger contra o comprometimento de credenciais](identity-azure-ad-identity-protection.md) |

