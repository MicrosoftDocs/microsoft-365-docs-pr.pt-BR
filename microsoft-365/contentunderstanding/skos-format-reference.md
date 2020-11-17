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
ms.openlocfilehash: 90c20ddb440e216941a5ea06f1aa815cb80102a9
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087268"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="d08a8-103">Formato SKOS como referência para a taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d08a8-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="d08a8-104">Este artigo inclui o vocabulário RDF utilizado para representar a [Taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) e é baseado no [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="d08a8-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="d08a8-105">Para a serialização desta sintaxe RDF, utilize o RDF [TARTARUGA](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="d08a8-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="d08a8-106">A tabela seguinte exibe os equivalentes ao [SKOS](https://www.w3.org/TR/skos-primer/) para o vocabulário [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="d08a8-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="d08a8-107">O SharePoint não suporta valores [SKOS](https://www.w3.org/TR/skos-primer/) que não tenham equivalente em taxonomia do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d08a8-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="d08a8-108">Taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d08a8-108">SharePoint taxonomy</span></span>|<span data-ttu-id="d08a8-109">Equivalente ao SKOS</span><span class="sxs-lookup"><span data-stu-id="d08a8-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="d08a8-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="d08a8-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="d08a8-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="d08a8-111">skos:Concept</span></span>|
|<span data-ttu-id="d08a8-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="d08a8-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="d08a8-113">skos:ConceitoScheme</span><span class="sxs-lookup"><span data-stu-id="d08a8-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="d08a8-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="d08a8-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="d08a8-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="d08a8-115">skos:inScheme</span></span>|
|<span data-ttu-id="d08a8-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="d08a8-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="d08a8-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="d08a8-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="d08a8-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="d08a8-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="d08a8-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="d08a8-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="d08a8-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="d08a8-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="d08a8-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="d08a8-121">skos:prefLabel</span></span>|
|<span data-ttu-id="d08a8-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="d08a8-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="d08a8-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="d08a8-123">skos:prefLabel</span></span>|
|<span data-ttu-id="d08a8-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="d08a8-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="d08a8-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="d08a8-125">skos:prefLabel</span></span>|
|<span data-ttu-id="d08a8-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="d08a8-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="d08a8-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="d08a8-127">skos:altLabel</span></span>|
|<span data-ttu-id="d08a8-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="d08a8-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="d08a8-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="d08a8-129">skos:definition</span></span>|
|<span data-ttu-id="d08a8-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="d08a8-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="d08a8-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="d08a8-131">skos:broader</span></span>|
|<span data-ttu-id="d08a8-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="d08a8-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="d08a8-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="d08a8-133">skos:narrower</span></span>|

<span data-ttu-id="d08a8-134">A tabela a seguir mostra as entidades do vocabulário de taxonomia do SharePoint derivado de [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="d08a8-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="d08a8-135">Vocabulário de taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d08a8-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="d08a8-136">Derivado de OWL</span><span class="sxs-lookup"><span data-stu-id="d08a8-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="d08a8-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="d08a8-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="d08a8-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="d08a8-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="d08a8-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="d08a8-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="d08a8-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="d08a8-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="d08a8-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="d08a8-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="d08a8-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="d08a8-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="d08a8-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="d08a8-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="d08a8-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="d08a8-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="d08a8-145">Vocabulário de taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d08a8-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="d08a8-146">Uma taxonomia é um sistema formal de classificação.</span><span class="sxs-lookup"><span data-stu-id="d08a8-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="d08a8-147">Uma taxonomia agrupa as palavras, rótulos e termos que descrevem algo, e depois organiza os grupos em uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="d08a8-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="d08a8-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="d08a8-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="d08a8-149">Representa um Termo ou Palavra-chave em uma hierarquia de metadados gerenciados.</span><span class="sxs-lookup"><span data-stu-id="d08a8-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="d08a8-150">Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) é a unidade atômica de um [Repositório de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d08a8-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="d08a8-151">Cada [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertence a um [Conjunto de Termos ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertence a um [Grupo de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="d08a8-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="d08a8-152">A sintaxe para definir um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="d08a8-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="d08a8-153">Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) existe obrigatoriamente dentro de um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="d08a8-154">DefaultLabel é o nome do [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) como aparece na representação visual.</span><span class="sxs-lookup"><span data-stu-id="d08a8-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="d08a8-155">Os campos obrigatórios para a definição de um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) incluem:</span><span class="sxs-lookup"><span data-stu-id="d08a8-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="d08a8-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="d08a8-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="d08a8-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="d08a8-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="d08a8-158">Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode:</span><span class="sxs-lookup"><span data-stu-id="d08a8-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="d08a8-159">Estar hierarquicamente relacionado a outro [Termo ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), desde que os [Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertençam ao mesmo [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="d08a8-160">Ter vários [Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) filhos, mas somente um único [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai.</span><span class="sxs-lookup"><span data-stu-id="d08a8-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="d08a8-161">Não ter um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai definido, se o topLevelTermOf for um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="d08a8-162">Tenha um defaultLabel, por idioma de trabalho na [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="d08a8-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="d08a8-163">Não existe se não contém um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai, nem se o topLevelTermOf for um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="d08a8-164">Ter apenas um rótulo padrão único no mesmo nível hierárquico.</span><span class="sxs-lookup"><span data-stu-id="d08a8-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="d08a8-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="d08a8-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="d08a8-166">Representa uma hierarquia ou um conjunto horizontal de objetos de Termo conhecido como "Conjunto de Termos".</span><span class="sxs-lookup"><span data-stu-id="d08a8-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="d08a8-167">Como o nome sugere, Conjunto de Termos é um conjunto de [Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="d08a8-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="d08a8-168">Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em uma [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) deve pertencer a um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="d08a8-169">Nenhum [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode existir independentemente.</span><span class="sxs-lookup"><span data-stu-id="d08a8-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="d08a8-170">A sintaxe para definir um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="d08a8-171">[Conjuntos de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) são logicamente agrupados em [Grupos de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="d08a8-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="d08a8-172">O campo necessário para definir um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="d08a8-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="d08a8-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="d08a8-174">No caso do termSetName fornecido não ser exclusivo no [Grupo de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), o SharePoint anexa um número no final do nome para manter a exclusividade do termSetName (s).</span><span class="sxs-lookup"><span data-stu-id="d08a8-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="d08a8-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="d08a8-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="d08a8-176">O SharePoint usa essa propriedade para mapear o primeiro [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) no [ Conjunto de Termos ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), que é o ponto de entrada para a hierarquia de [Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="d08a8-177">Esta é uma relação inversa com a taxonomia sharepoint-taxonomy:topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="d08a8-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="d08a8-178">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="d08a8-179">Você não pode definir o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior de um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai.</span><span class="sxs-lookup"><span data-stu-id="d08a8-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="d08a8-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="d08a8-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="d08a8-181">Sharepoint-taxonomy:topLevelTermOf é o inverso de sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="d08a8-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="d08a8-182">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="d08a8-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="d08a8-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="d08a8-184">Utilize isto para mapear um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="d08a8-185">Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) só pode existir em um único [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="d08a8-186">O SharePoint requer esta propriedade quando [definir um termo](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="d08a8-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="d08a8-187">Rótulos necessários</span><span class="sxs-lookup"><span data-stu-id="d08a8-187">Required labels</span></span>

<span data-ttu-id="d08a8-188">Sua organização pode desejar fazer um planejamento cuidadoso antes de começar a usar metadados gerenciados.</span><span class="sxs-lookup"><span data-stu-id="d08a8-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="d08a8-189">A quantia de planejamento que você deve fazer depende de quão formal é sua taxonomia.</span><span class="sxs-lookup"><span data-stu-id="d08a8-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="d08a8-190">Depende também de quanto controle você quer impor sobre os metadados.</span><span class="sxs-lookup"><span data-stu-id="d08a8-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="d08a8-191">Para cada nível da hierarquia, você precisa configurar os rótulos necessários para um Term ou TermSet.</span><span class="sxs-lookup"><span data-stu-id="d08a8-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="d08a8-192">Um termo pode ter um ou mais rótulos no idioma padrão e zero ou mais rótulos no idioma não padrão.</span><span class="sxs-lookup"><span data-stu-id="d08a8-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="d08a8-193">Se o termo tiver rótulos em um idioma, um dos rótulos deverá ser o padrão.</span><span class="sxs-lookup"><span data-stu-id="d08a8-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="d08a8-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="d08a8-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="d08a8-195">Utilize este rótulo léxico padrão para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que é um parâmetro obrigatório para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="d08a8-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="d08a8-196">Utilize para representar visualmente o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="d08a8-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="d08a8-197">A sintaxe para definir o defaultLabel é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="d08a8-198">O defaultLabel contém duas partes - a cadeia de caracteres e a marca de idioma.</span><span class="sxs-lookup"><span data-stu-id="d08a8-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="d08a8-199">O idioma deve ser um dos idiomas de trabalho do [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="d08a8-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="d08a8-200">O defaultLabel deve ser único para todos os [Termo ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) no mesmo [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), no mesmo nível hierárquico.</span><span class="sxs-lookup"><span data-stu-id="d08a8-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="d08a8-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="d08a8-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="d08a8-202">Obtém e define o nome do objeto no Conjunto de Termos atual.</span><span class="sxs-lookup"><span data-stu-id="d08a8-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="d08a8-203">Este é o rótulo léxico para um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), em um idioma de trabalho da [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="d08a8-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="d08a8-204">Este é um parâmetro necessário para um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="d08a8-205">Utilize para representar visualmente um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="d08a8-206">A sintaxe para definir um termSetName é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="d08a8-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="d08a8-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="d08a8-208">Obtém e define o nome da propriedade para o objeto Conjunto de Termos atual.</span><span class="sxs-lookup"><span data-stu-id="d08a8-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="d08a8-209">Este é o rótulo léxico para uma taxonomia do sharepoint: SharedCustomPropertyForTerm, taxonomia do sharepoint: LocalCustomPropertyForTerm e taxonomia do sharepoint: CustomPropertyForTermSet em um idioma de trabalho da [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="d08a8-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="d08a8-210">A sharepoint-taxonomy:propertyName é tratada como a chave da CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="d08a8-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="d08a8-211">A sintaxe para definir uma propetyName é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="d08a8-212">Rótulo opcionais</span><span class="sxs-lookup"><span data-stu-id="d08a8-212">Optional labels</span></span>

<span data-ttu-id="d08a8-213">Você também pode adicionar rótulos opcionais à sua taxonomia.</span><span class="sxs-lookup"><span data-stu-id="d08a8-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="d08a8-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="d08a8-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="d08a8-215">Este é o rótulo léxico alternativo para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="d08a8-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="d08a8-216">A sintaxe para definir um otherLabel é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="d08a8-217">Relações semânticas</span><span class="sxs-lookup"><span data-stu-id="d08a8-217">Semantic relationships</span></span>

<span data-ttu-id="d08a8-218">As taxonomias têm relacionamento associativo hierárquico e, às vezes, simples de "termo relacionado", mas algumas têm "relacionamentos semânticos" ou relacionamentos personalizados.</span><span class="sxs-lookup"><span data-stu-id="d08a8-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="d08a8-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="d08a8-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="d08a8-220">Esta hierarquia relaciona um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a outro [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="d08a8-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="d08a8-221">Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode ser um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior em um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), mas caso não seja, este deve ter um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai.</span><span class="sxs-lookup"><span data-stu-id="d08a8-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="d08a8-222">A sintaxe para definir um termo pai é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="d08a8-223">Isso significa que o TermA é o pai e TermA é o filho.</span><span class="sxs-lookup"><span data-stu-id="d08a8-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="d08a8-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="d08a8-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="d08a8-225">O objeto contém uma ou mais instâncias de Conjunto de Termos filho, que podem ser acessadas por meio da propriedade de Conjunto de Termos.</span><span class="sxs-lookup"><span data-stu-id="d08a8-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="d08a8-226">Esta classe também fornece métodos para criar novos objetos nos Conjunto de Termos filhos.</span><span class="sxs-lookup"><span data-stu-id="d08a8-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="d08a8-227">Permissões para editar instâncias de Termo filho e Conjunto de Termos são especificadas no grupo.</span><span class="sxs-lookup"><span data-stu-id="d08a8-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="d08a8-228">Esta hierarquia relaciona um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a outro [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="d08a8-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="d08a8-229">A sintaxe para definir uma termo filho é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="d08a8-230">Isso significa que o TermA é o pai e TermA é o filho.</span><span class="sxs-lookup"><span data-stu-id="d08a8-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="d08a8-231">Notas de documentação</span><span class="sxs-lookup"><span data-stu-id="d08a8-231">Documentation notes</span></span>

<span data-ttu-id="d08a8-232">Esta seção discute a taxonomia detalhada no namespace Microsoft.SharePoint.Taxonomy.</span><span class="sxs-lookup"><span data-stu-id="d08a8-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="d08a8-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="d08a8-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="d08a8-234">Esta é uma explicação detalhada de qualquer entidade de vocabulário de [ taxonomia do SharePoint ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="d08a8-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="d08a8-235">A sintaxe para acrescentar uma descrição é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="d08a8-236">Propriedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="d08a8-236">Custom properties</span></span>

<span data-ttu-id="d08a8-237">Obtém a coleção de objetos de propriedade personalizada para o Termo do objeto atual do dicionário para somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d08a8-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="d08a8-238">Propriedades personalizadas são pares de valores-chave que podem ser definidos para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), para complementar a descrição do [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="d08a8-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="d08a8-239">O SharePoint especifica a chave da propriedade personalizada com a ajuda do propertyName.</span><span class="sxs-lookup"><span data-stu-id="d08a8-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="d08a8-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="d08a8-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="d08a8-241">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="d08a8-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="d08a8-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="d08a8-243">Se a propriedade personalizada para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) precisar ser carregada junto com o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutilizar o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, então você deve defini-lo em SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="d08a8-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="d08a8-244">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="d08a8-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="d08a8-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="d08a8-246">Se a propriedade personalizada para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) não precisa ser carregada junto com o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutiliza o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, então você precisa defini-lo em LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="d08a8-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="d08a8-247">A sintaxe para definir isto é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="d08a8-248">Propriedades dos dados</span><span class="sxs-lookup"><span data-stu-id="d08a8-248">Data properties</span></span>

<span data-ttu-id="d08a8-249">Em cada nível da hierarquia, você pode configurar propriedades de dados específicas para um Termo ou Conjunto de Termos.</span><span class="sxs-lookup"><span data-stu-id="d08a8-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="d08a8-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="d08a8-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="d08a8-251">Utilize para especificar se um [Termo ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponível nas Listas e Bibliotecas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d08a8-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="d08a8-252">A sintaxe para isto é:</span><span class="sxs-lookup"><span data-stu-id="d08a8-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="d08a8-253">Domínio e alcance</span><span class="sxs-lookup"><span data-stu-id="d08a8-253">Domain and range</span></span>

<span data-ttu-id="d08a8-254">A tabela a seguir descreve o domínio e a variedade do vocabulário da taxonomia do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d08a8-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="d08a8-255">Verbos/predicados</span><span class="sxs-lookup"><span data-stu-id="d08a8-255">Predicates/verb</span></span>|<span data-ttu-id="d08a8-256">Significado</span><span class="sxs-lookup"><span data-stu-id="d08a8-256">Meaning</span></span>|<span data-ttu-id="d08a8-257">Domínio</span><span class="sxs-lookup"><span data-stu-id="d08a8-257">Domain</span></span>|<span data-ttu-id="d08a8-258">Intervalo</span><span class="sxs-lookup"><span data-stu-id="d08a8-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="d08a8-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="d08a8-259">inTermSet</span></span>|<span data-ttu-id="d08a8-260">No Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="d08a8-260">In term set</span></span>|<span data-ttu-id="d08a8-261">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-261">Term</span></span>|<span data-ttu-id="d08a8-262">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="d08a8-262">Term Set</span></span>|
<span data-ttu-id="d08a8-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="d08a8-263">inTermGroup</span></span>|<span data-ttu-id="d08a8-264">No grupo de termos</span><span class="sxs-lookup"><span data-stu-id="d08a8-264">In term group</span></span>|<span data-ttu-id="d08a8-265">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="d08a8-265">TermSet</span></span>|<span data-ttu-id="d08a8-266">Grupo de Termos</span><span class="sxs-lookup"><span data-stu-id="d08a8-266">TermGroup</span></span>|
<span data-ttu-id="d08a8-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="d08a8-267">topLevelTermOf</span></span>|<span data-ttu-id="d08a8-268">É o Termo de Nível Superior do</span><span class="sxs-lookup"><span data-stu-id="d08a8-268">Is Top Level Term Of</span></span>|<span data-ttu-id="d08a8-269">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-269">Term</span></span>|<span data-ttu-id="d08a8-270">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="d08a8-270">TermSet</span></span>|
<span data-ttu-id="d08a8-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="d08a8-271">hasTopLevelTerm</span></span>|<span data-ttu-id="d08a8-272">Tem um termo de nível superior</span><span class="sxs-lookup"><span data-stu-id="d08a8-272">Has top level term</span></span>|<span data-ttu-id="d08a8-273">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="d08a8-273">Term Set</span></span>|<span data-ttu-id="d08a8-274">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-274">Term</span></span>|
<span data-ttu-id="d08a8-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="d08a8-275">termSetName</span></span>|<span data-ttu-id="d08a8-276">O Conjunto de termos tem Nome</span><span class="sxs-lookup"><span data-stu-id="d08a8-276">Term set has Name</span></span>|<span data-ttu-id="d08a8-277">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-277">Term</span></span>|<span data-ttu-id="d08a8-278">Literalmente simples</span><span class="sxs-lookup"><span data-stu-id="d08a8-278">Plain literal</span></span>|
<span data-ttu-id="d08a8-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="d08a8-279">defaultLabel</span></span>|<span data-ttu-id="d08a8-280">O termo tem rótulo padrão</span><span class="sxs-lookup"><span data-stu-id="d08a8-280">Term has default label</span></span>|<span data-ttu-id="d08a8-281">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-281">Term</span></span>|<span data-ttu-id="d08a8-282">Literalmente simples</span><span class="sxs-lookup"><span data-stu-id="d08a8-282">Plain literal</span></span>|
<span data-ttu-id="d08a8-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="d08a8-283">otherLabel</span></span>|<span data-ttu-id="d08a8-284">O termo tem outro rótulo</span><span class="sxs-lookup"><span data-stu-id="d08a8-284">Term has other label</span></span>|<span data-ttu-id="d08a8-285">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-285">Term</span></span>|<span data-ttu-id="d08a8-286">Literalmente simples</span><span class="sxs-lookup"><span data-stu-id="d08a8-286">Plain literal</span></span>|
<span data-ttu-id="d08a8-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="d08a8-287">propertyName</span></span>|<span data-ttu-id="d08a8-288">Possui Rótulo de Propriedade</span><span class="sxs-lookup"><span data-stu-id="d08a8-288">Has Property Label</span></span>|<span data-ttu-id="d08a8-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="d08a8-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="d08a8-290">Booleano, String, Inteiro, Decimal, Duplo</span><span class="sxs-lookup"><span data-stu-id="d08a8-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="d08a8-291">descrição</span><span class="sxs-lookup"><span data-stu-id="d08a8-291">description</span></span>|<span data-ttu-id="d08a8-292">Tem Descrição</span><span class="sxs-lookup"><span data-stu-id="d08a8-292">Has Description</span></span>|<span data-ttu-id="d08a8-293">Tudo</span><span class="sxs-lookup"><span data-stu-id="d08a8-293">All</span></span>|<span data-ttu-id="d08a8-294">Literalmente simples</span><span class="sxs-lookup"><span data-stu-id="d08a8-294">Plain literal</span></span>|
|<span data-ttu-id="d08a8-295">pai</span><span class="sxs-lookup"><span data-stu-id="d08a8-295">parent</span></span>|<span data-ttu-id="d08a8-296">Tem pai</span><span class="sxs-lookup"><span data-stu-id="d08a8-296">Has parent</span></span>|<span data-ttu-id="d08a8-297">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-297">Term</span></span>|<span data-ttu-id="d08a8-298">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-298">Term</span></span>|
|<span data-ttu-id="d08a8-299">filho</span><span class="sxs-lookup"><span data-stu-id="d08a8-299">child</span></span>|<span data-ttu-id="d08a8-300">Tem filho</span><span class="sxs-lookup"><span data-stu-id="d08a8-300">Has Child</span></span>|<span data-ttu-id="d08a8-301">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-301">Term</span></span>|<span data-ttu-id="d08a8-302">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-302">Term</span></span>|
|<span data-ttu-id="d08a8-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="d08a8-303">isAvailableForTagging</span></span>|<span data-ttu-id="d08a8-304">Está disponível para marcação</span><span class="sxs-lookup"><span data-stu-id="d08a8-304">Is available for tagging</span></span>|<span data-ttu-id="d08a8-305">Termo, Conjunto de termos</span><span class="sxs-lookup"><span data-stu-id="d08a8-305">Term, Term Set</span></span>|<span data-ttu-id="d08a8-306">Booleano</span><span class="sxs-lookup"><span data-stu-id="d08a8-306">Boolean</span></span>|
|<span data-ttu-id="d08a8-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="d08a8-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="d08a8-308">Possui propriedade personalizada compartilhada</span><span class="sxs-lookup"><span data-stu-id="d08a8-308">Has shared custom property</span></span>|<span data-ttu-id="d08a8-309">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-309">Term</span></span>|<span data-ttu-id="d08a8-310">Booleano, string, Inteiro, Decimal, Duplo</span><span class="sxs-lookup"><span data-stu-id="d08a8-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="d08a8-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="d08a8-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="d08a8-312">Possui propriedade local personalizada</span><span class="sxs-lookup"><span data-stu-id="d08a8-312">Has local custom property</span></span>|<span data-ttu-id="d08a8-313">Termo</span><span class="sxs-lookup"><span data-stu-id="d08a8-313">Term</span></span>|<span data-ttu-id="d08a8-314">Booleano, String, Inteiro, Decimal, Duplo</span><span class="sxs-lookup"><span data-stu-id="d08a8-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="d08a8-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="d08a8-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="d08a8-316">Possui propriedade personalizada</span><span class="sxs-lookup"><span data-stu-id="d08a8-316">Has Custom Property</span></span>|<span data-ttu-id="d08a8-317">Conjunto de Termos</span><span class="sxs-lookup"><span data-stu-id="d08a8-317">TermSet</span></span>|<span data-ttu-id="d08a8-318">Booleano, String, Inteiro, Decimal, Duplo</span><span class="sxs-lookup"><span data-stu-id="d08a8-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="d08a8-319">Cenários válidos de [SKOS](https://www.w3.org/TR/skos-primer/) que a [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) não permite:</span><span class="sxs-lookup"><span data-stu-id="d08a8-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="d08a8-320">Redundância hierárquica - Um conceito do [SKOS](https://www.w3.org/TR/skos-primer/) pode ser anexado a vários conceitos mais amplos ao mesmo tempo, mas uma sharepoint-taxonomy:Term pode ter apenas uma sharepoint-taxonomy:parent, portanto, a dependência cíclica de termos também não é permitida.</span><span class="sxs-lookup"><span data-stu-id="d08a8-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="d08a8-321">Termos órfãos não são permitidos na taxonomia do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d08a8-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="d08a8-322">Cada sharepoint-taxonomy:Term deve ter uma sharepoint-taxonomy:parent ou deve ser um sharepoint-taxonomy:topLevelTermOf um Conjunto de Termos.</span><span class="sxs-lookup"><span data-stu-id="d08a8-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="d08a8-323">A taxonomia do SharePoint não oferece suporte a relações associativas.</span><span class="sxs-lookup"><span data-stu-id="d08a8-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="d08a8-324">A taxonomia do SharePoint permite apenas 2 tipos de relações hierárquicas – sharepoint-taxonomy:parent e sharepoint-Taxonomy:child.</span><span class="sxs-lookup"><span data-stu-id="d08a8-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="d08a8-325">Ao contrário do [SKOS](https://www.w3.org/TR/skos-primer/), a relação hierárquica no vocabulário de taxonomia do SharePoint, só pode ser estabelecida com Termos dentro do mesmo Conjunto de Termos.</span><span class="sxs-lookup"><span data-stu-id="d08a8-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="d08a8-326">Confira também</span><span class="sxs-lookup"><span data-stu-id="d08a8-326">See also</span></span>

[<span data-ttu-id="d08a8-327">Importar um conjunto de termos usando um formato com base em SKOS</span><span class="sxs-lookup"><span data-stu-id="d08a8-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

