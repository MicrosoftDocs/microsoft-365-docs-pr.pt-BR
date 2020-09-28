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
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>Referência de formato SKOS para a taxonomia do SharePoint

Este artigo inclui o vocabulário RDF usado para representar a [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) e é baseado no [skos](https://www.w3.org/TR/skos-primer/). Para a serialização dessa sintaxe RDF, use a [tartaruga](https://www.w3.org/TR/turtle/)RDF.

A tabela a seguir mostra os equivalentes do [skos](https://www.w3.org/TR/skos-primer/) para o vocabulário de [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) . O SharePoint não oferece suporte a valores de [skos](https://www.w3.org/TR/skos-primer/) que não tenham nenhuma taxonomia do SharePoint equivalente.

|Taxonomia do SharePoint|Equivalente SKOS|
|:-----------------|:--------------|
|SharePoint – taxonomia: termo|skos: conceito|
|SharePoint – taxonomia: Termset|skos:ConceptScheme|
|SharePoint – taxonomia: intermset|skos: inesquema|
|SharePoint – taxonomia: hasTopLevelTerm|skos:hasTopConcept|
|SharePoint – taxonomia: topLevelTermOf|skos:topConceptOf|
|SharePoint – taxonomia: defaultlabel|skos:prefLabel|
|SharePoint – taxonomia: termSetName|skos:prefLabel|
|SharePoint – taxonomia: propertyName|skos:prefLabel|
|SharePoint – taxonomia: otherLabel|skos:altLabel|
|SharePoint – taxonomia: Descrição|skos: definição|
|SharePoint – taxonomia: pai|skos: mais amplo|
|SharePoint – taxonomia: filho|skos: mais estreito|

A tabela a seguir exibe as entidades do vocabulário de taxonomia do SharePoint derivado de [Owl](https://www.w3.org/TR/owl2-primer/).

|Vocabulário de taxonomia do SharePoint|Derivado de OWL|
|:-----------------------------|:----------------------|
|SharePoint – taxonomia: isAvailableForTagging|Owl: datatypeproperty|
|SharePoint – taxonomia: SharedCustomPropertyForTerm|Owl: Fieldobjeto|
|SharePoint – taxonomia: LocalCustomPropertyForTerm|Owl: Fieldobjeto|
|SharePoint – taxonomia: CustomPropertyForTermSet|Owl: Fieldobjeto|

## <a name="sharepoint-taxonomy-vocabulary"></a>Vocabulário de taxonomia do SharePoint

Uma taxonomia é um sistema de classificação formal. Uma taxonomia agrupa as palavras, rótulos e termos que descrevem algo e, em seguida, organiza os grupos em uma hierarquia.

**SharePoint – taxonomia: termo**

Representa um termo ou uma palavra-chave em uma hierarquia de metadados gerenciados.

Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) é a unidade atômica de um [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)do SharePoint. Cada [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertence a um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertence a um [termo.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group) 

A sintaxe para definir um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) é a seguinte:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Há um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily em um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Defaultlabel é o nome do [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) como ele aparece na representação visual. Os campos obrigatórios para definir um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) incluem:

- SharePoint – taxonomia: defaultlabel
- SharePoint – taxonomia: intermset

Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode:

- Ser hierarquicamente relacionadas a outro [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que é fornecido, os [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertencem ao mesmo [termoset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Ter vários [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)filhos, mas apenas um único [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)pai.
- Não ter um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai definido, se for um TopLevelTermOf um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Ter um defaultlabel, por idioma de trabalho do [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .
- Não existir se não contiver um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)pai, nem o TopLevelTermOf um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Ter apenas um defaultlabel exclusivo no mesmo nível hierárquico.

**SharePoint – taxonomia: Termset**

Representa um conjunto hierárquico ou simples de objetos Term conhecidos como "Termset".

Como o nome sugere, Termset é um conjunto de [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) deve pertencer a um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Nenhum [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode existir de forma independente. 

A sintaxe para definir um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

Os [TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) são agrupados logicamente no [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). O campo obrigatório para definir um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:

- SharePoint – taxonomia: termSetName

No caso do termSetName fornecido não é exclusivo no @ @ @ [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint acrescenta um número ao final do nome para manter a exclusividade de termSetName (s)

**SharePoint – taxonomia: hasTopLevelTerm**

O SharePoint usa essa propriedade para mapear a maior parte do [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) no [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), que é o ponto de entrada para a hierarquia de [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Esta é uma relação inversa à taxonomia do SharePoint: topLevelTermOf. 

A sintaxe a ser definida é:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Não é possível definir o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior de um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)pai.

**SharePoint – taxonomia: topLevelTermOf**

SharePoint – taxonomia: topLevelTermOf é o inverso da taxonomia do SharePoint: hasTopLevelTerm

A sintaxe a ser definida é:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**SharePoint – taxonomia: intermset**

Use esta para mapear um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) para um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) só pode existir em um único [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). O SharePoint requer essa propriedade ao [definir um termo](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Rótulos necessários

Sua organização pode querer fazer um planejamento cuidadoso antes de começar a usar metadados gerenciados. A quantidade de planejamento que você deve fazer depende da forma formal de sua taxonomia. Também depende do nível de controle que você deseja impor nos metadados. Em cada nível da hierarquia, você precisa configurar os rótulos obrigatórios para um termo ou termo.

Um termo pode ter um ou mais rótulos no idioma padrão e zero ou mais rótulos no idioma não padrão. Se o termo tiver rótulos em um idioma, um dos rótulos deve ser o rótulo padrão.

**SharePoint – taxonomia: defaultlabel**

Use este rótulo lexical padrão para um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que é um parâmetro obrigatório para um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Use para representar visualmente o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

A sintaxe para definir um defaultlabel é:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

O defaultlabel contém duas partes, a cadeia de caracteres e a marca de idioma. O idioma deve ser um dos idiomas de trabalho do [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . Defaultlabel deve ser exclusivo para todos os [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) no mesmo [termoset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), no mesmo nível hierárquico.

**SharePoint – taxonomia: termSetName**

Obtém e define o nome do objeto Termset atual.

Esse rótulo léxico para um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), em um idioma de trabalho do [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . Este é um parâmetro obrigatório para um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Use para representar visualmente um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

A sintaxe para definir um termSetName é:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**SharePoint – taxonomia: propertyName**

Obtém e define o nome da propriedade para o objeto Termset atual.

Este é o rótulo léxico para uma taxonomia do SharePoint: SharedCustomPropertyForTerm, SharePoint-taxonomia: LocalCustomPropertyForTerm e SharePoint – taxonomia: CustomPropertyForTermSet em um idioma de trabalho do [termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .

O SharePoint – taxonomia: propertyName é tratado como a chave de CustomProperty.

A sintaxe para definir um propetyName é:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Rótulos opcionais

Você também pode adicionar rótulos opcionais à sua taxonomia.

**SharePoint – taxonomia: otherLabel**

Este é o rótulo lexical alternativo para um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

A sintaxe para definir um otherLabel é:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Relações semânticas

As taxonomias têm hierarquia e, às vezes, uma relação de associação "termo relacionado" simples, mas algumas têm "relacionamentos semânticos" ou relações criadas de forma personalizada. 

**SharePoint – taxonomia: pai**

Isso relaciona hierarquicamente um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) com outro [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode ser um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior de um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), mas caso contrário, ele deve ter um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)pai. 

A sintaxe para definir um pai é:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Isso significa que o TermA1 tem o termo pai. Inversamente, isso também significa que TermA1 é o filho do termo. A relação pai-filho é uma relação inversible.

**SharePoint – taxonomia: filho**

O objeto contém uma ou mais instâncias de Termset filhas, e elas podem ser acessadas por meio da propriedade TermSets. Essa classe também fornece métodos para criar novos objetos Child Termset. As permissões para editar as instâncias do termo filho e do Termset é especificada no grupo. 

Isso relaciona hierarquicamente um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) com outro [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

A sintaxe para definir um filho é:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Isso significa que o Termum tem TermA1 filho. Inversamente, isso também significa que o termo é o pai da relação pai-filho TermA1 é uma relação inversible.

## <a name="documentation-notes"></a>Notas da documentação

Esta seção discute a taxonomia detalhada no namespace Microsoft. SharePoint. taxonomia.

**SharePoint – taxonomia: Descrição**

Esta é uma explicação detalhada de qualquer entidade de vocabulário de [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) . 

A sintaxe para adicionar uma descrição é:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Propriedades personalizadas

Obtém a coleção de objetos Property personalizados para o objeto Term atual do dicionário somente leitura.

As propriedades personalizadas são pares de valores-chave que podem ser definidos para um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), para a descrição do [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). O SharePoint especifica a chave da propriedade personalizada com a ajuda de propertyName.

**SharePoint – taxonomia: CustomPropertyForTermSet**

A sintaxe a ser definida é:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**SharePoint – taxonomia: SharedCustomPropertyForTerm**

Se a propriedade personalizada de um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) precisar ser transportada junto com o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutilizar o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, precisará defini-lo em SharedCustomPropertyForTerm.

A sintaxe a ser definida é:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**SharePoint – taxonomia: LocalCustomPropertyForTerm**

Se a propriedade personalizada de um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) não precisar ser transferida junto com o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutilizar o [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, então você precisará defini-lo em LocalCustomPropertyForTerm.

A sintaxe a ser definida é:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Propriedades de dados

Em cada nível da hierarquia, você pode configurar propriedades de dados específicas para um termo ou termo.

**SharePoint – taxonomia: isAvailableForTagging**

Use isto para especificar se um [termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponível nas listas e bibliotecas do SharePoint.  

A sintaxe é:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Domínio e intervalo

A tabela abaixo descreve o domínio e o intervalo de vocabulário de taxonomia do SharePoint.

|Predicados/verbo|Significado|Domínio|Range|
|:--------------|:------|:-----|:----|
intermset|No conjunto de termos|Term|Conjunto de termos|
intermde|No grupo de termos|Termset|O termo|
topLevelTermOf|É o termo de nível superior de|Term|Termset|
hasTopLevelTerm|Tem termo de nível superior|Conjunto de termos|Term|
termSetName|O conjunto de termos tem nome|Term|Literal simples|
defaultlabel|O termo tem rótulo padrão|Term|Literal simples|
otherLabel|O termo tem outro rótulo|Term|Literal simples|
NomeDaPropriedade|Tem rótulo de propriedade|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean, String, Integer, Decimal, Double|
|description|Tem descrição|Todos|Literal simples|
|primário|Tem pai|Term|Term|
|pensão|Tem filho|Term|Term|
|isAvailableForTagging|Está disponível para marcação|Termo, conjunto de termos|Booliano|
|SharedCustomPropertyForTerm|Tem propriedade personalizada compartilhada|Term|Boolean, String, Integer, Decimal, Double|
|LocalCustomPropertyForTerm|Tem propriedade personalizada local|Term|Boolean, String, Integer, Decimal, Double|
|CustomPropertyForTermSet|Tem propriedade personalizada|Termset|Boolean, String, Integer, Decimal, Double|

[Skos](https://www.w3.org/TR/skos-primer/) cenários válidos que a [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) não permite:

- Redundância hierárquica – um conceito de [skos](https://www.w3.org/TR/skos-primer/) pode ser anexado a vários conceitos mais amplos ao mesmo tempo, mas uma taxonomia do SharePoint: o termo pode ter apenas uma taxonomia do SharePoint: o pai, portanto, A dependência cíclica, de termos também não é permitido.
- Termos órfãos não são permitidos na taxonomia do SharePoint. Cada SharePoint – taxonomia: o termo deve ter uma taxonomia do SharePoint: pai ou deve ser a taxonomia do SharePoint: topLevelTermOf um Termset.
- A taxonomia do SharePoint não oferece suporte a relações associativas.
- A taxonomia do SharePoint permite apenas 2 tipos de relações hierárquicas – SharePoint – taxonomia: pai e SharePoint – taxonomia: filho. 
- Ao contrário do [skos](https://www.w3.org/TR/skos-primer/) a relação hierárquica no vocabulário de taxonomia do SharePoint, só pode ser estabelecida com termos no mesmo termoset.

## <a name="see-also"></a>Confira também

[Importar um conjunto de termos usando um formato baseado em SKOS](import-term-set-skos.md)

