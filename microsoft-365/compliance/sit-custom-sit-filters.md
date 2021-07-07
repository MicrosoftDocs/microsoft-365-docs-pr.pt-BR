---
title: Referência de filtros de tipo de informação confidenciais personalizados
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Este artigo apresenta uma lista dos filtros que podem ser codificados em tipos de informações confidenciais personalizados.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322437"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>Referência de filtros de tipo de informação confidenciais personalizados

Na Microsoft, você pode definir filtros ou verificações adicionais ao criar um SIT (custom sensitive information types).

## <a name="list-of-supported-filters-and-use-cases"></a>Lista de filtros com suporte e casos de uso

### <a name="alldigitssame-exclude"></a>AllDigitsSame Exclude

Descrição: permite excluir as corresponde que têm todos os dígitos como dígitos duplicados, como 1111111111 ou 111-111-111

Definindo filtros
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

Usá-lo no pacote de regras no nível da entidade
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

Usando-o no pacote de regras no nível de padrão
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

Descrição: permite definir os caracteres in-locar para a entidade. Ele tem duas variantes, incluir e excluir.

Por exemplo, para excluir os números que começam com 0500, 91, 091, 010 em uma lista como esta:

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

você pode usar esse xml

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
Por exemplo, para incluir os números que começam com 0500, 91, 091, 0100 em uma lista como esta: 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

você pode usar esse xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

Descrição: permite definir os caracteres finais da entidade. 

Por exemplo, para excluir os números que terminam com 0500,91.091,0100 em uma lista como esta:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

você pode usar esse xml

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

Por exemplo, para incluir os números terminando com 0500, 91, 091, 0100, em uma lista como esta:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

você pode usar esse xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Completo

Descrição: permite proibir determinadas combinações para impedir que elas acionem a regra. Por exemplo, exclua 411111111111 da lista de combinações de cartão de crédito válidas.

Por exemplo, para excluir números de cartão de crédito como 411111111111111 e 3241891031113111 em uma lista como esta:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

você pode usar esse xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

Por exemplo, para incluir números de cartão de crédito como 411111111111111 e 3241891031113111 em uma lista como esta:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

você pode usar esse xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>Prefixo TextMatchFilter

Descrição: permite definir os caracteres anteriores que devem ser sempre incluídos ou excluídos. Por exemplo, se o número do cartão de crédito for precedido por 'ID do pedido:' remova a match das correspondeções válidas.

Por exemplo, para excluir ocorrências de números de telefone que têm Telefone **número** e **me** chamar em cadeias de caracteres antes do número de telefone, em uma lista como esta:

- número de telefone 091-8974-653278
- Telefone 45-124576532-123
- 45-124576532-123

você pode usar esse xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

Por exemplo, para incluir  ocorrências  que têm cadeias de caracteres de cartão e cartão de crédito antes do número do cartão de crédito, em uma lista como esta:

- Cartão de crédito 45-124576532-123 
- 45-124576532-123 (que pode ser número de telefone)

você pode usar esse xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a>Sufixo TextMatchFilter

Descrição: permite definir os seguintes caracteres que devem ser sempre incluídos ou excluídos. Por exemplo, se o número do cartão de crédito for seguido por '/xuid', remova a match das combinações válidas.

Por exemplo, as principais ocorrências de exclusão se houver mais cinco instâncias de quatro dígitos como sufixo em uma lista como esta:

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

você pode usar esse xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
Por exemplo, para excluir ocorrências se elas são seguidas **por /xuidsuffix**, como uma desta lista:

- 1234-5678-9321 /xuid
- 1234-5678-9321

você pode usar esse xml

''xml <Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group> </Keyword>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a>Usando filtros em pacotes de regras

Os filtros podem ser definidos em todo o SIT ou em um padrão. Aqui estão alguns exemplos de trechos de código. 

### <a name="at-sensitive-information-type-level"></a>No nível do tipo de informação confidenciais

Filtros em Entidade - abrange todos os padrões filho

Os filtros serão aplicados em **todas** as instâncias classificadas por qualquer um dos padrões nessa entidade/tipo confidencial

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>No padrão individual do nível de tipo de informação confidenciais

Filtra somente no nível de padrão.

O filtro será aplicado nas instâncias que corresponderem ao padrão.

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>No nível do tipo de informação confidenciais e um filtro adicional em alguns dos padrões dessa entidade

Filtra em Entity + pattern

Os filtros serão aplicados **em** todas as instâncias classificadas por qualquer um dos padrões nessa entidade/tipo confidencial. O filtro de nível de padrão filtrará as instâncias que corresponderem a esse padrão.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>Mais informações

- [Saiba mais sobre a prevenção contra perda de dados](dlp-learn-about-dlp.md)

- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)

- [O que as funções DLP procuram](what-the-dlp-functions-look-for.md)
