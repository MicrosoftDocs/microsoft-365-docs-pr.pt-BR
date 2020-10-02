---
title: Formato SKOS como referência para a taxonomia do SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Formato SKOS como referência para a taxonomia do SharePoint
ms.openlocfilehash: f81b618a7c302ce033c4e8ce2f7400e9616f2de0
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321320"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>Formato SKOS como referência para a taxonomia do SharePoint

Este artigo inclui o vocabulário RDF utilizado para representar a [Taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) e é baseado no [SKOS](https://www.w3.org/TR/skos-primer/). Para a serialização desta sintaxe RDF, utilize o RDF [TARTARUGA](https://www.w3.org/TR/turtle/).

A tabela seguinte exibe os equivalentes ao [SKOS](https://www.w3.org/TR/skos-primer/) para o vocabulário [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). O SharePoint não suporta valores [SKOS](https://www.w3.org/TR/skos-primer/) que não tenham equivalente em taxonomia do SharePoint.

|Taxonomia do SharePoint|Equivalente ao SKOS|
|:-----------------|:--------------|
|sharepoint-taxonomy:Term|skos:Concept|
|sharepoint-taxonomy:TermSet|skos:ConceitoScheme|
|sharepoint-taxonomy:inTermSet|skos:inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos:topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:description|skos:definition|
|sharepoint-taxonomy:parent|skos:broader|
|sharepoint-taxonomy:child|skos:narrower|

A tabela a seguir mostra as entidades do vocabulário de taxonomia do SharePoint derivado de [OWL](https://www.w3.org/TR/owl2-primer/).

|Vocabulário de taxonomia do SharePoint|Derivado de OWL|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>Vocabulário de taxonomia do SharePoint

Uma taxonomia é um sistema formal de classificação. Uma taxonomia agrupa as palavras, rótulos e termos que descrevem algo, e depois organiza os grupos em uma hierarquia.

**sharepoint-taxonomy:Term**

Representa um Termo ou Palavra-chave em uma hierarquia de metadados gerenciados.

Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) é a unidade atômica de um [Repositório de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) do SharePoint. Cada [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertence a um [Conjunto de Termos ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) que pertence a um [Grupo de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). 

A sintaxe para definir um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) é a seguinte:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) existe obrigatoriamente dentro de um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel é o nome do [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) como aparece na representação visual. Os campos obrigatórios para a definição de um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) incluem:

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode:

- Estar hierarquicamente relacionado a outro [Termo ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), desde que os [Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pertençam ao mesmo [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Ter vários [Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) filhos, mas somente um único [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai.
- Não ter um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai definido, se o topLevelTermOf for um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Tenha um defaultLabel, por idioma de trabalho na [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).
- Não existe se não contém um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai, nem se o topLevelTermOf for um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Ter apenas um rótulo padrão único no mesmo nível hierárquico.

**sharepoint-taxonomy:TermSet**

Representa uma hierarquia ou um conjunto horizontal de objetos de Termo conhecido como "Conjunto de Termos".

Como o nome sugere, Conjunto de Termos é um conjunto de [Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em uma [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) deve pertencer a um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Nenhum [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode existir independentemente. 

A sintaxe para definir um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[Conjuntos de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) são logicamente agrupados em [Grupos de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). O campo necessário para definir um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) é:

- sharepoint-taxonomy:termSetName

No caso do termSetName fornecido não ser exclusivo no [Grupo de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), o SharePoint anexa um número no final do nome para manter a exclusividade do termSetName (s).

**sharepoint-taxonomy:hasTopLevelTerm**

O SharePoint usa essa propriedade para mapear o primeiro [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) no [ Conjunto de Termos ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), que é o ponto de entrada para a hierarquia de [Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Esta é uma relação inversa com a taxonomia sharepoint-taxonomy:topLevelTermOf. 

A sintaxe para definir isto é:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Você não pode definir o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior de um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai.

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taxonomy:topLevelTermOf é o inverso de sharepoint-taxonomy:hasTopLevelTerm

A sintaxe para definir isto é:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

Utilize isto para mapear um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) só pode existir em um único [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). O SharePoint requer esta propriedade quando [definir um termo](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Rótulos necessários

Sua organização pode desejar fazer um planejamento cuidadoso antes de começar a usar metadados gerenciados. A quantia de planejamento que você deve fazer depende de quão formal é sua taxonomia. Depende também de quanto controle você quer impor sobre os metadados. Para cada nível da hierarquia, você precisa configurar os rótulos necessários para um Term ou TermSet.

Um termo pode ter um ou mais rótulos no idioma padrão e zero ou mais rótulos no idioma não padrão. Se o termo tiver rótulos em um idioma, um dos rótulos deverá ser o padrão.

**sharepoint-taxonomy:defaultLabel**

Utilize este rótulo léxico padrão para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) que é um parâmetro obrigatório para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Utilize para representar visualmente o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

A sintaxe para definir o defaultLabel é:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

O defaultLabel contém duas partes - a cadeia de caracteres e a marca de idioma. O idioma deve ser um dos idiomas de trabalho do [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). O defaultLabel deve ser único para todos os [Termo ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) no mesmo [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), no mesmo nível hierárquico.

**sharepoint-taxonomy:termSetName**

Obtém e define o nome do objeto no Conjunto de Termos atual.

Este é o rótulo léxico para um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), em um idioma de trabalho da [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Este é um parâmetro necessário para um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Utilize para representar visualmente um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

A sintaxe para definir um termSetName é:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

Obtém e define o nome da propriedade para o objeto Conjunto de Termos atual.

Este é o rótulo léxico para uma taxonomia do sharepoint: SharedCustomPropertyForTerm, taxonomia do sharepoint: LocalCustomPropertyForTerm e taxonomia do sharepoint: CustomPropertyForTermSet em um idioma de trabalho da [Loja de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).

A sharepoint-taxonomy:propertyName é tratada como a chave da CustomProperty.

A sintaxe para definir uma propetyName é:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Rótulo opcionais

Você também pode adicionar rótulos opcionais à sua taxonomia.

**sharepoint-taxonomy:otherLabel**

Este é o rótulo léxico alternativo para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

A sintaxe para definir um otherLabel é:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Relações semânticas

As taxonomias têm relacionamento associativo hierárquico e, às vezes, simples de "termo relacionado", mas algumas têm "relacionamentos semânticos" ou relacionamentos personalizados. 

**sharepoint-taxonomy:parent**

Esta hierarquia relaciona um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a outro [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pode ser um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) de nível superior em um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), mas caso não seja, este deve ter um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) pai. 

A sintaxe para definir um termo pai é:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Isso significa que o TermA é o pai e TermA é o filho.

**sharepoint-taxonomy:child**

O objeto contém uma ou mais instâncias de Conjunto de Termos filho, que podem ser acessadas por meio da propriedade de Conjunto de Termos. Esta classe também fornece métodos para criar novos objetos nos Conjunto de Termos filhos. Permissões para editar instâncias de Termo filho e Conjunto de Termos são especificadas no grupo. 

Esta hierarquia relaciona um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a outro [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

A sintaxe para definir uma termo filho é:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Isso significa que o TermA é o pai e TermA é o filho.

## <a name="documentation-notes"></a>Notas de documentação

Esta seção discute a taxonomia detalhada no namespace Microsoft.SharePoint.Taxonomy.

**sharepoint-taxonomy:description**

Esta é uma explicação detalhada de qualquer entidade de vocabulário de [ taxonomia do SharePoint ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). 

A sintaxe para acrescentar uma descrição é:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Propriedades personalizadas

Obtém a coleção de objetos de propriedade personalizada para o Termo do objeto atual do dicionário para somente leitura.

Propriedades personalizadas são pares de valores-chave que podem ser definidos para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), para complementar a descrição do [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). O SharePoint especifica a chave da propriedade personalizada com a ajuda do propertyName.

**sharepoint-taxonomy:CustomPropertyForTermSet**

A sintaxe para definir isto é:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

Se a propriedade personalizada para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) precisar ser carregada junto com o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutilizar o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, então você deve defini-lo em SharedCustomPropertyForTerm.

A sintaxe para definir isto é:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

Se a propriedade personalizada para um [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) não precisa ser carregada junto com o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando você reutiliza o [Termo](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) em outro lugar, então você precisa defini-lo em LocalCustomPropertyForTerm.

A sintaxe para definir isto é:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Propriedades dos dados

Em cada nível da hierarquia, você pode configurar propriedades de dados específicas para um Termo ou Conjunto de Termos.

**sharepoint-taxonomy:isAvailableForTagging**

Utilize para especificar se um [Termo ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ou um [Conjunto de Termos](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) está disponível nas Listas e Bibliotecas do SharePoint.  

A sintaxe para isto é:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Domínio e alcance

A tabela a seguir descreve o domínio e a variedade do vocabulário da taxonomia do SharePoint.

|Verbos/predicados|Significado|Domínio|Intervalo|
|:--------------|:------|:-----|:----|
inTermSet|No Conjunto de Termos|Termo|Conjunto de Termos|
inTermGroup|No grupo de termos|Conjunto de Termos|Grupo de Termos|
topLevelTermOf|É o Termo de Nível Superior do|Termo|Conjunto de Termos|
hasTopLevelTerm|Tem um termo de nível superior|Conjunto de Termos|Termo|
termSetName|O Conjunto de termos tem Nome|Termo|Literalmente simples|
defaultLabel|O termo tem rótulo padrão|Termo|Literalmente simples|
otherLabel|O termo tem outro rótulo|Termo|Literalmente simples|
propertyName|Possui Rótulo de Propriedade|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Booleano, String, Inteiro, Decimal, Duplo|
|descrição|Tem Descrição|Tudo|Literalmente simples|
|pai|Tem pai|Termo|Termo|
|filho|Tem filho|Termo|Termo|
|isAvailableForTagging|Está disponível para marcação|Termo, Conjunto de termos|Booleano|
|SharedCustomPropertyForTerm|Possui propriedade personalizada compartilhada|Termo|Booleano, string, Inteiro, Decimal, Duplo|
|LocalCustomPropertyForTerm|Possui propriedade local personalizada|Termo|Booleano, String, Inteiro, Decimal, Duplo|
|CustomPropertyForTermSet|Possui propriedade personalizada|Conjunto de Termos|Booleano, String, Inteiro, Decimal, Duplo|

Cenários válidos de [SKOS](https://www.w3.org/TR/skos-primer/) que a [taxonomia do SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) não permite:

- Redundância hierárquica - Um conceito do [SKOS](https://www.w3.org/TR/skos-primer/) pode ser anexado a vários conceitos mais amplos ao mesmo tempo, mas uma sharepoint-taxonomy:Term pode ter apenas uma sharepoint-taxonomy:parent, portanto, a dependência cíclica de termos também não é permitida.
- Termos órfãos não são permitidos na taxonomia do SharePoint. Cada sharepoint-taxonomy:Term deve ter uma sharepoint-taxonomy:parent ou deve ser um sharepoint-taxonomy:topLevelTermOf um Conjunto de Termos.
- A taxonomia do SharePoint não oferece suporte a relações associativas.
- A taxonomia do SharePoint permite apenas 2 tipos de relações hierárquicas – sharepoint-taxonomy:parent e sharepoint-Taxonomy:child. 
- Ao contrário do [SKOS](https://www.w3.org/TR/skos-primer/), a relação hierárquica no vocabulário de taxonomia do SharePoint, só pode ser estabelecida com Termos dentro do mesmo Conjunto de Termos.

## <a name="see-also"></a>Confira também

[Importar um conjunto de termos usando um formato com base em SKOS](import-term-set-skos.md)

