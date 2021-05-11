---
title: Limites no principal caso de Descoberta eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Este artigo descreve os limites no caso principal de Descoberta Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311419"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="3b7b6-103">Limites na Descoberta Principal da Descoberta</span><span class="sxs-lookup"><span data-stu-id="3b7b6-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="3b7b6-104">A tabela a seguir lista os limites para os principais casos de Descoberta e Retém associados a um caso de Descoberta eDiscovery principal.</span><span class="sxs-lookup"><span data-stu-id="3b7b6-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="3b7b6-105">Para obter mais informações sobre a Descoberta Básica, consulte [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="3b7b6-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="3b7b6-106">Descrição do limite</span><span class="sxs-lookup"><span data-stu-id="3b7b6-106">Description of limit</span></span> | <span data-ttu-id="3b7b6-107">Limite</span><span class="sxs-lookup"><span data-stu-id="3b7b6-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="3b7b6-108">Número máximo de casos para uma organização.</span><span class="sxs-lookup"><span data-stu-id="3b7b6-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="3b7b6-109">Sem limite</span><span class="sxs-lookup"><span data-stu-id="3b7b6-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="3b7b6-110">Número máximo de casos retém para uma organização.</span><span class="sxs-lookup"><span data-stu-id="3b7b6-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="3b7b6-111">10.000</span><span class="sxs-lookup"><span data-stu-id="3b7b6-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="3b7b6-112">Número máximo de caixas de correio em uma única caixa de espera.</span><span class="sxs-lookup"><span data-stu-id="3b7b6-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="3b7b6-113">Esse limite inclui o total combinado de caixas de correio de usuário e as caixas de correio associadas Microsoft 365 grupos, Microsoft Teams e Yammer Grupos.</span><span class="sxs-lookup"><span data-stu-id="3b7b6-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="3b7b6-114">1.000</span><span class="sxs-lookup"><span data-stu-id="3b7b6-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="3b7b6-115">Número máximo de sites em uma única espera de caso.</span><span class="sxs-lookup"><span data-stu-id="3b7b6-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="3b7b6-116">Esse limite inclui o total combinado de sites OneDrive for Business, sites SharePoint e os sites associados a grupos Microsoft 365, Microsoft Teams e grupos Yammer.</span><span class="sxs-lookup"><span data-stu-id="3b7b6-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="3b7b6-117">100</span><span class="sxs-lookup"><span data-stu-id="3b7b6-117">100</span></span>  <br/> |
  |<span data-ttu-id="3b7b6-118">Número máximo de casos exibidos na home page principal da Descoberta Online e o número máximo de itens exibidos nas guias Regiões, Pesquisas e Exportação dentro de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="3b7b6-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="3b7b6-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3b7b6-119"><sup>1</sup></span></span> |<span data-ttu-id="3b7b6-120">1.000</span><span class="sxs-lookup"><span data-stu-id="3b7b6-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="3b7b6-121"><sup>1</sup> Para exibir uma lista de mais de 1.000 casos, regiões, pesquisas ou exportações, você pode usar os cmdlets Office 365 Security & Compliance do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3b7b6-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="3b7b6-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="3b7b6-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="3b7b6-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="3b7b6-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="3b7b6-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="3b7b6-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="3b7b6-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="3b7b6-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="3b7b6-126">Para obter mais informações sobre os limites relacionados a pesquisas e exportações associadas a um caso de Descoberta Principal de Descoberta e, em Vez disso, consulte Limites para Pesquisa de Conteúdo e Descoberta [Principal de Descoberta e Descoberta.](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="3b7b6-126">For more information about limits related to searches and exports associated with a Core eDiscovery case, see [Limits for Content search and Core eDiscovery](limits-for-content-search.md).</span></span>