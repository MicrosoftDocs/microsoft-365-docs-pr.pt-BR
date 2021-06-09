---
title: Detecção quase duplicada - Descoberta Automática
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use a detecção quase duplicada para agrupar documentos textuamente semelhantes ao analisar dados de caso em Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286017"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="4f3cb-103">Detecção quase duplicada no Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4f3cb-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="4f3cb-104">Considere um conjunto de documentos a serem revisados no qual um subconjunto se baseia no mesmo modelo e tem principalmente o mesmo idioma clichê, com algumas diferenças aqui e ali.</span><span class="sxs-lookup"><span data-stu-id="4f3cb-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="4f3cb-105">Se um revistor pudesse identificar esse subconjunto, revisar um deles completamente e revisar as diferenças para o restante, ele não teria perdido nenhuma informação exclusiva enquanto levaria apenas uma fração de tempo que os levaria a ler todos os documentos de capa a capa.</span><span class="sxs-lookup"><span data-stu-id="4f3cb-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="4f3cb-106">Detecção de duplicata próxima agrupa documentos textualmente similares para deixar seu processo de avaliação mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="4f3cb-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="4f3cb-107">Como funciona?</span><span class="sxs-lookup"><span data-stu-id="4f3cb-107">How does it work?</span></span>

<span data-ttu-id="4f3cb-108">Quando a detecção de duplicatas próximas é executada, o sistema analisa cada documento com texto.</span><span class="sxs-lookup"><span data-stu-id="4f3cb-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="4f3cb-109">Depois, ela compara os documento entre si para determinar se suas semelhanças são maiores que o limite definido. </span><span class="sxs-lookup"><span data-stu-id="4f3cb-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="4f3cb-110">Se forem maiores, os documentos são agrupados.</span><span class="sxs-lookup"><span data-stu-id="4f3cb-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="4f3cb-111">Depois de todos os documentos serem comparados e agrupados, um documento de cada grupo é marcado como o “original”. Ao analisar seus documentos, você pode analisar primeiro o original e analisar os outros documentos no mesmo conjunto de duplicatas próximas, focando na diferença entre o original e o documento que está sendo analisado.</span><span class="sxs-lookup"><span data-stu-id="4f3cb-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
