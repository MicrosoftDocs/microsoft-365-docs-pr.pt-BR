---
title: Número de seguro social da UE ou ID equivalente
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
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o número de segurança social da UE ou o tipo de informação confidencial de ID equivalente. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: 276b9f2d20c2c682df2a2072c1103ab9fc67a098
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938689"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="bbc96-104">Número de seguro social da UE ou ID equivalente</span><span class="sxs-lookup"><span data-stu-id="bbc96-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="bbc96-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o número de segurança social da UE (SSN) ou o tipo de informação confidencial de ID equivalente.</span><span class="sxs-lookup"><span data-stu-id="bbc96-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="bbc96-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="bbc96-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="bbc96-107">Áustria</span><span class="sxs-lookup"><span data-stu-id="bbc96-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="bbc96-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="bbc96-108">Format</span></span>

<span data-ttu-id="bbc96-109">10 dígitos no formato especificado</span><span class="sxs-lookup"><span data-stu-id="bbc96-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bbc96-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="bbc96-110">Pattern</span></span>

<span data-ttu-id="bbc96-111">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="bbc96-111">10 digits:</span></span>
  
-  <span data-ttu-id="bbc96-112">Três dígitos que correspondem a um número de série</span><span class="sxs-lookup"><span data-stu-id="bbc96-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="bbc96-113">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-113">One check digit</span></span>
    
- <span data-ttu-id="bbc96-114">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="bbc96-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bbc96-115">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-115">Checksum</span></span>

<span data-ttu-id="bbc96-116">Sim</span><span class="sxs-lookup"><span data-stu-id="bbc96-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bbc96-117">Definição</span><span class="sxs-lookup"><span data-stu-id="bbc96-117">Definition</span></span>

<span data-ttu-id="bbc96-118">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-119">A função `Func_austria_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bbc96-120">Uma palavra- `Keywords_austria_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="bbc96-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bbc96-121">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-122">A função `Func_austria_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bbc96-123">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="bbc96-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="bbc96-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bbc96-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bbc96-125">segurança social não</span><span class="sxs-lookup"><span data-stu-id="bbc96-125">social security no</span></span>
  
<span data-ttu-id="bbc96-126">social security number</span><span class="sxs-lookup"><span data-stu-id="bbc96-126">social security number</span></span>
  
<span data-ttu-id="bbc96-127">social security code</span><span class="sxs-lookup"><span data-stu-id="bbc96-127">social security code</span></span>
  
<span data-ttu-id="bbc96-128">número de seguro</span><span class="sxs-lookup"><span data-stu-id="bbc96-128">insurance number</span></span>
  
<span data-ttu-id="bbc96-129">SSN austríaco</span><span class="sxs-lookup"><span data-stu-id="bbc96-129">austrian ssn</span></span>
  
<span data-ttu-id="bbc96-130">es #</span><span class="sxs-lookup"><span data-stu-id="bbc96-130">ssn#</span></span>
  
<span data-ttu-id="bbc96-131">es</span><span class="sxs-lookup"><span data-stu-id="bbc96-131">ssn</span></span>
  
<span data-ttu-id="bbc96-132">código de seguro</span><span class="sxs-lookup"><span data-stu-id="bbc96-132">insurance code</span></span>
  
<span data-ttu-id="bbc96-133">código de seguro #</span><span class="sxs-lookup"><span data-stu-id="bbc96-133">insurance code#</span></span>
  
<span data-ttu-id="bbc96-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="bbc96-134">socialsecurityno#</span></span>
  
<span data-ttu-id="bbc96-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="bbc96-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="bbc96-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="bbc96-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="bbc96-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="bbc96-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="bbc96-138">Bélgica</span><span class="sxs-lookup"><span data-stu-id="bbc96-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="bbc96-139">Formatar</span><span class="sxs-lookup"><span data-stu-id="bbc96-139">Format</span></span>

<span data-ttu-id="bbc96-140">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="bbc96-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bbc96-141">Padrão</span><span class="sxs-lookup"><span data-stu-id="bbc96-141">Pattern</span></span>

<span data-ttu-id="bbc96-142">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="bbc96-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="bbc96-143">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-143">Checksum</span></span>

<span data-ttu-id="bbc96-144">Sim</span><span class="sxs-lookup"><span data-stu-id="bbc96-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bbc96-145">Definição</span><span class="sxs-lookup"><span data-stu-id="bbc96-145">Definition</span></span>

<span data-ttu-id="bbc96-146">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-147">A função `Func_belgium_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bbc96-148">Uma palavra- `Keywords_belgium_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="bbc96-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bbc96-149">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-150">A função `Func_belgium_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bbc96-151">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="bbc96-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="bbc96-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bbc96-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bbc96-153">número Nacional belga</span><span class="sxs-lookup"><span data-stu-id="bbc96-153">belgian national number</span></span>
  
<span data-ttu-id="bbc96-154">número nacional</span><span class="sxs-lookup"><span data-stu-id="bbc96-154">national number</span></span>
  
<span data-ttu-id="bbc96-155">social security number</span><span class="sxs-lookup"><span data-stu-id="bbc96-155">social security number</span></span>
  
<span data-ttu-id="bbc96-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-156">nationalnumber#</span></span>
  
<span data-ttu-id="bbc96-157">es #</span><span class="sxs-lookup"><span data-stu-id="bbc96-157">ssn#</span></span>
  
<span data-ttu-id="bbc96-158">es</span><span class="sxs-lookup"><span data-stu-id="bbc96-158">ssn</span></span>
  
<span data-ttu-id="bbc96-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="bbc96-159">nationalnumber</span></span>
  
<span data-ttu-id="bbc96-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="bbc96-160">bnn#</span></span>
  
<span data-ttu-id="bbc96-161">bnn</span><span class="sxs-lookup"><span data-stu-id="bbc96-161">bnn</span></span>
  
<span data-ttu-id="bbc96-162">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-162">personal id number</span></span>
  
<span data-ttu-id="bbc96-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-163">personalidnumber#</span></span>
  
<span data-ttu-id="bbc96-164">nacional Numéro</span><span class="sxs-lookup"><span data-stu-id="bbc96-164">numéro national</span></span>
  
<span data-ttu-id="bbc96-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="bbc96-165">numéro de sécurité</span></span>
  
<span data-ttu-id="bbc96-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="bbc96-166">numéro d'assuré</span></span>
  
<span data-ttu-id="bbc96-167">nacional de identificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-167">identifiant national</span></span>
  
<span data-ttu-id="bbc96-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="bbc96-168">identifiantnational#</span></span>
  
<span data-ttu-id="bbc96-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="bbc96-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="bbc96-170">Croácia</span><span class="sxs-lookup"><span data-stu-id="bbc96-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="bbc96-171">Formatar</span><span class="sxs-lookup"><span data-stu-id="bbc96-171">Format</span></span>

<span data-ttu-id="bbc96-172">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="bbc96-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bbc96-173">Padrão</span><span class="sxs-lookup"><span data-stu-id="bbc96-173">Pattern</span></span>

 <span data-ttu-id="bbc96-174">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="bbc96-174">11 digits:</span></span> 
  
-  <span data-ttu-id="bbc96-175">Dez dígitos</span><span class="sxs-lookup"><span data-stu-id="bbc96-175">Ten digits</span></span> 
    
- <span data-ttu-id="bbc96-176">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bbc96-177">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-177">Checksum</span></span>

<span data-ttu-id="bbc96-178">Sim</span><span class="sxs-lookup"><span data-stu-id="bbc96-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bbc96-179">Definição</span><span class="sxs-lookup"><span data-stu-id="bbc96-179">Definition</span></span>

<span data-ttu-id="bbc96-180">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-181">A função `Func_croatia_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bbc96-182">Uma palavra- `Keywords_croatia_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="bbc96-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bbc96-183">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-184">A função `Func_croatia_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bbc96-185">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="bbc96-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="bbc96-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bbc96-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bbc96-187">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-187">personal identification number</span></span>
  
<span data-ttu-id="bbc96-188">número do cidadão mestre</span><span class="sxs-lookup"><span data-stu-id="bbc96-188">master citizen number</span></span>
  
<span data-ttu-id="bbc96-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="bbc96-189">national identification number</span></span>
  
<span data-ttu-id="bbc96-190">social security number</span><span class="sxs-lookup"><span data-stu-id="bbc96-190">social security number</span></span>
  
<span data-ttu-id="bbc96-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-191">nationalnumber#</span></span>
  
<span data-ttu-id="bbc96-192">es #</span><span class="sxs-lookup"><span data-stu-id="bbc96-192">ssn#</span></span>
  
<span data-ttu-id="bbc96-193">es</span><span class="sxs-lookup"><span data-stu-id="bbc96-193">ssn</span></span>
  
<span data-ttu-id="bbc96-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="bbc96-194">nationalnumber</span></span>
  
<span data-ttu-id="bbc96-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="bbc96-195">bnn#</span></span>
  
<span data-ttu-id="bbc96-196">bnn</span><span class="sxs-lookup"><span data-stu-id="bbc96-196">bnn</span></span>
  
<span data-ttu-id="bbc96-197">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-197">personal id number</span></span>
  
<span data-ttu-id="bbc96-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-198">personalidnumber#</span></span>
  
<span data-ttu-id="bbc96-199">NIB</span><span class="sxs-lookup"><span data-stu-id="bbc96-199">oib</span></span>
  
<span data-ttu-id="bbc96-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="bbc96-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="bbc96-201">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="bbc96-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="bbc96-202">Formatar</span><span class="sxs-lookup"><span data-stu-id="bbc96-202">Format</span></span>

<span data-ttu-id="bbc96-203">Dez dígitos e uma barra invertida no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="bbc96-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bbc96-204">Padrão</span><span class="sxs-lookup"><span data-stu-id="bbc96-204">Pattern</span></span>

<span data-ttu-id="bbc96-205">Dez dígitos e uma barra invertida:</span><span class="sxs-lookup"><span data-stu-id="bbc96-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="bbc96-206">Seis dígitos que correspondem à data de nascimento (AAMMDD):</span><span class="sxs-lookup"><span data-stu-id="bbc96-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="bbc96-207">Uma barra invertida</span><span class="sxs-lookup"><span data-stu-id="bbc96-207">A backslash</span></span>
    
- <span data-ttu-id="bbc96-208">Três dígitos que correspondem a um número de série que separa as pessoas nasceu na mesma data</span><span class="sxs-lookup"><span data-stu-id="bbc96-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="bbc96-209">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bbc96-210">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-210">Checksum</span></span>

<span data-ttu-id="bbc96-211">Sim</span><span class="sxs-lookup"><span data-stu-id="bbc96-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bbc96-212">Definição</span><span class="sxs-lookup"><span data-stu-id="bbc96-212">Definition</span></span>

<span data-ttu-id="bbc96-213">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-214">A função `Func_czech_republic_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bbc96-215">Uma palavra- `Keywords_czech_republic_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="bbc96-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bbc96-216">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-217">A função `Func_czech_republic_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bbc96-218">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="bbc96-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="bbc96-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bbc96-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bbc96-220">número de nascimento</span><span class="sxs-lookup"><span data-stu-id="bbc96-220">birth number</span></span>
  
<span data-ttu-id="bbc96-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="bbc96-221">national identification number</span></span>
  
<span data-ttu-id="bbc96-222">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-222">personal identification number</span></span>
  
<span data-ttu-id="bbc96-223">social security number</span><span class="sxs-lookup"><span data-stu-id="bbc96-223">social security number</span></span>
  
<span data-ttu-id="bbc96-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-224">nationalnumber#</span></span>
  
<span data-ttu-id="bbc96-225">es #</span><span class="sxs-lookup"><span data-stu-id="bbc96-225">ssn#</span></span>
  
<span data-ttu-id="bbc96-226">es</span><span class="sxs-lookup"><span data-stu-id="bbc96-226">ssn</span></span>
  
<span data-ttu-id="bbc96-227">número nacional</span><span class="sxs-lookup"><span data-stu-id="bbc96-227">national number</span></span>
  
<span data-ttu-id="bbc96-228">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-228">personal id number</span></span>
  
<span data-ttu-id="bbc96-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-229">personalidnumber#</span></span>
  
<span data-ttu-id="bbc96-230">rč</span><span class="sxs-lookup"><span data-stu-id="bbc96-230">rč</span></span>
  
<span data-ttu-id="bbc96-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="bbc96-231">rodné číslo</span></span>
  
<span data-ttu-id="bbc96-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="bbc96-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="bbc96-233">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="bbc96-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="bbc96-234">Formatar</span><span class="sxs-lookup"><span data-stu-id="bbc96-234">Format</span></span>

<span data-ttu-id="bbc96-235">Dez dígitos e um hífen no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="bbc96-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bbc96-236">Padrão</span><span class="sxs-lookup"><span data-stu-id="bbc96-236">Pattern</span></span>

<span data-ttu-id="bbc96-237">Dez dígitos e um hífen:</span><span class="sxs-lookup"><span data-stu-id="bbc96-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="bbc96-238">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="bbc96-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="bbc96-239">Um hífen</span><span class="sxs-lookup"><span data-stu-id="bbc96-239">A hyphen</span></span>
    
- <span data-ttu-id="bbc96-240">Quatro dígitos que correspondem a um número de sequência</span><span class="sxs-lookup"><span data-stu-id="bbc96-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bbc96-241">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-241">Checksum</span></span>

<span data-ttu-id="bbc96-242">Sim</span><span class="sxs-lookup"><span data-stu-id="bbc96-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bbc96-243">Definição</span><span class="sxs-lookup"><span data-stu-id="bbc96-243">Definition</span></span>

<span data-ttu-id="bbc96-244">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-245">A função `Func_denmark_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bbc96-246">Uma palavra- `Keywords_denmark_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="bbc96-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bbc96-247">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-248">A função `Func_denmark_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bbc96-249">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="bbc96-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="bbc96-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bbc96-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bbc96-251">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-251">personal identification number</span></span>
  
<span data-ttu-id="bbc96-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="bbc96-252">national identification number</span></span>
  
<span data-ttu-id="bbc96-253">social security number</span><span class="sxs-lookup"><span data-stu-id="bbc96-253">social security number</span></span>
  
<span data-ttu-id="bbc96-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-254">nationalnumber#</span></span>
  
<span data-ttu-id="bbc96-255">es #</span><span class="sxs-lookup"><span data-stu-id="bbc96-255">ssn#</span></span>
  
<span data-ttu-id="bbc96-256">es</span><span class="sxs-lookup"><span data-stu-id="bbc96-256">ssn</span></span>
  
<span data-ttu-id="bbc96-257">número nacional</span><span class="sxs-lookup"><span data-stu-id="bbc96-257">national number</span></span>
  
<span data-ttu-id="bbc96-258">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-258">personal id number</span></span>
  
<span data-ttu-id="bbc96-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-259">personalidnumber#</span></span>
  
<span data-ttu-id="bbc96-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="bbc96-260">cpr-nummer</span></span>
  
<span data-ttu-id="bbc96-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="bbc96-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="bbc96-262">Finlândia</span><span class="sxs-lookup"><span data-stu-id="bbc96-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="bbc96-263">Formatar</span><span class="sxs-lookup"><span data-stu-id="bbc96-263">Format</span></span>

<span data-ttu-id="bbc96-264">Uma combinação de 11 caracteres no formato especificado</span><span class="sxs-lookup"><span data-stu-id="bbc96-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bbc96-265">Padrão</span><span class="sxs-lookup"><span data-stu-id="bbc96-265">Pattern</span></span>

<span data-ttu-id="bbc96-266">Uma combinação de 11 caracteres no formato especificado:</span><span class="sxs-lookup"><span data-stu-id="bbc96-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="bbc96-267">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="bbc96-267">Six digits</span></span> 
    
- <span data-ttu-id="bbc96-268">Uma instância de um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="bbc96-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="bbc96-269">Símbolo de adição</span><span class="sxs-lookup"><span data-stu-id="bbc96-269">Plus symbol</span></span>
    
  - <span data-ttu-id="bbc96-270">Símbolo de subtração</span><span class="sxs-lookup"><span data-stu-id="bbc96-270">Minus symbol</span></span>
    
  - <span data-ttu-id="bbc96-271">A letra "A" (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="bbc96-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="bbc96-272">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="bbc96-272">Three digits</span></span>
    
- <span data-ttu-id="bbc96-273">Uma letra ou um dígito</span><span class="sxs-lookup"><span data-stu-id="bbc96-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bbc96-274">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-274">Checksum</span></span>

<span data-ttu-id="bbc96-275">Sim</span><span class="sxs-lookup"><span data-stu-id="bbc96-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bbc96-276">Definição</span><span class="sxs-lookup"><span data-stu-id="bbc96-276">Definition</span></span>

<span data-ttu-id="bbc96-277">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-278">A função `Func_finland_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bbc96-279">Uma palavra- `Keywords_finland_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="bbc96-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bbc96-280">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-281">A função `Func_finland_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bbc96-282">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="bbc96-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="bbc96-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bbc96-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bbc96-284">identification number</span><span class="sxs-lookup"><span data-stu-id="bbc96-284">identification number</span></span>
  
<span data-ttu-id="bbc96-285">ID pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-285">personal id</span></span>
  
<span data-ttu-id="bbc96-286">número de identidade</span><span class="sxs-lookup"><span data-stu-id="bbc96-286">identity number</span></span>
  
<span data-ttu-id="bbc96-287">número de ID nacional da finlandês</span><span class="sxs-lookup"><span data-stu-id="bbc96-287">finnish national id number</span></span>
  
<span data-ttu-id="bbc96-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-288">personalidnumber#</span></span>
  
<span data-ttu-id="bbc96-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="bbc96-289">national identification number</span></span>
  
<span data-ttu-id="bbc96-290">número de identificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-290">id number</span></span>
  
<span data-ttu-id="bbc96-291">n º de ID nacional</span><span class="sxs-lookup"><span data-stu-id="bbc96-291">national id no.</span></span>
  
<span data-ttu-id="bbc96-292">número de ID nacional</span><span class="sxs-lookup"><span data-stu-id="bbc96-292">national id number</span></span>
  
<span data-ttu-id="bbc96-293">ID não</span><span class="sxs-lookup"><span data-stu-id="bbc96-293">id no</span></span>
  
<span data-ttu-id="bbc96-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="bbc96-294">tunnistenumero</span></span>
  
<span data-ttu-id="bbc96-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="bbc96-295">henkilötunnus</span></span>
  
<span data-ttu-id="bbc96-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="bbc96-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="bbc96-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="bbc96-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="bbc96-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="bbc96-298">identiteetti numero</span></span>
  
<span data-ttu-id="bbc96-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="bbc96-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="bbc96-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="bbc96-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="bbc96-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="bbc96-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="bbc96-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="bbc96-302">tunnusnumero</span></span>
  
<span data-ttu-id="bbc96-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="bbc96-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="bbc96-304">hetu</span><span class="sxs-lookup"><span data-stu-id="bbc96-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="bbc96-305">França</span><span class="sxs-lookup"><span data-stu-id="bbc96-305">France</span></span>

<span data-ttu-id="bbc96-306">Para obter detalhes, consulte a seção "França Social Security Number (INSEE)" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="bbc96-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="bbc96-307">Alemanha</span><span class="sxs-lookup"><span data-stu-id="bbc96-307">Germany</span></span>

<span data-ttu-id="bbc96-308">Para obter detalhes, consulte a seção "número do cartão de identidade da Alemanha" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="bbc96-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="bbc96-309">Grécia</span><span class="sxs-lookup"><span data-stu-id="bbc96-309">Greece</span></span>

<span data-ttu-id="bbc96-310">Para obter detalhes, consulte a seção "cartão de ID nacional da Grécia" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="bbc96-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="bbc96-311">Hungria</span><span class="sxs-lookup"><span data-stu-id="bbc96-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="bbc96-312">Formatar</span><span class="sxs-lookup"><span data-stu-id="bbc96-312">Format</span></span>

<span data-ttu-id="bbc96-313">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="bbc96-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bbc96-314">Padrão</span><span class="sxs-lookup"><span data-stu-id="bbc96-314">Pattern</span></span>

<span data-ttu-id="bbc96-315">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="bbc96-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="bbc96-316">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-316">Checksum</span></span>

<span data-ttu-id="bbc96-317">Sim</span><span class="sxs-lookup"><span data-stu-id="bbc96-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bbc96-318">Definição</span><span class="sxs-lookup"><span data-stu-id="bbc96-318">Definition</span></span>

<span data-ttu-id="bbc96-319">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-320">A função `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bbc96-321">Uma palavra- `Keywords_hungary_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="bbc96-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bbc96-322">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-323">A função `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bbc96-324">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="bbc96-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="bbc96-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bbc96-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bbc96-326">número de seguro social de seguridade</span><span class="sxs-lookup"><span data-stu-id="bbc96-326">hungarian social security number</span></span>
  
<span data-ttu-id="bbc96-327">social security number</span><span class="sxs-lookup"><span data-stu-id="bbc96-327">social security number</span></span>
  
<span data-ttu-id="bbc96-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="bbc96-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="bbc96-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="bbc96-329">hssn#</span></span>
  
<span data-ttu-id="bbc96-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="bbc96-330">socialsecuritynno</span></span>
  
<span data-ttu-id="bbc96-331">hssn</span><span class="sxs-lookup"><span data-stu-id="bbc96-331">hssn</span></span>
  
<span data-ttu-id="bbc96-332">taj</span><span class="sxs-lookup"><span data-stu-id="bbc96-332">taj</span></span>
  
<span data-ttu-id="bbc96-333">taj #</span><span class="sxs-lookup"><span data-stu-id="bbc96-333">taj#</span></span>
  
<span data-ttu-id="bbc96-334">es</span><span class="sxs-lookup"><span data-stu-id="bbc96-334">ssn</span></span>
  
<span data-ttu-id="bbc96-335">es #</span><span class="sxs-lookup"><span data-stu-id="bbc96-335">ssn#</span></span>
  
<span data-ttu-id="bbc96-336">segurança social não</span><span class="sxs-lookup"><span data-stu-id="bbc96-336">social security no</span></span>
  
<span data-ttu-id="bbc96-337">áfa</span><span class="sxs-lookup"><span data-stu-id="bbc96-337">áfa</span></span>
  
<span data-ttu-id="bbc96-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="bbc96-338">közösségi adószám</span></span>
  
<span data-ttu-id="bbc96-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="bbc96-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="bbc96-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="bbc96-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="bbc96-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="bbc96-341">áfa szám</span></span>
  
<span data-ttu-id="bbc96-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="bbc96-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="bbc96-343">Portugal</span><span class="sxs-lookup"><span data-stu-id="bbc96-343">Portugal</span></span>

<span data-ttu-id="bbc96-344">Para obter detalhes, consulte a seção "número de cartão de cidadão da Portugal" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="bbc96-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="bbc96-345">Espanha</span><span class="sxs-lookup"><span data-stu-id="bbc96-345">Spain</span></span>

<span data-ttu-id="bbc96-346">Para obter detalhes, consulte a seção "número de seguridade social da Espanha (SSN)" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="bbc96-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="bbc96-347">Suécia</span><span class="sxs-lookup"><span data-stu-id="bbc96-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="bbc96-348">Formatar</span><span class="sxs-lookup"><span data-stu-id="bbc96-348">Format</span></span>

<span data-ttu-id="bbc96-349">12 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="bbc96-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bbc96-350">Padrão</span><span class="sxs-lookup"><span data-stu-id="bbc96-350">Pattern</span></span>

<span data-ttu-id="bbc96-351">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="bbc96-351">12 digits:</span></span>
  
-  <span data-ttu-id="bbc96-352">Oito dígitos que correspondem à data de nascimento (AAAAMMDD)</span><span class="sxs-lookup"><span data-stu-id="bbc96-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="bbc96-353">Três dígitos que correspondem a um número de série em que:</span><span class="sxs-lookup"><span data-stu-id="bbc96-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="bbc96-354">O último dígito no número de série indica sexo pela atribuição de um número ímpar para macho e um número par para o fêmea</span><span class="sxs-lookup"><span data-stu-id="bbc96-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="bbc96-355">Até 1990, a atribuição de número de série correspondente à região onde o portador do número nasceu ou (se nasceu antes de 1947) em que ele/ela estava em vida, de acordo com os registros de impostos, em 1º de janeiro de 1947, com um código especial (geralmente 9 como o sétimo dígito) para immigrants</span><span class="sxs-lookup"><span data-stu-id="bbc96-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="bbc96-356">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bbc96-357">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="bbc96-357">Checksum</span></span>

<span data-ttu-id="bbc96-358">Sim</span><span class="sxs-lookup"><span data-stu-id="bbc96-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bbc96-359">Definição</span><span class="sxs-lookup"><span data-stu-id="bbc96-359">Definition</span></span>

<span data-ttu-id="bbc96-360">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-361">A função `Func_sweden_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bbc96-362">Uma palavra- `Keywords_sweden_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="bbc96-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bbc96-363">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="bbc96-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bbc96-364">A função `Func_sweden_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="bbc96-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bbc96-365">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="bbc96-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="bbc96-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bbc96-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bbc96-367">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-367">personal id number</span></span>
  
<span data-ttu-id="bbc96-368">identification number</span><span class="sxs-lookup"><span data-stu-id="bbc96-368">identification number</span></span>
  
<span data-ttu-id="bbc96-369">n º de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="bbc96-369">personal id no</span></span>
  
<span data-ttu-id="bbc96-370">identidade não</span><span class="sxs-lookup"><span data-stu-id="bbc96-370">identity no</span></span>
  
<span data-ttu-id="bbc96-371">identificação não</span><span class="sxs-lookup"><span data-stu-id="bbc96-371">identification no</span></span>
  
<span data-ttu-id="bbc96-372">identificação pessoal não</span><span class="sxs-lookup"><span data-stu-id="bbc96-372">personal identification no</span></span>
  
<span data-ttu-id="bbc96-373">ID personnummer</span><span class="sxs-lookup"><span data-stu-id="bbc96-373">personnummer id</span></span>
  
<span data-ttu-id="bbc96-374">ID Personligt-Nummer</span><span class="sxs-lookup"><span data-stu-id="bbc96-374">personligt id-nummer</span></span>
  
<span data-ttu-id="bbc96-375">ID unikt-Nummer</span><span class="sxs-lookup"><span data-stu-id="bbc96-375">unikt id-nummer</span></span>
  
<span data-ttu-id="bbc96-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="bbc96-376">personnummer</span></span>
  
<span data-ttu-id="bbc96-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="bbc96-377">identifikationsnumret</span></span>
  
<span data-ttu-id="bbc96-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="bbc96-378">personnummer#</span></span>
  
<span data-ttu-id="bbc96-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="bbc96-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbc96-380">Confira também</span><span class="sxs-lookup"><span data-stu-id="bbc96-380">See also</span></span>

[<span data-ttu-id="bbc96-381">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="bbc96-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

