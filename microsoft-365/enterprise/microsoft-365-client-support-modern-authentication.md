---
title: Suporte ao aplicativo cliente Microsoft 365 — autenticação moderna
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
description: Neste artigo, saiba quais plataformas, clientes e módulos do PowerShell suportam a autenticação moderna para o Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eee0e9009f7e6a74f25ebf0315b2772ac3e98814
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384814"
---
# <a name="microsoft-365-client-app-support---modern-authentication"></a>Suporte ao aplicativo cliente Microsoft 365-autenticação moderna

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

A autenticação moderna permite o logon baseado na biblioteca de autenticação do Active Directory (ADAL) para aplicativos clientes do Office em diferentes plataformas. Isso permite que os recursos de entrada, como a autenticação multifator (MFA), o cartão inteligente e a autenticação baseada em certificado.

Saiba mais sobre [autenticação multifator](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) e [autenticação baseada em certificado](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started).

## <a name="supported-platforms"></a>Plataformas compatíveis

 - Área de trabalho do Windows 10
 - Aplicativos modernos do Windows 10
 - Navegadores da Web<sup>1</sup>
 - Android<sup>2</sup>
 - iOS
 - macOS

Para obter mais informações sobre o suporte à plataforma no Microsoft 365, consulte [System Requirements for Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

## <a name="supported-clients"></a>Clientes com suporte

As versões mais recentes dos seguintes clientes suportam a autenticação moderna:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Ícone do Access](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Ícone do Azure](../media/o365-azure-64x64.png) <br> [Portal do Azure <br>](https://azure.microsoft.com/features/azure-portal/) | ![Ícone do portal da empresa](../media/o365-microsoft-64x64.png) <br> [Portal da empresa <br>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Ícone do Delve](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Ícone do Dynamics 365](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) 
| ![Ícone de borda](../media/o365-edge-64x64.png) <br> [Borda](https://www.microsoft.com/windows/microsoft-edge) | ![Ícone do Excel](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Ícone do Forms](../media/o365-forms-64x64.png) <br> [Forms](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) | ![Ícone do Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Ícone de Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) 
| ![Ícone de administração do Office 365](../media/o365-o365admin-64x64.png) <br> [Administrador 365 da Microsoft <br>](https://products.office.com/business/manage-office-365-admin-app) | ![Ícone de lente](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Ícone do OneDrive for Business](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) |  ![Ícone do OneNote](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Ícone do Outlook](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) 
| ![Ícone do Planner](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Ícone do PowerApps](../media/o365-powerapps-64x64.png) <br> [PowerApps ](https://powerapps.microsoft.com) | ![Ícone de automatização de energia](../media/o365-flow-64x64.png) <br> [<br>Automatização de energia](https://flow.microsoft.com) | ![Ícone do PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com)| ![Ícone do PowerPoint](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Ícone do Project](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Ícone do Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![Ícone do SharePoint](../media/o365-sharepoint-64x64.png) <br> [Do](https://products.office.com/sharepoint) | ![Ícone do Skype for Business](../media/o365-skypeforbusiness-64x64.png) <br> [Skype for <br> Business<sup>1</sup>](https://www.skype.com/business/) | ![Ícone do StaffHub](../media/o365-staffhub-64x64.png) <br> [StaffHub](https://products.office.com/microsoft-staffhub/staff-scheduling-software)
| ![Ícone de notas auto-adesivas](../media/o365-stickynotes-64x64.png) <br> [Notas auto-adesivas](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Ícone do Stream](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Ícone do Sway](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Ícone do Teams](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) | ![Ícone de tarefas pendentes](../media/o365-todo-64x64.png) <br> [To Do](https://todo.microsoft.com) 
| ![Ícone do Visio](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Ícone do quadro de comunicações](../media/o365-whiteboard-64x64.png) <br> [Quadro de comunicações<sup>1</sup>,<sup>2</sup>](https://whiteboard.microsoft.com/) | ![Ícone do Word](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Ícone do Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview) | ![Ícone do Yammer](../media/o365-yammer-64x64.png) <br> [<br>Notificador do Yammer](https://products.office.com/yammer/yammer-overview) |  |

## <a name="supported-powershell-modules"></a>Módulos do PowerShell suportados

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Ícone do Azure](../media/o365-azure-64x64.png) <br> [PowerShell do Azure AD <br>](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Ícone do Exchange](../media/o365-exchange-64x64.png) <br> [PowerShell do Exchange Online <br>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![Ícone do SharePoint](../media/o365-sharepoint-64x64.png) <br> [PowerShell do SharePoint Online <br>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> suporte para whiteboard e Skype for Business no aplicativo Web disponível em breve. <br>
> <sup>2</sup> o suporte para o whiteboard no Android estará disponível em breve.

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
