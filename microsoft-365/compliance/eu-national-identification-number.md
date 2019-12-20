---
title: Número de identificação nacional da UE
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação nacional da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: c00619ed649db53777fa3629deac0162a3589475
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805934"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="7da1e-104">Número de identificação nacional da UE</span><span class="sxs-lookup"><span data-stu-id="7da1e-104">EU National Identification Number</span></span>

<span data-ttu-id="7da1e-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação nacional da UE.</span><span class="sxs-lookup"><span data-stu-id="7da1e-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="7da1e-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="7da1e-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="7da1e-107">Áustria</span><span class="sxs-lookup"><span data-stu-id="7da1e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-108">Format</span></span>

<span data-ttu-id="7da1e-109">Uma combinação de 24 caracteres de letras, dígitos e caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="7da1e-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-110">Pattern</span></span>

<span data-ttu-id="7da1e-111">24 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-111">24 characters:</span></span>
  
-  <span data-ttu-id="7da1e-112">22 letras (não diferencia maiúsculas de minúsculas), dígitos, barras invertidas, barras encaminhadas ou sinais de adição</span><span class="sxs-lookup"><span data-stu-id="7da1e-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="7da1e-113">Duas letras (não diferencia maiúsculas de minúsculas), dígitos, barras invertidas, barras invertidas, sinais de adição ou sinais de igual</span><span class="sxs-lookup"><span data-stu-id="7da1e-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-114">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-114">Checksum</span></span>

<span data-ttu-id="7da1e-115">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="7da1e-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-116">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-116">Definition</span></span>

<span data-ttu-id="7da1e-117">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-118">A expressão `Regex_austria_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-119">Uma palavra- `Keywords_austria_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7da1e-120">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="7da1e-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-122">número de identidade austríaca</span><span class="sxs-lookup"><span data-stu-id="7da1e-122">austrian identity number</span></span>
  
<span data-ttu-id="7da1e-123">número de identidade nacional</span><span class="sxs-lookup"><span data-stu-id="7da1e-123">national identity number</span></span>
  
<span data-ttu-id="7da1e-124">número de identidade</span><span class="sxs-lookup"><span data-stu-id="7da1e-124">identity number</span></span>
  
<span data-ttu-id="7da1e-125">national id</span><span class="sxs-lookup"><span data-stu-id="7da1e-125">national id</span></span>
  
<span data-ttu-id="7da1e-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="7da1e-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="7da1e-127">Bélgica</span><span class="sxs-lookup"><span data-stu-id="7da1e-127">Belgium</span></span>

<span data-ttu-id="7da1e-128">Para obter detalhes, consulte a seção "número nacional da Bélgica" em o [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="7da1e-129">Bulgária</span><span class="sxs-lookup"><span data-stu-id="7da1e-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-130">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-130">Format</span></span>

<span data-ttu-id="7da1e-131">Dez dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="7da1e-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-132">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-132">Pattern</span></span>

<span data-ttu-id="7da1e-133">Dez dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="7da1e-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="7da1e-134">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="7da1e-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="7da1e-135">Dois dígitos que correspondem à ordem de nascimento</span><span class="sxs-lookup"><span data-stu-id="7da1e-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="7da1e-136">Um dígito que corresponde ao gênero: um dígito par para macho e um dígito estranho para o fêmea</span><span class="sxs-lookup"><span data-stu-id="7da1e-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="7da1e-137">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-138">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-138">Checksum</span></span>

<span data-ttu-id="7da1e-139">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-140">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-140">Definition</span></span>

<span data-ttu-id="7da1e-141">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-142">A função `Func_bulgaria_national_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-143">Uma palavra- `Keywords_bulgaria_national_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="7da1e-144">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-145">A função `Func_bulgaria_national_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-146">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="7da1e-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="7da1e-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="7da1e-148">egn</span><span class="sxs-lookup"><span data-stu-id="7da1e-148">egn</span></span>
  
<span data-ttu-id="7da1e-149">egn #</span><span class="sxs-lookup"><span data-stu-id="7da1e-149">egn#</span></span>
  
<span data-ttu-id="7da1e-150">número nacional búlgaro</span><span class="sxs-lookup"><span data-stu-id="7da1e-150">bulgarian national number</span></span>
  
<span data-ttu-id="7da1e-151">número nacional</span><span class="sxs-lookup"><span data-stu-id="7da1e-151">national number</span></span>
  
<span data-ttu-id="7da1e-152">social security number</span><span class="sxs-lookup"><span data-stu-id="7da1e-152">social security number</span></span>
  
<span data-ttu-id="7da1e-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="7da1e-153">nationalnumber#</span></span>
  
<span data-ttu-id="7da1e-154">es #</span><span class="sxs-lookup"><span data-stu-id="7da1e-154">ssn#</span></span>
  
<span data-ttu-id="7da1e-155">es</span><span class="sxs-lookup"><span data-stu-id="7da1e-155">ssn</span></span>
  
<span data-ttu-id="7da1e-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="7da1e-156">nationalnumber</span></span>
  
<span data-ttu-id="7da1e-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="7da1e-157">bnn#</span></span>
  
<span data-ttu-id="7da1e-158">bnn</span><span class="sxs-lookup"><span data-stu-id="7da1e-158">bnn</span></span>
  
<span data-ttu-id="7da1e-159">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-159">personal id number</span></span>
  
<span data-ttu-id="7da1e-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7da1e-160">personalidnumber#</span></span>
  
<span data-ttu-id="7da1e-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="7da1e-161">единен граждански номер</span></span>
  
<span data-ttu-id="7da1e-162">edinen grazhdanski de nome</span><span class="sxs-lookup"><span data-stu-id="7da1e-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="7da1e-163">егн</span><span class="sxs-lookup"><span data-stu-id="7da1e-163">егн</span></span>
  
<span data-ttu-id="7da1e-164">егн #</span><span class="sxs-lookup"><span data-stu-id="7da1e-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="7da1e-165">Croácia</span><span class="sxs-lookup"><span data-stu-id="7da1e-165">Croatia</span></span>

<span data-ttu-id="7da1e-166">Para obter detalhes, consulte a seção "número de identidade da Croácia" em o [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="7da1e-167">Chipre</span><span class="sxs-lookup"><span data-stu-id="7da1e-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-168">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-168">Format</span></span>

<span data-ttu-id="7da1e-169">Dez dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="7da1e-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-170">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-170">Pattern</span></span>

 <span data-ttu-id="7da1e-171">Dez dígitos</span><span class="sxs-lookup"><span data-stu-id="7da1e-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="7da1e-172">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-172">Checksum</span></span>

<span data-ttu-id="7da1e-173">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="7da1e-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-174">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-174">Definition</span></span>

<span data-ttu-id="7da1e-175">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-176">A expressão `Regex_cyprus_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-177">Uma palavra- `Keywords_cyprus_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7da1e-178">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="7da1e-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-180">número do cartão de identificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-180">id card number</span></span>
  
<span data-ttu-id="7da1e-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="7da1e-181">national identification number</span></span>
  
<span data-ttu-id="7da1e-182">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-182">personal id number</span></span>
  
<span data-ttu-id="7da1e-183">número do cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="7da1e-183">identity card number</span></span>
  
<span data-ttu-id="7da1e-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="7da1e-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="7da1e-185">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="7da1e-185">Czech Republic</span></span>

<span data-ttu-id="7da1e-186">Para obter detalhes, consulte a seção "número de identidade nacional tcheco" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="7da1e-187">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="7da1e-187">Denmark</span></span>

<span data-ttu-id="7da1e-188">Para obter detalhes, consulte a seção "Dinamarca Personal Identification Number" em o [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="7da1e-189">Estônia</span><span class="sxs-lookup"><span data-stu-id="7da1e-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-190">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-190">Format</span></span>

<span data-ttu-id="7da1e-191">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="7da1e-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-192">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-192">Pattern</span></span>

<span data-ttu-id="7da1e-193">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="7da1e-193">11 digits:</span></span>
  
- <span data-ttu-id="7da1e-194">Um dígito que corresponde ao sexo e ao século de nascimento (número ímpar masculino, mesmo número fêmea; 1-2:19 Century; 3-4:20 Century; 5-6:21 século)</span><span class="sxs-lookup"><span data-stu-id="7da1e-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="7da1e-195">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="7da1e-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="7da1e-196">Três dígitos que correspondem a um número de série separando as pessoas que nasceu na mesma data</span><span class="sxs-lookup"><span data-stu-id="7da1e-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="7da1e-197">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-198">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-198">Checksum</span></span>

<span data-ttu-id="7da1e-199">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-200">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-200">Definition</span></span>

<span data-ttu-id="7da1e-201">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-202">A função `Func_estonia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-203">Uma palavra- `Keywords_estonia_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="7da1e-204">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-205">A função `Func_estonia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-206">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="7da1e-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-208">código de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-208">personal identification code</span></span>
  
<span data-ttu-id="7da1e-209">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-209">personal identification number</span></span>
  
<span data-ttu-id="7da1e-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="7da1e-210">national identification number</span></span>
  
<span data-ttu-id="7da1e-211">número nacional</span><span class="sxs-lookup"><span data-stu-id="7da1e-211">national number</span></span>
  
<span data-ttu-id="7da1e-212">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-212">personal id number</span></span>
  
<span data-ttu-id="7da1e-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7da1e-213">personalidnumber#</span></span>
  
<span data-ttu-id="7da1e-214">IKMover</span><span class="sxs-lookup"><span data-stu-id="7da1e-214">ik</span></span>
  
<span data-ttu-id="7da1e-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="7da1e-215">isikukood</span></span>
  
<span data-ttu-id="7da1e-216">ID-kaart</span><span class="sxs-lookup"><span data-stu-id="7da1e-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="7da1e-217">Finlândia</span><span class="sxs-lookup"><span data-stu-id="7da1e-217">Finland</span></span>

<span data-ttu-id="7da1e-218">Para obter detalhes, consulte a seção "ID nacional da Finlândia" em o [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="7da1e-219">França</span><span class="sxs-lookup"><span data-stu-id="7da1e-219">France</span></span>

<span data-ttu-id="7da1e-220">Para obter detalhes, consulte a seção "CNI (cartão de ID nacional da França)" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="7da1e-221">Alemanha</span><span class="sxs-lookup"><span data-stu-id="7da1e-221">Germany</span></span>

<span data-ttu-id="7da1e-222">Para obter detalhes, consulte a seção "número do cartão de identidade da Alemanha" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="7da1e-223">Grécia</span><span class="sxs-lookup"><span data-stu-id="7da1e-223">Greece</span></span>

<span data-ttu-id="7da1e-224">Para obter detalhes, consulte a seção "cartão de ID nacional da Grécia" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="7da1e-225">Hungria</span><span class="sxs-lookup"><span data-stu-id="7da1e-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-226">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-226">Format</span></span>

<span data-ttu-id="7da1e-227">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="7da1e-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-228">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-228">Pattern</span></span>

<span data-ttu-id="7da1e-229">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="7da1e-229">11 digits:</span></span>
  
-  <span data-ttu-id="7da1e-230">Um dígito que corresponde ao gênero (1-macho, 2-fêmea, outros números também são possíveis para o cidadãos nasceu antes 1900 ou cidadãos com cidadania dupla)</span><span class="sxs-lookup"><span data-stu-id="7da1e-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="7da1e-231">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="7da1e-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="7da1e-232">Três dígitos que correspondem a um número de série</span><span class="sxs-lookup"><span data-stu-id="7da1e-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="7da1e-233">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-234">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-234">Checksum</span></span>

<span data-ttu-id="7da1e-235">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-236">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-236">Definition</span></span>

<span data-ttu-id="7da1e-237">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-238">A função `Func_hungary_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-239">Uma palavra- `Keywords_hungary_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="7da1e-240">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-241">A função `Func_hungary_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-242">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="7da1e-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-244">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-244">personal identification number</span></span>
  
<span data-ttu-id="7da1e-245">identification number</span><span class="sxs-lookup"><span data-stu-id="7da1e-245">identification number</span></span>
  
<span data-ttu-id="7da1e-246">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-246">personal id number</span></span>
  
<span data-ttu-id="7da1e-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="7da1e-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="7da1e-248">Irlanda</span><span class="sxs-lookup"><span data-stu-id="7da1e-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-249">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-249">Format</span></span>

<span data-ttu-id="7da1e-250">Uma combinação de letras, dígitos e um espaço no padrão especificado de nove caracteres</span><span class="sxs-lookup"><span data-stu-id="7da1e-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-251">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-251">Pattern</span></span>

<span data-ttu-id="7da1e-252">Uma combinação de letras, dígitos e um espaço no padrão especificado de nove caracteres</span><span class="sxs-lookup"><span data-stu-id="7da1e-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="7da1e-253">De 1º de janeiro de 2013 até agora:</span><span class="sxs-lookup"><span data-stu-id="7da1e-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="7da1e-254">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="7da1e-254">Seven digits</span></span> 
    
- <span data-ttu-id="7da1e-255">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-255">One check digit</span></span>
    
- <span data-ttu-id="7da1e-256">Um espaço ou a letra maiúscula "W" (diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="7da1e-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="7da1e-257">Antes de 1º de janeiro de 2013:</span><span class="sxs-lookup"><span data-stu-id="7da1e-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="7da1e-258">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="7da1e-258">Seven digits</span></span> 
    
- <span data-ttu-id="7da1e-259">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-259">One check digit</span></span>
    
- <span data-ttu-id="7da1e-260">Um espaço ou uma letra maiúscula (diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="7da1e-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-261">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-261">Checksum</span></span>

<span data-ttu-id="7da1e-262">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-263">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-263">Definition</span></span>

<span data-ttu-id="7da1e-264">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-265">A função localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="7da1e-266">Uma palavra-chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-266">A keyword from is found.</span></span>
    
<span data-ttu-id="7da1e-267">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-268">A função localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-268">The function finds content that matches the pattern.</span></span>
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-269">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="7da1e-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-271">número de serviço público pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-271">personal public service number</span></span>
  
<span data-ttu-id="7da1e-272">PPS não</span><span class="sxs-lookup"><span data-stu-id="7da1e-272">pps no</span></span>
  
<span data-ttu-id="7da1e-273">número da receita e do seguro social</span><span class="sxs-lookup"><span data-stu-id="7da1e-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="7da1e-274">RSI não</span><span class="sxs-lookup"><span data-stu-id="7da1e-274">rsi no</span></span>
  
<span data-ttu-id="7da1e-275">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-275">personal identification number</span></span>
  
<span data-ttu-id="7da1e-276">identification number</span><span class="sxs-lookup"><span data-stu-id="7da1e-276">identification number</span></span>
  
<span data-ttu-id="7da1e-277">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-277">personal id number</span></span>
  
<span data-ttu-id="7da1e-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="7da1e-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="7da1e-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="7da1e-279">uimh.</span></span> <span data-ttu-id="7da1e-280">PSP</span><span class="sxs-lookup"><span data-stu-id="7da1e-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="7da1e-281">Itália</span><span class="sxs-lookup"><span data-stu-id="7da1e-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-282">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-282">Format</span></span>

<span data-ttu-id="7da1e-283">Uma combinação de 16 caracteres de letras e dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="7da1e-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-284">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-284">Pattern</span></span>

<span data-ttu-id="7da1e-285">Uma combinação de letras e dígitos de 16 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="7da1e-286">Três letras que correspondem às três primeiras consoantes no nome da família</span><span class="sxs-lookup"><span data-stu-id="7da1e-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="7da1e-287">Três letras que correspondem à primeira, terceira e quarta consoantes no primeiro nome</span><span class="sxs-lookup"><span data-stu-id="7da1e-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="7da1e-288">Dois dígitos que correspondem aos últimos dígitos do ano de nascimento</span><span class="sxs-lookup"><span data-stu-id="7da1e-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="7da1e-289">Uma letra que corresponde à carta para o mês de nascimento-as letras são usadas em ordem alfabética, mas apenas as letras de a a E, H, L, M, P, R a T são usadas (dessa forma, Janeiro é A e outubro é R)</span><span class="sxs-lookup"><span data-stu-id="7da1e-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="7da1e-290">Dois dígitos que correspondem ao dia do mês de nascimento — para diferenciar entre sexos, 40 é adicionado ao dia de nascimento para mulheres</span><span class="sxs-lookup"><span data-stu-id="7da1e-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="7da1e-291">Quatro dígitos que correspondem ao código de área específico do município onde a pessoa nasceu (códigos de todo o país são usados para países estrangeiros)</span><span class="sxs-lookup"><span data-stu-id="7da1e-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="7da1e-292">Um dígito de paridade</span><span class="sxs-lookup"><span data-stu-id="7da1e-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-293">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-293">Checksum</span></span>

<span data-ttu-id="7da1e-294">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-295">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-295">Definition</span></span>

<span data-ttu-id="7da1e-296">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-297">A função `Func_italy_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-298">Uma palavra- `Keywords_italy_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="7da1e-299">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-300">A função `Func_italy_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-301">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="7da1e-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-303">código pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-303">personal code</span></span>
  
<span data-ttu-id="7da1e-304">número de código pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-304">personal code number</span></span>
  
<span data-ttu-id="7da1e-305">número do certificado pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-305">personal certificate number</span></span>
  
<span data-ttu-id="7da1e-306">código fiscal</span><span class="sxs-lookup"><span data-stu-id="7da1e-306">fiscal code</span></span>
  
<span data-ttu-id="7da1e-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-307">personalcodeno#</span></span>
  
<span data-ttu-id="7da1e-308">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-308">personal id number</span></span>
  
<span data-ttu-id="7da1e-309">código de ID pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-309">personal id code</span></span>
  
<span data-ttu-id="7da1e-310">pessoal do Codice</span><span class="sxs-lookup"><span data-stu-id="7da1e-310">codice personale</span></span>
  
<span data-ttu-id="7da1e-311">numero certificato pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-311">numero certificato personale</span></span>
  
<span data-ttu-id="7da1e-312">pessoal do numero</span><span class="sxs-lookup"><span data-stu-id="7da1e-312">numero personale</span></span>
  
<span data-ttu-id="7da1e-313">pessoal da ID numero</span><span class="sxs-lookup"><span data-stu-id="7da1e-313">numero id personale</span></span>
  
<span data-ttu-id="7da1e-314">pessoal da ID codice</span><span class="sxs-lookup"><span data-stu-id="7da1e-314">codice id personale</span></span>
  
<span data-ttu-id="7da1e-315">fiscalização codice</span><span class="sxs-lookup"><span data-stu-id="7da1e-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="7da1e-316">Letônia</span><span class="sxs-lookup"><span data-stu-id="7da1e-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-317">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-317">Format</span></span>

<span data-ttu-id="7da1e-318">11 dígitos e um hífen no formato especificado</span><span class="sxs-lookup"><span data-stu-id="7da1e-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-319">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-319">Pattern</span></span>

<span data-ttu-id="7da1e-320">11 dígitos e um hífen:</span><span class="sxs-lookup"><span data-stu-id="7da1e-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="7da1e-321">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="7da1e-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="7da1e-322">Um hífen</span><span class="sxs-lookup"><span data-stu-id="7da1e-322">A hyphen</span></span>
    
- <span data-ttu-id="7da1e-323">Um dígito que corresponde ao século de nascimento ("0" para o século 19, "1" para o século 20 e "2" para o século 21)</span><span class="sxs-lookup"><span data-stu-id="7da1e-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="7da1e-324">Quatro dígitos, gerados aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="7da1e-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-325">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-325">Checksum</span></span>

<span data-ttu-id="7da1e-326">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-327">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-327">Definition</span></span>

<span data-ttu-id="7da1e-328">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-329">A função `Func_latvia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-330">Uma palavra- `Keywords_latvia_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="7da1e-331">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-332">A função `Func_latvia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-333">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="7da1e-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-335">código pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-335">personal code</span></span>
  
<span data-ttu-id="7da1e-336">número de código pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-336">personal code number</span></span>
  
<span data-ttu-id="7da1e-337">número do certificado pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-337">personal certificate number</span></span>
  
<span data-ttu-id="7da1e-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-338">personalcodeno#</span></span>
  
<span data-ttu-id="7da1e-339">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-339">personal id number</span></span>
  
<span data-ttu-id="7da1e-340">código de ID pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-340">personal id code</span></span>
  
<span data-ttu-id="7da1e-341">Kods personas</span><span class="sxs-lookup"><span data-stu-id="7da1e-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="7da1e-342">Lituânia</span><span class="sxs-lookup"><span data-stu-id="7da1e-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-343">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-343">Format</span></span>

<span data-ttu-id="7da1e-344">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="7da1e-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-345">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-345">Pattern</span></span>

<span data-ttu-id="7da1e-346">11 dígitos sem espaços e delimitadores:</span><span class="sxs-lookup"><span data-stu-id="7da1e-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="7da1e-347">Um dígito que corresponde ao sexo da pessoa e ao século de nascimento</span><span class="sxs-lookup"><span data-stu-id="7da1e-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="7da1e-348">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="7da1e-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="7da1e-349">Três dígitos que correspondem ao número de série da data de nascimento</span><span class="sxs-lookup"><span data-stu-id="7da1e-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="7da1e-350">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-351">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-351">Checksum</span></span>

<span data-ttu-id="7da1e-352">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-353">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-353">Definition</span></span>

<span data-ttu-id="7da1e-354">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-355">A função `Func_lithuania_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-356">Uma palavra- `Keywords_lithuania_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="7da1e-357">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-358">A função `Func_lithuania_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-359">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="7da1e-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-361">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-361">personal numeric code</span></span>
  
<span data-ttu-id="7da1e-362">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-362">unique identification number</span></span>
  
<span data-ttu-id="7da1e-363">número do serviço do cidadão</span><span class="sxs-lookup"><span data-stu-id="7da1e-363">citizen service number</span></span>
  
<span data-ttu-id="7da1e-364">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-364">unique identity number</span></span>
  
<span data-ttu-id="7da1e-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="7da1e-366">código pessoal.</span><span class="sxs-lookup"><span data-stu-id="7da1e-366">personal code.</span></span>
  
<span data-ttu-id="7da1e-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="7da1e-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="7da1e-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="7da1e-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="7da1e-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="7da1e-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="7da1e-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="7da1e-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="7da1e-371">kodas.</span><span class="sxs-lookup"><span data-stu-id="7da1e-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="7da1e-372">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="7da1e-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-373">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-373">Format</span></span>

<span data-ttu-id="7da1e-374">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="7da1e-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-375">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-375">Pattern</span></span>

<span data-ttu-id="7da1e-376">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="7da1e-376">11 digits</span></span>
  
- <span data-ttu-id="7da1e-377">Um dígito que corresponde ao sexo da pessoa e ao século de nascimento</span><span class="sxs-lookup"><span data-stu-id="7da1e-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="7da1e-378">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="7da1e-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="7da1e-379">Três dígitos que correspondem ao número de série da data de nascimento</span><span class="sxs-lookup"><span data-stu-id="7da1e-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="7da1e-380">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-381">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-381">Checksum</span></span>

<span data-ttu-id="7da1e-382">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="7da1e-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-383">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-383">Definition</span></span>

<span data-ttu-id="7da1e-384">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-385">A expressão `Regex_luxemburg_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-386">Uma palavra- `Keywords_luxemburg_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7da1e-387">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="7da1e-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-389">ID pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-389">personal id</span></span>
  
<span data-ttu-id="7da1e-390">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-390">personal id number</span></span>
  
<span data-ttu-id="7da1e-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-391">personalidno#</span></span>
  
<span data-ttu-id="7da1e-392">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-392">unique id number</span></span>
  
<span data-ttu-id="7da1e-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7da1e-393">personalidnumber#</span></span>
  
<span data-ttu-id="7da1e-394">chave de ID exclusiva</span><span class="sxs-lookup"><span data-stu-id="7da1e-394">unique id key</span></span>
  
<span data-ttu-id="7da1e-395">código de ID pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-395">personal id code</span></span>
  
<span data-ttu-id="7da1e-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="7da1e-396">uniqueidkey#</span></span>
  
<span data-ttu-id="7da1e-397">código individual</span><span class="sxs-lookup"><span data-stu-id="7da1e-397">individual code</span></span>
  
<span data-ttu-id="7da1e-398">ID individual</span><span class="sxs-lookup"><span data-stu-id="7da1e-398">individual id</span></span>
  
<span data-ttu-id="7da1e-399">ID eindeutige-Nummer</span><span class="sxs-lookup"><span data-stu-id="7da1e-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="7da1e-400">ID eindeutige</span><span class="sxs-lookup"><span data-stu-id="7da1e-400">eindeutige id</span></span>
  
<span data-ttu-id="7da1e-401">ID personnelle</span><span class="sxs-lookup"><span data-stu-id="7da1e-401">id personnelle</span></span>
  
<span data-ttu-id="7da1e-402">Numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="7da1e-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="7da1e-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="7da1e-403">idpersonnelle#</span></span>
  
<span data-ttu-id="7da1e-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7da1e-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="7da1e-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="7da1e-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="7da1e-406">Malta</span><span class="sxs-lookup"><span data-stu-id="7da1e-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-407">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-407">Format</span></span>

<span data-ttu-id="7da1e-408">Sete dígitos seguidos de uma letra</span><span class="sxs-lookup"><span data-stu-id="7da1e-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-409">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-409">Pattern</span></span>

<span data-ttu-id="7da1e-410">Sete dígitos seguidos de uma letra:</span><span class="sxs-lookup"><span data-stu-id="7da1e-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="7da1e-411">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="7da1e-411">Seven digits</span></span> 
    
- <span data-ttu-id="7da1e-412">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="7da1e-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-413">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-413">Checksum</span></span>

<span data-ttu-id="7da1e-414">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="7da1e-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-415">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-415">Definition</span></span>

<span data-ttu-id="7da1e-416">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-417">A expressão `Regex_malta_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-418">Uma palavra- `Keywords_malta_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="7da1e-419">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-420">A expressão `Regex_malta_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-421">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="7da1e-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-423">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-423">personal numeric code</span></span>
  
<span data-ttu-id="7da1e-424">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-424">unique identification number</span></span>
  
<span data-ttu-id="7da1e-425">número do serviço do cidadão</span><span class="sxs-lookup"><span data-stu-id="7da1e-425">citizen service number</span></span>
  
<span data-ttu-id="7da1e-426">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-426">unique identity number</span></span>
  
<span data-ttu-id="7da1e-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="7da1e-428">Kodiċi numerali pessoali</span><span class="sxs-lookup"><span data-stu-id="7da1e-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="7da1e-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="7da1e-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="7da1e-430">numru tas-servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="7da1e-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="7da1e-431">numru ta ' Identità uniku</span><span class="sxs-lookup"><span data-stu-id="7da1e-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="7da1e-432">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="7da1e-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-433">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-433">Format</span></span>

<span data-ttu-id="7da1e-434">Nove dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="7da1e-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-435">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-435">Pattern</span></span>

<span data-ttu-id="7da1e-436">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="7da1e-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7da1e-437">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-437">Checksum</span></span>

<span data-ttu-id="7da1e-438">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-439">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-439">Definition</span></span>

<span data-ttu-id="7da1e-440">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-441">A função `Func_netherlands_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-442">Uma palavra-chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-442">A keyword from is found.</span></span>
    
<span data-ttu-id="7da1e-443">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-444">A função `Func_netherlands_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-445">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="7da1e-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-447">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-447">personal numeric code</span></span>
  
<span data-ttu-id="7da1e-448">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-448">unique identification number</span></span>
  
<span data-ttu-id="7da1e-449">número do serviço do cidadão</span><span class="sxs-lookup"><span data-stu-id="7da1e-449">citizen service number</span></span>
  
<span data-ttu-id="7da1e-450">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-450">unique identity number</span></span>
  
<span data-ttu-id="7da1e-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="7da1e-452">BSN</span><span class="sxs-lookup"><span data-stu-id="7da1e-452">bsn</span></span>
  
<span data-ttu-id="7da1e-453">BSN #</span><span class="sxs-lookup"><span data-stu-id="7da1e-453">bsn#</span></span>
  
<span data-ttu-id="7da1e-454">código de numerieke persoonlijke</span><span class="sxs-lookup"><span data-stu-id="7da1e-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="7da1e-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="7da1e-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="7da1e-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="7da1e-456">burgerservicenummer</span></span>
  
<span data-ttu-id="7da1e-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="7da1e-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="7da1e-458">Polônia</span><span class="sxs-lookup"><span data-stu-id="7da1e-458">Poland</span></span>

<span data-ttu-id="7da1e-459">Para obter detalhes, consulte a seção "ID nacional da Polônia (PESEL)" em [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="7da1e-460">Portugal</span><span class="sxs-lookup"><span data-stu-id="7da1e-460">Portugal</span></span>

<span data-ttu-id="7da1e-461">Para obter detalhes, consulte a seção "número de cartão de cidadão da Portugal" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="7da1e-462">Romênia</span><span class="sxs-lookup"><span data-stu-id="7da1e-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-463">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-463">Format</span></span>

<span data-ttu-id="7da1e-464">13 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="7da1e-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-465">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-465">Pattern</span></span>

<span data-ttu-id="7da1e-466">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="7da1e-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7da1e-467">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-467">Checksum</span></span>

<span data-ttu-id="7da1e-468">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-469">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-469">Definition</span></span>

<span data-ttu-id="7da1e-470">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-471">A função `Func_romania_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-472">Uma palavra- `Keywords_romania_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="7da1e-473">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-474">A função `Func_romania_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-475">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="7da1e-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-477">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-477">personal numeric code</span></span>
  
<span data-ttu-id="7da1e-478">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-478">unique identification number</span></span>
  
<span data-ttu-id="7da1e-479">cnp</span><span class="sxs-lookup"><span data-stu-id="7da1e-479">cnp</span></span>
  
<span data-ttu-id="7da1e-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="7da1e-480">cnp#</span></span>
  
<span data-ttu-id="7da1e-481">pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-481">pin</span></span>
  
<span data-ttu-id="7da1e-482">pessoal #</span><span class="sxs-lookup"><span data-stu-id="7da1e-482">pin#</span></span>
  
<span data-ttu-id="7da1e-483">número de seguro</span><span class="sxs-lookup"><span data-stu-id="7da1e-483">insurance number</span></span>
  
<span data-ttu-id="7da1e-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="7da1e-484">insurancenumber#</span></span>
  
<span data-ttu-id="7da1e-485">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-485">unique identity number</span></span>
  
<span data-ttu-id="7da1e-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="7da1e-487">c.o.d. numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-487">cod numeric personal</span></span>
  
<span data-ttu-id="7da1e-488">identificare de c.o.d. pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-488">cod identificare personal</span></span>
  
<span data-ttu-id="7da1e-489">UNIC de c.o.d. identificare</span><span class="sxs-lookup"><span data-stu-id="7da1e-489">cod unic identificare</span></span>
  
<span data-ttu-id="7da1e-490">număr pessoal do UNIC</span><span class="sxs-lookup"><span data-stu-id="7da1e-490">număr personal unic</span></span>
  
<span data-ttu-id="7da1e-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="7da1e-491">număr identitate</span></span>
  
<span data-ttu-id="7da1e-492">număr identificare pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-492">număr identificare personal</span></span>
  
<span data-ttu-id="7da1e-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="7da1e-493">număridentitate#</span></span>
  
<span data-ttu-id="7da1e-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="7da1e-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="7da1e-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="7da1e-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="7da1e-496">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="7da1e-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-497">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-497">Format</span></span>

<span data-ttu-id="7da1e-498">Dez dígitos contendo uma barra invertida</span><span class="sxs-lookup"><span data-stu-id="7da1e-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-499">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-499">Pattern</span></span>

<span data-ttu-id="7da1e-500">Dez dígitos contendo uma barra invertida:</span><span class="sxs-lookup"><span data-stu-id="7da1e-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7da1e-501">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-501">Checksum</span></span>

<span data-ttu-id="7da1e-502">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-503">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-503">Definition</span></span>

<span data-ttu-id="7da1e-504">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-505">A função `Func_slovakia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-506">Uma palavra- `Keywords_slovakia_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="7da1e-507">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-508">A função `Func_slovakia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-509">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="7da1e-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-511">número de nascimento</span><span class="sxs-lookup"><span data-stu-id="7da1e-511">birth number</span></span>
  
<span data-ttu-id="7da1e-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="7da1e-512">national identification number</span></span>
  
<span data-ttu-id="7da1e-513">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-513">personal identification number</span></span>
  
<span data-ttu-id="7da1e-514">social security number</span><span class="sxs-lookup"><span data-stu-id="7da1e-514">social security number</span></span>
  
<span data-ttu-id="7da1e-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="7da1e-515">nationalnumber#</span></span>
  
<span data-ttu-id="7da1e-516">es #</span><span class="sxs-lookup"><span data-stu-id="7da1e-516">ssn#</span></span>
  
<span data-ttu-id="7da1e-517">es</span><span class="sxs-lookup"><span data-stu-id="7da1e-517">ssn</span></span>
  
<span data-ttu-id="7da1e-518">número nacional</span><span class="sxs-lookup"><span data-stu-id="7da1e-518">national number</span></span>
  
<span data-ttu-id="7da1e-519">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-519">personal id number</span></span>
  
<span data-ttu-id="7da1e-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7da1e-520">personalidnumber#</span></span>
  
<span data-ttu-id="7da1e-521">rč</span><span class="sxs-lookup"><span data-stu-id="7da1e-521">rč</span></span>
  
<span data-ttu-id="7da1e-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="7da1e-522">rodné číslo</span></span>
  
<span data-ttu-id="7da1e-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="7da1e-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="7da1e-524">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="7da1e-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-525">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-525">Format</span></span>

<span data-ttu-id="7da1e-526">13 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="7da1e-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-527">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-527">Pattern</span></span>

<span data-ttu-id="7da1e-528">13 dígitos no padrão especificado:</span><span class="sxs-lookup"><span data-stu-id="7da1e-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="7da1e-529">Sete dígitos que correspondem à data de nascimento (DDMMLLL), onde "LLL" corresponde aos últimos três dígitos do ano de nascimento</span><span class="sxs-lookup"><span data-stu-id="7da1e-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="7da1e-530">Dois dígitos que correspondem à área de nascimento</span><span class="sxs-lookup"><span data-stu-id="7da1e-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="7da1e-531">Três dígitos que correspondem a uma combinação de sexo e número de série para pessoas nasceu no mesmo dia (000-499 para macho e 500-999 para fêmea)</span><span class="sxs-lookup"><span data-stu-id="7da1e-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="7da1e-532">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-533">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-533">Checksum</span></span>

<span data-ttu-id="7da1e-534">Sim</span><span class="sxs-lookup"><span data-stu-id="7da1e-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-535">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-535">Definition</span></span>

<span data-ttu-id="7da1e-536">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-537">A função `Func_slovenia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-538">Uma palavra- `Keywords_slovenia_eu_national_id_card` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="7da1e-539">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-540">A função `Func_slovenia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="7da1e-541">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="7da1e-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-543">código numérico pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-543">personal numeric code</span></span>
  
<span data-ttu-id="7da1e-544">número de identificação exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-544">unique identification number</span></span>
  
<span data-ttu-id="7da1e-545">número de registro exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-545">unique registration number</span></span>
  
<span data-ttu-id="7da1e-546">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-546">unique identity number</span></span>
  
<span data-ttu-id="7da1e-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="7da1e-548">número de cidadão mestre exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-548">unique master citizen number</span></span>
  
<span data-ttu-id="7da1e-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="7da1e-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="7da1e-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="7da1e-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="7da1e-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="7da1e-552">emšo</span><span class="sxs-lookup"><span data-stu-id="7da1e-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="7da1e-553">Espanha</span><span class="sxs-lookup"><span data-stu-id="7da1e-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="7da1e-554">Formatar</span><span class="sxs-lookup"><span data-stu-id="7da1e-554">Format</span></span>

<span data-ttu-id="7da1e-555">Sete dígitos seguidos de um caractere</span><span class="sxs-lookup"><span data-stu-id="7da1e-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7da1e-556">Padrão</span><span class="sxs-lookup"><span data-stu-id="7da1e-556">Pattern</span></span>

<span data-ttu-id="7da1e-557">Sete dígitos seguidos de um caractere</span><span class="sxs-lookup"><span data-stu-id="7da1e-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="7da1e-558">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="7da1e-558">Seven digits</span></span>
    
- <span data-ttu-id="7da1e-559">Um dígito ou letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="7da1e-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7da1e-560">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="7da1e-560">Checksum</span></span>

<span data-ttu-id="7da1e-561">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="7da1e-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7da1e-562">Definição</span><span class="sxs-lookup"><span data-stu-id="7da1e-562">Definition</span></span>

<span data-ttu-id="7da1e-563">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="7da1e-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7da1e-564">A expressão `Regex_spain_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="7da1e-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7da1e-565">Uma palavra- `Keywords_spain_eu_national_id_card"` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="7da1e-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7da1e-566">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7da1e-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="7da1e-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="7da1e-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="7da1e-568">dni</span><span class="sxs-lookup"><span data-stu-id="7da1e-568">dni</span></span>
  
<span data-ttu-id="7da1e-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="7da1e-569">national identification number</span></span>
  
<span data-ttu-id="7da1e-570">número de identidade nacional</span><span class="sxs-lookup"><span data-stu-id="7da1e-570">national identity number</span></span>
  
<span data-ttu-id="7da1e-571">número de seguro</span><span class="sxs-lookup"><span data-stu-id="7da1e-571">insurance number</span></span>
  
<span data-ttu-id="7da1e-572">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="7da1e-572">personal identification number</span></span>
  
<span data-ttu-id="7da1e-573">identidade nacional</span><span class="sxs-lookup"><span data-stu-id="7da1e-573">national identity</span></span>
  
<span data-ttu-id="7da1e-574">identidade pessoal não</span><span class="sxs-lookup"><span data-stu-id="7da1e-574">personal identity no</span></span>
  
<span data-ttu-id="7da1e-575">número de identidade exclusivo</span><span class="sxs-lookup"><span data-stu-id="7da1e-575">unique identity number</span></span>
  
<span data-ttu-id="7da1e-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="7da1e-576">nationalidno#</span></span>
  
<span data-ttu-id="7da1e-577">UniqueId #</span><span class="sxs-lookup"><span data-stu-id="7da1e-577">uniqueid#</span></span>
  
<span data-ttu-id="7da1e-578">dni #</span><span class="sxs-lookup"><span data-stu-id="7da1e-578">dni#</span></span>
  
<span data-ttu-id="7da1e-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="7da1e-579">nationalid#</span></span>
  
<span data-ttu-id="7da1e-580">nie #</span><span class="sxs-lookup"><span data-stu-id="7da1e-580">nie#</span></span>
  
<span data-ttu-id="7da1e-581">nie</span><span class="sxs-lookup"><span data-stu-id="7da1e-581">nie</span></span>
  
<span data-ttu-id="7da1e-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="7da1e-582">nienúmero#</span></span>
  
<span data-ttu-id="7da1e-583">Nie número</span><span class="sxs-lookup"><span data-stu-id="7da1e-583">nie número</span></span>
  
<span data-ttu-id="7da1e-584">documento nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="7da1e-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="7da1e-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="7da1e-585">identidad único</span></span>
  
<span data-ttu-id="7da1e-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="7da1e-586">número nacional identidad</span></span>
  
<span data-ttu-id="7da1e-587">DNI número</span><span class="sxs-lookup"><span data-stu-id="7da1e-587">dni número</span></span>
  
<span data-ttu-id="7da1e-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="7da1e-588">dninúmero#</span></span>
  
<span data-ttu-id="7da1e-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="7da1e-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="7da1e-590">Suécia</span><span class="sxs-lookup"><span data-stu-id="7da1e-590">Sweden</span></span>

<span data-ttu-id="7da1e-591">Para obter detalhes, consulte a seção "ID nacional da Suécia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7da1e-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7da1e-592">Confira também</span><span class="sxs-lookup"><span data-stu-id="7da1e-592">See also</span></span>

[<span data-ttu-id="7da1e-593">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="7da1e-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

