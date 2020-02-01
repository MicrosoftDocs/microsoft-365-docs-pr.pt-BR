---
title: Gerar relatório de termo de pesquisa para um conjunto de revisão
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: f3421c62f0c7ac519ad44fc05174cd76872551d3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601608"
---
# <a name="generate-search-term-report-for-a-review-set"></a><span data-ttu-id="c72be-102">Gerar relatório de termo de pesquisa para um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="c72be-102">Generate search term report for a review set</span></span>

<span data-ttu-id="c72be-103">Na descoberta eletrônica, uma das condições usadas com mais frequência para consultar documentos é usar termos de pesquisa de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="c72be-103">In eDiscovery, one of the most frequently used conditions for querying documents is by using keyword search terms.</span></span> <span data-ttu-id="c72be-104">Identificando documentos que contenham as palavras-chave específicas (também conhecidas como *termos*) que são importantes para um caso, os revisores podem começar a obter uma compreensão de alto nível do que estão enfrentando.</span><span class="sxs-lookup"><span data-stu-id="c72be-104">By identifying documents that contain the specific keywords (also referred to as *terms*) that are important to a case, reviewers can begin to get a high-level understanding of what they are facing.</span></span> <span data-ttu-id="c72be-105">Em descoberta eletrônica avançada no Microsoft 365, você pode fazer isso precisamente gerando relatórios de termos de pesquisa em consultas salvas em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="c72be-105">In Advanced eDiscovery in Microsoft 365, you can do precisely this by generating search term reports on saved queries within a review set.</span></span>

## <a name="step-1-create-a-saved-query-in-the-review-set"></a><span data-ttu-id="c72be-106">Etapa 1: criar uma consulta salva no conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="c72be-106">Step 1: Create a saved query in the review set</span></span>

<span data-ttu-id="c72be-107">Para gerar um relatório de termo de pesquisa significativo, crie uma consulta salva que define o conjunto de documentos no conjunto de revisão para o qual você deseja gerar um relatório de termos de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c72be-107">To generate a meaningful search term report, create a saved query that defines the set of documents in the review set that you want to generate a search term report for.</span></span> <span data-ttu-id="c72be-108">Por exemplo, você pode usar um intervalo de datas ou o conjunto real de termos de pesquisa (usando o cartão de condição de palavras-chave) para criar a consulta.</span><span class="sxs-lookup"><span data-stu-id="c72be-108">For example, you can use a date range or the actual set of search terms (by using the Keywords condition card) to create the query.</span></span> <span data-ttu-id="c72be-109">Para saber mais sobre as consultas set de revisão, confira [consultar os dados em um conjunto de revisão](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="c72be-109">To learn more about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="step-2-generate-a-search-term-report"></a><span data-ttu-id="c72be-110">Etapa 2: gerar um relatório de termos de pesquisa</span><span class="sxs-lookup"><span data-stu-id="c72be-110">Step 2: Generate a search term report</span></span>

<span data-ttu-id="c72be-111">Há duas maneiras diferentes de gerar um relatório de termos de pesquisa: por meio do menu de contexto da consulta salva que você criou na etapa 1 ou do console de gerenciamento de relatório de termos de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c72be-111">There are two different ways to generate a search term report: through the context menu of the saved query you created in Step 1, or through the search term report management console.</span></span>

- <span data-ttu-id="c72be-112">Para usar o menu de contexto, abra o menu de contexto da consulta salva que você criou na etapa 1 e clique em **gerar relatório de termos de pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="c72be-112">To use the context menu, open the context menu of the saved query you created in Step 1, and click **Generate search term report**.</span></span>

- <span data-ttu-id="c72be-113">Para usar o console de gerenciamento, vá para **gerenciar análise definir > exibir relatórios de termos de pesquisa**, clique em **novo**e selecione a consulta salva que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="c72be-113">To use the management console, go to **Manage review set > View search term reports**, click **New**, and then select the saved query you created in Step 1.</span></span>

<span data-ttu-id="c72be-114">Em seguida, insira os termos que você gostaria de relatar, separados por nova linha; se a consulta salva que você criou na etapa 1 cartão de condição de palavra-chave usada, a página de submenu será preenchida com os termos do cartão de condição de primeira palavra-chave usado na consulta salva.</span><span class="sxs-lookup"><span data-stu-id="c72be-114">Then, enter the terms you would like to report on, separated by newline; if the saved query that you created in Step 1 used keyword condition card, the flyout page will be pre-populated with the terms from the first keyword condition card used in the saved query.</span></span>

<span data-ttu-id="c72be-115">Em seguida, selecione até três dinâmicas para relatar e clique em **gerar**, que iniciará o trabalho de geração de relatórios de termos de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c72be-115">Then, select up to three pivots to report on, and click on **Generate**, which will start the search term report generation job.</span></span>

### <a name="what-is-a-pivot"></a><span data-ttu-id="c72be-116">O que é uma tabela dinâmica?</span><span class="sxs-lookup"><span data-stu-id="c72be-116">What is a pivot?</span></span>

<span data-ttu-id="c72be-117">Os pivôs são como o relatório será organizado.</span><span class="sxs-lookup"><span data-stu-id="c72be-117">Pivots are how the report will be organized.</span></span> <span data-ttu-id="c72be-118">Considere o exemplo seguinte.</span><span class="sxs-lookup"><span data-stu-id="c72be-118">Consider the following example.</span></span>

- <span data-ttu-id="c72be-119">A consulta salva recupera 10 documentos: doc1 a doc10.</span><span class="sxs-lookup"><span data-stu-id="c72be-119">The saved query retrieves 10 documents: doc1 through doc10.</span></span>

- <span data-ttu-id="c72be-120">doc1, Doc2, Doc3, Doc4, doc5, doc6 e doc7 contêm o termo "eDiscovery".</span><span class="sxs-lookup"><span data-stu-id="c72be-120">doc1, doc2, doc3, doc4, doc5, doc6, and doc7 contain the term "eDiscovery".</span></span>

- <span data-ttu-id="c72be-121">doc6, doc7, doc8, doc9 e doc10 contêm o termo "investigação".</span><span class="sxs-lookup"><span data-stu-id="c72be-121">doc6, doc7, doc8, doc9, and doc10 contain the term "Investigation".</span></span>

- <span data-ttu-id="c72be-122">doc1, Doc3, doc5, doc7, doc9 são de responsáveis por.</span><span class="sxs-lookup"><span data-stu-id="c72be-122">doc1, doc3, doc5, doc7, doc9 are from custodian A.</span></span>

- <span data-ttu-id="c72be-123">Doc2, Doc4, doc6, doc8, doc10 são de responsáveis por ISB.</span><span class="sxs-lookup"><span data-stu-id="c72be-123">doc2, doc4, doc6, doc8, doc10 are from custodian B.</span></span>

<span data-ttu-id="c72be-124">Nesse caso, se você fosse gerar um relatório de termos de pesquisa nos termos "eDiscovery" e "investigação" e dinamizar os responsáveis, o relatório de termos de pesquisa será organizado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c72be-124">In this case, if you were to generate a search term report on the terms "eDiscovery" and "Investigation" and pivot on custodians, the search term report would be organized as follows:</span></span>

- <span data-ttu-id="c72be-125">"eDiscovery"-responsáveis: 4 documentos</span><span class="sxs-lookup"><span data-stu-id="c72be-125">"eDiscovery" - custodian A: 4 documents</span></span>

- <span data-ttu-id="c72be-126">"eDiscovery"-responsáveis B: 3 documentos</span><span class="sxs-lookup"><span data-stu-id="c72be-126">"eDiscovery" - custodian B: 3 documents</span></span>

- <span data-ttu-id="c72be-127">"Investigação"-responsáveis: 2 documentos</span><span class="sxs-lookup"><span data-stu-id="c72be-127">"Investigation" - custodian A: 2 documents</span></span>

- <span data-ttu-id="c72be-128">"Investigação"-responsáveis B: 3 documentos</span><span class="sxs-lookup"><span data-stu-id="c72be-128">"Investigation" - custodian B: 3 documents</span></span>

## <a name="step-3-download-report"></a><span data-ttu-id="c72be-129">Etapa 3: baixar o relatório</span><span class="sxs-lookup"><span data-stu-id="c72be-129">Step 3: Download report</span></span>

<span data-ttu-id="c72be-130">No console de gerenciamento de termos de pesquisa, você pode acompanhar o status de um trabalho de relatório de um termo de pesquisa criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c72be-130">In the search term management console, you can track the status of a previously-created search term report job.</span></span> <span data-ttu-id="c72be-131">Depois que o trabalho for concluído, você poderá clicar na linha do relatório de termos de pesquisa e clicar em "download", que baixará o relatório de termos de pesquisa em um formato CSV.</span><span class="sxs-lookup"><span data-stu-id="c72be-131">Once the job completes, you can click on the row for the search term report and click "Download", which will download the search term report in a CSV format.</span></span> <span data-ttu-id="c72be-132">Haverá uma linha por (Pesquisar termo, pivots) tupla e cada linha conterá as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="c72be-132">There will be one row per (search term, pivots) tuple, and each row will contain the following information:</span></span>

- <span data-ttu-id="c72be-133">Quantos documentos foram recuperados?</span><span class="sxs-lookup"><span data-stu-id="c72be-133">How many documents were retrieved?</span></span>

- <span data-ttu-id="c72be-134">Quantas vezes o termo de pesquisa foi encontrado nos documentos?</span><span class="sxs-lookup"><span data-stu-id="c72be-134">How many times was the search term found across the documents?</span></span>

- <span data-ttu-id="c72be-135">Qual é o volume total de documentos recuperados?</span><span class="sxs-lookup"><span data-stu-id="c72be-135">What is the total volume of retrieved documents?</span></span>

- <span data-ttu-id="c72be-136">Quantas famílias foram recuperadas?</span><span class="sxs-lookup"><span data-stu-id="c72be-136">How many families were retrieved?</span></span>

- <span data-ttu-id="c72be-137">Qual é a contagem total de documentos dessas famílias, incluindo os documentos que não tinham o termo de pesquisa?</span><span class="sxs-lookup"><span data-stu-id="c72be-137">What is the total document count of those families, including the documents that did not have the search term?</span></span>

- <span data-ttu-id="c72be-138">Qual é o volume total dos anteriores?</span><span class="sxs-lookup"><span data-stu-id="c72be-138">What is the total volume of the above?</span></span>