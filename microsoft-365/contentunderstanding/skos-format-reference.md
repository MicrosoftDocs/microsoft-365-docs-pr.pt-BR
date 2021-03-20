---
title: Formato SKOS como referência para a taxonomia do SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Formato SKOS como referência para a taxonomia do SharePoint
ms.openlocfilehash: 6a565de9598706e998206304093ed86a1a55704d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911169"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="39143-103">Formato SKOS como referência para a taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="39143-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="39143-104">Este artigo inclui o vocabulário RDF utilizado para representar a [Taxonomia do SharePoint](/dotnet/api/microsoft.sharepoint.taxonomy) e é baseado no [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="39143-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="39143-105">Para a serialização desta sintaxe RDF, utilize o RDF [TARTARUGA](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="39143-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="39143-106">A tabela seguinte exibe os equivalentes ao [SKOS](https://www.w3.org/TR/skos-primer/) para o vocabulário [taxonomia do SharePoint](/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="39143-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="39143-107">O SharePoint não suporta valores [SKOS](https://www.w3.org/TR/skos-primer/) que não tenham equivalente em taxonomia do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39143-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="39143-108">Taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="39143-108">SharePoint taxonomy</span></span>|<span data-ttu-id="39143-109">Equivalente ao SKOS</span><span class="sxs-lookup"><span data-stu-id="39143-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="39143-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="39143-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="39143-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="39143-111">skos:Concept</span></span>|
|<span data-ttu-id="39143-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="39143-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="39143-113">skos:ConceitoScheme</span><span class="sxs-lookup"><span data-stu-id="39143-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="39143-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="39143-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="39143-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="39143-115">skos:inScheme</span></span>|
|<span data-ttu-id="39143-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="39143-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="39143-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="39143-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="39143-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="39143-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="39143-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="39143-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="39143-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="39143-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="39143-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="39143-121">skos:prefLabel</span></span>|
|<span data-ttu-id="39143-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="39143-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="39143-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="39143-123">skos:prefLabel</span></span>|
|<span data-ttu-id="39143-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="39143-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="39143-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="39143-125">skos:prefLabel</span></span>|
|<span data-ttu-id="39143-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="39143-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="39143-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="39143-127">skos:altLabel</span></span>|
|<span data-ttu-id="39143-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="39143-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="39143-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="39143-129">skos:definition</span></span>|
|<span data-ttu-id="39143-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="39143-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="39143-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="39143-131">skos:broader</span></span>|
|<span data-ttu-id="39143-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="39143-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="39143-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="39143-133">skos:narrower</span></span>|

<span data-ttu-id="39143-134">A tabela a seguir mostra as entidades do vocabulário de taxonomia do SharePoint derivado de [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="39143-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="39143-135">Vocabulário de taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="39143-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="39143-136">Derivado de OWL</span><span class="sxs-lookup"><span data-stu-id="39143-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="39143-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="39143-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="39143-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="39143-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="39143-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="39143-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="39143-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="39143-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="39143-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="39143-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="39143-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="39143-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="39143-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="39143-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="39143-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="39143-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="39143-145">Vocabulário de taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="39143-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="39143-146">Uma taxonomia é um sistema formal de classificação.</span><span class="sxs-lookup"><span data-stu-id="39143-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="39143-147">Uma taxonomia agrupa as palavras, rótulos e termos que descrevem algo, e depois organiza os grupos em uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="39143-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="39143-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="39143-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="39143-149">Representa um Termo ou Palavra-chave em uma hierarquia de metadados gerenciados.</span><span class="sxs-lookup"><span data-stu-id="39143-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="39143-150">Um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) é a unidade atômica de um [Repositório de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39143-150">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="39143-151">Cada [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) pertence a um [Conjunto de Termos ](/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertence a um [Grupo de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="39143-151">Each [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="39143-152">A sintaxe para definir um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="39143-152">The syntax to define a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="39143-153">Um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) existe obrigatoriamente dentro de um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-153">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="39143-154">DefaultLabel é o nome do [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) como aparece na representação visual.</span><span class="sxs-lookup"><span data-stu-id="39143-154">DefaultLabel is the name of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="39143-155">Os campos obrigatórios para a definição de um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) incluem:</span><span class="sxs-lookup"><span data-stu-id="39143-155">The required fields for defining a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="39143-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="39143-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="39143-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="39143-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="39143-158">Um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) pode:</span><span class="sxs-lookup"><span data-stu-id="39143-158">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="39143-159">Estar hierarquicamente relacionado a outro [Termo ](/dotnet/api/microsoft.sharepoint.taxonomy.term), desde que os [Termos](/dotnet/api/microsoft.sharepoint.taxonomy.term) pertençam ao mesmo [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-159">Be hierarchically related to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="39143-160">Ter vários [Termos](/dotnet/api/microsoft.sharepoint.taxonomy.term) filhos, mas somente um único [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) pai.</span><span class="sxs-lookup"><span data-stu-id="39143-160">Have multiple child [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="39143-161">Não ter um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) pai definido, se o topLevelTermOf for um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-161">Not have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="39143-162">Tenha um defaultLabel, por idioma de trabalho na [Loja de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="39143-162">Have one defaultLabel, per [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="39143-163">Não existe se não contém um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) pai, nem se o topLevelTermOf for um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-163">Not exist if it neither contains a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="39143-164">Ter apenas um rótulo padrão único no mesmo nível hierárquico.</span><span class="sxs-lookup"><span data-stu-id="39143-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="39143-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="39143-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="39143-166">Representa uma hierarquia ou um conjunto horizontal de objetos de Termo conhecido como "Conjunto de Termos".</span><span class="sxs-lookup"><span data-stu-id="39143-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="39143-167">Como o nome sugere, Conjunto de Termos é um conjunto de [Termos](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="39143-167">As the name suggests, TermSet is a set of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="39143-168">Um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) em uma [Loja de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) deve pertencer a um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-168">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="39143-169">Nenhum [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) pode existir independentemente.</span><span class="sxs-lookup"><span data-stu-id="39143-169">No [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="39143-170">A sintaxe para definir um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:</span><span class="sxs-lookup"><span data-stu-id="39143-170">The syntax to define a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="39143-171">[Conjuntos de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset) são logicamente agrupados em [Grupos de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="39143-171">[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="39143-172">O campo necessário para definir um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:</span><span class="sxs-lookup"><span data-stu-id="39143-172">The required field for defining a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="39143-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="39143-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="39143-174">No caso do termSetName fornecido não ser exclusivo no [Grupo de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.group), o SharePoint anexa um número no final do nome para manter a exclusividade do termSetName (s).</span><span class="sxs-lookup"><span data-stu-id="39143-174">In the case of the termSetName provided is not unique within the [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="39143-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="39143-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="39143-176">O SharePoint usa essa propriedade para mapear o primeiro [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) no [ Conjunto de Termos ](/dotnet/api/microsoft.sharepoint.taxonomy.termset), que é o ponto de entrada para a hierarquia de [Termos](/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-176">SharePoint uses this property to map the top most [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="39143-177">Esta é uma relação inversa com a taxonomia sharepoint-taxonomy:topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="39143-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="39143-178">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="39143-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="39143-179">Você não pode definir o [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior de um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) pai.</span><span class="sxs-lookup"><span data-stu-id="39143-179">You cannot define the top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="39143-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="39143-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="39143-181">Sharepoint-taxonomy:topLevelTermOf é o inverso de sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="39143-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="39143-182">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="39143-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="39143-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="39143-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="39143-184">Utilize isto para mapear um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-184">Use this to map a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="39143-185">Um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) só pode existir em um único [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-185">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="39143-186">O SharePoint requer esta propriedade quando [definir um termo](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="39143-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="39143-187">Rótulos necessários</span><span class="sxs-lookup"><span data-stu-id="39143-187">Required labels</span></span>

<span data-ttu-id="39143-188">Sua organização pode desejar fazer um planejamento cuidadoso antes de começar a usar metadados gerenciados.</span><span class="sxs-lookup"><span data-stu-id="39143-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="39143-189">A quantia de planejamento que você deve fazer depende de quão formal é sua taxonomia.</span><span class="sxs-lookup"><span data-stu-id="39143-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="39143-190">Depende também de quanto controle você quer impor sobre os metadados.</span><span class="sxs-lookup"><span data-stu-id="39143-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="39143-191">Para cada nível da hierarquia, você precisa configurar os rótulos necessários para um Term ou TermSet.</span><span class="sxs-lookup"><span data-stu-id="39143-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="39143-192">Um termo pode ter um ou mais rótulos no idioma padrão e zero ou mais rótulos no idioma não padrão.</span><span class="sxs-lookup"><span data-stu-id="39143-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="39143-193">Se o termo tiver rótulos em um idioma, um dos rótulos deverá ser o padrão.</span><span class="sxs-lookup"><span data-stu-id="39143-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="39143-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="39143-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="39143-195">Utilize este rótulo léxico padrão para um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) que é um parâmetro obrigatório para um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="39143-195">Use this default lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="39143-196">Utilize para representar visualmente o [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="39143-196">Use to visually representing the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="39143-197">A sintaxe para definir o defaultLabel é:</span><span class="sxs-lookup"><span data-stu-id="39143-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="39143-198">O defaultLabel contém duas partes - a cadeia de caracteres e a marca de idioma.</span><span class="sxs-lookup"><span data-stu-id="39143-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="39143-199">O idioma deve ser um dos idiomas de trabalho do [Loja de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="39143-199">The language must be one of the [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="39143-200">O defaultLabel deve ser único para todos os [Termo ](/dotnet/api/microsoft.sharepoint.taxonomy.term) no mesmo [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset), no mesmo nível hierárquico.</span><span class="sxs-lookup"><span data-stu-id="39143-200">The defaultLabel must be unique for all [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="39143-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="39143-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="39143-202">Obtém e define o nome do objeto no Conjunto de Termos atual.</span><span class="sxs-lookup"><span data-stu-id="39143-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="39143-203">Este é o rótulo léxico para um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset), em um idioma de trabalho da [Loja de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="39143-203">This the lexical label for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="39143-204">Este é um parâmetro necessário para um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-204">This is a required parameter for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="39143-205">Utilize para representar visualmente um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-205">Use to visually representing a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="39143-206">A sintaxe para definir um termSetName é:</span><span class="sxs-lookup"><span data-stu-id="39143-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="39143-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="39143-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="39143-208">Obtém e define o nome da propriedade para o objeto Conjunto de Termos atual.</span><span class="sxs-lookup"><span data-stu-id="39143-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="39143-209">Este é o rótulo léxico para uma taxonomia do sharepoint: SharedCustomPropertyForTerm, taxonomia do sharepoint: LocalCustomPropertyForTerm e taxonomia do sharepoint: CustomPropertyForTermSet em um idioma de trabalho da [Loja de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="39143-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="39143-210">A sharepoint-taxonomy:propertyName é tratada como a chave da CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="39143-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="39143-211">A sintaxe para definir uma propetyName é:</span><span class="sxs-lookup"><span data-stu-id="39143-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="39143-212">Rótulo opcionais</span><span class="sxs-lookup"><span data-stu-id="39143-212">Optional labels</span></span>

<span data-ttu-id="39143-213">Você também pode adicionar rótulos opcionais à sua taxonomia.</span><span class="sxs-lookup"><span data-stu-id="39143-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="39143-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="39143-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="39143-215">Este é o rótulo léxico alternativo para um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="39143-215">This is the alternate lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="39143-216">A sintaxe para definir um otherLabel é:</span><span class="sxs-lookup"><span data-stu-id="39143-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="39143-217">Relações semânticas</span><span class="sxs-lookup"><span data-stu-id="39143-217">Semantic relationships</span></span>

<span data-ttu-id="39143-218">As taxonomias têm relacionamento associativo hierárquico e, às vezes, simples de "termo relacionado", mas algumas têm "relacionamentos semânticos" ou relacionamentos personalizados.</span><span class="sxs-lookup"><span data-stu-id="39143-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="39143-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="39143-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="39143-220">Esta hierarquia relaciona um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) a outro [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="39143-220">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="39143-221">Um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) pode ser um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior em um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset), mas caso não seja, este deve ter um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) pai.</span><span class="sxs-lookup"><span data-stu-id="39143-221">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="39143-222">A sintaxe para definir um termo pai é:</span><span class="sxs-lookup"><span data-stu-id="39143-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="39143-223">Isso significa que o TermA é o pai e TermA é o filho.</span><span class="sxs-lookup"><span data-stu-id="39143-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="39143-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="39143-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="39143-225">O objeto contém uma ou mais instâncias de Conjunto de Termos filho, que podem ser acessadas por meio da propriedade de Conjunto de Termos.</span><span class="sxs-lookup"><span data-stu-id="39143-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="39143-226">Esta classe também fornece métodos para criar novos objetos nos Conjunto de Termos filhos.</span><span class="sxs-lookup"><span data-stu-id="39143-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="39143-227">Permissões para editar instâncias de Termo filho e Conjunto de Termos são especificadas no grupo.</span><span class="sxs-lookup"><span data-stu-id="39143-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="39143-228">Esta hierarquia relaciona um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) a outro [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="39143-228">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="39143-229">A sintaxe para definir uma termo filho é:</span><span class="sxs-lookup"><span data-stu-id="39143-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="39143-230">Isso significa que o TermA é o pai e TermA é o filho.</span><span class="sxs-lookup"><span data-stu-id="39143-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="39143-231">Notas de documentação</span><span class="sxs-lookup"><span data-stu-id="39143-231">Documentation notes</span></span>

<span data-ttu-id="39143-232">Esta seção discute a taxonomia detalhada no namespace Microsoft.SharePoint.Taxonomy.</span><span class="sxs-lookup"><span data-stu-id="39143-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="39143-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="39143-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="39143-234">Esta é uma explicação detalhada de qualquer entidade de vocabulário de [ taxonomia do SharePoint ](/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="39143-234">This is a detailed explanation of any [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="39143-235">A sintaxe para acrescentar uma descrição é:</span><span class="sxs-lookup"><span data-stu-id="39143-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="39143-236">Propriedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="39143-236">Custom properties</span></span>

<span data-ttu-id="39143-237">Obtém a coleção de objetos de propriedade personalizada para o Termo do objeto atual do dicionário para somente leitura.</span><span class="sxs-lookup"><span data-stu-id="39143-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="39143-238">Propriedades personalizadas são pares de valores-chave que podem ser definidos para um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset), para complementar a descrição do [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="39143-238">Custom Properties are key-values pairs that can be defined for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="39143-239">O SharePoint especifica a chave da propriedade personalizada com a ajuda do propertyName.</span><span class="sxs-lookup"><span data-stu-id="39143-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="39143-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="39143-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="39143-241">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="39143-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="39143-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="39143-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="39143-243">Se a propriedade personalizada para um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) precisar ser carregada junto com o [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutilizar o [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, então você deve defini-lo em SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="39143-243">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="39143-244">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="39143-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="39143-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="39143-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="39143-246">Se a propriedade personalizada para um [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) não precisa ser carregada junto com o [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutiliza o [Termo](/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, então você precisa defini-lo em LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="39143-246">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="39143-247">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="39143-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="39143-248">Propriedades dos dados</span><span class="sxs-lookup"><span data-stu-id="39143-248">Data properties</span></span>

<span data-ttu-id="39143-249">Em cada nível da hierarquia, você pode configurar propriedades de dados específicas para um Termo ou Conjunto de Termos.</span><span class="sxs-lookup"><span data-stu-id="39143-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="39143-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="39143-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="39143-251">Utilize para especificar se um [Termo ](/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [Conjunto de Termos](/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponível nas Listas e Bibliotecas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39143-251">Use this to specify if a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="39143-252">A sintaxe para isto é:</span><span class="sxs-lookup"><span data-stu-id="39143-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="39143-253">Domínio e alcance</span><span class="sxs-lookup"><span data-stu-id="39143-253">Domain and range</span></span>

<span data-ttu-id="39143-254">A tabela a seguir descreve o domínio e a variedade do vocabulário da taxonomia do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39143-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="39143-255">Verbos/predicados</span><span class="sxs-lookup"><span data-stu-id="39143-255">Predicates/verb</span></span>|<span data-ttu-id="39143-256">Significado</span><span class="sxs-lookup"><span data-stu-id="39143-256">Meaning</span></span>|<span data-ttu-id="39143-257">Domínio</span><span class="sxs-lookup"><span data-stu-id="39143-257">Domain</span></span>|<span data-ttu-id="39143-258">Intervalo</span><span class="sxs-lookup"><span data-stu-id="39143-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="39143-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="39143-259">inTermSet</span></span>|<span data-ttu-id="39143-260">No Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="39143-260">In term set</span></span>|<span data-ttu-id="39143-261">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-261">Term</span></span>|<span data-ttu-id="39143-262">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="39143-262">Term Set</span></span>|
<span data-ttu-id="39143-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="39143-263">inTermGroup</span></span>|<span data-ttu-id="39143-264">No grupo de termos</span><span class="sxs-lookup"><span data-stu-id="39143-264">In term group</span></span>|<span data-ttu-id="39143-265">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="39143-265">TermSet</span></span>|<span data-ttu-id="39143-266">Grupo de Termos</span><span class="sxs-lookup"><span data-stu-id="39143-266">TermGroup</span></span>|
<span data-ttu-id="39143-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="39143-267">topLevelTermOf</span></span>|<span data-ttu-id="39143-268">É o Termo de Nível Superior do</span><span class="sxs-lookup"><span data-stu-id="39143-268">Is Top Level Term Of</span></span>|<span data-ttu-id="39143-269">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-269">Term</span></span>|<span data-ttu-id="39143-270">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="39143-270">TermSet</span></span>|
<span data-ttu-id="39143-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="39143-271">hasTopLevelTerm</span></span>|<span data-ttu-id="39143-272">Tem um termo de nível superior</span><span class="sxs-lookup"><span data-stu-id="39143-272">Has top level term</span></span>|<span data-ttu-id="39143-273">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="39143-273">Term Set</span></span>|<span data-ttu-id="39143-274">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-274">Term</span></span>|
<span data-ttu-id="39143-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="39143-275">termSetName</span></span>|<span data-ttu-id="39143-276">O Conjunto de termos tem Nome</span><span class="sxs-lookup"><span data-stu-id="39143-276">Term set has Name</span></span>|<span data-ttu-id="39143-277">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-277">Term</span></span>|<span data-ttu-id="39143-278">Literalmente simples</span><span class="sxs-lookup"><span data-stu-id="39143-278">Plain literal</span></span>|
<span data-ttu-id="39143-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="39143-279">defaultLabel</span></span>|<span data-ttu-id="39143-280">O termo tem rótulo padrão</span><span class="sxs-lookup"><span data-stu-id="39143-280">Term has default label</span></span>|<span data-ttu-id="39143-281">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-281">Term</span></span>|<span data-ttu-id="39143-282">Literalmente simples</span><span class="sxs-lookup"><span data-stu-id="39143-282">Plain literal</span></span>|
<span data-ttu-id="39143-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="39143-283">otherLabel</span></span>|<span data-ttu-id="39143-284">O termo tem outro rótulo</span><span class="sxs-lookup"><span data-stu-id="39143-284">Term has other label</span></span>|<span data-ttu-id="39143-285">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-285">Term</span></span>|<span data-ttu-id="39143-286">Literalmente simples</span><span class="sxs-lookup"><span data-stu-id="39143-286">Plain literal</span></span>|
<span data-ttu-id="39143-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="39143-287">propertyName</span></span>|<span data-ttu-id="39143-288">Possui Rótulo de Propriedade</span><span class="sxs-lookup"><span data-stu-id="39143-288">Has Property Label</span></span>|<span data-ttu-id="39143-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="39143-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="39143-290">Booleano, String, Inteiro, Decimal, Duplo</span><span class="sxs-lookup"><span data-stu-id="39143-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="39143-291">descrição</span><span class="sxs-lookup"><span data-stu-id="39143-291">description</span></span>|<span data-ttu-id="39143-292">Tem Descrição</span><span class="sxs-lookup"><span data-stu-id="39143-292">Has Description</span></span>|<span data-ttu-id="39143-293">Tudo</span><span class="sxs-lookup"><span data-stu-id="39143-293">All</span></span>|<span data-ttu-id="39143-294">Literalmente simples</span><span class="sxs-lookup"><span data-stu-id="39143-294">Plain literal</span></span>|
|<span data-ttu-id="39143-295">pai</span><span class="sxs-lookup"><span data-stu-id="39143-295">parent</span></span>|<span data-ttu-id="39143-296">Tem pai</span><span class="sxs-lookup"><span data-stu-id="39143-296">Has parent</span></span>|<span data-ttu-id="39143-297">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-297">Term</span></span>|<span data-ttu-id="39143-298">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-298">Term</span></span>|
|<span data-ttu-id="39143-299">filho</span><span class="sxs-lookup"><span data-stu-id="39143-299">child</span></span>|<span data-ttu-id="39143-300">Tem filho</span><span class="sxs-lookup"><span data-stu-id="39143-300">Has Child</span></span>|<span data-ttu-id="39143-301">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-301">Term</span></span>|<span data-ttu-id="39143-302">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-302">Term</span></span>|
|<span data-ttu-id="39143-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="39143-303">isAvailableForTagging</span></span>|<span data-ttu-id="39143-304">Está disponível para marcação</span><span class="sxs-lookup"><span data-stu-id="39143-304">Is available for tagging</span></span>|<span data-ttu-id="39143-305">Termo, Conjunto de termos</span><span class="sxs-lookup"><span data-stu-id="39143-305">Term, Term Set</span></span>|<span data-ttu-id="39143-306">Booleano</span><span class="sxs-lookup"><span data-stu-id="39143-306">Boolean</span></span>|
|<span data-ttu-id="39143-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="39143-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="39143-308">Possui propriedade personalizada compartilhada</span><span class="sxs-lookup"><span data-stu-id="39143-308">Has shared custom property</span></span>|<span data-ttu-id="39143-309">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-309">Term</span></span>|<span data-ttu-id="39143-310">Booleano, string, Inteiro, Decimal, Duplo</span><span class="sxs-lookup"><span data-stu-id="39143-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="39143-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="39143-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="39143-312">Possui propriedade local personalizada</span><span class="sxs-lookup"><span data-stu-id="39143-312">Has local custom property</span></span>|<span data-ttu-id="39143-313">Termo</span><span class="sxs-lookup"><span data-stu-id="39143-313">Term</span></span>|<span data-ttu-id="39143-314">Booleano, String, Inteiro, Decimal, Duplo</span><span class="sxs-lookup"><span data-stu-id="39143-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="39143-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="39143-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="39143-316">Possui propriedade personalizada</span><span class="sxs-lookup"><span data-stu-id="39143-316">Has Custom Property</span></span>|<span data-ttu-id="39143-317">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="39143-317">TermSet</span></span>|<span data-ttu-id="39143-318">Booleano, String, Inteiro, Decimal, Duplo</span><span class="sxs-lookup"><span data-stu-id="39143-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="39143-319">Cenários válidos de [SKOS](https://www.w3.org/TR/skos-primer/) que a [taxonomia do SharePoint](/dotnet/api/microsoft.sharepoint.taxonomy) não permite:</span><span class="sxs-lookup"><span data-stu-id="39143-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="39143-320">Redundância hierárquica - Um conceito do [SKOS](https://www.w3.org/TR/skos-primer/) pode ser anexado a vários conceitos mais amplos ao mesmo tempo, mas uma sharepoint-taxonomy:Term pode ter apenas uma sharepoint-taxonomy:parent, portanto, a dependência cíclica de termos também não é permitida.</span><span class="sxs-lookup"><span data-stu-id="39143-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="39143-321">Termos órfãos não são permitidos na taxonomia do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39143-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="39143-322">Cada sharepoint-taxonomy:Term deve ter uma sharepoint-taxonomy:parent ou deve ser um sharepoint-taxonomy:topLevelTermOf um Conjunto de Termos.</span><span class="sxs-lookup"><span data-stu-id="39143-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="39143-323">A taxonomia do SharePoint não oferece suporte a relações associativas.</span><span class="sxs-lookup"><span data-stu-id="39143-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="39143-324">A taxonomia do SharePoint permite apenas 2 tipos de relações hierárquicas – sharepoint-taxonomy:parent e sharepoint-Taxonomy:child.</span><span class="sxs-lookup"><span data-stu-id="39143-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="39143-325">Ao contrário do [SKOS](https://www.w3.org/TR/skos-primer/), a relação hierárquica no vocabulário de taxonomia do SharePoint, só pode ser estabelecida com Termos dentro do mesmo Conjunto de Termos.</span><span class="sxs-lookup"><span data-stu-id="39143-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="39143-326">Confira também</span><span class="sxs-lookup"><span data-stu-id="39143-326">See also</span></span>

[<span data-ttu-id="39143-327">Importar um conjunto de termos usando um formato com base em SKOS</span><span class="sxs-lookup"><span data-stu-id="39143-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)