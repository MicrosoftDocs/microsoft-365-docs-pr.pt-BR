---
title: Consultar o conteúdo em um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como criar e executar uma consulta em um conjunto de revisão para organizar o conteúdo para uma revisão mais eficiente em um Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736372"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="7bf07-103">Consultar e filtrar conteúdo em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="7bf07-103">Query and filter content in a review set</span></span>

<span data-ttu-id="7bf07-104">Na maioria dos casos, será útil aprofundar o conteúdo em um conjunto de revisão e organizá-lo para facilitar uma revisão mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="7bf07-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="7bf07-105">O uso de filtros e consultas em um conjunto de revisão ajuda você a se concentrar em um subconjunto de documentos que atendem aos critérios de sua revisão.</span><span class="sxs-lookup"><span data-stu-id="7bf07-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="7bf07-106">Filtros padrão</span><span class="sxs-lookup"><span data-stu-id="7bf07-106">Default filters</span></span>

<span data-ttu-id="7bf07-107">Em um conjunto de revisão, há cinco filtros padrão que são pré-carregados no conjunto de revisão:</span><span class="sxs-lookup"><span data-stu-id="7bf07-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="7bf07-108">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7bf07-108">Keywords</span></span>
- <span data-ttu-id="7bf07-109">Data</span><span class="sxs-lookup"><span data-stu-id="7bf07-109">Date</span></span>
- <span data-ttu-id="7bf07-110">Remetente/Autor</span><span class="sxs-lookup"><span data-stu-id="7bf07-110">Sender/Author</span></span>
- <span data-ttu-id="7bf07-111">Assunto/Título</span><span class="sxs-lookup"><span data-stu-id="7bf07-111">Subject/Title</span></span>
- <span data-ttu-id="7bf07-112">Tags</span><span class="sxs-lookup"><span data-stu-id="7bf07-112">Tags</span></span>

![Tipos de filtro padrão](../media/DefaultFilterTypes.png)

<span data-ttu-id="7bf07-114">Clique em cada filtro para expandi-lo e atribuir um valor.</span><span class="sxs-lookup"><span data-stu-id="7bf07-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="7bf07-115">Clique fora do filtro para aplicar automaticamente o filtro ao conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="7bf07-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="7bf07-116">A captura de tela a seguir mostra o filtro Data configurado para mostrar documentos dentro de um intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="7bf07-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![Filtro padrão expandido](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="7bf07-118">Adicionar ou remover filtros</span><span class="sxs-lookup"><span data-stu-id="7bf07-118">Add or remove filters</span></span>

<span data-ttu-id="7bf07-119">Para adicionar ou remover filtros exibidos para o conjunto de revisão, selecione **Filtros** para abrir o painel de filtro, que é exibido em uma página de sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="7bf07-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![Painel filtrar](../media/FilterPanel.png)

<span data-ttu-id="7bf07-121">Os filtros disponíveis são organizados em quatro seções:</span><span class="sxs-lookup"><span data-stu-id="7bf07-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="7bf07-122">**Pesquisa**: filtros que fornecem diferentes recursos de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7bf07-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="7bf07-123">**Análise &** codificação preditiva: filtra as propriedades geradas e adicionadas aos documentos quando você executar o trabalho de análise de **email** & Documento ou usar modelos de codificação preditivos.</span><span class="sxs-lookup"><span data-stu-id="7bf07-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="7bf07-124">**IDs**: Filtra todas as propriedades de ID de documentos.</span><span class="sxs-lookup"><span data-stu-id="7bf07-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="7bf07-125">**Propriedades do item**: Filtra para propriedades do documento.</span><span class="sxs-lookup"><span data-stu-id="7bf07-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="7bf07-126">Expanda cada seção e selecione ou desmarque filtros para adicioná-los ou removê-los no conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="7bf07-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="7bf07-127">Quando você adiciona um filtro, ele é exibido no conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="7bf07-127">When you add a filter, it's displayed in the filter set.</span></span> 

![Lista de seções de filtro e propriedades no painel de filtros](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="7bf07-129">Quando você expande uma seção no painel de filtro, você notará que os tipos de filtro padrão estão selecionados.</span><span class="sxs-lookup"><span data-stu-id="7bf07-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="7bf07-130">Você pode mantê-los selecionados ou desmarcados e removidos do conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="7bf07-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="7bf07-131">Tipos de filtro</span><span class="sxs-lookup"><span data-stu-id="7bf07-131">Filter types</span></span>

<span data-ttu-id="7bf07-132">Cada campo pesquisável em um conjunto de revisão tem um filtro correspondente que você pode usar para filtrar itens com base em um campo específico.</span><span class="sxs-lookup"><span data-stu-id="7bf07-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="7bf07-133">Há vários tipos de filtros:</span><span class="sxs-lookup"><span data-stu-id="7bf07-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="7bf07-134">**Freetext**: Um filtro de texto livre é aplicado a campos de texto, como "Assunto".</span><span class="sxs-lookup"><span data-stu-id="7bf07-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="7bf07-135">Você pode listar vários termos de pesquisa separando-os com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="7bf07-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="7bf07-136">**Data**: um filtro de data é usado para campos de data, como "Data da última modificação".</span><span class="sxs-lookup"><span data-stu-id="7bf07-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="7bf07-137">**Opções de** pesquisa : Um filtro de opções de pesquisa fornece uma lista de valores possíveis (cada valor é exibido com uma caixa de seleção que você pode selecionar) para campos específicos na revisão.</span><span class="sxs-lookup"><span data-stu-id="7bf07-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="7bf07-138">Esse filtro é usado para campos, como "Remetente", onde há um número finito de valores possíveis no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="7bf07-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="7bf07-139">**Palavra-chave**: uma condição de palavra-chave é uma instância específica de condição de texto livre que você pode usar para pesquisar termos.</span><span class="sxs-lookup"><span data-stu-id="7bf07-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="7bf07-140">Você também pode usar linguagem de consulta do tipo KQL neste tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="7bf07-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="7bf07-141">Para obter mais informações, consulte as seções Idioma de consulta e Construtor avançado de consultas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="7bf07-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="7bf07-142">Incluir e excluir relações de filtro</span><span class="sxs-lookup"><span data-stu-id="7bf07-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="7bf07-143">Você tem a opção de alterar a relação incluir e excluir para um filtro específico.</span><span class="sxs-lookup"><span data-stu-id="7bf07-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="7bf07-144">Por exemplo, no filtro Tag, você pode excluir itens **marcados** com uma marca específica selecionando Igual a nenhum no filtro suspenso.</span><span class="sxs-lookup"><span data-stu-id="7bf07-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![Excluir filtro de marca](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="7bf07-146">Salvar filtros como consultas</span><span class="sxs-lookup"><span data-stu-id="7bf07-146">Save filters as queries</span></span>

<span data-ttu-id="7bf07-147">Depois de satisfeito com seus filtros, você pode salvar a combinação de filtro como uma consulta de filtro.</span><span class="sxs-lookup"><span data-stu-id="7bf07-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="7bf07-148">Isso permite aplicar o filtro nas próximas sessões de revisão.</span><span class="sxs-lookup"><span data-stu-id="7bf07-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="7bf07-149">Para salvar um filtro, selecione **Salvar a consulta e** nomeá-la.</span><span class="sxs-lookup"><span data-stu-id="7bf07-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="7bf07-150">Você ou outros revisadores podem executar consultas de filtro salvas anteriormente selecionando o **menu** suspenso Consultas de filtro salvo e selecionando uma consulta de filtro a ser aplicada aos documentos do conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="7bf07-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![Salvar uma consulta de filtro](../media/SaveFilterQuery.png)

<span data-ttu-id="7bf07-152">Para excluir uma consulta de filtro, abra o painel de filtro e selecione o ícone de lixeira ao lado da consulta.</span><span class="sxs-lookup"><span data-stu-id="7bf07-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![Excluir uma consulta de filtro](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="7bf07-154">Linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="7bf07-154">Query language</span></span>

<span data-ttu-id="7bf07-155">Além de usar filtros, você também pode usar um idioma de consulta parecido com KQL no filtro Palavras-chave para criar sua consulta de pesquisa de conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="7bf07-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="7bf07-156">O idioma de consulta para consultas de conjunto de revisão dá suporte a operadores booleano padrão, como **AND**, **OR**, **NOT** e **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="7bf07-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="7bf07-157">Ele também dá suporte a um caractere curinga de caractere único (?) e a um caractere curinga de vários caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="7bf07-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="7bf07-158">Construtor avançado de consultas</span><span class="sxs-lookup"><span data-stu-id="7bf07-158">Advanced query builder</span></span>

<span data-ttu-id="7bf07-159">Você também pode criar consultas mais avançadas para pesquisar documentos em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="7bf07-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="7bf07-160">Abra o painel de filtro, selecione **Filtros** e expanda a **seção** Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7bf07-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![Adicionar um filtro KQL](../media/AddKQLFilter.png)

2. <span data-ttu-id="7bf07-162">Selecione o **filtro KQL** e clique em **Abrir construtor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="7bf07-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="7bf07-163">Neste painel, você pode criar consultas KQL complexas usando o construtor de consultas.</span><span class="sxs-lookup"><span data-stu-id="7bf07-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="7bf07-164">Você pode adicionar condições ou adicionar grupos de condição que são feitos de várias condições que são conectadas logicamente por **relações AND** **ou OR.**</span><span class="sxs-lookup"><span data-stu-id="7bf07-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![Usar o construtor de consultas para configurar consultas de filtro complexas](../media/ComplexQuery.png)
