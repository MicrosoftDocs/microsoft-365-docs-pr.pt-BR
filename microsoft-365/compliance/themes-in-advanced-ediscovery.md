---
title: Temas - Descoberta eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use Temas no Advanced eDiscovery para organizar conjuntos de revisão encontrando o tema dominante em cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285527"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="564c1-103">Temas no Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="564c1-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="564c1-104">Como uma pessoa escreve um documento?</span><span class="sxs-lookup"><span data-stu-id="564c1-104">How does a person write a document?</span></span> <span data-ttu-id="564c1-105">Geralmente, eles começam com uma ou mais ideias que querem transmitir no documento e compõem usando palavras que se alinham às ideias.</span><span class="sxs-lookup"><span data-stu-id="564c1-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="564c1-106">Quanto mais prevalente for uma ideia, mais frequentes serão as palavras relacionadas a essa ideia.</span><span class="sxs-lookup"><span data-stu-id="564c1-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="564c1-107">Isso também informa como as pessoas consomem documentos.</span><span class="sxs-lookup"><span data-stu-id="564c1-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="564c1-108">O importante a ser entendido na leitura de um documento são as ideias que o documento está tentando transmitir, quais ideias aparecem onde e quais são as relações entre as ideias.</span><span class="sxs-lookup"><span data-stu-id="564c1-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="564c1-109">Isso pode ser estendido para como uma pessoa deseja consumir um conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="564c1-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="564c1-110">Eles querem ver quais ideias estão presentes nos conjuntos e quais documentos estão falando sobre essas ideias.</span><span class="sxs-lookup"><span data-stu-id="564c1-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="564c1-111">Além disso, se eles encontram um documento específico de interesse, eles querem ser capazes de ver documentos que discutem ideias semelhantes.</span><span class="sxs-lookup"><span data-stu-id="564c1-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="564c1-112">A funcionalidade Temas no Advanced eDiscovery tenta imitar como os humanos explicam  os documentos, analisando os temas discutidos em um conjunto de revisão e atribuindo um tema a documentos no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="564c1-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="564c1-113">Em Advanced eDiscovery, Temas vão mais longe e identificam o *tema dominante* em cada documento.</span><span class="sxs-lookup"><span data-stu-id="564c1-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="564c1-114">O tema dominante é o que aparece com mais frequência em um documento.</span><span class="sxs-lookup"><span data-stu-id="564c1-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="564c1-115">Como os temas funcionam?</span><span class="sxs-lookup"><span data-stu-id="564c1-115">How does Themes work?</span></span>

<span data-ttu-id="564c1-116">A funcionalidade Temas analisa documentos com texto em um conjunto de revisão para analisar temas comuns que aparecem em todos os documentos no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="564c1-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="564c1-117">A Descoberta Eletrônica Avançada atribui esses temas aos documentos nos quais eles aparecem.</span><span class="sxs-lookup"><span data-stu-id="564c1-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="564c1-118">Ela também rotula cada tema com as palavras usadas nos documentos que são representantes do tema.</span><span class="sxs-lookup"><span data-stu-id="564c1-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="564c1-119">Como um documento pode ter vários tipos de assuntos, a Descoberta Eletrônica Avançada geralmente atribui vários temas a documentos. </span><span class="sxs-lookup"><span data-stu-id="564c1-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="564c1-120">O tema que mais se destaca em um documento é designado como o tema dominante.</span><span class="sxs-lookup"><span data-stu-id="564c1-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
