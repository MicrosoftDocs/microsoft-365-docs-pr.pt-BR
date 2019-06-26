---
title: Trabalho de pré-requisito para implementar a identidade e as políticas de acesso ao dispositivo-Microsoft 365 Enterprise | Microsoft docs
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
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 8ac644ccd7772d8e4c53395c8a42ff6ddbd683a6
ms.sourcegitcommit: a6878de8ab977b675a45fc847ff46a9c0365dc56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2019
ms.locfileid: "35231854"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabalho de pré-requisito para implementar as políticas de acesso de dispositivo e identidade

Este artigo descreve os pré-requisitos que precisam ser implementados antes que você possa implantar as políticas recomendadas de identidade e acesso de dispositivo. Este artigo também discute as configurações de cliente de plataforma padrão recomendamos fornecer a melhor experiência de SSO aos seus usuários, bem como os pré-requisitos técnicos para acesso condicional.


## <a name="prerequisites"></a>Pré-requisitos

Antes de implementar as políticas recomendadas de identidade e acesso de dispositivos, há vários pré-requisitos que sua organização deve atender. A tabela a seguir detalha os pré-requisitos que se aplicam ao seu ambiente. 


| Configuração | Somente na nuvem | Active Directory com sincronização de hash de senha |  Autenticação de passagem |  Federação com AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Configure a sincronização de hash de senha](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Isso deve ser habilitado para detectar credenciais vazadas e agir em busca de acesso condicional com base em risco. **Observação:** Isso é necessário independentemente de sua organização usar a autenticação gerenciada, como a autenticação de passagem (PTA) ou a autenticação federada. |    | Sim | Sim | Sim |
| [Habilitar o logon único contínuo](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) para assinar automaticamente os usuários quando eles estiverem em seus dispositivos corporativos conectados à sua rede corporativa. |  | Sim | Sim |  |
| [Configurar redes nomeadas](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). O Azure AD Identity Protection coleta e analisa todos os dados de sessão disponíveis para gerar uma pontuação de risco. Recomendamos que você especifique os intervalos de IP públicos da sua organização para sua rede na configuração de redes nomeadas do Azure AD. O tráfego proveniente desses intervalos recebe uma pontuação reduzida de risco e o tráfego de fora do ambiente corporativo recebe uma pontuação de risco maior. | Sim  | Sim | Sim | Sim |
|[Registre todos os usuários para redefinição de senha de autoatendimento (SSPR) e autenticação multifator (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Recomendamos que você registre os usuários do Azure MFA antes do tempo. O Azure AD Identity Protection utiliza o MFA do Azure para executar a verificação de segurança adicional. Além disso, para obter a melhor experiência de entrada, recomendamos que os usuários instalem o [aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) e o aplicativo do portal da empresa da Microsoft em seus dispositivos. Eles podem ser instalados a partir da loja de aplicativos para cada plataforma. | Sim | Sim | Sim | Sim |
| [Habilitar o registro automático de dispositivos de computadores Windows associados ao domínio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). O acesso condicional garantirá que os dispositivos que se conectam aos aplicativos são associados ao domínio ou estão em conformidade. Para dar suporte a isso em computadores Windows, o dispositivo deve ser registrado com o Azure AD.  Este artigo discute como configurar o registro de dispositivo automático. |   | Sim |  Sim |  Sim |
| **Preparar sua equipe de suporte**. Tenha um plano em vigor para os usuários que não podem concluir a MFA. Isso pode ser adicionado a um grupo de exclusão de política ou registrar novas informações da MFA para elas. Antes de fazer qualquer uma dessas alterações confidenciais de segurança, você precisa garantir que o usuário real está fazendo a solicitação. Exigir que os gerentes dos usuários ajudem na aprovação é uma etapa eficaz. | Sim | Sim | Sim | Sim |  
| [Configurar o write-back de senha para o AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). O Write-back de senha permite ao Azure AD exigir que os usuários alterem suas senhas locais quando um comprometimento de conta de alto risco for detectado. Você pode habilitar esse recurso usando o Azure AD Connect de duas maneiras: habilite o **write-back de senha** na tela recursos opcionais do assistente de configuração do Azure ad Connect ou habilite-o por meio do Windows PowerShell. |   | Sim | Sim | Sim |
| [Habilitar a proteção de identidade do Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable). O Azure AD Identity Protection permite que você detecte possíveis vulnerabilidades que afetam as identidades da sua organização e configure uma política de correção automatizada para riscos de entrada baixa, média e alta e o risco do usuário.  | Sim | Sim | Sim | Sim |
| **Habilitar a autenticação moderna** do [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) e do [Skype for Business online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). A autenticação moderna é um pré-requisito para usar a MFA (autenticação multifator). A autenticação moderna está habilitada por padrão para clientes do Office 2016, SharePoint Online e OneDrive for Business. | Sim | Sim | Sim | Sim |
||||||



## <a name="recommended-client-configurations"></a>Configurações de cliente recomendadas
Esta seção descreve as configurações do cliente de plataforma padrão recomendamos fornecer a melhor experiência de SSO para seus usuários, bem como os pré-requisitos técnicos para acesso condicional.

### <a name="windows-devices"></a>Dispositivos Windows
Recomendamos que o Windows 10 (versão 1703 ou posterior), como Azure foi desenvolvido para fornecer a melhor experiência de SSO possível para o Azure AD e local. Os dispositivos de trabalho ou de estudante emitidos devem ser configurados para ingressar no Azure AD diretamente ou se a organização usar o ingresso no domínio do AD local, esses dispositivos devem ser configurados [para registrar-se automaticamente e silenciosamente no Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Para os dispositivos do Windows BYOD, os usuários podem usar **adicionar conta corporativa ou de estudante**. Observe que os usuários do navegador Chrome no Windows 10 precisam [instalar uma extensão](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) para obter a mesma experiência de entrada suave que os usuários de borda/IE. Além disso, se sua organização tiver dispositivos Windows 7 associados ao domínio, você poderá instalar o Microsoft Workplace Join para computadores que não são Windows 10, [baixar o pacote para registrar](https://www.microsoft.com/download/details.aspx?id=53554) os dispositivos com o Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS
É recomendável instalar o [aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) em dispositivos de usuário antes de implantar o acesso condicional ou políticas de MFA. No mínimo, o aplicativo deve ser instalado quando os usuários são solicitados a registrar seus dispositivos com o Azure AD adicionando uma conta corporativa ou de estudante, ou quando instalam o aplicativo portal da empresa do Intune para registrar seus dispositivos no gerenciamento. Isso depende da política de acesso condicional configurada.

### <a name="android-devices"></a>Dispositivos Android
É recomendável que os usuários instalem o [aplicativo de Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) e o [aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de políticas de acesso condicional serem implantadas ou quando necessário durante determinadas tentativas de autenticação. Após a instalação do aplicativo, os usuários podem ser solicitados a se registrarem com o Azure AD ou registrar seus dispositivos com o Intune. Isso depende da política de acesso condicional configurada.

Também recomendamos que os dispositivos de propriedade corporativa (COD) sejam padronizados em OEMs e versões que dão suporte ao Android para trabalho ou ao Samsung Knox para permitir contas de email, ser gerenciados e protegidos pela política MDM do Intune.


### <a name="recommended-email-clients"></a>Clientes de email recomendados
Os seguintes clientes de email dão suporte a autenticação moderna e acesso condicional. 

|Plataforma|Cliente|Versão/Notas|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [habilitar a autenticação moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [atualizações necessárias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Mais recente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Mais recente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|Sem suporte||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas ao proteger documentos
Os clientes a seguir são recomendados quando uma política de documentos seguros foi aplicada.

|Plataforma|Word/Excel/PowerPoint|OneNote|Aplicativo OneDrive|Aplicativo do SharePoint|Cliente de sincronização do OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Com suporte|Com suporte|N/D|N/D|Versão prévia<sup>*</sup>|
|Windows 8.1|Com suporte|Com suporte|N/D|N/D|Versão prévia<sup>*</sup>|
|Windows 10|Com suporte|Com suporte|N/D|N/D|Versão prévia<sup>*</sup>|
|Windows Phone 10|Sem suporte|Sem suporte|Não Suportado|Não Suportado|Não Suportado|
|Android|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|iOS|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|macOS|Visualização Pública|Visualização Pública|N/D|N/D|Sem suporte|
|Linux|Sem suporte|Sem suporte|Sem suporte|Sem suporte|Sem suporte|

<sup>*</sup>Saiba mais sobre como usar o acesso condicional com o [cliente de sincronização do onedrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Suporte ao cliente do Office 365
Para obter mais informações sobre o suporte ao cliente do Office 365, consulte os seguintes artigos:
- [Suporte ao aplicativo cliente do Office 365-acesso condicional](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Suporte ao aplicativo cliente do Office 365-gerenciamento de aplicativo móvel](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Suporte ao aplicativo cliente do Office 365-autenticação moderna](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Protegendo contas de administrador
O Azure AD oferece uma maneira simples de começar a proteger o acesso de administrador com uma política de acesso condicional pré-configurada. No Azure AD, acesse **acesso condicional** e procure esta política – **política de linha de base: exigir MFA para administradores (visualização)**. Selecione esta política e selecione **usar política imediatamente**. 

Esta política requer MFA para as seguintes funções:
- Administradores globais
- Administradores do SharePoint
- Administradores do Exchange
- Administradores de acesso condicional
- Administradores de segurança

Para obter mais informações, consulte [Baseline Security Policy for Azure ad admin](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)accounts.

As recomendações adicionais incluem o seguinte:
- Use o Azure AD Privileged Identity Management para reduzir o número de contas administrativas persistentes. Confira [começar a usar o PIM](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Use o gerenciamento de acesso privilegiado no Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview) para proteger sua organização contra violações que podem usar contas de administrador privilegiadas existentes com acesso à posição para dados confidenciais ou acesso a definições de configuração crítica. 
- Use as contas de administrador somente para administração. Os administradores devem ter uma conta de usuário separada para uso não administrativo regular e só usar a conta administrativa, quando necessário, para concluir uma tarefa associada à função de trabalho. As funções de [administrador do office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) têm muito mais privilégios do que os serviços do Office 365.
- Siga as práticas recomendadas para proteger contas privilegiadas no Azure AD, conforme descrito neste [artigo](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Próximas etapas

[Configurar as políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md)

