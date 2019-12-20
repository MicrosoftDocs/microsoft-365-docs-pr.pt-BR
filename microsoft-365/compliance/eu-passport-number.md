---
title: Número do Passport da UE
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número do Passport da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: 4afcf7b764eb8976e0588464515256f7cb1bdb8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805944"
---
# <a name="eu-passport-number"></a><span data-ttu-id="3bdbc-104">Número do Passport da UE</span><span class="sxs-lookup"><span data-stu-id="3bdbc-104">EU Passport Number</span></span>

<span data-ttu-id="3bdbc-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número do Passport da UE.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="3bdbc-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3bdbc-107">Áustria</span><span class="sxs-lookup"><span data-stu-id="3bdbc-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-108">Format</span></span>

<span data-ttu-id="3bdbc-109">Uma letra seguida de um espaço opcional e sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-110">Pattern</span></span>

<span data-ttu-id="3bdbc-111">Uma combinação de uma letra, sete dígitos e um espaço:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="3bdbc-112">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="3bdbc-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="3bdbc-113">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="3bdbc-113">One space (optional)</span></span>
    
- <span data-ttu-id="3bdbc-114">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3bdbc-115">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-115">Checksum</span></span>

<span data-ttu-id="3bdbc-116">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="3bdbc-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-117">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-117">Definition</span></span>

<span data-ttu-id="3bdbc-118">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-119">A expressão `Regex_austria_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-120">Uma palavra- `Keywords_austria_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-121">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-121">Keywords</span></span>

<span data-ttu-id="3bdbc-122">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-122"></span></span>
|<span data-ttu-id="3bdbc-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-124">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-124">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-125">número de passaporte austríaco</span><span class="sxs-lookup"><span data-stu-id="3bdbc-125">austrian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-126">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-126">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="3bdbc-127">reisepass</span></span>  <br/> <span data-ttu-id="3bdbc-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="3bdbc-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="3bdbc-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="3bdbc-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-130">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-130">Format</span></span>

<span data-ttu-id="3bdbc-131">Duas letras seguidas por seis dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-132">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-132">Pattern</span></span>

<span data-ttu-id="3bdbc-133">Duas letras e seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-134">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-134">Checksum</span></span>

<span data-ttu-id="3bdbc-135">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="3bdbc-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-136">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-136">Definition</span></span>

<span data-ttu-id="3bdbc-137">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-138">A expressão `Regex_belgium_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-139">Uma palavra- `Keywords_belgium_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-140">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-140">Keywords</span></span>

<span data-ttu-id="3bdbc-141">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-141"></span></span>
|<span data-ttu-id="3bdbc-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-143">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-143">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-144">número de passaporte belga</span><span class="sxs-lookup"><span data-stu-id="3bdbc-144">belgian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-145">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-145">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="3bdbc-146">paspoort</span></span>  <br/> <span data-ttu-id="3bdbc-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3bdbc-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="3bdbc-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="3bdbc-148">reisepass kein</span></span>  <br/> <span data-ttu-id="3bdbc-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="3bdbc-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="3bdbc-150">Bulgária</span><span class="sxs-lookup"><span data-stu-id="3bdbc-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-151">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-151">Format</span></span>

<span data-ttu-id="3bdbc-152">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-153">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-153">Pattern</span></span>

 <span data-ttu-id="3bdbc-154">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-155">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-155">Checksum</span></span>

<span data-ttu-id="3bdbc-156">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-157">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-157">Definition</span></span>

<span data-ttu-id="3bdbc-158">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-159">A expressão `Regex_bulgaria_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-160">Uma palavra- `Keywords_bulgaria_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-161">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-161">Keywords</span></span>

<span data-ttu-id="3bdbc-162">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-162"></span></span>
|<span data-ttu-id="3bdbc-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-164">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-164">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-165">número de passaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="3bdbc-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-166">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-166">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="3bdbc-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="3bdbc-168">Croácia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-169">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-169">Format</span></span>

<span data-ttu-id="3bdbc-170">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-171">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-171">Pattern</span></span>

 <span data-ttu-id="3bdbc-172">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-173">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-173">Checksum</span></span>

<span data-ttu-id="3bdbc-174">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-175">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-175">Definition</span></span>

<span data-ttu-id="3bdbc-176">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-177">A expressão `Regex_croatia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-178">Uma palavra- `Keywords_croatia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-179">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-179">Keywords</span></span>

<span data-ttu-id="3bdbc-180">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-180"></span></span>
|<span data-ttu-id="3bdbc-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-182">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-182">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-183">número de passaporte Croata</span><span class="sxs-lookup"><span data-stu-id="3bdbc-183">croatian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-184">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-184">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="3bdbc-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="3bdbc-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="3bdbc-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-187">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-187">Format</span></span>

<span data-ttu-id="3bdbc-188">Uma letra seguida de 6-8 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-189">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-189">Pattern</span></span>

<span data-ttu-id="3bdbc-190">Uma letra seguida de seis a oito dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-191">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-191">Checksum</span></span>

<span data-ttu-id="3bdbc-192">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-193">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-193">Definition</span></span>

<span data-ttu-id="3bdbc-194">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-195">A expressão `Regex_cyprus_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-196">Uma palavra- `Keywords_cyprus_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-197">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-197">Keywords</span></span>

<span data-ttu-id="3bdbc-198">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-198"></span></span>
|<span data-ttu-id="3bdbc-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-200">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-200">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-201">número de passaporte do Chipre</span><span class="sxs-lookup"><span data-stu-id="3bdbc-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="3bdbc-202">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-202">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="3bdbc-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="3bdbc-204">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="3bdbc-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-205">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-205">Format</span></span>

<span data-ttu-id="3bdbc-206">Oito dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-207">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-207">Pattern</span></span>

<span data-ttu-id="3bdbc-208">Oito dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-209">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-209">Checksum</span></span>

<span data-ttu-id="3bdbc-210">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-211">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-211">Definition</span></span>

<span data-ttu-id="3bdbc-212">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-213">A expressão `Regex_czech_republic_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-214">Uma palavra- `Keywords_czech_republic_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-215">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-215">Keywords</span></span>

<span data-ttu-id="3bdbc-216">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-216"></span></span>
|<span data-ttu-id="3bdbc-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-218">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-218">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-219">número de passaporte tcheco</span><span class="sxs-lookup"><span data-stu-id="3bdbc-219">czech passport number</span></span>  <br/> <span data-ttu-id="3bdbc-220">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-220">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-221">Pas cestovní</span><span class="sxs-lookup"><span data-stu-id="3bdbc-221">cestovní pas</span></span>  <br/> <span data-ttu-id="3bdbc-222">Pas</span><span class="sxs-lookup"><span data-stu-id="3bdbc-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="3bdbc-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="3bdbc-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-224">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-224">Format</span></span>

<span data-ttu-id="3bdbc-225">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-226">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-226">Pattern</span></span>

 <span data-ttu-id="3bdbc-227">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-228">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-228">Checksum</span></span>

<span data-ttu-id="3bdbc-229">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-230">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-230">Definition</span></span>

<span data-ttu-id="3bdbc-231">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-232">A expressão `Regex_denmark_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-233">Uma palavra- `Keywords_denmark_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-234">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-234">Keywords</span></span>

<span data-ttu-id="3bdbc-235">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-235"></span></span>
|<span data-ttu-id="3bdbc-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-237">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-237">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-238">número de passaporte dinamarquês</span><span class="sxs-lookup"><span data-stu-id="3bdbc-238">danish passport number</span></span>  <br/> <span data-ttu-id="3bdbc-239">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-239">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-240">Pas</span><span class="sxs-lookup"><span data-stu-id="3bdbc-240">pas</span></span>  <br/> <span data-ttu-id="3bdbc-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="3bdbc-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="3bdbc-242">Estônia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-243">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-243">Format</span></span>

<span data-ttu-id="3bdbc-244">Uma letra seguida por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-245">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-245">Pattern</span></span>

<span data-ttu-id="3bdbc-246">Uma letra seguida por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-247">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-247">Checksum</span></span>

<span data-ttu-id="3bdbc-248">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-249">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-249">Definition</span></span>

<span data-ttu-id="3bdbc-250">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-251">A expressão `Regex_estonia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-252">Uma palavra- `Keywords_estonia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-253">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-253">Keywords</span></span>

<span data-ttu-id="3bdbc-254">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-254"></span></span>
|<span data-ttu-id="3bdbc-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-256">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-256">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-257">número de passaporte estoniano</span><span class="sxs-lookup"><span data-stu-id="3bdbc-257">estonian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-258">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-258">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-259">Eesti kodaniku</span><span class="sxs-lookup"><span data-stu-id="3bdbc-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="3bdbc-260">Finlândia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-260">Finland</span></span>

<span data-ttu-id="3bdbc-261">Para obter detalhes, consulte a seção "número de passaporte da Finlândia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3bdbc-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="3bdbc-262">França</span><span class="sxs-lookup"><span data-stu-id="3bdbc-262">France</span></span>

<span data-ttu-id="3bdbc-263">Para obter detalhes, consulte a seção "número do passaporte da França" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3bdbc-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="3bdbc-264">Alemanha</span><span class="sxs-lookup"><span data-stu-id="3bdbc-264">Germany</span></span>

<span data-ttu-id="3bdbc-265">Para obter detalhes, consulte a seção "número do passaporte em alemão" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3bdbc-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="3bdbc-266">Grécia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-267">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-267">Format</span></span>

<span data-ttu-id="3bdbc-268">Duas letras seguidas por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-269">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-269">Pattern</span></span>

<span data-ttu-id="3bdbc-270">Duas letras seguidas por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-271">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-271">Checksum</span></span>

<span data-ttu-id="3bdbc-272">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-273">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-273">Definition</span></span>

<span data-ttu-id="3bdbc-274">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-275">A expressão `Regex_greece_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-276">Uma palavra- `Keywords_greece_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-277">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-277">Keywords</span></span>

<span data-ttu-id="3bdbc-278">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-278"></span></span>
|<span data-ttu-id="3bdbc-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-280">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-280">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-281">número de passaporte grego</span><span class="sxs-lookup"><span data-stu-id="3bdbc-281">greek passport number</span></span>  <br/> <span data-ttu-id="3bdbc-282">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-282">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="3bdbc-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="3bdbc-284">Hungria</span><span class="sxs-lookup"><span data-stu-id="3bdbc-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-285">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-285">Format</span></span>

<span data-ttu-id="3bdbc-286">Duas letras seguidas por seis ou sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-287">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-287">Pattern</span></span>

<span data-ttu-id="3bdbc-288">Duas letras seguidas por seis ou sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-289">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-289">Checksum</span></span>

<span data-ttu-id="3bdbc-290">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-291">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-291">Definition</span></span>

<span data-ttu-id="3bdbc-292">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-293">A expressão `Regex_hungary_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-294">Uma palavra- `Keywords_hungary_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-295">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-295">Keywords</span></span>

<span data-ttu-id="3bdbc-296">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-296"></span></span>
|<span data-ttu-id="3bdbc-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-298">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-298">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-299">número de passaporte húngaro</span><span class="sxs-lookup"><span data-stu-id="3bdbc-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-300">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-300">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="3bdbc-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="3bdbc-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="3bdbc-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-303">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-303">Format</span></span>

<span data-ttu-id="3bdbc-304">Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-305">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-305">Pattern</span></span>

<span data-ttu-id="3bdbc-306">Duas letras ou dígitos seguidos por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3bdbc-307">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="3bdbc-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3bdbc-308">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3bdbc-309">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-309">Checksum</span></span>

<span data-ttu-id="3bdbc-310">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-311">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-311">Definition</span></span>

<span data-ttu-id="3bdbc-312">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-313">A expressão `Regex_ireland_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-314">Uma palavra- `Keywords_ireland_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-315">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-315">Keywords</span></span>

<span data-ttu-id="3bdbc-316">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-316"></span></span>
|<span data-ttu-id="3bdbc-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-318">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-318">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-319">número de passaporte do irlandês</span><span class="sxs-lookup"><span data-stu-id="3bdbc-319">irish passport number</span></span>  <br/> <span data-ttu-id="3bdbc-320">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-320">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-321">Pas</span><span class="sxs-lookup"><span data-stu-id="3bdbc-321">pas</span></span>  <br/> <span data-ttu-id="3bdbc-322">Passaport</span><span class="sxs-lookup"><span data-stu-id="3bdbc-322">passport</span></span>  <br/> <span data-ttu-id="3bdbc-323">passeport</span><span class="sxs-lookup"><span data-stu-id="3bdbc-323">passeport</span></span>  <br/> <span data-ttu-id="3bdbc-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="3bdbc-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="3bdbc-325">Itália</span><span class="sxs-lookup"><span data-stu-id="3bdbc-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-326">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-326">Format</span></span>

<span data-ttu-id="3bdbc-327">Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-328">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-328">Pattern</span></span>

<span data-ttu-id="3bdbc-329">Duas letras ou dígitos seguidos por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3bdbc-330">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="3bdbc-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3bdbc-331">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3bdbc-332">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-332">Checksum</span></span>

<span data-ttu-id="3bdbc-333">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="3bdbc-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-334">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-334">Definition</span></span>

<span data-ttu-id="3bdbc-335">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-336">A expressão `Regex_italy_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-337">Uma palavra- `Keywords_italy_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-338">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-338">Keywords</span></span>

<span data-ttu-id="3bdbc-339">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-339"></span></span>
|<span data-ttu-id="3bdbc-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-341">número de passaporte italiano</span><span class="sxs-lookup"><span data-stu-id="3bdbc-341">italian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="3bdbc-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="3bdbc-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="3bdbc-343">passaporto</span></span>  <br/> <span data-ttu-id="3bdbc-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="3bdbc-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="3bdbc-345">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-345">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="3bdbc-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="3bdbc-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="3bdbc-347">passaporto numero</span></span>  <br/> <span data-ttu-id="3bdbc-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="3bdbc-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="3bdbc-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="3bdbc-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="3bdbc-350">Letônia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-351">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-351">Format</span></span>

<span data-ttu-id="3bdbc-352">Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-353">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-353">Pattern</span></span>

<span data-ttu-id="3bdbc-354">Duas letras ou dígitos seguidos por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3bdbc-355">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="3bdbc-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3bdbc-356">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3bdbc-357">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-357">Checksum</span></span>

<span data-ttu-id="3bdbc-358">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-359">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-359">Definition</span></span>

<span data-ttu-id="3bdbc-360">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-361">A expressão `Regex_latvia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-362">Uma palavra- `Keywords_latvia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-363">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-363">Keywords</span></span>

<span data-ttu-id="3bdbc-364">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-364"></span></span>
|<span data-ttu-id="3bdbc-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-366">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-366">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-367">número de passaporte da Letão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-367">latvian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-368">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-368">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="3bdbc-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="3bdbc-370">Lituânia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-371">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-371">Format</span></span>

<span data-ttu-id="3bdbc-372">Oito dígitos ou letras sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-373">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-373">Pattern</span></span>

<span data-ttu-id="3bdbc-374">Oito dígitos ou letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="3bdbc-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-375">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-375">Checksum</span></span>

<span data-ttu-id="3bdbc-376">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="3bdbc-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-377">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-377">Definition</span></span>

<span data-ttu-id="3bdbc-378">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-379">A expressão `Regex_lithuania_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-380">Uma palavra- `Keywords_lithuania_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-381">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-381">Keywords</span></span>

<span data-ttu-id="3bdbc-382">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-382"></span></span>
|<span data-ttu-id="3bdbc-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-384">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-384">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-385">número de passaporte lithunian</span><span class="sxs-lookup"><span data-stu-id="3bdbc-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-386">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-386">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="3bdbc-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="3bdbc-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="3bdbc-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-389">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-389">Format</span></span>

<span data-ttu-id="3bdbc-390">Oito dígitos ou letras sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-391">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-391">Pattern</span></span>

<span data-ttu-id="3bdbc-392">Oito dígitos ou letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="3bdbc-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-393">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-393">Checksum</span></span>

<span data-ttu-id="3bdbc-394">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-395">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-395">Definition</span></span>

<span data-ttu-id="3bdbc-396">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-397">A expressão `Regex_nation_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-398">Uma palavra- `Keywords_nation_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-399">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-399">Keywords</span></span>

<span data-ttu-id="3bdbc-400">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-400"></span></span>
|<span data-ttu-id="3bdbc-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-402">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-402">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-403">número de passaporte da Letão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-403">latvian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-404">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-404">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="3bdbc-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="3bdbc-406">Malta</span><span class="sxs-lookup"><span data-stu-id="3bdbc-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-407">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-407">Format</span></span>

<span data-ttu-id="3bdbc-408">Sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-409">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-409">Pattern</span></span>

 <span data-ttu-id="3bdbc-410">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-411">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-411">Checksum</span></span>

<span data-ttu-id="3bdbc-412">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-413">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-413">Definition</span></span>

<span data-ttu-id="3bdbc-414">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-415">A expressão `Regex_malta_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-416">Uma palavra- `Keywords_malta_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-417">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-417">Keywords</span></span>

<span data-ttu-id="3bdbc-418">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-418"></span></span>
|<span data-ttu-id="3bdbc-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-420">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-420">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-421">número de passaporte Maltês</span><span class="sxs-lookup"><span data-stu-id="3bdbc-421">maltese passport number</span></span>  <br/> <span data-ttu-id="3bdbc-422">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-422">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="3bdbc-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="3bdbc-424">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-425">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-425">Format</span></span>

<span data-ttu-id="3bdbc-426">Nove letras ou dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-427">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-427">Pattern</span></span>

<span data-ttu-id="3bdbc-428">Nove letras ou dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-429">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-429">Checksum</span></span>

<span data-ttu-id="3bdbc-430">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="3bdbc-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-431">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-431">Definition</span></span>

<span data-ttu-id="3bdbc-432">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-433">A expressão `Regex_netherlands_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-434">Uma palavra- `Keywords_netherlands_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-435">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-435">Keywords</span></span>

<span data-ttu-id="3bdbc-436">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-436"></span></span>
|<span data-ttu-id="3bdbc-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-438">número de passaporte holandês</span><span class="sxs-lookup"><span data-stu-id="3bdbc-438">dutch passport number</span></span>  <br/> <span data-ttu-id="3bdbc-439">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-439">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-440">número de passaporte Holanda</span><span class="sxs-lookup"><span data-stu-id="3bdbc-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="3bdbc-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="3bdbc-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="3bdbc-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="3bdbc-442">paspoort</span></span>  <br/> <span data-ttu-id="3bdbc-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3bdbc-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="3bdbc-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3bdbc-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="3bdbc-445">Polônia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-445">Poland</span></span>

<span data-ttu-id="3bdbc-446">Para obter detalhes, consulte a seção "número de passaporte da Polônia" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3bdbc-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="3bdbc-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="3bdbc-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-448">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-448">Format</span></span>

<span data-ttu-id="3bdbc-449">Uma letra seguida de seis dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-450">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-450">Pattern</span></span>

<span data-ttu-id="3bdbc-451">Uma letra seguida por seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="3bdbc-452">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="3bdbc-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="3bdbc-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3bdbc-454">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-454">Checksum</span></span>

<span data-ttu-id="3bdbc-455">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-456">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-456">Definition</span></span>

<span data-ttu-id="3bdbc-457">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-458">A expressão `Regex_portugal_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-459">Uma palavra- `Keywords_portugal_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-460">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-460">Keywords</span></span>

<span data-ttu-id="3bdbc-461">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-461"></span></span>
|<span data-ttu-id="3bdbc-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-463">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-463">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-464">número de passaporte Português</span><span class="sxs-lookup"><span data-stu-id="3bdbc-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="3bdbc-465">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-465">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="3bdbc-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="3bdbc-467">Romênia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-468">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-468">Format</span></span>

<span data-ttu-id="3bdbc-469">Oito ou nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-470">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-470">Pattern</span></span>

<span data-ttu-id="3bdbc-471">Oito ou nove dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-472">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-472">Checksum</span></span>

<span data-ttu-id="3bdbc-473">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-474">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-474">Definition</span></span>

<span data-ttu-id="3bdbc-475">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-476">A expressão `Regex_romania_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-477">Uma palavra- `Keywords_romania_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-478">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-478">Keywords</span></span>

<span data-ttu-id="3bdbc-479">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-479"></span></span>
|<span data-ttu-id="3bdbc-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-481">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-481">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-482">número de passaporte romeno</span><span class="sxs-lookup"><span data-stu-id="3bdbc-482">romanian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-483">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-483">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="3bdbc-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="3bdbc-485">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-486">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-486">Format</span></span>

<span data-ttu-id="3bdbc-487">Um dígito ou letra seguido por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-488">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-488">Pattern</span></span>

<span data-ttu-id="3bdbc-489">Um dígito ou letra (não diferencia maiúsculas de minúsculas) seguido por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3bdbc-490">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-490">Checksum</span></span>

<span data-ttu-id="3bdbc-491">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-492">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-492">Definition</span></span>

<span data-ttu-id="3bdbc-493">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-494">A expressão `Regex_slovakia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-495">Uma palavra- `Keywords_slovakia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-496">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-496">Keywords</span></span>

<span data-ttu-id="3bdbc-497">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-497"></span></span>
|<span data-ttu-id="3bdbc-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-499">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-499">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-500">número de passaporte eslovaco</span><span class="sxs-lookup"><span data-stu-id="3bdbc-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-501">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-501">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="3bdbc-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="3bdbc-503">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-504">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-504">Format</span></span>

<span data-ttu-id="3bdbc-505">Duas letras seguidas por sete dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-506">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-506">Pattern</span></span>

<span data-ttu-id="3bdbc-507">Duas letras seguidas por sete dígitos:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="3bdbc-508">A letra "P"</span><span class="sxs-lookup"><span data-stu-id="3bdbc-508">The letter "P"</span></span>
    
- <span data-ttu-id="3bdbc-509">Uma letra maiúscula</span><span class="sxs-lookup"><span data-stu-id="3bdbc-509">One uppercase letter</span></span>
    
- <span data-ttu-id="3bdbc-510">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3bdbc-511">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-511">Checksum</span></span>

<span data-ttu-id="3bdbc-512">Não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-513">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-513">Definition</span></span>

<span data-ttu-id="3bdbc-514">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-515">A expressão `Regex_slovenia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-516">Uma palavra- `Keywords_slovenia_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-517">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-517">Keywords</span></span>

<span data-ttu-id="3bdbc-518">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-518"></span></span>
|<span data-ttu-id="3bdbc-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-520">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-520">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-521">número de passaporte esloveno</span><span class="sxs-lookup"><span data-stu-id="3bdbc-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="3bdbc-522">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-522">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-523">lista de številka potnega</span><span class="sxs-lookup"><span data-stu-id="3bdbc-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="3bdbc-524">Espanha</span><span class="sxs-lookup"><span data-stu-id="3bdbc-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="3bdbc-525">Formatar</span><span class="sxs-lookup"><span data-stu-id="3bdbc-525">Format</span></span>

<span data-ttu-id="3bdbc-526">Uma combinação de letras e números de oito ou nove caracteres sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="3bdbc-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3bdbc-527">Padrão</span><span class="sxs-lookup"><span data-stu-id="3bdbc-527">Pattern</span></span>

<span data-ttu-id="3bdbc-528">Uma combinação de letras e números de oito ou nove caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="3bdbc-529">Dois dígitos ou letras</span><span class="sxs-lookup"><span data-stu-id="3bdbc-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="3bdbc-530">Um dígito ou letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="3bdbc-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="3bdbc-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="3bdbc-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3bdbc-532">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3bdbc-532">Checksum</span></span>

<span data-ttu-id="3bdbc-533">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="3bdbc-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3bdbc-534">Definição</span><span class="sxs-lookup"><span data-stu-id="3bdbc-534">Definition</span></span>

<span data-ttu-id="3bdbc-535">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3bdbc-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3bdbc-536">A expressão `Regex_spain_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3bdbc-537">Uma palavra- `Keywords_spain_eu_passport_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="3bdbc-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3bdbc-538">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3bdbc-538">Keywords</span></span>

<span data-ttu-id="3bdbc-539">| |</span><span class="sxs-lookup"><span data-stu-id="3bdbc-539"></span></span>
|<span data-ttu-id="3bdbc-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3bdbc-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3bdbc-541">Passaport</span><span class="sxs-lookup"><span data-stu-id="3bdbc-541">passport</span></span>  <br/> <span data-ttu-id="3bdbc-542">o Passport da Espanha</span><span class="sxs-lookup"><span data-stu-id="3bdbc-542">spain passport</span></span>  <br/> <span data-ttu-id="3bdbc-543">Catálogo do Passport</span><span class="sxs-lookup"><span data-stu-id="3bdbc-543">passport book</span></span>  <br/> <span data-ttu-id="3bdbc-544">passport number</span><span class="sxs-lookup"><span data-stu-id="3bdbc-544">passport number</span></span>  <br/> <span data-ttu-id="3bdbc-545">Passport não</span><span class="sxs-lookup"><span data-stu-id="3bdbc-545">passport no</span></span>  <br/> <span data-ttu-id="3bdbc-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="3bdbc-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="3bdbc-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="3bdbc-547">número pasaporte</span></span>  <br/> <span data-ttu-id="3bdbc-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="3bdbc-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="3bdbc-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="3bdbc-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="3bdbc-550">Suécia</span><span class="sxs-lookup"><span data-stu-id="3bdbc-550">Sweden</span></span>

<span data-ttu-id="3bdbc-551">Para obter detalhes, consulte a seção "número de passaporte da Suécia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3bdbc-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="3bdbc-552">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="3bdbc-552">UK</span></span>

<span data-ttu-id="3bdbc-553">Para obter detalhes, consulte a seção "U.S./Reino Unido</span><span class="sxs-lookup"><span data-stu-id="3bdbc-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="3bdbc-554">Número do Passport "no [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3bdbc-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3bdbc-555">Confira também</span><span class="sxs-lookup"><span data-stu-id="3bdbc-555">See also</span></span>

[<span data-ttu-id="3bdbc-556">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="3bdbc-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

