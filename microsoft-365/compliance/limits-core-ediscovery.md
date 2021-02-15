---
title: Limites no caso principal de Descoberta eDiscovery
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
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799658"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="083d2-103">Limites na Descoberta eDiscovery Principal</span><span class="sxs-lookup"><span data-stu-id="083d2-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="083d2-104">A tabela a seguir lista os limites para os principais casos de Descoberta e retém associados a um caso de Descoberta eDiscovery principal.</span><span class="sxs-lookup"><span data-stu-id="083d2-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="083d2-105">Para obter mais informações sobre a Descoberta Principal, consulte [Visão Geral da Descoberta Principal do eDiscovery.](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="083d2-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="083d2-106">Descrição do limite</span><span class="sxs-lookup"><span data-stu-id="083d2-106">Description of limit</span></span> | <span data-ttu-id="083d2-107">Limite</span><span class="sxs-lookup"><span data-stu-id="083d2-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="083d2-108">Número máximo de casos para uma organização</span><span class="sxs-lookup"><span data-stu-id="083d2-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="083d2-109">Sem limite</span><span class="sxs-lookup"><span data-stu-id="083d2-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="083d2-110">Número máximo de retém de caso para uma organização</span><span class="sxs-lookup"><span data-stu-id="083d2-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="083d2-111">10.000</span><span class="sxs-lookup"><span data-stu-id="083d2-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="083d2-112">Número máximo de caixas de correio em um único caso de espera</span><span class="sxs-lookup"><span data-stu-id="083d2-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="083d2-113">1.000</span><span class="sxs-lookup"><span data-stu-id="083d2-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="083d2-114">Número máximo de sites do SharePoint e do OneDrive for Business em um único caso de espera</span><span class="sxs-lookup"><span data-stu-id="083d2-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="083d2-115">100</span><span class="sxs-lookup"><span data-stu-id="083d2-115">100</span></span>  <br/> |
  |<span data-ttu-id="083d2-116">Número máximo de casos exibidos na home page principal da Descoberta e o número máximo de itens exibidos nas guias Regiões, Pesquisas e Exportação em uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="083d2-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="083d2-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="083d2-117"><sup>1</sup></span></span> |<span data-ttu-id="083d2-118">1.000</span><span class="sxs-lookup"><span data-stu-id="083d2-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="083d2-119"><sup>1</sup> Para exibir uma lista de mais de 1.000 casos, regiões, pesquisas ou exportações, você pode usar os cmdlets correspondentes do PowerShell de Conformidade e Segurança do Office 36 & 5:</span><span class="sxs-lookup"><span data-stu-id="083d2-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="083d2-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="083d2-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="083d2-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="083d2-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="083d2-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="083d2-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="083d2-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="083d2-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="083d2-124">Para obter mais informações sobre limites relacionados a pesquisas de conteúdo e exportações associadas a um caso de Descoberta eDiscovery Principal, consulte Limites para Pesquisa de Conteúdo e Descobertas Principais [de eDiscovery](limits-for-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="083d2-124">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>