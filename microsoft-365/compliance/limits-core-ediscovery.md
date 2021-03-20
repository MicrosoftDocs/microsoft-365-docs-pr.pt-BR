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
description: Este artigo descreve os limites no caso principal de Descoberta eDiscovery no Microsoft 365.
ms.openlocfilehash: e18e1e6c1d9d7ecd78deaf267be72ccdc9d1ba5d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905883"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="0e893-103">Limites na Descoberta Principal da Descoberta</span><span class="sxs-lookup"><span data-stu-id="0e893-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="0e893-104">A tabela a seguir lista os limites para os principais casos de Descoberta e Retém associados a um caso de Descoberta eDiscovery principal.</span><span class="sxs-lookup"><span data-stu-id="0e893-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="0e893-105">Para obter mais informações sobre a Descoberta Básica, consulte [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="0e893-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="0e893-106">Descrição do limite</span><span class="sxs-lookup"><span data-stu-id="0e893-106">Description of limit</span></span> | <span data-ttu-id="0e893-107">Limite</span><span class="sxs-lookup"><span data-stu-id="0e893-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="0e893-108">Número máximo de casos para uma organização.</span><span class="sxs-lookup"><span data-stu-id="0e893-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="0e893-109">Sem limite</span><span class="sxs-lookup"><span data-stu-id="0e893-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="0e893-110">Número máximo de casos retém para uma organização.</span><span class="sxs-lookup"><span data-stu-id="0e893-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="0e893-111">10.000</span><span class="sxs-lookup"><span data-stu-id="0e893-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="0e893-112">Número máximo de caixas de correio em uma única caixa de espera.</span><span class="sxs-lookup"><span data-stu-id="0e893-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="0e893-113">Esse limite inclui o total combinado de caixas de correio de usuário e as caixas de correio associadas aos Grupos do Microsoft 365, Microsoft Teams e Grupos do Yammer.</span><span class="sxs-lookup"><span data-stu-id="0e893-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="0e893-114">1.000</span><span class="sxs-lookup"><span data-stu-id="0e893-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="0e893-115">Número máximo de sites em uma única espera de caso.</span><span class="sxs-lookup"><span data-stu-id="0e893-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="0e893-116">Esse limite inclui o total combinado de sites do OneDrive for Business, sites do SharePoint e os sites associados aos Grupos do Microsoft 365, Microsoft Teams e Grupos do Yammer.</span><span class="sxs-lookup"><span data-stu-id="0e893-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="0e893-117">100</span><span class="sxs-lookup"><span data-stu-id="0e893-117">100</span></span>  <br/> |
  |<span data-ttu-id="0e893-118">Número máximo de casos exibidos na home page principal da Descoberta Online e o número máximo de itens exibidos nas guias Regiões, Pesquisas e Exportação dentro de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="0e893-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="0e893-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0e893-119"><sup>1</sup></span></span> |<span data-ttu-id="0e893-120">1.000</span><span class="sxs-lookup"><span data-stu-id="0e893-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="0e893-121"><sup>1</sup> Para exibir uma lista de mais de 1.000 casos, regiões, pesquisas ou exportações, você pode usar os cmdlets correspondentes do Office 365 Security & Compliance PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0e893-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="0e893-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="0e893-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="0e893-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="0e893-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="0e893-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="0e893-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="0e893-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="0e893-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="0e893-126">Para obter mais informações sobre limites relacionados a pesquisas de conteúdo e exportações associadas a um caso de Descoberta Principal de Descoberta e Descoberta, consulte [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="0e893-126">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>