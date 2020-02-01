---
title: Repetir uma pesquisa de conteúdo para resolver um erro de localização de conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use o botão repetir para resolver pesquisas de conteúdo que têm erros de local de conteúdo.
ms.openlocfilehash: ce88749a887fea57e977e210de1eda40268cb832
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601618"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="35bef-103">Repetir uma pesquisa de conteúdo para resolver um erro de localização de conteúdo</span><span class="sxs-lookup"><span data-stu-id="35bef-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="35bef-104">Ao usar a pesquisa de conteúdo no centro de conformidade e segurança para pesquisar um grande número de caixas de correio, você pode receber erros de pesquisa semelhantes aos seguintes:</span><span class="sxs-lookup"><span data-stu-id="35bef-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the following:</span></span>

```text
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="35bef-105">Esses erros (com códigos de erro de CS001-002, CS003-002, CS008-009, CS012-002 e outros erros da forma CS0XX-0XX) indicam que a pesquisa de conteúdo não pôde pesquisar locais de conteúdo específicos; Neste exemplo, duas caixas de correio não foram pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="35bef-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="35bef-106">Esses erros são exibidos na página do menu de detalhes de status da pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="35bef-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="35bef-107">Causa de erros de localização de conteúdo</span><span class="sxs-lookup"><span data-stu-id="35bef-107">Cause of content location errors</span></span>

<span data-ttu-id="35bef-108">Ao pesquisar um grande número de caixas de correio, a pesquisa é distribuída entre milhares de servidores em um datacenter da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35bef-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="35bef-109">A qualquer momento, os servidores específicos podem estar no estado de reinicialização ou no processo de failover para cópias redundantes.</span><span class="sxs-lookup"><span data-stu-id="35bef-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="35bef-110">Em qualquer um desses casos, a solicitação de pesquisa de conteúdo para recuperar dados irá expirar.</span><span class="sxs-lookup"><span data-stu-id="35bef-110">In either of these cases, the Content Search's request to retrieve data will timeout.</span></span> <span data-ttu-id="35bef-111">No exemplo anterior, os erros para as caixas de correio que falharam foram o resultado da pesquisa com tempo limite.</span><span class="sxs-lookup"><span data-stu-id="35bef-111">In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="35bef-112">Resolvendo erros de localização de conteúdo</span><span class="sxs-lookup"><span data-stu-id="35bef-112">Resolving content location errors</span></span>

<span data-ttu-id="35bef-113">A reinicialização da pesquisa geralmente resultará em erros semelhantes em servidores diferentes.</span><span class="sxs-lookup"><span data-stu-id="35bef-113">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="35bef-114">Em vez de reiniciar a pesquisa, clique no botão **repetir** que é exibido na parte superior da página de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="35bef-114">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Clique no botão repetir para resolver erros de localização de conteúdo](media/retrycontentsearch3.png)

<span data-ttu-id="35bef-116">Isso resultará na repetição da pesquisa apenas para as caixas de correio que falharam.</span><span class="sxs-lookup"><span data-stu-id="35bef-116">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="35bef-117">Quando você repetir a pesquisa, os outros resultados retornados com êxito serão mantidos.</span><span class="sxs-lookup"><span data-stu-id="35bef-117">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="35bef-118">Dicas para evitar erros de localização de conteúdo</span><span class="sxs-lookup"><span data-stu-id="35bef-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="35bef-119">Aqui estão algumas causas de adição de erros de local de conteúdo e algumas dicas para ajudá-lo a evitá-los ao pesquisar grandes números de caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="35bef-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="35bef-120">A caixa de correio que está sendo pesquisada pode estar ocupada devido à atividade do usuário.</span><span class="sxs-lookup"><span data-stu-id="35bef-120">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="35bef-121">Nesse caso, o serviço de pesquisa pode se limitar a impedir que a caixa de correio fique indisponível.</span><span class="sxs-lookup"><span data-stu-id="35bef-121">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="35bef-122">Para evitar isso, tente executar pesquisas fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="35bef-122">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="35bef-123">A consulta de pesquisa pode recuperar muito conteúdo da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="35bef-123">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="35bef-124">Se possível, tente restringir o escopo da pesquisa usando palavras-chave, intervalos de datas e condições de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="35bef-124">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="35bef-125">Excesso de palavras-chave ou frases de palavra-chave quando você cria uma consulta de pesquisa usando a [lista de palavras-chave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span><span class="sxs-lookup"><span data-stu-id="35bef-125">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span></span> <span data-ttu-id="35bef-126">Quando você executa uma consulta de pesquisa que usa a lista de palavras-chave, o serviço essencialmente executa uma pesquisa separada para cada linha na lista de palavras-chave para que as estatísticas possam ser geradas.</span><span class="sxs-lookup"><span data-stu-id="35bef-126">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="35bef-127">Se você estiver usando a lista de palavras-chave em consultas de pesquisa, minimize o número de linhas na lista de palavras-chave ou divida as palavras-chave do número em listas menores e crie uma pesquisa diferente para cada lista de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="35bef-127">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="35bef-128">Para ajudar a reduzir os problemas causados por listas de palavras-chave grandes, agora você está limitado a um máximo de 20 linhas na lista de palavras-chave de uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="35bef-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="35bef-129">Muitas pesquisas estão sendo realizadas na mesma caixa de correio ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="35bef-129">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="35bef-130">Se possível, tente executar uma pesquisa de cada vez em uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="35bef-130">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="35bef-131">Pesquisar muitas caixas de correio em uma única pesquisa.</span><span class="sxs-lookup"><span data-stu-id="35bef-131">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="35bef-132">A probabilidade de erros de localização de conteúdo aumenta ao pesquisar um número muito grande de caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="35bef-132">The probability of content location errors increases when searching a very large number of mailboxes.</span></span> <span data-ttu-id="35bef-133">Se possível, tente executar várias pesquisas para que cada pesquisa inclua um subconjunto de caixas de correio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="35bef-133">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="35bef-134">A manutenção necessária está sendo executada na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="35bef-134">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="35bef-135">Embora essa causa provavelmente ocorra com frequência, espere um pouco antes de receber o erro de localização do conteúdo e repita a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="35bef-135">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
