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
ms.openlocfilehash: 49ed1e329e83b73441c89de9a142bfb9dcac5395
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806689"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Suporte ao aplicativo cliente Microsoft 365: autenticação baseada em certificado

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

A autenticação baseada em certificado permite que você autentique no Azure Active Directory com um certificado de cliente em dispositivos Windows, Android ou iOS. A configuração desse recurso elimina a necessidade de inserir uma combinação de nome de usuário e senha em determinados emails e aplicativos do Microsoft Office em seu dispositivo móvel.

Saiba mais sobre [a autenticação baseada em certificado](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Plataformas de & de clientes com suporte

As versões mais recentes dos seguintes clientes e plataformas dão suporte à autenticação baseada em certificado. Para obter mais informações sobre o suporte à plataforma no Microsoft 365, consulte [System Requirements for Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Clientes | Android | iOS | Mac| Windows 10 <br> Aplicativos modernos| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Administrador do Azure Active Directory | Não disponível | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) |
| Access | Não disponível | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) |
| Administrador do Azure | Não disponível | Não disponível | Não disponível | Não disponível | Não disponível |
| Portal da empresa | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D |
| Consome | Liga | Liga | Não disponível | ![Com suporte](../media/check-mark.png) | N/D |
| Delve | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Não disponível | Não disponível | Não disponível |
| Borda | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) |
| Excel | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Administração do Exchange Online | Não disponível | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) |
| Formulários | Não disponível | Não disponível | Não disponível | Não disponível | Não disponível |
| Administração do Office 365 | Não disponível | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) |  |
| Kaizala | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Não disponível | Não disponível | Não disponível |
| Office Lens| ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Office Mobile | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Não disponível | Não disponível | Não disponível |
| Portal do Office | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) | N/D |
| OneDrive | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Liga | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| OneNote | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Outlook | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Planner | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Não disponível | Não disponível | Não disponível |
| Aplicativos de energia | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) | N/D |
| Power Automate | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Não disponível | Não disponível | Não disponível |
| Power BI | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| PowerPoint | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Project | Não disponível | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) |
| Publisher | Não disponível | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) |
| Skype for Business | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | ![Com suporte](../media/check-mark.png) |
| Administração do Skype for Business | Não disponível | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) |
| SharePoint | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Não disponível | Não disponível | Não disponível |
| Administração do SharePoint Online | Liga | Liga | Não disponível | Não disponível | Não disponível |
| Notas auto-adesivas | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) | N/D |
| Fluxo | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Não disponível | Não disponível | Não disponível |
| Sway | Não disponível | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) | N/D |
| Teams | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D | Liga |
| To Do | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | N/D |
| Visio | Não disponível | ![Com suporte](../media/check-mark.png) | Não disponível | Não disponível | ![Com suporte](../media/check-mark.png) |
| Quadro de comunicações | Liga | Liga | Não disponível | ![Com suporte](../media/check-mark.png) | N/D |
| Word | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) |
| Análise de local de trabalho | Não disponível | Não disponível | Não disponível | Não disponível | Não disponível |
| Yammer | ![Com suporte](../media/check-mark.png) | ![Com suporte](../media/check-mark.png) | Liga | Não disponível | Liga |

## <a name="supported-powershell-modules"></a>Módulos do PowerShell suportados

- [PowerShell do Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

