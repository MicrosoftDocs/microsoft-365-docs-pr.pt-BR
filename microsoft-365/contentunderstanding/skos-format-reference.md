---
title: Referência de formato SKOS para a taxonomia do SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: Referência de formato SKOS para a taxonomia do SharePoint
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295725"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="3fac1-103">Referência de formato SKOS para a taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="3fac1-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="3fac1-104">Este artigo inclui o vocabulário RDF usado para representar a [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) e é baseado no [skos](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="3fac1-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="3fac1-105">Para a serialização dessa sintaxe RDF, use a [tartaruga](https://www.w3.org/TR/turtle/)RDF.</span><span class="sxs-lookup"><span data-stu-id="3fac1-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="3fac1-106">A tabela a seguir mostra os equivalentes do [skos](https://www.w3.org/TR/skos-primer/) para o vocabulário de [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) .</span><span class="sxs-lookup"><span data-stu-id="3fac1-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="3fac1-107">O SharePoint não oferece suporte a valores de [skos](https://www.w3.org/TR/skos-primer/) que não tenham nenhuma taxonomia do SharePoint equivalente.</span><span class="sxs-lookup"><span data-stu-id="3fac1-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="3fac1-108">Taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="3fac1-108">SharePoint taxonomy</span></span>|<span data-ttu-id="3fac1-109">Equivalente SKOS</span><span class="sxs-lookup"><span data-stu-id="3fac1-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="3fac1-110">SharePoint – taxonomia: termo</span><span class="sxs-lookup"><span data-stu-id="3fac1-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="3fac1-111">skos: conceito</span><span class="sxs-lookup"><span data-stu-id="3fac1-111">skos:Concept</span></span>|
|<span data-ttu-id="3fac1-112">SharePoint – taxonomia: Termset</span><span class="sxs-lookup"><span data-stu-id="3fac1-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="3fac1-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="3fac1-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="3fac1-114">SharePoint – taxonomia: intermset</span><span class="sxs-lookup"><span data-stu-id="3fac1-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="3fac1-115">skos: inesquema</span><span class="sxs-lookup"><span data-stu-id="3fac1-115">skos:inScheme</span></span>|
|<span data-ttu-id="3fac1-116">SharePoint – taxonomia: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="3fac1-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="3fac1-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="3fac1-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="3fac1-118">SharePoint – taxonomia: topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="3fac1-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="3fac1-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="3fac1-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="3fac1-120">SharePoint – taxonomia: defaultlabel</span><span class="sxs-lookup"><span data-stu-id="3fac1-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="3fac1-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="3fac1-121">skos:prefLabel</span></span>|
|<span data-ttu-id="3fac1-122">SharePoint – taxonomia: termSetName</span><span class="sxs-lookup"><span data-stu-id="3fac1-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="3fac1-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="3fac1-123">skos:prefLabel</span></span>|
|<span data-ttu-id="3fac1-124">SharePoint – taxonomia: propertyName</span><span class="sxs-lookup"><span data-stu-id="3fac1-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="3fac1-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="3fac1-125">skos:prefLabel</span></span>|
|<span data-ttu-id="3fac1-126">SharePoint – taxonomia: otherLabel</span><span class="sxs-lookup"><span data-stu-id="3fac1-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="3fac1-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="3fac1-127">skos:altLabel</span></span>|
|<span data-ttu-id="3fac1-128">SharePoint – taxonomia: Descrição</span><span class="sxs-lookup"><span data-stu-id="3fac1-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="3fac1-129">skos: definição</span><span class="sxs-lookup"><span data-stu-id="3fac1-129">skos:definition</span></span>|
|<span data-ttu-id="3fac1-130">SharePoint – taxonomia: pai</span><span class="sxs-lookup"><span data-stu-id="3fac1-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="3fac1-131">skos: mais amplo</span><span class="sxs-lookup"><span data-stu-id="3fac1-131">skos:broader</span></span>|
|<span data-ttu-id="3fac1-132">SharePoint – taxonomia: filho</span><span class="sxs-lookup"><span data-stu-id="3fac1-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="3fac1-133">skos: mais estreito</span><span class="sxs-lookup"><span data-stu-id="3fac1-133">skos:narrower</span></span>|

<span data-ttu-id="3fac1-134">A tabela a seguir exibe as entidades do vocabulário de taxonomia do SharePoint derivado de [Owl](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="3fac1-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="3fac1-135">Vocabulário de taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="3fac1-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="3fac1-136">Derivado de OWL</span><span class="sxs-lookup"><span data-stu-id="3fac1-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="3fac1-137">SharePoint – taxonomia: isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="3fac1-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="3fac1-138">Owl: datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="3fac1-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="3fac1-139">SharePoint – taxonomia: SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="3fac1-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="3fac1-140">Owl: Fieldobjeto</span><span class="sxs-lookup"><span data-stu-id="3fac1-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="3fac1-141">SharePoint – taxonomia: LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="3fac1-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="3fac1-142">Owl: Fieldobjeto</span><span class="sxs-lookup"><span data-stu-id="3fac1-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="3fac1-143">SharePoint – taxonomia: CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="3fac1-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="3fac1-144">Owl: Fieldobjeto</span><span class="sxs-lookup"><span data-stu-id="3fac1-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="3fac1-145">Vocabulário de taxonomia do SharePoint</span><span class="sxs-lookup"><span data-stu-id="3fac1-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="3fac1-146">Uma taxonomia é um sistema de classificação formal.</span><span class="sxs-lookup"><span data-stu-id="3fac1-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="3fac1-147">Uma taxonomia agrupa as palavras, rótulos e termos que descrevem algo e, em seguida, organiza os grupos em uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="3fac1-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="3fac1-148">**SharePoint – taxonomia: termo**</span><span class="sxs-lookup"><span data-stu-id="3fac1-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="3fac1-149">Representa um termo ou uma palavra-chave em uma hierarquia de metadados gerenciados.</span><span class="sxs-lookup"><span data-stu-id="3fac1-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="3fac1-150">Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) é a unidade atômica de um [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3fac1-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="3fac1-151">Cada [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertence a um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertence a um [termo.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)</span><span class="sxs-lookup"><span data-stu-id="3fac1-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="3fac1-152">A sintaxe para definir um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="3fac1-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="3fac1-153">Há um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily em um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="3fac1-154">Defaultlabel é o nome do [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) como ele aparece na representação visual.</span><span class="sxs-lookup"><span data-stu-id="3fac1-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="3fac1-155">Os campos obrigatórios para definir um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) incluem:</span><span class="sxs-lookup"><span data-stu-id="3fac1-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="3fac1-156">SharePoint – taxonomia: defaultlabel</span><span class="sxs-lookup"><span data-stu-id="3fac1-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="3fac1-157">SharePoint – taxonomia: intermset</span><span class="sxs-lookup"><span data-stu-id="3fac1-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="3fac1-158">Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode:</span><span class="sxs-lookup"><span data-stu-id="3fac1-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="3fac1-159">Ser hierarquicamente relacionadas a outro [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que é fornecido, os [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertencem ao mesmo [termoset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="3fac1-160">Ter vários [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)filhos, mas apenas um único [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)pai.</span><span class="sxs-lookup"><span data-stu-id="3fac1-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="3fac1-161">Não ter um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai definido, se for um TopLevelTermOf um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="3fac1-162">Ter um defaultlabel, por idioma de trabalho do [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="3fac1-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="3fac1-163">Não existir se não contiver um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)pai, nem o TopLevelTermOf um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="3fac1-164">Ter apenas um defaultlabel exclusivo no mesmo nível hierárquico.</span><span class="sxs-lookup"><span data-stu-id="3fac1-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="3fac1-165">**SharePoint – taxonomia: Termset**</span><span class="sxs-lookup"><span data-stu-id="3fac1-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="3fac1-166">Representa um conjunto hierárquico ou simples de objetos Term conhecidos como "Termset".</span><span class="sxs-lookup"><span data-stu-id="3fac1-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="3fac1-167">Como o nome sugere, Termset é um conjunto de [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="3fac1-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="3fac1-168">Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) deve pertencer a um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="3fac1-169">Nenhum [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode existir de forma independente.</span><span class="sxs-lookup"><span data-stu-id="3fac1-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="3fac1-170">A sintaxe para definir um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="3fac1-171">Os [TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) são agrupados logicamente no [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="3fac1-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="3fac1-172">O campo obrigatório para definir um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="3fac1-173">SharePoint – taxonomia: termSetName</span><span class="sxs-lookup"><span data-stu-id="3fac1-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="3fac1-174">No caso do termSetName fornecido não é exclusivo no @ @ @ [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint acrescenta um número ao final do nome para manter a exclusividade de termSetName (s)</span><span class="sxs-lookup"><span data-stu-id="3fac1-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="3fac1-175">**SharePoint – taxonomia: hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="3fac1-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="3fac1-176">O SharePoint usa essa propriedade para mapear a maior parte do [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) no [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), que é o ponto de entrada para a hierarquia de [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="3fac1-177">Esta é uma relação inversa à taxonomia do SharePoint: topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="3fac1-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="3fac1-178">A sintaxe a ser definida é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="3fac1-179">Não é possível definir o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior de um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)pai.</span><span class="sxs-lookup"><span data-stu-id="3fac1-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="3fac1-180">**SharePoint – taxonomia: topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="3fac1-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="3fac1-181">SharePoint – taxonomia: topLevelTermOf é o inverso da taxonomia do SharePoint: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="3fac1-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="3fac1-182">A sintaxe a ser definida é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="3fac1-183">**SharePoint – taxonomia: intermset**</span><span class="sxs-lookup"><span data-stu-id="3fac1-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="3fac1-184">Use esta para mapear um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) para um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="3fac1-185">Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) só pode existir em um único [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="3fac1-186">O SharePoint requer essa propriedade ao [definir um termo](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="3fac1-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="3fac1-187">Rótulos necessários</span><span class="sxs-lookup"><span data-stu-id="3fac1-187">Required labels</span></span>

<span data-ttu-id="3fac1-188">Sua organização pode querer fazer um planejamento cuidadoso antes de começar a usar metadados gerenciados.</span><span class="sxs-lookup"><span data-stu-id="3fac1-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="3fac1-189">A quantidade de planejamento que você deve fazer depende da forma formal de sua taxonomia.</span><span class="sxs-lookup"><span data-stu-id="3fac1-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="3fac1-190">Também depende do nível de controle que você deseja impor nos metadados.</span><span class="sxs-lookup"><span data-stu-id="3fac1-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="3fac1-191">Em cada nível da hierarquia, você precisa configurar os rótulos obrigatórios para um termo ou termo.</span><span class="sxs-lookup"><span data-stu-id="3fac1-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="3fac1-192">Um termo pode ter um ou mais rótulos no idioma padrão e zero ou mais rótulos no idioma não padrão.</span><span class="sxs-lookup"><span data-stu-id="3fac1-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="3fac1-193">Se o termo tiver rótulos em um idioma, um dos rótulos deve ser o rótulo padrão.</span><span class="sxs-lookup"><span data-stu-id="3fac1-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="3fac1-194">**SharePoint – taxonomia: defaultlabel**</span><span class="sxs-lookup"><span data-stu-id="3fac1-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="3fac1-195">Use este rótulo lexical padrão para um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que é um parâmetro obrigatório para um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="3fac1-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="3fac1-196">Use para representar visualmente o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="3fac1-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="3fac1-197">A sintaxe para definir um defaultlabel é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="3fac1-198">O defaultlabel contém duas partes, a cadeia de caracteres e a marca de idioma.</span><span class="sxs-lookup"><span data-stu-id="3fac1-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="3fac1-199">O idioma deve ser um dos idiomas de trabalho do [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="3fac1-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="3fac1-200">Defaultlabel deve ser exclusivo para todos os [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) no mesmo [termoset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), no mesmo nível hierárquico.</span><span class="sxs-lookup"><span data-stu-id="3fac1-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="3fac1-201">**SharePoint – taxonomia: termSetName**</span><span class="sxs-lookup"><span data-stu-id="3fac1-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="3fac1-202">Obtém e define o nome do objeto Termset atual.</span><span class="sxs-lookup"><span data-stu-id="3fac1-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="3fac1-203">Esse rótulo léxico para um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), em um idioma de trabalho do [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="3fac1-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="3fac1-204">Este é um parâmetro obrigatório para um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="3fac1-205">Use para representar visualmente um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="3fac1-206">A sintaxe para definir um termSetName é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="3fac1-207">**SharePoint – taxonomia: propertyName**</span><span class="sxs-lookup"><span data-stu-id="3fac1-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="3fac1-208">Obtém e define o nome da propriedade para o objeto Termset atual.</span><span class="sxs-lookup"><span data-stu-id="3fac1-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="3fac1-209">Este é o rótulo léxico para uma taxonomia do SharePoint: SharedCustomPropertyForTerm, SharePoint-taxonomia: LocalCustomPropertyForTerm e SharePoint – taxonomia: CustomPropertyForTermSet em um idioma de trabalho do [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="3fac1-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="3fac1-210">O SharePoint – taxonomia: propertyName é tratado como a chave de CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="3fac1-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="3fac1-211">A sintaxe para definir um propetyName é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="3fac1-212">Rótulos opcionais</span><span class="sxs-lookup"><span data-stu-id="3fac1-212">Optional labels</span></span>

<span data-ttu-id="3fac1-213">Você também pode adicionar rótulos opcionais à sua taxonomia.</span><span class="sxs-lookup"><span data-stu-id="3fac1-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="3fac1-214">**SharePoint – taxonomia: otherLabel**</span><span class="sxs-lookup"><span data-stu-id="3fac1-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="3fac1-215">Este é o rótulo lexical alternativo para um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="3fac1-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="3fac1-216">A sintaxe para definir um otherLabel é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="3fac1-217">Relações semânticas</span><span class="sxs-lookup"><span data-stu-id="3fac1-217">Semantic relationships</span></span>

<span data-ttu-id="3fac1-218">As taxonomias têm hierarquia e, às vezes, uma relação de associação "termo relacionado" simples, mas algumas têm "relacionamentos semânticos" ou relações criadas de forma personalizada.</span><span class="sxs-lookup"><span data-stu-id="3fac1-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="3fac1-219">**SharePoint – taxonomia: pai**</span><span class="sxs-lookup"><span data-stu-id="3fac1-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="3fac1-220">Isso relaciona hierarquicamente um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) com outro [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="3fac1-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="3fac1-221">Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode ser um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior de um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), mas caso contrário, ele deve ter um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)pai.</span><span class="sxs-lookup"><span data-stu-id="3fac1-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="3fac1-222">A sintaxe para definir um pai é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="3fac1-223">Isso significa que o TermA1 tem o termo pai.</span><span class="sxs-lookup"><span data-stu-id="3fac1-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="3fac1-224">Inversamente, isso também significa que TermA1 é o filho do termo.</span><span class="sxs-lookup"><span data-stu-id="3fac1-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="3fac1-225">A relação pai-filho é uma relação inversible.</span><span class="sxs-lookup"><span data-stu-id="3fac1-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="3fac1-226">**SharePoint – taxonomia: filho**</span><span class="sxs-lookup"><span data-stu-id="3fac1-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="3fac1-227">O objeto contém uma ou mais instâncias de Termset filhas, e elas podem ser acessadas por meio da propriedade TermSets.</span><span class="sxs-lookup"><span data-stu-id="3fac1-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="3fac1-228">Essa classe também fornece métodos para criar novos objetos Child Termset.</span><span class="sxs-lookup"><span data-stu-id="3fac1-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="3fac1-229">As permissões para editar as instâncias do termo filho e do Termset é especificada no grupo.</span><span class="sxs-lookup"><span data-stu-id="3fac1-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="3fac1-230">Isso relaciona hierarquicamente um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) com outro [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="3fac1-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="3fac1-231">A sintaxe para definir um filho é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="3fac1-232">Isso significa que o Termum tem TermA1 filho.</span><span class="sxs-lookup"><span data-stu-id="3fac1-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="3fac1-233">Inversamente, isso também significa que o termo é o pai da relação pai-filho TermA1 é uma relação inversible.</span><span class="sxs-lookup"><span data-stu-id="3fac1-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="3fac1-234">Notas da documentação</span><span class="sxs-lookup"><span data-stu-id="3fac1-234">Documentation notes</span></span>

<span data-ttu-id="3fac1-235">Esta seção discute a taxonomia detalhada no namespace Microsoft. SharePoint. taxonomia.</span><span class="sxs-lookup"><span data-stu-id="3fac1-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="3fac1-236">**SharePoint – taxonomia: Descrição**</span><span class="sxs-lookup"><span data-stu-id="3fac1-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="3fac1-237">Esta é uma explicação detalhada de qualquer entidade de vocabulário de [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) .</span><span class="sxs-lookup"><span data-stu-id="3fac1-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="3fac1-238">A sintaxe para adicionar uma descrição é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="3fac1-239">Propriedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="3fac1-239">Custom properties</span></span>

<span data-ttu-id="3fac1-240">Obtém a coleção de objetos Property personalizados para o objeto Term atual do dicionário somente leitura.</span><span class="sxs-lookup"><span data-stu-id="3fac1-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="3fac1-241">As propriedades personalizadas são pares de valores-chave que podem ser definidos para um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), para a descrição do [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="3fac1-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="3fac1-242">O SharePoint especifica a chave da propriedade personalizada com a ajuda de propertyName.</span><span class="sxs-lookup"><span data-stu-id="3fac1-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="3fac1-243">**SharePoint – taxonomia: CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="3fac1-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="3fac1-244">A sintaxe a ser definida é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="3fac1-245">**SharePoint – taxonomia: SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="3fac1-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="3fac1-246">Se a propriedade personalizada de um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) precisar ser transportada junto com o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutilizar o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, precisará defini-lo em SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="3fac1-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="3fac1-247">A sintaxe a ser definida é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="3fac1-248">**SharePoint – taxonomia: LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="3fac1-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="3fac1-249">Se a propriedade personalizada de um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) não precisar ser transferida junto com o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutilizar o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, então você precisará defini-lo em LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="3fac1-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="3fac1-250">A sintaxe a ser definida é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="3fac1-251">Propriedades de dados</span><span class="sxs-lookup"><span data-stu-id="3fac1-251">Data properties</span></span>

<span data-ttu-id="3fac1-252">Em cada nível da hierarquia, você pode configurar propriedades de dados específicas para um termo ou termo.</span><span class="sxs-lookup"><span data-stu-id="3fac1-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="3fac1-253">**SharePoint – taxonomia: isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="3fac1-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="3fac1-254">Use isto para especificar se um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponível nas listas e bibliotecas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3fac1-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="3fac1-255">A sintaxe é:</span><span class="sxs-lookup"><span data-stu-id="3fac1-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="3fac1-256">Domínio e intervalo</span><span class="sxs-lookup"><span data-stu-id="3fac1-256">Domain and range</span></span>

<span data-ttu-id="3fac1-257">A tabela abaixo descreve o domínio e o intervalo de vocabulário de taxonomia do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3fac1-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="3fac1-258">Predicados/verbo</span><span class="sxs-lookup"><span data-stu-id="3fac1-258">Predicates/verb</span></span>|<span data-ttu-id="3fac1-259">Significado</span><span class="sxs-lookup"><span data-stu-id="3fac1-259">Meaning</span></span>|<span data-ttu-id="3fac1-260">Domínio</span><span class="sxs-lookup"><span data-stu-id="3fac1-260">Domain</span></span>|<span data-ttu-id="3fac1-261">Range</span><span class="sxs-lookup"><span data-stu-id="3fac1-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="3fac1-262">intermset</span><span class="sxs-lookup"><span data-stu-id="3fac1-262">inTermSet</span></span>|<span data-ttu-id="3fac1-263">No conjunto de termos</span><span class="sxs-lookup"><span data-stu-id="3fac1-263">In term set</span></span>|<span data-ttu-id="3fac1-264">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-264">Term</span></span>|<span data-ttu-id="3fac1-265">Conjunto de termos</span><span class="sxs-lookup"><span data-stu-id="3fac1-265">Term Set</span></span>|
<span data-ttu-id="3fac1-266">intermde</span><span class="sxs-lookup"><span data-stu-id="3fac1-266">inTermGroup</span></span>|<span data-ttu-id="3fac1-267">No grupo de termos</span><span class="sxs-lookup"><span data-stu-id="3fac1-267">In term group</span></span>|<span data-ttu-id="3fac1-268">Termset</span><span class="sxs-lookup"><span data-stu-id="3fac1-268">TermSet</span></span>|<span data-ttu-id="3fac1-269">O termo</span><span class="sxs-lookup"><span data-stu-id="3fac1-269">TermGroup</span></span>|
<span data-ttu-id="3fac1-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="3fac1-270">topLevelTermOf</span></span>|<span data-ttu-id="3fac1-271">É o termo de nível superior de</span><span class="sxs-lookup"><span data-stu-id="3fac1-271">Is Top Level Term Of</span></span>|<span data-ttu-id="3fac1-272">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-272">Term</span></span>|<span data-ttu-id="3fac1-273">Termset</span><span class="sxs-lookup"><span data-stu-id="3fac1-273">TermSet</span></span>|
<span data-ttu-id="3fac1-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="3fac1-274">hasTopLevelTerm</span></span>|<span data-ttu-id="3fac1-275">Tem termo de nível superior</span><span class="sxs-lookup"><span data-stu-id="3fac1-275">Has top level term</span></span>|<span data-ttu-id="3fac1-276">Conjunto de termos</span><span class="sxs-lookup"><span data-stu-id="3fac1-276">Term Set</span></span>|<span data-ttu-id="3fac1-277">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-277">Term</span></span>|
<span data-ttu-id="3fac1-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="3fac1-278">termSetName</span></span>|<span data-ttu-id="3fac1-279">O conjunto de termos tem nome</span><span class="sxs-lookup"><span data-stu-id="3fac1-279">Term set has Name</span></span>|<span data-ttu-id="3fac1-280">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-280">Term</span></span>|<span data-ttu-id="3fac1-281">Literal simples</span><span class="sxs-lookup"><span data-stu-id="3fac1-281">Plain literal</span></span>|
<span data-ttu-id="3fac1-282">defaultlabel</span><span class="sxs-lookup"><span data-stu-id="3fac1-282">defaultLabel</span></span>|<span data-ttu-id="3fac1-283">O termo tem rótulo padrão</span><span class="sxs-lookup"><span data-stu-id="3fac1-283">Term has default label</span></span>|<span data-ttu-id="3fac1-284">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-284">Term</span></span>|<span data-ttu-id="3fac1-285">Literal simples</span><span class="sxs-lookup"><span data-stu-id="3fac1-285">Plain literal</span></span>|
<span data-ttu-id="3fac1-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="3fac1-286">otherLabel</span></span>|<span data-ttu-id="3fac1-287">O termo tem outro rótulo</span><span class="sxs-lookup"><span data-stu-id="3fac1-287">Term has other label</span></span>|<span data-ttu-id="3fac1-288">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-288">Term</span></span>|<span data-ttu-id="3fac1-289">Literal simples</span><span class="sxs-lookup"><span data-stu-id="3fac1-289">Plain literal</span></span>|
<span data-ttu-id="3fac1-290">NomeDaPropriedade</span><span class="sxs-lookup"><span data-stu-id="3fac1-290">propertyName</span></span>|<span data-ttu-id="3fac1-291">Tem rótulo de propriedade</span><span class="sxs-lookup"><span data-stu-id="3fac1-291">Has Property Label</span></span>|<span data-ttu-id="3fac1-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="3fac1-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="3fac1-293">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="3fac1-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="3fac1-294">description</span><span class="sxs-lookup"><span data-stu-id="3fac1-294">description</span></span>|<span data-ttu-id="3fac1-295">Tem descrição</span><span class="sxs-lookup"><span data-stu-id="3fac1-295">Has Description</span></span>|<span data-ttu-id="3fac1-296">Todos</span><span class="sxs-lookup"><span data-stu-id="3fac1-296">All</span></span>|<span data-ttu-id="3fac1-297">Literal simples</span><span class="sxs-lookup"><span data-stu-id="3fac1-297">Plain literal</span></span>|
|<span data-ttu-id="3fac1-298">primário</span><span class="sxs-lookup"><span data-stu-id="3fac1-298">parent</span></span>|<span data-ttu-id="3fac1-299">Tem pai</span><span class="sxs-lookup"><span data-stu-id="3fac1-299">Has parent</span></span>|<span data-ttu-id="3fac1-300">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-300">Term</span></span>|<span data-ttu-id="3fac1-301">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-301">Term</span></span>|
|<span data-ttu-id="3fac1-302">pensão</span><span class="sxs-lookup"><span data-stu-id="3fac1-302">child</span></span>|<span data-ttu-id="3fac1-303">Tem filho</span><span class="sxs-lookup"><span data-stu-id="3fac1-303">Has Child</span></span>|<span data-ttu-id="3fac1-304">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-304">Term</span></span>|<span data-ttu-id="3fac1-305">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-305">Term</span></span>|
|<span data-ttu-id="3fac1-306">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="3fac1-306">isAvailableForTagging</span></span>|<span data-ttu-id="3fac1-307">Está disponível para marcação</span><span class="sxs-lookup"><span data-stu-id="3fac1-307">Is available for tagging</span></span>|<span data-ttu-id="3fac1-308">Termo, conjunto de termos</span><span class="sxs-lookup"><span data-stu-id="3fac1-308">Term, Term Set</span></span>|<span data-ttu-id="3fac1-309">Booliano</span><span class="sxs-lookup"><span data-stu-id="3fac1-309">Boolean</span></span>|
|<span data-ttu-id="3fac1-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="3fac1-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="3fac1-311">Tem propriedade personalizada compartilhada</span><span class="sxs-lookup"><span data-stu-id="3fac1-311">Has shared custom property</span></span>|<span data-ttu-id="3fac1-312">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-312">Term</span></span>|<span data-ttu-id="3fac1-313">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="3fac1-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="3fac1-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="3fac1-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="3fac1-315">Tem propriedade personalizada local</span><span class="sxs-lookup"><span data-stu-id="3fac1-315">Has local custom property</span></span>|<span data-ttu-id="3fac1-316">Term</span><span class="sxs-lookup"><span data-stu-id="3fac1-316">Term</span></span>|<span data-ttu-id="3fac1-317">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="3fac1-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="3fac1-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="3fac1-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="3fac1-319">Tem propriedade personalizada</span><span class="sxs-lookup"><span data-stu-id="3fac1-319">Has Custom Property</span></span>|<span data-ttu-id="3fac1-320">Termset</span><span class="sxs-lookup"><span data-stu-id="3fac1-320">TermSet</span></span>|<span data-ttu-id="3fac1-321">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="3fac1-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="3fac1-322">[Skos](https://www.w3.org/TR/skos-primer/) cenários válidos que a [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) não permite:</span><span class="sxs-lookup"><span data-stu-id="3fac1-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="3fac1-323">Redundância hierárquica – um conceito de [skos](https://www.w3.org/TR/skos-primer/) pode ser anexado a vários conceitos mais amplos ao mesmo tempo, mas uma taxonomia do SharePoint: o termo pode ter apenas uma taxonomia do SharePoint: o pai, portanto, A dependência cíclica, de termos também não é permitido.</span><span class="sxs-lookup"><span data-stu-id="3fac1-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="3fac1-324">Termos órfãos não são permitidos na taxonomia do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3fac1-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="3fac1-325">Cada SharePoint – taxonomia: o termo deve ter uma taxonomia do SharePoint: pai ou deve ser a taxonomia do SharePoint: topLevelTermOf um Termset.</span><span class="sxs-lookup"><span data-stu-id="3fac1-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="3fac1-326">A taxonomia do SharePoint não oferece suporte a relações associativas.</span><span class="sxs-lookup"><span data-stu-id="3fac1-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="3fac1-327">A taxonomia do SharePoint permite apenas 2 tipos de relações hierárquicas – SharePoint – taxonomia: pai e SharePoint – taxonomia: filho.</span><span class="sxs-lookup"><span data-stu-id="3fac1-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="3fac1-328">Ao contrário do [skos](https://www.w3.org/TR/skos-primer/) a relação hierárquica no vocabulário de taxonomia do SharePoint, só pode ser estabelecida com termos no mesmo termoset.</span><span class="sxs-lookup"><span data-stu-id="3fac1-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fac1-329">Confira também</span><span class="sxs-lookup"><span data-stu-id="3fac1-329">See also</span></span>

[<span data-ttu-id="3fac1-330">Importar um conjunto de termos usando um formato baseado em SKOS</span><span class="sxs-lookup"><span data-stu-id="3fac1-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

