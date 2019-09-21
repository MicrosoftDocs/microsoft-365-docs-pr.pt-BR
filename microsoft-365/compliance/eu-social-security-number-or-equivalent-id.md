---
title: Número de seguro social da UE ou ID equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o número de segurança social da UE ou o tipo de informação confidencial de ID equivalente. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072664"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="1a763-104">Número de seguro social da UE ou ID equivalente</span><span class="sxs-lookup"><span data-stu-id="1a763-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="1a763-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o número de segurança social da UE (SSN) ou o tipo de informação confidencial de ID equivalente.</span><span class="sxs-lookup"><span data-stu-id="1a763-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="1a763-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="1a763-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="1a763-107">Áustria </span><span class="sxs-lookup"><span data-stu-id="1a763-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="1a763-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="1a763-108">Format</span></span>

<span data-ttu-id="1a763-109">10 dígitos no formato especificado</span><span class="sxs-lookup"><span data-stu-id="1a763-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1a763-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="1a763-110">Pattern</span></span>

<span data-ttu-id="1a763-111">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1a763-111">10 digits:</span></span>
  
-  <span data-ttu-id="1a763-112">Três dígitos que correspondem a um número de série</span><span class="sxs-lookup"><span data-stu-id="1a763-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="1a763-113">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-113">One check digit</span></span>
    
- <span data-ttu-id="1a763-114">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="1a763-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1a763-115">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-115">Checksum</span></span>

<span data-ttu-id="1a763-116">Sim</span><span class="sxs-lookup"><span data-stu-id="1a763-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1a763-117">Definição</span><span class="sxs-lookup"><span data-stu-id="1a763-117">Definition</span></span>

<span data-ttu-id="1a763-118">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-119">A função `Func_austria_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1a763-120">Uma palavra- `Keywords_austria_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="1a763-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1a763-121">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-122">A função `Func_austria_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1a763-123">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1a763-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="1a763-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1a763-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1a763-125">segurança social não</span><span class="sxs-lookup"><span data-stu-id="1a763-125">social security no</span></span>
  
<span data-ttu-id="1a763-126">social security number</span><span class="sxs-lookup"><span data-stu-id="1a763-126">social security number</span></span>
  
<span data-ttu-id="1a763-127">social security code</span><span class="sxs-lookup"><span data-stu-id="1a763-127">social security code</span></span>
  
<span data-ttu-id="1a763-128">número de seguro</span><span class="sxs-lookup"><span data-stu-id="1a763-128">insurance number</span></span>
  
<span data-ttu-id="1a763-129">SSN austríaco</span><span class="sxs-lookup"><span data-stu-id="1a763-129">austrian ssn</span></span>
  
<span data-ttu-id="1a763-130">es #</span><span class="sxs-lookup"><span data-stu-id="1a763-130">ssn#</span></span>
  
<span data-ttu-id="1a763-131">es</span><span class="sxs-lookup"><span data-stu-id="1a763-131">ssn</span></span>
  
<span data-ttu-id="1a763-132">código de seguro</span><span class="sxs-lookup"><span data-stu-id="1a763-132">insurance code</span></span>
  
<span data-ttu-id="1a763-133">código de seguro #</span><span class="sxs-lookup"><span data-stu-id="1a763-133">insurance code#</span></span>
  
<span data-ttu-id="1a763-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="1a763-134">socialsecurityno#</span></span>
  
<span data-ttu-id="1a763-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="1a763-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="1a763-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="1a763-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="1a763-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="1a763-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="1a763-138">Bélgica </span><span class="sxs-lookup"><span data-stu-id="1a763-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="1a763-139">Formatar</span><span class="sxs-lookup"><span data-stu-id="1a763-139">Format</span></span>

<span data-ttu-id="1a763-140">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="1a763-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1a763-141">Padrão</span><span class="sxs-lookup"><span data-stu-id="1a763-141">Pattern</span></span>

<span data-ttu-id="1a763-142">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="1a763-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1a763-143">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-143">Checksum</span></span>

<span data-ttu-id="1a763-144">Sim</span><span class="sxs-lookup"><span data-stu-id="1a763-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1a763-145">Definição</span><span class="sxs-lookup"><span data-stu-id="1a763-145">Definition</span></span>

<span data-ttu-id="1a763-146">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-147">A função `Func_belgium_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1a763-148">Uma palavra- `Keywords_belgium_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="1a763-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1a763-149">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-150">A função `Func_belgium_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1a763-151">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1a763-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="1a763-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1a763-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1a763-153">número Nacional belga</span><span class="sxs-lookup"><span data-stu-id="1a763-153">belgian national number</span></span>
  
<span data-ttu-id="1a763-154">número nacional</span><span class="sxs-lookup"><span data-stu-id="1a763-154">national number</span></span>
  
<span data-ttu-id="1a763-155">social security number</span><span class="sxs-lookup"><span data-stu-id="1a763-155">social security number</span></span>
  
<span data-ttu-id="1a763-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-156">nationalnumber#</span></span>
  
<span data-ttu-id="1a763-157">es #</span><span class="sxs-lookup"><span data-stu-id="1a763-157">ssn#</span></span>
  
<span data-ttu-id="1a763-158">es</span><span class="sxs-lookup"><span data-stu-id="1a763-158">ssn</span></span>
  
<span data-ttu-id="1a763-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="1a763-159">nationalnumber</span></span>
  
<span data-ttu-id="1a763-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="1a763-160">bnn#</span></span>
  
<span data-ttu-id="1a763-161">bnn</span><span class="sxs-lookup"><span data-stu-id="1a763-161">bnn</span></span>
  
<span data-ttu-id="1a763-162">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-162">personal id number</span></span>
  
<span data-ttu-id="1a763-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-163">personalidnumber#</span></span>
  
<span data-ttu-id="1a763-164">nacional Numéro</span><span class="sxs-lookup"><span data-stu-id="1a763-164">numéro national</span></span>
  
<span data-ttu-id="1a763-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="1a763-165">numéro de sécurité</span></span>
  
<span data-ttu-id="1a763-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="1a763-166">numéro d'assuré</span></span>
  
<span data-ttu-id="1a763-167">nacional de identificação</span><span class="sxs-lookup"><span data-stu-id="1a763-167">identifiant national</span></span>
  
<span data-ttu-id="1a763-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="1a763-168">identifiantnational#</span></span>
  
<span data-ttu-id="1a763-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="1a763-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="1a763-170">Croácia</span><span class="sxs-lookup"><span data-stu-id="1a763-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="1a763-171">Formatar</span><span class="sxs-lookup"><span data-stu-id="1a763-171">Format</span></span>

<span data-ttu-id="1a763-172">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="1a763-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1a763-173">Padrão</span><span class="sxs-lookup"><span data-stu-id="1a763-173">Pattern</span></span>

 <span data-ttu-id="1a763-174">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1a763-174">11 digits:</span></span> 
  
-  <span data-ttu-id="1a763-175">Dez dígitos</span><span class="sxs-lookup"><span data-stu-id="1a763-175">Ten digits</span></span> 
    
- <span data-ttu-id="1a763-176">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1a763-177">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-177">Checksum</span></span>

<span data-ttu-id="1a763-178">Sim</span><span class="sxs-lookup"><span data-stu-id="1a763-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1a763-179">Definição</span><span class="sxs-lookup"><span data-stu-id="1a763-179">Definition</span></span>

<span data-ttu-id="1a763-180">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-181">A função `Func_croatia_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1a763-182">Uma palavra- `Keywords_croatia_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="1a763-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1a763-183">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-184">A função `Func_croatia_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1a763-185">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1a763-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="1a763-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1a763-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1a763-187">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-187">personal identification number</span></span>
  
<span data-ttu-id="1a763-188">número do cidadão mestre</span><span class="sxs-lookup"><span data-stu-id="1a763-188">master citizen number</span></span>
  
<span data-ttu-id="1a763-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="1a763-189">national identification number</span></span>
  
<span data-ttu-id="1a763-190">social security number</span><span class="sxs-lookup"><span data-stu-id="1a763-190">social security number</span></span>
  
<span data-ttu-id="1a763-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-191">nationalnumber#</span></span>
  
<span data-ttu-id="1a763-192">es #</span><span class="sxs-lookup"><span data-stu-id="1a763-192">ssn#</span></span>
  
<span data-ttu-id="1a763-193">es</span><span class="sxs-lookup"><span data-stu-id="1a763-193">ssn</span></span>
  
<span data-ttu-id="1a763-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="1a763-194">nationalnumber</span></span>
  
<span data-ttu-id="1a763-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="1a763-195">bnn#</span></span>
  
<span data-ttu-id="1a763-196">bnn</span><span class="sxs-lookup"><span data-stu-id="1a763-196">bnn</span></span>
  
<span data-ttu-id="1a763-197">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-197">personal id number</span></span>
  
<span data-ttu-id="1a763-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-198">personalidnumber#</span></span>
  
<span data-ttu-id="1a763-199">NIB</span><span class="sxs-lookup"><span data-stu-id="1a763-199">oib</span></span>
  
<span data-ttu-id="1a763-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="1a763-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="1a763-201">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="1a763-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="1a763-202">Formatar</span><span class="sxs-lookup"><span data-stu-id="1a763-202">Format</span></span>

<span data-ttu-id="1a763-203">Dez dígitos e uma barra invertida no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="1a763-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1a763-204">Padrão</span><span class="sxs-lookup"><span data-stu-id="1a763-204">Pattern</span></span>

<span data-ttu-id="1a763-205">Dez dígitos e uma barra invertida:</span><span class="sxs-lookup"><span data-stu-id="1a763-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="1a763-206">Seis dígitos que correspondem à data de nascimento (AAMMDD):</span><span class="sxs-lookup"><span data-stu-id="1a763-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="1a763-207">Uma barra invertida</span><span class="sxs-lookup"><span data-stu-id="1a763-207">A backslash</span></span>
    
- <span data-ttu-id="1a763-208">Três dígitos que correspondem a um número de série que separa as pessoas nasceu na mesma data</span><span class="sxs-lookup"><span data-stu-id="1a763-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="1a763-209">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1a763-210">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-210">Checksum</span></span>

<span data-ttu-id="1a763-211">Sim</span><span class="sxs-lookup"><span data-stu-id="1a763-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1a763-212">Definição</span><span class="sxs-lookup"><span data-stu-id="1a763-212">Definition</span></span>

<span data-ttu-id="1a763-213">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-214">A função `Func_czech_republic_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1a763-215">Uma palavra- `Keywords_czech_republic_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="1a763-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1a763-216">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-217">A função `Func_czech_republic_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1a763-218">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1a763-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="1a763-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1a763-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1a763-220">número de nascimento</span><span class="sxs-lookup"><span data-stu-id="1a763-220">birth number</span></span>
  
<span data-ttu-id="1a763-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="1a763-221">national identification number</span></span>
  
<span data-ttu-id="1a763-222">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-222">personal identification number</span></span>
  
<span data-ttu-id="1a763-223">social security number</span><span class="sxs-lookup"><span data-stu-id="1a763-223">social security number</span></span>
  
<span data-ttu-id="1a763-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-224">nationalnumber#</span></span>
  
<span data-ttu-id="1a763-225">es #</span><span class="sxs-lookup"><span data-stu-id="1a763-225">ssn#</span></span>
  
<span data-ttu-id="1a763-226">es</span><span class="sxs-lookup"><span data-stu-id="1a763-226">ssn</span></span>
  
<span data-ttu-id="1a763-227">número nacional</span><span class="sxs-lookup"><span data-stu-id="1a763-227">national number</span></span>
  
<span data-ttu-id="1a763-228">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-228">personal id number</span></span>
  
<span data-ttu-id="1a763-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-229">personalidnumber#</span></span>
  
<span data-ttu-id="1a763-230">rč</span><span class="sxs-lookup"><span data-stu-id="1a763-230">rč</span></span>
  
<span data-ttu-id="1a763-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="1a763-231">rodné číslo</span></span>
  
<span data-ttu-id="1a763-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="1a763-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="1a763-233">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="1a763-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="1a763-234">Formatar</span><span class="sxs-lookup"><span data-stu-id="1a763-234">Format</span></span>

<span data-ttu-id="1a763-235">Dez dígitos e um hífen no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="1a763-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1a763-236">Padrão</span><span class="sxs-lookup"><span data-stu-id="1a763-236">Pattern</span></span>

<span data-ttu-id="1a763-237">Dez dígitos e um hífen:</span><span class="sxs-lookup"><span data-stu-id="1a763-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="1a763-238">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="1a763-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="1a763-239">Um hífen</span><span class="sxs-lookup"><span data-stu-id="1a763-239">A hyphen</span></span>
    
- <span data-ttu-id="1a763-240">Quatro dígitos que correspondem a um número de sequência</span><span class="sxs-lookup"><span data-stu-id="1a763-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1a763-241">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-241">Checksum</span></span>

<span data-ttu-id="1a763-242">Sim</span><span class="sxs-lookup"><span data-stu-id="1a763-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1a763-243">Definição</span><span class="sxs-lookup"><span data-stu-id="1a763-243">Definition</span></span>

<span data-ttu-id="1a763-244">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-245">A função `Func_denmark_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1a763-246">Uma palavra- `Keywords_denmark_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="1a763-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1a763-247">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-248">A função `Func_denmark_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1a763-249">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1a763-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="1a763-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1a763-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1a763-251">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-251">personal identification number</span></span>
  
<span data-ttu-id="1a763-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="1a763-252">national identification number</span></span>
  
<span data-ttu-id="1a763-253">social security number</span><span class="sxs-lookup"><span data-stu-id="1a763-253">social security number</span></span>
  
<span data-ttu-id="1a763-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-254">nationalnumber#</span></span>
  
<span data-ttu-id="1a763-255">es #</span><span class="sxs-lookup"><span data-stu-id="1a763-255">ssn#</span></span>
  
<span data-ttu-id="1a763-256">es</span><span class="sxs-lookup"><span data-stu-id="1a763-256">ssn</span></span>
  
<span data-ttu-id="1a763-257">número nacional</span><span class="sxs-lookup"><span data-stu-id="1a763-257">national number</span></span>
  
<span data-ttu-id="1a763-258">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-258">personal id number</span></span>
  
<span data-ttu-id="1a763-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-259">personalidnumber#</span></span>
  
<span data-ttu-id="1a763-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="1a763-260">cpr-nummer</span></span>
  
<span data-ttu-id="1a763-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="1a763-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="1a763-262">Finlândia</span><span class="sxs-lookup"><span data-stu-id="1a763-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="1a763-263">Formatar</span><span class="sxs-lookup"><span data-stu-id="1a763-263">Format</span></span>

<span data-ttu-id="1a763-264">Uma combinação de 11 caracteres no formato especificado</span><span class="sxs-lookup"><span data-stu-id="1a763-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1a763-265">Padrão</span><span class="sxs-lookup"><span data-stu-id="1a763-265">Pattern</span></span>

<span data-ttu-id="1a763-266">Uma combinação de 11 caracteres no formato especificado:</span><span class="sxs-lookup"><span data-stu-id="1a763-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="1a763-267">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="1a763-267">Six digits</span></span> 
    
- <span data-ttu-id="1a763-268">Uma instância de um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1a763-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="1a763-269">Símbolo de adição</span><span class="sxs-lookup"><span data-stu-id="1a763-269">Plus symbol</span></span>
    
  - <span data-ttu-id="1a763-270">Símbolo de subtração</span><span class="sxs-lookup"><span data-stu-id="1a763-270">Minus symbol</span></span>
    
  - <span data-ttu-id="1a763-271">A letra "A" (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="1a763-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="1a763-272">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="1a763-272">Three digits</span></span>
    
- <span data-ttu-id="1a763-273">Uma letra ou um dígito</span><span class="sxs-lookup"><span data-stu-id="1a763-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1a763-274">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-274">Checksum</span></span>

<span data-ttu-id="1a763-275">Sim</span><span class="sxs-lookup"><span data-stu-id="1a763-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1a763-276">Definição</span><span class="sxs-lookup"><span data-stu-id="1a763-276">Definition</span></span>

<span data-ttu-id="1a763-277">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-278">A função `Func_finland_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1a763-279">Uma palavra- `Keywords_finland_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="1a763-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1a763-280">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-281">A função `Func_finland_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1a763-282">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1a763-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="1a763-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1a763-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1a763-284">identification number</span><span class="sxs-lookup"><span data-stu-id="1a763-284">identification number</span></span>
  
<span data-ttu-id="1a763-285">ID pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-285">personal id</span></span>
  
<span data-ttu-id="1a763-286">número de identidade</span><span class="sxs-lookup"><span data-stu-id="1a763-286">identity number</span></span>
  
<span data-ttu-id="1a763-287">número de ID nacional da finlandês</span><span class="sxs-lookup"><span data-stu-id="1a763-287">finnish national id number</span></span>
  
<span data-ttu-id="1a763-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-288">personalidnumber#</span></span>
  
<span data-ttu-id="1a763-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="1a763-289">national identification number</span></span>
  
<span data-ttu-id="1a763-290">número de identificação</span><span class="sxs-lookup"><span data-stu-id="1a763-290">id number</span></span>
  
<span data-ttu-id="1a763-291">n º de ID nacional</span><span class="sxs-lookup"><span data-stu-id="1a763-291">national id no.</span></span>
  
<span data-ttu-id="1a763-292">número de ID nacional</span><span class="sxs-lookup"><span data-stu-id="1a763-292">national id number</span></span>
  
<span data-ttu-id="1a763-293">ID não</span><span class="sxs-lookup"><span data-stu-id="1a763-293">id no</span></span>
  
<span data-ttu-id="1a763-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="1a763-294">tunnistenumero</span></span>
  
<span data-ttu-id="1a763-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="1a763-295">henkilötunnus</span></span>
  
<span data-ttu-id="1a763-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="1a763-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="1a763-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="1a763-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="1a763-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="1a763-298">identiteetti numero</span></span>
  
<span data-ttu-id="1a763-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="1a763-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="1a763-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="1a763-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="1a763-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="1a763-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="1a763-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="1a763-302">tunnusnumero</span></span>
  
<span data-ttu-id="1a763-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="1a763-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="1a763-304">hetu</span><span class="sxs-lookup"><span data-stu-id="1a763-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="1a763-305">França</span><span class="sxs-lookup"><span data-stu-id="1a763-305">France</span></span>

<span data-ttu-id="1a763-306">Para obter detalhes, consulte a seção "França Social Security Number (INSEE)" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1a763-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="1a763-307">Alemanha</span><span class="sxs-lookup"><span data-stu-id="1a763-307">Germany</span></span>

<span data-ttu-id="1a763-308">Para obter detalhes, consulte a seção "número do cartão de identidade da Alemanha" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1a763-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="1a763-309">Grécia</span><span class="sxs-lookup"><span data-stu-id="1a763-309">Greece</span></span>

<span data-ttu-id="1a763-310">Para obter detalhes, consulte a seção "cartão de ID nacional da Grécia" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1a763-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="1a763-311">Hungria</span><span class="sxs-lookup"><span data-stu-id="1a763-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="1a763-312">Formatar</span><span class="sxs-lookup"><span data-stu-id="1a763-312">Format</span></span>

<span data-ttu-id="1a763-313">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="1a763-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1a763-314">Padrão</span><span class="sxs-lookup"><span data-stu-id="1a763-314">Pattern</span></span>

<span data-ttu-id="1a763-315">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="1a763-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1a763-316">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-316">Checksum</span></span>

<span data-ttu-id="1a763-317">Sim</span><span class="sxs-lookup"><span data-stu-id="1a763-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1a763-318">Definição</span><span class="sxs-lookup"><span data-stu-id="1a763-318">Definition</span></span>

<span data-ttu-id="1a763-319">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-320">A função `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1a763-321">Uma palavra- `Keywords_hungary_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="1a763-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1a763-322">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-323">A função `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1a763-324">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1a763-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="1a763-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1a763-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1a763-326">número de seguro social de seguridade</span><span class="sxs-lookup"><span data-stu-id="1a763-326">hungarian social security number</span></span>
  
<span data-ttu-id="1a763-327">social security number</span><span class="sxs-lookup"><span data-stu-id="1a763-327">social security number</span></span>
  
<span data-ttu-id="1a763-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="1a763-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="1a763-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="1a763-329">hssn#</span></span>
  
<span data-ttu-id="1a763-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="1a763-330">socialsecuritynno</span></span>
  
<span data-ttu-id="1a763-331">hssn</span><span class="sxs-lookup"><span data-stu-id="1a763-331">hssn</span></span>
  
<span data-ttu-id="1a763-332">taj</span><span class="sxs-lookup"><span data-stu-id="1a763-332">taj</span></span>
  
<span data-ttu-id="1a763-333">taj #</span><span class="sxs-lookup"><span data-stu-id="1a763-333">taj#</span></span>
  
<span data-ttu-id="1a763-334">es</span><span class="sxs-lookup"><span data-stu-id="1a763-334">ssn</span></span>
  
<span data-ttu-id="1a763-335">es #</span><span class="sxs-lookup"><span data-stu-id="1a763-335">ssn#</span></span>
  
<span data-ttu-id="1a763-336">segurança social não</span><span class="sxs-lookup"><span data-stu-id="1a763-336">social security no</span></span>
  
<span data-ttu-id="1a763-337">áfa</span><span class="sxs-lookup"><span data-stu-id="1a763-337">áfa</span></span>
  
<span data-ttu-id="1a763-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="1a763-338">közösségi adószám</span></span>
  
<span data-ttu-id="1a763-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="1a763-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="1a763-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="1a763-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="1a763-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="1a763-341">áfa szám</span></span>
  
<span data-ttu-id="1a763-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="1a763-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="1a763-343">Portugal</span><span class="sxs-lookup"><span data-stu-id="1a763-343">Portugal</span></span>

<span data-ttu-id="1a763-344">Para obter detalhes, consulte a seção "número de cartão de cidadão da Portugal" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1a763-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="1a763-345">Espanha</span><span class="sxs-lookup"><span data-stu-id="1a763-345">Spain</span></span>

<span data-ttu-id="1a763-346">Para obter detalhes, consulte a seção "número de seguridade social da Espanha (SSN)" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1a763-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="1a763-347">Suécia</span><span class="sxs-lookup"><span data-stu-id="1a763-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="1a763-348">Formatar</span><span class="sxs-lookup"><span data-stu-id="1a763-348">Format</span></span>

<span data-ttu-id="1a763-349">12 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="1a763-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1a763-350">Padrão</span><span class="sxs-lookup"><span data-stu-id="1a763-350">Pattern</span></span>

<span data-ttu-id="1a763-351">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="1a763-351">12 digits:</span></span>
  
-  <span data-ttu-id="1a763-352">Oito dígitos que correspondem à data de nascimento (AAAAMMDD)</span><span class="sxs-lookup"><span data-stu-id="1a763-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="1a763-353">Três dígitos que correspondem a um número de série em que:</span><span class="sxs-lookup"><span data-stu-id="1a763-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="1a763-354">O último dígito no número de série indica sexo pela atribuição de um número ímpar para macho e um número par para o fêmea</span><span class="sxs-lookup"><span data-stu-id="1a763-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="1a763-355">Até 1990, a atribuição de número de série correspondente à região onde o portador do número nasceu ou (se nasceu antes de 1947) em que ele/ela estava em vida, de acordo com os registros de impostos, em 1º de janeiro de 1947, com um código especial (geralmente 9 como o sétimo dígito) para immigrants</span><span class="sxs-lookup"><span data-stu-id="1a763-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="1a763-356">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1a763-357">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="1a763-357">Checksum</span></span>

<span data-ttu-id="1a763-358">Sim</span><span class="sxs-lookup"><span data-stu-id="1a763-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1a763-359">Definição</span><span class="sxs-lookup"><span data-stu-id="1a763-359">Definition</span></span>

<span data-ttu-id="1a763-360">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-361">A função `Func_sweden_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1a763-362">Uma palavra- `Keywords_sweden_eu_ssn_or_equivalent` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="1a763-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1a763-363">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="1a763-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1a763-364">A função `Func_sweden_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="1a763-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1a763-365">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1a763-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="1a763-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1a763-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1a763-367">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-367">personal id number</span></span>
  
<span data-ttu-id="1a763-368">identification number</span><span class="sxs-lookup"><span data-stu-id="1a763-368">identification number</span></span>
  
<span data-ttu-id="1a763-369">n º de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="1a763-369">personal id no</span></span>
  
<span data-ttu-id="1a763-370">identidade não</span><span class="sxs-lookup"><span data-stu-id="1a763-370">identity no</span></span>
  
<span data-ttu-id="1a763-371">identificação não</span><span class="sxs-lookup"><span data-stu-id="1a763-371">identification no</span></span>
  
<span data-ttu-id="1a763-372">identificação pessoal não</span><span class="sxs-lookup"><span data-stu-id="1a763-372">personal identification no</span></span>
  
<span data-ttu-id="1a763-373">ID personnummer</span><span class="sxs-lookup"><span data-stu-id="1a763-373">personnummer id</span></span>
  
<span data-ttu-id="1a763-374">ID Personligt-Nummer</span><span class="sxs-lookup"><span data-stu-id="1a763-374">personligt id-nummer</span></span>
  
<span data-ttu-id="1a763-375">ID unikt-Nummer</span><span class="sxs-lookup"><span data-stu-id="1a763-375">unikt id-nummer</span></span>
  
<span data-ttu-id="1a763-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="1a763-376">personnummer</span></span>
  
<span data-ttu-id="1a763-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="1a763-377">identifikationsnumret</span></span>
  
<span data-ttu-id="1a763-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="1a763-378">personnummer#</span></span>
  
<span data-ttu-id="1a763-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="1a763-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1a763-380">Confira também</span><span class="sxs-lookup"><span data-stu-id="1a763-380">See also</span></span>

[<span data-ttu-id="1a763-381">O que os tipos de informações confidenciais procuram</span><span class="sxs-lookup"><span data-stu-id="1a763-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

