---
title: Suporte ao aplicativo cliente Microsoft 365 — acesso condicional
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: Neste artigo, saiba quais plataformas, clientes e módulos do PowerShell suportam acesso condicional para o Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d44dffd6da91be9e64953d1b744043114ba68183
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384928"
---
# <a name="microsoft-365-client-app-support--conditional-access"></a>Suporte ao aplicativo cliente Microsoft 365 — acesso condicional

No local de trabalho moderno, os usuários podem acessar os recursos da sua organização usando vários dispositivos e aplicativos de qualquer lugar. Como resultado, apenas o foco em quem pode acessar um recurso não é mais suficiente. Sua organização também deve suportar como e onde um recurso é acessado em sua infraestrutura de controle de acesso.

Com o dispositivo do Azure Active Directory (Azure AD), o local e o acesso condicional com base na autenticação multifator, você pode atender a esse novo requisito. O Acesso Condicional é um recurso do Azure AD que permite impor controles no acesso a aplicativos em seu ambiente, todos baseados em condições específicas e gerenciados a partir de um local central.

Saiba mais sobre o [Acesso Condicional do Azure AD](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-platforms"></a>Plataformas compatíveis

 - Área de trabalho do Windows 10
 - Aplicativos modernos do Windows 10
 - Navegadores da Web
 - Android
 - iOS
 - macOS<sup>1</sup>

Para obter mais informações sobre o suporte à plataforma no Microsoft 365, consulte [System Requirements for Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

## <a name="supported-clients"></a>Clientes com suporte

As versões mais recentes dos seguintes clientes suportam acesso condicional:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Ícone do Azure](../media/o365-azure-64x64.png) <br> [Portal do Azure AD <br>](https://azure.microsoft.com/features/azure-portal/) | ![Ícone do Access](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Ícone do portal da empresa](../media/o365-microsoft-64x64.png) <br> [Portal da empresa <br>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal)  | ![Ícone da Cortana](../media/o365-cortana-64x64.png) <br> [Consome](https://www.microsoft.com/cortana) | ![Ícone do Delve](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) 
| ![Ícone do Dynamics 365](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) | ![Ícone de borda](../media/o365-edge-64x64.png) <br> [Borda](https://www.microsoft.com/windows/microsoft-edge) | ![Ícone do Exchange](../media/o365-exchange-64x64.png) <br> [Exchange](https://products.office.com/exchange/exchange-online) | ![Ícone do Excel](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Ícone do Forms](../media/o365-forms-64x64.png) <br> [Forms](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) 
| ![Ícone do Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Ícone de Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Ícone de lente](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Ícone de administração do Office 365](../media/o365-o365admin-64x64.png) <br> [Administrador 365 da Microsoft <br>](https://products.office.com/business/manage-office-365-admin-app) | ![Ícone do OneDrive for Business](../media/o365-OneDrive-64x64.png) <br> [OneDrive<sup>1</sup>](https://products.office.com/onedrive-for-business/online-cloud-storage) 
| ![Ícone do OneNote](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Ícone do Outlook](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) | ![Ícone do Planner](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Ícone do PowerApps](../media/o365-powerapps-64x64.png) <br> [PowerApps](https://powerapps.microsoft.com) | ![Ícone de automatização de energia](../media/o365-flow-64x64.png) <br> [<br>Automatização de energia](https://flow.microsoft.com)
| ![Ícone do PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com) | ![Ícone do PowerPoint](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) | ![Ícone do Project](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Ícone do Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![Ícone do SharePoint](../media/o365-sharepoint-64x64.png) <br> [Do](https://products.office.com/sharepoint) 
| ![Ícone do Skype for Business](../media/o365-skypeforbusiness-64x64.png) <br> [Skype for <br> Business](https://www.skype.com/business/) | ![Ícone de notas auto-adesivas](../media/o365-stickynotes-64x64.png) <br> [Notas auto-adesivas](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Ícone do Stream](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Ícone do Sway](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Ícone do Teams](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) 
| ![Ícone de tarefas pendentes](../media/o365-todo-64x64.png) <br> [To Do](https://todo.microsoft.com) | ![Ícone do Visio](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Ícone do Word](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Ícone do Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview)

## <a name="supported-powershell-modules"></a>Módulos do PowerShell suportados

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Ícone do Azure](../media/o365-azure-64x64.png) <br> [PowerShell do Azure AD <br>](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Ícone do Exchange](../media/o365-exchange-64x64.png) <br> [PowerShell do Exchange Online <br>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![Ícone do SharePoint](../media/o365-sharepoint-64x64.png) <br> [PowerShell do SharePoint Online <br>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> suporte para onedrive no MacOS disponível em breve.

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
