---
title: 'Suporte ao aplicativo cliente Microsoft 365: autenticação baseada em certificado'
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
description: Neste artigo, encontre detalhes sobre o suporte do aplicativo cliente do Microsoft 365 para autenticação baseada em certificado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57ced47c268f4d0515acb26aa8f705fa6e9ae0f9
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999379"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Suporte ao aplicativo cliente Microsoft 365: autenticação baseada em certificado

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

A autenticação moderna é um termo abrangente para uma combinação de métodos de autenticação e autorização. Entre eles:

- **Métodos de autenticação** : autenticação multifator; Autenticação baseada em certificado do cliente.
- **Métodos de autorização** : implementação da Microsoft de autorização aberta (OAuth).

A autenticação moderna é habilitada por meio do uso de uma biblioteca de autenticação, como a ADAL (biblioteca de autenticação do Active Directory) ou a biblioteca de autenticação da Microsoft (MSAL). A autenticação moderna é o que os clientes usam para autenticar e autorizar o acesso aos recursos do Microsoft 365. A autenticação moderna aproveita o OAuth e fornece um mecanismo seguro para que os clientes acessem os serviços do Microsoft 365, sem exigir acesso às credenciais do usuário. Ao entrar, o usuário é autenticado diretamente com o Active Directory do Azure e recebe um par de tokens de acesso/atualização em retorno. O token de acesso concede ao cliente acesso aos recursos apropriados no Microsoft 365 locatário. Um token de atualização é usado para obter um novo par de tokens de acesso ou de atualização quando o token de acesso atual expira.

A autenticação moderna oferece suporte a diferentes mecanismos de autenticação, como a autenticação baseada em certificado. Os clientes nos dispositivos Windows, Android ou iOS podem usar a autenticação baseada em certificado (CBA) para autenticar no Azure Active Directory usando um certificado de cliente no dispositivo. Em vez de um nome de usuário/senha típico, o certificado é usado para obter um par de tokens de acesso/atualização do Azure Active Directory.

Saiba mais sobre [a autenticação baseada em certificado](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Plataformas de & de clientes com suporte

As versões mais recentes dos seguintes clientes e plataformas dão suporte à autenticação baseada em certificado ao entrar em contas do Active Directory do Azure no cliente (por exemplo, ao adicionar uma conta ao aplicativo). Para obter mais informações sobre o suporte à plataforma no Microsoft 365, consulte [System Requirements for Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Clientes | Android | iOS | Mac| Windows 10 <br> Aplicativos modernos| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Administrador do Azure Active Directory | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Acesso | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Administrador do Azure | N/D | N/D | N/D | N/D | N/D |
| Portal da empresa | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D |
| Consome | Liga | Liga | N/A | ![Com suporte](../media/check-mark.png) | N/D |
| Delve | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Borda<sup>1</sup> | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Excel | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Administração do Exchange Online | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Forms | N/D | N/D | N/D | N/D | N/D |
| Administração do Office 365 | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |  |
| Kaizala | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Office Lens| ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Office Mobile | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Portal do Office | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| OneDrive | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Liga | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| OneNote | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Outlook | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Planner | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Aplicativos de energia | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Power Automate | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| PowerPoint | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Skype for Business | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) |
| Administração do Skype for Business | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| SharePoint | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Administração do SharePoint Online | Liga | Liga | N/D | N/D | N/D |
| Notas auto-adesivas | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Fluxo | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Teams | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | Liga |
| To Do | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D |
| Visio | N/A | ![Com suporte](../media/check-mark.png) | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Whiteboard | Liga | Liga | N/A | ![Com suporte](../media/check-mark.png) | N/D |
| Word | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Análise de local de trabalho | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Liga | N/A | Liga |

>[!NOTE]
><sup>1</sup> Edge para IOS e Android oferece suporte à autenticação baseada em certificado durante a conta de adição de fluxos. O Edge for iOS e Android não oferece suporte à autenticação baseada em certificado ao realizar autenticação em sites da Web, que normalmente são sites da intranet. <br><br>  Neste cenário, um usuário navega até um site (geralmente na intranet) onde o site exige que o usuário autentique por meio de um certificado. Isso não envolve a autenticação moderna e não utiliza uma biblioteca de autenticação da Microsoft. Isso se deve à limitação do iOS: o iOS impede que aplicativos de terceiros acessem o chaveiro do sistema onde os certificados estão armazenados (somente aplicativos Apple e o [controlador Safari WebView](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) pode acessar o keychain do sistema). <br><br> Como a borda conta com Webkit, a borda não consegue acessar o chaveiro do sistema e apresenta ao usuário a opção de certificado. Isso, infelizmente, é o design devido à arquitetura da Apple.

## <a name="supported-powershell-modules"></a>Módulos do PowerShell suportados

- [PowerShell do Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

