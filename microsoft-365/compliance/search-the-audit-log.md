---
title: Pesquisar o log de auditoria para a atividade do usuário e do administrador
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 'O log de auditoria é um log de auditoria unificado. Por que usar um log de auditoria unificada? Porque os eventos da maioria dos serviços que sua organização assina são registrados em um único log de auditoria que você pode pesquisar. Isso significa que você pode pesquisar o usuário e a atividade de administrador nesses serviços:'
ms.openlocfilehash: 95f5025e4831223c93251c7c22d1f43d44086d48
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625091"
---
# <a name="search-the-audit-log-for-user-and-admin-activity"></a><span data-ttu-id="be79d-106">Pesquisar o log de auditoria para a atividade do usuário e do administrador</span><span class="sxs-lookup"><span data-stu-id="be79d-106">Search the audit log for user and admin activity</span></span>

<span data-ttu-id="be79d-107">O log de auditoria é um log de auditoria unificado.</span><span class="sxs-lookup"><span data-stu-id="be79d-107">The audit log is a unified audit log.</span></span> <span data-ttu-id="be79d-108">Por que usar um log de auditoria unificada?</span><span class="sxs-lookup"><span data-stu-id="be79d-108">Why a unified audit log?</span></span> <span data-ttu-id="be79d-109">Como os eventos da maioria dos serviços que você está assinando são registrados em um único log de auditoria que você pode pesquisar.</span><span class="sxs-lookup"><span data-stu-id="be79d-109">Because events from most services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="be79d-110">Isso significa que você pode pesquisar o usuário e a atividade de administrador nesses serviços:</span><span class="sxs-lookup"><span data-stu-id="be79d-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="be79d-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="be79d-111">SharePoint</span></span>
- <span data-ttu-id="be79d-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="be79d-112">OneDrive</span></span>
- <span data-ttu-id="be79d-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="be79d-113">Exchange</span></span>
- <span data-ttu-id="be79d-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="be79d-114">Azure Active Directory</span></span>
- <span data-ttu-id="be79d-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be79d-115">Microsoft Teams</span></span>
- <span data-ttu-id="be79d-116">Descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="be79d-116">eDiscovery</span></span>
- <span data-ttu-id="be79d-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="be79d-117">Power BI</span></span>
- <span data-ttu-id="be79d-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="be79d-118">Yammer</span></span>
- <span data-ttu-id="be79d-119">Sway</span><span class="sxs-lookup"><span data-stu-id="be79d-119">Sway</span></span>
- <span data-ttu-id="be79d-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="be79d-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="be79d-121">Configurar a auditoria</span><span class="sxs-lookup"><span data-stu-id="be79d-121">Set up auditing</span></span>
  
<span data-ttu-id="be79d-122">Há algumas coisas que você precisa fazer antes de Pesquisar o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="be79d-122">There's few things you have to do before you can search the audit log.</span></span>
  
- <span data-ttu-id="be79d-123">[Ativar a pesquisa de log de auditoria](turn-audit-log-search-on-or-off.md) para iniciar a gravação de eventos que podem ser pesquisados</span><span class="sxs-lookup"><span data-stu-id="be79d-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="be79d-124">[Habilitar a auditoria de caixa de correio](enable-mailbox-auditing.md) para que você possa procurar eventos relacionados à caixa de correio; como quando um usuário entra na caixa de correio ou exclui itens da pasta itens recuperáveis</span><span class="sxs-lookup"><span data-stu-id="be79d-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="be79d-125">Pesquisar o log de auditoria</span><span class="sxs-lookup"><span data-stu-id="be79d-125">Search the audit log</span></span>
  
<span data-ttu-id="be79d-126">Depois de ativar a auditoria, você pesquisa centenas de tipos individuais de eventos de vários serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="be79d-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Microsoft 365 services.</span></span>
  
- <span data-ttu-id="be79d-127">[Pesquisar o log de auditoria](search-the-audit-log-in-security-and-compliance.md) para atividades de usuário e de administrador</span><span class="sxs-lookup"><span data-stu-id="be79d-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="be79d-128">[Entender as propriedades detalhadas](detailed-properties-in-the-office-365-audit-log.md) em cada registro de auditoria incluído nos resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="be79d-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="be79d-129">[Pesquisa de atividades relacionadas à descoberta eletrônica](search-for-ediscovery-activities-in-the-audit-log.md) realizadas por administradores e gerentes de conformidade</span><span class="sxs-lookup"><span data-stu-id="be79d-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
