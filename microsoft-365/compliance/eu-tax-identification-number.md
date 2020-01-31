---
title: Número de identificação do imposto da UE
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
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação de imposto da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: 5467db921bd518eeeab18a36ee2de473f9017358
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41591012"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="96be3-104">Número de identificação do imposto da UE</span><span class="sxs-lookup"><span data-stu-id="96be3-104">EU Tax Identification Number</span></span>

<span data-ttu-id="96be3-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação de imposto (TIN) da UE.</span><span class="sxs-lookup"><span data-stu-id="96be3-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="96be3-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="96be3-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="96be3-107">Áustria</span><span class="sxs-lookup"><span data-stu-id="96be3-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="96be3-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-108">Format</span></span>

<span data-ttu-id="96be3-109">Nove dígitos com hífen opcional e barra para frente</span><span class="sxs-lookup"><span data-stu-id="96be3-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-110">Pattern</span></span>

<span data-ttu-id="96be3-111">Nove dígitos com hífen opcional e barra para frente:</span><span class="sxs-lookup"><span data-stu-id="96be3-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="96be3-112">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-112">Two digits</span></span> 
    
- <span data-ttu-id="96be3-113">Um hífen (opcional)</span><span class="sxs-lookup"><span data-stu-id="96be3-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="96be3-114">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-114">Three digits</span></span>
    
- <span data-ttu-id="96be3-115">Uma barra (opcional)</span><span class="sxs-lookup"><span data-stu-id="96be3-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="96be3-116">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-117">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-117">Checksum</span></span>

<span data-ttu-id="96be3-118">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-119">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-119">Definition</span></span>

<span data-ttu-id="96be3-120">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-121">A função `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-122">Uma palavra- `Keywords_austria_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-123">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-124">A função `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-125">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="96be3-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-127">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-127">tax number</span></span>
  
<span data-ttu-id="96be3-128">number</span><span class="sxs-lookup"><span data-stu-id="96be3-128">number</span></span>
  
<span data-ttu-id="96be3-129">número de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-129">tax registration number</span></span>
  
<span data-ttu-id="96be3-130">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-130">tax id</span></span>
  
<span data-ttu-id="96be3-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="96be3-131">st.nr.</span></span>
  
<span data-ttu-id="96be3-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="96be3-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="96be3-133">Bélgica</span><span class="sxs-lookup"><span data-stu-id="96be3-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="96be3-134">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-134">Format</span></span>

<span data-ttu-id="96be3-135">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-136">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-136">Pattern</span></span>

<span data-ttu-id="96be3-137">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="96be3-137">11 digits:</span></span>
  
- <span data-ttu-id="96be3-138">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-138">Two digits</span></span>
    
- <span data-ttu-id="96be3-139">Um "0" ou "1"</span><span class="sxs-lookup"><span data-stu-id="96be3-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="96be3-140">Um dígito</span><span class="sxs-lookup"><span data-stu-id="96be3-140">One digit</span></span>
    
- <span data-ttu-id="96be3-141">"0" ou "1" ou "2" ou "3"</span><span class="sxs-lookup"><span data-stu-id="96be3-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="96be3-142">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-143">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-143">Checksum</span></span>

<span data-ttu-id="96be3-144">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-145">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-145">Definition</span></span>

<span data-ttu-id="96be3-146">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-147">A expressão `Regex_belgium_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-148">Uma palavra- `Keywords_belgium_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-149">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="96be3-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-151">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-151">tax number</span></span>
  
<span data-ttu-id="96be3-152">número de Registro Nacional</span><span class="sxs-lookup"><span data-stu-id="96be3-152">national registration number</span></span>
  
<span data-ttu-id="96be3-153">número de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-153">tax registration number</span></span>
  
<span data-ttu-id="96be3-154">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-154">tax id</span></span>
  
<span data-ttu-id="96be3-155">nse</span><span class="sxs-lookup"><span data-stu-id="96be3-155">nif</span></span>
  
<span data-ttu-id="96be3-156">nse #</span><span class="sxs-lookup"><span data-stu-id="96be3-156">nif#</span></span>
  
<span data-ttu-id="96be3-157">Numéro de Registro Nacional</span><span class="sxs-lookup"><span data-stu-id="96be3-157">numéro de registre national</span></span>
  
<span data-ttu-id="96be3-158">Numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="96be3-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="96be3-159">Bulgária</span><span class="sxs-lookup"><span data-stu-id="96be3-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="96be3-160">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-160">Format</span></span>

<span data-ttu-id="96be3-161">Dez dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-162">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-162">Pattern</span></span>

<span data-ttu-id="96be3-163">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-164">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-164">Checksum</span></span>

<span data-ttu-id="96be3-165">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-166">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-166">Definition</span></span>

<span data-ttu-id="96be3-167">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-168">A função `Func_bulgaria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-169">Uma palavra- `Keywords_bulgaria_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-170">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-171">A função `Func_bulgaria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-172">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="96be3-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-174">bucn</span><span class="sxs-lookup"><span data-stu-id="96be3-174">bucn</span></span>
  
<span data-ttu-id="96be3-175">número civil uniforme</span><span class="sxs-lookup"><span data-stu-id="96be3-175">uniform civil number</span></span>
  
<span data-ttu-id="96be3-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="96be3-176">bucn#</span></span>
  
<span data-ttu-id="96be3-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="96be3-178">ID civil uniforme</span><span class="sxs-lookup"><span data-stu-id="96be3-178">uniform civil id</span></span>
  
<span data-ttu-id="96be3-179">Nenhum civil uniforme</span><span class="sxs-lookup"><span data-stu-id="96be3-179">uniform civil no</span></span>
  
<span data-ttu-id="96be3-180">egn</span><span class="sxs-lookup"><span data-stu-id="96be3-180">egn</span></span>
  
<span data-ttu-id="96be3-181">número civil uniforme búlgaro</span><span class="sxs-lookup"><span data-stu-id="96be3-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="96be3-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="96be3-182">uniformcivilno#</span></span>
  
<span data-ttu-id="96be3-183">egn #</span><span class="sxs-lookup"><span data-stu-id="96be3-183">egn#</span></span>
  
<span data-ttu-id="96be3-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="96be3-184">униформ граждански номер</span></span>
  
<span data-ttu-id="96be3-185">ID униформ</span><span class="sxs-lookup"><span data-stu-id="96be3-185">униформ id</span></span>
  
<span data-ttu-id="96be3-186">ID de граждански униформ</span><span class="sxs-lookup"><span data-stu-id="96be3-186">униформ граждански id</span></span>
  
<span data-ttu-id="96be3-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="96be3-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="96be3-188">Croácia</span><span class="sxs-lookup"><span data-stu-id="96be3-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="96be3-189">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-189">Format</span></span>

<span data-ttu-id="96be3-190">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-191">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-191">Pattern</span></span>

<span data-ttu-id="96be3-192">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="96be3-192">11 digits:</span></span>
  
- <span data-ttu-id="96be3-193">Dez dígitos, escolhidos aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="96be3-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="96be3-194">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-195">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-195">Checksum</span></span>

<span data-ttu-id="96be3-196">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-197">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-197">Definition</span></span>

<span data-ttu-id="96be3-198">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-199">A função `Func_croatia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-200">Uma palavra- `Keywords_croatia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-201">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-202">A função `Func_croatia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-203">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="96be3-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-205">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-205">tax number</span></span>
  
<span data-ttu-id="96be3-206">imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-206">tax</span></span>
  
<span data-ttu-id="96be3-207">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-207">tax id</span></span>
  
<span data-ttu-id="96be3-208">OID</span><span class="sxs-lookup"><span data-stu-id="96be3-208">oid</span></span>
  
<span data-ttu-id="96be3-209">OID #</span><span class="sxs-lookup"><span data-stu-id="96be3-209">oid#</span></span>
  
<span data-ttu-id="96be3-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="96be3-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="96be3-211">Chipre</span><span class="sxs-lookup"><span data-stu-id="96be3-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="96be3-212">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-212">Format</span></span>

<span data-ttu-id="96be3-213">Oito dígitos e uma letra no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="96be3-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-214">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-214">Pattern</span></span>

<span data-ttu-id="96be3-215">Oito dígitos e uma letra:</span><span class="sxs-lookup"><span data-stu-id="96be3-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="96be3-216">Um "0"</span><span class="sxs-lookup"><span data-stu-id="96be3-216">A "0"</span></span> 
    
- <span data-ttu-id="96be3-217">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="96be3-217">Seven digits</span></span>
    
- <span data-ttu-id="96be3-218">Uma letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-219">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-219">Checksum</span></span>

<span data-ttu-id="96be3-220">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-221">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-221">Definition</span></span>

<span data-ttu-id="96be3-222">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-223">A função `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-224">Uma palavra- `Keywords_cyprus_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-225">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-226">A função `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-227">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="96be3-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-229">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-229">tax number</span></span>
  
<span data-ttu-id="96be3-230">imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-230">tax</span></span>
  
<span data-ttu-id="96be3-231">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-231">tax id</span></span>
  
<span data-ttu-id="96be3-232">código de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-232">tax identification code</span></span>
  
<span data-ttu-id="96be3-233">tic</span><span class="sxs-lookup"><span data-stu-id="96be3-233">tic</span></span>
  
<span data-ttu-id="96be3-234">tic #</span><span class="sxs-lookup"><span data-stu-id="96be3-234">tic#</span></span>
  
<span data-ttu-id="96be3-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="96be3-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="96be3-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="96be3-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="96be3-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="96be3-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="96be3-238">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="96be3-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="96be3-239">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-239">Format</span></span>

<span data-ttu-id="96be3-240">Nove ou dez dígitos com uma barra invertida opcional</span><span class="sxs-lookup"><span data-stu-id="96be3-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-241">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-241">Pattern</span></span>

<span data-ttu-id="96be3-242">Nove ou dez dígitos com uma barra invertida opcional:</span><span class="sxs-lookup"><span data-stu-id="96be3-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="96be3-243">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-243">Six digits</span></span> 
    
- <span data-ttu-id="96be3-244">Uma barra invertida (opcional)</span><span class="sxs-lookup"><span data-stu-id="96be3-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="96be3-245">Três ou quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-246">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-246">Checksum</span></span>

<span data-ttu-id="96be3-247">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-248">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-248">Definition</span></span>

<span data-ttu-id="96be3-249">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-250">A expressão `Regex_czech_republic_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-251">Uma palavra- `Keywords_czech_republic_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-252">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="96be3-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-254">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-254">tax number</span></span>
  
<span data-ttu-id="96be3-255">imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-255">tax</span></span>
  
<span data-ttu-id="96be3-256">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-256">tax id</span></span>
  
<span data-ttu-id="96be3-257">número pessoal</span><span class="sxs-lookup"><span data-stu-id="96be3-257">personal number</span></span>
  
<span data-ttu-id="96be3-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="96be3-258">daňové číslo</span></span>
  
<span data-ttu-id="96be3-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="96be3-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="96be3-260">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="96be3-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="96be3-261">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-261">Format</span></span>

<span data-ttu-id="96be3-262">Dez dígitos contendo um hífen</span><span class="sxs-lookup"><span data-stu-id="96be3-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-263">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-263">Pattern</span></span>

<span data-ttu-id="96be3-264">Dez dígitos contendo um hífen:</span><span class="sxs-lookup"><span data-stu-id="96be3-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="96be3-265">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="96be3-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="96be3-266">Um hífen</span><span class="sxs-lookup"><span data-stu-id="96be3-266">A hyphen</span></span>
    
- <span data-ttu-id="96be3-267">Quatro dígitos que correspondem a um número de sequência onde o primeiro dígito corresponde ao século do nascimento e o último dígito corresponde ao sexo da pessoa (ímpar para macho e par para fêmea)</span><span class="sxs-lookup"><span data-stu-id="96be3-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-268">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-268">Checksum</span></span>

<span data-ttu-id="96be3-269">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-270">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-270">Definition</span></span>

<span data-ttu-id="96be3-271">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-272">A função `Func_denmark_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-273">Uma palavra- `Keywords_denmark_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-274">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-275">A função `Func_denmark_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-276">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="96be3-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-278">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-278">tax number</span></span>
  
<span data-ttu-id="96be3-279">imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-279">tax</span></span>
  
<span data-ttu-id="96be3-280">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-280">tax id</span></span>
  
<span data-ttu-id="96be3-281">número de CPR</span><span class="sxs-lookup"><span data-stu-id="96be3-281">cpr number</span></span>
  
<span data-ttu-id="96be3-282">pedir #</span><span class="sxs-lookup"><span data-stu-id="96be3-282">cpr#</span></span>
  
<span data-ttu-id="96be3-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="96be3-283">skat nummer</span></span>
  
<span data-ttu-id="96be3-284">ID Skat</span><span class="sxs-lookup"><span data-stu-id="96be3-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="96be3-285">Estônia</span><span class="sxs-lookup"><span data-stu-id="96be3-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="96be3-286">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-286">Format</span></span>

<span data-ttu-id="96be3-287">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-288">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-288">Pattern</span></span>

<span data-ttu-id="96be3-289">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="96be3-289">11 digits:</span></span>
  
-  <span data-ttu-id="96be3-290">Um dígito que corresponde ao gênero e ao século de nascimento onde um número ímpar indica macho e o número par indica fêmea da seguinte maneira: 1, 2 para o século 19; 3, 4 para o século 20; e 5, 6 para o século 21</span><span class="sxs-lookup"><span data-stu-id="96be3-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="96be3-291">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="96be3-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="96be3-292">Três dígitos que correspondem a um número de série separando as pessoas que nasceu na mesma data</span><span class="sxs-lookup"><span data-stu-id="96be3-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="96be3-293">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-294">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-294">Checksum</span></span>

<span data-ttu-id="96be3-295">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-296">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-296">Definition</span></span>

<span data-ttu-id="96be3-297">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-298">A função `Func_estonia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-299">Uma palavra- `Keywords_estonia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-300">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-301">A função `Func_estonia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-302">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="96be3-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-304">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-304">tax number</span></span>
  
<span data-ttu-id="96be3-305">imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-305">tax</span></span>
  
<span data-ttu-id="96be3-306">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-306">tax id</span></span>
  
<span data-ttu-id="96be3-307">código pessoal</span><span class="sxs-lookup"><span data-stu-id="96be3-307">personal code</span></span>
  
<span data-ttu-id="96be3-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="96be3-308">maksunumber</span></span>
  
<span data-ttu-id="96be3-309">ID maksu</span><span class="sxs-lookup"><span data-stu-id="96be3-309">maksu id</span></span>
  
<span data-ttu-id="96be3-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="96be3-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="96be3-311">Finlândia</span><span class="sxs-lookup"><span data-stu-id="96be3-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="96be3-312">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-312">Format</span></span>

<span data-ttu-id="96be3-313">Uma combinação de 11 caracteres de dígitos, letras e sinal de mais e de menos</span><span class="sxs-lookup"><span data-stu-id="96be3-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-314">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-314">Pattern</span></span>

<span data-ttu-id="96be3-315">Uma combinação de 11 caracteres de dígitos, letras e sinal de mais e menos:</span><span class="sxs-lookup"><span data-stu-id="96be3-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="96be3-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-316">Six digits</span></span>
    
- <span data-ttu-id="96be3-317">Uma das seguintes opções: um sinal de adição, um sinal de menos ou a letra "A" (não diferencia maiúsculas de minúsculas) onde o sinal de mais significa que nasceu entre 1800-1899, o sinal de menos significa que nasceu entre 1900-1999 e "A" significa que nasceu 2000 e depois</span><span class="sxs-lookup"><span data-stu-id="96be3-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="96be3-318">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-318">Three digits</span></span>
    
- <span data-ttu-id="96be3-319">Uma letra ou um número</span><span class="sxs-lookup"><span data-stu-id="96be3-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-320">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-320">Checksum</span></span>

<span data-ttu-id="96be3-321">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-322">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-322">Definition</span></span>

<span data-ttu-id="96be3-323">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-324">A função `Func_finland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-325">Uma palavra- `Keywords_finland_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-326">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-327">A função `Func_finland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-328">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="96be3-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-330">identification number</span><span class="sxs-lookup"><span data-stu-id="96be3-330">identification number</span></span>
  
<span data-ttu-id="96be3-331">ID pessoal</span><span class="sxs-lookup"><span data-stu-id="96be3-331">personal id</span></span>
  
<span data-ttu-id="96be3-332">número de identidade</span><span class="sxs-lookup"><span data-stu-id="96be3-332">identity number</span></span>
  
<span data-ttu-id="96be3-333">número de ID nacional da finlandês</span><span class="sxs-lookup"><span data-stu-id="96be3-333">finnish national id number</span></span>
  
<span data-ttu-id="96be3-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-334">personalidnumber#</span></span>
  
<span data-ttu-id="96be3-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="96be3-335">national identification number</span></span>
  
<span data-ttu-id="96be3-336">número de identificação</span><span class="sxs-lookup"><span data-stu-id="96be3-336">id number</span></span>
  
<span data-ttu-id="96be3-337">n º de ID nacional</span><span class="sxs-lookup"><span data-stu-id="96be3-337">national id no.</span></span>
  
<span data-ttu-id="96be3-338">número de ID nacional</span><span class="sxs-lookup"><span data-stu-id="96be3-338">national id number</span></span>
  
<span data-ttu-id="96be3-339">ID não</span><span class="sxs-lookup"><span data-stu-id="96be3-339">id no</span></span>
  
<span data-ttu-id="96be3-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="96be3-340">tunnistenumero</span></span>
  
<span data-ttu-id="96be3-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="96be3-341">henkilötunnus</span></span>
  
<span data-ttu-id="96be3-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="96be3-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="96be3-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="96be3-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="96be3-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="96be3-344">identiteetti numero</span></span>
  
<span data-ttu-id="96be3-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="96be3-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="96be3-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="96be3-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="96be3-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="96be3-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="96be3-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="96be3-348">tunnusnumero</span></span>
  
<span data-ttu-id="96be3-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="96be3-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="96be3-350">França</span><span class="sxs-lookup"><span data-stu-id="96be3-350">France</span></span>

### <a name="format"></a><span data-ttu-id="96be3-351">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-351">Format</span></span>

<span data-ttu-id="96be3-352">13 dígitos para pessoas e nove dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="96be3-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-353">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-353">Pattern</span></span>

<span data-ttu-id="96be3-354">13 dígitos para pessoas:</span><span class="sxs-lookup"><span data-stu-id="96be3-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="96be3-355">Um dígito que deve ser 0, 1, 2 ou 3</span><span class="sxs-lookup"><span data-stu-id="96be3-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="96be3-356">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-356">12 digits</span></span>
    
<span data-ttu-id="96be3-357">Nove dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="96be3-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-358">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-358">Checksum</span></span>

<span data-ttu-id="96be3-359">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-360">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-360">Definition</span></span>

<span data-ttu-id="96be3-361">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-362">A função `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-363">Uma palavra- `Keywords_france_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-364">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-365">A função `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-366">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="96be3-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-368">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-368">tax identification number</span></span>
  
<span data-ttu-id="96be3-369">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-369">tax number</span></span>
  
<span data-ttu-id="96be3-370">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-370">tax id</span></span>
  
<span data-ttu-id="96be3-371">Numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="96be3-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="96be3-372">Alemanha</span><span class="sxs-lookup"><span data-stu-id="96be3-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="96be3-373">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-373">Format</span></span>

<span data-ttu-id="96be3-374">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-375">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-375">Pattern</span></span>

<span data-ttu-id="96be3-376">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="96be3-376">11 digits :</span></span>
  
-  <span data-ttu-id="96be3-377">Dez dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-377">Ten digits</span></span> 
    
- <span data-ttu-id="96be3-378">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-379">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-379">Checksum</span></span>

<span data-ttu-id="96be3-380">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-381">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-381">Definition</span></span>

<span data-ttu-id="96be3-382">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-383">A função `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-384">Uma palavra- `Keywords_germany_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-385">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-386">A função `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-387">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="96be3-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-389">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-389">tax number</span></span>
  
<span data-ttu-id="96be3-390">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-390">tax no.</span></span>
  
<span data-ttu-id="96be3-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-391">taxno#</span></span>
  
<span data-ttu-id="96be3-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-392">taxnumber#</span></span>
  
<span data-ttu-id="96be3-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="96be3-393">taxnumber</span></span>
  
<span data-ttu-id="96be3-394">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-394">tax id</span></span>
  
<span data-ttu-id="96be3-395">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-395">taxid#</span></span>
  
<span data-ttu-id="96be3-396">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-396">tax identification number</span></span>
  
<span data-ttu-id="96be3-397">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-397">tax identification no.</span></span>
  
<span data-ttu-id="96be3-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="96be3-398">steuernummer</span></span>
  
<span data-ttu-id="96be3-399">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="96be3-399">steuer id</span></span>
  
<span data-ttu-id="96be3-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="96be3-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="96be3-401">Grécia</span><span class="sxs-lookup"><span data-stu-id="96be3-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="96be3-402">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-402">Format</span></span>

<span data-ttu-id="96be3-403">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-404">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-404">Pattern</span></span>

<span data-ttu-id="96be3-405">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-406">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-406">Checksum</span></span>

<span data-ttu-id="96be3-407">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-408">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-408">Definition</span></span>

<span data-ttu-id="96be3-409">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-410">A expressão `Regex_greece_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-411">Uma palavra- `Keywords_greece_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-412">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="96be3-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-414">AFM</span><span class="sxs-lookup"><span data-stu-id="96be3-414">afm</span></span>
  
<span data-ttu-id="96be3-415">Tin</span><span class="sxs-lookup"><span data-stu-id="96be3-415">tin</span></span>
  
<span data-ttu-id="96be3-416">n º de ID de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-416">tax id no.</span></span>
  
<span data-ttu-id="96be3-417">ID de imposto não</span><span class="sxs-lookup"><span data-stu-id="96be3-417">tax id no</span></span>
  
<span data-ttu-id="96be3-418">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-418">tax identification number</span></span>
  
<span data-ttu-id="96be3-419">número do registro de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-419">tax registry number</span></span>
  
<span data-ttu-id="96be3-420">n º do registro de impostos</span><span class="sxs-lookup"><span data-stu-id="96be3-420">tax registry no.</span></span>
  
<span data-ttu-id="96be3-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="96be3-421">afm#</span></span>
  
<span data-ttu-id="96be3-422">Tin #</span><span class="sxs-lookup"><span data-stu-id="96be3-422">tin#</span></span>
  
<span data-ttu-id="96be3-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="96be3-423">taxidno#</span></span>
  
<span data-ttu-id="96be3-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="96be3-424">taxregistryno#</span></span>
  
<span data-ttu-id="96be3-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="96be3-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="96be3-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="96be3-426">aφμ</span></span>
  
<span data-ttu-id="96be3-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="96be3-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="96be3-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="96be3-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="96be3-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="96be3-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="96be3-430">Hungria</span><span class="sxs-lookup"><span data-stu-id="96be3-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="96be3-431">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-431">Format</span></span>

<span data-ttu-id="96be3-432">Dez dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-433">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-433">Pattern</span></span>

<span data-ttu-id="96be3-434">Dez dígitos:</span><span class="sxs-lookup"><span data-stu-id="96be3-434">Ten digits:</span></span>
  
-  <span data-ttu-id="96be3-435">Um dígito que deve ser "8"</span><span class="sxs-lookup"><span data-stu-id="96be3-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="96be3-436">Cinco dígitos que correspondem ao número de dias entre a data 01/01/1867 e a data do nascimento da pessoa</span><span class="sxs-lookup"><span data-stu-id="96be3-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="96be3-437">Três dígitos que correspondem ao número gerado pela chance de diferenciar as pessoas nasceu no mesmo dia</span><span class="sxs-lookup"><span data-stu-id="96be3-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="96be3-438">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-439">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-439">Checksum</span></span>

<span data-ttu-id="96be3-440">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-441">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-441">Definition</span></span>

<span data-ttu-id="96be3-442">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-443">A função `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-444">Uma palavra- `Keywords_hungary_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-445">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-446">A função `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-447">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="96be3-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-449">número de identificação do imposto húngaro</span><span class="sxs-lookup"><span data-stu-id="96be3-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="96be3-450">Tin húngaro</span><span class="sxs-lookup"><span data-stu-id="96be3-450">hungarian tin</span></span>
  
<span data-ttu-id="96be3-451">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-451">tax id number</span></span>
  
<span data-ttu-id="96be3-452">número de IVA</span><span class="sxs-lookup"><span data-stu-id="96be3-452">vat number</span></span>
  
<span data-ttu-id="96be3-453">autoridade de imposto não</span><span class="sxs-lookup"><span data-stu-id="96be3-453">tax authority no</span></span>
  
<span data-ttu-id="96be3-454">número de identidade do imposto ID do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-454">tax id tax identity number</span></span>
  
<span data-ttu-id="96be3-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-455">taxidnumber#</span></span>
  
<span data-ttu-id="96be3-456">Tin #</span><span class="sxs-lookup"><span data-stu-id="96be3-456">tin#</span></span>
  
<span data-ttu-id="96be3-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="96be3-457">hungatiantin#</span></span>
  
<span data-ttu-id="96be3-458">identificação de imposto não</span><span class="sxs-lookup"><span data-stu-id="96be3-458">tax identification no</span></span>
  
<span data-ttu-id="96be3-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="96be3-459">taxidno#</span></span>
  
<span data-ttu-id="96be3-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="96be3-460">adóazonosító szám</span></span>
  
<span data-ttu-id="96be3-461">adószám</span><span class="sxs-lookup"><span data-stu-id="96be3-461">adószám</span></span>
  
<span data-ttu-id="96be3-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="96be3-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="96be3-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="96be3-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="96be3-464">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-464">Format</span></span>

<span data-ttu-id="96be3-465">Sete dígitos seguidos de uma letra sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-466">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-466">Pattern</span></span>

<span data-ttu-id="96be3-467">Sete dígitos seguidos de uma letra:</span><span class="sxs-lookup"><span data-stu-id="96be3-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="96be3-468">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="96be3-468">Seven digits</span></span> 
    
- <span data-ttu-id="96be3-469">Uma letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-470">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-470">Checksum</span></span>

<span data-ttu-id="96be3-471">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-472">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-472">Definition</span></span>

<span data-ttu-id="96be3-473">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-474">A função `Func_ireland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-475">Uma palavra- `Keywords_ireland_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-476">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-477">A função `Func_ireland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-478">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="96be3-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-480">serviço público não</span><span class="sxs-lookup"><span data-stu-id="96be3-480">public service no</span></span>
  
<span data-ttu-id="96be3-481">serviço público pessoal não</span><span class="sxs-lookup"><span data-stu-id="96be3-481">personal public service no</span></span>
  
<span data-ttu-id="96be3-482">PPS não</span><span class="sxs-lookup"><span data-stu-id="96be3-482">pps no</span></span>
  
<span data-ttu-id="96be3-483">serviço pessoal não</span><span class="sxs-lookup"><span data-stu-id="96be3-483">personal service no</span></span>
  
<span data-ttu-id="96be3-484">serviço PPS não</span><span class="sxs-lookup"><span data-stu-id="96be3-484">pps service no</span></span>
  
<span data-ttu-id="96be3-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="96be3-485">ppsno#</span></span>
  
<span data-ttu-id="96be3-486">número do PPS do irlandês</span><span class="sxs-lookup"><span data-stu-id="96be3-486">irish pps no</span></span>
  
<span data-ttu-id="96be3-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="96be3-487">publicserviceno#</span></span>
  
<span data-ttu-id="96be3-488">número de serviço público pessoal</span><span class="sxs-lookup"><span data-stu-id="96be3-488">personal public service number</span></span>
  
<span data-ttu-id="96be3-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="96be3-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="96be3-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="96be3-490">pps uimh</span></span>
  
<span data-ttu-id="96be3-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="96be3-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="96be3-492">Itália</span><span class="sxs-lookup"><span data-stu-id="96be3-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="96be3-493">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-493">Format</span></span>

<span data-ttu-id="96be3-494">16 letras e dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="96be3-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-495">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-495">Pattern</span></span>

<span data-ttu-id="96be3-496">16 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="96be3-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="96be3-497">Três letras que correspondem às três primeiras consoantes no nome da família</span><span class="sxs-lookup"><span data-stu-id="96be3-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="96be3-498">Três letras que correspondem à primeira, terceira e quarta consoantes no primeiro nome</span><span class="sxs-lookup"><span data-stu-id="96be3-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="96be3-499">Dois dígitos que correspondem aos últimos dígitos do ano de nascimento</span><span class="sxs-lookup"><span data-stu-id="96be3-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="96be3-500">Um dígito que corresponde ao mês de nascimento-as letras são usadas em ordem alfabética, mas apenas as letras de a a E, H, L, M, P, R a T são usadas (portanto, Janeiro é A e outubro é R)</span><span class="sxs-lookup"><span data-stu-id="96be3-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="96be3-501">Dois dígitos que correspondem ao dia do mês de nascimento, onde 40 é adicionado ao dia de nascimento de mulheres para diferenciar da homens</span><span class="sxs-lookup"><span data-stu-id="96be3-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="96be3-502">Quatro dígitos que correspondem a um código de área específico para o município onde a pessoa nasceu — códigos em todo o país são usados para países estrangeiros</span><span class="sxs-lookup"><span data-stu-id="96be3-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="96be3-503">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-504">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-504">Checksum</span></span>

<span data-ttu-id="96be3-505">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-506">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-506">Definition</span></span>

<span data-ttu-id="96be3-507">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-508">A função `Func_italy_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-509">Uma palavra- `Keywords_italy_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-510">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-511">A função `Func_italy_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-512">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="96be3-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-514">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-514">tax number</span></span>
  
<span data-ttu-id="96be3-515">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-515">tax no.</span></span>
  
<span data-ttu-id="96be3-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-516">taxno#</span></span>
  
<span data-ttu-id="96be3-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-517">taxnumber#</span></span>
  
<span data-ttu-id="96be3-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="96be3-518">taxnumber</span></span>
  
<span data-ttu-id="96be3-519">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-519">tax id</span></span>
  
<span data-ttu-id="96be3-520">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-520">taxid#</span></span>
  
<span data-ttu-id="96be3-521">código fiscal</span><span class="sxs-lookup"><span data-stu-id="96be3-521">fiscal code</span></span>
  
<span data-ttu-id="96be3-522">fiscalização codice</span><span class="sxs-lookup"><span data-stu-id="96be3-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="96be3-523">Letônia</span><span class="sxs-lookup"><span data-stu-id="96be3-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="96be3-524">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-524">Format</span></span>

<span data-ttu-id="96be3-525">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-526">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-526">Pattern</span></span>

<span data-ttu-id="96be3-527">11 dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="96be3-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="96be3-528">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="96be3-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="96be3-529">Um dígito que corresponde ao século de nascimento onde "0" corresponde ao século 19, "1" corresponde a 20 Century e "2" corresponde ao século 21</span><span class="sxs-lookup"><span data-stu-id="96be3-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="96be3-530">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-531">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-531">Checksum</span></span>

<span data-ttu-id="96be3-532">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-533">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-533">Definition</span></span>

<span data-ttu-id="96be3-534">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-535">A função `Func_latvia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-536">Uma palavra- `Keywords_latvia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-537">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-538">A função `Func_latvia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-539">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="96be3-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-541">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-541">tax number</span></span>
  
<span data-ttu-id="96be3-542">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-542">tax no.</span></span>
  
<span data-ttu-id="96be3-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-543">taxno#</span></span>
  
<span data-ttu-id="96be3-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-544">taxnumber#</span></span>
  
<span data-ttu-id="96be3-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="96be3-545">taxnumber</span></span>
  
<span data-ttu-id="96be3-546">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-546">tax id</span></span>
  
<span data-ttu-id="96be3-547">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-547">taxid#</span></span>
  
<span data-ttu-id="96be3-548">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-548">tax identification number</span></span>
  
<span data-ttu-id="96be3-549">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-549">tax identification no.</span></span>
  
<span data-ttu-id="96be3-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="96be3-550">nodokļa numurs</span></span>
  
<span data-ttu-id="96be3-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="96be3-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="96be3-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="96be3-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="96be3-553">Lituânia</span><span class="sxs-lookup"><span data-stu-id="96be3-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="96be3-554">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-554">Format</span></span>

<span data-ttu-id="96be3-555">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-556">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-556">Pattern</span></span>

<span data-ttu-id="96be3-557">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-558">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-558">Checksum</span></span>

<span data-ttu-id="96be3-559">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-560">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-560">Definition</span></span>

<span data-ttu-id="96be3-561">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-562">A função `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-563">Uma palavra- `Keywords_lithuania_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-564">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-565">A função `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-566">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="96be3-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-568">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-568">tax number</span></span>
  
<span data-ttu-id="96be3-569">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-569">tax no.</span></span>
  
<span data-ttu-id="96be3-570">n º do imposto #</span><span class="sxs-lookup"><span data-stu-id="96be3-570">tax no#</span></span>
  
<span data-ttu-id="96be3-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-571">taxnumber#</span></span>
  
<span data-ttu-id="96be3-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="96be3-572">taxnumber</span></span>
  
<span data-ttu-id="96be3-573">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-573">tax id</span></span>
  
<span data-ttu-id="96be3-574">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-574">taxid#</span></span>
  
<span data-ttu-id="96be3-575">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-575">tax identification number</span></span>
  
<span data-ttu-id="96be3-576">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-576">tax identification no.</span></span>
  
<span data-ttu-id="96be3-577">ID mokesčių</span><span class="sxs-lookup"><span data-stu-id="96be3-577">mokesčių id</span></span>
  
<span data-ttu-id="96be3-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="96be3-578">mokesčių numeris</span></span>
  
<span data-ttu-id="96be3-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="96be3-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="96be3-580">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="96be3-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="96be3-581">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-581">Format</span></span>

<span data-ttu-id="96be3-582">13 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-583">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-583">Pattern</span></span>

<span data-ttu-id="96be3-584">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="96be3-584">13 digits:</span></span>
  
-  <span data-ttu-id="96be3-585">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-585">11 digits</span></span> 
    
- <span data-ttu-id="96be3-586">Dois dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-587">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-587">Checksum</span></span>

<span data-ttu-id="96be3-588">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-589">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-589">Definition</span></span>

<span data-ttu-id="96be3-590">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-591">A função `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-592">Uma palavra- `Keywords_luxemburg_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-593">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-594">A função `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-595">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="96be3-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-597">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-597">tax number</span></span>
  
<span data-ttu-id="96be3-598">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-598">tax no.</span></span>
  
<span data-ttu-id="96be3-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-599">taxno#</span></span>
  
<span data-ttu-id="96be3-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-600">taxnumber#</span></span>
  
<span data-ttu-id="96be3-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="96be3-601">taxnumber</span></span>
  
<span data-ttu-id="96be3-602">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-602">tax id</span></span>
  
<span data-ttu-id="96be3-603">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-603">taxid#</span></span>
  
<span data-ttu-id="96be3-604">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-604">tax identification number</span></span>
  
<span data-ttu-id="96be3-605">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-605">tax identification no.</span></span>
  
<span data-ttu-id="96be3-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="96be3-606">steuernummer</span></span>
  
<span data-ttu-id="96be3-607">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="96be3-607">steuer id</span></span>
  
<span data-ttu-id="96be3-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="96be3-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="96be3-609">Malta</span><span class="sxs-lookup"><span data-stu-id="96be3-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="96be3-610">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-610">Format</span></span>

<span data-ttu-id="96be3-611">Para as nacionalidades maltês: 7 dígitos e uma letra no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="96be3-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="96be3-612">Entidades nacionais e Maltês não-maltês: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-613">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-613">Pattern</span></span>

<span data-ttu-id="96be3-614">Nacionalidades maltês: 7 dígitos e uma letra</span><span class="sxs-lookup"><span data-stu-id="96be3-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="96be3-615">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="96be3-615">Seven digits</span></span> 
    
- <span data-ttu-id="96be3-616">Uma letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="96be3-617">Entidades nacionais e Maltês não-maltês: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="96be3-618">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="96be3-619">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-619">Checksum</span></span>

<span data-ttu-id="96be3-620">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-621">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-621">Definition</span></span>

<span data-ttu-id="96be3-622">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-623">A função `Func_malta_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-624">Uma palavra- `Keywords_malta_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-625">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-626">A função `Func_malta_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-627">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="96be3-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-629">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-629">tax number</span></span>
  
<span data-ttu-id="96be3-630">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-630">tax no.</span></span>
  
<span data-ttu-id="96be3-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-631">taxno#</span></span>
  
<span data-ttu-id="96be3-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-632">taxnumber#</span></span>
  
<span data-ttu-id="96be3-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="96be3-633">taxnumber</span></span>
  
<span data-ttu-id="96be3-634">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-634">tax id</span></span>
  
<span data-ttu-id="96be3-635">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-635">taxid#</span></span>
  
<span data-ttu-id="96be3-636">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-636">tax identification number</span></span>
  
<span data-ttu-id="96be3-637">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-637">tax identification no.</span></span>
  
<span data-ttu-id="96be3-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="96be3-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="96be3-639">ID tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="96be3-639">id tat-taxxa</span></span>
  
<span data-ttu-id="96be3-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="96be3-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="96be3-641">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="96be3-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="96be3-642">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-642">Format</span></span>

<span data-ttu-id="96be3-643">Nove dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-644">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-644">Pattern</span></span>

<span data-ttu-id="96be3-645">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="96be3-646">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-646">Checksum</span></span>

<span data-ttu-id="96be3-647">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-648">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-648">Definition</span></span>

<span data-ttu-id="96be3-649">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-650">A função `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-651">Uma palavra- `Keywords_netherlands_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-652">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-653">A função `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-654">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="96be3-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-656">número de identificação do imposto Holanda</span><span class="sxs-lookup"><span data-stu-id="96be3-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="96be3-657">identificação de imposto Holanda</span><span class="sxs-lookup"><span data-stu-id="96be3-657">netherlands tax identification</span></span>
  
<span data-ttu-id="96be3-658">número de identificação de imposto do Netherland</span><span class="sxs-lookup"><span data-stu-id="96be3-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="96be3-659">identificação de imposto do Netherland</span><span class="sxs-lookup"><span data-stu-id="96be3-659">netherland's tax identification</span></span>
  
<span data-ttu-id="96be3-660">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-660">tax identification number</span></span>
  
<span data-ttu-id="96be3-661">ID de imposto holandês</span><span class="sxs-lookup"><span data-stu-id="96be3-661">dutch tax id</span></span>
  
<span data-ttu-id="96be3-662">número de identificação do imposto holandês</span><span class="sxs-lookup"><span data-stu-id="96be3-662">dutch tax identification number</span></span>
  
<span data-ttu-id="96be3-663">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-663">tax id</span></span>
  
<span data-ttu-id="96be3-664">ID de imposto #</span><span class="sxs-lookup"><span data-stu-id="96be3-664">tax id#</span></span>
  
<span data-ttu-id="96be3-665">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-665">tax number</span></span>
  
<span data-ttu-id="96be3-666">n º do imposto #</span><span class="sxs-lookup"><span data-stu-id="96be3-666">tax no#</span></span>
  
<span data-ttu-id="96be3-667">imposto #</span><span class="sxs-lookup"><span data-stu-id="96be3-667">tax#</span></span>
  
<span data-ttu-id="96be3-668">Tin</span><span class="sxs-lookup"><span data-stu-id="96be3-668">tin</span></span>
  
<span data-ttu-id="96be3-669">Tin #</span><span class="sxs-lookup"><span data-stu-id="96be3-669">tin#</span></span>
  
<span data-ttu-id="96be3-670">Tin Holanda</span><span class="sxs-lookup"><span data-stu-id="96be3-670">netherlands tin</span></span>
  
<span data-ttu-id="96be3-671">Tin do Netherland</span><span class="sxs-lookup"><span data-stu-id="96be3-671">netherland's tin</span></span>
  
<span data-ttu-id="96be3-672">Países Baixos identificatienummer</span><span class="sxs-lookup"><span data-stu-id="96be3-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="96be3-673">identificatienummer Van é última</span><span class="sxs-lookup"><span data-stu-id="96be3-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="96be3-674">identificatienummer a última</span><span class="sxs-lookup"><span data-stu-id="96be3-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="96be3-675">Países Baixos identificatie</span><span class="sxs-lookup"><span data-stu-id="96be3-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="96be3-676">Países Baixos Nummer ID da última vez</span><span class="sxs-lookup"><span data-stu-id="96be3-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="96be3-677">Países Baixos belastingnummer</span><span class="sxs-lookup"><span data-stu-id="96be3-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="96be3-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="96be3-678">btw nummer</span></span>
  
<span data-ttu-id="96be3-679">Nederlandse identificatie</span><span class="sxs-lookup"><span data-stu-id="96be3-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="96be3-680">Polônia</span><span class="sxs-lookup"><span data-stu-id="96be3-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="96be3-681">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-681">Format</span></span>

<span data-ttu-id="96be3-682">Onze dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-683">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-683">Pattern</span></span>

<span data-ttu-id="96be3-684">Onze dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-685">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-685">Checksum</span></span>

<span data-ttu-id="96be3-686">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-687">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-687">Definition</span></span>

<span data-ttu-id="96be3-688">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-689">A função `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-690">Uma palavra- `Keywords_poland_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-691">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-692">A função `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-693">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="96be3-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-695">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-695">tax number</span></span>
  
<span data-ttu-id="96be3-696">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-696">tax no.</span></span>
  
<span data-ttu-id="96be3-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-697">taxno#</span></span>
  
<span data-ttu-id="96be3-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-698">taxnumber#</span></span>
  
<span data-ttu-id="96be3-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="96be3-699">taxnumber</span></span>
  
<span data-ttu-id="96be3-700">nip</span><span class="sxs-lookup"><span data-stu-id="96be3-700">nip</span></span>
  
<span data-ttu-id="96be3-701">nip #</span><span class="sxs-lookup"><span data-stu-id="96be3-701">nip#</span></span>
  
<span data-ttu-id="96be3-702">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-702">tax id</span></span>
  
<span data-ttu-id="96be3-703">ID de imposto #</span><span class="sxs-lookup"><span data-stu-id="96be3-703">tax id#</span></span>
  
<span data-ttu-id="96be3-704">ID Nip</span><span class="sxs-lookup"><span data-stu-id="96be3-704">nip id</span></span>
  
<span data-ttu-id="96be3-705">ID Nip #</span><span class="sxs-lookup"><span data-stu-id="96be3-705">nip id#</span></span>
  
<span data-ttu-id="96be3-706">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-706">tax identification number</span></span>
  
<span data-ttu-id="96be3-707">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-707">tax identification no.</span></span>
  
<span data-ttu-id="96be3-708">número de IVA</span><span class="sxs-lookup"><span data-stu-id="96be3-708">vat number</span></span>
  
<span data-ttu-id="96be3-709">IVA não.</span><span class="sxs-lookup"><span data-stu-id="96be3-709">vat no.</span></span>
  
<span data-ttu-id="96be3-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="96be3-710">vatno#</span></span>
  
<span data-ttu-id="96be3-711">ID de IVA</span><span class="sxs-lookup"><span data-stu-id="96be3-711">vat id</span></span>
  
<span data-ttu-id="96be3-712">ID de IVA #</span><span class="sxs-lookup"><span data-stu-id="96be3-712">vat id#</span></span>
  
<span data-ttu-id="96be3-713">numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="96be3-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="96be3-714">polski numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="96be3-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="96be3-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="96be3-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="96be3-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="96be3-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="96be3-717">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-717">Format</span></span>

<span data-ttu-id="96be3-718">Nove dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-719">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-719">Pattern</span></span>

<span data-ttu-id="96be3-720">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-721">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-721">Checksum</span></span>

<span data-ttu-id="96be3-722">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-723">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-723">Definition</span></span>

<span data-ttu-id="96be3-724">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-725">A função `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-726">Uma palavra- `Keywords_portugal_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-727">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-728">A função `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-729">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="96be3-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-731">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-731">tax number</span></span>
  
<span data-ttu-id="96be3-732">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-732">tax no.</span></span>
  
<span data-ttu-id="96be3-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-733">taxno#</span></span>
  
<span data-ttu-id="96be3-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="96be3-734">taxnumber#</span></span>
  
<span data-ttu-id="96be3-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="96be3-735">taxnumber</span></span>
  
<span data-ttu-id="96be3-736">nse</span><span class="sxs-lookup"><span data-stu-id="96be3-736">nif</span></span>
  
<span data-ttu-id="96be3-737">nse #</span><span class="sxs-lookup"><span data-stu-id="96be3-737">nif#</span></span>
  
<span data-ttu-id="96be3-738">fiscal numero</span><span class="sxs-lookup"><span data-stu-id="96be3-738">numero fiscal</span></span>
  
<span data-ttu-id="96be3-739">número de identificação fiscal</span><span class="sxs-lookup"><span data-stu-id="96be3-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="96be3-740">Romênia</span><span class="sxs-lookup"><span data-stu-id="96be3-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="96be3-741">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-741">Format</span></span>

<span data-ttu-id="96be3-742">13 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-743">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-743">Pattern</span></span>

<span data-ttu-id="96be3-744">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-745">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-745">Checksum</span></span>

<span data-ttu-id="96be3-746">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-747">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-747">Definition</span></span>

<span data-ttu-id="96be3-748">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-749">A expressão `Regex_romania_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-750">Uma palavra- `Keywords_romania_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-751">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="96be3-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-753">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-753">tax id</span></span>
  
<span data-ttu-id="96be3-754">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-754">tax id number</span></span>
  
<span data-ttu-id="96be3-755">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="96be3-755">tax file no</span></span>
  
<span data-ttu-id="96be3-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="96be3-756">tax file number</span></span>
  
<span data-ttu-id="96be3-757">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-757">tax no</span></span>
  
<span data-ttu-id="96be3-758">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-758">tax number</span></span>
  
<span data-ttu-id="96be3-759">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-759">taxid#</span></span>
  
<span data-ttu-id="96be3-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-760">taxno#</span></span>
  
<span data-ttu-id="96be3-761">ID-UL Taxei</span><span class="sxs-lookup"><span data-stu-id="96be3-761">id-ul taxei</span></span>
  
<span data-ttu-id="96be3-762">numărul de identificare Fiscală</span><span class="sxs-lookup"><span data-stu-id="96be3-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="96be3-763">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="96be3-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="96be3-764">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-764">Format</span></span>

<span data-ttu-id="96be3-765">10 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-766">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-766">Pattern</span></span>

<span data-ttu-id="96be3-767">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-768">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-768">Checksum</span></span>

<span data-ttu-id="96be3-769">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="96be3-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-770">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-770">Definition</span></span>

<span data-ttu-id="96be3-771">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-772">A expressão `Regex_slovakia_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-773">Uma palavra- `Keywords_slovakia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-774">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="96be3-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-776">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-776">tax id</span></span>
  
<span data-ttu-id="96be3-777">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-777">tax id number</span></span>
  
<span data-ttu-id="96be3-778">ID do Tin</span><span class="sxs-lookup"><span data-stu-id="96be3-778">tin id</span></span>
  
<span data-ttu-id="96be3-779">Tin não</span><span class="sxs-lookup"><span data-stu-id="96be3-779">tin no</span></span>
  
<span data-ttu-id="96be3-780">ID de Tin de eslovaco</span><span class="sxs-lookup"><span data-stu-id="96be3-780">slovakian tin id</span></span>
  
<span data-ttu-id="96be3-781">Tin</span><span class="sxs-lookup"><span data-stu-id="96be3-781">tin</span></span>
  
<span data-ttu-id="96be3-782">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="96be3-782">tax file no</span></span>
  
<span data-ttu-id="96be3-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="96be3-783">tax file number</span></span>
  
<span data-ttu-id="96be3-784">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-784">tax no</span></span>
  
<span data-ttu-id="96be3-785">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-785">tax number</span></span>
  
<span data-ttu-id="96be3-786">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-786">taxid#</span></span>
  
<span data-ttu-id="96be3-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-787">taxno#</span></span>
  
<span data-ttu-id="96be3-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="96be3-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="96be3-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="96be3-789">daňové číslo</span></span>
  
<span data-ttu-id="96be3-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="96be3-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="96be3-791">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="96be3-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="96be3-792">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-792">Format</span></span>

<span data-ttu-id="96be3-793">Oito dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-794">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-794">Pattern</span></span>

<span data-ttu-id="96be3-795">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-796">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-796">Checksum</span></span>

<span data-ttu-id="96be3-797">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-798">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-798">Definition</span></span>

<span data-ttu-id="96be3-799">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-800">A função `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-801">Uma palavra- `Keywords_slovenia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-802">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-803">A função `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-804">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="96be3-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-806">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-806">tax id</span></span>
  
<span data-ttu-id="96be3-807">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-807">tax id number</span></span>
  
<span data-ttu-id="96be3-808">ID do Tin</span><span class="sxs-lookup"><span data-stu-id="96be3-808">tin id</span></span>
  
<span data-ttu-id="96be3-809">Tin não</span><span class="sxs-lookup"><span data-stu-id="96be3-809">tin no</span></span>
  
<span data-ttu-id="96be3-810">ID de Tin esloveno</span><span class="sxs-lookup"><span data-stu-id="96be3-810">slovenian tin id</span></span>
  
<span data-ttu-id="96be3-811">Tin</span><span class="sxs-lookup"><span data-stu-id="96be3-811">tin</span></span>
  
<span data-ttu-id="96be3-812">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="96be3-812">tax file no</span></span>
  
<span data-ttu-id="96be3-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="96be3-813">tax file number</span></span>
  
<span data-ttu-id="96be3-814">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-814">tax no</span></span>
  
<span data-ttu-id="96be3-815">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-815">tax number</span></span>
  
<span data-ttu-id="96be3-816">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-816">taxid#</span></span>
  
<span data-ttu-id="96be3-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-817">taxno#</span></span>
  
<span data-ttu-id="96be3-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="96be3-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="96be3-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="96be3-819">davčna številka</span></span>
  
<span data-ttu-id="96be3-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="96be3-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="96be3-821">Espanha</span><span class="sxs-lookup"><span data-stu-id="96be3-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="96be3-822">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-822">Format</span></span>

<span data-ttu-id="96be3-823">Sete ou oito dígitos e uma ou duas letras no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="96be3-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-824">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-824">Pattern</span></span>

<span data-ttu-id="96be3-825">Pessoas naturais do espanhol com um cartão de identidade nacional da Espanha:</span><span class="sxs-lookup"><span data-stu-id="96be3-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="96be3-826">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-826">Eight digits</span></span> 
    
- <span data-ttu-id="96be3-827">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="96be3-828">Spaniards não residente sem um cartão de identidade nacional da Espanha</span><span class="sxs-lookup"><span data-stu-id="96be3-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="96be3-829">Uma letra maiúscula "L" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="96be3-830">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="96be3-830">Seven digits</span></span>
    
- <span data-ttu-id="96be3-831">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="96be3-832">Spaniards residentes sob a idade de 14 anos sem um cartão de identidade nacional da Espanha:</span><span class="sxs-lookup"><span data-stu-id="96be3-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="96be3-833">Uma letra maiúscula "K" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="96be3-834">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="96be3-834">Seven digits</span></span> 
    
- <span data-ttu-id="96be3-835">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="96be3-836">Foreigners com o número de identificação do estrangeiro</span><span class="sxs-lookup"><span data-stu-id="96be3-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="96be3-837">Uma letra maiúscula que é "X", "Y" ou "Z" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="96be3-838">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="96be3-838">Seven digits</span></span>
    
- <span data-ttu-id="96be3-839">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="96be3-840">Foreigners sem um número de identificação do estrangeiro</span><span class="sxs-lookup"><span data-stu-id="96be3-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="96be3-841">Uma letra maiúscula que é "M" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="96be3-842">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="96be3-842">Seven digits</span></span>
    
- <span data-ttu-id="96be3-843">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="96be3-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="96be3-844">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-844">Checksum</span></span>

<span data-ttu-id="96be3-845">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-846">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-846">Definition</span></span>

<span data-ttu-id="96be3-847">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-848">A função `Func_spain_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-849">Uma palavra- `Keywords_spain_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-850">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-851">A função `Func_spain_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-852">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="96be3-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-854">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-854">tax id</span></span>
  
<span data-ttu-id="96be3-855">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-855">tax id number</span></span>
  
<span data-ttu-id="96be3-856">ID de CIF</span><span class="sxs-lookup"><span data-stu-id="96be3-856">cif id</span></span>
  
<span data-ttu-id="96be3-857">Não CIF</span><span class="sxs-lookup"><span data-stu-id="96be3-857">cif no</span></span>
  
<span data-ttu-id="96be3-858">ID de CIF espanhol</span><span class="sxs-lookup"><span data-stu-id="96be3-858">spanish cif id</span></span>
  
<span data-ttu-id="96be3-859">CIF</span><span class="sxs-lookup"><span data-stu-id="96be3-859">cif</span></span>
  
<span data-ttu-id="96be3-860">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="96be3-860">tax file no</span></span>
  
<span data-ttu-id="96be3-861">número de CIF espanhol</span><span class="sxs-lookup"><span data-stu-id="96be3-861">spanish cif number</span></span>
  
<span data-ttu-id="96be3-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="96be3-862">tax file number</span></span>
  
<span data-ttu-id="96be3-863">Não CIF espanhol</span><span class="sxs-lookup"><span data-stu-id="96be3-863">spanish cif no</span></span>
  
<span data-ttu-id="96be3-864">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-864">tax no</span></span>
  
<span data-ttu-id="96be3-865">número do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-865">tax number</span></span>
  
<span data-ttu-id="96be3-866">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-866">taxid#</span></span>
  
<span data-ttu-id="96be3-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="96be3-867">taxno#</span></span>
  
<span data-ttu-id="96be3-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="96be3-868">cifid#</span></span>
  
<span data-ttu-id="96be3-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="96be3-869">spanishcifid#</span></span>
  
<span data-ttu-id="96be3-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="96be3-870">spanishcifno#</span></span>
  
<span data-ttu-id="96be3-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="96be3-871">número de contribuyente</span></span>
  
<span data-ttu-id="96be3-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="96be3-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="96be3-873">número de Identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="96be3-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="96be3-874">número CIF</span><span class="sxs-lookup"><span data-stu-id="96be3-874">cif número</span></span>
  
<span data-ttu-id="96be3-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="96be3-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="96be3-876">Suécia</span><span class="sxs-lookup"><span data-stu-id="96be3-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="96be3-877">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-877">Format</span></span>

<span data-ttu-id="96be3-878">Dez dígitos e um símbolo no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="96be3-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-879">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-879">Pattern</span></span>

<span data-ttu-id="96be3-880">Dez dígitos e um símbolo:</span><span class="sxs-lookup"><span data-stu-id="96be3-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="96be3-881">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="96be3-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="96be3-882">Um sinal de adição, sinal de menos ou barra invertida</span><span class="sxs-lookup"><span data-stu-id="96be3-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="96be3-883">Três dígitos que tornam o número de identificação exclusivo, onde:</span><span class="sxs-lookup"><span data-stu-id="96be3-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="96be3-884">Para números emitidos antes de 1990, o sétimo e oitavo dígito identificam o Condado de nascimento ou pessoas de nasceu</span><span class="sxs-lookup"><span data-stu-id="96be3-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="96be3-885">O dígito na nona posição indica sexo por tanto ímpar para masculino ou par para fêmea</span><span class="sxs-lookup"><span data-stu-id="96be3-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="96be3-886">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="96be3-887">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-887">Checksum</span></span>

<span data-ttu-id="96be3-888">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-889">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-889">Definition</span></span>

<span data-ttu-id="96be3-890">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-891">A função `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-892">Uma palavra- `Keywords_sweden_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="96be3-893">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-894">A função `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-895">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="96be3-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-897">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-897">tax id</span></span>
  
<span data-ttu-id="96be3-898">n º de ID de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-898">tax id no.</span></span>
  
<span data-ttu-id="96be3-899">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-899">tax id number</span></span>
  
<span data-ttu-id="96be3-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="96be3-900">tax identification</span></span>
  
<span data-ttu-id="96be3-901">identificação de imposto #</span><span class="sxs-lookup"><span data-stu-id="96be3-901">tax identification#</span></span>
  
<span data-ttu-id="96be3-902">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-902">tax no.</span></span>
  
<span data-ttu-id="96be3-903">imposto #</span><span class="sxs-lookup"><span data-stu-id="96be3-903">tax#</span></span>
  
<span data-ttu-id="96be3-904">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-904">taxid#</span></span>
  
<span data-ttu-id="96be3-905">arquivo de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-905">tax file</span></span>
  
<span data-ttu-id="96be3-906">arquivo de impostos não.</span><span class="sxs-lookup"><span data-stu-id="96be3-906">tax file no.</span></span>
  
<span data-ttu-id="96be3-907">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="96be3-907">personal id number</span></span>
  
<span data-ttu-id="96be3-908">skatt ID Nummer</span><span class="sxs-lookup"><span data-stu-id="96be3-908">skatt id nummer</span></span>
  
<span data-ttu-id="96be3-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="96be3-909">skatt identifikation</span></span>
  
<span data-ttu-id="96be3-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="96be3-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="96be3-911">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="96be3-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="96be3-912">Formatar</span><span class="sxs-lookup"><span data-stu-id="96be3-912">Format</span></span>

<span data-ttu-id="96be3-913">Referência de contribuidor exclusivo (UTR): 10 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="96be3-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="96be3-914">Número de seguro nacional (NINO): para obter detalhes, consulte a seção "Reino Unido</span><span class="sxs-lookup"><span data-stu-id="96be3-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="96be3-915">Número de seguro nacional (NINO) "em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="96be3-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="96be3-916">Padrão</span><span class="sxs-lookup"><span data-stu-id="96be3-916">Pattern</span></span>

<span data-ttu-id="96be3-917">Referência de contribuidor exclusivo (UTR): 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="96be3-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="96be3-918">Número de seguro nacional (NINO): para obter detalhes, consulte a seção "Reino Unido</span><span class="sxs-lookup"><span data-stu-id="96be3-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="96be3-919">Número de seguro nacional (NINO) "em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="96be3-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="96be3-920">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="96be3-920">Checksum</span></span>

<span data-ttu-id="96be3-921">Sim</span><span class="sxs-lookup"><span data-stu-id="96be3-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="96be3-922">Definição</span><span class="sxs-lookup"><span data-stu-id="96be3-922">Definition</span></span>

<span data-ttu-id="96be3-923">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="96be3-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="96be3-924">A função `Func_uk_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="96be3-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="96be3-925">Uma palavra- `Keywords_uk_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="96be3-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="96be3-926">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="96be3-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="96be3-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="96be3-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="96be3-928">tax id</span><span class="sxs-lookup"><span data-stu-id="96be3-928">tax id</span></span>
  
<span data-ttu-id="96be3-929">n º de ID de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-929">tax id no.</span></span>
  
<span data-ttu-id="96be3-930">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-930">tax id number</span></span>
  
<span data-ttu-id="96be3-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="96be3-931">tax identification</span></span>
  
<span data-ttu-id="96be3-932">identificação de imposto #</span><span class="sxs-lookup"><span data-stu-id="96be3-932">tax identification#</span></span>
  
<span data-ttu-id="96be3-933">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-933">tax no.</span></span>
  
<span data-ttu-id="96be3-934">imposto #</span><span class="sxs-lookup"><span data-stu-id="96be3-934">tax#</span></span>
  
<span data-ttu-id="96be3-935">táxi #</span><span class="sxs-lookup"><span data-stu-id="96be3-935">taxid#</span></span>
  
<span data-ttu-id="96be3-936">arquivo de imposto</span><span class="sxs-lookup"><span data-stu-id="96be3-936">tax file</span></span>
  
<span data-ttu-id="96be3-937">arquivo de impostos não.</span><span class="sxs-lookup"><span data-stu-id="96be3-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96be3-938">Confira também</span><span class="sxs-lookup"><span data-stu-id="96be3-938">See also</span></span>

[<span data-ttu-id="96be3-939">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="96be3-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

