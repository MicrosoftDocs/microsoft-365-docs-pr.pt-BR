---
title: Temas
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
description: ''
ms.openlocfilehash: ba57a89365c2a76dec215f56d7ed0755f27be12d
ms.sourcegitcommit: caa3f681a68daf5e463093a922c3d6f378143d91
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "39191197"
---
# <a name="themes"></a><span data-ttu-id="c046f-102">Temas</span><span class="sxs-lookup"><span data-stu-id="c046f-102">Themes</span></span>

<span data-ttu-id="c046f-103">Como uma pessoa escreve um documento?</span><span class="sxs-lookup"><span data-stu-id="c046f-103">How does a person write a document?</span></span> <span data-ttu-id="c046f-104">Geralmente, elas começam com uma ou mais ideias que desejam transmitir no documento e compor usando palavras que se alinham com as ideias.</span><span class="sxs-lookup"><span data-stu-id="c046f-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="c046f-105">Quanto mais predominante uma ideia é, mais frequentes as palavras relacionadas a essa ideia tendem a ser.</span><span class="sxs-lookup"><span data-stu-id="c046f-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="c046f-106">Isso informa como as pessoas consomem documentos também.</span><span class="sxs-lookup"><span data-stu-id="c046f-106">This informs how people consume documents as well.</span></span> <span data-ttu-id="c046f-107">O importante a ser compreendido na leitura de um documento é as ideias que o documento está tentando transmitir, quais ideias aparecem onde e quais são as relações entre as idéias.</span><span class="sxs-lookup"><span data-stu-id="c046f-107">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="c046f-108">Isso pode ser estendido para a forma como uma pessoa deseja consumir um conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="c046f-108">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="c046f-109">Eles desejam ver quais ideias estão presentes nos conjuntos e quais documentos estão falando sobre essas ideias.</span><span class="sxs-lookup"><span data-stu-id="c046f-109">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="c046f-110">Além disso, caso encontrem um documento de interesse específico, eles desejam poder ver documentos que discutem ideias semelhantes.</span><span class="sxs-lookup"><span data-stu-id="c046f-110">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="c046f-111">A funcionalidade temas em descoberta eletrônica avançada tenta simular o motivo dos seresns de documentos, analisando os *temas* que são discutidos em um conjunto de análise e atribuindo um tema a documentos no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="c046f-111">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="c046f-112">Na descoberta eletrônica avançada, os temas vão para um passo adiante e identificam o *tema dominante* em cada documento.</span><span class="sxs-lookup"><span data-stu-id="c046f-112">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="c046f-113">O tema dominante é aquele que aparece mais freqüentemente em um documento.</span><span class="sxs-lookup"><span data-stu-id="c046f-113">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="c046f-114">Como os temas funcionam?</span><span class="sxs-lookup"><span data-stu-id="c046f-114">How does Themes work?</span></span>

<span data-ttu-id="c046f-115">A funcionalidade temas analisa documentos com texto em uma revisão definida para analisar temas comuns que aparecem em todos os documentos do conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="c046f-115">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="c046f-116">A descoberta eletrônica avançada atribui esses temas aos documentos em que eles aparecem.</span><span class="sxs-lookup"><span data-stu-id="c046f-116">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="c046f-117">Ele também rotula cada tema com as palavras usadas nos documentos que são representativos do tema.</span><span class="sxs-lookup"><span data-stu-id="c046f-117">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="c046f-118">Como um documento pode conter vários tipos de assunto, a descoberta eletrônica avançada freqüentemente atribui vários temas a documentos.</span><span class="sxs-lookup"><span data-stu-id="c046f-118">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="c046f-119">O tema que aparece mais proeminentemente em um documento é designado como seu tema dominante.</span><span class="sxs-lookup"><span data-stu-id="c046f-119">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>