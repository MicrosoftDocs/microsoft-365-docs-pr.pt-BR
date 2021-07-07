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
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="1b0ce-103">Referência de filtros de tipo de informação confidenciais personalizados</span><span class="sxs-lookup"><span data-stu-id="1b0ce-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="1b0ce-104">Na Microsoft, você pode definir filtros ou verificações adicionais ao criar um SIT (custom sensitive information types).</span><span class="sxs-lookup"><span data-stu-id="1b0ce-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="1b0ce-105">Lista de filtros com suporte e casos de uso</span><span class="sxs-lookup"><span data-stu-id="1b0ce-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="1b0ce-106">AllDigitsSame Exclude</span><span class="sxs-lookup"><span data-stu-id="1b0ce-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="1b0ce-107">Descrição: permite excluir as corresponde que têm todos os dígitos como dígitos duplicados, como 1111111111 ou 111-111-111</span><span class="sxs-lookup"><span data-stu-id="1b0ce-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="1b0ce-108">Definindo filtros</span><span class="sxs-lookup"><span data-stu-id="1b0ce-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="1b0ce-109">Usá-lo no pacote de regras no nível da entidade</span><span class="sxs-lookup"><span data-stu-id="1b0ce-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="1b0ce-110">Usando-o no pacote de regras no nível de padrão</span><span class="sxs-lookup"><span data-stu-id="1b0ce-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="1b0ce-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="1b0ce-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="1b0ce-112">Descrição: permite definir os caracteres in-locar para a entidade.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="1b0ce-113">Ele tem duas variantes, incluir e excluir.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="1b0ce-114">Por exemplo, para excluir os números que começam com 0500, 91, 091, 010 em uma lista como esta:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="1b0ce-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="1b0ce-115">0500-4500-027</span></span>
- <span data-ttu-id="1b0ce-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="1b0ce-116">91564721450</span></span>
- <span data-ttu-id="1b0ce-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="1b0ce-117">91-8523697410</span></span>
- <span data-ttu-id="1b0ce-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="1b0ce-118">700-8956-7844</span></span>
- <span data-ttu-id="1b0ce-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="1b0ce-119">1000-3265-9874</span></span>
- <span data-ttu-id="1b0ce-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="1b0ce-120">0100-7892-3012</span></span>

<span data-ttu-id="1b0ce-121">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-121">you can use this xml</span></span>

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
<span data-ttu-id="1b0ce-122">Por exemplo, para incluir os números que começam com 0500, 91, 091, 0100 em uma lista como esta:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="1b0ce-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="1b0ce-123">0500-4500-027</span></span>
- <span data-ttu-id="1b0ce-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="1b0ce-124">91564721450</span></span>
- <span data-ttu-id="1b0ce-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="1b0ce-125">91-8523697410</span></span>
- <span data-ttu-id="1b0ce-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="1b0ce-126">700-8956-7844</span></span>
- <span data-ttu-id="1b0ce-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="1b0ce-127">1000-3265-9874</span></span>
- <span data-ttu-id="1b0ce-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="1b0ce-128">0100-7892-3012</span></span>

<span data-ttu-id="1b0ce-129">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="1b0ce-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="1b0ce-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="1b0ce-131">Descrição: permite definir os caracteres finais da entidade.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="1b0ce-132">Por exemplo, para excluir os números que terminam com 0500,91.091,0100 em uma lista como esta:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="1b0ce-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="1b0ce-133">1234567891</span></span>
- <span data-ttu-id="1b0ce-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="1b0ce-134">1234-5678-0091</span></span>
- <span data-ttu-id="1b0ce-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="1b0ce-135">1234.4567.7091</span></span>
- <span data-ttu-id="1b0ce-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="1b0ce-136">1234-8091-4564</span></span>

<span data-ttu-id="1b0ce-137">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-137">you can use this xml</span></span>

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

<span data-ttu-id="1b0ce-138">Por exemplo, para incluir os números terminando com 0500, 91, 091, 0100, em uma lista como esta:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="1b0ce-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="1b0ce-139">1234567891</span></span>
- <span data-ttu-id="1b0ce-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="1b0ce-140">1234-5678-0091</span></span>
- <span data-ttu-id="1b0ce-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="1b0ce-141">1234.4567.7091</span></span>
- <span data-ttu-id="1b0ce-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="1b0ce-142">1234-8091-4564</span></span>

<span data-ttu-id="1b0ce-143">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="1b0ce-144">TextMatchFilter Completo</span><span class="sxs-lookup"><span data-stu-id="1b0ce-144">TextMatchFilter Full</span></span>

<span data-ttu-id="1b0ce-145">Descrição: permite proibir determinadas combinações para impedir que elas acionem a regra.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="1b0ce-146">Por exemplo, exclua 411111111111 da lista de combinações de cartão de crédito válidas.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="1b0ce-147">Por exemplo, para excluir números de cartão de crédito como 411111111111111 e 3241891031113111 em uma lista como esta:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="1b0ce-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="1b0ce-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="1b0ce-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="1b0ce-149">4111111111111111</span></span>
- <span data-ttu-id="1b0ce-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="1b0ce-150">3241891031113111</span></span>

<span data-ttu-id="1b0ce-151">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-151">you can use this xml</span></span>

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

<span data-ttu-id="1b0ce-152">Por exemplo, para incluir números de cartão de crédito como 411111111111111 e 3241891031113111 em uma lista como esta:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="1b0ce-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="1b0ce-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="1b0ce-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="1b0ce-154">4111111111111111</span></span>
- <span data-ttu-id="1b0ce-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="1b0ce-155">3241891031113111</span></span>

<span data-ttu-id="1b0ce-156">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="1b0ce-157">Prefixo TextMatchFilter</span><span class="sxs-lookup"><span data-stu-id="1b0ce-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="1b0ce-158">Descrição: permite definir os caracteres anteriores que devem ser sempre incluídos ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="1b0ce-159">Por exemplo, se o número do cartão de crédito for precedido por 'ID do pedido:' remova a match das correspondeções válidas.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="1b0ce-160">Por exemplo, para excluir ocorrências de números de telefone que têm Telefone **número** e **me** chamar em cadeias de caracteres antes do número de telefone, em uma lista como esta:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="1b0ce-161">número de telefone 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="1b0ce-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="1b0ce-162">Telefone 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="1b0ce-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="1b0ce-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="1b0ce-163">45-124576532-123</span></span>

<span data-ttu-id="1b0ce-164">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-164">you can use this xml</span></span>

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

<span data-ttu-id="1b0ce-165">Por exemplo, para incluir  ocorrências  que têm cadeias de caracteres de cartão e cartão de crédito antes do número do cartão de crédito, em uma lista como esta:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="1b0ce-166">Cartão de crédito 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="1b0ce-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="1b0ce-167">45-124576532-123 (que pode ser número de telefone)</span><span class="sxs-lookup"><span data-stu-id="1b0ce-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="1b0ce-168">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-168">you can use this xml</span></span>

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

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="1b0ce-169">Sufixo TextMatchFilter</span><span class="sxs-lookup"><span data-stu-id="1b0ce-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="1b0ce-170">Descrição: permite definir os seguintes caracteres que devem ser sempre incluídos ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="1b0ce-171">Por exemplo, se o número do cartão de crédito for seguido por '/xuid', remova a match das combinações válidas.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="1b0ce-172">Por exemplo, as principais ocorrências de exclusão se houver mais cinco instâncias de quatro dígitos como sufixo em uma lista como esta:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="1b0ce-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="1b0ce-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="1b0ce-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="1b0ce-174">1234-5678-9321</span></span>

<span data-ttu-id="1b0ce-175">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="1b0ce-176">Por exemplo, para excluir ocorrências se elas são seguidas **por /xuidsuffix**, como uma desta lista:</span><span class="sxs-lookup"><span data-stu-id="1b0ce-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="1b0ce-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="1b0ce-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="1b0ce-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="1b0ce-178">1234-5678-9321</span></span>

<span data-ttu-id="1b0ce-179">você pode usar esse xml</span><span class="sxs-lookup"><span data-stu-id="1b0ce-179">you can use this xml</span></span>

<span data-ttu-id="1b0ce-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="1b0ce-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="1b0ce-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="1b0ce-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="1b0ce-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="1b0ce-182">/xuid</span></span></Term>
    <span data-ttu-id="1b0ce-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="1b0ce-183"></Group> </Keyword></span></span>
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

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="1b0ce-184">Usando filtros em pacotes de regras</span><span class="sxs-lookup"><span data-stu-id="1b0ce-184">Using filters in rule packages</span></span>

<span data-ttu-id="1b0ce-185">Os filtros podem ser definidos em todo o SIT ou em um padrão.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="1b0ce-186">Aqui estão alguns exemplos de trechos de código.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="1b0ce-187">No nível do tipo de informação confidenciais</span><span class="sxs-lookup"><span data-stu-id="1b0ce-187">At sensitive information type level</span></span>

<span data-ttu-id="1b0ce-188">Filtros em Entidade - abrange todos os padrões filho</span><span class="sxs-lookup"><span data-stu-id="1b0ce-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="1b0ce-189">Os filtros serão aplicados em **todas** as instâncias classificadas por qualquer um dos padrões nessa entidade/tipo confidencial</span><span class="sxs-lookup"><span data-stu-id="1b0ce-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="1b0ce-190">No padrão individual do nível de tipo de informação confidenciais</span><span class="sxs-lookup"><span data-stu-id="1b0ce-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="1b0ce-191">Filtra somente no nível de padrão.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="1b0ce-192">O filtro será aplicado nas instâncias que corresponderem ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="1b0ce-193">No nível do tipo de informação confidenciais e um filtro adicional em alguns dos padrões dessa entidade</span><span class="sxs-lookup"><span data-stu-id="1b0ce-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="1b0ce-194">Filtra em Entity + pattern</span><span class="sxs-lookup"><span data-stu-id="1b0ce-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="1b0ce-195">Os filtros serão aplicados **em** todas as instâncias classificadas por qualquer um dos padrões nessa entidade/tipo confidencial.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="1b0ce-196">O filtro de nível de padrão filtrará as instâncias que corresponderem a esse padrão.</span><span class="sxs-lookup"><span data-stu-id="1b0ce-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="1b0ce-197">Mais informações</span><span class="sxs-lookup"><span data-stu-id="1b0ce-197">More information</span></span>

- [<span data-ttu-id="1b0ce-198">Saiba mais sobre a prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="1b0ce-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="1b0ce-199">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="1b0ce-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="1b0ce-200">O que as funções DLP procuram</span><span class="sxs-lookup"><span data-stu-id="1b0ce-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
