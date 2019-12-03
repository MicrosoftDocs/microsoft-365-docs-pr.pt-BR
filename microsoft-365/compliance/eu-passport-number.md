---
title: Número do Passport da UE
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número do Passport da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: 44ee6e7b46d79772bcd3aec0fd26265f58f6c4c6
ms.sourcegitcommit: 3fd6d175c1954ce463198e835d1d8f2f91d80d79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2019
ms.locfileid: "39662796"
---
# <a name="eu-passport-number"></a><span data-ttu-id="05cd7-104">Número do Passport da UE</span><span class="sxs-lookup"><span data-stu-id="05cd7-104">EU Passport Number</span></span>

<span data-ttu-id="05cd7-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número do Passport da UE.</span><span class="sxs-lookup"><span data-stu-id="05cd7-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="05cd7-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="05cd7-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="05cd7-107">Áustria</span><span class="sxs-lookup"><span data-stu-id="05cd7-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-108">Format</span></span>

<span data-ttu-id="05cd7-109">Uma letra seguida de um espaço opcional e sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-110">Pattern</span></span>

<span data-ttu-id="05cd7-111">Uma combinação de uma letra, sete dígitos e um espaço:</span><span class="sxs-lookup"><span data-stu-id="05cd7-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="05cd7-112">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="05cd7-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="05cd7-113">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="05cd7-113">One space (optional)</span></span>
    
- <span data-ttu-id="05cd7-114">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05cd7-115">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-115">Checksum</span></span>

<span data-ttu-id="05cd7-116">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="05cd7-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-117">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-117">Definition</span></span>

<span data-ttu-id="05cd7-118">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-119">A expressão `Regex_austria_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-120">Uma palavra- `Keywords_austria_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-121">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-121">Keywords</span></span>

<span data-ttu-id="05cd7-122">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-122"></span></span>
|<span data-ttu-id="05cd7-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-124">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-124">passport number</span></span>  <br/> <span data-ttu-id="05cd7-125">número de passaporte austríaco</span><span class="sxs-lookup"><span data-stu-id="05cd7-125">austrian passport number</span></span>  <br/> <span data-ttu-id="05cd7-126">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-126">passport no</span></span>  <br/> <span data-ttu-id="05cd7-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="05cd7-127">reisepass</span></span>  <br/> <span data-ttu-id="05cd7-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="05cd7-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="05cd7-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="05cd7-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-130">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-130">Format</span></span>

<span data-ttu-id="05cd7-131">Duas letras seguidas por seis dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-132">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-132">Pattern</span></span>

<span data-ttu-id="05cd7-133">Duas letras e seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-134">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-134">Checksum</span></span>

<span data-ttu-id="05cd7-135">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="05cd7-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-136">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-136">Definition</span></span>

<span data-ttu-id="05cd7-137">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-138">A expressão `Regex_belgium_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-139">Uma palavra- `Keywords_belgium_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-140">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-140">Keywords</span></span>

<span data-ttu-id="05cd7-141">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-141"></span></span>
|<span data-ttu-id="05cd7-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-143">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-143">passport number</span></span>  <br/> <span data-ttu-id="05cd7-144">número de passaporte belga</span><span class="sxs-lookup"><span data-stu-id="05cd7-144">belgian passport number</span></span>  <br/> <span data-ttu-id="05cd7-145">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-145">passport no</span></span>  <br/> <span data-ttu-id="05cd7-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="05cd7-146">paspoort</span></span>  <br/> <span data-ttu-id="05cd7-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="05cd7-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="05cd7-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="05cd7-148">reisepass kein</span></span>  <br/> <span data-ttu-id="05cd7-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="05cd7-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="05cd7-150">Bulgária</span><span class="sxs-lookup"><span data-stu-id="05cd7-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-151">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-151">Format</span></span>

<span data-ttu-id="05cd7-152">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-153">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-153">Pattern</span></span>

 <span data-ttu-id="05cd7-154">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="05cd7-155">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-155">Checksum</span></span>

<span data-ttu-id="05cd7-156">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-157">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-157">Definition</span></span>

<span data-ttu-id="05cd7-158">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-159">A expressão `Regex_bulgaria_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-160">Uma palavra- `Keywords_bulgaria_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-161">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-161">Keywords</span></span>

<span data-ttu-id="05cd7-162">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-162"></span></span>
|<span data-ttu-id="05cd7-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-164">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-164">passport number</span></span>  <br/> <span data-ttu-id="05cd7-165">número de passaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="05cd7-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="05cd7-166">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-166">passport no</span></span>  <br/> <span data-ttu-id="05cd7-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="05cd7-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="05cd7-168">Croácia</span><span class="sxs-lookup"><span data-stu-id="05cd7-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-169">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-169">Format</span></span>

<span data-ttu-id="05cd7-170">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-171">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-171">Pattern</span></span>

 <span data-ttu-id="05cd7-172">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="05cd7-173">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-173">Checksum</span></span>

<span data-ttu-id="05cd7-174">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-175">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-175">Definition</span></span>

<span data-ttu-id="05cd7-176">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-177">A expressão `Regex_croatia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-178">Uma palavra- `Keywords_croatia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-179">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-179">Keywords</span></span>

<span data-ttu-id="05cd7-180">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-180"></span></span>
|<span data-ttu-id="05cd7-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-182">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-182">passport number</span></span>  <br/> <span data-ttu-id="05cd7-183">número de passaporte Croata</span><span class="sxs-lookup"><span data-stu-id="05cd7-183">croatian passport number</span></span>  <br/> <span data-ttu-id="05cd7-184">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-184">passport no</span></span>  <br/> <span data-ttu-id="05cd7-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="05cd7-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="05cd7-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="05cd7-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-187">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-187">Format</span></span>

<span data-ttu-id="05cd7-188">Uma letra seguida de 6-8 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-189">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-189">Pattern</span></span>

<span data-ttu-id="05cd7-190">Uma letra seguida de seis a oito dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-191">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-191">Checksum</span></span>

<span data-ttu-id="05cd7-192">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-193">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-193">Definition</span></span>

<span data-ttu-id="05cd7-194">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-195">A expressão `Regex_cyprus_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-196">Uma palavra- `Keywords_cyprus_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-197">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-197">Keywords</span></span>

<span data-ttu-id="05cd7-198">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-198"></span></span>
|<span data-ttu-id="05cd7-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-200">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-200">passport number</span></span>  <br/> <span data-ttu-id="05cd7-201">número de passaporte do Chipre</span><span class="sxs-lookup"><span data-stu-id="05cd7-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="05cd7-202">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-202">passport no</span></span>  <br/> <span data-ttu-id="05cd7-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="05cd7-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="05cd7-204">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="05cd7-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-205">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-205">Format</span></span>

<span data-ttu-id="05cd7-206">Oito dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-207">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-207">Pattern</span></span>

<span data-ttu-id="05cd7-208">Oito dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-209">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-209">Checksum</span></span>

<span data-ttu-id="05cd7-210">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-211">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-211">Definition</span></span>

<span data-ttu-id="05cd7-212">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-213">A expressão `Regex_czech_republic_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-214">Uma palavra- `Keywords_czech_republic_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-215">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-215">Keywords</span></span>

<span data-ttu-id="05cd7-216">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-216"></span></span>
|<span data-ttu-id="05cd7-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-218">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-218">passport number</span></span>  <br/> <span data-ttu-id="05cd7-219">número de passaporte tcheco</span><span class="sxs-lookup"><span data-stu-id="05cd7-219">czech passport number</span></span>  <br/> <span data-ttu-id="05cd7-220">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-220">passport no</span></span>  <br/> <span data-ttu-id="05cd7-221">Pas cestovní</span><span class="sxs-lookup"><span data-stu-id="05cd7-221">cestovní pas</span></span>  <br/> <span data-ttu-id="05cd7-222">Pas</span><span class="sxs-lookup"><span data-stu-id="05cd7-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="05cd7-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="05cd7-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-224">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-224">Format</span></span>

<span data-ttu-id="05cd7-225">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-226">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-226">Pattern</span></span>

 <span data-ttu-id="05cd7-227">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="05cd7-228">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-228">Checksum</span></span>

<span data-ttu-id="05cd7-229">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-230">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-230">Definition</span></span>

<span data-ttu-id="05cd7-231">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-232">A expressão `Regex_denmark_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-233">Uma palavra- `Keywords_denmark_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-234">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-234">Keywords</span></span>

<span data-ttu-id="05cd7-235">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-235"></span></span>
|<span data-ttu-id="05cd7-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-237">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-237">passport number</span></span>  <br/> <span data-ttu-id="05cd7-238">número de passaporte dinamarquês</span><span class="sxs-lookup"><span data-stu-id="05cd7-238">danish passport number</span></span>  <br/> <span data-ttu-id="05cd7-239">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-239">passport no</span></span>  <br/> <span data-ttu-id="05cd7-240">Pas</span><span class="sxs-lookup"><span data-stu-id="05cd7-240">pas</span></span>  <br/> <span data-ttu-id="05cd7-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="05cd7-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="05cd7-242">Estônia</span><span class="sxs-lookup"><span data-stu-id="05cd7-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-243">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-243">Format</span></span>

<span data-ttu-id="05cd7-244">Uma letra seguida por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-245">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-245">Pattern</span></span>

<span data-ttu-id="05cd7-246">Uma letra seguida por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-247">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-247">Checksum</span></span>

<span data-ttu-id="05cd7-248">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-249">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-249">Definition</span></span>

<span data-ttu-id="05cd7-250">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-251">A expressão `Regex_estonia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-252">Uma palavra- `Keywords_estonia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-253">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-253">Keywords</span></span>

<span data-ttu-id="05cd7-254">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-254"></span></span>
|<span data-ttu-id="05cd7-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-256">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-256">passport number</span></span>  <br/> <span data-ttu-id="05cd7-257">número de passaporte estoniano</span><span class="sxs-lookup"><span data-stu-id="05cd7-257">estonian passport number</span></span>  <br/> <span data-ttu-id="05cd7-258">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-258">passport no</span></span>  <br/> <span data-ttu-id="05cd7-259">Eesti kodaniku</span><span class="sxs-lookup"><span data-stu-id="05cd7-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="05cd7-260">Finlândia</span><span class="sxs-lookup"><span data-stu-id="05cd7-260">Finland</span></span>

<span data-ttu-id="05cd7-261">Para obter detalhes, consulte a seção "número de passaporte da Finlândia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="05cd7-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="05cd7-262">França</span><span class="sxs-lookup"><span data-stu-id="05cd7-262">France</span></span>

<span data-ttu-id="05cd7-263">Para obter detalhes, consulte a seção "número do passaporte da França" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="05cd7-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="05cd7-264">Alemanha</span><span class="sxs-lookup"><span data-stu-id="05cd7-264">Germany</span></span>

<span data-ttu-id="05cd7-265">Para obter detalhes, consulte a seção "número do passaporte em alemão" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="05cd7-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="05cd7-266">Grécia</span><span class="sxs-lookup"><span data-stu-id="05cd7-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-267">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-267">Format</span></span>

<span data-ttu-id="05cd7-268">Duas letras seguidas por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-269">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-269">Pattern</span></span>

<span data-ttu-id="05cd7-270">Duas letras seguidas por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-271">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-271">Checksum</span></span>

<span data-ttu-id="05cd7-272">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-273">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-273">Definition</span></span>

<span data-ttu-id="05cd7-274">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-275">A expressão `Regex_greece_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-276">Uma palavra- `Keywords_greece_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-277">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-277">Keywords</span></span>

<span data-ttu-id="05cd7-278">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-278"></span></span>
|<span data-ttu-id="05cd7-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-280">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-280">passport number</span></span>  <br/> <span data-ttu-id="05cd7-281">número de passaporte grego</span><span class="sxs-lookup"><span data-stu-id="05cd7-281">greek passport number</span></span>  <br/> <span data-ttu-id="05cd7-282">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-282">passport no</span></span>  <br/> <span data-ttu-id="05cd7-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="05cd7-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="05cd7-284">Hungria</span><span class="sxs-lookup"><span data-stu-id="05cd7-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-285">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-285">Format</span></span>

<span data-ttu-id="05cd7-286">Duas letras seguidas por seis ou sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-287">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-287">Pattern</span></span>

<span data-ttu-id="05cd7-288">Duas letras seguidas por seis ou sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-289">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-289">Checksum</span></span>

<span data-ttu-id="05cd7-290">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-291">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-291">Definition</span></span>

<span data-ttu-id="05cd7-292">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-293">A expressão `Regex_hungary_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-294">Uma palavra- `Keywords_hungary_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-295">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-295">Keywords</span></span>

<span data-ttu-id="05cd7-296">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-296"></span></span>
|<span data-ttu-id="05cd7-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-298">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-298">passport number</span></span>  <br/> <span data-ttu-id="05cd7-299">número de passaporte húngaro</span><span class="sxs-lookup"><span data-stu-id="05cd7-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="05cd7-300">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-300">passport no</span></span>  <br/> <span data-ttu-id="05cd7-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="05cd7-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="05cd7-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="05cd7-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-303">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-303">Format</span></span>

<span data-ttu-id="05cd7-304">Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-305">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-305">Pattern</span></span>

<span data-ttu-id="05cd7-306">Duas letras ou dígitos seguidos por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="05cd7-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="05cd7-307">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="05cd7-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="05cd7-308">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05cd7-309">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-309">Checksum</span></span>

<span data-ttu-id="05cd7-310">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-311">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-311">Definition</span></span>

<span data-ttu-id="05cd7-312">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-313">A expressão `Regex_ireland_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-314">Uma palavra- `Keywords_ireland_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-315">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-315">Keywords</span></span>

<span data-ttu-id="05cd7-316">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-316"></span></span>
|<span data-ttu-id="05cd7-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-318">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-318">passport number</span></span>  <br/> <span data-ttu-id="05cd7-319">número de passaporte do irlandês</span><span class="sxs-lookup"><span data-stu-id="05cd7-319">irish passport number</span></span>  <br/> <span data-ttu-id="05cd7-320">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-320">passport no</span></span>  <br/> <span data-ttu-id="05cd7-321">Pas</span><span class="sxs-lookup"><span data-stu-id="05cd7-321">pas</span></span>  <br/> <span data-ttu-id="05cd7-322">Passaport</span><span class="sxs-lookup"><span data-stu-id="05cd7-322">passport</span></span>  <br/> <span data-ttu-id="05cd7-323">passeport</span><span class="sxs-lookup"><span data-stu-id="05cd7-323">passeport</span></span>  <br/> <span data-ttu-id="05cd7-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="05cd7-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="05cd7-325">Itália</span><span class="sxs-lookup"><span data-stu-id="05cd7-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-326">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-326">Format</span></span>

<span data-ttu-id="05cd7-327">Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-328">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-328">Pattern</span></span>

<span data-ttu-id="05cd7-329">Duas letras ou dígitos seguidos por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="05cd7-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="05cd7-330">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="05cd7-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="05cd7-331">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05cd7-332">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-332">Checksum</span></span>

<span data-ttu-id="05cd7-333">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="05cd7-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-334">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-334">Definition</span></span>

<span data-ttu-id="05cd7-335">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-336">A expressão `Regex_italy_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-337">Uma palavra- `Keywords_italy_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-338">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-338">Keywords</span></span>

<span data-ttu-id="05cd7-339">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-339"></span></span>
|<span data-ttu-id="05cd7-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-341">número de passaporte italiano</span><span class="sxs-lookup"><span data-stu-id="05cd7-341">italian passport number</span></span>  <br/> <span data-ttu-id="05cd7-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="05cd7-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="05cd7-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="05cd7-343">passaporto</span></span>  <br/> <span data-ttu-id="05cd7-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="05cd7-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="05cd7-345">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-345">passport number</span></span>  <br/> <span data-ttu-id="05cd7-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="05cd7-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="05cd7-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="05cd7-347">passaporto numero</span></span>  <br/> <span data-ttu-id="05cd7-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="05cd7-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="05cd7-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="05cd7-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="05cd7-350">Letônia</span><span class="sxs-lookup"><span data-stu-id="05cd7-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-351">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-351">Format</span></span>

<span data-ttu-id="05cd7-352">Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-353">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-353">Pattern</span></span>

<span data-ttu-id="05cd7-354">Duas letras ou dígitos seguidos por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="05cd7-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="05cd7-355">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="05cd7-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="05cd7-356">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05cd7-357">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-357">Checksum</span></span>

<span data-ttu-id="05cd7-358">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-359">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-359">Definition</span></span>

<span data-ttu-id="05cd7-360">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-361">A expressão `Regex_latvia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-362">Uma palavra- `Keywords_latvia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-363">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-363">Keywords</span></span>

<span data-ttu-id="05cd7-364">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-364"></span></span>
|<span data-ttu-id="05cd7-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-366">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-366">passport number</span></span>  <br/> <span data-ttu-id="05cd7-367">número de passaporte da Letão</span><span class="sxs-lookup"><span data-stu-id="05cd7-367">latvian passport number</span></span>  <br/> <span data-ttu-id="05cd7-368">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-368">passport no</span></span>  <br/> <span data-ttu-id="05cd7-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="05cd7-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="05cd7-370">Lituânia</span><span class="sxs-lookup"><span data-stu-id="05cd7-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-371">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-371">Format</span></span>

<span data-ttu-id="05cd7-372">Oito dígitos ou letras sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-373">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-373">Pattern</span></span>

<span data-ttu-id="05cd7-374">Oito dígitos ou letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="05cd7-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-375">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-375">Checksum</span></span>

<span data-ttu-id="05cd7-376">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="05cd7-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-377">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-377">Definition</span></span>

<span data-ttu-id="05cd7-378">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-379">A expressão `Regex_lithuania_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-380">Uma palavra- `Keywords_lithuania_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-381">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-381">Keywords</span></span>

<span data-ttu-id="05cd7-382">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-382"></span></span>
|<span data-ttu-id="05cd7-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-384">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-384">passport number</span></span>  <br/> <span data-ttu-id="05cd7-385">número de passaporte lithunian</span><span class="sxs-lookup"><span data-stu-id="05cd7-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="05cd7-386">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-386">passport no</span></span>  <br/> <span data-ttu-id="05cd7-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="05cd7-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="05cd7-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="05cd7-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-389">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-389">Format</span></span>

<span data-ttu-id="05cd7-390">Oito dígitos ou letras sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-391">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-391">Pattern</span></span>

<span data-ttu-id="05cd7-392">Oito dígitos ou letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="05cd7-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-393">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-393">Checksum</span></span>

<span data-ttu-id="05cd7-394">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-395">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-395">Definition</span></span>

<span data-ttu-id="05cd7-396">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-397">A expressão `Regex_nation_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-398">Uma palavra- `Keywords_nation_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-399">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-399">Keywords</span></span>

<span data-ttu-id="05cd7-400">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-400"></span></span>
|<span data-ttu-id="05cd7-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-402">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-402">passport number</span></span>  <br/> <span data-ttu-id="05cd7-403">número de passaporte da Letão</span><span class="sxs-lookup"><span data-stu-id="05cd7-403">latvian passport number</span></span>  <br/> <span data-ttu-id="05cd7-404">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-404">passport no</span></span>  <br/> <span data-ttu-id="05cd7-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="05cd7-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="05cd7-406">Malta</span><span class="sxs-lookup"><span data-stu-id="05cd7-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-407">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-407">Format</span></span>

<span data-ttu-id="05cd7-408">Sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-409">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-409">Pattern</span></span>

 <span data-ttu-id="05cd7-410">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="05cd7-411">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-411">Checksum</span></span>

<span data-ttu-id="05cd7-412">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-413">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-413">Definition</span></span>

<span data-ttu-id="05cd7-414">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-415">A expressão `Regex_malta_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-416">Uma palavra- `Keywords_malta_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-417">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-417">Keywords</span></span>

<span data-ttu-id="05cd7-418">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-418"></span></span>
|<span data-ttu-id="05cd7-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-420">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-420">passport number</span></span>  <br/> <span data-ttu-id="05cd7-421">número de passaporte Maltês</span><span class="sxs-lookup"><span data-stu-id="05cd7-421">maltese passport number</span></span>  <br/> <span data-ttu-id="05cd7-422">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-422">passport no</span></span>  <br/> <span data-ttu-id="05cd7-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="05cd7-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="05cd7-424">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="05cd7-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-425">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-425">Format</span></span>

<span data-ttu-id="05cd7-426">Nove letras ou dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-427">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-427">Pattern</span></span>

<span data-ttu-id="05cd7-428">Nove letras ou dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-429">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-429">Checksum</span></span>

<span data-ttu-id="05cd7-430">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="05cd7-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-431">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-431">Definition</span></span>

<span data-ttu-id="05cd7-432">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-433">A expressão `Regex_netherlands_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-434">Uma palavra- `Keywords_netherlands_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-435">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-435">Keywords</span></span>

<span data-ttu-id="05cd7-436">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-436"></span></span>
|<span data-ttu-id="05cd7-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-438">número de passaporte holandês</span><span class="sxs-lookup"><span data-stu-id="05cd7-438">dutch passport number</span></span>  <br/> <span data-ttu-id="05cd7-439">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-439">passport number</span></span>  <br/> <span data-ttu-id="05cd7-440">número de passaporte Holanda</span><span class="sxs-lookup"><span data-stu-id="05cd7-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="05cd7-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="05cd7-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="05cd7-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="05cd7-442">paspoort</span></span>  <br/> <span data-ttu-id="05cd7-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="05cd7-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="05cd7-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="05cd7-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="05cd7-445">Polônia</span><span class="sxs-lookup"><span data-stu-id="05cd7-445">Poland</span></span>

<span data-ttu-id="05cd7-446">Para obter detalhes, consulte a seção "número de passaporte da Polônia" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="05cd7-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="05cd7-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="05cd7-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-448">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-448">Format</span></span>

<span data-ttu-id="05cd7-449">Uma letra seguida de seis dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-450">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-450">Pattern</span></span>

<span data-ttu-id="05cd7-451">Uma letra seguida por seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="05cd7-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="05cd7-452">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="05cd7-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="05cd7-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05cd7-454">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-454">Checksum</span></span>

<span data-ttu-id="05cd7-455">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-456">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-456">Definition</span></span>

<span data-ttu-id="05cd7-457">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-458">A expressão `Regex_portugal_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-459">Uma palavra- `Keywords_portugal_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-460">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-460">Keywords</span></span>

<span data-ttu-id="05cd7-461">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-461"></span></span>
|<span data-ttu-id="05cd7-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-463">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-463">passport number</span></span>  <br/> <span data-ttu-id="05cd7-464">número de passaporte Português</span><span class="sxs-lookup"><span data-stu-id="05cd7-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="05cd7-465">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-465">passport no</span></span>  <br/> <span data-ttu-id="05cd7-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="05cd7-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="05cd7-467">Romênia</span><span class="sxs-lookup"><span data-stu-id="05cd7-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-468">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-468">Format</span></span>

<span data-ttu-id="05cd7-469">Oito ou nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-470">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-470">Pattern</span></span>

<span data-ttu-id="05cd7-471">Oito ou nove dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-472">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-472">Checksum</span></span>

<span data-ttu-id="05cd7-473">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-474">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-474">Definition</span></span>

<span data-ttu-id="05cd7-475">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-476">A expressão `Regex_romania_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-477">Uma palavra- `Keywords_romania_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-478">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-478">Keywords</span></span>

<span data-ttu-id="05cd7-479">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-479"></span></span>
|<span data-ttu-id="05cd7-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-481">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-481">passport number</span></span>  <br/> <span data-ttu-id="05cd7-482">número de passaporte romeno</span><span class="sxs-lookup"><span data-stu-id="05cd7-482">romanian passport number</span></span>  <br/> <span data-ttu-id="05cd7-483">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-483">passport no</span></span>  <br/> <span data-ttu-id="05cd7-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="05cd7-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="05cd7-485">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="05cd7-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-486">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-486">Format</span></span>

<span data-ttu-id="05cd7-487">Um dígito ou letra seguido por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-488">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-488">Pattern</span></span>

<span data-ttu-id="05cd7-489">Um dígito ou letra (não diferencia maiúsculas de minúsculas) seguido por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05cd7-490">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-490">Checksum</span></span>

<span data-ttu-id="05cd7-491">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-492">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-492">Definition</span></span>

<span data-ttu-id="05cd7-493">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-494">A expressão `Regex_slovakia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-495">Uma palavra- `Keywords_slovakia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-496">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-496">Keywords</span></span>

<span data-ttu-id="05cd7-497">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-497"></span></span>
|<span data-ttu-id="05cd7-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-499">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-499">passport number</span></span>  <br/> <span data-ttu-id="05cd7-500">número de passaporte eslovaco</span><span class="sxs-lookup"><span data-stu-id="05cd7-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="05cd7-501">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-501">passport no</span></span>  <br/> <span data-ttu-id="05cd7-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="05cd7-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="05cd7-503">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="05cd7-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-504">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-504">Format</span></span>

<span data-ttu-id="05cd7-505">Duas letras seguidas por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-506">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-506">Pattern</span></span>

<span data-ttu-id="05cd7-507">Duas letras seguidas por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="05cd7-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="05cd7-508">A letra "P"</span><span class="sxs-lookup"><span data-stu-id="05cd7-508">The letter "P"</span></span>
    
- <span data-ttu-id="05cd7-509">Uma letra maiúscula</span><span class="sxs-lookup"><span data-stu-id="05cd7-509">One uppercase letter</span></span>
    
- <span data-ttu-id="05cd7-510">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05cd7-511">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-511">Checksum</span></span>

<span data-ttu-id="05cd7-512">Não</span><span class="sxs-lookup"><span data-stu-id="05cd7-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-513">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-513">Definition</span></span>

<span data-ttu-id="05cd7-514">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-515">A expressão `Regex_slovenia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-516">Uma palavra- `Keywords_slovenia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-517">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-517">Keywords</span></span>

<span data-ttu-id="05cd7-518">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-518"></span></span>
|<span data-ttu-id="05cd7-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-520">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-520">passport number</span></span>  <br/> <span data-ttu-id="05cd7-521">número de passaporte esloveno</span><span class="sxs-lookup"><span data-stu-id="05cd7-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="05cd7-522">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-522">passport no</span></span>  <br/> <span data-ttu-id="05cd7-523">lista de številka potnega</span><span class="sxs-lookup"><span data-stu-id="05cd7-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="05cd7-524">Espanha</span><span class="sxs-lookup"><span data-stu-id="05cd7-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="05cd7-525">Formatar</span><span class="sxs-lookup"><span data-stu-id="05cd7-525">Format</span></span>

<span data-ttu-id="05cd7-526">Uma combinação de letras e números de oito ou nove caracteres sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="05cd7-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05cd7-527">Padrão</span><span class="sxs-lookup"><span data-stu-id="05cd7-527">Pattern</span></span>

<span data-ttu-id="05cd7-528">Uma combinação de letras e números de oito ou nove caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="05cd7-529">Dois dígitos ou letras</span><span class="sxs-lookup"><span data-stu-id="05cd7-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="05cd7-530">Um dígito ou letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="05cd7-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="05cd7-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="05cd7-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05cd7-532">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="05cd7-532">Checksum</span></span>

<span data-ttu-id="05cd7-533">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="05cd7-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05cd7-534">Definição</span><span class="sxs-lookup"><span data-stu-id="05cd7-534">Definition</span></span>

<span data-ttu-id="05cd7-535">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="05cd7-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05cd7-536">A expressão `Regex_spain_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="05cd7-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05cd7-537">Uma palavra- `Keywords_spain_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="05cd7-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05cd7-538">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="05cd7-538">Keywords</span></span>

<span data-ttu-id="05cd7-539">| |</span><span class="sxs-lookup"><span data-stu-id="05cd7-539"></span></span>
|<span data-ttu-id="05cd7-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="05cd7-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="05cd7-541">Passaport</span><span class="sxs-lookup"><span data-stu-id="05cd7-541">passport</span></span>  <br/> <span data-ttu-id="05cd7-542">o Passport da Espanha</span><span class="sxs-lookup"><span data-stu-id="05cd7-542">spain passport</span></span>  <br/> <span data-ttu-id="05cd7-543">Catálogo do Passport</span><span class="sxs-lookup"><span data-stu-id="05cd7-543">passport book</span></span>  <br/> <span data-ttu-id="05cd7-544">passport number</span><span class="sxs-lookup"><span data-stu-id="05cd7-544">passport number</span></span>  <br/> <span data-ttu-id="05cd7-545">Passport não</span><span class="sxs-lookup"><span data-stu-id="05cd7-545">passport no</span></span>  <br/> <span data-ttu-id="05cd7-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="05cd7-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="05cd7-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="05cd7-547">número pasaporte</span></span>  <br/> <span data-ttu-id="05cd7-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="05cd7-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="05cd7-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="05cd7-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="05cd7-550">Suécia</span><span class="sxs-lookup"><span data-stu-id="05cd7-550">Sweden</span></span>

<span data-ttu-id="05cd7-551">Para obter detalhes, consulte a seção "número de passaporte da Suécia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="05cd7-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="05cd7-552">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="05cd7-552">UK</span></span>

<span data-ttu-id="05cd7-553">Para obter detalhes, consulte a seção "U.S./Reino Unido</span><span class="sxs-lookup"><span data-stu-id="05cd7-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="05cd7-554">Número do Passport "no [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="05cd7-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="05cd7-555">Confira também</span><span class="sxs-lookup"><span data-stu-id="05cd7-555">See also</span></span>

[<span data-ttu-id="05cd7-556">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="05cd7-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

