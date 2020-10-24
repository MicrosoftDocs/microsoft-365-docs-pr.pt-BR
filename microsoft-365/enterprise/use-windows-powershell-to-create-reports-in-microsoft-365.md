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
description: 'Resumo: Use o PowerShell para Microsoft 365 para criar relatórios que você não pode produzir no centro de administração do Microsoft 365.'
ms.openlocfilehash: 10000f62b1d6a747cf0373623c6038b080666e1a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753973"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="d6b5b-103">Usar o PowerShell para criar relatórios para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6b5b-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="d6b5b-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d6b5b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d6b5b-105">Muitos relatórios diferentes estão disponíveis no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6b5b-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d6b5b-106">No entanto, esses relatórios fornecem tantas informações e, às vezes, você precisa de mais.</span><span class="sxs-lookup"><span data-stu-id="d6b5b-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="d6b5b-107">É quando você precisa do PowerShell para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6b5b-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="d6b5b-108">Estes artigos descrevem como usar o PowerShell para a Microsoft 365 para obter informações do seu locatário do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="d6b5b-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="d6b5b-109">Introdução aos relatórios usando o PowerShell para o Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="d6b5b-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="d6b5b-110">Por que você precisa usar o PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6b5b-110">Why you need to use PowerShell for Microsoft 365</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
    
- <span data-ttu-id="d6b5b-111">Relatórios de contas de usuário e licenças:</span><span class="sxs-lookup"><span data-stu-id="d6b5b-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="d6b5b-112">Exibir licenças e serviços do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6b5b-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="d6b5b-113">Exibir usuários licenciados e não licenciados da Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6b5b-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="d6b5b-114">Exibir a licença de conta e os detalhes de serviço do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6b5b-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="d6b5b-115">Exibir contas de usuário do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6b5b-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="d6b5b-116">Relatórios do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="d6b5b-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="d6b5b-117">Introdução ao Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d6b5b-117">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="d6b5b-118">Get-SPOSiteGroup-Obtém todos os grupos em um conjunto de sites especificado</span><span class="sxs-lookup"><span data-stu-id="d6b5b-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="d6b5b-119">Relatórios do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="d6b5b-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="d6b5b-120">Usar o Exchange Online PowerShell para exibir a caixa de correio</span><span class="sxs-lookup"><span data-stu-id="d6b5b-120">Use Exchange Online PowerShell to display mailbox</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="d6b5b-121">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d6b5b-121">Related articlesl</span></span>

[<span data-ttu-id="d6b5b-122">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6b5b-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d6b5b-123">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6b5b-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d6b5b-124">Gerenciar o SharePoint com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6b5b-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d6b5b-125">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6b5b-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  