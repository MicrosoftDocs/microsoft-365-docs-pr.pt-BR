---
title: Número da carteira de motorista da UE
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de licença do driver da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: 2e75a8724dc91ef2d895c977fdd5fcc21e7a1da4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938825"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="48fa6-104">Número da carteira de motorista da UE</span><span class="sxs-lookup"><span data-stu-id="48fa6-104">EU Driver's License Number</span></span>

<span data-ttu-id="48fa6-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de licença do driver da UE.</span><span class="sxs-lookup"><span data-stu-id="48fa6-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="48fa6-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="48fa6-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="48fa6-107">Áustria</span><span class="sxs-lookup"><span data-stu-id="48fa6-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-108">Format</span></span>

<span data-ttu-id="48fa6-109">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-110">Pattern</span></span>

<span data-ttu-id="48fa6-111">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="48fa6-112">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-112">Checksum</span></span>

<span data-ttu-id="48fa6-113">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-114">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-114">Definition</span></span>

<span data-ttu-id="48fa6-115">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-116">A expressão `Regex_austria_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-117">Uma palavra- `Keywords_austria_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="48fa6-118">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-118">Keywords</span></span>

<span data-ttu-id="48fa6-119">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-119">| |</span></span>
|<span data-ttu-id="48fa6-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-121">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-121">dl#</span></span>  <br/> <span data-ttu-id="48fa6-122">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-122">driver license</span></span>  <br/> <span data-ttu-id="48fa6-123">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-123">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-124">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-124">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-125">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-125">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-126">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-127">driver's licence</span></span>  <br/> <span data-ttu-id="48fa6-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-128">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-129">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-129">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-130">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="48fa6-131">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-131">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-132">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="48fa6-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="48fa6-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="48fa6-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="48fa6-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="48fa6-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-136">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-136">Format</span></span>

<span data-ttu-id="48fa6-137">10 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-138">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-138">Pattern</span></span>

<span data-ttu-id="48fa6-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="48fa6-140">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-140">Checksum</span></span>

<span data-ttu-id="48fa6-141">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-142">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-142">Definition</span></span>

<span data-ttu-id="48fa6-143">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-144">A expressão `Regex_belgium_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-145">Uma palavra- `Keywords_belgium_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="48fa6-146">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-146">Keywords</span></span>

<span data-ttu-id="48fa6-147">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-147">| |</span></span>
|<span data-ttu-id="48fa6-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-149">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-149">dl#</span></span>  <br/> <span data-ttu-id="48fa6-150">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-150">driver license</span></span>  <br/> <span data-ttu-id="48fa6-151">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-151">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-152">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-152">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-153">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-153">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-154">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-155">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-156">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-157">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-157">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-158">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-158">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-159">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="48fa6-160">rijbewijs</span></span>  <br/> <span data-ttu-id="48fa6-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="48fa6-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="48fa6-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48fa6-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="48fa6-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48fa6-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="48fa6-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48fa6-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="48fa6-165">führerschein- nr</span><span class="sxs-lookup"><span data-stu-id="48fa6-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="48fa6-166">fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="48fa6-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="48fa6-167">fuehrerschein- nr</span><span class="sxs-lookup"><span data-stu-id="48fa6-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="48fa6-168">Bulgária</span><span class="sxs-lookup"><span data-stu-id="48fa6-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-169">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-169">Format</span></span>

<span data-ttu-id="48fa6-170">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-171">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-171">Pattern</span></span>

<span data-ttu-id="48fa6-172">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="48fa6-173">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-173">Checksum</span></span>

<span data-ttu-id="48fa6-174">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-175">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-175">Definition</span></span>

<span data-ttu-id="48fa6-176">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-177">A expressão `Regex_bulgaria_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-178">Uma palavra- `Keywords_bulgaria_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="48fa6-179">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-179">Keywords</span></span>

<span data-ttu-id="48fa6-180">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-180">| |</span></span>
|<span data-ttu-id="48fa6-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-182">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-182">dl#</span></span>  <br/> <span data-ttu-id="48fa6-183">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-183">driver license</span></span>  <br/> <span data-ttu-id="48fa6-184">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-184">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-185">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-185">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-186">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-186">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-187">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-188">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-189">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-190">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-190">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-191">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-191">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-192">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-192">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-193">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="48fa6-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="48fa6-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="48fa6-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="48fa6-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="48fa6-196">сумпс</span></span>  <br/> <span data-ttu-id="48fa6-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="48fa6-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="48fa6-198">Croácia</span><span class="sxs-lookup"><span data-stu-id="48fa6-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-199">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-199">Format</span></span>

<span data-ttu-id="48fa6-200">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-201">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-201">Pattern</span></span>

<span data-ttu-id="48fa6-202">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="48fa6-203">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-203">Checksum</span></span>

<span data-ttu-id="48fa6-204">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-205">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-205">Definition</span></span>

<span data-ttu-id="48fa6-206">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-207">A expressão `Regex_croatia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-208">Uma palavra- `Keywords_croatia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="48fa6-209">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-209">Keywords</span></span>

<span data-ttu-id="48fa6-210">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-210">| |</span></span>
|<span data-ttu-id="48fa6-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-212">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-212">dl#</span></span>  <br/> <span data-ttu-id="48fa6-213">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-213">driver license</span></span>  <br/> <span data-ttu-id="48fa6-214">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-214">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-215">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-215">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-216">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-216">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-217">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-218">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-219">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-220">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-220">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-221">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-221">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-222">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-222">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-223">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="48fa6-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="48fa6-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="48fa6-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-226">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-226">Format</span></span>

<span data-ttu-id="48fa6-227">12 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-228">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-228">Pattern</span></span>

<span data-ttu-id="48fa6-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="48fa6-230">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-230">Checksum</span></span>

<span data-ttu-id="48fa6-231">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-232">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-232">Definition</span></span>

<span data-ttu-id="48fa6-233">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-234">A expressão `Regex_cyprus_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-235">Uma palavra- `Keywords_cyprus_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-236">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-236">Keywords</span></span>

<span data-ttu-id="48fa6-237">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-237">| |</span></span>
|<span data-ttu-id="48fa6-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-239">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-239">dl#</span></span>  <br/> <span data-ttu-id="48fa6-240">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-240">driver license</span></span>  <br/> <span data-ttu-id="48fa6-241">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-241">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-242">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-242">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-243">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-243">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-244">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-245">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-246">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-246">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-247">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-247">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-248">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-248">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-249">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="48fa6-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="48fa6-251">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="48fa6-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-252">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-252">Format</span></span>

<span data-ttu-id="48fa6-253">Duas letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-254">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-254">Pattern</span></span>

<span data-ttu-id="48fa6-255">Oito letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="48fa6-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="48fa6-256">Duas letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="48fa6-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="48fa6-257">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="48fa6-257">A space (optional)</span></span>
    
- <span data-ttu-id="48fa6-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-259">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-259">Checksum</span></span>

<span data-ttu-id="48fa6-260">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-261">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-261">Definition</span></span>

<span data-ttu-id="48fa6-262">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-263">A expressão `Regex_czech_republic_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-264">Uma palavra- `Keywords_czech_republic_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="48fa6-265">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-265">Keywords</span></span>

<span data-ttu-id="48fa6-266">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-266">| |</span></span>
|<span data-ttu-id="48fa6-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-268">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-268">dl#</span></span>  <br/> <span data-ttu-id="48fa6-269">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-269">driver license</span></span>  <br/> <span data-ttu-id="48fa6-270">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-270">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-271">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-271">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-272">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-272">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-273">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-274">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-275">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-276">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-276">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-277">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-277">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-278">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-278">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-279">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-279">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-280">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="48fa6-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="48fa6-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="48fa6-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-283">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-283">Format</span></span>

<span data-ttu-id="48fa6-284">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-285">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-285">Pattern</span></span>

<span data-ttu-id="48fa6-286">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="48fa6-287">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-287">Checksum</span></span>

<span data-ttu-id="48fa6-288">Sim</span><span class="sxs-lookup"><span data-stu-id="48fa6-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-289">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-289">Definition</span></span>

<span data-ttu-id="48fa6-290">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-291">A expressão `Regex_denmark_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-292">Uma palavra- `Keywords_denmark_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="48fa6-293">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-293">Keywords</span></span>

<span data-ttu-id="48fa6-294">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-294">| |</span></span>
|<span data-ttu-id="48fa6-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-296">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-296">dl#</span></span>  <br/> <span data-ttu-id="48fa6-297">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-297">driver license</span></span>  <br/> <span data-ttu-id="48fa6-298">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-298">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-299">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-299">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-300">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-300">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-301">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-302">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-303">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-304">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-304">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-305">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-305">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-306">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-306">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-307">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="48fa6-308">kørekort</span></span>  <br/> <span data-ttu-id="48fa6-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="48fa6-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="48fa6-310">Estônia</span><span class="sxs-lookup"><span data-stu-id="48fa6-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-311">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-311">Format</span></span>

<span data-ttu-id="48fa6-312">Duas letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-313">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-313">Pattern</span></span>

<span data-ttu-id="48fa6-314">Duas letras e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="48fa6-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="48fa6-315">As letras "ET" (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="48fa6-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="48fa6-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-317">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-317">Checksum</span></span>

<span data-ttu-id="48fa6-318">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-319">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-319">Definition</span></span>

<span data-ttu-id="48fa6-320">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-321">A expressão `Regex_estonia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-322">Uma palavra- `Keywords_estonia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-323">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-323">Keywords</span></span>

<span data-ttu-id="48fa6-324">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-324">| |</span></span>
|<span data-ttu-id="48fa6-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-326">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-326">dl#</span></span>  <br/> <span data-ttu-id="48fa6-327">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-327">driver license</span></span>  <br/> <span data-ttu-id="48fa6-328">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-328">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-329">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-329">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-330">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-330">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-331">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-331">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-332">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-333">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-334">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-335">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-335">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-336">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-336">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-337">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="48fa6-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="48fa6-339">Finlândia</span><span class="sxs-lookup"><span data-stu-id="48fa6-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-340">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-340">Format</span></span>

<span data-ttu-id="48fa6-341">10 dígitos que contêm um hífen</span><span class="sxs-lookup"><span data-stu-id="48fa6-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-342">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-342">Pattern</span></span>

<span data-ttu-id="48fa6-343">10 dígitos contendo um hífen:</span><span class="sxs-lookup"><span data-stu-id="48fa6-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="48fa6-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-344">Six digits</span></span> 
    
- <span data-ttu-id="48fa6-345">Um hífen</span><span class="sxs-lookup"><span data-stu-id="48fa6-345">A hyphen</span></span>
    
-  <span data-ttu-id="48fa6-346">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="48fa6-347">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-347">Checksum</span></span>

<span data-ttu-id="48fa6-348">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-349">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-349">Definition</span></span>

<span data-ttu-id="48fa6-350">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-351">A expressão `Regex_finland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-352">Uma palavra- `Keywords_finland_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-353">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-353">Keywords</span></span>

<span data-ttu-id="48fa6-354">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-354">| |</span></span>
|<span data-ttu-id="48fa6-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-356">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-356">dl#</span></span>  <br/> <span data-ttu-id="48fa6-357">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-357">driver license</span></span>  <br/> <span data-ttu-id="48fa6-358">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-358">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-359">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-359">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-360">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-360">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-361">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-362">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-363">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-364">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-364">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-365">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-365">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-366">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-366">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-367">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="48fa6-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="48fa6-369">França</span><span class="sxs-lookup"><span data-stu-id="48fa6-369">France</span></span>

<span data-ttu-id="48fa6-370">Para obter detalhes, consulte a seção "número da carteira de motorista do driver da França" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="48fa6-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="48fa6-371">Alemanha</span><span class="sxs-lookup"><span data-stu-id="48fa6-371">Germany</span></span>

<span data-ttu-id="48fa6-372">Para obter detalhes, consulte a seção "número da carteira de motorista do driver alemão" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="48fa6-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="48fa6-373">Grécia</span><span class="sxs-lookup"><span data-stu-id="48fa6-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-374">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-374">Format</span></span>

<span data-ttu-id="48fa6-375">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-376">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-376">Pattern</span></span>

 <span data-ttu-id="48fa6-377">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="48fa6-378">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-378">Checksum</span></span>

<span data-ttu-id="48fa6-379">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-380">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-380">Definition</span></span>

<span data-ttu-id="48fa6-381">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-382">A expressão `Regex_greece_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-383">Uma palavra- `Keywords_greece_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-384">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-384">Keywords</span></span>

<span data-ttu-id="48fa6-385">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-385">| |</span></span>
|<span data-ttu-id="48fa6-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="48fa6-387">dlL#</span></span>  <br/> <span data-ttu-id="48fa6-388">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-388">driver license</span></span>  <br/> <span data-ttu-id="48fa6-389">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-389">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-390">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-390">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-391">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-391">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-392">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-393">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-394">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-395">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-395">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-396">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-396">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-397">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-397">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-398">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="48fa6-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="48fa6-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="48fa6-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="48fa6-401">Hungria</span><span class="sxs-lookup"><span data-stu-id="48fa6-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-402">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-402">Format</span></span>

<span data-ttu-id="48fa6-403">Duas letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-404">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-404">Pattern</span></span>

<span data-ttu-id="48fa6-405">Duas letras e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="48fa6-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="48fa6-406">Duas letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="48fa6-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="48fa6-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-408">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-408">Checksum</span></span>

<span data-ttu-id="48fa6-409">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-410">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-410">Definition</span></span>

<span data-ttu-id="48fa6-411">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-412">A expressão `Regex_hungary_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-413">Uma palavra- `Keywords_hungary_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-414">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-414">Keywords</span></span>

<span data-ttu-id="48fa6-415">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-415">| |</span></span>
|<span data-ttu-id="48fa6-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-417">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-417">dl#</span></span>  <br/> <span data-ttu-id="48fa6-418">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-418">driver license</span></span>  <br/> <span data-ttu-id="48fa6-419">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-419">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-420">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-420">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-421">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-421">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-422">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-423">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-424">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-425">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-425">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-426">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-426">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-427">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-427">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-428">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="48fa6-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="48fa6-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="48fa6-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-431">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-431">Format</span></span>

<span data-ttu-id="48fa6-432">Seis dígitos seguidos de quatro letras</span><span class="sxs-lookup"><span data-stu-id="48fa6-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-433">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-433">Pattern</span></span>

<span data-ttu-id="48fa6-434">Seis dígitos e quatro letras:</span><span class="sxs-lookup"><span data-stu-id="48fa6-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="48fa6-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-435">Six digits</span></span>
    
- <span data-ttu-id="48fa6-436">Quatro letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="48fa6-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-437">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-437">Checksum</span></span>

<span data-ttu-id="48fa6-438">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-439">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-439">Definition</span></span>

<span data-ttu-id="48fa6-440">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-441">A expressão `Regex_ireland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-442">Uma palavra- `Keywords_ireland_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-443">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-443">Keywords</span></span>

<span data-ttu-id="48fa6-444">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-444">| |</span></span>
|<span data-ttu-id="48fa6-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-446">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-446">dl#</span></span>  <br/> <span data-ttu-id="48fa6-447">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-447">driver license</span></span>  <br/> <span data-ttu-id="48fa6-448">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-448">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-449">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-449">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-450">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-450">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-451">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-452">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-453">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-454">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-454">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-455">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-455">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-456">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-456">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-457">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="48fa6-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="48fa6-459">Itália</span><span class="sxs-lookup"><span data-stu-id="48fa6-459">Italy</span></span>

<span data-ttu-id="48fa6-460">Para obter detalhes, consulte a seção "número da carteira de motorista do driver da Itália" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="48fa6-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="48fa6-461">Letônia</span><span class="sxs-lookup"><span data-stu-id="48fa6-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-462">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-462">Format</span></span>

<span data-ttu-id="48fa6-463">Três letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-464">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-464">Pattern</span></span>

<span data-ttu-id="48fa6-465">Três letras e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="48fa6-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="48fa6-466">Três letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="48fa6-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="48fa6-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-468">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-468">Checksum</span></span>

<span data-ttu-id="48fa6-469">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-470">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-470">Definition</span></span>

<span data-ttu-id="48fa6-471">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-472">A expressão `Regex_latvia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-473">Uma palavra- `Keywords_latvia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-474">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-474">Keywords</span></span>

<span data-ttu-id="48fa6-475">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-475">| |</span></span>
|<span data-ttu-id="48fa6-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-477">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-477">dl#</span></span>  <br/> <span data-ttu-id="48fa6-478">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-478">driver license</span></span>  <br/> <span data-ttu-id="48fa6-479">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-479">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-480">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-480">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-481">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-481">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-482">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-483">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-484">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-485">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-485">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-486">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-486">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-487">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-487">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-488">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="48fa6-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="48fa6-490">Lituânia</span><span class="sxs-lookup"><span data-stu-id="48fa6-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-491">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-491">Format</span></span>

<span data-ttu-id="48fa6-492">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-493">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-493">Pattern</span></span>

 <span data-ttu-id="48fa6-494">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="48fa6-495">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-495">Checksum</span></span>

<span data-ttu-id="48fa6-496">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-497">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-497">Definition</span></span>

<span data-ttu-id="48fa6-498">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-499">A expressão `Regex_lithuania_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-500">Uma palavra- `Keywords_lithuania_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-501">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-501">Keywords</span></span>

<span data-ttu-id="48fa6-502">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-502">| |</span></span>
|<span data-ttu-id="48fa6-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-504">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-504">dl#</span></span>  <br/> <span data-ttu-id="48fa6-505">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-505">driver license</span></span>  <br/> <span data-ttu-id="48fa6-506">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-506">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-507">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-507">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-508">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-508">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-509">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-510">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-511">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-512">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-512">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-513">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-513">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-514">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-514">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-515">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="48fa6-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="48fa6-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="48fa6-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-518">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-518">Format</span></span>

<span data-ttu-id="48fa6-519">Seis dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-520">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-520">Pattern</span></span>

 <span data-ttu-id="48fa6-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="48fa6-522">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-522">Checksum</span></span>

<span data-ttu-id="48fa6-523">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-524">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-524">Definition</span></span>

<span data-ttu-id="48fa6-525">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-526">A expressão `Regex_luxemburg_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-527">Uma palavra- `Keywords_luxemburg_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-528">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-528">Keywords</span></span>

<span data-ttu-id="48fa6-529">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-529">| |</span></span>
|<span data-ttu-id="48fa6-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-531">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-531">dl#</span></span>  <br/> <span data-ttu-id="48fa6-532">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-532">driver license</span></span>  <br/> <span data-ttu-id="48fa6-533">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-533">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-534">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-534">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-535">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-535">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-536">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-537">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-538">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-539">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-539">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-540">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-540">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-541">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-541">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-542">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="48fa6-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="48fa6-544">Malta</span><span class="sxs-lookup"><span data-stu-id="48fa6-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-545">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-545">Format</span></span>

<span data-ttu-id="48fa6-546">Combinação de dois caracteres e seis dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="48fa6-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-547">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-547">Pattern</span></span>

<span data-ttu-id="48fa6-548">Combinação de dois caracteres e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="48fa6-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="48fa6-549">Dois caracteres (dígitos ou letras, não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="48fa6-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="48fa6-550">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="48fa6-550">A space (optional)</span></span>
    
- <span data-ttu-id="48fa6-551">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-551">Three digits</span></span>
    
- <span data-ttu-id="48fa6-552">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="48fa6-552">A space (optional)</span></span>
    
- <span data-ttu-id="48fa6-553">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-554">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-554">Checksum</span></span>

<span data-ttu-id="48fa6-555">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-556">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-556">Definition</span></span>

<span data-ttu-id="48fa6-557">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-558">A expressão `Regex_malta_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-559">Uma palavra- `Keywords_malta_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-560">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-560">Keywords</span></span>

<span data-ttu-id="48fa6-561">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-561">| |</span></span>
|<span data-ttu-id="48fa6-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-563">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-563">dl#</span></span>  <br/> <span data-ttu-id="48fa6-564">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-564">driver license</span></span>  <br/> <span data-ttu-id="48fa6-565">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-565">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-566">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-566">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-567">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-567">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-568">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-569">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-570">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-571">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-571">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-572">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-572">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-573">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-573">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-574">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="48fa6-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="48fa6-576">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="48fa6-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-577">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-577">Format</span></span>

<span data-ttu-id="48fa6-578">10 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-579">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-579">Pattern</span></span>

<span data-ttu-id="48fa6-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="48fa6-581">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-581">Checksum</span></span>

<span data-ttu-id="48fa6-582">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-583">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-583">Definition</span></span>

<span data-ttu-id="48fa6-584">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-585">A expressão `Regex_netherlands_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-586">Uma palavra- `Keywords_netherlands_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-587">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-587">Keywords</span></span>

<span data-ttu-id="48fa6-588">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-588">| |</span></span>
|<span data-ttu-id="48fa6-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-590">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-590">dl#</span></span>  <br/> <span data-ttu-id="48fa6-591">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-591">driver license</span></span>  <br/> <span data-ttu-id="48fa6-592">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-592">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-593">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-593">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-594">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-594">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-595">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-596">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-597">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-598">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-598">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-599">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-599">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-600">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-600">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-601">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="48fa6-602">permis de conduire</span></span>  <br/> <span data-ttu-id="48fa6-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="48fa6-603">rijbewijs</span></span>  <br/> <span data-ttu-id="48fa6-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="48fa6-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="48fa6-605">Polônia</span><span class="sxs-lookup"><span data-stu-id="48fa6-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-606">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-606">Format</span></span>

<span data-ttu-id="48fa6-607">14 dígitos contendo 2 barras</span><span class="sxs-lookup"><span data-stu-id="48fa6-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-608">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-608">Pattern</span></span>

<span data-ttu-id="48fa6-609">14 dígitos e 2 barras de avanço:</span><span class="sxs-lookup"><span data-stu-id="48fa6-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="48fa6-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-610">Five digits</span></span> 
    
- <span data-ttu-id="48fa6-611">Uma barra</span><span class="sxs-lookup"><span data-stu-id="48fa6-611">A forward slash</span></span>
    
- <span data-ttu-id="48fa6-612">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-612">Two digits</span></span>
    
- <span data-ttu-id="48fa6-613">Uma barra</span><span class="sxs-lookup"><span data-stu-id="48fa6-613">A forward slash</span></span>
    
- <span data-ttu-id="48fa6-614">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-615">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-615">Checksum</span></span>

<span data-ttu-id="48fa6-616">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-617">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-617">Definition</span></span>

<span data-ttu-id="48fa6-618">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-619">A expressão `Regex_poland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-620">Uma palavra- `Keywords_poland_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-621">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-621">Keywords</span></span>

<span data-ttu-id="48fa6-622">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-622">| |</span></span>
|<span data-ttu-id="48fa6-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-624">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-624">dl#</span></span>  <br/> <span data-ttu-id="48fa6-625">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-625">driver license</span></span>  <br/> <span data-ttu-id="48fa6-626">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-626">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-627">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-627">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-628">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-628">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-629">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-630">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-631">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-632">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-632">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-633">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-633">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-634">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-634">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-635">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="48fa6-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="48fa6-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="48fa6-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-638">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-638">Format</span></span>

<span data-ttu-id="48fa6-639">Duas letras seguidas por sete números no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="48fa6-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-640">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-640">Pattern</span></span>

<span data-ttu-id="48fa6-641">Duas letras seguidas por sete números com caracteres especiais:</span><span class="sxs-lookup"><span data-stu-id="48fa6-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="48fa6-642">Duas letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="48fa6-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="48fa6-643">Um hífen</span><span class="sxs-lookup"><span data-stu-id="48fa6-643">A hyphen</span></span>
    
- <span data-ttu-id="48fa6-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-644">Six digits</span></span>
    
- <span data-ttu-id="48fa6-645">Um espaço</span><span class="sxs-lookup"><span data-stu-id="48fa6-645">A space</span></span>
    
- <span data-ttu-id="48fa6-646">Um dígito</span><span class="sxs-lookup"><span data-stu-id="48fa6-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-647">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-647">Checksum</span></span>

<span data-ttu-id="48fa6-648">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-649">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-649">Definition</span></span>

<span data-ttu-id="48fa6-650">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-651">A expressão `Regex_portugal_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-652">Uma palavra- `Keywords_portugal_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-653">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-653">Keywords</span></span>

<span data-ttu-id="48fa6-654">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-654">| |</span></span>
|<span data-ttu-id="48fa6-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-656">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-656">dl#</span></span>  <br/> <span data-ttu-id="48fa6-657">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-657">driver license</span></span>  <br/> <span data-ttu-id="48fa6-658">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-658">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-659">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-659">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-660">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-660">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-661">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-662">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-663">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-664">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-664">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-665">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-665">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-666">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-666">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-667">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="48fa6-669">Romênia</span><span class="sxs-lookup"><span data-stu-id="48fa6-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-670">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-670">Format</span></span>

<span data-ttu-id="48fa6-671">Um caractere seguido por oito dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-672">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-672">Pattern</span></span>

<span data-ttu-id="48fa6-673">Um caractere seguido por oito dígitos:</span><span class="sxs-lookup"><span data-stu-id="48fa6-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="48fa6-674">Uma letra (não diferencia maiúsculas de minúsculas) ou dígito</span><span class="sxs-lookup"><span data-stu-id="48fa6-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="48fa6-675">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-676">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-676">Checksum</span></span>

<span data-ttu-id="48fa6-677">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-678">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-678">Definition</span></span>

<span data-ttu-id="48fa6-679">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-680">A expressão `Regex_romania_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-681">Uma palavra- `Keywords_romania_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-682">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-682">Keywords</span></span>

<span data-ttu-id="48fa6-683">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-683">| |</span></span>
|<span data-ttu-id="48fa6-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-685">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-685">dl#</span></span>  <br/> <span data-ttu-id="48fa6-686">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-686">driver license</span></span>  <br/> <span data-ttu-id="48fa6-687">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-687">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-688">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-688">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-689">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-689">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-690">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-691">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-692">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-693">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-693">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-694">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-694">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-695">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-695">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-696">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-697">permé de conducere</span><span class="sxs-lookup"><span data-stu-id="48fa6-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="48fa6-698">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="48fa6-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-699">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-699">Format</span></span>

<span data-ttu-id="48fa6-700">Um caractere seguido por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-701">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-701">Pattern</span></span>

<span data-ttu-id="48fa6-702">Um caractere seguido por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="48fa6-703">Uma letra (não diferencia maiúsculas de minúsculas) ou dígito</span><span class="sxs-lookup"><span data-stu-id="48fa6-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="48fa6-704">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="48fa6-705">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-705">Checksum</span></span>

<span data-ttu-id="48fa6-706">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-707">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-707">Definition</span></span>

<span data-ttu-id="48fa6-708">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-709">A expressão `Regex_slovakia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-710">Uma palavra- `Keywords_slovakia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-711">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-711">Keywords</span></span>

<span data-ttu-id="48fa6-712">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-712">| |</span></span>
|<span data-ttu-id="48fa6-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-714">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-714">dl#</span></span>  <br/> <span data-ttu-id="48fa6-715">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-715">driver license</span></span>  <br/> <span data-ttu-id="48fa6-716">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-716">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-717">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-717">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-718">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-718">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-719">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-720">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-721">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-722">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-722">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-723">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-723">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-724">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-724">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-725">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="48fa6-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="48fa6-727">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="48fa6-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-728">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-728">Format</span></span>

<span data-ttu-id="48fa6-729">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="48fa6-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-730">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-730">Pattern</span></span>

<span data-ttu-id="48fa6-731">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="48fa6-732">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-732">Checksum</span></span>

<span data-ttu-id="48fa6-733">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-734">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-734">Definition</span></span>

<span data-ttu-id="48fa6-735">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-736">A expressão `Regex_slovenia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-737">Uma palavra- `Keywords_slovenia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-738">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-738">Keywords</span></span>

<span data-ttu-id="48fa6-739">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-739">| |</span></span>
|<span data-ttu-id="48fa6-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-741">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-741">dl#</span></span>  <br/> <span data-ttu-id="48fa6-742">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-742">driver license</span></span>  <br/> <span data-ttu-id="48fa6-743">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-743">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-744">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-744">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-745">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-745">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-746">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-747">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-748">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-749">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-749">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-750">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-750">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-751">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-751">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-752">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="48fa6-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="48fa6-754">Espanha</span><span class="sxs-lookup"><span data-stu-id="48fa6-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-755">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-755">Format</span></span>

<span data-ttu-id="48fa6-756">Oito dígitos seguidos de um caractere</span><span class="sxs-lookup"><span data-stu-id="48fa6-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-757">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-757">Pattern</span></span>

<span data-ttu-id="48fa6-758">Oito dígitos seguidos de um caractere:</span><span class="sxs-lookup"><span data-stu-id="48fa6-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="48fa6-759">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-759">Eight digits</span></span> 
    
- <span data-ttu-id="48fa6-760">Um dígito ou letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="48fa6-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-761">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-761">Checksum</span></span>

<span data-ttu-id="48fa6-762">Sim</span><span class="sxs-lookup"><span data-stu-id="48fa6-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-763">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-763">Definition</span></span>

<span data-ttu-id="48fa6-764">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-765">A função `Func_spain_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-766">Uma palavra- `Keywords_spain_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48fa6-767">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-767">Keywords</span></span>

<span data-ttu-id="48fa6-768">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-768">| |</span></span>
|<span data-ttu-id="48fa6-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-770">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-771">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-771">dl#</span></span>  <br/> <span data-ttu-id="48fa6-772">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-772">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-773">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-773">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-774">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-774">driver license</span></span>  <br/> <span data-ttu-id="48fa6-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-775">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-776">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-777">driver's licence</span></span>  <br/> <span data-ttu-id="48fa6-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-778">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-779">driving licence</span></span>  <br/> <span data-ttu-id="48fa6-780">driving licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-780">driving license</span></span>  <br/> <span data-ttu-id="48fa6-781">número de licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-781">driver licence number</span></span>  <br/> <span data-ttu-id="48fa6-782">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-782">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-783">número de licença de drivers</span><span class="sxs-lookup"><span data-stu-id="48fa6-783">drivers licence number</span></span>  <br/> <span data-ttu-id="48fa6-784">número de licença de drivers</span><span class="sxs-lookup"><span data-stu-id="48fa6-784">drivers license number</span></span>  <br/> <span data-ttu-id="48fa6-785">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-785">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-786">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-786">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-787">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-787">driving licence number</span></span>  <br/> <span data-ttu-id="48fa6-788">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-788">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-789">permissão de condução</span><span class="sxs-lookup"><span data-stu-id="48fa6-789">driving permit</span></span>  <br/> <span data-ttu-id="48fa6-790">número de permissão de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-790">driving permit number</span></span>  <br/> <span data-ttu-id="48fa6-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="48fa6-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="48fa6-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="48fa6-792">permiso conducción</span></span>  <br/> <span data-ttu-id="48fa6-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="48fa6-794">número de Carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="48fa6-795">número Carnet conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="48fa6-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-796">licencia conducir</span></span>  <br/> <span data-ttu-id="48fa6-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="48fa6-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="48fa6-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="48fa6-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-800">permiso conducir</span></span>  <br/> <span data-ttu-id="48fa6-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="48fa6-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="48fa6-802">El Carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="48fa6-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="48fa6-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="48fa6-804">Suécia</span><span class="sxs-lookup"><span data-stu-id="48fa6-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="48fa6-805">Formatar</span><span class="sxs-lookup"><span data-stu-id="48fa6-805">Format</span></span>

<span data-ttu-id="48fa6-806">Dez dígitos contendo um hífen</span><span class="sxs-lookup"><span data-stu-id="48fa6-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="48fa6-807">Padrão</span><span class="sxs-lookup"><span data-stu-id="48fa6-807">Pattern</span></span>

<span data-ttu-id="48fa6-808">Dez dígitos contendo um hífen:</span><span class="sxs-lookup"><span data-stu-id="48fa6-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="48fa6-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-809">Six digits</span></span> 
    
- <span data-ttu-id="48fa6-810">Um hífen</span><span class="sxs-lookup"><span data-stu-id="48fa6-810">A hyphen</span></span>
    
- <span data-ttu-id="48fa6-811">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="48fa6-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="48fa6-812">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="48fa6-812">Checksum</span></span>

<span data-ttu-id="48fa6-813">Não</span><span class="sxs-lookup"><span data-stu-id="48fa6-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="48fa6-814">Definição</span><span class="sxs-lookup"><span data-stu-id="48fa6-814">Definition</span></span>

<span data-ttu-id="48fa6-815">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="48fa6-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="48fa6-816">A expressão `Regex_sweden_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="48fa6-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="48fa6-817">Uma palavra- `Keywords_sweden_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="48fa6-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="48fa6-818">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="48fa6-818">Keywords</span></span>

<span data-ttu-id="48fa6-819">| |</span><span class="sxs-lookup"><span data-stu-id="48fa6-819">| |</span></span>
|<span data-ttu-id="48fa6-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="48fa6-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="48fa6-821">distribuição #</span><span class="sxs-lookup"><span data-stu-id="48fa6-821">dl#</span></span>  <br/> <span data-ttu-id="48fa6-822">driver license</span><span class="sxs-lookup"><span data-stu-id="48fa6-822">driver license</span></span>  <br/> <span data-ttu-id="48fa6-823">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-823">driver license number</span></span>  <br/> <span data-ttu-id="48fa6-824">licença de driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-824">driver licence</span></span>  <br/> <span data-ttu-id="48fa6-825">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="48fa6-825">drivers lic.</span></span>  <br/> <span data-ttu-id="48fa6-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="48fa6-826">drivers license</span></span>  <br/> <span data-ttu-id="48fa6-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48fa6-827">drivers licence</span></span>  <br/> <span data-ttu-id="48fa6-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="48fa6-828">driver's license</span></span>  <br/> <span data-ttu-id="48fa6-829">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="48fa6-829">driver's license number</span></span>  <br/> <span data-ttu-id="48fa6-830">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="48fa6-830">driver's licence number</span></span>  <br/> <span data-ttu-id="48fa6-831">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="48fa6-831">driving license number</span></span>  <br/> <span data-ttu-id="48fa6-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="48fa6-832">dlno#</span></span>  <br/> <span data-ttu-id="48fa6-833">körkort</span><span class="sxs-lookup"><span data-stu-id="48fa6-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="48fa6-834">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="48fa6-834">UK</span></span>

<span data-ttu-id="48fa6-835">Para obter detalhes, consulte a seção "Reino Unido</span><span class="sxs-lookup"><span data-stu-id="48fa6-835">For details, see the section "U.K.</span></span> <span data-ttu-id="48fa6-836">Número da carteira de motorista "em [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="48fa6-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="48fa6-837">Confira também</span><span class="sxs-lookup"><span data-stu-id="48fa6-837">See also</span></span>

[<span data-ttu-id="48fa6-838">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="48fa6-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

