---
title: Exibir a atividade de rótulos de documentos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Aprenda a usar o Label Activity Explorer no Centro de conformidade e segurança do Microsoft 365 para pesquisar e exibir a atividade do rótulo.
ms.openlocfilehash: 9cf505575a17c8f6eb4d48e609d358f9c988965f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819021"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="73600-103">Exibir a atividade de rótulos de documentos</span><span class="sxs-lookup"><span data-stu-id="73600-103">View label activity for documents</span></span>

<span data-ttu-id="73600-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span><span class="sxs-lookup"><span data-stu-id="73600-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span></span> <span data-ttu-id="73600-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span><span class="sxs-lookup"><span data-stu-id="73600-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span></span> <span data-ttu-id="73600-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span><span class="sxs-lookup"><span data-stu-id="73600-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="73600-107">Por exemplo, com o Explorador de Atividade do Rótulo, você pode:</span><span class="sxs-lookup"><span data-stu-id="73600-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="73600-108">Exibir o número de vezes que cada rótulo foi aplicado em cada dia (até 30 dias).</span><span class="sxs-lookup"><span data-stu-id="73600-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="73600-109">Ver quem rotulou exatamente o arquivo em qual data, juntamente com um link para o site onde reside esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="73600-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="73600-110">Exiba quais arquivos tiveram os rótulos alterados ou removidos, quais são os rótulos antigos e os novos e quem fez a alteração.</span><span class="sxs-lookup"><span data-stu-id="73600-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="73600-111">Filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="73600-111">Filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="73600-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="73600-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="73600-113">View label activity for folders as well as individual documents.</span><span class="sxs-lookup"><span data-stu-id="73600-113">View label activity for folders as well as individual documents.</span></span> <span data-ttu-id="73600-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span><span class="sxs-lookup"><span data-stu-id="73600-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="73600-115">Você pode encontrar o Explorador de Atividade de Rótulo no Centro de Conformidade &amp;e Segurança > **Governança de informações** > **Explorador de atividade de rótulo**.</span><span class="sxs-lookup"><span data-stu-id="73600-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="73600-116">Observe que no Gerenciador de Atividade de Rótulo exige uma assinatura do Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="73600-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![Explorador de Atividade de Rótulo](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="73600-118">Exibir atividades de rótulo para arquivos ou pastas</span><span class="sxs-lookup"><span data-stu-id="73600-118">View label activities for files or folders</span></span>

<span data-ttu-id="73600-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span><span class="sxs-lookup"><span data-stu-id="73600-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span></span> <span data-ttu-id="73600-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span><span class="sxs-lookup"><span data-stu-id="73600-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="73600-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span><span class="sxs-lookup"><span data-stu-id="73600-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span></span> <span data-ttu-id="73600-122">Therefore, labeling folders might affect a significant number of files.</span><span class="sxs-lookup"><span data-stu-id="73600-122">Therefore, labeling folders might affect a significant number of files.</span></span> <span data-ttu-id="73600-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="73600-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![Menu suspenso mostrando as atividades do rótulo para arquivos e pastas](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="73600-125">Atividades do rótulo</span><span class="sxs-lookup"><span data-stu-id="73600-125">Label activities</span></span>

 <span data-ttu-id="73600-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="73600-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span></span> <span data-ttu-id="73600-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span><span class="sxs-lookup"><span data-stu-id="73600-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="73600-128">Alterações do rótulo</span><span class="sxs-lookup"><span data-stu-id="73600-128">Label changes</span></span>

 <span data-ttu-id="73600-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="73600-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span></span> <span data-ttu-id="73600-130">You can use this view to quickly see such risky actions and the user who performed them.</span><span class="sxs-lookup"><span data-stu-id="73600-130">You can use this view to quickly see such risky actions and the user who performed them.</span></span> <span data-ttu-id="73600-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span><span class="sxs-lookup"><span data-stu-id="73600-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![Painel de detalhes para atividade de rótulos](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="73600-133">Filtrar atividade do rótulo</span><span class="sxs-lookup"><span data-stu-id="73600-133">Filter label activity</span></span>

<span data-ttu-id="73600-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="73600-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="73600-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="73600-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![Filtros para atividade do rótulo](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

