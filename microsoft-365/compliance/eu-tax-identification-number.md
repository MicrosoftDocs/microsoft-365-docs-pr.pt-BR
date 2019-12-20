---
title: Número de identificação do imposto da UE
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
ms.openlocfilehash: 0ee76fa46bb22b2754098d053ab769b862fdd3f2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805844"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="2e583-104">Número de identificação do imposto da UE</span><span class="sxs-lookup"><span data-stu-id="2e583-104">EU Tax Identification Number</span></span>

<span data-ttu-id="2e583-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação de imposto (TIN) da UE.</span><span class="sxs-lookup"><span data-stu-id="2e583-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="2e583-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="2e583-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="2e583-107">Áustria</span><span class="sxs-lookup"><span data-stu-id="2e583-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="2e583-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-108">Format</span></span>

<span data-ttu-id="2e583-109">Nove dígitos com hífen opcional e barra para frente</span><span class="sxs-lookup"><span data-stu-id="2e583-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-110">Pattern</span></span>

<span data-ttu-id="2e583-111">Nove dígitos com hífen opcional e barra para frente:</span><span class="sxs-lookup"><span data-stu-id="2e583-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="2e583-112">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-112">Two digits</span></span> 
    
- <span data-ttu-id="2e583-113">Um hífen (opcional)</span><span class="sxs-lookup"><span data-stu-id="2e583-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="2e583-114">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-114">Three digits</span></span>
    
- <span data-ttu-id="2e583-115">Uma barra (opcional)</span><span class="sxs-lookup"><span data-stu-id="2e583-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="2e583-116">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-117">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-117">Checksum</span></span>

<span data-ttu-id="2e583-118">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-119">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-119">Definition</span></span>

<span data-ttu-id="2e583-120">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-121">A função `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-122">Uma palavra- `Keywords_austria_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-123">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-124">A função `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-125">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="2e583-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-127">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-127">tax number</span></span>
  
<span data-ttu-id="2e583-128">number</span><span class="sxs-lookup"><span data-stu-id="2e583-128">number</span></span>
  
<span data-ttu-id="2e583-129">número de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-129">tax registration number</span></span>
  
<span data-ttu-id="2e583-130">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-130">tax id</span></span>
  
<span data-ttu-id="2e583-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="2e583-131">st.nr.</span></span>
  
<span data-ttu-id="2e583-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="2e583-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="2e583-133">Bélgica</span><span class="sxs-lookup"><span data-stu-id="2e583-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="2e583-134">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-134">Format</span></span>

<span data-ttu-id="2e583-135">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-136">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-136">Pattern</span></span>

<span data-ttu-id="2e583-137">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e583-137">11 digits:</span></span>
  
- <span data-ttu-id="2e583-138">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-138">Two digits</span></span>
    
- <span data-ttu-id="2e583-139">Um "0" ou "1"</span><span class="sxs-lookup"><span data-stu-id="2e583-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="2e583-140">Um dígito</span><span class="sxs-lookup"><span data-stu-id="2e583-140">One digit</span></span>
    
- <span data-ttu-id="2e583-141">"0" ou "1" ou "2" ou "3"</span><span class="sxs-lookup"><span data-stu-id="2e583-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="2e583-142">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-143">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-143">Checksum</span></span>

<span data-ttu-id="2e583-144">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-145">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-145">Definition</span></span>

<span data-ttu-id="2e583-146">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-147">A expressão `Regex_belgium_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-148">Uma palavra- `Keywords_belgium_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e583-149">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="2e583-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-151">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-151">tax number</span></span>
  
<span data-ttu-id="2e583-152">número de Registro Nacional</span><span class="sxs-lookup"><span data-stu-id="2e583-152">national registration number</span></span>
  
<span data-ttu-id="2e583-153">número de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-153">tax registration number</span></span>
  
<span data-ttu-id="2e583-154">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-154">tax id</span></span>
  
<span data-ttu-id="2e583-155">nse</span><span class="sxs-lookup"><span data-stu-id="2e583-155">nif</span></span>
  
<span data-ttu-id="2e583-156">nse #</span><span class="sxs-lookup"><span data-stu-id="2e583-156">nif#</span></span>
  
<span data-ttu-id="2e583-157">Numéro de Registro Nacional</span><span class="sxs-lookup"><span data-stu-id="2e583-157">numéro de registre national</span></span>
  
<span data-ttu-id="2e583-158">Numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="2e583-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="2e583-159">Bulgária</span><span class="sxs-lookup"><span data-stu-id="2e583-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="2e583-160">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-160">Format</span></span>

<span data-ttu-id="2e583-161">Dez dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-162">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-162">Pattern</span></span>

<span data-ttu-id="2e583-163">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-164">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-164">Checksum</span></span>

<span data-ttu-id="2e583-165">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-166">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-166">Definition</span></span>

<span data-ttu-id="2e583-167">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-168">A função `Func_bulgaria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-169">Uma palavra- `Keywords_bulgaria_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-170">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-171">A função `Func_bulgaria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-172">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="2e583-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-174">bucn</span><span class="sxs-lookup"><span data-stu-id="2e583-174">bucn</span></span>
  
<span data-ttu-id="2e583-175">número civil uniforme</span><span class="sxs-lookup"><span data-stu-id="2e583-175">uniform civil number</span></span>
  
<span data-ttu-id="2e583-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="2e583-176">bucn#</span></span>
  
<span data-ttu-id="2e583-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="2e583-178">ID civil uniforme</span><span class="sxs-lookup"><span data-stu-id="2e583-178">uniform civil id</span></span>
  
<span data-ttu-id="2e583-179">Nenhum civil uniforme</span><span class="sxs-lookup"><span data-stu-id="2e583-179">uniform civil no</span></span>
  
<span data-ttu-id="2e583-180">egn</span><span class="sxs-lookup"><span data-stu-id="2e583-180">egn</span></span>
  
<span data-ttu-id="2e583-181">número civil uniforme búlgaro</span><span class="sxs-lookup"><span data-stu-id="2e583-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="2e583-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="2e583-182">uniformcivilno#</span></span>
  
<span data-ttu-id="2e583-183">egn #</span><span class="sxs-lookup"><span data-stu-id="2e583-183">egn#</span></span>
  
<span data-ttu-id="2e583-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="2e583-184">униформ граждански номер</span></span>
  
<span data-ttu-id="2e583-185">ID униформ</span><span class="sxs-lookup"><span data-stu-id="2e583-185">униформ id</span></span>
  
<span data-ttu-id="2e583-186">ID de граждански униформ</span><span class="sxs-lookup"><span data-stu-id="2e583-186">униформ граждански id</span></span>
  
<span data-ttu-id="2e583-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="2e583-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="2e583-188">Croácia</span><span class="sxs-lookup"><span data-stu-id="2e583-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="2e583-189">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-189">Format</span></span>

<span data-ttu-id="2e583-190">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-191">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-191">Pattern</span></span>

<span data-ttu-id="2e583-192">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e583-192">11 digits:</span></span>
  
- <span data-ttu-id="2e583-193">Dez dígitos, escolhidos aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="2e583-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="2e583-194">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-195">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-195">Checksum</span></span>

<span data-ttu-id="2e583-196">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-197">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-197">Definition</span></span>

<span data-ttu-id="2e583-198">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-199">A função `Func_croatia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-200">Uma palavra- `Keywords_croatia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-201">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-202">A função `Func_croatia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-203">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="2e583-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-205">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-205">tax number</span></span>
  
<span data-ttu-id="2e583-206">imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-206">tax</span></span>
  
<span data-ttu-id="2e583-207">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-207">tax id</span></span>
  
<span data-ttu-id="2e583-208">OID</span><span class="sxs-lookup"><span data-stu-id="2e583-208">oid</span></span>
  
<span data-ttu-id="2e583-209">OID #</span><span class="sxs-lookup"><span data-stu-id="2e583-209">oid#</span></span>
  
<span data-ttu-id="2e583-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="2e583-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="2e583-211">Chipre</span><span class="sxs-lookup"><span data-stu-id="2e583-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="2e583-212">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-212">Format</span></span>

<span data-ttu-id="2e583-213">Oito dígitos e uma letra no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="2e583-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-214">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-214">Pattern</span></span>

<span data-ttu-id="2e583-215">Oito dígitos e uma letra:</span><span class="sxs-lookup"><span data-stu-id="2e583-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="2e583-216">Um "0"</span><span class="sxs-lookup"><span data-stu-id="2e583-216">A "0"</span></span> 
    
- <span data-ttu-id="2e583-217">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="2e583-217">Seven digits</span></span>
    
- <span data-ttu-id="2e583-218">Uma letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-219">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-219">Checksum</span></span>

<span data-ttu-id="2e583-220">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-221">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-221">Definition</span></span>

<span data-ttu-id="2e583-222">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-223">A função `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-224">Uma palavra- `Keywords_cyprus_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-225">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-226">A função `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-227">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="2e583-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-229">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-229">tax number</span></span>
  
<span data-ttu-id="2e583-230">imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-230">tax</span></span>
  
<span data-ttu-id="2e583-231">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-231">tax id</span></span>
  
<span data-ttu-id="2e583-232">código de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-232">tax identification code</span></span>
  
<span data-ttu-id="2e583-233">tic</span><span class="sxs-lookup"><span data-stu-id="2e583-233">tic</span></span>
  
<span data-ttu-id="2e583-234">tic #</span><span class="sxs-lookup"><span data-stu-id="2e583-234">tic#</span></span>
  
<span data-ttu-id="2e583-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="2e583-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="2e583-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="2e583-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="2e583-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="2e583-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="2e583-238">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="2e583-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="2e583-239">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-239">Format</span></span>

<span data-ttu-id="2e583-240">Nove ou dez dígitos com uma barra invertida opcional</span><span class="sxs-lookup"><span data-stu-id="2e583-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-241">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-241">Pattern</span></span>

<span data-ttu-id="2e583-242">Nove ou dez dígitos com uma barra invertida opcional:</span><span class="sxs-lookup"><span data-stu-id="2e583-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="2e583-243">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-243">Six digits</span></span> 
    
- <span data-ttu-id="2e583-244">Uma barra invertida (opcional)</span><span class="sxs-lookup"><span data-stu-id="2e583-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="2e583-245">Três ou quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-246">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-246">Checksum</span></span>

<span data-ttu-id="2e583-247">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-248">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-248">Definition</span></span>

<span data-ttu-id="2e583-249">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-250">A expressão `Regex_czech_republic_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-251">Uma palavra- `Keywords_czech_republic_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e583-252">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="2e583-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-254">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-254">tax number</span></span>
  
<span data-ttu-id="2e583-255">imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-255">tax</span></span>
  
<span data-ttu-id="2e583-256">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-256">tax id</span></span>
  
<span data-ttu-id="2e583-257">número pessoal</span><span class="sxs-lookup"><span data-stu-id="2e583-257">personal number</span></span>
  
<span data-ttu-id="2e583-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="2e583-258">daňové číslo</span></span>
  
<span data-ttu-id="2e583-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="2e583-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="2e583-260">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="2e583-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="2e583-261">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-261">Format</span></span>

<span data-ttu-id="2e583-262">Dez dígitos contendo um hífen</span><span class="sxs-lookup"><span data-stu-id="2e583-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-263">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-263">Pattern</span></span>

<span data-ttu-id="2e583-264">Dez dígitos contendo um hífen:</span><span class="sxs-lookup"><span data-stu-id="2e583-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="2e583-265">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="2e583-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="2e583-266">Um hífen</span><span class="sxs-lookup"><span data-stu-id="2e583-266">A hyphen</span></span>
    
- <span data-ttu-id="2e583-267">Quatro dígitos que correspondem a um número de sequência onde o primeiro dígito corresponde ao século do nascimento e o último dígito corresponde ao sexo da pessoa (ímpar para macho e par para fêmea)</span><span class="sxs-lookup"><span data-stu-id="2e583-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-268">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-268">Checksum</span></span>

<span data-ttu-id="2e583-269">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-270">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-270">Definition</span></span>

<span data-ttu-id="2e583-271">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-272">A função `Func_denmark_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-273">Uma palavra- `Keywords_denmark_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-274">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-275">A função `Func_denmark_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-276">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="2e583-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-278">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-278">tax number</span></span>
  
<span data-ttu-id="2e583-279">imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-279">tax</span></span>
  
<span data-ttu-id="2e583-280">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-280">tax id</span></span>
  
<span data-ttu-id="2e583-281">número de CPR</span><span class="sxs-lookup"><span data-stu-id="2e583-281">cpr number</span></span>
  
<span data-ttu-id="2e583-282">pedir #</span><span class="sxs-lookup"><span data-stu-id="2e583-282">cpr#</span></span>
  
<span data-ttu-id="2e583-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="2e583-283">skat nummer</span></span>
  
<span data-ttu-id="2e583-284">ID Skat</span><span class="sxs-lookup"><span data-stu-id="2e583-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="2e583-285">Estônia</span><span class="sxs-lookup"><span data-stu-id="2e583-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="2e583-286">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-286">Format</span></span>

<span data-ttu-id="2e583-287">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-288">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-288">Pattern</span></span>

<span data-ttu-id="2e583-289">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e583-289">11 digits:</span></span>
  
-  <span data-ttu-id="2e583-290">Um dígito que corresponde ao gênero e ao século de nascimento onde um número ímpar indica macho e o número par indica fêmea da seguinte maneira: 1, 2 para o século 19; 3, 4 para o século 20; e 5, 6 para o século 21</span><span class="sxs-lookup"><span data-stu-id="2e583-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="2e583-291">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="2e583-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="2e583-292">Três dígitos que correspondem a um número de série separando as pessoas que nasceu na mesma data</span><span class="sxs-lookup"><span data-stu-id="2e583-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="2e583-293">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-294">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-294">Checksum</span></span>

<span data-ttu-id="2e583-295">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-296">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-296">Definition</span></span>

<span data-ttu-id="2e583-297">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-298">A função `Func_estonia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-299">Uma palavra- `Keywords_estonia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-300">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-301">A função `Func_estonia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-302">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="2e583-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-304">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-304">tax number</span></span>
  
<span data-ttu-id="2e583-305">imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-305">tax</span></span>
  
<span data-ttu-id="2e583-306">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-306">tax id</span></span>
  
<span data-ttu-id="2e583-307">código pessoal</span><span class="sxs-lookup"><span data-stu-id="2e583-307">personal code</span></span>
  
<span data-ttu-id="2e583-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="2e583-308">maksunumber</span></span>
  
<span data-ttu-id="2e583-309">ID maksu</span><span class="sxs-lookup"><span data-stu-id="2e583-309">maksu id</span></span>
  
<span data-ttu-id="2e583-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="2e583-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="2e583-311">Finlândia</span><span class="sxs-lookup"><span data-stu-id="2e583-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="2e583-312">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-312">Format</span></span>

<span data-ttu-id="2e583-313">Uma combinação de 11 caracteres de dígitos, letras e sinal de mais e de menos</span><span class="sxs-lookup"><span data-stu-id="2e583-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-314">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-314">Pattern</span></span>

<span data-ttu-id="2e583-315">Uma combinação de 11 caracteres de dígitos, letras e sinal de mais e menos:</span><span class="sxs-lookup"><span data-stu-id="2e583-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="2e583-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-316">Six digits</span></span>
    
- <span data-ttu-id="2e583-317">Uma das seguintes opções: um sinal de adição, um sinal de menos ou a letra "A" (não diferencia maiúsculas de minúsculas) onde o sinal de mais significa que nasceu entre 1800-1899, o sinal de menos significa que nasceu entre 1900-1999 e "A" significa que nasceu 2000 e depois</span><span class="sxs-lookup"><span data-stu-id="2e583-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="2e583-318">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-318">Three digits</span></span>
    
- <span data-ttu-id="2e583-319">Uma letra ou um número</span><span class="sxs-lookup"><span data-stu-id="2e583-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-320">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-320">Checksum</span></span>

<span data-ttu-id="2e583-321">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-322">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-322">Definition</span></span>

<span data-ttu-id="2e583-323">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-324">A função `Func_finland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-325">Uma palavra- `Keywords_finland_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-326">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-327">A função `Func_finland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-328">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="2e583-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-330">identification number</span><span class="sxs-lookup"><span data-stu-id="2e583-330">identification number</span></span>
  
<span data-ttu-id="2e583-331">ID pessoal</span><span class="sxs-lookup"><span data-stu-id="2e583-331">personal id</span></span>
  
<span data-ttu-id="2e583-332">número de identidade</span><span class="sxs-lookup"><span data-stu-id="2e583-332">identity number</span></span>
  
<span data-ttu-id="2e583-333">número de ID nacional da finlandês</span><span class="sxs-lookup"><span data-stu-id="2e583-333">finnish national id number</span></span>
  
<span data-ttu-id="2e583-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-334">personalidnumber#</span></span>
  
<span data-ttu-id="2e583-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="2e583-335">national identification number</span></span>
  
<span data-ttu-id="2e583-336">número de identificação</span><span class="sxs-lookup"><span data-stu-id="2e583-336">id number</span></span>
  
<span data-ttu-id="2e583-337">n º de ID nacional</span><span class="sxs-lookup"><span data-stu-id="2e583-337">national id no.</span></span>
  
<span data-ttu-id="2e583-338">número de ID nacional</span><span class="sxs-lookup"><span data-stu-id="2e583-338">national id number</span></span>
  
<span data-ttu-id="2e583-339">ID não</span><span class="sxs-lookup"><span data-stu-id="2e583-339">id no</span></span>
  
<span data-ttu-id="2e583-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="2e583-340">tunnistenumero</span></span>
  
<span data-ttu-id="2e583-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="2e583-341">henkilötunnus</span></span>
  
<span data-ttu-id="2e583-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="2e583-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="2e583-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="2e583-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="2e583-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="2e583-344">identiteetti numero</span></span>
  
<span data-ttu-id="2e583-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="2e583-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="2e583-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="2e583-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="2e583-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="2e583-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="2e583-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="2e583-348">tunnusnumero</span></span>
  
<span data-ttu-id="2e583-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="2e583-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="2e583-350">França</span><span class="sxs-lookup"><span data-stu-id="2e583-350">France</span></span>

### <a name="format"></a><span data-ttu-id="2e583-351">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-351">Format</span></span>

<span data-ttu-id="2e583-352">13 dígitos para pessoas e nove dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="2e583-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-353">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-353">Pattern</span></span>

<span data-ttu-id="2e583-354">13 dígitos para pessoas:</span><span class="sxs-lookup"><span data-stu-id="2e583-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="2e583-355">Um dígito que deve ser 0, 1, 2 ou 3</span><span class="sxs-lookup"><span data-stu-id="2e583-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="2e583-356">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-356">12 digits</span></span>
    
<span data-ttu-id="2e583-357">Nove dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="2e583-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-358">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-358">Checksum</span></span>

<span data-ttu-id="2e583-359">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-360">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-360">Definition</span></span>

<span data-ttu-id="2e583-361">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-362">A função `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-363">Uma palavra- `Keywords_france_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-364">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-365">A função `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-366">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="2e583-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-368">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-368">tax identification number</span></span>
  
<span data-ttu-id="2e583-369">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-369">tax number</span></span>
  
<span data-ttu-id="2e583-370">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-370">tax id</span></span>
  
<span data-ttu-id="2e583-371">Numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="2e583-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="2e583-372">Alemanha</span><span class="sxs-lookup"><span data-stu-id="2e583-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="2e583-373">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-373">Format</span></span>

<span data-ttu-id="2e583-374">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-375">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-375">Pattern</span></span>

<span data-ttu-id="2e583-376">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e583-376">11 digits :</span></span>
  
-  <span data-ttu-id="2e583-377">Dez dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-377">Ten digits</span></span> 
    
- <span data-ttu-id="2e583-378">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-379">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-379">Checksum</span></span>

<span data-ttu-id="2e583-380">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-381">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-381">Definition</span></span>

<span data-ttu-id="2e583-382">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-383">A função `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-384">Uma palavra- `Keywords_germany_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-385">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-386">A função `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-387">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="2e583-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-389">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-389">tax number</span></span>
  
<span data-ttu-id="2e583-390">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-390">tax no.</span></span>
  
<span data-ttu-id="2e583-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-391">taxno#</span></span>
  
<span data-ttu-id="2e583-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-392">taxnumber#</span></span>
  
<span data-ttu-id="2e583-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2e583-393">taxnumber</span></span>
  
<span data-ttu-id="2e583-394">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-394">tax id</span></span>
  
<span data-ttu-id="2e583-395">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-395">taxid#</span></span>
  
<span data-ttu-id="2e583-396">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-396">tax identification number</span></span>
  
<span data-ttu-id="2e583-397">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-397">tax identification no.</span></span>
  
<span data-ttu-id="2e583-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="2e583-398">steuernummer</span></span>
  
<span data-ttu-id="2e583-399">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="2e583-399">steuer id</span></span>
  
<span data-ttu-id="2e583-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e583-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="2e583-401">Grécia</span><span class="sxs-lookup"><span data-stu-id="2e583-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="2e583-402">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-402">Format</span></span>

<span data-ttu-id="2e583-403">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-404">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-404">Pattern</span></span>

<span data-ttu-id="2e583-405">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-406">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-406">Checksum</span></span>

<span data-ttu-id="2e583-407">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-408">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-408">Definition</span></span>

<span data-ttu-id="2e583-409">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-410">A expressão `Regex_greece_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-411">Uma palavra- `Keywords_greece_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e583-412">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="2e583-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-414">AFM</span><span class="sxs-lookup"><span data-stu-id="2e583-414">afm</span></span>
  
<span data-ttu-id="2e583-415">Tin</span><span class="sxs-lookup"><span data-stu-id="2e583-415">tin</span></span>
  
<span data-ttu-id="2e583-416">n º de ID de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-416">tax id no.</span></span>
  
<span data-ttu-id="2e583-417">ID de imposto não</span><span class="sxs-lookup"><span data-stu-id="2e583-417">tax id no</span></span>
  
<span data-ttu-id="2e583-418">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-418">tax identification number</span></span>
  
<span data-ttu-id="2e583-419">número do registro de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-419">tax registry number</span></span>
  
<span data-ttu-id="2e583-420">n º do registro de impostos</span><span class="sxs-lookup"><span data-stu-id="2e583-420">tax registry no.</span></span>
  
<span data-ttu-id="2e583-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="2e583-421">afm#</span></span>
  
<span data-ttu-id="2e583-422">Tin #</span><span class="sxs-lookup"><span data-stu-id="2e583-422">tin#</span></span>
  
<span data-ttu-id="2e583-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="2e583-423">taxidno#</span></span>
  
<span data-ttu-id="2e583-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="2e583-424">taxregistryno#</span></span>
  
<span data-ttu-id="2e583-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="2e583-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="2e583-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="2e583-426">aφμ</span></span>
  
<span data-ttu-id="2e583-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="2e583-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="2e583-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="2e583-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="2e583-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="2e583-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="2e583-430">Hungria</span><span class="sxs-lookup"><span data-stu-id="2e583-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="2e583-431">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-431">Format</span></span>

<span data-ttu-id="2e583-432">Dez dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-433">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-433">Pattern</span></span>

<span data-ttu-id="2e583-434">Dez dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e583-434">Ten digits:</span></span>
  
-  <span data-ttu-id="2e583-435">Um dígito que deve ser "8"</span><span class="sxs-lookup"><span data-stu-id="2e583-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="2e583-436">Cinco dígitos que correspondem ao número de dias entre a data 01/01/1867 e a data do nascimento da pessoa</span><span class="sxs-lookup"><span data-stu-id="2e583-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="2e583-437">Três dígitos que correspondem ao número gerado pela chance de diferenciar as pessoas nasceu no mesmo dia</span><span class="sxs-lookup"><span data-stu-id="2e583-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="2e583-438">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-439">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-439">Checksum</span></span>

<span data-ttu-id="2e583-440">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-441">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-441">Definition</span></span>

<span data-ttu-id="2e583-442">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-443">A função `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-444">Uma palavra- `Keywords_hungary_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-445">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-446">A função `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-447">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="2e583-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-449">número de identificação do imposto húngaro</span><span class="sxs-lookup"><span data-stu-id="2e583-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="2e583-450">Tin húngaro</span><span class="sxs-lookup"><span data-stu-id="2e583-450">hungarian tin</span></span>
  
<span data-ttu-id="2e583-451">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-451">tax id number</span></span>
  
<span data-ttu-id="2e583-452">número de IVA</span><span class="sxs-lookup"><span data-stu-id="2e583-452">vat number</span></span>
  
<span data-ttu-id="2e583-453">autoridade de imposto não</span><span class="sxs-lookup"><span data-stu-id="2e583-453">tax authority no</span></span>
  
<span data-ttu-id="2e583-454">número de identidade do imposto ID do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-454">tax id tax identity number</span></span>
  
<span data-ttu-id="2e583-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-455">taxidnumber#</span></span>
  
<span data-ttu-id="2e583-456">Tin #</span><span class="sxs-lookup"><span data-stu-id="2e583-456">tin#</span></span>
  
<span data-ttu-id="2e583-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="2e583-457">hungatiantin#</span></span>
  
<span data-ttu-id="2e583-458">identificação de imposto não</span><span class="sxs-lookup"><span data-stu-id="2e583-458">tax identification no</span></span>
  
<span data-ttu-id="2e583-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="2e583-459">taxidno#</span></span>
  
<span data-ttu-id="2e583-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="2e583-460">adóazonosító szám</span></span>
  
<span data-ttu-id="2e583-461">adószám</span><span class="sxs-lookup"><span data-stu-id="2e583-461">adószám</span></span>
  
<span data-ttu-id="2e583-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="2e583-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="2e583-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="2e583-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="2e583-464">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-464">Format</span></span>

<span data-ttu-id="2e583-465">Sete dígitos seguidos de uma letra sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-466">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-466">Pattern</span></span>

<span data-ttu-id="2e583-467">Sete dígitos seguidos de uma letra:</span><span class="sxs-lookup"><span data-stu-id="2e583-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="2e583-468">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="2e583-468">Seven digits</span></span> 
    
- <span data-ttu-id="2e583-469">Uma letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-470">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-470">Checksum</span></span>

<span data-ttu-id="2e583-471">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-472">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-472">Definition</span></span>

<span data-ttu-id="2e583-473">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-474">A função `Func_ireland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-475">Uma palavra- `Keywords_ireland_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-476">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-477">A função `Func_ireland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-478">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="2e583-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-480">serviço público não</span><span class="sxs-lookup"><span data-stu-id="2e583-480">public service no</span></span>
  
<span data-ttu-id="2e583-481">serviço público pessoal não</span><span class="sxs-lookup"><span data-stu-id="2e583-481">personal public service no</span></span>
  
<span data-ttu-id="2e583-482">PPS não</span><span class="sxs-lookup"><span data-stu-id="2e583-482">pps no</span></span>
  
<span data-ttu-id="2e583-483">serviço pessoal não</span><span class="sxs-lookup"><span data-stu-id="2e583-483">personal service no</span></span>
  
<span data-ttu-id="2e583-484">serviço PPS não</span><span class="sxs-lookup"><span data-stu-id="2e583-484">pps service no</span></span>
  
<span data-ttu-id="2e583-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="2e583-485">ppsno#</span></span>
  
<span data-ttu-id="2e583-486">número do PPS do irlandês</span><span class="sxs-lookup"><span data-stu-id="2e583-486">irish pps no</span></span>
  
<span data-ttu-id="2e583-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="2e583-487">publicserviceno#</span></span>
  
<span data-ttu-id="2e583-488">número de serviço público pessoal</span><span class="sxs-lookup"><span data-stu-id="2e583-488">personal public service number</span></span>
  
<span data-ttu-id="2e583-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="2e583-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="2e583-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="2e583-490">pps uimh</span></span>
  
<span data-ttu-id="2e583-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="2e583-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="2e583-492">Itália</span><span class="sxs-lookup"><span data-stu-id="2e583-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="2e583-493">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-493">Format</span></span>

<span data-ttu-id="2e583-494">16 letras e dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="2e583-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-495">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-495">Pattern</span></span>

<span data-ttu-id="2e583-496">16 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e583-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="2e583-497">Três letras que correspondem às três primeiras consoantes no nome da família</span><span class="sxs-lookup"><span data-stu-id="2e583-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="2e583-498">Três letras que correspondem à primeira, terceira e quarta consoantes no primeiro nome</span><span class="sxs-lookup"><span data-stu-id="2e583-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="2e583-499">Dois dígitos que correspondem aos últimos dígitos do ano de nascimento</span><span class="sxs-lookup"><span data-stu-id="2e583-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="2e583-500">Um dígito que corresponde ao mês de nascimento-as letras são usadas em ordem alfabética, mas apenas as letras de a a E, H, L, M, P, R a T são usadas (portanto, Janeiro é A e outubro é R)</span><span class="sxs-lookup"><span data-stu-id="2e583-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="2e583-501">Dois dígitos que correspondem ao dia do mês de nascimento, onde 40 é adicionado ao dia de nascimento de mulheres para diferenciar da homens</span><span class="sxs-lookup"><span data-stu-id="2e583-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="2e583-502">Quatro dígitos que correspondem a um código de área específico para o município onde a pessoa nasceu — códigos em todo o país são usados para países estrangeiros</span><span class="sxs-lookup"><span data-stu-id="2e583-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="2e583-503">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-504">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-504">Checksum</span></span>

<span data-ttu-id="2e583-505">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-506">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-506">Definition</span></span>

<span data-ttu-id="2e583-507">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-508">A função `Func_italy_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-509">Uma palavra- `Keywords_italy_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-510">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-511">A função `Func_italy_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-512">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="2e583-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-514">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-514">tax number</span></span>
  
<span data-ttu-id="2e583-515">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-515">tax no.</span></span>
  
<span data-ttu-id="2e583-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-516">taxno#</span></span>
  
<span data-ttu-id="2e583-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-517">taxnumber#</span></span>
  
<span data-ttu-id="2e583-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2e583-518">taxnumber</span></span>
  
<span data-ttu-id="2e583-519">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-519">tax id</span></span>
  
<span data-ttu-id="2e583-520">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-520">taxid#</span></span>
  
<span data-ttu-id="2e583-521">código fiscal</span><span class="sxs-lookup"><span data-stu-id="2e583-521">fiscal code</span></span>
  
<span data-ttu-id="2e583-522">fiscalização codice</span><span class="sxs-lookup"><span data-stu-id="2e583-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="2e583-523">Letônia</span><span class="sxs-lookup"><span data-stu-id="2e583-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="2e583-524">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-524">Format</span></span>

<span data-ttu-id="2e583-525">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-526">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-526">Pattern</span></span>

<span data-ttu-id="2e583-527">11 dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="2e583-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="2e583-528">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="2e583-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="2e583-529">Um dígito que corresponde ao século de nascimento onde "0" corresponde ao século 19, "1" corresponde a 20 Century e "2" corresponde ao século 21</span><span class="sxs-lookup"><span data-stu-id="2e583-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="2e583-530">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-531">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-531">Checksum</span></span>

<span data-ttu-id="2e583-532">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-533">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-533">Definition</span></span>

<span data-ttu-id="2e583-534">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-535">A função `Func_latvia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-536">Uma palavra- `Keywords_latvia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-537">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-538">A função `Func_latvia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-539">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="2e583-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-541">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-541">tax number</span></span>
  
<span data-ttu-id="2e583-542">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-542">tax no.</span></span>
  
<span data-ttu-id="2e583-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-543">taxno#</span></span>
  
<span data-ttu-id="2e583-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-544">taxnumber#</span></span>
  
<span data-ttu-id="2e583-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2e583-545">taxnumber</span></span>
  
<span data-ttu-id="2e583-546">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-546">tax id</span></span>
  
<span data-ttu-id="2e583-547">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-547">taxid#</span></span>
  
<span data-ttu-id="2e583-548">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-548">tax identification number</span></span>
  
<span data-ttu-id="2e583-549">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-549">tax identification no.</span></span>
  
<span data-ttu-id="2e583-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="2e583-550">nodokļa numurs</span></span>
  
<span data-ttu-id="2e583-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="2e583-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="2e583-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="2e583-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="2e583-553">Lituânia</span><span class="sxs-lookup"><span data-stu-id="2e583-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="2e583-554">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-554">Format</span></span>

<span data-ttu-id="2e583-555">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-556">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-556">Pattern</span></span>

<span data-ttu-id="2e583-557">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-558">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-558">Checksum</span></span>

<span data-ttu-id="2e583-559">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-560">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-560">Definition</span></span>

<span data-ttu-id="2e583-561">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-562">A função `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-563">Uma palavra- `Keywords_lithuania_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-564">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-565">A função `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-566">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="2e583-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-568">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-568">tax number</span></span>
  
<span data-ttu-id="2e583-569">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-569">tax no.</span></span>
  
<span data-ttu-id="2e583-570">n º do imposto #</span><span class="sxs-lookup"><span data-stu-id="2e583-570">tax no#</span></span>
  
<span data-ttu-id="2e583-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-571">taxnumber#</span></span>
  
<span data-ttu-id="2e583-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2e583-572">taxnumber</span></span>
  
<span data-ttu-id="2e583-573">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-573">tax id</span></span>
  
<span data-ttu-id="2e583-574">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-574">taxid#</span></span>
  
<span data-ttu-id="2e583-575">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-575">tax identification number</span></span>
  
<span data-ttu-id="2e583-576">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-576">tax identification no.</span></span>
  
<span data-ttu-id="2e583-577">ID mokesčių</span><span class="sxs-lookup"><span data-stu-id="2e583-577">mokesčių id</span></span>
  
<span data-ttu-id="2e583-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="2e583-578">mokesčių numeris</span></span>
  
<span data-ttu-id="2e583-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="2e583-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="2e583-580">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="2e583-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="2e583-581">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-581">Format</span></span>

<span data-ttu-id="2e583-582">13 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-583">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-583">Pattern</span></span>

<span data-ttu-id="2e583-584">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="2e583-584">13 digits:</span></span>
  
-  <span data-ttu-id="2e583-585">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-585">11 digits</span></span> 
    
- <span data-ttu-id="2e583-586">Dois dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-587">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-587">Checksum</span></span>

<span data-ttu-id="2e583-588">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-589">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-589">Definition</span></span>

<span data-ttu-id="2e583-590">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-591">A função `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-592">Uma palavra- `Keywords_luxemburg_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-593">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-594">A função `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-595">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="2e583-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-597">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-597">tax number</span></span>
  
<span data-ttu-id="2e583-598">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-598">tax no.</span></span>
  
<span data-ttu-id="2e583-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-599">taxno#</span></span>
  
<span data-ttu-id="2e583-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-600">taxnumber#</span></span>
  
<span data-ttu-id="2e583-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2e583-601">taxnumber</span></span>
  
<span data-ttu-id="2e583-602">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-602">tax id</span></span>
  
<span data-ttu-id="2e583-603">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-603">taxid#</span></span>
  
<span data-ttu-id="2e583-604">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-604">tax identification number</span></span>
  
<span data-ttu-id="2e583-605">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-605">tax identification no.</span></span>
  
<span data-ttu-id="2e583-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="2e583-606">steuernummer</span></span>
  
<span data-ttu-id="2e583-607">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="2e583-607">steuer id</span></span>
  
<span data-ttu-id="2e583-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e583-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="2e583-609">Malta</span><span class="sxs-lookup"><span data-stu-id="2e583-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="2e583-610">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-610">Format</span></span>

<span data-ttu-id="2e583-611">Para as nacionalidades maltês: 7 dígitos e uma letra no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="2e583-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="2e583-612">Entidades nacionais e Maltês não-maltês: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-613">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-613">Pattern</span></span>

<span data-ttu-id="2e583-614">Nacionalidades maltês: 7 dígitos e uma letra</span><span class="sxs-lookup"><span data-stu-id="2e583-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="2e583-615">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="2e583-615">Seven digits</span></span> 
    
- <span data-ttu-id="2e583-616">Uma letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="2e583-617">Entidades nacionais e Maltês não-maltês: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="2e583-618">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2e583-619">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-619">Checksum</span></span>

<span data-ttu-id="2e583-620">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-621">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-621">Definition</span></span>

<span data-ttu-id="2e583-622">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-623">A função `Func_malta_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-624">Uma palavra- `Keywords_malta_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-625">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-626">A função `Func_malta_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-627">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="2e583-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-629">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-629">tax number</span></span>
  
<span data-ttu-id="2e583-630">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-630">tax no.</span></span>
  
<span data-ttu-id="2e583-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-631">taxno#</span></span>
  
<span data-ttu-id="2e583-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-632">taxnumber#</span></span>
  
<span data-ttu-id="2e583-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2e583-633">taxnumber</span></span>
  
<span data-ttu-id="2e583-634">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-634">tax id</span></span>
  
<span data-ttu-id="2e583-635">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-635">taxid#</span></span>
  
<span data-ttu-id="2e583-636">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-636">tax identification number</span></span>
  
<span data-ttu-id="2e583-637">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-637">tax identification no.</span></span>
  
<span data-ttu-id="2e583-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="2e583-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="2e583-639">ID tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="2e583-639">id tat-taxxa</span></span>
  
<span data-ttu-id="2e583-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="2e583-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="2e583-641">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="2e583-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="2e583-642">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-642">Format</span></span>

<span data-ttu-id="2e583-643">Nove dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-644">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-644">Pattern</span></span>

<span data-ttu-id="2e583-645">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2e583-646">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-646">Checksum</span></span>

<span data-ttu-id="2e583-647">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-648">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-648">Definition</span></span>

<span data-ttu-id="2e583-649">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-650">A função `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-651">Uma palavra- `Keywords_netherlands_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-652">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-653">A função `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-654">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="2e583-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-656">número de identificação do imposto Holanda</span><span class="sxs-lookup"><span data-stu-id="2e583-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="2e583-657">identificação de imposto Holanda</span><span class="sxs-lookup"><span data-stu-id="2e583-657">netherlands tax identification</span></span>
  
<span data-ttu-id="2e583-658">número de identificação de imposto do Netherland</span><span class="sxs-lookup"><span data-stu-id="2e583-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="2e583-659">identificação de imposto do Netherland</span><span class="sxs-lookup"><span data-stu-id="2e583-659">netherland's tax identification</span></span>
  
<span data-ttu-id="2e583-660">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-660">tax identification number</span></span>
  
<span data-ttu-id="2e583-661">ID de imposto holandês</span><span class="sxs-lookup"><span data-stu-id="2e583-661">dutch tax id</span></span>
  
<span data-ttu-id="2e583-662">número de identificação do imposto holandês</span><span class="sxs-lookup"><span data-stu-id="2e583-662">dutch tax identification number</span></span>
  
<span data-ttu-id="2e583-663">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-663">tax id</span></span>
  
<span data-ttu-id="2e583-664">ID de imposto #</span><span class="sxs-lookup"><span data-stu-id="2e583-664">tax id#</span></span>
  
<span data-ttu-id="2e583-665">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-665">tax number</span></span>
  
<span data-ttu-id="2e583-666">n º do imposto #</span><span class="sxs-lookup"><span data-stu-id="2e583-666">tax no#</span></span>
  
<span data-ttu-id="2e583-667">imposto #</span><span class="sxs-lookup"><span data-stu-id="2e583-667">tax#</span></span>
  
<span data-ttu-id="2e583-668">Tin</span><span class="sxs-lookup"><span data-stu-id="2e583-668">tin</span></span>
  
<span data-ttu-id="2e583-669">Tin #</span><span class="sxs-lookup"><span data-stu-id="2e583-669">tin#</span></span>
  
<span data-ttu-id="2e583-670">Tin Holanda</span><span class="sxs-lookup"><span data-stu-id="2e583-670">netherlands tin</span></span>
  
<span data-ttu-id="2e583-671">Tin do Netherland</span><span class="sxs-lookup"><span data-stu-id="2e583-671">netherland's tin</span></span>
  
<span data-ttu-id="2e583-672">Países Baixos identificatienummer</span><span class="sxs-lookup"><span data-stu-id="2e583-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="2e583-673">identificatienummer Van é última</span><span class="sxs-lookup"><span data-stu-id="2e583-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="2e583-674">identificatienummer a última</span><span class="sxs-lookup"><span data-stu-id="2e583-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="2e583-675">Países Baixos identificatie</span><span class="sxs-lookup"><span data-stu-id="2e583-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="2e583-676">Países Baixos Nummer ID da última vez</span><span class="sxs-lookup"><span data-stu-id="2e583-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="2e583-677">Países Baixos belastingnummer</span><span class="sxs-lookup"><span data-stu-id="2e583-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="2e583-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="2e583-678">btw nummer</span></span>
  
<span data-ttu-id="2e583-679">Nederlandse identificatie</span><span class="sxs-lookup"><span data-stu-id="2e583-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="2e583-680">Polônia</span><span class="sxs-lookup"><span data-stu-id="2e583-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="2e583-681">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-681">Format</span></span>

<span data-ttu-id="2e583-682">Onze dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-683">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-683">Pattern</span></span>

<span data-ttu-id="2e583-684">Onze dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-685">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-685">Checksum</span></span>

<span data-ttu-id="2e583-686">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-687">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-687">Definition</span></span>

<span data-ttu-id="2e583-688">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-689">A função `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-690">Uma palavra- `Keywords_poland_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-691">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-692">A função `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-693">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="2e583-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-695">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-695">tax number</span></span>
  
<span data-ttu-id="2e583-696">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-696">tax no.</span></span>
  
<span data-ttu-id="2e583-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-697">taxno#</span></span>
  
<span data-ttu-id="2e583-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-698">taxnumber#</span></span>
  
<span data-ttu-id="2e583-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2e583-699">taxnumber</span></span>
  
<span data-ttu-id="2e583-700">nip</span><span class="sxs-lookup"><span data-stu-id="2e583-700">nip</span></span>
  
<span data-ttu-id="2e583-701">nip #</span><span class="sxs-lookup"><span data-stu-id="2e583-701">nip#</span></span>
  
<span data-ttu-id="2e583-702">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-702">tax id</span></span>
  
<span data-ttu-id="2e583-703">ID de imposto #</span><span class="sxs-lookup"><span data-stu-id="2e583-703">tax id#</span></span>
  
<span data-ttu-id="2e583-704">ID Nip</span><span class="sxs-lookup"><span data-stu-id="2e583-704">nip id</span></span>
  
<span data-ttu-id="2e583-705">ID Nip #</span><span class="sxs-lookup"><span data-stu-id="2e583-705">nip id#</span></span>
  
<span data-ttu-id="2e583-706">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-706">tax identification number</span></span>
  
<span data-ttu-id="2e583-707">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-707">tax identification no.</span></span>
  
<span data-ttu-id="2e583-708">número de IVA</span><span class="sxs-lookup"><span data-stu-id="2e583-708">vat number</span></span>
  
<span data-ttu-id="2e583-709">IVA não.</span><span class="sxs-lookup"><span data-stu-id="2e583-709">vat no.</span></span>
  
<span data-ttu-id="2e583-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="2e583-710">vatno#</span></span>
  
<span data-ttu-id="2e583-711">ID de IVA</span><span class="sxs-lookup"><span data-stu-id="2e583-711">vat id</span></span>
  
<span data-ttu-id="2e583-712">ID de IVA #</span><span class="sxs-lookup"><span data-stu-id="2e583-712">vat id#</span></span>
  
<span data-ttu-id="2e583-713">numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="2e583-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="2e583-714">polski numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="2e583-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="2e583-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="2e583-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="2e583-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="2e583-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="2e583-717">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-717">Format</span></span>

<span data-ttu-id="2e583-718">Nove dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-719">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-719">Pattern</span></span>

<span data-ttu-id="2e583-720">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-721">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-721">Checksum</span></span>

<span data-ttu-id="2e583-722">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-723">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-723">Definition</span></span>

<span data-ttu-id="2e583-724">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-725">A função `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-726">Uma palavra- `Keywords_portugal_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-727">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-728">A função `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-729">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="2e583-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-731">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-731">tax number</span></span>
  
<span data-ttu-id="2e583-732">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-732">tax no.</span></span>
  
<span data-ttu-id="2e583-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-733">taxno#</span></span>
  
<span data-ttu-id="2e583-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2e583-734">taxnumber#</span></span>
  
<span data-ttu-id="2e583-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2e583-735">taxnumber</span></span>
  
<span data-ttu-id="2e583-736">nse</span><span class="sxs-lookup"><span data-stu-id="2e583-736">nif</span></span>
  
<span data-ttu-id="2e583-737">nse #</span><span class="sxs-lookup"><span data-stu-id="2e583-737">nif#</span></span>
  
<span data-ttu-id="2e583-738">fiscal numero</span><span class="sxs-lookup"><span data-stu-id="2e583-738">numero fiscal</span></span>
  
<span data-ttu-id="2e583-739">número de identificação fiscal</span><span class="sxs-lookup"><span data-stu-id="2e583-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="2e583-740">Romênia</span><span class="sxs-lookup"><span data-stu-id="2e583-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="2e583-741">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-741">Format</span></span>

<span data-ttu-id="2e583-742">13 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-743">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-743">Pattern</span></span>

<span data-ttu-id="2e583-744">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-745">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-745">Checksum</span></span>

<span data-ttu-id="2e583-746">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-747">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-747">Definition</span></span>

<span data-ttu-id="2e583-748">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-749">A expressão `Regex_romania_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-750">Uma palavra- `Keywords_romania_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e583-751">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="2e583-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-753">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-753">tax id</span></span>
  
<span data-ttu-id="2e583-754">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-754">tax id number</span></span>
  
<span data-ttu-id="2e583-755">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="2e583-755">tax file no</span></span>
  
<span data-ttu-id="2e583-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="2e583-756">tax file number</span></span>
  
<span data-ttu-id="2e583-757">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-757">tax no</span></span>
  
<span data-ttu-id="2e583-758">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-758">tax number</span></span>
  
<span data-ttu-id="2e583-759">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-759">taxid#</span></span>
  
<span data-ttu-id="2e583-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-760">taxno#</span></span>
  
<span data-ttu-id="2e583-761">ID-UL Taxei</span><span class="sxs-lookup"><span data-stu-id="2e583-761">id-ul taxei</span></span>
  
<span data-ttu-id="2e583-762">numărul de identificare Fiscală</span><span class="sxs-lookup"><span data-stu-id="2e583-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="2e583-763">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="2e583-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="2e583-764">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-764">Format</span></span>

<span data-ttu-id="2e583-765">10 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-766">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-766">Pattern</span></span>

<span data-ttu-id="2e583-767">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-768">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-768">Checksum</span></span>

<span data-ttu-id="2e583-769">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="2e583-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-770">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-770">Definition</span></span>

<span data-ttu-id="2e583-771">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-772">A expressão `Regex_slovakia_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-773">Uma palavra- `Keywords_slovakia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e583-774">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="2e583-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-776">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-776">tax id</span></span>
  
<span data-ttu-id="2e583-777">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-777">tax id number</span></span>
  
<span data-ttu-id="2e583-778">ID do Tin</span><span class="sxs-lookup"><span data-stu-id="2e583-778">tin id</span></span>
  
<span data-ttu-id="2e583-779">Tin não</span><span class="sxs-lookup"><span data-stu-id="2e583-779">tin no</span></span>
  
<span data-ttu-id="2e583-780">ID de Tin de eslovaco</span><span class="sxs-lookup"><span data-stu-id="2e583-780">slovakian tin id</span></span>
  
<span data-ttu-id="2e583-781">Tin</span><span class="sxs-lookup"><span data-stu-id="2e583-781">tin</span></span>
  
<span data-ttu-id="2e583-782">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="2e583-782">tax file no</span></span>
  
<span data-ttu-id="2e583-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="2e583-783">tax file number</span></span>
  
<span data-ttu-id="2e583-784">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-784">tax no</span></span>
  
<span data-ttu-id="2e583-785">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-785">tax number</span></span>
  
<span data-ttu-id="2e583-786">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-786">taxid#</span></span>
  
<span data-ttu-id="2e583-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-787">taxno#</span></span>
  
<span data-ttu-id="2e583-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="2e583-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="2e583-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="2e583-789">daňové číslo</span></span>
  
<span data-ttu-id="2e583-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="2e583-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="2e583-791">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="2e583-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="2e583-792">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-792">Format</span></span>

<span data-ttu-id="2e583-793">Oito dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-794">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-794">Pattern</span></span>

<span data-ttu-id="2e583-795">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-796">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-796">Checksum</span></span>

<span data-ttu-id="2e583-797">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-798">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-798">Definition</span></span>

<span data-ttu-id="2e583-799">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-800">A função `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-801">Uma palavra- `Keywords_slovenia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-802">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-803">A função `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-804">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="2e583-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-806">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-806">tax id</span></span>
  
<span data-ttu-id="2e583-807">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-807">tax id number</span></span>
  
<span data-ttu-id="2e583-808">ID do Tin</span><span class="sxs-lookup"><span data-stu-id="2e583-808">tin id</span></span>
  
<span data-ttu-id="2e583-809">Tin não</span><span class="sxs-lookup"><span data-stu-id="2e583-809">tin no</span></span>
  
<span data-ttu-id="2e583-810">ID de Tin esloveno</span><span class="sxs-lookup"><span data-stu-id="2e583-810">slovenian tin id</span></span>
  
<span data-ttu-id="2e583-811">Tin</span><span class="sxs-lookup"><span data-stu-id="2e583-811">tin</span></span>
  
<span data-ttu-id="2e583-812">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="2e583-812">tax file no</span></span>
  
<span data-ttu-id="2e583-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="2e583-813">tax file number</span></span>
  
<span data-ttu-id="2e583-814">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-814">tax no</span></span>
  
<span data-ttu-id="2e583-815">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-815">tax number</span></span>
  
<span data-ttu-id="2e583-816">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-816">taxid#</span></span>
  
<span data-ttu-id="2e583-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-817">taxno#</span></span>
  
<span data-ttu-id="2e583-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="2e583-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="2e583-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="2e583-819">davčna številka</span></span>
  
<span data-ttu-id="2e583-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="2e583-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="2e583-821">Espanha</span><span class="sxs-lookup"><span data-stu-id="2e583-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="2e583-822">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-822">Format</span></span>

<span data-ttu-id="2e583-823">Sete ou oito dígitos e uma ou duas letras no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="2e583-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-824">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-824">Pattern</span></span>

<span data-ttu-id="2e583-825">Pessoas naturais do espanhol com um cartão de identidade nacional da Espanha:</span><span class="sxs-lookup"><span data-stu-id="2e583-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="2e583-826">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-826">Eight digits</span></span> 
    
- <span data-ttu-id="2e583-827">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="2e583-828">Spaniards não residente sem um cartão de identidade nacional da Espanha</span><span class="sxs-lookup"><span data-stu-id="2e583-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="2e583-829">Uma letra maiúscula "L" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="2e583-830">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="2e583-830">Seven digits</span></span>
    
- <span data-ttu-id="2e583-831">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="2e583-832">Spaniards residentes sob a idade de 14 anos sem um cartão de identidade nacional da Espanha:</span><span class="sxs-lookup"><span data-stu-id="2e583-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="2e583-833">Uma letra maiúscula "K" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="2e583-834">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="2e583-834">Seven digits</span></span> 
    
- <span data-ttu-id="2e583-835">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="2e583-836">Foreigners com o número de identificação do estrangeiro</span><span class="sxs-lookup"><span data-stu-id="2e583-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="2e583-837">Uma letra maiúscula que é "X", "Y" ou "Z" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="2e583-838">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="2e583-838">Seven digits</span></span>
    
- <span data-ttu-id="2e583-839">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="2e583-840">Foreigners sem um número de identificação do estrangeiro</span><span class="sxs-lookup"><span data-stu-id="2e583-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="2e583-841">Uma letra maiúscula que é "M" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="2e583-842">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="2e583-842">Seven digits</span></span>
    
- <span data-ttu-id="2e583-843">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="2e583-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2e583-844">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-844">Checksum</span></span>

<span data-ttu-id="2e583-845">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-846">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-846">Definition</span></span>

<span data-ttu-id="2e583-847">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-848">A função `Func_spain_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-849">Uma palavra- `Keywords_spain_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-850">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-851">A função `Func_spain_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-852">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="2e583-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-854">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-854">tax id</span></span>
  
<span data-ttu-id="2e583-855">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-855">tax id number</span></span>
  
<span data-ttu-id="2e583-856">ID de CIF</span><span class="sxs-lookup"><span data-stu-id="2e583-856">cif id</span></span>
  
<span data-ttu-id="2e583-857">Não CIF</span><span class="sxs-lookup"><span data-stu-id="2e583-857">cif no</span></span>
  
<span data-ttu-id="2e583-858">ID de CIF espanhol</span><span class="sxs-lookup"><span data-stu-id="2e583-858">spanish cif id</span></span>
  
<span data-ttu-id="2e583-859">CIF</span><span class="sxs-lookup"><span data-stu-id="2e583-859">cif</span></span>
  
<span data-ttu-id="2e583-860">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="2e583-860">tax file no</span></span>
  
<span data-ttu-id="2e583-861">número de CIF espanhol</span><span class="sxs-lookup"><span data-stu-id="2e583-861">spanish cif number</span></span>
  
<span data-ttu-id="2e583-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="2e583-862">tax file number</span></span>
  
<span data-ttu-id="2e583-863">Não CIF espanhol</span><span class="sxs-lookup"><span data-stu-id="2e583-863">spanish cif no</span></span>
  
<span data-ttu-id="2e583-864">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-864">tax no</span></span>
  
<span data-ttu-id="2e583-865">número do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-865">tax number</span></span>
  
<span data-ttu-id="2e583-866">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-866">taxid#</span></span>
  
<span data-ttu-id="2e583-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="2e583-867">taxno#</span></span>
  
<span data-ttu-id="2e583-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="2e583-868">cifid#</span></span>
  
<span data-ttu-id="2e583-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="2e583-869">spanishcifid#</span></span>
  
<span data-ttu-id="2e583-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="2e583-870">spanishcifno#</span></span>
  
<span data-ttu-id="2e583-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="2e583-871">número de contribuyente</span></span>
  
<span data-ttu-id="2e583-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="2e583-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="2e583-873">número de Identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="2e583-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="2e583-874">número CIF</span><span class="sxs-lookup"><span data-stu-id="2e583-874">cif número</span></span>
  
<span data-ttu-id="2e583-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="2e583-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="2e583-876">Suécia</span><span class="sxs-lookup"><span data-stu-id="2e583-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="2e583-877">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-877">Format</span></span>

<span data-ttu-id="2e583-878">Dez dígitos e um símbolo no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="2e583-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-879">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-879">Pattern</span></span>

<span data-ttu-id="2e583-880">Dez dígitos e um símbolo:</span><span class="sxs-lookup"><span data-stu-id="2e583-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="2e583-881">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="2e583-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2e583-882">Um sinal de adição, sinal de menos ou barra invertida</span><span class="sxs-lookup"><span data-stu-id="2e583-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="2e583-883">Três dígitos que tornam o número de identificação exclusivo, onde:</span><span class="sxs-lookup"><span data-stu-id="2e583-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="2e583-884">Para números emitidos antes de 1990, o sétimo e oitavo dígito identificam o Condado de nascimento ou pessoas de nasceu</span><span class="sxs-lookup"><span data-stu-id="2e583-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="2e583-885">O dígito na nona posição indica sexo por tanto ímpar para masculino ou par para fêmea</span><span class="sxs-lookup"><span data-stu-id="2e583-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="2e583-886">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2e583-887">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-887">Checksum</span></span>

<span data-ttu-id="2e583-888">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-889">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-889">Definition</span></span>

<span data-ttu-id="2e583-890">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-891">A função `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-892">Uma palavra- `Keywords_sweden_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2e583-893">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-894">A função `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2e583-895">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="2e583-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-897">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-897">tax id</span></span>
  
<span data-ttu-id="2e583-898">n º de ID de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-898">tax id no.</span></span>
  
<span data-ttu-id="2e583-899">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-899">tax id number</span></span>
  
<span data-ttu-id="2e583-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="2e583-900">tax identification</span></span>
  
<span data-ttu-id="2e583-901">identificação de imposto #</span><span class="sxs-lookup"><span data-stu-id="2e583-901">tax identification#</span></span>
  
<span data-ttu-id="2e583-902">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-902">tax no.</span></span>
  
<span data-ttu-id="2e583-903">imposto #</span><span class="sxs-lookup"><span data-stu-id="2e583-903">tax#</span></span>
  
<span data-ttu-id="2e583-904">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-904">taxid#</span></span>
  
<span data-ttu-id="2e583-905">arquivo de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-905">tax file</span></span>
  
<span data-ttu-id="2e583-906">arquivo de impostos não.</span><span class="sxs-lookup"><span data-stu-id="2e583-906">tax file no.</span></span>
  
<span data-ttu-id="2e583-907">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="2e583-907">personal id number</span></span>
  
<span data-ttu-id="2e583-908">skatt ID Nummer</span><span class="sxs-lookup"><span data-stu-id="2e583-908">skatt id nummer</span></span>
  
<span data-ttu-id="2e583-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="2e583-909">skatt identifikation</span></span>
  
<span data-ttu-id="2e583-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="2e583-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="2e583-911">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="2e583-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="2e583-912">Formatar</span><span class="sxs-lookup"><span data-stu-id="2e583-912">Format</span></span>

<span data-ttu-id="2e583-913">Referência de contribuidor exclusivo (UTR): 10 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="2e583-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="2e583-914">Número de seguro nacional (NINO): para obter detalhes, consulte a seção "Reino Unido</span><span class="sxs-lookup"><span data-stu-id="2e583-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="2e583-915">Número de seguro nacional (NINO) "em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2e583-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2e583-916">Padrão</span><span class="sxs-lookup"><span data-stu-id="2e583-916">Pattern</span></span>

<span data-ttu-id="2e583-917">Referência de contribuidor exclusivo (UTR): 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="2e583-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="2e583-918">Número de seguro nacional (NINO): para obter detalhes, consulte a seção "Reino Unido</span><span class="sxs-lookup"><span data-stu-id="2e583-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="2e583-919">Número de seguro nacional (NINO) "em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2e583-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2e583-920">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2e583-920">Checksum</span></span>

<span data-ttu-id="2e583-921">Sim</span><span class="sxs-lookup"><span data-stu-id="2e583-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2e583-922">Definição</span><span class="sxs-lookup"><span data-stu-id="2e583-922">Definition</span></span>

<span data-ttu-id="2e583-923">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="2e583-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2e583-924">A função `Func_uk_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="2e583-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2e583-925">Uma palavra- `Keywords_uk_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="2e583-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e583-926">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2e583-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="2e583-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2e583-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="2e583-928">tax id</span><span class="sxs-lookup"><span data-stu-id="2e583-928">tax id</span></span>
  
<span data-ttu-id="2e583-929">n º de ID de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-929">tax id no.</span></span>
  
<span data-ttu-id="2e583-930">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-930">tax id number</span></span>
  
<span data-ttu-id="2e583-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="2e583-931">tax identification</span></span>
  
<span data-ttu-id="2e583-932">identificação de imposto #</span><span class="sxs-lookup"><span data-stu-id="2e583-932">tax identification#</span></span>
  
<span data-ttu-id="2e583-933">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-933">tax no.</span></span>
  
<span data-ttu-id="2e583-934">imposto #</span><span class="sxs-lookup"><span data-stu-id="2e583-934">tax#</span></span>
  
<span data-ttu-id="2e583-935">táxi #</span><span class="sxs-lookup"><span data-stu-id="2e583-935">taxid#</span></span>
  
<span data-ttu-id="2e583-936">arquivo de imposto</span><span class="sxs-lookup"><span data-stu-id="2e583-936">tax file</span></span>
  
<span data-ttu-id="2e583-937">arquivo de impostos não.</span><span class="sxs-lookup"><span data-stu-id="2e583-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e583-938">Confira também</span><span class="sxs-lookup"><span data-stu-id="2e583-938">See also</span></span>

[<span data-ttu-id="2e583-939">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="2e583-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

