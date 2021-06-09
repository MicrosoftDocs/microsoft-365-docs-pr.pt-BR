---
title: 'Microsoft 365 Suporte ao aplicativo cliente: Autenticação baseada em certificado'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Neste artigo, encontre detalhes sobre o Microsoft 365 de aplicativo cliente para autenticação baseada em certificado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5ebef7c10aa61ba28c8fb841468be244f6e8542
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904980"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 Suporte ao aplicativo cliente: Autenticação baseada em certificado

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Autenticação moderna é um termo de guarda-chuva para uma combinação de métodos de autenticação e autorização. São elas:

- **Métodos de autenticação**: Autenticação multifato; Autenticação baseada em certificado do cliente.
- **Métodos de autorização**: Implementação da Microsoft de Autorização Aberta (OAuth).

A autenticação moderna é habilitada usando uma biblioteca de autenticação, como a Biblioteca de Autenticação do Active Directory (ADAL) ou a Biblioteca de Autenticação da Microsoft (MSAL). Autenticação moderna é o que os clientes usam para autenticar e autorizar o acesso Microsoft 365 recursos. A autenticação moderna usa o OAuth e fornece um mecanismo seguro para os clientes acessarem Microsoft 365 serviços, sem exigir acesso às credenciais do usuário. Ao entrar, o usuário autentica diretamente com Azure Active Directory e recebe um par de tokens de acesso/atualização em retorno. O token de acesso concede ao cliente acesso aos recursos apropriados no Microsoft 365 locatário. Um token de atualização é usado para obter um novo par de tokens de acesso ou atualização quando o token de acesso atual expira.

A autenticação moderna oferece suporte a diferentes mecanismos de autenticação, como autenticação baseada em certificado. Os clientes em Windows, Android ou iOS podem usar a autenticação baseada em certificado (CBA) para autenticar Azure Active Directory usando um certificado de cliente no dispositivo. Em vez de um nome de usuário/senha típico, o certificado é usado para obter um par de tokens de acesso/atualização de Azure Active Directory.

Saiba mais sobre [autenticação baseada em certificado.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Clientes com suporte & plataformas

As versões mais recentes dos seguintes clientes e plataformas suportam autenticação baseada em certificado ao entrar em Azure Active Directory contas dentro do cliente (por exemplo, ao adicionar uma conta ao aplicativo). Para obter mais informações sobre o suporte à plataforma Microsoft 365, consulte [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

>[!NOTE]
>A borda para iOS e Android oferece suporte à autenticação baseada em certificado durante fluxos de adoção de conta. A borda para iOS e Android não dá suporte à autenticação baseada em certificado ao executar a autenticação em sites, que normalmente são sites de intranet. <br><br>  Nesse cenário, um usuário navega até um site (geralmente na intranet) onde o site exige que o usuário se autenture por meio de um certificado. Isso não envolve autenticação moderna e não aproveita uma biblioteca de autenticação da Microsoft. Isso ocorre devido a uma limitação com o iOS: o iOS impede que aplicativos de terceiros acessem o chaveiro do sistema onde os certificados estão armazenados (somente aplicativos da Apple e o controlador [webview safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) podem acessar o chaveiro do sistema). <br><br> Como o Edge depende da estrutura [webKit](https://developer.apple.com/documentation/webkit) para renderizar sites, o Edge não consegue acessar o chaveiro do sistema e apresentar ao usuário uma opção de certificado. Isso, infelizmente, é devido ao design devido à arquitetura da Apple.

## <a name="supported-powershell-modules"></a>Módulos do PowerShell com suporte

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [PowerShell do Exchange Online](/powershell/exchange/exchange-online-powershell)
- [PowerShell do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

