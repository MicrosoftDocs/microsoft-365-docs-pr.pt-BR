---
title: Trabalho de pré-requisito para implementar a identidade e dispositivo acessar diretivas - Microsoft 365 Enterprise | Documentos do Microsoft
description: Descreve as políticas para as recomendações da Microsoft sobre como aplicar as configurações e políticas de dispositivo e identidade.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ee517e774e0606c62efdc67d869ad0aca5a41640
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865334"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabalho de pré-requisito para implementar políticas de acesso de dispositivo e identidade

Este artigo descreve os pré-requisitos que devem ser implementadas antes de implantar o identity recomendada e políticas de acesso de dispositivo. Este artigo também descreve as configurações de cliente de plataforma padrão que é recomendável para oferecer a melhor experiência SSO para seus usuários, bem como os pré-requisitos técnicos para acesso condicional.


## <a name="prerequisites"></a>Pré-requisitos

Antes de implementar a identidade recomendada e políticas de acesso de dispositivo, há vários pré-requisitos que deve atender a sua organização. A tabela a seguir detalha os pré-requisitos que se aplicam ao seu ambiente. 


| Configuração | Somente na nuvem | Active Directory com a sincronização de hash de senha |  Autenticação passagem |  Federação com o AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Configurar a sincronização de Hash de senha](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Isso deve ser habilitado para detectar credenciais perdidas e agir neles para acesso condicional baseado em risco. **Observação:** Isso é necessário independentemente se sua organização usa a autenticação gerenciada, como autenticação federada ou autenticação de passagem (PTA). |    | Sim | Sim | Sim |
| [Habilitar logon único perfeita](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) para entrar automaticamente usuários quando eles estão em seus dispositivos corporativos conectados à sua rede corporativa. |  | Sim | Sim |  |
| [Configure denominado redes](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Proteção de identidade AD Azure coleta e analisa todos os dados de sessão disponíveis para gerar uma pontuação de risco. Recomendamos que você especificar intervalos IP públicos da sua organização para a sua rede no Windows Azure AD denominado configuração de redes. Tráfego provenientes desses intervalos recebe uma pontuação de redução de risco e tráfego de fora do ambiente empresarial recebe uma pontuação maior de risco. | Sim  | Sim | Sim | Sim |
|[Registrar a todos os usuários de redefinição de senha de autoatendimento (SSPR) e a autenticação multifator (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Recomendamos que você registre os usuários para Azure MFA antes do tempo. Proteção de identidade do Windows Azure AD faz uso do Windows Azure MFA para executar a verificação de segurança adicionais. Além disso, para uma melhor experiência entrar, recomendamos os usuários a instalar o [aplicativo Microsoft autenticador](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) e o aplicativo de Portal da empresa Microsoft em seus dispositivos. Elas podem ser instaladas de app store em cada plataforma. | Sim | Sim | Sim | Sim |
| [Ativar o registro de automáticas de dispositivos de computadores associados a um domínio do Windows](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Acesso condicional irá se certificar de dispositivos que se conectam aos aplicativos estão associados a um domínio ou de conformidade. Para suportar isso em computadores com Windows, o dispositivo deve ser registrado com o Azure AD.  Este artigo discute como configurar a inscrição automática do dispositivo. |   | Sim |  Sim |  Sim |
| **Prepare a sua equipe de suporte**. Ter um plano para usuários que não foi possível concluir MFA. Isso poderia ser adicioná-los a um grupo de exclusão de política ou Registrando as novas informações de MFA-los. Antes de fazer qualquer uma dessas alterações de segurança, você precisará garantir que o usuário real está fazendo a solicitação. Exigir que os gerentes dos usuários para ajudá-lo com a aprovação é uma etapa efetiva. | Sim | Sim | Sim | Sim |  
| [Configure write-back de senha para AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Write-back de senha permite que o Azure AD exigir que os usuários alterar suas senhas no local quando um comprometimento da conta de alto risco é detectado. É possível habilitar esse recurso usando o Azure Connect da AD em uma das duas maneiras: habilite **Write-back de senha** na tela do Assistente de instalação Connect do Azure AD recursos opcionais, ou habilitá-lo por meio do Windows PowerShell. |   | Sim | Sim | Sim |
| [Habilitar a proteção de identidade do Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable). Proteção de identidade AD Azure permite detectar possíveis vulnerabilidades afetar identidades da sua organização e configurar uma política de correção automatizada para baixo, médio e entrada de alto risco e risco do usuário.  | Sim | Sim | Sim | Sim |
| **Habilitar autenticação moderna** para [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) e [Skype para negócios Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Autenticação moderna é um pré-requisito para usar a autenticação multifator (MFA). Autenticação moderna está habilitada por padrão para o Office 2016 clientes, SharePoint Online e OneDrive for Business. | Sim | Sim | Sim | Sim |
||||||



## <a name="recommended-client-configurations"></a>Configurações de cliente recomendadas
Esta seção descreve as configurações de cliente de plataforma padrão que é recomendável para oferecer a melhor experiência SSO para seus usuários, bem como os pré-requisitos técnicos para acesso condicional.

### <a name="windows-devices"></a>Dispositivos Windows
Recomendamos que o Windows 10 (versão 1703 ou posterior), como o Windows Azure é projetado para fornecer o SSO mais suave experiência possíveis para o local e o Azure AD. Trabalho ou escola emitidos dispositivos devem ser configurados para ingressar diretamente no Azure AD ou se a organização utiliza associação de domínio do AD no local, esses dispositivos devem ser [configurados para automaticamente e registrar silenciosamente com o Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Para os dispositivos Windows BYOD, os usuários podem usar **Adicionar trabalho ou escola conta**. Observe que os usuários do navegador Google Chrome em Windows 10 necessário para [instalar uma extensão](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) obter a mesma suave entrar experiência como usuários de borda/IE. Além disso, se sua organização tiver dispositivos associados a um domínio do Windows 7, você pode instalar ingressar de local de trabalho com a Microsoft para computadores de não - Windows 10, [Baixe o pacote para registrar](https://www.microsoft.com/download/details.aspx?id=53554) os dispositivos com o Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS
Recomendamos instalar o [aplicativo Microsoft autenticador](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) em dispositivos do usuário antes de implantar o acesso condicional ou diretivas MFA. No mínimo, o aplicativo deve ser instalado quando os usuários, serão solicitados para registrar seus dispositivos com Windows Azure AD, adicionando um trabalho ou escola conta ou ao instalar o aplicativo de portal de empresa Intune para registrar seu dispositivo para gerenciamento. Isso depende a política de acesso condicional configuradas.

### <a name="android-devices"></a>Dispositivos Android
É recomendável que os usuários instalem o [aplicativo de Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) e o [aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de políticas de acesso condicional serem implantadas ou quando necessário durante determinadas tentativas de autenticação. Após a instalação do aplicativo, os usuários podem ser solicitados a se registrarem com o Azure AD ou registrar seus dispositivos com o Intune. Isso depende da política de acesso condicional configurada.

Também recomendamos que corporativo pertencentes a dispositivos (COD) são padronizados em OEMs e versões que suportam Android para trabalho ou Samsung Knox permitir que as contas de email, sejam gerenciadas e protegidas pela política Intune MDM.


### <a name="recommended-email-clients"></a>Clientes de email recomendados
Os clientes de email a seguir oferecem suporte a autenticação moderna e acesso condicional. 

|Plataforma|Cliente|Versão/Notas|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Habilitar autenticação moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [atualizações necessárias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Mais recente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Mais recente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|Sem suporte||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas ao proteger documentos
Os seguintes clientes são recomendados quando tiver sido aplicada a uma política de documentos seguros.

|Plataforma|Word/Excel/PowerPoint|OneNote|Aplicativo OneDrive|Aplicativo do SharePoint|Cliente de sincronização do OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Com suporte|Com suporte|N/D|N/D|Versão prévia<sup>*</sup>|
|Windows 8.1|Com suporte|Com suporte|N/D|N/D|Versão prévia<sup>*</sup>|
|Windows 10|Com suporte|Com suporte|N/D|N/D|Versão prévia<sup>*</sup>|
|Windows Phone 10|Sem suporte|Sem suporte|Não suportado|Não suportado|Não suportado|
|Android|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|iOS|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|macOS|Visualização Pública|Visualização Pública|N/D|N/D|Sem suporte|
|Linux|Sem suporte|Sem suporte|Sem suporte|Sem suporte|Sem suporte|

<sup>*</sup>Saiba mais sobre como usar o acesso condicional com o [cliente de sincronização do OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Suporte ao cliente do Office 365
Para obter mais informações sobre o suporte de cliente do Office 365, consulte os seguintes artigos:
- [Suporte para aplicativos de cliente do Office 365 - acesso condicional](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Suporte para aplicativos de cliente do Office 365 - gerenciamento de aplicativos móveis](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Suporte de aplicativo de cliente do Office 365 - autenticação moderno](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Protegendo as contas de administrador
Azure AD fornece uma maneira simples para você começar a proteger o acesso de administrador com uma política de acesso condicional pré-configurado. No Windows Azure AD, vá para **acesso condicional** e procure por essa diretiva — **diretiva base: exigem MFA para os administradores**. Selecione essa diretiva e selecione **a política de uso imediatamente**. 

Esta diretiva requer MFA para as seguintes funções:
- Administradores globais
- Administradores do SharePoint
- Administradores do Exchange
- Administradores de acesso condicional
- Administradores de segurança

Para obter mais informações, consulte [diretiva de segurança de linha de base para contas de administração do Windows Azure AD](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Recomendações adicionais incluem o seguinte:
- Use o gerenciamento de identidade privilegiado do Windows Azure AD para reduzir o número de contas administrativas persistentes. Consulte a [começar a usar o PIM](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Use o gerenciamento de acesso privilegiado no Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview) para proteger sua organização contra violações que podem usar existente privilegiado contas de administrador com acesso de uma posição para dados confidenciais ou acesso às definições de configuração crítico. 
- Use contas de administrador do Office 365 para a administração. Os administradores devem ter a um usuário separado da conta para uso não-administrativa regular e só use sua conta administrativa quando necessário para concluir uma tarefa associada a seu cargo. Funções de [administrador do Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) tem substancialmente mais privilégios que os serviços do Office 365.
- Siga as práticas recomendadas para proteger contas com privilégios no Windows Azure AD, conforme descrito neste [artigo](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Próximas etapas

[Configurar a identidade comum e políticas de acesso de dispositivo](identity-access-policies.md)

