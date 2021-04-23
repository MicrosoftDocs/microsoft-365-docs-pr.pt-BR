---
title: Trabalho de pré-requisito para implementar políticas de acesso a dispositivos e identidade - Microsoft 365 para empresas | Microsoft Docs
description: Este artigo descreve os pré-requisitos necessários para usar políticas e configurações de acesso a dispositivos e identidades.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: edce65314062f731673926195be791f77d1cb823
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952543"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabalho de pré-requisito para implementar políticas de acesso a dispositivos e identidades

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- Azure

Este artigo descreve que os administradores de pré-requisitos devem se reunir para usar políticas de acesso de dispositivo e identidade recomendadas e usar o Acesso Condicional. Ele também discute os padrões recomendados para configurar plataformas cliente para a melhor experiência de SSO (login único).

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar as políticas de acesso a dispositivos e identidades recomendadas, sua organização precisa atender aos pré-requisitos. Os requisitos são diferentes para os vários modelos de identidade e autenticação listados:

- Apenas Nuvem
- Híbrida com autenticação PHS (sincronização de hash de senha)
- Híbrido com autenticação de passagem (PTA)
- Federado

A tabela a seguir detalha os recursos de pré-requisito e sua configuração que se aplicam a todos os modelos de identidade, exceto quando notados.

|Configuração|Exceptions|Licenciamento|
|---|:---:|---|
|[Configurar PHS](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Isso deve ser habilitado para detectar credenciais vazadas e para atuar neles para o Acesso Condicional baseado em risco. **Observação:** Isso é necessário independentemente de sua organização usar autenticação federada.|Apenas Nuvem|Microsoft 365 E3 ou E5|
|[Habilita o logom único contínuo](/azure/active-directory/connect/active-directory-aadconnect-sso) para entrar automaticamente nos usuários quando eles estão em seus dispositivos de organização conectados à rede da sua organização.|Somente nuvem e federado|Microsoft 365 E3 ou E5|
|[Configurar locais nomeados](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations). O Azure AD Identity Protection coleta e analisa todos os dados de sessão disponíveis para gerar uma pontuação de risco. Recomendamos que você especifique os intervalos ip públicos da sua organização para sua rede na configuração de locais nomeados do Azure AD. O tráfego proveniente desses intervalos recebe uma pontuação de risco reduzida, e o tráfego de fora do ambiente da organização recebe uma pontuação de risco maior.||Microsoft 365 E3 ou E5|
|Registre todos os usuários para redefinição de senha de [autoatendados (SSPR) e autenticação multifafatória (MFA)](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Recomendamos que você registre usuários para a Autenticação Multifa factor do Azure AD com antecedência. A Proteção de Identidade do Azure AD usa a Autenticação Multifafação do Azure AD para executar verificação de segurança adicional. Além disso, para a melhor experiência de entrada, recomendamos que os usuários instalem o [aplicativo Microsoft Authenticator](/azure/active-directory/user-help/microsoft-authenticator-app-how-to) e o aplicativo Microsoft Company Portal em seus dispositivos. Eles podem ser instalados na loja de aplicativos para cada plataforma.||Microsoft 365 E3 ou E5|
|[Habilitar o registro automático de dispositivo de computadores Windows ingressados no domínio.](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup) O Acesso Condicional garantirá que os dispositivos que se conectam aos aplicativos sejam ingressados no domínio ou em conformidade. Para dar suporte a isso em computadores Windows, o dispositivo deve ser registrado com o Azure AD.  Este artigo discute como configurar o registro de dispositivo automático.|Apenas Nuvem|Microsoft 365 E3 ou E5|
|**Preparar sua equipe de suporte**. Tenha um plano em vigor para os usuários que não podem concluir a MFA. Isso pode estar adicionando-os a um grupo de exclusão de política ou registrando novas informações de MFA para eles. Antes de fazer qualquer uma dessas alterações sensíveis à segurança, você precisa garantir que o usuário real está fazendo a solicitação. Exigir que os gerentes dos usuários ajudem na aprovação é uma etapa eficaz.||Microsoft 365 E3 ou E5|
|[Configurar o write-back de senha para o AD local](/azure/active-directory/active-directory-passwords-getting-started). O writeback de senha permite ao Azure AD exigir que os usuários alterem suas senhas locais quando um comprometimento de conta de alto risco é detectado. Você pode habilitar esse recurso usando o Azure AD Connect de duas maneiras: habilitar o **Writeback** de Senha na tela de recursos opcionais do assistente de instalação do Azure AD Connect ou habilita-lo por meio de Windows PowerShell.|Apenas Nuvem|Microsoft 365 E3 ou E5|
|[Configurar a proteção de senha do Azure AD.](/azure/active-directory/authentication/concept-password-ban-bad) A Proteção por Senha do Microsoft Azure AD detecta e bloqueia senhas fracas conhecidas e suas variantes e também pode bloquear termos fracos adicionais específicos de sua organização. Listas de senhas globais proibidas padrão são aplicadas automaticamente a todos os usuários em um locatário do Microsoft Azure AD. Você pode definir entradas adicionais em uma lista de senhas proibidas personalizadas. Quando os usuários alteram ou redefinem suas senhas, essas listas de senhas proibidas são verificadas para garantir o uso de senhas fortes.||Microsoft 365 E3 ou E5|
|[Habilitar a Proteção de Identidade do Azure Active Directory](/azure/active-directory/identity-protection/overview-identity-protection). A Proteção de Identidade do Azure AD permite detectar possíveis vulnerabilidades que afetam as identidades da sua organização e configurar uma política de correção automatizada para baixo, médio e alto risco de login e risco de usuário.||Microsoft 365 E5 ou Microsoft 365 E3 com o complemento segurança do E5|
|**Habilitar a autenticação** [moderna para o Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) e para o Skype for Business [Online.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) A autenticação moderna é um pré-requisito para usar o MFA. A autenticação moderna é habilitada por padrão para clientes do Office 2016 e 2019, SharePoint e OneDrive for Business.||Microsoft 365 E3 ou E5|
|

## <a name="recommended-client-configurations"></a>Configurações de cliente recomendadas

Esta seção descreve as configurações padrão do cliente de plataforma que recomendamos para fornecer a melhor experiência de SSO para seus usuários, bem como os pré-requisitos técnicos para Acesso Condicional.

### <a name="windows-devices"></a>Dispositivos Windows

Recomendamos o Windows 10 (versão 2004 ou posterior), pois o Azure foi projetado para fornecer a experiência SSO mais suave possível tanto para o local quanto para o Azure AD. Dispositivos de trabalho ou de estudante devem ser configurados para ingressar diretamente no Azure AD ou se a organização usa a junção de domínio do AD local, esses dispositivos devem ser configurados para registrar-se automaticamente e silenciosamente no [Azure AD](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Para dispositivos ByOD Windows, os usuários podem usar **Adicionar conta de estudante ou trabalho.** Observe que os usuários do navegador Google Chrome em dispositivos Windows 10 precisam instalar uma extensão para obter [a](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) mesma experiência de entrada suave que os usuários do Microsoft Edge. Além disso, se sua organização tiver dispositivos Windows 8 ou 8.1 ingressados no domínio, você poderá instalar o Microsoft Workplace Join para computadores que não são do Windows 10. [Baixe o pacote para registrar](https://www.microsoft.com/download/details.aspx?id=53554) os dispositivos com o Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS

Recomendamos instalar o aplicativo [Microsoft Authenticator em](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) dispositivos de usuário antes de implantar políticas de Acesso Condicional ou MFA. No mínimo, o aplicativo deve ser instalado quando os usuários são solicitados a registrar seu dispositivo no Azure AD adicionando uma conta de estudante ou trabalho ou quando instalam o aplicativo portal da empresa do Intune para registrar seu dispositivo no gerenciamento. Isso depende da política de Acesso Condicional configurada.

### <a name="android-devices"></a>Dispositivos Android

Recomendamos que os usuários instalem o aplicativo do Portal da Empresa do [Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) e o aplicativo [Microsoft Authenticator](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes que as políticas de Acesso Condicional sejam implantadas ou quando necessárias durante determinadas tentativas de autenticação. Após a instalação do aplicativo, os usuários podem ser solicitados a se registrarem com o Azure AD ou registrar seus dispositivos com o Intune. Isso depende da política de Acesso Condicional configurada.

Também recomendamos que os dispositivos de propriedade da organização sejam padronizados em OEMs e versões que suportam Android for Work ou Samsung Knox para permitir que contas de email, sejam gerenciadas e protegidas pela política MDM do Intune.

### <a name="recommended-email-clients"></a>Clientes de email recomendados

Os clientes de email a seguir suportam autenticação moderna e Acesso Condicional.

|Plataforma|Cliente|Versão/Notas|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Habilitar autenticação moderna](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [Atualizações necessárias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Mais recente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Mais recente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 e 2016|
|**Linux**|Sem suporte||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas ao proteger documentos

Os clientes a seguir são recomendados quando uma política de documentos seguros foi aplicada.

|Plataforma|Word/Excel/PowerPoint|OneNote|Aplicativo OneDrive|Aplicativo do SharePoint|[Cliente de sincronização do OneDrive](/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|Com suporte|Com suporte|N/D|N/D|Com suporte|
|Windows 10|Com suporte|Com suporte|N/D|N/D|Com suporte|
|Android|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|iOS|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|macOS|Com suporte|Com suporte|N/D|N/D|Sem suporte|
|Linux|Sem suporte|Sem suporte|Sem suporte|Sem suporte|Sem suporte|
|

### <a name="microsoft-365-client-support"></a>Suporte ao aplicativo cliente do Microsoft 365

Para obter mais informações sobre o suporte ao cliente no Microsoft 365, consulte os seguintes artigos:

- [Suporte ao aplicativo cliente do Microsoft 365 - Acesso Condicional](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Suporte ao aplicativo cliente do Microsoft 365 - Autenticação multifafação](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>Protegendo contas de administrador

Para o Microsoft 365 E3 ou E5 ou com licenças Azure AD Premium P1 ou P2 separadas, você pode exigir MFA para contas de administrador com uma política de Acesso Condicional criada manualmente. Consulte [Acesso Condicional: Exigir MFA para administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) para obter os detalhes.

Para edições do Microsoft 365 ou office 365 que não [](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) suportam o Acesso Condicional, você pode habilitar os padrões de segurança para exigir MFA para todas as contas.

Aqui estão algumas recomendações adicionais:

- Use [o Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-getting-started) para reduzir o número de contas administrativas persistentes.
- [Use o gerenciamento de](../../compliance/privileged-access-management-overview.md) acesso privilegiado para proteger sua organização contra violações que podem usar contas de administrador privilegiadas existentes com acesso permanente a dados confidenciais ou acesso a configurações críticas.
- Criar e usar contas separadas atribuídas a funções de administrador do [Microsoft 365](../../admin/add-users/about-admin-roles.md) *somente para administração*. Os administradores devem ter sua própria conta de usuário para uso normal não administrativo e usar apenas uma conta administrativa quando necessário para concluir uma tarefa associada à função ou função de trabalho.
- Siga [as práticas recomendadas](/azure/active-directory/admin-roles-best-practices) para proteger contas privilegiadas no Azure AD.

## <a name="next-step"></a>Próxima etapa

[![Etapa 2: Configurar a identidade comum e acessar políticas de Acesso Condicional](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Configurar as políticas comuns de identidade e acesso a dispositivos](identity-access-policies.md)