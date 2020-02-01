---
title: Número da carteira de motorista da UE
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de licença do driver da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592652"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="a09a4-104">Número da carteira de motorista da UE</span><span class="sxs-lookup"><span data-stu-id="a09a4-104">EU Driver's License Number</span></span>

<span data-ttu-id="a09a4-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de licença do driver da UE.</span><span class="sxs-lookup"><span data-stu-id="a09a4-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="a09a4-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="a09a4-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="a09a4-107">Áustria</span><span class="sxs-lookup"><span data-stu-id="a09a4-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-108">Format</span></span>

<span data-ttu-id="a09a4-109">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-110">Pattern</span></span>

<span data-ttu-id="a09a4-111">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a09a4-112">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-112">Checksum</span></span>

<span data-ttu-id="a09a4-113">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-114">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-114">Definition</span></span>

<span data-ttu-id="a09a4-115">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-116">A expressão `Regex_austria_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-117">Uma palavra- `Keywords_austria_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="a09a4-118">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-118">Keywords</span></span>

<span data-ttu-id="a09a4-119">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-119">| |</span></span>
|<span data-ttu-id="a09a4-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-121">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-121">dl#</span></span>  <br/> <span data-ttu-id="a09a4-122">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-122">driver license</span></span>  <br/> <span data-ttu-id="a09a4-123">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-123">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-124">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-124">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-125">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-125">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-126">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-127">driver's licence</span></span>  <br/> <span data-ttu-id="a09a4-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-128">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-129">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-129">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-130">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="a09a4-131">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-131">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-132">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a09a4-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="a09a4-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="a09a4-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="a09a4-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="a09a4-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-136">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-136">Format</span></span>

<span data-ttu-id="a09a4-137">10 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-138">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-138">Pattern</span></span>

<span data-ttu-id="a09a4-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a09a4-140">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-140">Checksum</span></span>

<span data-ttu-id="a09a4-141">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-142">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-142">Definition</span></span>

<span data-ttu-id="a09a4-143">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-144">A expressão `Regex_belgium_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-145">Uma palavra- `Keywords_belgium_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="a09a4-146">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-146">Keywords</span></span>

<span data-ttu-id="a09a4-147">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-147">| |</span></span>
|<span data-ttu-id="a09a4-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-149">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-149">dl#</span></span>  <br/> <span data-ttu-id="a09a4-150">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-150">driver license</span></span>  <br/> <span data-ttu-id="a09a4-151">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-151">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-152">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-152">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-153">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-153">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-154">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-155">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-156">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-157">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-157">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-158">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-158">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-159">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="a09a4-160">rijbewijs</span></span>  <br/> <span data-ttu-id="a09a4-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a09a4-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="a09a4-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a09a4-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="a09a4-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a09a4-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="a09a4-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a09a4-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="a09a4-165">führerschein- nr</span><span class="sxs-lookup"><span data-stu-id="a09a4-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="a09a4-166">fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a09a4-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="a09a4-167">fuehrerschein- nr</span><span class="sxs-lookup"><span data-stu-id="a09a4-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="a09a4-168">Bulgária</span><span class="sxs-lookup"><span data-stu-id="a09a4-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-169">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-169">Format</span></span>

<span data-ttu-id="a09a4-170">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-171">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-171">Pattern</span></span>

<span data-ttu-id="a09a4-172">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a09a4-173">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-173">Checksum</span></span>

<span data-ttu-id="a09a4-174">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-175">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-175">Definition</span></span>

<span data-ttu-id="a09a4-176">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-177">A expressão `Regex_bulgaria_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-178">Uma palavra- `Keywords_bulgaria_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="a09a4-179">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-179">Keywords</span></span>

<span data-ttu-id="a09a4-180">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-180">| |</span></span>
|<span data-ttu-id="a09a4-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-182">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-182">dl#</span></span>  <br/> <span data-ttu-id="a09a4-183">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-183">driver license</span></span>  <br/> <span data-ttu-id="a09a4-184">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-184">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-185">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-185">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-186">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-186">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-187">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-188">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-189">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-190">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-190">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-191">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-191">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-192">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-192">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-193">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="a09a4-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="a09a4-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="a09a4-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="a09a4-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="a09a4-196">сумпс</span></span>  <br/> <span data-ttu-id="a09a4-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="a09a4-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="a09a4-198">Croácia</span><span class="sxs-lookup"><span data-stu-id="a09a4-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-199">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-199">Format</span></span>

<span data-ttu-id="a09a4-200">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-201">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-201">Pattern</span></span>

<span data-ttu-id="a09a4-202">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a09a4-203">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-203">Checksum</span></span>

<span data-ttu-id="a09a4-204">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-205">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-205">Definition</span></span>

<span data-ttu-id="a09a4-206">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-207">A expressão `Regex_croatia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-208">Uma palavra- `Keywords_croatia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="a09a4-209">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-209">Keywords</span></span>

<span data-ttu-id="a09a4-210">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-210">| |</span></span>
|<span data-ttu-id="a09a4-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-212">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-212">dl#</span></span>  <br/> <span data-ttu-id="a09a4-213">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-213">driver license</span></span>  <br/> <span data-ttu-id="a09a4-214">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-214">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-215">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-215">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-216">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-216">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-217">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-218">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-219">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-220">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-220">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-221">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-221">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-222">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-222">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-223">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="a09a4-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="a09a4-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="a09a4-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-226">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-226">Format</span></span>

<span data-ttu-id="a09a4-227">12 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-228">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-228">Pattern</span></span>

<span data-ttu-id="a09a4-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a09a4-230">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-230">Checksum</span></span>

<span data-ttu-id="a09a4-231">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-232">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-232">Definition</span></span>

<span data-ttu-id="a09a4-233">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-234">A expressão `Regex_cyprus_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-235">Uma palavra- `Keywords_cyprus_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-236">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-236">Keywords</span></span>

<span data-ttu-id="a09a4-237">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-237">| |</span></span>
|<span data-ttu-id="a09a4-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-239">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-239">dl#</span></span>  <br/> <span data-ttu-id="a09a4-240">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-240">driver license</span></span>  <br/> <span data-ttu-id="a09a4-241">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-241">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-242">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-242">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-243">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-243">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-244">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-245">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-246">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-246">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-247">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-247">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-248">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-248">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-249">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="a09a4-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="a09a4-251">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="a09a4-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-252">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-252">Format</span></span>

<span data-ttu-id="a09a4-253">Duas letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-254">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-254">Pattern</span></span>

<span data-ttu-id="a09a4-255">Oito letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="a09a4-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="a09a4-256">Duas letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a09a4-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="a09a4-257">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="a09a4-257">A space (optional)</span></span>
    
- <span data-ttu-id="a09a4-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-259">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-259">Checksum</span></span>

<span data-ttu-id="a09a4-260">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-261">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-261">Definition</span></span>

<span data-ttu-id="a09a4-262">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-263">A expressão `Regex_czech_republic_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-264">Uma palavra- `Keywords_czech_republic_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="a09a4-265">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-265">Keywords</span></span>

<span data-ttu-id="a09a4-266">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-266">| |</span></span>
|<span data-ttu-id="a09a4-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-268">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-268">dl#</span></span>  <br/> <span data-ttu-id="a09a4-269">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-269">driver license</span></span>  <br/> <span data-ttu-id="a09a4-270">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-270">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-271">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-271">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-272">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-272">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-273">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-274">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-275">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-276">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-276">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-277">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-277">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-278">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-278">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-279">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-279">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-280">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="a09a4-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="a09a4-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="a09a4-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-283">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-283">Format</span></span>

<span data-ttu-id="a09a4-284">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-285">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-285">Pattern</span></span>

<span data-ttu-id="a09a4-286">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a09a4-287">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-287">Checksum</span></span>

<span data-ttu-id="a09a4-288">Sim</span><span class="sxs-lookup"><span data-stu-id="a09a4-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-289">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-289">Definition</span></span>

<span data-ttu-id="a09a4-290">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-291">A expressão `Regex_denmark_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-292">Uma palavra- `Keywords_denmark_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="a09a4-293">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-293">Keywords</span></span>

<span data-ttu-id="a09a4-294">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-294">| |</span></span>
|<span data-ttu-id="a09a4-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-296">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-296">dl#</span></span>  <br/> <span data-ttu-id="a09a4-297">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-297">driver license</span></span>  <br/> <span data-ttu-id="a09a4-298">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-298">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-299">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-299">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-300">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-300">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-301">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-302">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-303">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-304">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-304">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-305">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-305">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-306">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-306">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-307">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="a09a4-308">kørekort</span></span>  <br/> <span data-ttu-id="a09a4-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="a09a4-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="a09a4-310">Estônia</span><span class="sxs-lookup"><span data-stu-id="a09a4-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-311">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-311">Format</span></span>

<span data-ttu-id="a09a4-312">Duas letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-313">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-313">Pattern</span></span>

<span data-ttu-id="a09a4-314">Duas letras e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="a09a4-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="a09a4-315">As letras "ET" (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a09a4-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="a09a4-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-317">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-317">Checksum</span></span>

<span data-ttu-id="a09a4-318">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-319">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-319">Definition</span></span>

<span data-ttu-id="a09a4-320">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-321">A expressão `Regex_estonia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-322">Uma palavra- `Keywords_estonia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-323">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-323">Keywords</span></span>

<span data-ttu-id="a09a4-324">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-324">| |</span></span>
|<span data-ttu-id="a09a4-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-326">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-326">dl#</span></span>  <br/> <span data-ttu-id="a09a4-327">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-327">driver license</span></span>  <br/> <span data-ttu-id="a09a4-328">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-328">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-329">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-329">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-330">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-330">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-331">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-331">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-332">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-333">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-334">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-335">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-335">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-336">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-336">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-337">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="a09a4-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="a09a4-339">Finlândia</span><span class="sxs-lookup"><span data-stu-id="a09a4-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-340">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-340">Format</span></span>

<span data-ttu-id="a09a4-341">10 dígitos que contêm um hífen</span><span class="sxs-lookup"><span data-stu-id="a09a4-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-342">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-342">Pattern</span></span>

<span data-ttu-id="a09a4-343">10 dígitos contendo um hífen:</span><span class="sxs-lookup"><span data-stu-id="a09a4-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="a09a4-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-344">Six digits</span></span> 
    
- <span data-ttu-id="a09a4-345">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a09a4-345">A hyphen</span></span>
    
-  <span data-ttu-id="a09a4-346">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="a09a4-347">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-347">Checksum</span></span>

<span data-ttu-id="a09a4-348">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-349">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-349">Definition</span></span>

<span data-ttu-id="a09a4-350">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-351">A expressão `Regex_finland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-352">Uma palavra- `Keywords_finland_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-353">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-353">Keywords</span></span>

<span data-ttu-id="a09a4-354">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-354">| |</span></span>
|<span data-ttu-id="a09a4-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-356">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-356">dl#</span></span>  <br/> <span data-ttu-id="a09a4-357">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-357">driver license</span></span>  <br/> <span data-ttu-id="a09a4-358">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-358">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-359">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-359">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-360">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-360">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-361">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-362">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-363">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-364">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-364">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-365">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-365">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-366">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-366">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-367">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="a09a4-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="a09a4-369">França</span><span class="sxs-lookup"><span data-stu-id="a09a4-369">France</span></span>

<span data-ttu-id="a09a4-370">Para obter detalhes, consulte a seção "número da carteira de motorista do driver da França" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a09a4-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="a09a4-371">Alemanha</span><span class="sxs-lookup"><span data-stu-id="a09a4-371">Germany</span></span>

<span data-ttu-id="a09a4-372">Para obter detalhes, consulte a seção "número da carteira de motorista do driver alemão" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a09a4-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="a09a4-373">Grécia</span><span class="sxs-lookup"><span data-stu-id="a09a4-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-374">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-374">Format</span></span>

<span data-ttu-id="a09a4-375">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-376">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-376">Pattern</span></span>

 <span data-ttu-id="a09a4-377">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a09a4-378">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-378">Checksum</span></span>

<span data-ttu-id="a09a4-379">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-380">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-380">Definition</span></span>

<span data-ttu-id="a09a4-381">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-382">A expressão `Regex_greece_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-383">Uma palavra- `Keywords_greece_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-384">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-384">Keywords</span></span>

<span data-ttu-id="a09a4-385">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-385">| |</span></span>
|<span data-ttu-id="a09a4-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="a09a4-387">dlL#</span></span>  <br/> <span data-ttu-id="a09a4-388">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-388">driver license</span></span>  <br/> <span data-ttu-id="a09a4-389">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-389">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-390">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-390">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-391">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-391">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-392">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-393">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-394">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-395">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-395">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-396">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-396">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-397">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-397">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-398">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="a09a4-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="a09a4-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="a09a4-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="a09a4-401">Hungria</span><span class="sxs-lookup"><span data-stu-id="a09a4-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-402">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-402">Format</span></span>

<span data-ttu-id="a09a4-403">Duas letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-404">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-404">Pattern</span></span>

<span data-ttu-id="a09a4-405">Duas letras e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="a09a4-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="a09a4-406">Duas letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a09a4-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="a09a4-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-408">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-408">Checksum</span></span>

<span data-ttu-id="a09a4-409">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-410">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-410">Definition</span></span>

<span data-ttu-id="a09a4-411">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-412">A expressão `Regex_hungary_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-413">Uma palavra- `Keywords_hungary_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-414">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-414">Keywords</span></span>

<span data-ttu-id="a09a4-415">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-415">| |</span></span>
|<span data-ttu-id="a09a4-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-417">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-417">dl#</span></span>  <br/> <span data-ttu-id="a09a4-418">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-418">driver license</span></span>  <br/> <span data-ttu-id="a09a4-419">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-419">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-420">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-420">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-421">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-421">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-422">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-423">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-424">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-425">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-425">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-426">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-426">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-427">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-427">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-428">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="a09a4-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="a09a4-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="a09a4-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-431">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-431">Format</span></span>

<span data-ttu-id="a09a4-432">Seis dígitos seguidos de quatro letras</span><span class="sxs-lookup"><span data-stu-id="a09a4-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-433">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-433">Pattern</span></span>

<span data-ttu-id="a09a4-434">Seis dígitos e quatro letras:</span><span class="sxs-lookup"><span data-stu-id="a09a4-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="a09a4-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-435">Six digits</span></span>
    
- <span data-ttu-id="a09a4-436">Quatro letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a09a4-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-437">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-437">Checksum</span></span>

<span data-ttu-id="a09a4-438">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-439">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-439">Definition</span></span>

<span data-ttu-id="a09a4-440">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-441">A expressão `Regex_ireland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-442">Uma palavra- `Keywords_ireland_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-443">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-443">Keywords</span></span>

<span data-ttu-id="a09a4-444">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-444">| |</span></span>
|<span data-ttu-id="a09a4-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-446">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-446">dl#</span></span>  <br/> <span data-ttu-id="a09a4-447">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-447">driver license</span></span>  <br/> <span data-ttu-id="a09a4-448">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-448">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-449">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-449">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-450">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-450">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-451">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-452">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-453">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-454">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-454">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-455">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-455">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-456">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-456">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-457">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="a09a4-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="a09a4-459">Itália</span><span class="sxs-lookup"><span data-stu-id="a09a4-459">Italy</span></span>

<span data-ttu-id="a09a4-460">Para obter detalhes, consulte a seção "número da carteira de motorista do driver da Itália" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a09a4-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="a09a4-461">Letônia</span><span class="sxs-lookup"><span data-stu-id="a09a4-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-462">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-462">Format</span></span>

<span data-ttu-id="a09a4-463">Três letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-464">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-464">Pattern</span></span>

<span data-ttu-id="a09a4-465">Três letras e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="a09a4-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="a09a4-466">Três letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a09a4-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="a09a4-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-468">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-468">Checksum</span></span>

<span data-ttu-id="a09a4-469">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-470">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-470">Definition</span></span>

<span data-ttu-id="a09a4-471">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-472">A expressão `Regex_latvia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-473">Uma palavra- `Keywords_latvia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-474">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-474">Keywords</span></span>

<span data-ttu-id="a09a4-475">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-475">| |</span></span>
|<span data-ttu-id="a09a4-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-477">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-477">dl#</span></span>  <br/> <span data-ttu-id="a09a4-478">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-478">driver license</span></span>  <br/> <span data-ttu-id="a09a4-479">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-479">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-480">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-480">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-481">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-481">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-482">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-483">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-484">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-485">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-485">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-486">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-486">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-487">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-487">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-488">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="a09a4-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="a09a4-490">Lituânia</span><span class="sxs-lookup"><span data-stu-id="a09a4-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-491">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-491">Format</span></span>

<span data-ttu-id="a09a4-492">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-493">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-493">Pattern</span></span>

 <span data-ttu-id="a09a4-494">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a09a4-495">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-495">Checksum</span></span>

<span data-ttu-id="a09a4-496">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-497">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-497">Definition</span></span>

<span data-ttu-id="a09a4-498">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-499">A expressão `Regex_lithuania_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-500">Uma palavra- `Keywords_lithuania_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-501">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-501">Keywords</span></span>

<span data-ttu-id="a09a4-502">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-502">| |</span></span>
|<span data-ttu-id="a09a4-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-504">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-504">dl#</span></span>  <br/> <span data-ttu-id="a09a4-505">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-505">driver license</span></span>  <br/> <span data-ttu-id="a09a4-506">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-506">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-507">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-507">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-508">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-508">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-509">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-510">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-511">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-512">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-512">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-513">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-513">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-514">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-514">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-515">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="a09a4-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="a09a4-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="a09a4-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-518">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-518">Format</span></span>

<span data-ttu-id="a09a4-519">Seis dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-520">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-520">Pattern</span></span>

 <span data-ttu-id="a09a4-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a09a4-522">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-522">Checksum</span></span>

<span data-ttu-id="a09a4-523">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-524">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-524">Definition</span></span>

<span data-ttu-id="a09a4-525">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-526">A expressão `Regex_luxemburg_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-527">Uma palavra- `Keywords_luxemburg_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-528">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-528">Keywords</span></span>

<span data-ttu-id="a09a4-529">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-529">| |</span></span>
|<span data-ttu-id="a09a4-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-531">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-531">dl#</span></span>  <br/> <span data-ttu-id="a09a4-532">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-532">driver license</span></span>  <br/> <span data-ttu-id="a09a4-533">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-533">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-534">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-534">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-535">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-535">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-536">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-537">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-538">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-539">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-539">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-540">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-540">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-541">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-541">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-542">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="a09a4-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="a09a4-544">Malta</span><span class="sxs-lookup"><span data-stu-id="a09a4-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-545">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-545">Format</span></span>

<span data-ttu-id="a09a4-546">Combinação de dois caracteres e seis dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="a09a4-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-547">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-547">Pattern</span></span>

<span data-ttu-id="a09a4-548">Combinação de dois caracteres e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="a09a4-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="a09a4-549">Dois caracteres (dígitos ou letras, não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a09a4-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="a09a4-550">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="a09a4-550">A space (optional)</span></span>
    
- <span data-ttu-id="a09a4-551">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-551">Three digits</span></span>
    
- <span data-ttu-id="a09a4-552">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="a09a4-552">A space (optional)</span></span>
    
- <span data-ttu-id="a09a4-553">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-554">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-554">Checksum</span></span>

<span data-ttu-id="a09a4-555">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-556">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-556">Definition</span></span>

<span data-ttu-id="a09a4-557">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-558">A expressão `Regex_malta_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-559">Uma palavra- `Keywords_malta_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-560">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-560">Keywords</span></span>

<span data-ttu-id="a09a4-561">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-561">| |</span></span>
|<span data-ttu-id="a09a4-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-563">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-563">dl#</span></span>  <br/> <span data-ttu-id="a09a4-564">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-564">driver license</span></span>  <br/> <span data-ttu-id="a09a4-565">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-565">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-566">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-566">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-567">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-567">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-568">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-569">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-570">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-571">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-571">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-572">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-572">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-573">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-573">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-574">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="a09a4-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="a09a4-576">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="a09a4-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-577">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-577">Format</span></span>

<span data-ttu-id="a09a4-578">10 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-579">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-579">Pattern</span></span>

<span data-ttu-id="a09a4-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a09a4-581">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-581">Checksum</span></span>

<span data-ttu-id="a09a4-582">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-583">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-583">Definition</span></span>

<span data-ttu-id="a09a4-584">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-585">A expressão `Regex_netherlands_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-586">Uma palavra- `Keywords_netherlands_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-587">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-587">Keywords</span></span>

<span data-ttu-id="a09a4-588">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-588">| |</span></span>
|<span data-ttu-id="a09a4-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-590">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-590">dl#</span></span>  <br/> <span data-ttu-id="a09a4-591">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-591">driver license</span></span>  <br/> <span data-ttu-id="a09a4-592">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-592">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-593">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-593">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-594">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-594">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-595">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-596">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-597">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-598">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-598">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-599">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-599">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-600">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-600">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-601">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="a09a4-602">permis de conduire</span></span>  <br/> <span data-ttu-id="a09a4-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="a09a4-603">rijbewijs</span></span>  <br/> <span data-ttu-id="a09a4-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="a09a4-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="a09a4-605">Polônia</span><span class="sxs-lookup"><span data-stu-id="a09a4-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-606">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-606">Format</span></span>

<span data-ttu-id="a09a4-607">14 dígitos contendo 2 barras</span><span class="sxs-lookup"><span data-stu-id="a09a4-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-608">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-608">Pattern</span></span>

<span data-ttu-id="a09a4-609">14 dígitos e 2 barras de avanço:</span><span class="sxs-lookup"><span data-stu-id="a09a4-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="a09a4-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-610">Five digits</span></span> 
    
- <span data-ttu-id="a09a4-611">Uma barra</span><span class="sxs-lookup"><span data-stu-id="a09a4-611">A forward slash</span></span>
    
- <span data-ttu-id="a09a4-612">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-612">Two digits</span></span>
    
- <span data-ttu-id="a09a4-613">Uma barra</span><span class="sxs-lookup"><span data-stu-id="a09a4-613">A forward slash</span></span>
    
- <span data-ttu-id="a09a4-614">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-615">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-615">Checksum</span></span>

<span data-ttu-id="a09a4-616">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-617">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-617">Definition</span></span>

<span data-ttu-id="a09a4-618">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-619">A expressão `Regex_poland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-620">Uma palavra- `Keywords_poland_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-621">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-621">Keywords</span></span>

<span data-ttu-id="a09a4-622">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-622">| |</span></span>
|<span data-ttu-id="a09a4-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-624">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-624">dl#</span></span>  <br/> <span data-ttu-id="a09a4-625">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-625">driver license</span></span>  <br/> <span data-ttu-id="a09a4-626">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-626">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-627">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-627">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-628">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-628">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-629">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-630">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-631">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-632">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-632">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-633">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-633">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-634">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-634">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-635">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="a09a4-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="a09a4-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="a09a4-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-638">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-638">Format</span></span>

<span data-ttu-id="a09a4-639">Duas letras seguidas por sete números no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="a09a4-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-640">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-640">Pattern</span></span>

<span data-ttu-id="a09a4-641">Duas letras seguidas por sete números com caracteres especiais:</span><span class="sxs-lookup"><span data-stu-id="a09a4-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="a09a4-642">Duas letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a09a4-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="a09a4-643">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a09a4-643">A hyphen</span></span>
    
- <span data-ttu-id="a09a4-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-644">Six digits</span></span>
    
- <span data-ttu-id="a09a4-645">Um espaço</span><span class="sxs-lookup"><span data-stu-id="a09a4-645">A space</span></span>
    
- <span data-ttu-id="a09a4-646">Um dígito</span><span class="sxs-lookup"><span data-stu-id="a09a4-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-647">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-647">Checksum</span></span>

<span data-ttu-id="a09a4-648">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-649">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-649">Definition</span></span>

<span data-ttu-id="a09a4-650">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-651">A expressão `Regex_portugal_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-652">Uma palavra- `Keywords_portugal_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-653">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-653">Keywords</span></span>

<span data-ttu-id="a09a4-654">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-654">| |</span></span>
|<span data-ttu-id="a09a4-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-656">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-656">dl#</span></span>  <br/> <span data-ttu-id="a09a4-657">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-657">driver license</span></span>  <br/> <span data-ttu-id="a09a4-658">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-658">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-659">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-659">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-660">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-660">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-661">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-662">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-663">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-664">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-664">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-665">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-665">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-666">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-666">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-667">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="a09a4-669">Romênia</span><span class="sxs-lookup"><span data-stu-id="a09a4-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-670">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-670">Format</span></span>

<span data-ttu-id="a09a4-671">Um caractere seguido por oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-672">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-672">Pattern</span></span>

<span data-ttu-id="a09a4-673">Um caractere seguido por oito dígitos:</span><span class="sxs-lookup"><span data-stu-id="a09a4-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="a09a4-674">Uma letra (não diferencia maiúsculas de minúsculas) ou dígito</span><span class="sxs-lookup"><span data-stu-id="a09a4-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="a09a4-675">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-676">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-676">Checksum</span></span>

<span data-ttu-id="a09a4-677">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-678">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-678">Definition</span></span>

<span data-ttu-id="a09a4-679">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-680">A expressão `Regex_romania_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-681">Uma palavra- `Keywords_romania_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-682">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-682">Keywords</span></span>

<span data-ttu-id="a09a4-683">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-683">| |</span></span>
|<span data-ttu-id="a09a4-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-685">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-685">dl#</span></span>  <br/> <span data-ttu-id="a09a4-686">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-686">driver license</span></span>  <br/> <span data-ttu-id="a09a4-687">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-687">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-688">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-688">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-689">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-689">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-690">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-691">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-692">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-693">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-693">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-694">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-694">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-695">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-695">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-696">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-697">permé de conducere</span><span class="sxs-lookup"><span data-stu-id="a09a4-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="a09a4-698">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="a09a4-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-699">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-699">Format</span></span>

<span data-ttu-id="a09a4-700">Um caractere seguido por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-701">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-701">Pattern</span></span>

<span data-ttu-id="a09a4-702">Um caractere seguido por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="a09a4-703">Uma letra (não diferencia maiúsculas de minúsculas) ou dígito</span><span class="sxs-lookup"><span data-stu-id="a09a4-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="a09a4-704">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="a09a4-705">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-705">Checksum</span></span>

<span data-ttu-id="a09a4-706">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-707">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-707">Definition</span></span>

<span data-ttu-id="a09a4-708">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-709">A expressão `Regex_slovakia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-710">Uma palavra- `Keywords_slovakia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-711">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-711">Keywords</span></span>

<span data-ttu-id="a09a4-712">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-712">| |</span></span>
|<span data-ttu-id="a09a4-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-714">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-714">dl#</span></span>  <br/> <span data-ttu-id="a09a4-715">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-715">driver license</span></span>  <br/> <span data-ttu-id="a09a4-716">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-716">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-717">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-717">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-718">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-718">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-719">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-720">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-721">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-722">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-722">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-723">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-723">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-724">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-724">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-725">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="a09a4-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="a09a4-727">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="a09a4-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-728">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-728">Format</span></span>

<span data-ttu-id="a09a4-729">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="a09a4-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-730">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-730">Pattern</span></span>

<span data-ttu-id="a09a4-731">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a09a4-732">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-732">Checksum</span></span>

<span data-ttu-id="a09a4-733">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-734">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-734">Definition</span></span>

<span data-ttu-id="a09a4-735">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-736">A expressão `Regex_slovenia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-737">Uma palavra- `Keywords_slovenia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-738">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-738">Keywords</span></span>

<span data-ttu-id="a09a4-739">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-739">| |</span></span>
|<span data-ttu-id="a09a4-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-741">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-741">dl#</span></span>  <br/> <span data-ttu-id="a09a4-742">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-742">driver license</span></span>  <br/> <span data-ttu-id="a09a4-743">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-743">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-744">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-744">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-745">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-745">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-746">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-747">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-748">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-749">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-749">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-750">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-750">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-751">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-751">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-752">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="a09a4-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="a09a4-754">Espanha</span><span class="sxs-lookup"><span data-stu-id="a09a4-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-755">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-755">Format</span></span>

<span data-ttu-id="a09a4-756">Oito dígitos seguidos de um caractere</span><span class="sxs-lookup"><span data-stu-id="a09a4-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-757">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-757">Pattern</span></span>

<span data-ttu-id="a09a4-758">Oito dígitos seguidos de um caractere:</span><span class="sxs-lookup"><span data-stu-id="a09a4-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="a09a4-759">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-759">Eight digits</span></span> 
    
- <span data-ttu-id="a09a4-760">Um dígito ou letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a09a4-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-761">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-761">Checksum</span></span>

<span data-ttu-id="a09a4-762">Sim</span><span class="sxs-lookup"><span data-stu-id="a09a4-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-763">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-763">Definition</span></span>

<span data-ttu-id="a09a4-764">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-765">A função `Func_spain_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-766">Uma palavra- `Keywords_spain_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a09a4-767">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-767">Keywords</span></span>

<span data-ttu-id="a09a4-768">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-768">| |</span></span>
|<span data-ttu-id="a09a4-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-770">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-771">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-771">dl#</span></span>  <br/> <span data-ttu-id="a09a4-772">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-772">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-773">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-773">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-774">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-774">driver license</span></span>  <br/> <span data-ttu-id="a09a4-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-775">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-776">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-777">driver's licence</span></span>  <br/> <span data-ttu-id="a09a4-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-778">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-779">driving licence</span></span>  <br/> <span data-ttu-id="a09a4-780">driving licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-780">driving license</span></span>  <br/> <span data-ttu-id="a09a4-781">número de licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-781">driver licence number</span></span>  <br/> <span data-ttu-id="a09a4-782">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-782">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-783">número de licença de drivers</span><span class="sxs-lookup"><span data-stu-id="a09a4-783">drivers licence number</span></span>  <br/> <span data-ttu-id="a09a4-784">número de licença de drivers</span><span class="sxs-lookup"><span data-stu-id="a09a4-784">drivers license number</span></span>  <br/> <span data-ttu-id="a09a4-785">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-785">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-786">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-786">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-787">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-787">driving licence number</span></span>  <br/> <span data-ttu-id="a09a4-788">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-788">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-789">permissão de condução</span><span class="sxs-lookup"><span data-stu-id="a09a4-789">driving permit</span></span>  <br/> <span data-ttu-id="a09a4-790">número de permissão de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-790">driving permit number</span></span>  <br/> <span data-ttu-id="a09a4-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="a09a4-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="a09a4-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="a09a4-792">permiso conducción</span></span>  <br/> <span data-ttu-id="a09a4-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="a09a4-794">número de Carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="a09a4-795">número Carnet conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="a09a4-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-796">licencia conducir</span></span>  <br/> <span data-ttu-id="a09a4-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="a09a4-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="a09a4-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="a09a4-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-800">permiso conducir</span></span>  <br/> <span data-ttu-id="a09a4-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="a09a4-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="a09a4-802">El Carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="a09a4-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="a09a4-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="a09a4-804">Suécia</span><span class="sxs-lookup"><span data-stu-id="a09a4-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="a09a4-805">Formatar</span><span class="sxs-lookup"><span data-stu-id="a09a4-805">Format</span></span>

<span data-ttu-id="a09a4-806">Dez dígitos contendo um hífen</span><span class="sxs-lookup"><span data-stu-id="a09a4-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a09a4-807">Padrão</span><span class="sxs-lookup"><span data-stu-id="a09a4-807">Pattern</span></span>

<span data-ttu-id="a09a4-808">Dez dígitos contendo um hífen:</span><span class="sxs-lookup"><span data-stu-id="a09a4-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="a09a4-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-809">Six digits</span></span> 
    
- <span data-ttu-id="a09a4-810">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a09a4-810">A hyphen</span></span>
    
- <span data-ttu-id="a09a4-811">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a09a4-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a09a4-812">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a09a4-812">Checksum</span></span>

<span data-ttu-id="a09a4-813">Não</span><span class="sxs-lookup"><span data-stu-id="a09a4-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a09a4-814">Definição</span><span class="sxs-lookup"><span data-stu-id="a09a4-814">Definition</span></span>

<span data-ttu-id="a09a4-815">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a09a4-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a09a4-816">A expressão `Regex_sweden_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a09a4-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a09a4-817">Uma palavra- `Keywords_sweden_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="a09a4-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="a09a4-818">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a09a4-818">Keywords</span></span>

<span data-ttu-id="a09a4-819">| |</span><span class="sxs-lookup"><span data-stu-id="a09a4-819">| |</span></span>
|<span data-ttu-id="a09a4-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="a09a4-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="a09a4-821">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a09a4-821">dl#</span></span>  <br/> <span data-ttu-id="a09a4-822">driver license</span><span class="sxs-lookup"><span data-stu-id="a09a4-822">driver license</span></span>  <br/> <span data-ttu-id="a09a4-823">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-823">driver license number</span></span>  <br/> <span data-ttu-id="a09a4-824">licença de driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-824">driver licence</span></span>  <br/> <span data-ttu-id="a09a4-825">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="a09a4-825">drivers lic.</span></span>  <br/> <span data-ttu-id="a09a4-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="a09a4-826">drivers license</span></span>  <br/> <span data-ttu-id="a09a4-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a09a4-827">drivers licence</span></span>  <br/> <span data-ttu-id="a09a4-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="a09a4-828">driver's license</span></span>  <br/> <span data-ttu-id="a09a4-829">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="a09a4-829">driver's license number</span></span>  <br/> <span data-ttu-id="a09a4-830">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="a09a4-830">driver's licence number</span></span>  <br/> <span data-ttu-id="a09a4-831">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="a09a4-831">driving license number</span></span>  <br/> <span data-ttu-id="a09a4-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="a09a4-832">dlno#</span></span>  <br/> <span data-ttu-id="a09a4-833">körkort</span><span class="sxs-lookup"><span data-stu-id="a09a4-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="a09a4-834">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a09a4-834">UK</span></span>

<span data-ttu-id="a09a4-835">Para obter detalhes, consulte a seção "Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a09a4-835">For details, see the section "U.K.</span></span> <span data-ttu-id="a09a4-836">Número da carteira de motorista "em [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a09a4-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a09a4-837">Confira também</span><span class="sxs-lookup"><span data-stu-id="a09a4-837">See also</span></span>

[<span data-ttu-id="a09a4-838">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="a09a4-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

