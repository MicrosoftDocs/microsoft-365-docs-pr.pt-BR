---
title: Trabalho de pré-requisito para implementar políticas de acesso a identidades e dispositivos - Microsoft 365 para empresas | Microsoft Docs
description: Este artigo descreve os pré-requisitos que você precisa atender para usar configurações e políticas de acesso a dispositivos e identidades.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
ms.date: 09/01/2020
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
ms.openlocfilehash: a479d1bf7fee95a7d8ba862674cd75bfd3c699c7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932557"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabalho de pré-requisito para implementar políticas de acesso a identidades e dispositivos

Este artigo descreve os pré-requisitos que os administradores devem atender para usar as políticas de acesso a dispositivos e identidade recomendadas e usar o Acesso Condicional. Ele também aborda os padrões recomendados para configurar plataformas de cliente para a melhor experiência de SSO (single sign-on).

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar as políticas de acesso a identidades e dispositivos recomendadas, sua organização precisa atender aos pré-requisitos. Os requisitos são diferentes para os vários modelos de identidade e autenticação listados:

- Apenas Nuvem
- Híbrida com autenticação phS (sincronização de hash de senha)
- Híbrido com autenticação de passagem (PTA)
- Federado

A tabela a seguir detalha os recursos de pré-requisito e suas configurações que se aplicam a todos os modelos de identidade, exceto quando notados.

|Configuração|Exceptions|
|---|:---:|
|[Configurar PHS](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Isso deve ser habilitado para detectar credenciais vazadas e agir sobre elas para acesso condicional baseado em risco. **Observação:** Isso é necessário independentemente de sua organização usar ou não a autenticação federada.|Apenas Nuvem|
|[Habilita o logor único contínuo](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) para conectar automaticamente os usuários quando eles estão nos dispositivos da organização conectados à rede da sua organização.|Somente nuvem e federado|
|[Configurar redes nomeadas](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). O Azure AD Identity Protection coleta e analisa todos os dados de sessão disponíveis para gerar uma pontuação de risco. Recomendamos que você especifique os intervalos de IP públicos da sua organização para sua rede na configuração de redes nomeadas do Azure AD. O tráfego proveniente desses intervalos recebe uma pontuação de risco reduzida, e o tráfego de fora do ambiente da organização recebe uma pontuação de risco maior.||
|Registre todos os usuários para redefinição de senha de autoatendado [(SSPR) e autenticação multifa factor (MFA).](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) Recomendamos que você registre os usuários para a Autenticação Multifa factor do Azure AD com antecedência. O Azure AD Identity Protection usa a Autenticação Multifa factor do Azure AD para executar uma verificação de segurança adicional. Além disso, para obter a melhor experiência de entrada, recomendamos que os usuários instalem o aplicativo [Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) e o aplicativo Microsoft Company Portal em seus dispositivos. Eles podem ser instalados na loja de aplicativos para cada plataforma.||
|[Habilitar o registro automático de dispositivo de computadores Windows ingressados no domínio.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup) O Acesso Condicional garantirá que os dispositivos que se conectam a aplicativos sejam ingressados no domínio ou compatíveis. Para dar suporte a isso em computadores Windows, o dispositivo deve ser registrado com o Azure AD.  Este artigo discute como configurar o registro de dispositivo automático.|Apenas Nuvem|
|**Preparar sua equipe de suporte**. Tenha um plano em vigor para os usuários que não podem concluir a MFA. Isso pode estar adicionando-os a um grupo de exclusão de política ou registrando novas informações de MFA para eles. Antes de fazer qualquer uma dessas alterações sensíveis à segurança, você precisa garantir que o usuário real está fazendo a solicitação. Exigir que os gerentes dos usuários ajudem na aprovação é uma etapa eficaz.||
|[Configurar o write-back de senha para o AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). O write-back de senha permite que o Azure AD exige que os usuários alterem suas senhas locais quando um comprometimento de conta de alto risco é detectado. Você pode habilitar esse recurso usando o Azure AD Connect de duas maneiras: habilitando o **Write-back** de Senha na tela de recursos opcionais do assistente de configuração do Azure AD Connect ou habilitando-o por meio do Windows PowerShell.|Apenas Nuvem|
|Configure a proteção por senha [do Azure AD.](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) A Proteção por Senha do Microsoft Azure AD detecta e bloqueia senhas fracas conhecidas e suas variantes e também pode bloquear termos fracos adicionais específicos de sua organização. Listas de senhas globais proibidas padrão são aplicadas automaticamente a todos os usuários em um locatário do Microsoft Azure AD. Você pode definir entradas adicionais em uma lista de senhas proibidas personalizadas. Quando os usuários alteram ou redefinem suas senhas, essas listas de senhas proibidas são verificadas para garantir o uso de senhas fortes.||
|[Habilita o Azure Active Directory Identity Protection.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection) O Azure AD Identity Protection permite detectar possíveis vulnerabilidades que afetam as identidades da sua organização e configurar uma política de correção automatizada para baixo, médio e alto risco de login e risco do usuário.||
|**Habilitar a** [autenticação moderna para o Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) e para o Skype for Business [Online.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) A autenticação moderna é um pré-requisito para usar a MFA. A autenticação moderna é habilitada por padrão para clientes do Office 2016 e 2019, SharePoint e OneDrive for Business.||
|

## <a name="recommended-client-configurations"></a>Configurações de cliente recomendadas

Esta seção descreve as configurações padrão do cliente da plataforma que recomendamos para fornecer a melhor experiência de SSO aos usuários, bem como os pré-requisitos técnicos para Acesso Condicional.

### <a name="windows-devices"></a>Dispositivos Windows

Recomendamos o Windows 10 (versão 2004 ou posterior), pois o Azure foi projetado para fornecer a experiência de SSO mais suave possível para o Azure AD e local. Dispositivos emitidos pelo trabalho ou pela escola devem ser configurados para ingressar diretamente no Azure AD ou se a organização usa o ingressar no domínio do AD local, esses dispositivos devem ser configurados para se registrar automaticamente e silenciosamente no [Azure AD.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

Para dispositivos Windows BYOD, os usuários podem usar **Adicionar conta comercial ou de estudante.** Observe que os usuários do navegador Google Chrome em dispositivos Windows 10 precisam instalar uma extensão para obter [a](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) mesma experiência de entrada suave que os usuários do Microsoft Edge. Além disso, se sua organização tiver dispositivos Windows 8 ou 8.1 ingressados no domínio, você poderá instalar o Microsoft Workplace Join para computadores que não são do Windows 10. [Baixe o pacote para registrar os](https://www.microsoft.com/download/details.aspx?id=53554) dispositivos com o Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS

Recomendamos instalar o aplicativo [Microsoft Authenticator em](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) dispositivos do usuário antes de implantar o Acesso Condicional ou políticas de MFA. No mínimo, o aplicativo deve ser instalado quando os usuários são solicitados a registrar seus dispositivos no Azure AD adicionando uma conta de trabalho ou de estudante, ou quando eles instalam o aplicativo de portal da empresa do Intune para registrar seus dispositivos no gerenciamento. Isso depende da política de Acesso Condicional configurada.

### <a name="android-devices"></a>Dispositivos Android

Recomendamos que os usuários instalem o aplicativo Portal da Empresa do [Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) e o aplicativo [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes que as políticas de Acesso Condicional sejam implantadas ou quando necessário durante determinadas tentativas de autenticação. Após a instalação do aplicativo, os usuários podem ser solicitados a se registrarem com o Azure AD ou registrar seus dispositivos com o Intune. Isso depende da política de Acesso Condicional configurada.

Também recomendamos que os dispositivos de propriedade da organização sejam padronizados em OEMs e versões que suportam Android for Work ou Samsung Knox para permitir contas de email, serem gerenciados e protegidos pela política MDM do Intune.

### <a name="recommended-email-clients"></a>Clientes de email recomendados

Os clientes de email a seguir suportam autenticação moderna e Acesso Condicional.

|Plataforma|Cliente|Versão/Notas|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Habilitar a autenticação moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) <p> [Atualizações necessárias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Mais recente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Mais recente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 e 2016|
|**Linux**|Sem suporte||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas ao proteger documentos

Os clientes a seguir são recomendados quando uma política de documentos seguros é aplicada.

|Plataforma|Word/Excel/PowerPoint|OneNote|Aplicativo OneDrive|Aplicativo do SharePoint|[Cliente de sincronização do OneDrive](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|Com suporte|Com suporte|Não disponível|Não disponível|Com suporte|
|Windows 10|Com suporte|Com suporte|Não disponível|Não disponível|Com suporte|
|Android|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|iOS|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|macOS|Com suporte|Com suporte|Não disponível|Não disponível|Sem suporte|
|Linux|Sem suporte|Sem suporte|Sem suporte|Sem suporte|Sem suporte|
|

### <a name="microsoft-365-client-support"></a>Suporte ao aplicativo cliente do Microsoft 365

Para obter mais informações sobre o suporte ao cliente no Microsoft 365, consulte os seguintes artigos:

- [Suporte ao aplicativo cliente do Microsoft 365 - Acesso Condicional](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Suporte ao aplicativo cliente do Microsoft 365 - Autenticação moderna](../../enterprise/microsoft-365-client-support-modern-authentication.md)

## <a name="protecting-administrator-accounts"></a>Protegendo contas de administrador

Para o Microsoft 365 E3 ou E5 ou com licenças separadas do Azure AD Premium P1 ou P2, você pode exigir a MFA para contas de administrador com uma política de Acesso Condicional criada manualmente. Consulte [Acesso Condicional: Exigir MFA para administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) para obter os detalhes.

Para edições do Microsoft 365 ou Office 365 que não [](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) suportam Acesso Condicional, você pode habilitar os padrões de segurança para exigir MFA para todas as contas.

Aqui estão algumas recomendações adicionais:

- Use [o Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) para reduzir o número de contas administrativas persistentes.
- [Use o gerenciamento de acesso privilegiado](../../compliance/privileged-access-management-overview.md) para proteger sua organização contra violações que possam usar contas de administrador privilegiadas existentes com acesso permanente a dados confidenciais ou acesso a configurações críticas.
- Crie e use contas separadas atribuídas a funções de administrador do [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) *somente para administração.* Os administradores devem ter sua própria conta de usuário para uso regular não administrativo e usar somente uma conta administrativa quando necessário para concluir uma tarefa associada à sua função ou função de trabalho.
- Siga [as práticas recomendadas](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para proteger contas privilegiadas no Azure AD.

## <a name="next-step"></a>Próxima etapa

[![Etapa 2: Configurar a identidade comum e as políticas de Acesso Condicional](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Configurar as políticas comuns de identidade e acesso ao dispositivo](identity-access-policies.md)
