---
title: Usar o PowerShell para criar relatórios para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: 'Resumo: use o PowerShell para Microsoft 365 para criar relatórios que você não pode produzir no Microsoft 365 de administração.'
ms.openlocfilehash: 9e3b90dcdd32f80125175ad2e15a852db51e17f8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572736"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="83a20-103">Usar o PowerShell para criar relatórios para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="83a20-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="83a20-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="83a20-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="83a20-105">Muitos relatórios diferentes estão disponíveis no Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="83a20-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="83a20-106">Mas esses relatórios só fornecem muitas informações e, às vezes, você precisa de mais.</span><span class="sxs-lookup"><span data-stu-id="83a20-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="83a20-107">É quando você precisa do PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83a20-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="83a20-108">Estes artigos descrevem como usar o PowerShell para Microsoft 365 obter informações do seu locatário Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="83a20-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="83a20-109">Começar a relatar usando o PowerShell para Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="83a20-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="83a20-110">Por que você precisa usar o PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="83a20-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="83a20-111">Relatórios de contas de usuário e licenças:</span><span class="sxs-lookup"><span data-stu-id="83a20-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="83a20-112">Exibir Microsoft 365 licenças e serviços com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="83a20-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="83a20-113">Exibir Microsoft 365 usuários licenciados e não licenciados com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="83a20-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="83a20-114">Exibir Microsoft 365 de licença de conta e detalhes de serviço com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="83a20-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="83a20-115">Exibir Microsoft 365 contas de usuário com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="83a20-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="83a20-116">Relatórios do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="83a20-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="83a20-117">Introdução ao Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="83a20-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="83a20-118">Get-SPOSiteGroup - Obtém todos os grupos em um conjunto de sites especificado</span><span class="sxs-lookup"><span data-stu-id="83a20-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="83a20-119">Relatórios do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="83a20-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="83a20-120">Usar Exchange Online PowerShell para exibir caixa de correio</span><span class="sxs-lookup"><span data-stu-id="83a20-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articles"></a><span data-ttu-id="83a20-121">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="83a20-121">Related articles</span></span>

[<span data-ttu-id="83a20-122">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="83a20-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="83a20-123">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="83a20-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="83a20-124">Gerenciar SharePoint com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="83a20-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="83a20-125">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="83a20-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
