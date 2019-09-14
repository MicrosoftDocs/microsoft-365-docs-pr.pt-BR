---
title: 'Etapa 5: Simplificar o acesso para usuários'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure a redefinição de senha de autoatendimento (SSPR) do Azure Active Directory.
ms.openlocfilehash: ec81b2931fd4ad599ffcf983ea8a7d764c56404a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981792"
---
# <a name="step-5-simplify-access-for-users"></a>Etapa 5: Simplificar o acesso para usuários

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>Simplificar as atualizações de senha

*Isso é opcional para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você permitirá que os usuários redefinam suas senhas através do Azure Active Directory (Azure AD) que depois é replicada para os seus serviços locais de domínio do Active Directory (AD DS). Este processo é conhecido como write-back de senha. Com o write-back de senha, os usuários não precisam atualizar suas senhas através dos serviços locais de domínio do AD DS, onde as contas de usuário e seus atributos são armazenados. Isso é valioso para usuários móveis ou remotos que não têm uma conexão de acesso remoto à rede local.

O write-back de senha é necessário para o uso por completo das capacidades de Proteção de Identidade do Azure AD, por exemplo para exigir que os usuários alterem a senha local quando for detectado um alto risco de comprometimento da conta.

Para obter mais informações e instruções de configuração, consulte o artigo sobre o [Azure AD SSPR com o write-back de senha](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Atualize para a versão mais recente do Azure AD Connect a fim de garantir a melhor experiência possível e o acesso a novos recursos à medida que são lançados. Para saber mais, consulte as informações sobre a [instalação personalizada do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

|||
|:-------|:-----|
|![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia de laboratório de teste: write-back de senha](password-writeback-m365-ent-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-writeback) para esta seção.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>Simplificar as redefinições de senha

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você habilitará a redefinição de senha de autoatendimento (SSPR) para permitir que usuários redefinam ou desbloqueiem suas senhas ou contas. Para ser alertado sobre uso indevido ou abuso, você pode usar os relatórios detalhados que rastreiam quando usuários acessam o sistema, junto com as notificações. Você deve habilitar o write-back de senha antes que possa implantar as redefinições de senha.

Confira as[instruções para implantar redefinição de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia de laboratório de teste: redefinição de senha](password-reset-m365-ent-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-reset) para esta seção.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>Simplificar a entrada do usuário

*Isso é opcional para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você vai configurar o Logon Único Contínuo do Azure Active Directory (Azure AD Seamless SSO) para permitir que seus usuários entrem nos serviços que usam as contas de usuário do Azure AD sem precisar digitar suas senhas e em muitos casos, seus nomes de usuário. Isso facilita o acesso de seus usuários a aplicativos baseados na nuvem, como o Office 365, sem precisar de nenhum componente adicional local, como servidores de federação de identidades.

Você configura o SSO Contínuo do Azure Active Directory com a ferramenta Azure AD Connect.

Confira as [instruções para configurar o SSO Contínuo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: Logon Único Contínuo do Azure Active Directory](single-sign-on-m365-ent-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sso) para esta seção.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>Personalizar páginas de entrada do Office 365

*Isso é opcional e para as versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você ajudará usuários a reconhecer a página de entrada da sua organização ao adicionar o nome, o logotipo da sua empresa e outros elementos reconhecíveis. 

Com o Microsoft 365 Enterprise, é possível personalizar a aparência das páginas de entrada e do Painel de acesso para incluírem o logotipo da empresa, os esquemas de cores e as informações do usuário personalizadas. 

Saiba mais em [Adicionar a marca da empresa na página de entrada do Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).

Confira as instruções de configuração em [Adicionar a marca da empresa na página de entrada e no Painel de acesso](http://aka.ms/aadpaddbranding).

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-custom-sign-in) para esta seção.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [Usar grupos para facilitar o gerenciamento](identity-self-service-group-management.md) |


