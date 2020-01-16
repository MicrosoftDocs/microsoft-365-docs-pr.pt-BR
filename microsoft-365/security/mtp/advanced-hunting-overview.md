---
title: Visão geral sobre a busca avançada na Proteção contra Ameaças da Microsoft
description: Saiba mais sobre as consultas avançadas de buscas no Microsoft 365 e sobre como usá-las para encontrar ameaças e deficiências na rede de forma proativa
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção contra ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, Kusto, Microsoft 365, proteção contra ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 791eee143c80e00a3fdb1fa4dbde8bbf41612e9a
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210346"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="b133b-104">Faça buscas proativas por ameaças com a busca avançada da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b133b-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="b133b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b133b-105">**Applies to:**</span></span>
- <span data-ttu-id="b133b-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b133b-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b133b-107">A busca avançada é uma ferramenta de busca de ameaças baseada em consultas que permite explorar até 30 dias de dados brutos.</span><span class="sxs-lookup"><span data-stu-id="b133b-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="b133b-108">Você pode inspecionar proativamente os eventos na sua rede para localizar indicadores e entidades interessantes.</span><span class="sxs-lookup"><span data-stu-id="b133b-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="b133b-109">O acesso flexível aos dados facilita a busca irrestrita por ameaças potenciais e conhecidas.</span><span class="sxs-lookup"><span data-stu-id="b133b-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="b133b-110">No centro de segurança do Microsoft 365, a busca avançada oferece suporte a consultas que procuram dados do Microsoft defender ATP, abrangendo dados de dispositivos integrados e o Office 365 ATP, fornecendo dados de emails.</span><span class="sxs-lookup"><span data-stu-id="b133b-110">In the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="b133b-111">Para usar a busca avançada, é necessário [habilitar a Proteção contra Ameaças da Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="b133b-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="b133b-112">Introdução à busca avançada</span><span class="sxs-lookup"><span data-stu-id="b133b-112">Get started with advanced hunting</span></span>

<span data-ttu-id="b133b-113">Recomendamos que você execute várias etapas para começar a trabalhar rapidamente com a busca avançada.</span><span class="sxs-lookup"><span data-stu-id="b133b-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="b133b-114">Meta de aprendizagem</span><span class="sxs-lookup"><span data-stu-id="b133b-114">Learning goal</span></span> | <span data-ttu-id="b133b-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="b133b-115">Description</span></span> | <span data-ttu-id="b133b-116">Recurso</span><span class="sxs-lookup"><span data-stu-id="b133b-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="b133b-117">**Ver qual seria a linguagem**</span><span class="sxs-lookup"><span data-stu-id="b133b-117">**Get a feel for the language**</span></span> | <span data-ttu-id="b133b-118">A busca avançada se baseia na [linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/), que oferece suporte à mesma sintaxe e operadores.</span><span class="sxs-lookup"><span data-stu-id="b133b-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="b133b-119">Comece a aprender a linguagem de consulta executando a primeira consulta.</span><span class="sxs-lookup"><span data-stu-id="b133b-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="b133b-120">Visão geral sobre a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b133b-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="b133b-121">**Compreender o esquema**</span><span class="sxs-lookup"><span data-stu-id="b133b-121">**Understand the schema**</span></span> | <span data-ttu-id="b133b-122">Obtenha uma compreensão de alto nível das tabelas no esquema e em suas colunas.</span><span class="sxs-lookup"><span data-stu-id="b133b-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="b133b-123">Isso ajuda a determinar onde procurar dados e como construir suas consultas.</span><span class="sxs-lookup"><span data-stu-id="b133b-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="b133b-124">Referência de esquema</span><span class="sxs-lookup"><span data-stu-id="b133b-124">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="b133b-125">**Usar consultas predefinidas**</span><span class="sxs-lookup"><span data-stu-id="b133b-125">**Use predefined queries**</span></span> | <span data-ttu-id="b133b-126">Explore coleções de consultas predefinidas que abrangem diferentes cenários de exploração de ameaças.</span><span class="sxs-lookup"><span data-stu-id="b133b-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="b133b-127">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="b133b-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="b133b-128">**Otimizar consultas**</span><span class="sxs-lookup"><span data-stu-id="b133b-128">**Optimize queries**</span></span> | <span data-ttu-id="b133b-129">Saiba como criar consultas eficientes e que combinem dados de emails e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b133b-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="b133b-130">[Práticas recomendadas de consulta](advanced-hunting-shared-queries.md), [Busca em dispositivos e emails](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="b133b-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="b133b-131">Obter ajuda durante a criação de consultas</span><span class="sxs-lookup"><span data-stu-id="b133b-131">Get help as you write queries</span></span>
<span data-ttu-id="b133b-132">Aproveite as funcionalidades a seguir para escrever rapidamente as consultas:</span><span class="sxs-lookup"><span data-stu-id="b133b-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="b133b-133">**Sugestão automática** — conforme você faz a consulta, a busca avançada fornece sugestões.</span><span class="sxs-lookup"><span data-stu-id="b133b-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="b133b-134">**Referência de esquema** — inclui a lista de tabelas e suas colunas ao lado da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b133b-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="b133b-135">Para saber mais, passe o mouse sobre um item.</span><span class="sxs-lookup"><span data-stu-id="b133b-135">For more information, hover over an item.</span></span> <span data-ttu-id="b133b-136">Clique duas vezes em um item para inseri-lo no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="b133b-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="b133b-137">Detalhamento dos resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="b133b-137">Drilldown from query results</span></span>
<span data-ttu-id="b133b-138">Para ver em seus resultados de consulta mais informações sobre entidades, como máquinas, arquivos, usuários, endereços IP e URLs, simplesmente clique no identificador de entidade.</span><span class="sxs-lookup"><span data-stu-id="b133b-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="b133b-139">Isso abre uma página de perfil detalhada para a entidade selecionada no Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b133b-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="b133b-140">Ajustar consultas a partir dos resultados</span><span class="sxs-lookup"><span data-stu-id="b133b-140">Tweak your queries from the results</span></span>
<span data-ttu-id="b133b-141">Clique com o botão direito do mouse em um valor no conjunto de resultados para aprimorar rapidamente a consulta.</span><span class="sxs-lookup"><span data-stu-id="b133b-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="b133b-142">Você pode usar as opções para:</span><span class="sxs-lookup"><span data-stu-id="b133b-142">You can use the options to:</span></span>

- <span data-ttu-id="b133b-143">Procurar explicitamente pelo valor selecionado (`==`)</span><span class="sxs-lookup"><span data-stu-id="b133b-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="b133b-144">Excluir o valor selecionado da consulta (`!=`)</span><span class="sxs-lookup"><span data-stu-id="b133b-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="b133b-145">Obter operadores mais avançados para adicionar o valor à sua consulta, como `contains`, `starts with` e `ends with`</span><span class="sxs-lookup"><span data-stu-id="b133b-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Imagem do conjunto de resultados da busca avançada do Microsoft Defender ATP](../images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="b133b-147">Filtrar os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="b133b-147">Filter the query results</span></span>
<span data-ttu-id="b133b-148">Os filtros exibidos à direita fornecem um resumo do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b133b-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="b133b-149">Cada coluna tem sua própria seção, que lista os valores distintos encontrados para essa coluna e o número de instâncias.</span><span class="sxs-lookup"><span data-stu-id="b133b-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="b133b-150">Refine a consulta selecionando os botões "+" ou "-" nos valores que você deseja incluir ou excluir e selecione **Executar consulta**.</span><span class="sxs-lookup"><span data-stu-id="b133b-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Imagem do filtro de busca avançada](../images/advanced-hunting-filter.png)

<span data-ttu-id="b133b-152">Depois de aplicar o filtro para modificar e executar a consulta, os resultados serão atualizados de acordo.</span><span class="sxs-lookup"><span data-stu-id="b133b-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b133b-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b133b-153">Related topics</span></span>
- [<span data-ttu-id="b133b-154">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b133b-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b133b-155">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="b133b-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b133b-156">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="b133b-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b133b-157">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b133b-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b133b-158">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="b133b-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)