---
title: Limites no caso de descoberta eletrônica principal
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
description: Este artigo descreve os limites no caso de descoberta eletrônica principal no Microsoft 365.
ms.openlocfilehash: 6224ce5ecb8fc0439e43ab5e1362f8a618194202
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358509"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="71f16-103">Limites na descoberta eletrônica principal</span><span class="sxs-lookup"><span data-stu-id="71f16-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="71f16-104">A tabela a seguir lista os limites para os principais casos de descoberta eletrônica e suspensões associados a uma ocorrência de descoberta eletrônica principal.</span><span class="sxs-lookup"><span data-stu-id="71f16-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="71f16-105">Para obter mais informações sobre a descoberta eletrônica principal, consulte [Overview of Core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="71f16-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="71f16-106">**Descrição do limite**</span><span class="sxs-lookup"><span data-stu-id="71f16-106">**Description of limit**</span></span>|<span data-ttu-id="71f16-107">**Limite**</span><span class="sxs-lookup"><span data-stu-id="71f16-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="71f16-108">Número máximo de casos para uma organização</span><span class="sxs-lookup"><span data-stu-id="71f16-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="71f16-109">Sem limite</span><span class="sxs-lookup"><span data-stu-id="71f16-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="71f16-110">Número máximo de isenções de caso para uma organização</span><span class="sxs-lookup"><span data-stu-id="71f16-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="71f16-111">10.000</span><span class="sxs-lookup"><span data-stu-id="71f16-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="71f16-112">Número máximo de caixas de correio em uma única retenção de caso</span><span class="sxs-lookup"><span data-stu-id="71f16-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="71f16-113">1,000</span><span class="sxs-lookup"><span data-stu-id="71f16-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="71f16-114">Número máximo de sites do SharePoint e do OneDrive for Business em uma única retenção de caso</span><span class="sxs-lookup"><span data-stu-id="71f16-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="71f16-115">100</span><span class="sxs-lookup"><span data-stu-id="71f16-115">100</span></span>  <br/> |
  |<span data-ttu-id="71f16-116">Número máximo de casos exibidos na Home Page principal da descoberta eletrônica e o número máximo de itens exibidos nas guias isenções, pesquisas e exportação em um caso.</span><span class="sxs-lookup"><span data-stu-id="71f16-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="71f16-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="71f16-117"><sup>1</sup></span></span> |<span data-ttu-id="71f16-118">1,000</span><span class="sxs-lookup"><span data-stu-id="71f16-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="71f16-119"><sup>1</sup> para exibir uma lista de mais de 1.000 casos, isenções, pesquisas ou exportações, você pode usar o cmdlet do PowerShell de segurança & conformidade do Office 365 correspondente:</span><span class="sxs-lookup"><span data-stu-id="71f16-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="71f16-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="71f16-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [<span data-ttu-id="71f16-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="71f16-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [<span data-ttu-id="71f16-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="71f16-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [<span data-ttu-id="71f16-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="71f16-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
