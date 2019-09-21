---
title: Número da carteira de motorista da UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de licença do driver da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072679"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="6a4f8-104">Número da carteira de motorista da UE</span><span class="sxs-lookup"><span data-stu-id="6a4f8-104">EU Driver's License Number</span></span>

<span data-ttu-id="6a4f8-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de licença do driver da UE.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="6a4f8-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="6a4f8-107">Áustria </span><span class="sxs-lookup"><span data-stu-id="6a4f8-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-108">Format</span></span>

<span data-ttu-id="6a4f8-109">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-110">Pattern</span></span>

<span data-ttu-id="6a4f8-111">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-112">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-112">Checksum</span></span>

<span data-ttu-id="6a4f8-113">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-114">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-114">Definition</span></span>

<span data-ttu-id="6a4f8-115">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-116">A expressão `Regex_austria_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-117">Uma palavra- `Keywords_austria_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="6a4f8-118">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-118">Keywords</span></span>

<span data-ttu-id="6a4f8-119">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-119"></span></span>
|<span data-ttu-id="6a4f8-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-121">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-121">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-122">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-122">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-123">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-123">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-124">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-124">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-125">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-125">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-126">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-127">driver's licence</span></span>  <br/> <span data-ttu-id="6a4f8-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-128">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-129">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-129">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-130">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="6a4f8-131">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-131">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-132">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="6a4f8-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="6a4f8-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="6a4f8-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="6a4f8-135">Bélgica </span><span class="sxs-lookup"><span data-stu-id="6a4f8-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-136">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-136">Format</span></span>

<span data-ttu-id="6a4f8-137">10 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-138">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-138">Pattern</span></span>

<span data-ttu-id="6a4f8-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-140">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-140">Checksum</span></span>

<span data-ttu-id="6a4f8-141">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-142">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-142">Definition</span></span>

<span data-ttu-id="6a4f8-143">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-144">A expressão `Regex_belgium_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-145">Uma palavra- `Keywords_belgium_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="6a4f8-146">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-146">Keywords</span></span>

<span data-ttu-id="6a4f8-147">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-147"></span></span>
|<span data-ttu-id="6a4f8-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-149">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-149">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-150">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-150">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-151">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-151">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-152">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-152">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-153">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-153">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-154">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-155">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-156">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-157">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-157">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-158">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-158">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-159">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="6a4f8-160">rijbewijs</span></span>  <br/> <span data-ttu-id="6a4f8-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="6a4f8-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="6a4f8-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="6a4f8-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="6a4f8-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="6a4f8-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="6a4f8-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="6a4f8-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="6a4f8-165">führerschein- nr</span><span class="sxs-lookup"><span data-stu-id="6a4f8-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="6a4f8-166">fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="6a4f8-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="6a4f8-167">fuehrerschein- nr</span><span class="sxs-lookup"><span data-stu-id="6a4f8-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="6a4f8-168">Bulgária</span><span class="sxs-lookup"><span data-stu-id="6a4f8-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-169">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-169">Format</span></span>

<span data-ttu-id="6a4f8-170">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-171">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-171">Pattern</span></span>

<span data-ttu-id="6a4f8-172">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-173">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-173">Checksum</span></span>

<span data-ttu-id="6a4f8-174">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-175">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-175">Definition</span></span>

<span data-ttu-id="6a4f8-176">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-177">A expressão `Regex_bulgaria_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-178">Uma palavra- `Keywords_bulgaria_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="6a4f8-179">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-179">Keywords</span></span>

<span data-ttu-id="6a4f8-180">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-180"></span></span>
|<span data-ttu-id="6a4f8-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-182">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-182">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-183">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-183">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-184">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-184">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-185">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-185">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-186">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-186">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-187">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-188">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-189">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-190">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-190">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-191">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-191">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-192">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-192">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-193">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="6a4f8-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="6a4f8-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="6a4f8-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="6a4f8-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="6a4f8-196">сумпс</span></span>  <br/> <span data-ttu-id="6a4f8-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="6a4f8-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="6a4f8-198">Croácia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-199">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-199">Format</span></span>

<span data-ttu-id="6a4f8-200">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-201">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-201">Pattern</span></span>

<span data-ttu-id="6a4f8-202">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-203">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-203">Checksum</span></span>

<span data-ttu-id="6a4f8-204">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-205">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-205">Definition</span></span>

<span data-ttu-id="6a4f8-206">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-207">A expressão `Regex_croatia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-208">Uma palavra- `Keywords_croatia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="6a4f8-209">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-209">Keywords</span></span>

<span data-ttu-id="6a4f8-210">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-210"></span></span>
|<span data-ttu-id="6a4f8-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-212">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-212">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-213">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-213">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-214">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-214">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-215">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-215">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-216">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-216">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-217">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-218">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-219">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-220">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-220">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-221">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-221">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-222">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-222">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-223">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="6a4f8-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="6a4f8-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="6a4f8-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-226">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-226">Format</span></span>

<span data-ttu-id="6a4f8-227">12 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-228">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-228">Pattern</span></span>

<span data-ttu-id="6a4f8-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-230">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-230">Checksum</span></span>

<span data-ttu-id="6a4f8-231">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-232">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-232">Definition</span></span>

<span data-ttu-id="6a4f8-233">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-234">A expressão `Regex_cyprus_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-235">Uma palavra- `Keywords_cyprus_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-236">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-236">Keywords</span></span>

<span data-ttu-id="6a4f8-237">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-237"></span></span>
|<span data-ttu-id="6a4f8-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-239">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-239">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-240">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-240">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-241">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-241">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-242">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-242">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-243">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-243">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-244">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-245">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-246">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-246">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-247">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-247">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-248">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-248">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-249">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="6a4f8-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="6a4f8-251">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="6a4f8-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-252">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-252">Format</span></span>

<span data-ttu-id="6a4f8-253">Duas letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-254">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-254">Pattern</span></span>

<span data-ttu-id="6a4f8-255">Oito letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="6a4f8-256">Duas letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="6a4f8-257">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-257">A space (optional)</span></span>
    
- <span data-ttu-id="6a4f8-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-259">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-259">Checksum</span></span>

<span data-ttu-id="6a4f8-260">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-261">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-261">Definition</span></span>

<span data-ttu-id="6a4f8-262">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-263">A expressão `Regex_czech_republic_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-264">Uma palavra- `Keywords_czech_republic_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="6a4f8-265">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-265">Keywords</span></span>

<span data-ttu-id="6a4f8-266">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-266"></span></span>
|<span data-ttu-id="6a4f8-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-268">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-268">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-269">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-269">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-270">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-270">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-271">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-271">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-272">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-272">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-273">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-274">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-275">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-276">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-276">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-277">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-277">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-278">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-278">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-279">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-279">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-280">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="6a4f8-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="6a4f8-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="6a4f8-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-283">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-283">Format</span></span>

<span data-ttu-id="6a4f8-284">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-285">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-285">Pattern</span></span>

<span data-ttu-id="6a4f8-286">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-287">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-287">Checksum</span></span>

<span data-ttu-id="6a4f8-288">Sim</span><span class="sxs-lookup"><span data-stu-id="6a4f8-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-289">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-289">Definition</span></span>

<span data-ttu-id="6a4f8-290">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-291">A expressão `Regex_denmark_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-292">Uma palavra- `Keywords_denmark_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="6a4f8-293">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-293">Keywords</span></span>

<span data-ttu-id="6a4f8-294">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-294"></span></span>
|<span data-ttu-id="6a4f8-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-296">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-296">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-297">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-297">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-298">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-298">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-299">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-299">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-300">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-300">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-301">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-302">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-303">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-304">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-304">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-305">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-305">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-306">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-306">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-307">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="6a4f8-308">kørekort</span></span>  <br/> <span data-ttu-id="6a4f8-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="6a4f8-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="6a4f8-310">Estônia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-311">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-311">Format</span></span>

<span data-ttu-id="6a4f8-312">Duas letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-313">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-313">Pattern</span></span>

<span data-ttu-id="6a4f8-314">Duas letras e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="6a4f8-315">As letras "ET" (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="6a4f8-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-317">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-317">Checksum</span></span>

<span data-ttu-id="6a4f8-318">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-319">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-319">Definition</span></span>

<span data-ttu-id="6a4f8-320">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-321">A expressão `Regex_estonia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-322">Uma palavra- `Keywords_estonia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-323">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-323">Keywords</span></span>

<span data-ttu-id="6a4f8-324">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-324"></span></span>
|<span data-ttu-id="6a4f8-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-326">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-326">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-327">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-327">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-328">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-328">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-329">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-329">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-330">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-330">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-331">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-331">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-332">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-333">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-334">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-335">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-335">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-336">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-336">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-337">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="6a4f8-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="6a4f8-339">Finlândia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-340">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-340">Format</span></span>

<span data-ttu-id="6a4f8-341">10 dígitos que contêm um hífen</span><span class="sxs-lookup"><span data-stu-id="6a4f8-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-342">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-342">Pattern</span></span>

<span data-ttu-id="6a4f8-343">10 dígitos contendo um hífen:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="6a4f8-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-344">Six digits</span></span> 
    
- <span data-ttu-id="6a4f8-345">Um hífen</span><span class="sxs-lookup"><span data-stu-id="6a4f8-345">A hyphen</span></span>
    
-  <span data-ttu-id="6a4f8-346">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-347">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-347">Checksum</span></span>

<span data-ttu-id="6a4f8-348">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-349">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-349">Definition</span></span>

<span data-ttu-id="6a4f8-350">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-351">A expressão `Regex_finland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-352">Uma palavra- `Keywords_finland_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-353">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-353">Keywords</span></span>

<span data-ttu-id="6a4f8-354">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-354"></span></span>
|<span data-ttu-id="6a4f8-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-356">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-356">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-357">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-357">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-358">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-358">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-359">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-359">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-360">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-360">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-361">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-362">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-363">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-364">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-364">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-365">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-365">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-366">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-366">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-367">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="6a4f8-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="6a4f8-369">França</span><span class="sxs-lookup"><span data-stu-id="6a4f8-369">France</span></span>

<span data-ttu-id="6a4f8-370">Para obter detalhes, consulte a seção "número da carteira de motorista do driver da França" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6a4f8-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="6a4f8-371">Alemanha</span><span class="sxs-lookup"><span data-stu-id="6a4f8-371">Germany</span></span>

<span data-ttu-id="6a4f8-372">Para obter detalhes, consulte a seção "número da carteira de motorista do driver alemão" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6a4f8-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="6a4f8-373">Grécia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-374">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-374">Format</span></span>

<span data-ttu-id="6a4f8-375">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-376">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-376">Pattern</span></span>

 <span data-ttu-id="6a4f8-377">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-378">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-378">Checksum</span></span>

<span data-ttu-id="6a4f8-379">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-380">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-380">Definition</span></span>

<span data-ttu-id="6a4f8-381">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-382">A expressão `Regex_greece_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-383">Uma palavra- `Keywords_greece_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-384">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-384">Keywords</span></span>

<span data-ttu-id="6a4f8-385">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-385"></span></span>
|<span data-ttu-id="6a4f8-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-387">dlL#</span></span>  <br/> <span data-ttu-id="6a4f8-388">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-388">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-389">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-389">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-390">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-390">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-391">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-391">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-392">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-393">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-394">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-395">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-395">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-396">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-396">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-397">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-397">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-398">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="6a4f8-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="6a4f8-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="6a4f8-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="6a4f8-401">Hungria</span><span class="sxs-lookup"><span data-stu-id="6a4f8-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-402">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-402">Format</span></span>

<span data-ttu-id="6a4f8-403">Duas letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-404">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-404">Pattern</span></span>

<span data-ttu-id="6a4f8-405">Duas letras e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="6a4f8-406">Duas letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="6a4f8-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-408">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-408">Checksum</span></span>

<span data-ttu-id="6a4f8-409">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-410">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-410">Definition</span></span>

<span data-ttu-id="6a4f8-411">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-412">A expressão `Regex_hungary_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-413">Uma palavra- `Keywords_hungary_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-414">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-414">Keywords</span></span>

<span data-ttu-id="6a4f8-415">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-415"></span></span>
|<span data-ttu-id="6a4f8-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-417">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-417">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-418">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-418">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-419">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-419">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-420">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-420">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-421">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-421">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-422">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-423">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-424">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-425">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-425">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-426">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-426">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-427">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-427">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-428">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="6a4f8-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="6a4f8-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="6a4f8-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-431">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-431">Format</span></span>

<span data-ttu-id="6a4f8-432">Seis dígitos seguidos de quatro letras</span><span class="sxs-lookup"><span data-stu-id="6a4f8-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-433">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-433">Pattern</span></span>

<span data-ttu-id="6a4f8-434">Seis dígitos e quatro letras:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="6a4f8-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-435">Six digits</span></span>
    
- <span data-ttu-id="6a4f8-436">Quatro letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-437">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-437">Checksum</span></span>

<span data-ttu-id="6a4f8-438">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-439">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-439">Definition</span></span>

<span data-ttu-id="6a4f8-440">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-441">A expressão `Regex_ireland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-442">Uma palavra- `Keywords_ireland_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-443">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-443">Keywords</span></span>

<span data-ttu-id="6a4f8-444">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-444"></span></span>
|<span data-ttu-id="6a4f8-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-446">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-446">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-447">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-447">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-448">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-448">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-449">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-449">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-450">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-450">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-451">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-452">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-453">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-454">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-454">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-455">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-455">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-456">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-456">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-457">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="6a4f8-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="6a4f8-459">Itália</span><span class="sxs-lookup"><span data-stu-id="6a4f8-459">Italy</span></span>

<span data-ttu-id="6a4f8-460">Para obter detalhes, consulte a seção "número da carteira de motorista do driver da Itália" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6a4f8-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="6a4f8-461">Letônia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-462">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-462">Format</span></span>

<span data-ttu-id="6a4f8-463">Três letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-464">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-464">Pattern</span></span>

<span data-ttu-id="6a4f8-465">Três letras e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="6a4f8-466">Três letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="6a4f8-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-468">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-468">Checksum</span></span>

<span data-ttu-id="6a4f8-469">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-470">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-470">Definition</span></span>

<span data-ttu-id="6a4f8-471">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-472">A expressão `Regex_latvia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-473">Uma palavra- `Keywords_latvia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-474">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-474">Keywords</span></span>

<span data-ttu-id="6a4f8-475">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-475"></span></span>
|<span data-ttu-id="6a4f8-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-477">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-477">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-478">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-478">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-479">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-479">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-480">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-480">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-481">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-481">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-482">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-483">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-484">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-485">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-485">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-486">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-486">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-487">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-487">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-488">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="6a4f8-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="6a4f8-490">Lituânia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-491">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-491">Format</span></span>

<span data-ttu-id="6a4f8-492">Oito dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-493">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-493">Pattern</span></span>

 <span data-ttu-id="6a4f8-494">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-495">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-495">Checksum</span></span>

<span data-ttu-id="6a4f8-496">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-497">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-497">Definition</span></span>

<span data-ttu-id="6a4f8-498">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-499">A expressão `Regex_lithuania_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-500">Uma palavra- `Keywords_lithuania_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-501">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-501">Keywords</span></span>

<span data-ttu-id="6a4f8-502">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-502"></span></span>
|<span data-ttu-id="6a4f8-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-504">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-504">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-505">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-505">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-506">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-506">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-507">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-507">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-508">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-508">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-509">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-510">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-511">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-512">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-512">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-513">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-513">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-514">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-514">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-515">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="6a4f8-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="6a4f8-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="6a4f8-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-518">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-518">Format</span></span>

<span data-ttu-id="6a4f8-519">Seis dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-520">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-520">Pattern</span></span>

 <span data-ttu-id="6a4f8-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-522">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-522">Checksum</span></span>

<span data-ttu-id="6a4f8-523">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-524">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-524">Definition</span></span>

<span data-ttu-id="6a4f8-525">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-526">A expressão `Regex_luxemburg_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-527">Uma palavra- `Keywords_luxemburg_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-528">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-528">Keywords</span></span>

<span data-ttu-id="6a4f8-529">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-529"></span></span>
|<span data-ttu-id="6a4f8-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-531">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-531">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-532">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-532">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-533">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-533">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-534">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-534">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-535">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-535">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-536">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-537">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-538">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-539">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-539">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-540">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-540">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-541">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-541">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-542">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="6a4f8-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="6a4f8-544">Malta</span><span class="sxs-lookup"><span data-stu-id="6a4f8-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-545">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-545">Format</span></span>

<span data-ttu-id="6a4f8-546">Combinação de dois caracteres e seis dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="6a4f8-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-547">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-547">Pattern</span></span>

<span data-ttu-id="6a4f8-548">Combinação de dois caracteres e seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="6a4f8-549">Dois caracteres (dígitos ou letras, não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="6a4f8-550">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-550">A space (optional)</span></span>
    
- <span data-ttu-id="6a4f8-551">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-551">Three digits</span></span>
    
- <span data-ttu-id="6a4f8-552">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-552">A space (optional)</span></span>
    
- <span data-ttu-id="6a4f8-553">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-554">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-554">Checksum</span></span>

<span data-ttu-id="6a4f8-555">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-556">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-556">Definition</span></span>

<span data-ttu-id="6a4f8-557">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-558">A expressão `Regex_malta_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-559">Uma palavra- `Keywords_malta_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-560">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-560">Keywords</span></span>

<span data-ttu-id="6a4f8-561">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-561"></span></span>
|<span data-ttu-id="6a4f8-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-563">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-563">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-564">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-564">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-565">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-565">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-566">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-566">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-567">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-567">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-568">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-569">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-570">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-571">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-571">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-572">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-572">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-573">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-573">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-574">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="6a4f8-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="6a4f8-576">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-577">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-577">Format</span></span>

<span data-ttu-id="6a4f8-578">10 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-579">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-579">Pattern</span></span>

<span data-ttu-id="6a4f8-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-581">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-581">Checksum</span></span>

<span data-ttu-id="6a4f8-582">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-583">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-583">Definition</span></span>

<span data-ttu-id="6a4f8-584">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-585">A expressão `Regex_netherlands_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-586">Uma palavra- `Keywords_netherlands_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-587">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-587">Keywords</span></span>

<span data-ttu-id="6a4f8-588">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-588"></span></span>
|<span data-ttu-id="6a4f8-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-590">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-590">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-591">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-591">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-592">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-592">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-593">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-593">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-594">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-594">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-595">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-596">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-597">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-598">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-598">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-599">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-599">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-600">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-600">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-601">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="6a4f8-602">permis de conduire</span></span>  <br/> <span data-ttu-id="6a4f8-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="6a4f8-603">rijbewijs</span></span>  <br/> <span data-ttu-id="6a4f8-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="6a4f8-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="6a4f8-605">Polônia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-606">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-606">Format</span></span>

<span data-ttu-id="6a4f8-607">14 dígitos contendo 2 barras</span><span class="sxs-lookup"><span data-stu-id="6a4f8-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-608">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-608">Pattern</span></span>

<span data-ttu-id="6a4f8-609">14 dígitos e 2 barras de avanço:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="6a4f8-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-610">Five digits</span></span> 
    
- <span data-ttu-id="6a4f8-611">Uma barra</span><span class="sxs-lookup"><span data-stu-id="6a4f8-611">A forward slash</span></span>
    
- <span data-ttu-id="6a4f8-612">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-612">Two digits</span></span>
    
- <span data-ttu-id="6a4f8-613">Uma barra</span><span class="sxs-lookup"><span data-stu-id="6a4f8-613">A forward slash</span></span>
    
- <span data-ttu-id="6a4f8-614">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-615">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-615">Checksum</span></span>

<span data-ttu-id="6a4f8-616">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-617">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-617">Definition</span></span>

<span data-ttu-id="6a4f8-618">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-619">A expressão `Regex_poland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-620">Uma palavra- `Keywords_poland_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-621">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-621">Keywords</span></span>

<span data-ttu-id="6a4f8-622">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-622"></span></span>
|<span data-ttu-id="6a4f8-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-624">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-624">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-625">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-625">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-626">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-626">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-627">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-627">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-628">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-628">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-629">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-630">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-631">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-632">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-632">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-633">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-633">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-634">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-634">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-635">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="6a4f8-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="6a4f8-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="6a4f8-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-638">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-638">Format</span></span>

<span data-ttu-id="6a4f8-639">Duas letras seguidas por sete números no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="6a4f8-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-640">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-640">Pattern</span></span>

<span data-ttu-id="6a4f8-641">Duas letras seguidas por sete números com caracteres especiais:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="6a4f8-642">Duas letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="6a4f8-643">Um hífen</span><span class="sxs-lookup"><span data-stu-id="6a4f8-643">A hyphen</span></span>
    
- <span data-ttu-id="6a4f8-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-644">Six digits</span></span>
    
- <span data-ttu-id="6a4f8-645">Um espaço</span><span class="sxs-lookup"><span data-stu-id="6a4f8-645">A space</span></span>
    
- <span data-ttu-id="6a4f8-646">Um dígito</span><span class="sxs-lookup"><span data-stu-id="6a4f8-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-647">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-647">Checksum</span></span>

<span data-ttu-id="6a4f8-648">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-649">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-649">Definition</span></span>

<span data-ttu-id="6a4f8-650">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-651">A expressão `Regex_portugal_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-652">Uma palavra- `Keywords_portugal_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-653">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-653">Keywords</span></span>

<span data-ttu-id="6a4f8-654">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-654"></span></span>
|<span data-ttu-id="6a4f8-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-656">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-656">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-657">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-657">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-658">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-658">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-659">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-659">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-660">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-660">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-661">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-662">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-663">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-664">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-664">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-665">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-665">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-666">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-666">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-667">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="6a4f8-669">Romênia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-670">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-670">Format</span></span>

<span data-ttu-id="6a4f8-671">Um caractere seguido por oito dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-672">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-672">Pattern</span></span>

<span data-ttu-id="6a4f8-673">Um caractere seguido por oito dígitos:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="6a4f8-674">Uma letra (não diferencia maiúsculas de minúsculas) ou dígito</span><span class="sxs-lookup"><span data-stu-id="6a4f8-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="6a4f8-675">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-676">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-676">Checksum</span></span>

<span data-ttu-id="6a4f8-677">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-678">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-678">Definition</span></span>

<span data-ttu-id="6a4f8-679">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-680">A expressão `Regex_romania_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-681">Uma palavra- `Keywords_romania_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-682">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-682">Keywords</span></span>

<span data-ttu-id="6a4f8-683">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-683"></span></span>
|<span data-ttu-id="6a4f8-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-685">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-685">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-686">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-686">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-687">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-687">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-688">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-688">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-689">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-689">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-690">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-691">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-692">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-693">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-693">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-694">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-694">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-695">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-695">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-696">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-697">permé de conducere</span><span class="sxs-lookup"><span data-stu-id="6a4f8-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="6a4f8-698">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-699">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-699">Format</span></span>

<span data-ttu-id="6a4f8-700">Um caractere seguido por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-701">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-701">Pattern</span></span>

<span data-ttu-id="6a4f8-702">Um caractere seguido por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="6a4f8-703">Uma letra (não diferencia maiúsculas de minúsculas) ou dígito</span><span class="sxs-lookup"><span data-stu-id="6a4f8-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="6a4f8-704">Sete dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-705">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-705">Checksum</span></span>

<span data-ttu-id="6a4f8-706">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-707">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-707">Definition</span></span>

<span data-ttu-id="6a4f8-708">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-709">A expressão `Regex_slovakia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-710">Uma palavra- `Keywords_slovakia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-711">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-711">Keywords</span></span>

<span data-ttu-id="6a4f8-712">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-712"></span></span>
|<span data-ttu-id="6a4f8-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-714">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-714">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-715">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-715">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-716">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-716">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-717">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-717">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-718">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-718">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-719">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-720">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-721">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-722">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-722">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-723">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-723">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-724">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-724">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-725">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="6a4f8-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="6a4f8-727">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-728">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-728">Format</span></span>

<span data-ttu-id="6a4f8-729">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="6a4f8-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-730">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-730">Pattern</span></span>

<span data-ttu-id="6a4f8-731">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a4f8-732">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-732">Checksum</span></span>

<span data-ttu-id="6a4f8-733">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-734">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-734">Definition</span></span>

<span data-ttu-id="6a4f8-735">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-736">A expressão `Regex_slovenia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-737">Uma palavra- `Keywords_slovenia_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-738">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-738">Keywords</span></span>

<span data-ttu-id="6a4f8-739">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-739"></span></span>
|<span data-ttu-id="6a4f8-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-741">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-741">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-742">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-742">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-743">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-743">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-744">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-744">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-745">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-745">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-746">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-747">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-748">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-749">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-749">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-750">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-750">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-751">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-751">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-752">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="6a4f8-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="6a4f8-754">Espanha</span><span class="sxs-lookup"><span data-stu-id="6a4f8-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-755">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-755">Format</span></span>

<span data-ttu-id="6a4f8-756">Oito dígitos seguidos de um caractere</span><span class="sxs-lookup"><span data-stu-id="6a4f8-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-757">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-757">Pattern</span></span>

<span data-ttu-id="6a4f8-758">Oito dígitos seguidos de um caractere:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="6a4f8-759">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-759">Eight digits</span></span> 
    
- <span data-ttu-id="6a4f8-760">Um dígito ou letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="6a4f8-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-761">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-761">Checksum</span></span>

<span data-ttu-id="6a4f8-762">Sim</span><span class="sxs-lookup"><span data-stu-id="6a4f8-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-763">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-763">Definition</span></span>

<span data-ttu-id="6a4f8-764">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-765">A função `Func_spain_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-766">Uma palavra- `Keywords_spain_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-767">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-767">Keywords</span></span>

<span data-ttu-id="6a4f8-768">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-768"></span></span>
|<span data-ttu-id="6a4f8-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-770">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-771">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-771">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-772">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-772">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-773">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-773">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-774">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-774">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-775">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-776">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-777">driver's licence</span></span>  <br/> <span data-ttu-id="6a4f8-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-778">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-779">driving licence</span></span>  <br/> <span data-ttu-id="6a4f8-780">driving licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-780">driving license</span></span>  <br/> <span data-ttu-id="6a4f8-781">número de licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-781">driver licence number</span></span>  <br/> <span data-ttu-id="6a4f8-782">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-782">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-783">número de licença de drivers</span><span class="sxs-lookup"><span data-stu-id="6a4f8-783">drivers licence number</span></span>  <br/> <span data-ttu-id="6a4f8-784">número de licença de drivers</span><span class="sxs-lookup"><span data-stu-id="6a4f8-784">drivers license number</span></span>  <br/> <span data-ttu-id="6a4f8-785">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-785">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-786">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-786">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-787">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-787">driving licence number</span></span>  <br/> <span data-ttu-id="6a4f8-788">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-788">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-789">permissão de condução</span><span class="sxs-lookup"><span data-stu-id="6a4f8-789">driving permit</span></span>  <br/> <span data-ttu-id="6a4f8-790">número de permissão de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-790">driving permit number</span></span>  <br/> <span data-ttu-id="6a4f8-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="6a4f8-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="6a4f8-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="6a4f8-792">permiso conducción</span></span>  <br/> <span data-ttu-id="6a4f8-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="6a4f8-794">número de Carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="6a4f8-795">número Carnet conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="6a4f8-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-796">licencia conducir</span></span>  <br/> <span data-ttu-id="6a4f8-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="6a4f8-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="6a4f8-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="6a4f8-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-800">permiso conducir</span></span>  <br/> <span data-ttu-id="6a4f8-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="6a4f8-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="6a4f8-802">El Carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="6a4f8-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="6a4f8-804">Suécia</span><span class="sxs-lookup"><span data-stu-id="6a4f8-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="6a4f8-805">Formatar</span><span class="sxs-lookup"><span data-stu-id="6a4f8-805">Format</span></span>

<span data-ttu-id="6a4f8-806">Dez dígitos contendo um hífen</span><span class="sxs-lookup"><span data-stu-id="6a4f8-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a4f8-807">Padrão</span><span class="sxs-lookup"><span data-stu-id="6a4f8-807">Pattern</span></span>

<span data-ttu-id="6a4f8-808">Dez dígitos contendo um hífen:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="6a4f8-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-809">Six digits</span></span> 
    
- <span data-ttu-id="6a4f8-810">Um hífen</span><span class="sxs-lookup"><span data-stu-id="6a4f8-810">A hyphen</span></span>
    
- <span data-ttu-id="6a4f8-811">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="6a4f8-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a4f8-812">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="6a4f8-812">Checksum</span></span>

<span data-ttu-id="6a4f8-813">Não</span><span class="sxs-lookup"><span data-stu-id="6a4f8-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a4f8-814">Definição</span><span class="sxs-lookup"><span data-stu-id="6a4f8-814">Definition</span></span>

<span data-ttu-id="6a4f8-815">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="6a4f8-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a4f8-816">A expressão `Regex_sweden_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a4f8-817">Uma palavra- `Keywords_sweden_eu_driver's_license_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="6a4f8-818">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a4f8-818">Keywords</span></span>

<span data-ttu-id="6a4f8-819">| |</span><span class="sxs-lookup"><span data-stu-id="6a4f8-819"></span></span>
|<span data-ttu-id="6a4f8-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6a4f8-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6a4f8-821">distribuição #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-821">dl#</span></span>  <br/> <span data-ttu-id="6a4f8-822">driver license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-822">driver license</span></span>  <br/> <span data-ttu-id="6a4f8-823">número de carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-823">driver license number</span></span>  <br/> <span data-ttu-id="6a4f8-824">licença de driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-824">driver licence</span></span>  <br/> <span data-ttu-id="6a4f8-825">drivers driver'lic.</span><span class="sxs-lookup"><span data-stu-id="6a4f8-825">drivers lic.</span></span>  <br/> <span data-ttu-id="6a4f8-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-826">drivers license</span></span>  <br/> <span data-ttu-id="6a4f8-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a4f8-827">drivers licence</span></span>  <br/> <span data-ttu-id="6a4f8-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a4f8-828">driver's license</span></span>  <br/> <span data-ttu-id="6a4f8-829">número da carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="6a4f8-829">driver's license number</span></span>  <br/> <span data-ttu-id="6a4f8-830">número de licença do driver</span><span class="sxs-lookup"><span data-stu-id="6a4f8-830">driver's licence number</span></span>  <br/> <span data-ttu-id="6a4f8-831">número da licença de dirigir</span><span class="sxs-lookup"><span data-stu-id="6a4f8-831">driving license number</span></span>  <br/> <span data-ttu-id="6a4f8-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="6a4f8-832">dlno#</span></span>  <br/> <span data-ttu-id="6a4f8-833">körkort</span><span class="sxs-lookup"><span data-stu-id="6a4f8-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="6a4f8-834">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="6a4f8-834">UK</span></span>

<span data-ttu-id="6a4f8-835">Para obter detalhes, consulte a seção "Reino Unido</span><span class="sxs-lookup"><span data-stu-id="6a4f8-835">For details, see the section "U.K.</span></span> <span data-ttu-id="6a4f8-836">Número da carteira de motorista "em [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6a4f8-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a4f8-837">Confira também</span><span class="sxs-lookup"><span data-stu-id="6a4f8-837">See also</span></span>

[<span data-ttu-id="6a4f8-838">O que os tipos de informações confidenciais procuram</span><span class="sxs-lookup"><span data-stu-id="6a4f8-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

