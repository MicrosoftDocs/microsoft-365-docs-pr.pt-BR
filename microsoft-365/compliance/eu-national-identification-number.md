---
title: Número de identificação nacional da UE
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação nacional da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: 4dac77f129b45f457a82e709cb5a3b846a95cdf4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938757"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="44449-104">Número de identificação nacional da UE</span><span class="sxs-lookup"><span data-stu-id="44449-104">EU National Identification Number</span></span>

<span data-ttu-id="44449-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação nacional da UE.</span><span class="sxs-lookup"><span data-stu-id="44449-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="44449-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="44449-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="44449-107">Áustria</span><span class="sxs-lookup"><span data-stu-id="44449-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="44449-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-108">Format</span></span>

<span data-ttu-id="44449-109">Uma combinação de 24 caracteres de letras, dígitos e caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="44449-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-110">Pattern</span></span>

<span data-ttu-id="44449-111">24 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-111">24 characters:</span></span>
  
-  <span data-ttu-id="44449-112">22 letras (não diferencia maiúsculas de minúsculas), dígitos, barras invertidas, barras encaminhadas ou sinais de adição</span><span class="sxs-lookup"><span data-stu-id="44449-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="44449-113">Duas letras (não diferencia maiúsculas de minúsculas), dígitos, barras invertidas, barras invertidas, sinais de adição ou sinais de igual</span><span class="sxs-lookup"><span data-stu-id="44449-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-114">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-114">Checksum</span></span>

<span data-ttu-id="44449-115">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44449-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-116">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-116">Definition</span></span>

<span data-ttu-id="44449-117">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-118">A expressão `Regex_austria_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-119">Uma palavra- `Keywords_austria_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-120">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="44449-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="44449-122">número de identidade austríaca</span><span class="sxs-lookup"><span data-stu-id="44449-122">austrian identity number</span></span>
  
<span data-ttu-id="44449-123">número de identidade nacional</span><span class="sxs-lookup"><span data-stu-id="44449-123">national identity number</span></span>
  
<span data-ttu-id="44449-124">número de identidade</span><span class="sxs-lookup"><span data-stu-id="44449-124">identity number</span></span>
  
<span data-ttu-id="44449-125">national id</span><span class="sxs-lookup"><span data-stu-id="44449-125">national id</span></span>
  
<span data-ttu-id="44449-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="44449-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="44449-127">Bélgica</span><span class="sxs-lookup"><span data-stu-id="44449-127">Belgium</span></span>

<span data-ttu-id="44449-128">Para obter detalhes, consulte a seção "número nacional da Bélgica" em o [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="44449-129">Bulgária</span><span class="sxs-lookup"><span data-stu-id="44449-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="44449-130">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-130">Format</span></span>

<span data-ttu-id="44449-131">Dez dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44449-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-132">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-132">Pattern</span></span>

<span data-ttu-id="44449-133">Dez dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44449-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="44449-134">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="44449-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="44449-135">Dois dígitos que correspondem à ordem de nascimento</span><span class="sxs-lookup"><span data-stu-id="44449-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="44449-136">Um dígito que corresponde ao gênero: um dígito par para macho e um dígito estranho para o fêmea</span><span class="sxs-lookup"><span data-stu-id="44449-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="44449-137">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-138">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-138">Checksum</span></span>

<span data-ttu-id="44449-139">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-140">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-140">Definition</span></span>

<span data-ttu-id="44449-141">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-142">A função `Func_bulgaria_national_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-143">Uma palavra- `Keywords_bulgaria_national_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="44449-144">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-145">A função `Func_bulgaria_national_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-146">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="44449-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="44449-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="44449-148">egn</span><span class="sxs-lookup"><span data-stu-id="44449-148">egn</span></span>
  
<span data-ttu-id="44449-149">egn #</span><span class="sxs-lookup"><span data-stu-id="44449-149">egn#</span></span>
  
<span data-ttu-id="44449-150">número nacional búlgaro</span><span class="sxs-lookup"><span data-stu-id="44449-150">bulgarian national number</span></span>
  
<span data-ttu-id="44449-151">número nacional</span><span class="sxs-lookup"><span data-stu-id="44449-151">national number</span></span>
  
<span data-ttu-id="44449-152">social security number</span><span class="sxs-lookup"><span data-stu-id="44449-152">social security number</span></span>
  
<span data-ttu-id="44449-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="44449-153">nationalnumber#</span></span>
  
<span data-ttu-id="44449-154">es #</span><span class="sxs-lookup"><span data-stu-id="44449-154">ssn#</span></span>
  
<span data-ttu-id="44449-155">es</span><span class="sxs-lookup"><span data-stu-id="44449-155">ssn</span></span>
  
<span data-ttu-id="44449-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="44449-156">nationalnumber</span></span>
  
<span data-ttu-id="44449-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="44449-157">bnn#</span></span>
  
<span data-ttu-id="44449-158">bnn</span><span class="sxs-lookup"><span data-stu-id="44449-158">bnn</span></span>
  
<span data-ttu-id="44449-159">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-159">personal id number</span></span>
  
<span data-ttu-id="44449-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44449-160">personalidnumber#</span></span>
  
<span data-ttu-id="44449-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="44449-161">единен граждански номер</span></span>
  
<span data-ttu-id="44449-162">edinen grazhdanski de nome</span><span class="sxs-lookup"><span data-stu-id="44449-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="44449-163">егн</span><span class="sxs-lookup"><span data-stu-id="44449-163">егн</span></span>
  
<span data-ttu-id="44449-164">егн #</span><span class="sxs-lookup"><span data-stu-id="44449-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="44449-165">Croácia</span><span class="sxs-lookup"><span data-stu-id="44449-165">Croatia</span></span>

<span data-ttu-id="44449-166">Para obter detalhes, consulte a seção "número de identidade da Croácia" em o [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="44449-167">Chipre</span><span class="sxs-lookup"><span data-stu-id="44449-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="44449-168">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-168">Format</span></span>

<span data-ttu-id="44449-169">Dez dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44449-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-170">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-170">Pattern</span></span>

 <span data-ttu-id="44449-171">Dez dígitos</span><span class="sxs-lookup"><span data-stu-id="44449-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="44449-172">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-172">Checksum</span></span>

<span data-ttu-id="44449-173">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44449-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-174">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-174">Definition</span></span>

<span data-ttu-id="44449-175">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-176">A expressão `Regex_cyprus_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-177">Uma palavra- `Keywords_cyprus_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-178">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="44449-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="44449-180">número do cartão de identificação</span><span class="sxs-lookup"><span data-stu-id="44449-180">id card number</span></span>
  
<span data-ttu-id="44449-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="44449-181">national identification number</span></span>
  
<span data-ttu-id="44449-182">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-182">personal id number</span></span>
  
<span data-ttu-id="44449-183">número do cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="44449-183">identity card number</span></span>
  
<span data-ttu-id="44449-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="44449-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="44449-185">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="44449-185">Czech Republic</span></span>

<span data-ttu-id="44449-186">Para obter detalhes, consulte a seção "número de identidade nacional tcheco" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="44449-187">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="44449-187">Denmark</span></span>

<span data-ttu-id="44449-188">Para obter detalhes, consulte a seção "Dinamarca Personal Identification Number" em o [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="44449-189">Estônia</span><span class="sxs-lookup"><span data-stu-id="44449-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="44449-190">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-190">Format</span></span>

<span data-ttu-id="44449-191">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44449-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-192">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-192">Pattern</span></span>

<span data-ttu-id="44449-193">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44449-193">11 digits:</span></span>
  
- <span data-ttu-id="44449-194">Um dígito que corresponde ao sexo e ao século de nascimento (número ímpar masculino, mesmo número fêmea; 1-2:19 Century; 3-4:20 Century; 5-6:21 século)</span><span class="sxs-lookup"><span data-stu-id="44449-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="44449-195">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="44449-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="44449-196">Três dígitos que correspondem a um número de série separando as pessoas que nasceu na mesma data</span><span class="sxs-lookup"><span data-stu-id="44449-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="44449-197">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-198">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-198">Checksum</span></span>

<span data-ttu-id="44449-199">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-200">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-200">Definition</span></span>

<span data-ttu-id="44449-201">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-202">A função `Func_estonia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-203">Uma palavra- `Keywords_estonia_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="44449-204">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-205">A função `Func_estonia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-206">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="44449-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="44449-208">código de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-208">personal identification code</span></span>
  
<span data-ttu-id="44449-209">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-209">personal identification number</span></span>
  
<span data-ttu-id="44449-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="44449-210">national identification number</span></span>
  
<span data-ttu-id="44449-211">número nacional</span><span class="sxs-lookup"><span data-stu-id="44449-211">national number</span></span>
  
<span data-ttu-id="44449-212">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-212">personal id number</span></span>
  
<span data-ttu-id="44449-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44449-213">personalidnumber#</span></span>
  
<span data-ttu-id="44449-214">IKMover</span><span class="sxs-lookup"><span data-stu-id="44449-214">ik</span></span>
  
<span data-ttu-id="44449-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="44449-215">isikukood</span></span>
  
<span data-ttu-id="44449-216">ID-kaart</span><span class="sxs-lookup"><span data-stu-id="44449-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="44449-217">Finlândia</span><span class="sxs-lookup"><span data-stu-id="44449-217">Finland</span></span>

<span data-ttu-id="44449-218">Para obter detalhes, consulte a seção "ID nacional da Finlândia" em o [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="44449-219">França</span><span class="sxs-lookup"><span data-stu-id="44449-219">France</span></span>

<span data-ttu-id="44449-220">Para obter detalhes, consulte a seção "CNI (cartão de ID nacional da França)" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="44449-221">Alemanha</span><span class="sxs-lookup"><span data-stu-id="44449-221">Germany</span></span>

<span data-ttu-id="44449-222">Para obter detalhes, consulte a seção "número do cartão de identidade da Alemanha" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="44449-223">Grécia</span><span class="sxs-lookup"><span data-stu-id="44449-223">Greece</span></span>

<span data-ttu-id="44449-224">Para obter detalhes, consulte a seção "cartão de ID nacional da Grécia" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="44449-225">Hungria</span><span class="sxs-lookup"><span data-stu-id="44449-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="44449-226">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-226">Format</span></span>

<span data-ttu-id="44449-227">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="44449-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-228">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-228">Pattern</span></span>

<span data-ttu-id="44449-229">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44449-229">11 digits:</span></span>
  
-  <span data-ttu-id="44449-230">Um dígito que corresponde ao gênero (1-macho, 2-fêmea, outros números também são possíveis para o cidadãos nasceu antes 1900 ou cidadãos com cidadania dupla)</span><span class="sxs-lookup"><span data-stu-id="44449-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="44449-231">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="44449-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="44449-232">Três dígitos que correspondem a um número de série</span><span class="sxs-lookup"><span data-stu-id="44449-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="44449-233">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-234">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-234">Checksum</span></span>

<span data-ttu-id="44449-235">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-236">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-236">Definition</span></span>

<span data-ttu-id="44449-237">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-238">A função `Func_hungary_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-239">Uma palavra- `Keywords_hungary_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="44449-240">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-241">A função `Func_hungary_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-242">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="44449-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="44449-244">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-244">personal identification number</span></span>
  
<span data-ttu-id="44449-245">identification number</span><span class="sxs-lookup"><span data-stu-id="44449-245">identification number</span></span>
  
<span data-ttu-id="44449-246">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-246">personal id number</span></span>
  
<span data-ttu-id="44449-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="44449-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="44449-248">Irlanda</span><span class="sxs-lookup"><span data-stu-id="44449-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="44449-249">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-249">Format</span></span>

<span data-ttu-id="44449-250">Uma combinação de letras, dígitos e um espaço no padrão especificado de nove caracteres</span><span class="sxs-lookup"><span data-stu-id="44449-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-251">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-251">Pattern</span></span>

<span data-ttu-id="44449-252">Uma combinação de letras, dígitos e um espaço no padrão especificado de nove caracteres</span><span class="sxs-lookup"><span data-stu-id="44449-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="44449-253">De 1º de janeiro de 2013 até agora:</span><span class="sxs-lookup"><span data-stu-id="44449-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="44449-254">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44449-254">Seven digits</span></span> 
    
- <span data-ttu-id="44449-255">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-255">One check digit</span></span>
    
- <span data-ttu-id="44449-256">Um espaço ou a letra maiúscula "W" (diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="44449-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="44449-257">Antes de 1º de janeiro de 2013:</span><span class="sxs-lookup"><span data-stu-id="44449-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="44449-258">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44449-258">Seven digits</span></span> 
    
- <span data-ttu-id="44449-259">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-259">One check digit</span></span>
    
- <span data-ttu-id="44449-260">Um espaço ou uma letra maiúscula (diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="44449-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-261">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-261">Checksum</span></span>

<span data-ttu-id="44449-262">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-263">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-263">Definition</span></span>

<span data-ttu-id="44449-264">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-265">A função localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="44449-266">Uma palavra-chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-266">A keyword from is found.</span></span>
    
<span data-ttu-id="44449-267">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-268">A função localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-269">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="44449-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="44449-271">número de serviço público pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-271">personal public service number</span></span>
  
<span data-ttu-id="44449-272">PPS não</span><span class="sxs-lookup"><span data-stu-id="44449-272">pps no</span></span>
  
<span data-ttu-id="44449-273">número da receita e do seguro social</span><span class="sxs-lookup"><span data-stu-id="44449-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="44449-274">RSI não</span><span class="sxs-lookup"><span data-stu-id="44449-274">rsi no</span></span>
  
<span data-ttu-id="44449-275">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-275">personal identification number</span></span>
  
<span data-ttu-id="44449-276">identification number</span><span class="sxs-lookup"><span data-stu-id="44449-276">identification number</span></span>
  
<span data-ttu-id="44449-277">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-277">personal id number</span></span>
  
<span data-ttu-id="44449-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="44449-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="44449-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="44449-279">uimh.</span></span> <span data-ttu-id="44449-280">PSP</span><span class="sxs-lookup"><span data-stu-id="44449-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="44449-281">Itália</span><span class="sxs-lookup"><span data-stu-id="44449-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="44449-282">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-282">Format</span></span>

<span data-ttu-id="44449-283">Uma combinação de 16 caracteres de letras e dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="44449-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-284">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-284">Pattern</span></span>

<span data-ttu-id="44449-285">Uma combinação de letras e dígitos de 16 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="44449-286">Três letras que correspondem às três primeiras consoantes no nome da família</span><span class="sxs-lookup"><span data-stu-id="44449-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="44449-287">Três letras que correspondem à primeira, terceira e quarta consoantes no primeiro nome</span><span class="sxs-lookup"><span data-stu-id="44449-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="44449-288">Dois dígitos que correspondem aos últimos dígitos do ano de nascimento</span><span class="sxs-lookup"><span data-stu-id="44449-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="44449-289">Uma letra que corresponde à carta para o mês de nascimento-as letras são usadas em ordem alfabética, mas apenas as letras de a a E, H, L, M, P, R a T são usadas (dessa forma, Janeiro é A e outubro é R)</span><span class="sxs-lookup"><span data-stu-id="44449-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="44449-290">Dois dígitos que correspondem ao dia do mês de nascimento — para diferenciar entre sexos, 40 é adicionado ao dia de nascimento para mulheres</span><span class="sxs-lookup"><span data-stu-id="44449-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="44449-291">Quatro dígitos que correspondem ao código de área específico do município onde a pessoa nasceu (códigos de todo o país são usados para países estrangeiros)</span><span class="sxs-lookup"><span data-stu-id="44449-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="44449-292">Um dígito de paridade</span><span class="sxs-lookup"><span data-stu-id="44449-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-293">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-293">Checksum</span></span>

<span data-ttu-id="44449-294">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-295">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-295">Definition</span></span>

<span data-ttu-id="44449-296">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-297">A função `Func_italy_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-298">Uma palavra- `Keywords_italy_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="44449-299">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-300">A função `Func_italy_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-301">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="44449-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="44449-303">código pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-303">personal code</span></span>
  
<span data-ttu-id="44449-304">número de código pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-304">personal code number</span></span>
  
<span data-ttu-id="44449-305">número do certificado pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-305">personal certificate number</span></span>
  
<span data-ttu-id="44449-306">código fiscal</span><span class="sxs-lookup"><span data-stu-id="44449-306">fiscal code</span></span>
  
<span data-ttu-id="44449-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="44449-307">personalcodeno#</span></span>
  
<span data-ttu-id="44449-308">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-308">personal id number</span></span>
  
<span data-ttu-id="44449-309">código de ID pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-309">personal id code</span></span>
  
<span data-ttu-id="44449-310">pessoal do Codice</span><span class="sxs-lookup"><span data-stu-id="44449-310">codice personale</span></span>
  
<span data-ttu-id="44449-311">numero certificato pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-311">numero certificato personale</span></span>
  
<span data-ttu-id="44449-312">pessoal do numero</span><span class="sxs-lookup"><span data-stu-id="44449-312">numero personale</span></span>
  
<span data-ttu-id="44449-313">pessoal da ID numero</span><span class="sxs-lookup"><span data-stu-id="44449-313">numero id personale</span></span>
  
<span data-ttu-id="44449-314">pessoal da ID codice</span><span class="sxs-lookup"><span data-stu-id="44449-314">codice id personale</span></span>
  
<span data-ttu-id="44449-315">fiscalização codice</span><span class="sxs-lookup"><span data-stu-id="44449-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="44449-316">Letônia</span><span class="sxs-lookup"><span data-stu-id="44449-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="44449-317">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-317">Format</span></span>

<span data-ttu-id="44449-318">11 dígitos e um hífen no formato especificado</span><span class="sxs-lookup"><span data-stu-id="44449-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-319">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-319">Pattern</span></span>

<span data-ttu-id="44449-320">11 dígitos e um hífen:</span><span class="sxs-lookup"><span data-stu-id="44449-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="44449-321">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="44449-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="44449-322">Um hífen</span><span class="sxs-lookup"><span data-stu-id="44449-322">A hyphen</span></span>
    
- <span data-ttu-id="44449-323">Um dígito que corresponde ao século de nascimento ("0" para o século 19, "1" para o século 20 e "2" para o século 21)</span><span class="sxs-lookup"><span data-stu-id="44449-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="44449-324">Quatro dígitos, gerados aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="44449-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-325">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-325">Checksum</span></span>

<span data-ttu-id="44449-326">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-327">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-327">Definition</span></span>

<span data-ttu-id="44449-328">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-329">A função `Func_latvia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-330">Uma palavra- `Keywords_latvia_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="44449-331">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-332">A função `Func_latvia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-333">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="44449-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="44449-335">código pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-335">personal code</span></span>
  
<span data-ttu-id="44449-336">número de código pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-336">personal code number</span></span>
  
<span data-ttu-id="44449-337">número do certificado pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-337">personal certificate number</span></span>
  
<span data-ttu-id="44449-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="44449-338">personalcodeno#</span></span>
  
<span data-ttu-id="44449-339">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-339">personal id number</span></span>
  
<span data-ttu-id="44449-340">código de ID pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-340">personal id code</span></span>
  
<span data-ttu-id="44449-341">Kods personas</span><span class="sxs-lookup"><span data-stu-id="44449-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="44449-342">Lituânia</span><span class="sxs-lookup"><span data-stu-id="44449-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="44449-343">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-343">Format</span></span>

<span data-ttu-id="44449-344">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44449-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-345">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-345">Pattern</span></span>

<span data-ttu-id="44449-346">11 dígitos sem espaços e delimitadores:</span><span class="sxs-lookup"><span data-stu-id="44449-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="44449-347">Um dígito que corresponde ao sexo da pessoa e ao século de nascimento</span><span class="sxs-lookup"><span data-stu-id="44449-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="44449-348">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="44449-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="44449-349">Três dígitos que correspondem ao número de série da data de nascimento</span><span class="sxs-lookup"><span data-stu-id="44449-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="44449-350">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-351">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-351">Checksum</span></span>

<span data-ttu-id="44449-352">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-353">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-353">Definition</span></span>

<span data-ttu-id="44449-354">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-355">A função `Func_lithuania_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-356">Uma palavra- `Keywords_lithuania_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="44449-357">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-358">A função `Func_lithuania_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-359">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="44449-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="44449-361">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-361">personal numeric code</span></span>
  
<span data-ttu-id="44449-362">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-362">unique identification number</span></span>
  
<span data-ttu-id="44449-363">número do serviço do cidadão</span><span class="sxs-lookup"><span data-stu-id="44449-363">citizen service number</span></span>
  
<span data-ttu-id="44449-364">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-364">unique identity number</span></span>
  
<span data-ttu-id="44449-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="44449-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="44449-366">código pessoal.</span><span class="sxs-lookup"><span data-stu-id="44449-366">personal code.</span></span>
  
<span data-ttu-id="44449-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="44449-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="44449-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="44449-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="44449-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="44449-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="44449-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="44449-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="44449-371">kodas.</span><span class="sxs-lookup"><span data-stu-id="44449-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="44449-372">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="44449-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="44449-373">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-373">Format</span></span>

<span data-ttu-id="44449-374">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44449-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-375">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-375">Pattern</span></span>

<span data-ttu-id="44449-376">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="44449-376">11 digits</span></span>
  
- <span data-ttu-id="44449-377">Um dígito que corresponde ao sexo da pessoa e ao século de nascimento</span><span class="sxs-lookup"><span data-stu-id="44449-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="44449-378">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="44449-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="44449-379">Três dígitos que correspondem ao número de série da data de nascimento</span><span class="sxs-lookup"><span data-stu-id="44449-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="44449-380">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-381">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-381">Checksum</span></span>

<span data-ttu-id="44449-382">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44449-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-383">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-383">Definition</span></span>

<span data-ttu-id="44449-384">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-385">A expressão `Regex_luxemburg_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-386">Uma palavra- `Keywords_luxemburg_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-387">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="44449-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="44449-389">ID pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-389">personal id</span></span>
  
<span data-ttu-id="44449-390">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-390">personal id number</span></span>
  
<span data-ttu-id="44449-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="44449-391">personalidno#</span></span>
  
<span data-ttu-id="44449-392">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-392">unique id number</span></span>
  
<span data-ttu-id="44449-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44449-393">personalidnumber#</span></span>
  
<span data-ttu-id="44449-394">chave de ID exclusiva</span><span class="sxs-lookup"><span data-stu-id="44449-394">unique id key</span></span>
  
<span data-ttu-id="44449-395">código de ID pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-395">personal id code</span></span>
  
<span data-ttu-id="44449-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="44449-396">uniqueidkey#</span></span>
  
<span data-ttu-id="44449-397">código individual</span><span class="sxs-lookup"><span data-stu-id="44449-397">individual code</span></span>
  
<span data-ttu-id="44449-398">ID individual</span><span class="sxs-lookup"><span data-stu-id="44449-398">individual id</span></span>
  
<span data-ttu-id="44449-399">ID eindeutige-Nummer</span><span class="sxs-lookup"><span data-stu-id="44449-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="44449-400">ID eindeutige</span><span class="sxs-lookup"><span data-stu-id="44449-400">eindeutige id</span></span>
  
<span data-ttu-id="44449-401">ID personnelle</span><span class="sxs-lookup"><span data-stu-id="44449-401">id personnelle</span></span>
  
<span data-ttu-id="44449-402">Numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="44449-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="44449-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="44449-403">idpersonnelle#</span></span>
  
<span data-ttu-id="44449-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="44449-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="44449-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="44449-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="44449-406">Malta</span><span class="sxs-lookup"><span data-stu-id="44449-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="44449-407">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-407">Format</span></span>

<span data-ttu-id="44449-408">Sete dígitos seguidos de uma letra</span><span class="sxs-lookup"><span data-stu-id="44449-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-409">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-409">Pattern</span></span>

<span data-ttu-id="44449-410">Sete dígitos seguidos de uma letra:</span><span class="sxs-lookup"><span data-stu-id="44449-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="44449-411">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44449-411">Seven digits</span></span> 
    
- <span data-ttu-id="44449-412">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44449-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-413">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-413">Checksum</span></span>

<span data-ttu-id="44449-414">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44449-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-415">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-415">Definition</span></span>

<span data-ttu-id="44449-416">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-417">A expressão `Regex_malta_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-418">Uma palavra- `Keywords_malta_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="44449-419">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-420">A expressão `Regex_malta_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-421">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="44449-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="44449-423">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-423">personal numeric code</span></span>
  
<span data-ttu-id="44449-424">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-424">unique identification number</span></span>
  
<span data-ttu-id="44449-425">número do serviço do cidadão</span><span class="sxs-lookup"><span data-stu-id="44449-425">citizen service number</span></span>
  
<span data-ttu-id="44449-426">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-426">unique identity number</span></span>
  
<span data-ttu-id="44449-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="44449-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="44449-428">Kodiċi numerali pessoali</span><span class="sxs-lookup"><span data-stu-id="44449-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="44449-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="44449-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="44449-430">numru tas-servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="44449-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="44449-431">numru ta ' Identità uniku</span><span class="sxs-lookup"><span data-stu-id="44449-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="44449-432">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="44449-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="44449-433">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-433">Format</span></span>

<span data-ttu-id="44449-434">Nove dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44449-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-435">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-435">Pattern</span></span>

<span data-ttu-id="44449-436">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="44449-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44449-437">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-437">Checksum</span></span>

<span data-ttu-id="44449-438">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-439">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-439">Definition</span></span>

<span data-ttu-id="44449-440">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-441">A função `Func_netherlands_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-442">Uma palavra-chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-442">A keyword from is found.</span></span>
    
<span data-ttu-id="44449-443">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-444">A função `Func_netherlands_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-445">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="44449-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="44449-447">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-447">personal numeric code</span></span>
  
<span data-ttu-id="44449-448">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-448">unique identification number</span></span>
  
<span data-ttu-id="44449-449">número do serviço do cidadão</span><span class="sxs-lookup"><span data-stu-id="44449-449">citizen service number</span></span>
  
<span data-ttu-id="44449-450">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-450">unique identity number</span></span>
  
<span data-ttu-id="44449-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="44449-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="44449-452">BSN</span><span class="sxs-lookup"><span data-stu-id="44449-452">bsn</span></span>
  
<span data-ttu-id="44449-453">BSN #</span><span class="sxs-lookup"><span data-stu-id="44449-453">bsn#</span></span>
  
<span data-ttu-id="44449-454">código de numerieke persoonlijke</span><span class="sxs-lookup"><span data-stu-id="44449-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="44449-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="44449-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="44449-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="44449-456">burgerservicenummer</span></span>
  
<span data-ttu-id="44449-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="44449-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="44449-458">Polônia</span><span class="sxs-lookup"><span data-stu-id="44449-458">Poland</span></span>

<span data-ttu-id="44449-459">Para obter detalhes, consulte a seção "ID nacional da Polônia (PESEL)" em [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="44449-460">Portugal</span><span class="sxs-lookup"><span data-stu-id="44449-460">Portugal</span></span>

<span data-ttu-id="44449-461">Para obter detalhes, consulte a seção "número de cartão de cidadão da Portugal" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="44449-462">Romênia</span><span class="sxs-lookup"><span data-stu-id="44449-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="44449-463">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-463">Format</span></span>

<span data-ttu-id="44449-464">13 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44449-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-465">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-465">Pattern</span></span>

<span data-ttu-id="44449-466">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="44449-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44449-467">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-467">Checksum</span></span>

<span data-ttu-id="44449-468">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-469">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-469">Definition</span></span>

<span data-ttu-id="44449-470">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-471">A função `Func_romania_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-472">Uma palavra- `Keywords_romania_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="44449-473">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-474">A função `Func_romania_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-475">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="44449-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="44449-477">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-477">personal numeric code</span></span>
  
<span data-ttu-id="44449-478">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-478">unique identification number</span></span>
  
<span data-ttu-id="44449-479">cnp</span><span class="sxs-lookup"><span data-stu-id="44449-479">cnp</span></span>
  
<span data-ttu-id="44449-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="44449-480">cnp#</span></span>
  
<span data-ttu-id="44449-481">pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-481">pin</span></span>
  
<span data-ttu-id="44449-482">pessoal #</span><span class="sxs-lookup"><span data-stu-id="44449-482">pin#</span></span>
  
<span data-ttu-id="44449-483">número de seguro</span><span class="sxs-lookup"><span data-stu-id="44449-483">insurance number</span></span>
  
<span data-ttu-id="44449-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="44449-484">insurancenumber#</span></span>
  
<span data-ttu-id="44449-485">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-485">unique identity number</span></span>
  
<span data-ttu-id="44449-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="44449-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="44449-487">c.o.d. numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-487">cod numeric personal</span></span>
  
<span data-ttu-id="44449-488">identificare de c.o.d. pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-488">cod identificare personal</span></span>
  
<span data-ttu-id="44449-489">UNIC de c.o.d. identificare</span><span class="sxs-lookup"><span data-stu-id="44449-489">cod unic identificare</span></span>
  
<span data-ttu-id="44449-490">număr pessoal do UNIC</span><span class="sxs-lookup"><span data-stu-id="44449-490">număr personal unic</span></span>
  
<span data-ttu-id="44449-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="44449-491">număr identitate</span></span>
  
<span data-ttu-id="44449-492">număr identificare pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-492">număr identificare personal</span></span>
  
<span data-ttu-id="44449-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="44449-493">număridentitate#</span></span>
  
<span data-ttu-id="44449-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="44449-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="44449-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="44449-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="44449-496">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="44449-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="44449-497">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-497">Format</span></span>

<span data-ttu-id="44449-498">Dez dígitos contendo uma barra invertida</span><span class="sxs-lookup"><span data-stu-id="44449-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-499">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-499">Pattern</span></span>

<span data-ttu-id="44449-500">Dez dígitos contendo uma barra invertida:</span><span class="sxs-lookup"><span data-stu-id="44449-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44449-501">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-501">Checksum</span></span>

<span data-ttu-id="44449-502">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-503">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-503">Definition</span></span>

<span data-ttu-id="44449-504">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-505">A função `Func_slovakia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-506">Uma palavra- `Keywords_slovakia_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="44449-507">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-508">A função `Func_slovakia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-509">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="44449-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="44449-511">número de nascimento</span><span class="sxs-lookup"><span data-stu-id="44449-511">birth number</span></span>
  
<span data-ttu-id="44449-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="44449-512">national identification number</span></span>
  
<span data-ttu-id="44449-513">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-513">personal identification number</span></span>
  
<span data-ttu-id="44449-514">social security number</span><span class="sxs-lookup"><span data-stu-id="44449-514">social security number</span></span>
  
<span data-ttu-id="44449-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="44449-515">nationalnumber#</span></span>
  
<span data-ttu-id="44449-516">es #</span><span class="sxs-lookup"><span data-stu-id="44449-516">ssn#</span></span>
  
<span data-ttu-id="44449-517">es</span><span class="sxs-lookup"><span data-stu-id="44449-517">ssn</span></span>
  
<span data-ttu-id="44449-518">número nacional</span><span class="sxs-lookup"><span data-stu-id="44449-518">national number</span></span>
  
<span data-ttu-id="44449-519">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-519">personal id number</span></span>
  
<span data-ttu-id="44449-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44449-520">personalidnumber#</span></span>
  
<span data-ttu-id="44449-521">rč</span><span class="sxs-lookup"><span data-stu-id="44449-521">rč</span></span>
  
<span data-ttu-id="44449-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="44449-522">rodné číslo</span></span>
  
<span data-ttu-id="44449-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="44449-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="44449-524">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="44449-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="44449-525">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-525">Format</span></span>

<span data-ttu-id="44449-526">13 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44449-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-527">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-527">Pattern</span></span>

<span data-ttu-id="44449-528">13 dígitos no padrão especificado:</span><span class="sxs-lookup"><span data-stu-id="44449-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="44449-529">Sete dígitos que correspondem à data de nascimento (DDMMLLL), onde "LLL" corresponde aos últimos três dígitos do ano de nascimento</span><span class="sxs-lookup"><span data-stu-id="44449-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="44449-530">Dois dígitos que correspondem à área de nascimento</span><span class="sxs-lookup"><span data-stu-id="44449-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="44449-531">Três dígitos que correspondem a uma combinação de sexo e número de série para pessoas nasceu no mesmo dia (000-499 para macho e 500-999 para fêmea)</span><span class="sxs-lookup"><span data-stu-id="44449-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="44449-532">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-533">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-533">Checksum</span></span>

<span data-ttu-id="44449-534">Sim</span><span class="sxs-lookup"><span data-stu-id="44449-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-535">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-535">Definition</span></span>

<span data-ttu-id="44449-536">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-537">A função `Func_slovenia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-538">Uma palavra- `Keywords_slovenia_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="44449-539">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-540">A função `Func_slovenia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-541">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="44449-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="44449-543">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-543">personal numeric code</span></span>
  
<span data-ttu-id="44449-544">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-544">unique identification number</span></span>
  
<span data-ttu-id="44449-545">número de registro exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-545">unique registration number</span></span>
  
<span data-ttu-id="44449-546">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-546">unique identity number</span></span>
  
<span data-ttu-id="44449-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="44449-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="44449-548">número de cidadão mestre exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-548">unique master citizen number</span></span>
  
<span data-ttu-id="44449-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="44449-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="44449-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="44449-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="44449-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="44449-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="44449-552">emšo</span><span class="sxs-lookup"><span data-stu-id="44449-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="44449-553">Espanha</span><span class="sxs-lookup"><span data-stu-id="44449-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="44449-554">Formatar</span><span class="sxs-lookup"><span data-stu-id="44449-554">Format</span></span>

<span data-ttu-id="44449-555">Sete dígitos seguidos de um caractere</span><span class="sxs-lookup"><span data-stu-id="44449-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44449-556">Padrão</span><span class="sxs-lookup"><span data-stu-id="44449-556">Pattern</span></span>

<span data-ttu-id="44449-557">Sete dígitos seguidos de um caractere</span><span class="sxs-lookup"><span data-stu-id="44449-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="44449-558">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44449-558">Seven digits</span></span>
    
- <span data-ttu-id="44449-559">Um dígito ou letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44449-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44449-560">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44449-560">Checksum</span></span>

<span data-ttu-id="44449-561">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44449-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44449-562">Definição</span><span class="sxs-lookup"><span data-stu-id="44449-562">Definition</span></span>

<span data-ttu-id="44449-563">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44449-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44449-564">A expressão `Regex_spain_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44449-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44449-565">Uma palavra- `Keywords_spain_eu_national_id_card"` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44449-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44449-566">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44449-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="44449-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="44449-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="44449-568">dni</span><span class="sxs-lookup"><span data-stu-id="44449-568">dni</span></span>
  
<span data-ttu-id="44449-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="44449-569">national identification number</span></span>
  
<span data-ttu-id="44449-570">número de identidade nacional</span><span class="sxs-lookup"><span data-stu-id="44449-570">national identity number</span></span>
  
<span data-ttu-id="44449-571">número de seguro</span><span class="sxs-lookup"><span data-stu-id="44449-571">insurance number</span></span>
  
<span data-ttu-id="44449-572">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44449-572">personal identification number</span></span>
  
<span data-ttu-id="44449-573">identidade nacional</span><span class="sxs-lookup"><span data-stu-id="44449-573">national identity</span></span>
  
<span data-ttu-id="44449-574">identidade pessoal não</span><span class="sxs-lookup"><span data-stu-id="44449-574">personal identity no</span></span>
  
<span data-ttu-id="44449-575">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="44449-575">unique identity number</span></span>
  
<span data-ttu-id="44449-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="44449-576">nationalidno#</span></span>
  
<span data-ttu-id="44449-577">UniqueId #</span><span class="sxs-lookup"><span data-stu-id="44449-577">uniqueid#</span></span>
  
<span data-ttu-id="44449-578">dni #</span><span class="sxs-lookup"><span data-stu-id="44449-578">dni#</span></span>
  
<span data-ttu-id="44449-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="44449-579">nationalid#</span></span>
  
<span data-ttu-id="44449-580">nie #</span><span class="sxs-lookup"><span data-stu-id="44449-580">nie#</span></span>
  
<span data-ttu-id="44449-581">nie</span><span class="sxs-lookup"><span data-stu-id="44449-581">nie</span></span>
  
<span data-ttu-id="44449-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="44449-582">nienúmero#</span></span>
  
<span data-ttu-id="44449-583">Nie número</span><span class="sxs-lookup"><span data-stu-id="44449-583">nie número</span></span>
  
<span data-ttu-id="44449-584">documento nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="44449-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="44449-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="44449-585">identidad único</span></span>
  
<span data-ttu-id="44449-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="44449-586">número nacional identidad</span></span>
  
<span data-ttu-id="44449-587">DNI número</span><span class="sxs-lookup"><span data-stu-id="44449-587">dni número</span></span>
  
<span data-ttu-id="44449-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="44449-588">dninúmero#</span></span>
  
<span data-ttu-id="44449-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="44449-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="44449-590">Suécia</span><span class="sxs-lookup"><span data-stu-id="44449-590">Sweden</span></span>

<span data-ttu-id="44449-591">Para obter detalhes, consulte a seção "ID nacional da Suécia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44449-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44449-592">Confira também</span><span class="sxs-lookup"><span data-stu-id="44449-592">See also</span></span>

[<span data-ttu-id="44449-593">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="44449-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

