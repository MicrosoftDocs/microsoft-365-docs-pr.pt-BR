---
title: Número do Passport da UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número do Passport da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072667"
---
# <a name="eu-passport-number"></a><span data-ttu-id="99419-104">Número do Passport da UE</span><span class="sxs-lookup"><span data-stu-id="99419-104">EU Passport Number</span></span>

<span data-ttu-id="99419-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número do Passport da UE.</span><span class="sxs-lookup"><span data-stu-id="99419-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="99419-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="99419-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="99419-107">Áustria </span><span class="sxs-lookup"><span data-stu-id="99419-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="99419-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-108">Format</span></span>

<span data-ttu-id="99419-109">Uma letra seguida de um espaço opcional e sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-110">Pattern</span></span>

<span data-ttu-id="99419-111">Uma combinação de uma letra, sete dígitos e um espaço:</span><span class="sxs-lookup"><span data-stu-id="99419-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="99419-112">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="99419-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="99419-113">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="99419-113">One space (optional)</span></span>
    
- <span data-ttu-id="99419-114">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99419-115">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-115">Checksum</span></span>

<span data-ttu-id="99419-116">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="99419-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-117">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-117">Definition</span></span>

<span data-ttu-id="99419-118">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-119">A expressão `Regex_austria_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-120">Uma palavra- `Keywords_austria_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-121">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-121">Keywords</span></span>

<span data-ttu-id="99419-122">| |</span><span class="sxs-lookup"><span data-stu-id="99419-122"></span></span>
|<span data-ttu-id="99419-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-124">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-124">passport number</span></span>  <br/> <span data-ttu-id="99419-125">número de passaporte austríaco</span><span class="sxs-lookup"><span data-stu-id="99419-125">austrian passport number</span></span>  <br/> <span data-ttu-id="99419-126">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-126">passport no</span></span>  <br/> <span data-ttu-id="99419-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="99419-127">reisepass</span></span>  <br/> <span data-ttu-id="99419-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="99419-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="99419-129">Bélgica </span><span class="sxs-lookup"><span data-stu-id="99419-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="99419-130">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-130">Format</span></span>

<span data-ttu-id="99419-131">Duas letras seguidas por seis dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-132">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-132">Pattern</span></span>

<span data-ttu-id="99419-133">Duas letras e seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-134">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-134">Checksum</span></span>

<span data-ttu-id="99419-135">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="99419-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-136">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-136">Definition</span></span>

<span data-ttu-id="99419-137">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-138">A expressão `Regex_belgium_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-139">Uma palavra- `Keywords_belgium_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-140">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-140">Keywords</span></span>

<span data-ttu-id="99419-141">| |</span><span class="sxs-lookup"><span data-stu-id="99419-141"></span></span>
|<span data-ttu-id="99419-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-143">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-143">passport number</span></span>  <br/> <span data-ttu-id="99419-144">número de passaporte belga</span><span class="sxs-lookup"><span data-stu-id="99419-144">belgian passport number</span></span>  <br/> <span data-ttu-id="99419-145">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-145">passport no</span></span>  <br/> <span data-ttu-id="99419-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="99419-146">paspoort</span></span>  <br/> <span data-ttu-id="99419-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="99419-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="99419-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="99419-148">reisepass kein</span></span>  <br/> <span data-ttu-id="99419-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="99419-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="99419-150">Bulgária</span><span class="sxs-lookup"><span data-stu-id="99419-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="99419-151">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-151">Format</span></span>

<span data-ttu-id="99419-152">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-153">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-153">Pattern</span></span>

 <span data-ttu-id="99419-154">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="99419-155">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-155">Checksum</span></span>

<span data-ttu-id="99419-156">Não</span><span class="sxs-lookup"><span data-stu-id="99419-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-157">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-157">Definition</span></span>

<span data-ttu-id="99419-158">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-159">A expressão `Regex_bulgaria_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-160">Uma palavra- `Keywords_bulgaria_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-161">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-161">Keywords</span></span>

<span data-ttu-id="99419-162">| |</span><span class="sxs-lookup"><span data-stu-id="99419-162"></span></span>
|<span data-ttu-id="99419-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-164">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-164">passport number</span></span>  <br/> <span data-ttu-id="99419-165">número de passaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="99419-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="99419-166">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-166">passport no</span></span>  <br/> <span data-ttu-id="99419-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="99419-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="99419-168">Croácia</span><span class="sxs-lookup"><span data-stu-id="99419-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="99419-169">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-169">Format</span></span>

<span data-ttu-id="99419-170">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-171">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-171">Pattern</span></span>

 <span data-ttu-id="99419-172">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="99419-173">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-173">Checksum</span></span>

<span data-ttu-id="99419-174">Não</span><span class="sxs-lookup"><span data-stu-id="99419-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-175">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-175">Definition</span></span>

<span data-ttu-id="99419-176">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-177">A expressão `Regex_croatia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-178">Uma palavra- `Keywords_croatia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-179">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-179">Keywords</span></span>

<span data-ttu-id="99419-180">| |</span><span class="sxs-lookup"><span data-stu-id="99419-180"></span></span>
|<span data-ttu-id="99419-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-182">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-182">passport number</span></span>  <br/> <span data-ttu-id="99419-183">número de passaporte Croata</span><span class="sxs-lookup"><span data-stu-id="99419-183">croatian passport number</span></span>  <br/> <span data-ttu-id="99419-184">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-184">passport no</span></span>  <br/> <span data-ttu-id="99419-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="99419-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="99419-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="99419-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="99419-187">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-187">Format</span></span>

<span data-ttu-id="99419-188">Uma letra seguida de 6-8 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-189">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-189">Pattern</span></span>

<span data-ttu-id="99419-190">Uma letra seguida de seis a oito dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-191">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-191">Checksum</span></span>

<span data-ttu-id="99419-192">Não</span><span class="sxs-lookup"><span data-stu-id="99419-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-193">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-193">Definition</span></span>

<span data-ttu-id="99419-194">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-195">A expressão `Regex_cyprus_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-196">Uma palavra- `Keywords_cyprus_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-197">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-197">Keywords</span></span>

<span data-ttu-id="99419-198">| |</span><span class="sxs-lookup"><span data-stu-id="99419-198"></span></span>
|<span data-ttu-id="99419-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-200">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-200">passport number</span></span>  <br/> <span data-ttu-id="99419-201">número de passaporte do Chipre</span><span class="sxs-lookup"><span data-stu-id="99419-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="99419-202">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-202">passport no</span></span>  <br/> <span data-ttu-id="99419-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="99419-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="99419-204">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="99419-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="99419-205">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-205">Format</span></span>

<span data-ttu-id="99419-206">Oito dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-207">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-207">Pattern</span></span>

<span data-ttu-id="99419-208">Oito dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-209">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-209">Checksum</span></span>

<span data-ttu-id="99419-210">Não</span><span class="sxs-lookup"><span data-stu-id="99419-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-211">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-211">Definition</span></span>

<span data-ttu-id="99419-212">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-213">A expressão `Regex_czech_republic_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-214">Uma palavra- `Keywords_czech_republic_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-215">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-215">Keywords</span></span>

<span data-ttu-id="99419-216">| |</span><span class="sxs-lookup"><span data-stu-id="99419-216"></span></span>
|<span data-ttu-id="99419-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-218">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-218">passport number</span></span>  <br/> <span data-ttu-id="99419-219">número de passaporte tcheco</span><span class="sxs-lookup"><span data-stu-id="99419-219">czech passport number</span></span>  <br/> <span data-ttu-id="99419-220">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-220">passport no</span></span>  <br/> <span data-ttu-id="99419-221">Pas cestovní</span><span class="sxs-lookup"><span data-stu-id="99419-221">cestovní pas</span></span>  <br/> <span data-ttu-id="99419-222">Pas</span><span class="sxs-lookup"><span data-stu-id="99419-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="99419-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="99419-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="99419-224">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-224">Format</span></span>

<span data-ttu-id="99419-225">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-226">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-226">Pattern</span></span>

 <span data-ttu-id="99419-227">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="99419-228">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-228">Checksum</span></span>

<span data-ttu-id="99419-229">Não</span><span class="sxs-lookup"><span data-stu-id="99419-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-230">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-230">Definition</span></span>

<span data-ttu-id="99419-231">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-232">A expressão `Regex_denmark_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-233">Uma palavra- `Keywords_denmark_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-234">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-234">Keywords</span></span>

<span data-ttu-id="99419-235">| |</span><span class="sxs-lookup"><span data-stu-id="99419-235"></span></span>
|<span data-ttu-id="99419-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-237">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-237">passport number</span></span>  <br/> <span data-ttu-id="99419-238">número de passaporte dinamarquês</span><span class="sxs-lookup"><span data-stu-id="99419-238">danish passport number</span></span>  <br/> <span data-ttu-id="99419-239">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-239">passport no</span></span>  <br/> <span data-ttu-id="99419-240">Pas</span><span class="sxs-lookup"><span data-stu-id="99419-240">pas</span></span>  <br/> <span data-ttu-id="99419-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="99419-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="99419-242">Estônia</span><span class="sxs-lookup"><span data-stu-id="99419-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="99419-243">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-243">Format</span></span>

<span data-ttu-id="99419-244">Uma letra seguida por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-245">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-245">Pattern</span></span>

<span data-ttu-id="99419-246">Uma letra seguida por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-247">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-247">Checksum</span></span>

<span data-ttu-id="99419-248">Não</span><span class="sxs-lookup"><span data-stu-id="99419-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-249">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-249">Definition</span></span>

<span data-ttu-id="99419-250">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-251">A expressão `Regex_estonia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-252">Uma palavra- `Keywords_estonia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-253">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-253">Keywords</span></span>

<span data-ttu-id="99419-254">| |</span><span class="sxs-lookup"><span data-stu-id="99419-254"></span></span>
|<span data-ttu-id="99419-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-256">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-256">passport number</span></span>  <br/> <span data-ttu-id="99419-257">número de passaporte estoniano</span><span class="sxs-lookup"><span data-stu-id="99419-257">estonian passport number</span></span>  <br/> <span data-ttu-id="99419-258">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-258">passport no</span></span>  <br/> <span data-ttu-id="99419-259">Eesti kodaniku</span><span class="sxs-lookup"><span data-stu-id="99419-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="99419-260">Finlândia</span><span class="sxs-lookup"><span data-stu-id="99419-260">Finland</span></span>

<span data-ttu-id="99419-261">Para obter detalhes, consulte a seção "número de passaporte da Finlândia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99419-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="99419-262">França</span><span class="sxs-lookup"><span data-stu-id="99419-262">France</span></span>

<span data-ttu-id="99419-263">Para obter detalhes, consulte a seção "número do passaporte da França" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99419-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="99419-264">Alemanha</span><span class="sxs-lookup"><span data-stu-id="99419-264">Germany</span></span>

<span data-ttu-id="99419-265">Para obter detalhes, consulte a seção "número de passaporte da Alemanha" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99419-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="99419-266">Grécia</span><span class="sxs-lookup"><span data-stu-id="99419-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="99419-267">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-267">Format</span></span>

<span data-ttu-id="99419-268">Duas letras seguidas por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-269">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-269">Pattern</span></span>

<span data-ttu-id="99419-270">Duas letras seguidas por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-271">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-271">Checksum</span></span>

<span data-ttu-id="99419-272">Não</span><span class="sxs-lookup"><span data-stu-id="99419-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-273">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-273">Definition</span></span>

<span data-ttu-id="99419-274">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-275">A expressão `Regex_greece_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-276">Uma palavra- `Keywords_greece_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-277">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-277">Keywords</span></span>

<span data-ttu-id="99419-278">| |</span><span class="sxs-lookup"><span data-stu-id="99419-278"></span></span>
|<span data-ttu-id="99419-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-280">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-280">passport number</span></span>  <br/> <span data-ttu-id="99419-281">número de passaporte grego</span><span class="sxs-lookup"><span data-stu-id="99419-281">greek passport number</span></span>  <br/> <span data-ttu-id="99419-282">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-282">passport no</span></span>  <br/> <span data-ttu-id="99419-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="99419-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="99419-284">Hungria</span><span class="sxs-lookup"><span data-stu-id="99419-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="99419-285">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-285">Format</span></span>

<span data-ttu-id="99419-286">Duas letras seguidas por seis ou sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-287">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-287">Pattern</span></span>

<span data-ttu-id="99419-288">Duas letras seguidas por seis ou sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-289">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-289">Checksum</span></span>

<span data-ttu-id="99419-290">Não</span><span class="sxs-lookup"><span data-stu-id="99419-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-291">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-291">Definition</span></span>

<span data-ttu-id="99419-292">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-293">A expressão `Regex_hungary_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-294">Uma palavra- `Keywords_hungary_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-295">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-295">Keywords</span></span>

<span data-ttu-id="99419-296">| |</span><span class="sxs-lookup"><span data-stu-id="99419-296"></span></span>
|<span data-ttu-id="99419-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-298">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-298">passport number</span></span>  <br/> <span data-ttu-id="99419-299">número de passaporte húngaro</span><span class="sxs-lookup"><span data-stu-id="99419-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="99419-300">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-300">passport no</span></span>  <br/> <span data-ttu-id="99419-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="99419-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="99419-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="99419-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="99419-303">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-303">Format</span></span>

<span data-ttu-id="99419-304">Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-305">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-305">Pattern</span></span>

<span data-ttu-id="99419-306">Duas letras ou dígitos seguidos por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="99419-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="99419-307">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="99419-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="99419-308">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99419-309">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-309">Checksum</span></span>

<span data-ttu-id="99419-310">Não</span><span class="sxs-lookup"><span data-stu-id="99419-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-311">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-311">Definition</span></span>

<span data-ttu-id="99419-312">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-313">A expressão `Regex_ireland_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-314">Uma palavra- `Keywords_ireland_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-315">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-315">Keywords</span></span>

<span data-ttu-id="99419-316">| |</span><span class="sxs-lookup"><span data-stu-id="99419-316"></span></span>
|<span data-ttu-id="99419-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-318">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-318">passport number</span></span>  <br/> <span data-ttu-id="99419-319">número de passaporte do irlandês</span><span class="sxs-lookup"><span data-stu-id="99419-319">irish passport number</span></span>  <br/> <span data-ttu-id="99419-320">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-320">passport no</span></span>  <br/> <span data-ttu-id="99419-321">Pas</span><span class="sxs-lookup"><span data-stu-id="99419-321">pas</span></span>  <br/> <span data-ttu-id="99419-322">Passaport</span><span class="sxs-lookup"><span data-stu-id="99419-322">passport</span></span>  <br/> <span data-ttu-id="99419-323">passeport</span><span class="sxs-lookup"><span data-stu-id="99419-323">passeport</span></span>  <br/> <span data-ttu-id="99419-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="99419-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="99419-325">Itália</span><span class="sxs-lookup"><span data-stu-id="99419-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="99419-326">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-326">Format</span></span>

<span data-ttu-id="99419-327">Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-328">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-328">Pattern</span></span>

<span data-ttu-id="99419-329">Duas letras ou dígitos seguidos por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="99419-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="99419-330">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="99419-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="99419-331">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99419-332">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-332">Checksum</span></span>

<span data-ttu-id="99419-333">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="99419-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-334">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-334">Definition</span></span>

<span data-ttu-id="99419-335">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-336">A expressão `Regex_italy_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-337">Uma palavra- `Keywords_italy_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-338">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-338">Keywords</span></span>

<span data-ttu-id="99419-339">| |</span><span class="sxs-lookup"><span data-stu-id="99419-339"></span></span>
|<span data-ttu-id="99419-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-341">número de passaporte italiano</span><span class="sxs-lookup"><span data-stu-id="99419-341">italian passport number</span></span>  <br/> <span data-ttu-id="99419-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="99419-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="99419-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="99419-343">passaporto</span></span>  <br/> <span data-ttu-id="99419-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="99419-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="99419-345">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-345">passport number</span></span>  <br/> <span data-ttu-id="99419-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="99419-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="99419-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="99419-347">passaporto numero</span></span>  <br/> <span data-ttu-id="99419-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="99419-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="99419-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="99419-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="99419-350">Letônia</span><span class="sxs-lookup"><span data-stu-id="99419-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="99419-351">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-351">Format</span></span>

<span data-ttu-id="99419-352">Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-353">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-353">Pattern</span></span>

<span data-ttu-id="99419-354">Duas letras ou dígitos seguidos por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="99419-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="99419-355">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="99419-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="99419-356">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99419-357">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-357">Checksum</span></span>

<span data-ttu-id="99419-358">Não</span><span class="sxs-lookup"><span data-stu-id="99419-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-359">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-359">Definition</span></span>

<span data-ttu-id="99419-360">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-361">A expressão `Regex_latvia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-362">Uma palavra- `Keywords_latvia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-363">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-363">Keywords</span></span>

<span data-ttu-id="99419-364">| |</span><span class="sxs-lookup"><span data-stu-id="99419-364"></span></span>
|<span data-ttu-id="99419-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-366">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-366">passport number</span></span>  <br/> <span data-ttu-id="99419-367">número de passaporte da Letão</span><span class="sxs-lookup"><span data-stu-id="99419-367">latvian passport number</span></span>  <br/> <span data-ttu-id="99419-368">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-368">passport no</span></span>  <br/> <span data-ttu-id="99419-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="99419-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="99419-370">Lituânia</span><span class="sxs-lookup"><span data-stu-id="99419-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="99419-371">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-371">Format</span></span>

<span data-ttu-id="99419-372">Oito dígitos ou letras sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-373">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-373">Pattern</span></span>

<span data-ttu-id="99419-374">Oito dígitos ou letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="99419-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-375">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-375">Checksum</span></span>

<span data-ttu-id="99419-376">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="99419-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-377">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-377">Definition</span></span>

<span data-ttu-id="99419-378">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-379">A expressão `Regex_lithuania_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-380">Uma palavra- `Keywords_lithuania_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-381">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-381">Keywords</span></span>

<span data-ttu-id="99419-382">| |</span><span class="sxs-lookup"><span data-stu-id="99419-382"></span></span>
|<span data-ttu-id="99419-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-384">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-384">passport number</span></span>  <br/> <span data-ttu-id="99419-385">número de passaporte lithunian</span><span class="sxs-lookup"><span data-stu-id="99419-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="99419-386">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-386">passport no</span></span>  <br/> <span data-ttu-id="99419-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="99419-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="99419-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="99419-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="99419-389">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-389">Format</span></span>

<span data-ttu-id="99419-390">Oito dígitos ou letras sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-391">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-391">Pattern</span></span>

<span data-ttu-id="99419-392">Oito dígitos ou letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="99419-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-393">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-393">Checksum</span></span>

<span data-ttu-id="99419-394">Não</span><span class="sxs-lookup"><span data-stu-id="99419-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-395">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-395">Definition</span></span>

<span data-ttu-id="99419-396">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-397">A expressão `Regex_nation_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-398">Uma palavra- `Keywords_nation_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-399">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-399">Keywords</span></span>

<span data-ttu-id="99419-400">| |</span><span class="sxs-lookup"><span data-stu-id="99419-400"></span></span>
|<span data-ttu-id="99419-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-402">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-402">passport number</span></span>  <br/> <span data-ttu-id="99419-403">número de passaporte da Letão</span><span class="sxs-lookup"><span data-stu-id="99419-403">latvian passport number</span></span>  <br/> <span data-ttu-id="99419-404">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-404">passport no</span></span>  <br/> <span data-ttu-id="99419-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="99419-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="99419-406">Malta</span><span class="sxs-lookup"><span data-stu-id="99419-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="99419-407">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-407">Format</span></span>

<span data-ttu-id="99419-408">Sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-409">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-409">Pattern</span></span>

 <span data-ttu-id="99419-410">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="99419-411">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-411">Checksum</span></span>

<span data-ttu-id="99419-412">Não</span><span class="sxs-lookup"><span data-stu-id="99419-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-413">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-413">Definition</span></span>

<span data-ttu-id="99419-414">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-415">A expressão `Regex_malta_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-416">Uma palavra- `Keywords_malta_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-417">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-417">Keywords</span></span>

<span data-ttu-id="99419-418">| |</span><span class="sxs-lookup"><span data-stu-id="99419-418"></span></span>
|<span data-ttu-id="99419-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-420">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-420">passport number</span></span>  <br/> <span data-ttu-id="99419-421">número de passaporte Maltês</span><span class="sxs-lookup"><span data-stu-id="99419-421">maltese passport number</span></span>  <br/> <span data-ttu-id="99419-422">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-422">passport no</span></span>  <br/> <span data-ttu-id="99419-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="99419-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="99419-424">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="99419-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="99419-425">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-425">Format</span></span>

<span data-ttu-id="99419-426">Nove letras ou dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-427">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-427">Pattern</span></span>

<span data-ttu-id="99419-428">Nove letras ou dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-429">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-429">Checksum</span></span>

<span data-ttu-id="99419-430">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="99419-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-431">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-431">Definition</span></span>

<span data-ttu-id="99419-432">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-433">A expressão `Regex_netherlands_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-434">Uma palavra- `Keywords_netherlands_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-435">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-435">Keywords</span></span>

<span data-ttu-id="99419-436">| |</span><span class="sxs-lookup"><span data-stu-id="99419-436"></span></span>
|<span data-ttu-id="99419-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-438">número de passaporte holandês</span><span class="sxs-lookup"><span data-stu-id="99419-438">dutch passport number</span></span>  <br/> <span data-ttu-id="99419-439">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-439">passport number</span></span>  <br/> <span data-ttu-id="99419-440">número de passaporte Holanda</span><span class="sxs-lookup"><span data-stu-id="99419-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="99419-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="99419-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="99419-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="99419-442">paspoort</span></span>  <br/> <span data-ttu-id="99419-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="99419-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="99419-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="99419-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="99419-445">Polônia</span><span class="sxs-lookup"><span data-stu-id="99419-445">Poland</span></span>

<span data-ttu-id="99419-446">Para obter detalhes, consulte a seção "número de passaporte da Polônia" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99419-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="99419-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="99419-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="99419-448">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-448">Format</span></span>

<span data-ttu-id="99419-449">Uma letra seguida de seis dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-450">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-450">Pattern</span></span>

<span data-ttu-id="99419-451">Uma letra seguida por seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="99419-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="99419-452">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="99419-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="99419-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99419-454">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-454">Checksum</span></span>

<span data-ttu-id="99419-455">Não</span><span class="sxs-lookup"><span data-stu-id="99419-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-456">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-456">Definition</span></span>

<span data-ttu-id="99419-457">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-458">A expressão `Regex_portugal_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-459">Uma palavra- `Keywords_portugal_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-460">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-460">Keywords</span></span>

<span data-ttu-id="99419-461">| |</span><span class="sxs-lookup"><span data-stu-id="99419-461"></span></span>
|<span data-ttu-id="99419-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-463">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-463">passport number</span></span>  <br/> <span data-ttu-id="99419-464">número de passaporte Português</span><span class="sxs-lookup"><span data-stu-id="99419-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="99419-465">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-465">passport no</span></span>  <br/> <span data-ttu-id="99419-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="99419-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="99419-467">Romênia</span><span class="sxs-lookup"><span data-stu-id="99419-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="99419-468">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-468">Format</span></span>

<span data-ttu-id="99419-469">Oito ou nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-470">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-470">Pattern</span></span>

<span data-ttu-id="99419-471">Oito ou nove dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-472">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-472">Checksum</span></span>

<span data-ttu-id="99419-473">Não</span><span class="sxs-lookup"><span data-stu-id="99419-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-474">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-474">Definition</span></span>

<span data-ttu-id="99419-475">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-476">A expressão `Regex_romania_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-477">Uma palavra- `Keywords_romania_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-478">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-478">Keywords</span></span>

<span data-ttu-id="99419-479">| |</span><span class="sxs-lookup"><span data-stu-id="99419-479"></span></span>
|<span data-ttu-id="99419-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-481">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-481">passport number</span></span>  <br/> <span data-ttu-id="99419-482">número de passaporte romeno</span><span class="sxs-lookup"><span data-stu-id="99419-482">romanian passport number</span></span>  <br/> <span data-ttu-id="99419-483">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-483">passport no</span></span>  <br/> <span data-ttu-id="99419-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="99419-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="99419-485">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="99419-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="99419-486">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-486">Format</span></span>

<span data-ttu-id="99419-487">Um dígito ou letra seguido por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-488">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-488">Pattern</span></span>

<span data-ttu-id="99419-489">Um dígito ou letra (não diferencia maiúsculas de minúsculas) seguido por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99419-490">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-490">Checksum</span></span>

<span data-ttu-id="99419-491">Não</span><span class="sxs-lookup"><span data-stu-id="99419-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-492">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-492">Definition</span></span>

<span data-ttu-id="99419-493">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-494">A expressão `Regex_slovakia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-495">Uma palavra- `Keywords_slovakia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-496">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-496">Keywords</span></span>

<span data-ttu-id="99419-497">| |</span><span class="sxs-lookup"><span data-stu-id="99419-497"></span></span>
|<span data-ttu-id="99419-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-499">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-499">passport number</span></span>  <br/> <span data-ttu-id="99419-500">número de passaporte eslovaco</span><span class="sxs-lookup"><span data-stu-id="99419-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="99419-501">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-501">passport no</span></span>  <br/> <span data-ttu-id="99419-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="99419-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="99419-503">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="99419-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="99419-504">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-504">Format</span></span>

<span data-ttu-id="99419-505">Duas letras seguidas por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-506">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-506">Pattern</span></span>

<span data-ttu-id="99419-507">Duas letras seguidas por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="99419-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="99419-508">A letra "P"</span><span class="sxs-lookup"><span data-stu-id="99419-508">The letter "P"</span></span>
    
- <span data-ttu-id="99419-509">Uma letra maiúscula</span><span class="sxs-lookup"><span data-stu-id="99419-509">One uppercase letter</span></span>
    
- <span data-ttu-id="99419-510">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99419-511">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-511">Checksum</span></span>

<span data-ttu-id="99419-512">Não</span><span class="sxs-lookup"><span data-stu-id="99419-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-513">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-513">Definition</span></span>

<span data-ttu-id="99419-514">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-515">A expressão `Regex_slovenia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-516">Uma palavra- `Keywords_slovenia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-517">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-517">Keywords</span></span>

<span data-ttu-id="99419-518">| |</span><span class="sxs-lookup"><span data-stu-id="99419-518"></span></span>
|<span data-ttu-id="99419-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-520">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-520">passport number</span></span>  <br/> <span data-ttu-id="99419-521">número de passaporte esloveno</span><span class="sxs-lookup"><span data-stu-id="99419-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="99419-522">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-522">passport no</span></span>  <br/> <span data-ttu-id="99419-523">lista de številka potnega</span><span class="sxs-lookup"><span data-stu-id="99419-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="99419-524">Espanha</span><span class="sxs-lookup"><span data-stu-id="99419-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="99419-525">Formatar</span><span class="sxs-lookup"><span data-stu-id="99419-525">Format</span></span>

<span data-ttu-id="99419-526">Uma combinação de letras e números de oito ou nove caracteres sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="99419-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99419-527">Padrão</span><span class="sxs-lookup"><span data-stu-id="99419-527">Pattern</span></span>

<span data-ttu-id="99419-528">Uma combinação de letras e números de oito ou nove caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="99419-529">Dois dígitos ou letras</span><span class="sxs-lookup"><span data-stu-id="99419-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="99419-530">Um dígito ou letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="99419-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="99419-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="99419-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99419-532">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="99419-532">Checksum</span></span>

<span data-ttu-id="99419-533">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="99419-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99419-534">Definição</span><span class="sxs-lookup"><span data-stu-id="99419-534">Definition</span></span>

<span data-ttu-id="99419-535">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="99419-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99419-536">A expressão `Regex_spain_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="99419-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99419-537">Uma palavra- `Keywords_spain_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="99419-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99419-538">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="99419-538">Keywords</span></span>

<span data-ttu-id="99419-539">| |</span><span class="sxs-lookup"><span data-stu-id="99419-539"></span></span>
|<span data-ttu-id="99419-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99419-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99419-541">Passaport</span><span class="sxs-lookup"><span data-stu-id="99419-541">passport</span></span>  <br/> <span data-ttu-id="99419-542">o Passport da Espanha</span><span class="sxs-lookup"><span data-stu-id="99419-542">spain passport</span></span>  <br/> <span data-ttu-id="99419-543">Catálogo do Passport</span><span class="sxs-lookup"><span data-stu-id="99419-543">passport book</span></span>  <br/> <span data-ttu-id="99419-544">passport number</span><span class="sxs-lookup"><span data-stu-id="99419-544">passport number</span></span>  <br/> <span data-ttu-id="99419-545">Passport não</span><span class="sxs-lookup"><span data-stu-id="99419-545">passport no</span></span>  <br/> <span data-ttu-id="99419-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="99419-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="99419-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="99419-547">número pasaporte</span></span>  <br/> <span data-ttu-id="99419-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="99419-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="99419-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="99419-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="99419-550">Suécia</span><span class="sxs-lookup"><span data-stu-id="99419-550">Sweden</span></span>

<span data-ttu-id="99419-551">Para obter detalhes, consulte a seção "número de passaporte da Suécia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99419-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="99419-552">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="99419-552">UK</span></span>

<span data-ttu-id="99419-553">Para obter detalhes, consulte a seção "U.S./Reino Unido</span><span class="sxs-lookup"><span data-stu-id="99419-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="99419-554">Número do Passport "no [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99419-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99419-555">Confira também</span><span class="sxs-lookup"><span data-stu-id="99419-555">See also</span></span>

[<span data-ttu-id="99419-556">O que os tipos de informações confidenciais procuram</span><span class="sxs-lookup"><span data-stu-id="99419-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

