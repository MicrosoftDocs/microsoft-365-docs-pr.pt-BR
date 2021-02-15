---
title: 'Suporte ao aplicativo cliente microsoft 365: autenticação baseada em certificado'
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
description: Neste artigo, encontre detalhes sobre o suporte do aplicativo cliente Microsoft 365 para autenticação baseada em certificado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7ab5e4a2575796e37a115b36a4f78add20414ef
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097253"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Suporte ao aplicativo cliente microsoft 365: autenticação baseada em certificado

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

A autenticação moderna é um termo-guarda para uma combinação de métodos de autenticação e autorização. Entre eles:

- **Métodos de autenticação:** Autenticação multifa factor; Autenticação baseada em certificado de cliente.
- **Métodos de autorização:** implementação da Autorização Aberta (OAuth) pela Microsoft.

A autenticação moderna é habilitada por meio de uma biblioteca de autenticação, como a ADAL (Biblioteca de Autenticação do Active Directory) ou a Biblioteca de Autenticação da Microsoft (MSAL). Autenticação moderna é o que os clientes usam para autenticar e autorizar o acesso aos recursos do Microsoft 365. A autenticação moderna aproveita o OAuth e fornece um mecanismo seguro para que os clientes acessem os serviços do Microsoft 365, sem a necessidade de acesso às credenciais do usuário. Na entrada, o usuário autentica diretamente no Azure Active Directory e recebe um par de token de acesso/atualização em troca. O token de acesso concede ao cliente acesso aos recursos apropriados no locatário do Microsoft 365. Um token de atualização é usado para obter um novo par de tokens de acesso ou atualização quando o token de acesso atual expira.

A autenticação moderna dá suporte a diferentes mecanismos de autenticação, como autenticação baseada em certificado. Os clientes em dispositivos Windows, Android ou iOS podem usar a autenticação baseada em certificado (CBA) para autenticar no Azure Active Directory usando um certificado de cliente no dispositivo. Em vez de um nome de usuário/senha típico, o certificado é usado para obter um par de token de acesso/atualização do Azure Active Directory.

Saiba mais sobre [a autenticação baseada em certificado.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Clientes com suporte & plataformas

As versões mais recentes dos seguintes clientes e plataformas suportam autenticação baseada em certificado ao entrar em contas do Azure Active Directory dentro do cliente (por exemplo, ao adicionar uma conta ao aplicativo). Para saber mais sobre o suporte à plataforma no Microsoft 365, confira [Os requisitos do sistema para o Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

| Clientes | Android | iOS | Mac| Windows 10 <br> Aplicativos modernos| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Administrador do Azure Active Directory | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Acessar | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Administrador do Azure | N/D | N/D | N/D | N/D | N/D |
| Portal da empresa | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D |
| Cortana | Planejado | Planejado | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Delve | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Borda<sup>1</sup> | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Excel | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Administrador do Exchange Online | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Forms | N/D | N/D | N/D | N/D | N/D |
| Administração do Office 365 | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |  |
| Kaizala | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Office Lens| ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Office Mobile | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Portal do Office | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| OneDrive | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Planejado | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| OneNote | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Outlook | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Planner | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Power Apps | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Power Automate | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| PowerPoint | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Skype for Business | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) |
| Administrador do Skype for Business | N/D | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| SharePoint | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Administrador do SharePoint Online | Planejado | Planejado | N/D | N/D | N/D |
| Observações Desaderentadas | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Stream | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Teams | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | Planejado |
| To Do | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D |
| Visio | N/D | ![Com suporte](../media/check-mark.png) | N/D | N/D | ![Com suporte](../media/check-mark.png) |
| Whiteboard | Planejado | Planejado | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Word | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Análise do local de trabalho | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Planejado | N/D | Planejado |

>[!NOTE]
><sup>1 Edge</sup> para iOS e Android oferece suporte à autenticação baseada em certificado durante a adoção de fluxos de adoção da conta. O Edge para iOS e Android não dá suporte à autenticação baseada em certificado ao executar a autenticação em sites, que normalmente são sites da intranet. <br><br>  Nesse cenário, um usuário navega até um site (geralmente na intranet) em que o site exige que o usuário autentgue por meio de um certificado. Isso não envolve autenticação moderna e não utiliza uma biblioteca de autenticação da Microsoft. Isso ocorre devido a uma limitação com o iOS: o iOS impede que aplicativos de terceiros acessem o keychain do sistema onde os certificados estão armazenados (somente os aplicativos Apple e o controlador [de webview safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) podem acessar o keychain do sistema). <br><br> Como o Edge depende da estrutura [do WebKit](https://developer.apple.com/documentation/webkit) para renderizar sites, o Edge não consegue acessar o keychain do sistema e apresentar ao usuário uma escolha de certificado. Infelizmente, isso ocorre devido ao design devido à arquitetura da Apple.

## <a name="supported-powershell-modules"></a>Módulos do PowerShell com suporte

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [PowerShell do Exchange Online](/powershell/exchange/exchange-online-powershell)
- [PowerShell do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

