---
title: Consultar os dados em um conjunto de revisão
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
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073770"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="4532d-102">Consultar os dados em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="4532d-102">Query the data in a review set</span></span>

<span data-ttu-id="4532d-103">Na maioria dos casos, será útil ser capaz de se aprofundar no que está em um conjunto de revisão e organizá-los para análise mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="4532d-103">In most cases, it will be useful to be able to dig deeper into what is there in a review set and organize them to review more efficiently.</span></span> <span data-ttu-id="4532d-104">As consultas em um conjunto de revisão permitem que você faça isso, permitindo que você se concentre em um subconjunto de documentos que atendem aos critérios definidos por você ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="4532d-104">Queries within a review set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-review-set"></a><span data-ttu-id="4532d-105">Criar e executar uma consulta dentro de um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="4532d-105">Creating and running a query within a review set</span></span>

<span data-ttu-id="4532d-106">Para criar e executar uma consulta no conjunto de análise, clique em "nova consulta" em seu conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="4532d-106">In order to create and run a query within your review set, click on "New Query" in your review set.</span></span> <span data-ttu-id="4532d-107">Depois de nomear sua consulta e definir as condições, clique em "salvar" para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="4532d-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="4532d-108">Para executar uma consulta que tenha sido salva anteriormente, basta clicar na consulta salva.</span><span class="sxs-lookup"><span data-stu-id="4532d-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="4532d-109">Consulte os [campos de metadados do documento](document-metadata-fields.md) para obter uma lista de metadados que você pode pesquisar.</span><span class="sxs-lookup"><span data-stu-id="4532d-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="4532d-110">Criar sua consulta</span><span class="sxs-lookup"><span data-stu-id="4532d-110">Building your query</span></span>

<span data-ttu-id="4532d-111">Você pode criar sua consulta usando uma combinação de cartões de condição e linguagem de consulta no cartão de condição de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="4532d-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="4532d-112">Você pode agrupar cartões de condição juntos como um bloco para criar uma consulta mais complexa.</span><span class="sxs-lookup"><span data-stu-id="4532d-112">You can group condition cards together as a block to craft a more complex query.</span></span>

### <a name="condition-card"></a><span data-ttu-id="4532d-113">Cartão de condição</span><span class="sxs-lookup"><span data-stu-id="4532d-113">Condition card</span></span>

<span data-ttu-id="4532d-114">Cada campo pesquisável em um conjunto de revisão tem um cartão de condição correspondente que você pode usar para criar sua consulta.</span><span class="sxs-lookup"><span data-stu-id="4532d-114">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="4532d-115">Há vários tipos de cartões de condição:</span><span class="sxs-lookup"><span data-stu-id="4532d-115">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="4532d-116">FREETEXT: o cartão de condição do freetext é usado para campos de texto como o assunto.</span><span class="sxs-lookup"><span data-stu-id="4532d-116">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="4532d-117">Você pode listar vários termos de pesquisa separando-os com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="4532d-117">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="4532d-118">Date: o cartão de condição de data é usado para campos de data, como data da última modificação.</span><span class="sxs-lookup"><span data-stu-id="4532d-118">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="4532d-119">Opções de pesquisa: o cartão de condição opções de pesquisa fornecerá uma lista de valores possíveis para o campo específico em seu conjunto de análise.</span><span class="sxs-lookup"><span data-stu-id="4532d-119">Search options: search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="4532d-120">Isso é usado para campos, como remetente, onde há um número finito de valores possíveis em seu conjunto de análise.</span><span class="sxs-lookup"><span data-stu-id="4532d-120">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>
- <span data-ttu-id="4532d-121">Palavra-chave: cartão de condição de palavra-chave é uma instância específica do cartão de condição FREETEXT que você pode usar para pesquisar termos ou usar o idioma de consulta do KQL.</span><span class="sxs-lookup"><span data-stu-id="4532d-121">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="4532d-122">Veja mais detalhes abaixo.</span><span class="sxs-lookup"><span data-stu-id="4532d-122">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="4532d-123">Linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="4532d-123">Query language</span></span>

<span data-ttu-id="4532d-124">Além de cartões de condição, você pode usar um idioma de consulta do tipo KQL no cartão de palavras-chave para criar sua consulta.</span><span class="sxs-lookup"><span data-stu-id="4532d-124">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="4532d-125">A linguagem de consulta oferece suporte à sintaxe KQL padrão como e, ou, não e NEAR (n).</span><span class="sxs-lookup"><span data-stu-id="4532d-125">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="4532d-126">Também suporta curingas de caractere único (?) e curinga de vários caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="4532d-126">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>

## <a name="filter"></a><span data-ttu-id="4532d-127">Filtrar</span><span class="sxs-lookup"><span data-stu-id="4532d-127">Filter</span></span>

<span data-ttu-id="4532d-128">Além das consultas que você pode salvar, você pode sobrepor mais condições de imediato aos resultados da consulta usando filtros.</span><span class="sxs-lookup"><span data-stu-id="4532d-128">In addition to queries that you can save, you can overlay additional conditions on the fly to your query results using filters.</span></span> <span data-ttu-id="4532d-129">Os filtros diferem das consultas de algumas maneiras significativas:</span><span class="sxs-lookup"><span data-stu-id="4532d-129">Filters differ from queries in a few significant ways:</span></span>
- <span data-ttu-id="4532d-130">Os filtros são temporários (ou seja, não persistem em diferentes sessões), enquanto as consultas são salvas no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="4532d-130">Filters are transient (i.e. they do not persist over different sessions), whereas queries are saved to the review set.</span></span>
- <span data-ttu-id="4532d-131">Os filtros são sempre aditivos; os filtros serão aplicados na parte superior da consulta que você tem em vigor no momento, ao passo que a aplicação de uma consulta substituirá a consulta em vigor.</span><span class="sxs-lookup"><span data-stu-id="4532d-131">Filters are always additive; filters will apply on top of the query you have in effect at the moment, whereas applying a query will replace the query in effect.</span></span>