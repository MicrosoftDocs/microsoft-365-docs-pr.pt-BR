---
title: Limites no caso de descoberta eletrônica principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 4d91b81caee31e693ce29c6d8d629d563d973ae7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551359"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="20a07-103">Limites na descoberta eletrônica principal</span><span class="sxs-lookup"><span data-stu-id="20a07-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="20a07-104">A tabela a seguir lista os limites para os principais casos de descoberta eletrônica e suspensões associados a uma ocorrência de descoberta eletrônica principal.</span><span class="sxs-lookup"><span data-stu-id="20a07-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="20a07-105">Para obter mais informações sobre a descoberta eletrônica principal, consulte [Overview of Core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="20a07-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="20a07-106">**Descrição do limite**</span><span class="sxs-lookup"><span data-stu-id="20a07-106">**Description of limit**</span></span>|<span data-ttu-id="20a07-107">**Limite**</span><span class="sxs-lookup"><span data-stu-id="20a07-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="20a07-108">Número máximo de casos para uma organização</span><span class="sxs-lookup"><span data-stu-id="20a07-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="20a07-109">Sem limite</span><span class="sxs-lookup"><span data-stu-id="20a07-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="20a07-110">Número máximo de isenções de caso para uma organização</span><span class="sxs-lookup"><span data-stu-id="20a07-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="20a07-111">10.000</span><span class="sxs-lookup"><span data-stu-id="20a07-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="20a07-112">Número máximo de caixas de correio em uma única retenção de caso</span><span class="sxs-lookup"><span data-stu-id="20a07-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="20a07-113">1.000</span><span class="sxs-lookup"><span data-stu-id="20a07-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="20a07-114">Número máximo de sites do SharePoint e do OneDrive for Business em uma única retenção de caso</span><span class="sxs-lookup"><span data-stu-id="20a07-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="20a07-115">100</span><span class="sxs-lookup"><span data-stu-id="20a07-115">100</span></span>  <br/> |
  |<span data-ttu-id="20a07-116">Número máximo de casos exibidos na Home Page principal da descoberta eletrônica e o número máximo de itens exibidos nas guias isenções, pesquisas e exportação em um caso.</span><span class="sxs-lookup"><span data-stu-id="20a07-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="20a07-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="20a07-117"><sup>1</sup></span></span> |<span data-ttu-id="20a07-118">1.000</span><span class="sxs-lookup"><span data-stu-id="20a07-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="20a07-119"><sup>1</sup> para exibir uma lista de mais de 1.000 casos, isenções, pesquisas ou exportações, você pode usar o cmdlet do PowerShell de segurança & conformidade do Office 365 correspondente:</span><span class="sxs-lookup"><span data-stu-id="20a07-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="20a07-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="20a07-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [<span data-ttu-id="20a07-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="20a07-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [<span data-ttu-id="20a07-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="20a07-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [<span data-ttu-id="20a07-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="20a07-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)
