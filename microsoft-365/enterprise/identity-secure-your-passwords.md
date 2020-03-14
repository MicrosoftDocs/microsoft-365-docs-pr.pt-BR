---
title: 'Etapa 2: proteger suas senhas'
f1.keywords:
- NOCSH
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
description: Você precisa de senhas fortes e gerenciáveis em toda a organização.
ms.openlocfilehash: c0ad9e2ad86cb803484e3d350fe112580610f509
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633089"
---
# <a name="step-2-secure-your-passwords"></a>Etapa 2: proteger suas senhas

![Fase 2-identidade](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>Evitar o uso de senhas ruins

*Isso é opcional e se aplica tanto à versão E3 quanto à versão E5 do Microsoft 365* 

Todos os usuários devem usar as [Diretrizes de senhas da Microsoft](https://www.microsoft.com/research/publication/password-guidance/) para criar senhas de conta de usuário.

Para impedir que os usuários criem senhas que possam ser facilmente descobertas, use a proteção de senhas do Azure AD, que usa uma lista geral e uma opcional personalizada de senhas proibidas, sendo a última especificada por você. Você pode, por exemplo, usar termos específicos da sua organização, como:

- Nomes de marcas
- Nomes de produtos
- Locais (por exemplo, sedes de empresas)
- Termos internos específicos da empresa
- Abreviaturas com significados específicos da empresa.

Você pode bloquear senhas ruins [na nuvem](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e para seu [Active Directory Domain Services (AD DS) local](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-password-prot) desta seção.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>Simplificar as redefinições de senha

*Isso é opcional e se aplica tanto à versão E3 quanto à versão E5 do Microsoft 365* 

Nesta seção, você habilitará a redefinição de senha de autoatendimento (SSPR) para permitir que usuários redefinam ou desbloqueiem suas senhas ou contas. Para ser alertado sobre uso indevido ou abuso, você pode usar os relatórios detalhados que rastreiam quando usuários acessam o sistema, junto com as notificações. Você deve habilitar o write-back de senha antes que possa implantar as redefinições de senha.

Confira as[instruções para implantar redefinição de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia de laboratório de teste: redefinição de senha](password-reset-m365-ent-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-reset) para esta seção.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>Simplificar a entrada do usuário

*Isso é opcional para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você vai configurar o Azure AD Seamless SSO (Logon Único Contínuo do Azure Active Directory), que funciona com PHS (Sincronização de Hash de Senha) e PTA (Autenticação de Passagem), para permitir que seus usuários entrem nos serviços que usam as contas de usuário do Azure AD sem precisar digitar suas senhas e em muitos casos, seus nomes de usuário. Isso facilita o acesso de seus usuários a aplicativos baseados na nuvem, como o Office 365, sem precisar de nenhum componente adicional local, como servidores de federação de identidades.

Você configura o SSO Contínuo do Azure Active Directory com a ferramenta Azure AD Connect.

Confira as [instruções para configurar o SSO Contínuo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: Logon Único Contínuo do Azure Active Directory](single-sign-on-m365-ent-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sso) para esta seção.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>Personalizar páginas de entrada do Office 365

*Isso é opcional e para as versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você ajudará usuários a reconhecer a página de entrada da sua organização ao adicionar o nome, o logotipo da sua empresa e outros elementos reconhecíveis. 

Com o Microsoft 365 Enterprise, é possível personalizar a aparência das páginas de entrada e do Painel de acesso para incluírem o logotipo da empresa, os esquemas de cores e as informações do usuário personalizadas. 

Saiba mais em [Adicionar a marca da empresa na página de entrada do Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).

Confira as instruções de configuração em [Adicionar a marca da empresa na página de entrada e no Painel de acesso](https://aka.ms/aadpaddbranding).

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-custom-sign-in) para esta seção.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![Etapa 3](../media/stepnumbers/Step3.png)| [Proteger e gerenciar as entradas do seu usuário](identity-secure-user-sign-ins.md) |
