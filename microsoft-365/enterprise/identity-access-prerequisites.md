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
ms.openlocfilehash: e97b16b3520d500737e0b397e8e2a515ecac9b3f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865334"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabalho de pré-requisito para implementar políticas de acesso de dispositivo e identidade

Este artigo descreve os pré-requisitos necessários implementar antes de implantar o identity recomendada e políticas de acesso de dispositivo. Este artigo também descreve as configurações de cliente de plataforma padrão que é recomendável para oferecer a melhor experiência SSO para seus usuários, bem como os pré-requisitos técnicos para acesso condicional.


## <a name="prerequisites"></a>Pré-requisitos

Antes de implementar a identidade recomendada e políticas de acesso de dispositivo, há vários pré-requisitos que deve atender a sua organização. Consulte a tabela a seguir para os pré-requisitos que se aplicam ao seu ambiente. 


| Configuração | Somente na nuvem | Active Directory com a sincronização de hash de senha |  Federação com o AD FS |
| :------------- | :-----------: | :--------------: | :------------: |
|  [Configurar a sincronização de Hash de senha](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Isso deve ser ativado para detectar credenciais perdidas e agir neles para risco com base acesso condicional. **Observação:** Isso é necessário, independentemente se sua organização usa a autenticação gerenciada, como autenticação federada ou autenticação de passagem (PTA). |    | Sim | Sim |
| [Habilitar o logon único perfeita](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) para entrar automaticamente usuários quando eles estão em seus dispositivos corporativos conectados à sua rede corporativa. |  | Sim |  |
| [Configure denominado redes](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Proteção de identidade AD Azure coleta e analisa todos os dados de sessão disponíveis para gerar uma pontuação de risco. Recomendamos que você especificar intervalos IP públicos da sua organização para a sua rede no Windows Azure AD denominado configuração de redes. Tráfego provenientes desses intervalos recebe uma pontuação de risco reduzido, portanto o tráfego de fora do ambiente empresarial é tratado como pontuação maior de risco. | Sim  | Sim | Sim |
|[Registrar a todos os usuários de redefinição de senha de autoatendimento (SSPR) e a autenticação multifator (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Recomendamos que você registre os usuários para Azure MFA antes do tempo. Proteção de identidade do Windows Azure AD faz uso do Windows Azure MFA para executar a verificação de segurança adicionais. Além disso, para uma melhor experiência entrar, recomendamos os usuários a instalar o [Microsoft autenticador App](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) e o aplicativo de Portal da empresa Microsoft em seus dispositivos. Elas podem ser instaladas de app store em cada plataforma. | Sim | Sim | Sim |
| [Habilitar o registro automático de dispositivo de computadores Windows ingressados no domínio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). O acesso condicional pode garantir que o dispositivo se conectando ao serviço é um dispositivo em conformidade ou ingressado no domínio. Para dar suporte a isso em computadores Windows, o dispositivo deve ser registrado com o Azure AD.  Este artigo discute como configurar o registro de dispositivo automático. |   | Sim |  Sim |
| **Preparar sua equipe de suporte**. Tenha um plano em vigor para os usuários que não podem concluir a MFA. Isso pode ser adicioná-los a um grupo de exclusão de política ou registrar novas informações de MFA para eles. Antes de fazer qualquer uma dessas alterações importantes de segurança, você precisa garantir que o usuário atual está fazendo a solicitação. Exigir que os gerentes dos usuários ajudem na aprovação é uma etapa eficaz. | Sim | Sim | Sim |
| [Configurar o write-back de senha para o AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). O write-back de senha permite que o Azure AD exija que os usuários alterem suas senhas locais quando um alto risco de comprometimento de contas tiver sido detectado. Você pode habilitar esse recurso usando o Azure AD Connect de uma das duas maneiras. Você pode habilitar o write-back de senha na tela de recursos opcionais do assistente de configuração do Azure AD Connect ou pode habilitá-lo por meio do Windows PowerShell. |   | Sim | Sim |
| [Habilitar a proteção de identidade do Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable). Proteção de identidade AD Azure permite detectar possíveis vulnerabilidades afetar identidades da sua organização e configurar política de correção automatizada para baixo, médio e entrada de alto risco e o risco de usuário.  | Sim | Sim | Sim |
| **Habilitar autenticação moderna** para [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) e [Skype para negócios Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Autenticação moderna é um pré-requisito para usar a autenticação multifator (MFA). Autenticação moderna está habilitada por padrão para o Office 2016 clientes, SharePoint Online e OneDrive for Business. | Sim | Sim | Sim |
|||||



## <a name="recommended-client-configurations"></a>Configurações de cliente recomendadas
Esta seção descreve as configurações de cliente de plataforma padrão que recomendamos para oferecer a melhor experiência SSO para seus usuários, bem como os pré-requisitos técnicos para acesso condicional.

### <a name="windows-devices"></a>Dispositivos Windows
Recomendamos que o Windows 10 (versão 1703 ou posterior), como Azure foi desenvolvido para fornecer a melhor experiência de SSO possível para o Azure AD e local. Dispositivos emitidos pelo trabalho ou pela escola devem ser configurados para ingressar no Azure AD diretamente ou, se a organização usar o ingresso no domínio do AD local, esses dispositivos deverão ser [configurados para se registrar com o Azure AD de forma automática e silenciosa](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Para dispositivos Windows BYOD, os usuários podem usar "Adicionar conta corporativa ou de estudante". Observe que os usuários do navegador Chrome no Windows 10 precisam [instalar uma extensão](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) para esses usuários poderem obter a mesma experiência de entrada sem problemas que o Edge/IE. Além disso, se sua organização tiver dispositivos Windows 7 ingressados no domínio, você poderá instalar o Microsoft Workplace Join para computadores sem Windows 10 [empacotarem para registrar](https://www.microsoft.com/download/details.aspx?id=53554) os dispositivos com o Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS
Recomendamos instalar o [aplicativo Microsoft autenticador](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) em dispositivos do usuário antes de implantar o acesso condicional ou diretivas MFA. No mínimo, o aplicativo deve ser instalado quando os usuários serão solicitados a registrar seus dispositivos com o Windows Azure AD, adicionando um trabalho ou escola conta ou ao instalar o aplicativo de portal de empresa Intune para registrar seu dispositivo para gerenciamento. Isso depende a política de acesso condicional configuradas.

### <a name="android-devices"></a>Dispositivos Android
É recomendável que os usuários instalem o [aplicativo de Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
) e o [aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de políticas de acesso condicional serem implantadas ou quando necessário durante determinadas tentativas de autenticação. Após a instalação do aplicativo, os usuários podem ser solicitados a se registrarem com o Azure AD ou registrar seus dispositivos com o Intune. Isso depende da política de acesso condicional configurada.

Também recomendamos que os CODs (dispositivos corporativos) sejam padronizados em OEMs e versões que dão suporte ao Android for Work ou Samsung Knox para permitir que as contas de email sejam gerenciadas e protegidas pela política de MDM do Intune.


### <a name="recommended-email-clients"></a>Clientes de email recomendados
Os seguintes clientes de email suportam moderno de autenticação e acesso condicional. 

|Plataforma|Cliente|Versão/Notas|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Habilitar autenticação moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [Atualizações necessárias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Mais recente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Mais recente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|Sem suporte||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas ao proteger documentos
Os seguintes clientes são recomendados quando uma política de documentos seguros é aplicada.

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

<sup>*</sup>Saiba mais sobre como usar o acesso condicional com o [Cliente de sincronização do OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Suporte ao cliente do Office 365
Para obter mais informações sobre o suporte de cliente do Office 365, consulte os seguintes artigos:
- [Suporte para aplicativos de cliente do Office 365 - acesso condicional](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Suporte para aplicativos de cliente do Office 365 - gerenciamento de aplicativos móveis](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Suporte de aplicativo de cliente do Office 365 - autenticação moderno](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Protegendo as contas de administrador
Azure Active Directory fornece uma maneira simples para você começar a proteger o acesso de administrador com uma política de acesso condicional pré-configurado. Dentro do Azure AD, vá para o blade acesso condicional e procure por essa diretiva — **diretiva base: exigem MFA para os administradores**. Clique nesta diretiva e selecione a **política de uso imediatamente**. 

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
- Use contas de administrador do Office 365 para a administração. Os administradores devem ter a um usuário separado da conta para uso não-administrativa regular e só use sua conta administrativa quando necessário para concluir uma tarefa associada a seu cargo. Funções de [administrador do Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) tem privilégios significativamente mais para serviços do Office 365.
- Siga as práticas recomendadas para proteger contas com privilégios no Windows Azure AD, conforme descrito neste [artigo](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Próximas etapas

[Configurar a identidade comum e políticas de acesso de dispositivo](identity-access-policies.md)

