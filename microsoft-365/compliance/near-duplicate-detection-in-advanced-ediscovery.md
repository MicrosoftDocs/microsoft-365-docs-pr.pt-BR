---
title: Detecção duplicada próxima - Descoberta Automática
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
description: Use a detecção quase duplicada para agrupar textually documentos semelhantes ao analisar dados de caso na Descoberta Eletrônica Avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286017"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="06c1a-103">Detecção quase duplicada na Descoberta Automática Avançada</span><span class="sxs-lookup"><span data-stu-id="06c1a-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="06c1a-104">Considere um conjunto de documentos a serem revisados no qual um subconjunto é baseado no mesmo modelo e tem principalmente o mesmo idioma clichê, com algumas diferenças aqui e ali.</span><span class="sxs-lookup"><span data-stu-id="06c1a-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="06c1a-105">Se um revisador puder identificar esse subconjunto, revisar um deles exaustivamente e analisar as diferenças para o restante, ele não teria perdido nenhuma informação exclusiva enquanto ocupava apenas uma fração de tempo que o levaria a ler todos os documentos decodificáveis.</span><span class="sxs-lookup"><span data-stu-id="06c1a-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="06c1a-106">Documentos semelhantes textuicamente próximos a grupos de detecção duplicados para ajudar você a tornar o processo de revisão mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="06c1a-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="06c1a-107">Como funciona?</span><span class="sxs-lookup"><span data-stu-id="06c1a-107">How does it work?</span></span>

<span data-ttu-id="06c1a-108">Quando a detecção quase duplicada é executado, o sistema analisará cada documento com texto.</span><span class="sxs-lookup"><span data-stu-id="06c1a-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="06c1a-109">Em seguida, ele compara cada documento entre si para determinar se sua semelhança é maior do que o limite definido.</span><span class="sxs-lookup"><span data-stu-id="06c1a-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="06c1a-110">Se for, os documentos serão agrupados.</span><span class="sxs-lookup"><span data-stu-id="06c1a-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="06c1a-111">Depois que todos os documentos são comparados e agrupados, um documento de cada grupo é marcado como o "pivô"; ao revisar seus documentos, você pode revisar um pivô primeiro e revisar os outros documentos no mesmo conjunto quase duplicado, concentrando-se na diferença entre o pivô e o documento que está em revisão.</span><span class="sxs-lookup"><span data-stu-id="06c1a-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
