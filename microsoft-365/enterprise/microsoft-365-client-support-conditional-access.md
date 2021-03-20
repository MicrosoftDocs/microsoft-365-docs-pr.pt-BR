---
title: 'Suporte ao aplicativo cliente do Microsoft 365: Acesso Condicional'
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
description: Neste artigo, saiba quais plataformas, clientes e módulos do PowerShell suportam o Acesso Condicional para o Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904955"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="e3cdd-103">Suporte ao aplicativo cliente do Microsoft 365: Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="e3cdd-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="e3cdd-104">No local de trabalho moderno, os usuários podem acessar os recursos da sua organização usando vários dispositivos e aplicativos de qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="e3cdd-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="e3cdd-105">Como resultado, apenas o foco em quem pode acessar um recurso não é mais suficiente.</span><span class="sxs-lookup"><span data-stu-id="e3cdd-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="e3cdd-106">Sua organização também deve dar suporte a como e onde um recurso é acessado em sua infraestrutura de controle de acesso.</span><span class="sxs-lookup"><span data-stu-id="e3cdd-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="e3cdd-107">Com o Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span><span class="sxs-lookup"><span data-stu-id="e3cdd-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="e3cdd-108">O Acesso Condicional é um recurso do Azure Active Directory que permite impor controles sobre o acesso a aplicativos em seu ambiente, tudo com base em condições específicas e gerenciados de um local central.</span><span class="sxs-lookup"><span data-stu-id="e3cdd-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="e3cdd-109">Saiba mais sobre o Acesso Condicional [do Azure Active Directory](/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="e3cdd-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="e3cdd-110">Clientes com suporte & plataformas</span><span class="sxs-lookup"><span data-stu-id="e3cdd-110">Supported clients & platforms</span></span>

<span data-ttu-id="e3cdd-111">As versões mais recentes dos seguintes clientes e plataformas suportam o acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="e3cdd-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="e3cdd-112">Para obter mais informações sobre o suporte à plataforma no Microsoft 365, consulte [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span><span class="sxs-lookup"><span data-stu-id="e3cdd-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="e3cdd-113">Módulos do PowerShell com suporte</span><span class="sxs-lookup"><span data-stu-id="e3cdd-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="e3cdd-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3cdd-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="e3cdd-115">PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e3cdd-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="e3cdd-116">PowerShell do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e3cdd-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
