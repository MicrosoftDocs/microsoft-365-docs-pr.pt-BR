---
title: 'Microsoft 365 Suporte ao aplicativo cliente: autenticação multifa factor'
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
description: Neste artigo, saiba quais plataformas, clientes e módulos do PowerShell suportam a autenticação multifafação para Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8749c05e3f7ce5dacf7d3ed1eaa46a46a20482d5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286448"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="1227f-103">Microsoft 365 Suporte ao aplicativo cliente: autenticação multifa factor</span><span class="sxs-lookup"><span data-stu-id="1227f-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="1227f-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1227f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1227f-105">Para fornecer um nível adicional de segurança para entrar, os clientes podem ser configurados para usar a autenticação multifato (MFA), que usa uma senha de usuário e outro método de verificação de usuário com base em:</span><span class="sxs-lookup"><span data-stu-id="1227f-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="1227f-106">Algo em sua posse que não é facilmente duplicado, como um telefone inteligente.</span><span class="sxs-lookup"><span data-stu-id="1227f-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="1227f-107">Algo que o usuário tem de forma exclusiva e biologicamente, como suas impressões digitais, face ou outro atributo biométrico</span><span class="sxs-lookup"><span data-stu-id="1227f-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="1227f-108">Saiba mais sobre [a autenticação multifa factor](/azure/active-directory/authentication/multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="1227f-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="1227f-109">Clientes com suporte & plataformas</span><span class="sxs-lookup"><span data-stu-id="1227f-109">Supported clients & platforms</span></span>

<span data-ttu-id="1227f-110">As versões mais recentes dos seguintes clientes e plataformas suportam a autenticação multifa factor.</span><span class="sxs-lookup"><span data-stu-id="1227f-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="1227f-111">Para obter mais informações sobre o suporte à plataforma Microsoft 365, consulte [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span><span class="sxs-lookup"><span data-stu-id="1227f-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="1227f-112">Módulos do PowerShell com suporte</span><span class="sxs-lookup"><span data-stu-id="1227f-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="1227f-113">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="1227f-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="1227f-114">PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1227f-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="1227f-115">PowerShell do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1227f-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
