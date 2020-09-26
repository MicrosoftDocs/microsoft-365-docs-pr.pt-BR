---
title: Detecção de duplicidade próxima-investigação de dados
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
description: Ao gerenciar investigações de dados, use a detecção quase duplicada para agrupar documentos semelhantes ao analisar evidências em investigações de dados (versão prévia).
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 37ce968016e674ec83da536c65361d2075cf9bbb
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285947"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="dca0f-103">Detecção de duplicata próxima</span><span class="sxs-lookup"><span data-stu-id="dca0f-103">Near duplicate detection</span></span>

<span data-ttu-id="dca0f-104">Considere um conjunto de documentos para ser revisado no qual um subconjunto é baseado no mesmo modelo e tem principalmente o mesmo idioma clichê, com algumas diferenças aqui e ali.</span><span class="sxs-lookup"><span data-stu-id="dca0f-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="dca0f-105">Se um revisor pudesse identificar esse subconjunto, revise um deles cuidadosamente e revise as diferenças para o resto, eles não teriam informações exclusivas e, ao mesmo tempo, levaria apenas uma fração de tempo que teria levado em vista para ler todos os documentos na capa.</span><span class="sxs-lookup"><span data-stu-id="dca0f-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="dca0f-106">Um grupo de detecção de duplicidades próximo agrupa documentos semelhantes para ajudá-lo a tornar seu processo de revisão mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="dca0f-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="dca0f-107">Como funciona?</span><span class="sxs-lookup"><span data-stu-id="dca0f-107">How does it work?</span></span>

<span data-ttu-id="dca0f-108">Quando a detecção próxima duplicação é executada, o sistema analisa todos os documentos com texto.</span><span class="sxs-lookup"><span data-stu-id="dca0f-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="dca0f-109">Em seguida, ele compara todos os documentos entre si para determinar se sua similaridade é maior do que o limite definido.</span><span class="sxs-lookup"><span data-stu-id="dca0f-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="dca0f-110">Se for, os documentos serão agrupados.</span><span class="sxs-lookup"><span data-stu-id="dca0f-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="dca0f-111">Depois que todos os documentos forem comparados e agrupados, um documento de cada grupo será marcado como "pivô"; ao revisar seus documentos, você pode revisar uma tabela dinâmica primeiro e revisar os outros documentos no mesmo conjunto próximo duplicado, concentrando-se na diferença entre a tabela dinâmica e o documento que está em revisão.</span><span class="sxs-lookup"><span data-stu-id="dca0f-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
