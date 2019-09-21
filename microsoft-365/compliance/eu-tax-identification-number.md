---
title: Número de identificação do imposto da UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação de imposto da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072659"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="44a77-104">Número de identificação do imposto da UE</span><span class="sxs-lookup"><span data-stu-id="44a77-104">EU Tax Identification Number</span></span>

<span data-ttu-id="44a77-105">Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação de imposto (TIN) da UE.</span><span class="sxs-lookup"><span data-stu-id="44a77-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="44a77-106">Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.</span><span class="sxs-lookup"><span data-stu-id="44a77-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="44a77-107">Áustria </span><span class="sxs-lookup"><span data-stu-id="44a77-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="44a77-108">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-108">Format</span></span>

<span data-ttu-id="44a77-109">Nove dígitos com hífen opcional e barra para frente</span><span class="sxs-lookup"><span data-stu-id="44a77-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-110">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-110">Pattern</span></span>

<span data-ttu-id="44a77-111">Nove dígitos com hífen opcional e barra para frente:</span><span class="sxs-lookup"><span data-stu-id="44a77-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="44a77-112">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-112">Two digits</span></span> 
    
- <span data-ttu-id="44a77-113">Um hífen (opcional)</span><span class="sxs-lookup"><span data-stu-id="44a77-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="44a77-114">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-114">Three digits</span></span>
    
- <span data-ttu-id="44a77-115">Uma barra (opcional)</span><span class="sxs-lookup"><span data-stu-id="44a77-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="44a77-116">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-117">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-117">Checksum</span></span>

<span data-ttu-id="44a77-118">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-119">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-119">Definition</span></span>

<span data-ttu-id="44a77-120">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-121">A função `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-122">Uma palavra- `Keywords_austria_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-123">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-124">A função `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-125">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="44a77-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-127">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-127">tax number</span></span>
  
<span data-ttu-id="44a77-128">number</span><span class="sxs-lookup"><span data-stu-id="44a77-128">number</span></span>
  
<span data-ttu-id="44a77-129">número de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-129">tax registration number</span></span>
  
<span data-ttu-id="44a77-130">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-130">tax id</span></span>
  
<span data-ttu-id="44a77-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="44a77-131">st.nr.</span></span>
  
<span data-ttu-id="44a77-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="44a77-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="44a77-133">Bélgica </span><span class="sxs-lookup"><span data-stu-id="44a77-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="44a77-134">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-134">Format</span></span>

<span data-ttu-id="44a77-135">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-136">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-136">Pattern</span></span>

<span data-ttu-id="44a77-137">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44a77-137">11 digits:</span></span>
  
- <span data-ttu-id="44a77-138">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-138">Two digits</span></span>
    
- <span data-ttu-id="44a77-139">Um "0" ou "1"</span><span class="sxs-lookup"><span data-stu-id="44a77-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="44a77-140">Um dígito</span><span class="sxs-lookup"><span data-stu-id="44a77-140">One digit</span></span>
    
- <span data-ttu-id="44a77-141">"0" ou "1" ou "2" ou "3"</span><span class="sxs-lookup"><span data-stu-id="44a77-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="44a77-142">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-143">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-143">Checksum</span></span>

<span data-ttu-id="44a77-144">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-145">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-145">Definition</span></span>

<span data-ttu-id="44a77-146">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-147">A expressão `Regex_belgium_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-148">Uma palavra- `Keywords_belgium_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44a77-149">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="44a77-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-151">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-151">tax number</span></span>
  
<span data-ttu-id="44a77-152">número de Registro Nacional</span><span class="sxs-lookup"><span data-stu-id="44a77-152">national registration number</span></span>
  
<span data-ttu-id="44a77-153">número de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-153">tax registration number</span></span>
  
<span data-ttu-id="44a77-154">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-154">tax id</span></span>
  
<span data-ttu-id="44a77-155">nse</span><span class="sxs-lookup"><span data-stu-id="44a77-155">nif</span></span>
  
<span data-ttu-id="44a77-156">nse #</span><span class="sxs-lookup"><span data-stu-id="44a77-156">nif#</span></span>
  
<span data-ttu-id="44a77-157">Numéro de Registro Nacional</span><span class="sxs-lookup"><span data-stu-id="44a77-157">numéro de registre national</span></span>
  
<span data-ttu-id="44a77-158">Numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="44a77-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="44a77-159">Bulgária</span><span class="sxs-lookup"><span data-stu-id="44a77-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="44a77-160">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-160">Format</span></span>

<span data-ttu-id="44a77-161">Dez dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-162">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-162">Pattern</span></span>

<span data-ttu-id="44a77-163">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-164">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-164">Checksum</span></span>

<span data-ttu-id="44a77-165">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-166">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-166">Definition</span></span>

<span data-ttu-id="44a77-167">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-168">A função `Func_bulgaria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-169">Uma palavra- `Keywords_bulgaria_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-170">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-171">A função `Func_bulgaria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-172">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="44a77-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-174">bucn</span><span class="sxs-lookup"><span data-stu-id="44a77-174">bucn</span></span>
  
<span data-ttu-id="44a77-175">número civil uniforme</span><span class="sxs-lookup"><span data-stu-id="44a77-175">uniform civil number</span></span>
  
<span data-ttu-id="44a77-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="44a77-176">bucn#</span></span>
  
<span data-ttu-id="44a77-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="44a77-178">ID civil uniforme</span><span class="sxs-lookup"><span data-stu-id="44a77-178">uniform civil id</span></span>
  
<span data-ttu-id="44a77-179">Nenhum civil uniforme</span><span class="sxs-lookup"><span data-stu-id="44a77-179">uniform civil no</span></span>
  
<span data-ttu-id="44a77-180">egn</span><span class="sxs-lookup"><span data-stu-id="44a77-180">egn</span></span>
  
<span data-ttu-id="44a77-181">número civil uniforme búlgaro</span><span class="sxs-lookup"><span data-stu-id="44a77-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="44a77-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="44a77-182">uniformcivilno#</span></span>
  
<span data-ttu-id="44a77-183">egn #</span><span class="sxs-lookup"><span data-stu-id="44a77-183">egn#</span></span>
  
<span data-ttu-id="44a77-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="44a77-184">униформ граждански номер</span></span>
  
<span data-ttu-id="44a77-185">ID униформ</span><span class="sxs-lookup"><span data-stu-id="44a77-185">униформ id</span></span>
  
<span data-ttu-id="44a77-186">ID de граждански униформ</span><span class="sxs-lookup"><span data-stu-id="44a77-186">униформ граждански id</span></span>
  
<span data-ttu-id="44a77-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="44a77-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="44a77-188">Croácia</span><span class="sxs-lookup"><span data-stu-id="44a77-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="44a77-189">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-189">Format</span></span>

<span data-ttu-id="44a77-190">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-191">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-191">Pattern</span></span>

<span data-ttu-id="44a77-192">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44a77-192">11 digits:</span></span>
  
- <span data-ttu-id="44a77-193">Dez dígitos, escolhidos aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="44a77-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="44a77-194">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-195">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-195">Checksum</span></span>

<span data-ttu-id="44a77-196">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-197">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-197">Definition</span></span>

<span data-ttu-id="44a77-198">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-199">A função `Func_croatia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-200">Uma palavra- `Keywords_croatia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-201">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-202">A função `Func_croatia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-203">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="44a77-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-205">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-205">tax number</span></span>
  
<span data-ttu-id="44a77-206">imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-206">tax</span></span>
  
<span data-ttu-id="44a77-207">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-207">tax id</span></span>
  
<span data-ttu-id="44a77-208">OID</span><span class="sxs-lookup"><span data-stu-id="44a77-208">oid</span></span>
  
<span data-ttu-id="44a77-209">OID #</span><span class="sxs-lookup"><span data-stu-id="44a77-209">oid#</span></span>
  
<span data-ttu-id="44a77-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="44a77-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="44a77-211">Chipre</span><span class="sxs-lookup"><span data-stu-id="44a77-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="44a77-212">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-212">Format</span></span>

<span data-ttu-id="44a77-213">Oito dígitos e uma letra no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="44a77-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-214">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-214">Pattern</span></span>

<span data-ttu-id="44a77-215">Oito dígitos e uma letra:</span><span class="sxs-lookup"><span data-stu-id="44a77-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="44a77-216">Um "0"</span><span class="sxs-lookup"><span data-stu-id="44a77-216">A "0"</span></span> 
    
- <span data-ttu-id="44a77-217">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44a77-217">Seven digits</span></span>
    
- <span data-ttu-id="44a77-218">Uma letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-219">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-219">Checksum</span></span>

<span data-ttu-id="44a77-220">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-221">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-221">Definition</span></span>

<span data-ttu-id="44a77-222">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-223">A função `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-224">Uma palavra- `Keywords_cyprus_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-225">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-226">A função `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-227">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="44a77-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-229">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-229">tax number</span></span>
  
<span data-ttu-id="44a77-230">imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-230">tax</span></span>
  
<span data-ttu-id="44a77-231">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-231">tax id</span></span>
  
<span data-ttu-id="44a77-232">código de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-232">tax identification code</span></span>
  
<span data-ttu-id="44a77-233">tic</span><span class="sxs-lookup"><span data-stu-id="44a77-233">tic</span></span>
  
<span data-ttu-id="44a77-234">tic #</span><span class="sxs-lookup"><span data-stu-id="44a77-234">tic#</span></span>
  
<span data-ttu-id="44a77-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="44a77-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="44a77-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="44a77-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="44a77-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="44a77-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="44a77-238">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="44a77-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="44a77-239">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-239">Format</span></span>

<span data-ttu-id="44a77-240">Nove ou dez dígitos com uma barra invertida opcional</span><span class="sxs-lookup"><span data-stu-id="44a77-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-241">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-241">Pattern</span></span>

<span data-ttu-id="44a77-242">Nove ou dez dígitos com uma barra invertida opcional:</span><span class="sxs-lookup"><span data-stu-id="44a77-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="44a77-243">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-243">Six digits</span></span> 
    
- <span data-ttu-id="44a77-244">Uma barra invertida (opcional)</span><span class="sxs-lookup"><span data-stu-id="44a77-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="44a77-245">Três ou quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-246">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-246">Checksum</span></span>

<span data-ttu-id="44a77-247">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-248">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-248">Definition</span></span>

<span data-ttu-id="44a77-249">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-250">A expressão `Regex_czech_republic_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-251">Uma palavra- `Keywords_czech_republic_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44a77-252">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="44a77-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-254">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-254">tax number</span></span>
  
<span data-ttu-id="44a77-255">imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-255">tax</span></span>
  
<span data-ttu-id="44a77-256">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-256">tax id</span></span>
  
<span data-ttu-id="44a77-257">número pessoal</span><span class="sxs-lookup"><span data-stu-id="44a77-257">personal number</span></span>
  
<span data-ttu-id="44a77-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="44a77-258">daňové číslo</span></span>
  
<span data-ttu-id="44a77-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="44a77-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="44a77-260">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="44a77-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="44a77-261">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-261">Format</span></span>

<span data-ttu-id="44a77-262">Dez dígitos contendo um hífen</span><span class="sxs-lookup"><span data-stu-id="44a77-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-263">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-263">Pattern</span></span>

<span data-ttu-id="44a77-264">Dez dígitos contendo um hífen:</span><span class="sxs-lookup"><span data-stu-id="44a77-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="44a77-265">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="44a77-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="44a77-266">Um hífen</span><span class="sxs-lookup"><span data-stu-id="44a77-266">A hyphen</span></span>
    
- <span data-ttu-id="44a77-267">Quatro dígitos que correspondem a um número de sequência onde o primeiro dígito corresponde ao século do nascimento e o último dígito corresponde ao sexo da pessoa (ímpar para macho e par para fêmea)</span><span class="sxs-lookup"><span data-stu-id="44a77-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-268">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-268">Checksum</span></span>

<span data-ttu-id="44a77-269">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-270">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-270">Definition</span></span>

<span data-ttu-id="44a77-271">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-272">A função `Func_denmark_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-273">Uma palavra- `Keywords_denmark_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-274">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-275">A função `Func_denmark_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-276">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="44a77-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-278">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-278">tax number</span></span>
  
<span data-ttu-id="44a77-279">imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-279">tax</span></span>
  
<span data-ttu-id="44a77-280">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-280">tax id</span></span>
  
<span data-ttu-id="44a77-281">número de CPR</span><span class="sxs-lookup"><span data-stu-id="44a77-281">cpr number</span></span>
  
<span data-ttu-id="44a77-282">pedir #</span><span class="sxs-lookup"><span data-stu-id="44a77-282">cpr#</span></span>
  
<span data-ttu-id="44a77-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="44a77-283">skat nummer</span></span>
  
<span data-ttu-id="44a77-284">ID Skat</span><span class="sxs-lookup"><span data-stu-id="44a77-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="44a77-285">Estônia</span><span class="sxs-lookup"><span data-stu-id="44a77-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="44a77-286">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-286">Format</span></span>

<span data-ttu-id="44a77-287">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-288">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-288">Pattern</span></span>

<span data-ttu-id="44a77-289">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44a77-289">11 digits:</span></span>
  
-  <span data-ttu-id="44a77-290">Um dígito que corresponde ao gênero e ao século de nascimento onde um número ímpar indica macho e o número par indica fêmea da seguinte maneira: 1, 2 para o século 19; 3, 4 para o século 20; e 5, 6 para o século 21</span><span class="sxs-lookup"><span data-stu-id="44a77-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="44a77-291">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="44a77-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="44a77-292">Três dígitos que correspondem a um número de série separando as pessoas que nasceu na mesma data</span><span class="sxs-lookup"><span data-stu-id="44a77-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="44a77-293">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-294">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-294">Checksum</span></span>

<span data-ttu-id="44a77-295">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-296">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-296">Definition</span></span>

<span data-ttu-id="44a77-297">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-298">A função `Func_estonia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-299">Uma palavra- `Keywords_estonia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-300">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-301">A função `Func_estonia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-302">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="44a77-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-304">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-304">tax number</span></span>
  
<span data-ttu-id="44a77-305">imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-305">tax</span></span>
  
<span data-ttu-id="44a77-306">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-306">tax id</span></span>
  
<span data-ttu-id="44a77-307">código pessoal</span><span class="sxs-lookup"><span data-stu-id="44a77-307">personal code</span></span>
  
<span data-ttu-id="44a77-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="44a77-308">maksunumber</span></span>
  
<span data-ttu-id="44a77-309">ID maksu</span><span class="sxs-lookup"><span data-stu-id="44a77-309">maksu id</span></span>
  
<span data-ttu-id="44a77-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="44a77-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="44a77-311">Finlândia</span><span class="sxs-lookup"><span data-stu-id="44a77-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="44a77-312">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-312">Format</span></span>

<span data-ttu-id="44a77-313">Uma combinação de 11 caracteres de dígitos, letras e sinal de mais e de menos</span><span class="sxs-lookup"><span data-stu-id="44a77-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-314">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-314">Pattern</span></span>

<span data-ttu-id="44a77-315">Uma combinação de 11 caracteres de dígitos, letras e sinal de mais e menos:</span><span class="sxs-lookup"><span data-stu-id="44a77-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="44a77-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-316">Six digits</span></span>
    
- <span data-ttu-id="44a77-317">Uma das seguintes opções: um sinal de adição, um sinal de menos ou a letra "A" (não diferencia maiúsculas de minúsculas) onde o sinal de mais significa que nasceu entre 1800-1899, o sinal de menos significa que nasceu entre 1900-1999 e "A" significa que nasceu 2000 e depois</span><span class="sxs-lookup"><span data-stu-id="44a77-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="44a77-318">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-318">Three digits</span></span>
    
- <span data-ttu-id="44a77-319">Uma letra ou um número</span><span class="sxs-lookup"><span data-stu-id="44a77-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-320">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-320">Checksum</span></span>

<span data-ttu-id="44a77-321">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-322">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-322">Definition</span></span>

<span data-ttu-id="44a77-323">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-324">A função `Func_finland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-325">Uma palavra- `Keywords_finland_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-326">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-327">A função `Func_finland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-328">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="44a77-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-330">identification number</span><span class="sxs-lookup"><span data-stu-id="44a77-330">identification number</span></span>
  
<span data-ttu-id="44a77-331">ID pessoal</span><span class="sxs-lookup"><span data-stu-id="44a77-331">personal id</span></span>
  
<span data-ttu-id="44a77-332">número de identidade</span><span class="sxs-lookup"><span data-stu-id="44a77-332">identity number</span></span>
  
<span data-ttu-id="44a77-333">número de ID nacional da finlandês</span><span class="sxs-lookup"><span data-stu-id="44a77-333">finnish national id number</span></span>
  
<span data-ttu-id="44a77-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-334">personalidnumber#</span></span>
  
<span data-ttu-id="44a77-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="44a77-335">national identification number</span></span>
  
<span data-ttu-id="44a77-336">número de identificação</span><span class="sxs-lookup"><span data-stu-id="44a77-336">id number</span></span>
  
<span data-ttu-id="44a77-337">n º de ID nacional</span><span class="sxs-lookup"><span data-stu-id="44a77-337">national id no.</span></span>
  
<span data-ttu-id="44a77-338">número de ID nacional</span><span class="sxs-lookup"><span data-stu-id="44a77-338">national id number</span></span>
  
<span data-ttu-id="44a77-339">ID não</span><span class="sxs-lookup"><span data-stu-id="44a77-339">id no</span></span>
  
<span data-ttu-id="44a77-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="44a77-340">tunnistenumero</span></span>
  
<span data-ttu-id="44a77-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="44a77-341">henkilötunnus</span></span>
  
<span data-ttu-id="44a77-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="44a77-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="44a77-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="44a77-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="44a77-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="44a77-344">identiteetti numero</span></span>
  
<span data-ttu-id="44a77-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="44a77-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="44a77-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="44a77-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="44a77-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="44a77-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="44a77-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="44a77-348">tunnusnumero</span></span>
  
<span data-ttu-id="44a77-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="44a77-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="44a77-350">França</span><span class="sxs-lookup"><span data-stu-id="44a77-350">France</span></span>

### <a name="format"></a><span data-ttu-id="44a77-351">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-351">Format</span></span>

<span data-ttu-id="44a77-352">13 dígitos para pessoas e nove dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="44a77-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-353">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-353">Pattern</span></span>

<span data-ttu-id="44a77-354">13 dígitos para pessoas:</span><span class="sxs-lookup"><span data-stu-id="44a77-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="44a77-355">Um dígito que deve ser 0, 1, 2 ou 3</span><span class="sxs-lookup"><span data-stu-id="44a77-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="44a77-356">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-356">12 digits</span></span>
    
<span data-ttu-id="44a77-357">Nove dígitos para entidades</span><span class="sxs-lookup"><span data-stu-id="44a77-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-358">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-358">Checksum</span></span>

<span data-ttu-id="44a77-359">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-360">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-360">Definition</span></span>

<span data-ttu-id="44a77-361">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-362">A função `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-363">Uma palavra- `Keywords_france_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-364">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-365">A função `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-366">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="44a77-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-368">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-368">tax identification number</span></span>
  
<span data-ttu-id="44a77-369">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-369">tax number</span></span>
  
<span data-ttu-id="44a77-370">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-370">tax id</span></span>
  
<span data-ttu-id="44a77-371">Numéro d'identification fiscal</span><span class="sxs-lookup"><span data-stu-id="44a77-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="44a77-372">Alemanha</span><span class="sxs-lookup"><span data-stu-id="44a77-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="44a77-373">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-373">Format</span></span>

<span data-ttu-id="44a77-374">11 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-375">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-375">Pattern</span></span>

<span data-ttu-id="44a77-376">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44a77-376">11 digits :</span></span>
  
-  <span data-ttu-id="44a77-377">Dez dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-377">Ten digits</span></span> 
    
- <span data-ttu-id="44a77-378">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-379">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-379">Checksum</span></span>

<span data-ttu-id="44a77-380">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-381">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-381">Definition</span></span>

<span data-ttu-id="44a77-382">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-383">A função `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-384">Uma palavra- `Keywords_germany_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-385">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-386">A função `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-387">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="44a77-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-389">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-389">tax number</span></span>
  
<span data-ttu-id="44a77-390">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-390">tax no.</span></span>
  
<span data-ttu-id="44a77-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-391">taxno#</span></span>
  
<span data-ttu-id="44a77-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-392">taxnumber#</span></span>
  
<span data-ttu-id="44a77-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="44a77-393">taxnumber</span></span>
  
<span data-ttu-id="44a77-394">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-394">tax id</span></span>
  
<span data-ttu-id="44a77-395">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-395">taxid#</span></span>
  
<span data-ttu-id="44a77-396">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-396">tax identification number</span></span>
  
<span data-ttu-id="44a77-397">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-397">tax identification no.</span></span>
  
<span data-ttu-id="44a77-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="44a77-398">steuernummer</span></span>
  
<span data-ttu-id="44a77-399">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="44a77-399">steuer id</span></span>
  
<span data-ttu-id="44a77-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="44a77-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="44a77-401">Grécia</span><span class="sxs-lookup"><span data-stu-id="44a77-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="44a77-402">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-402">Format</span></span>

<span data-ttu-id="44a77-403">Nove dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-404">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-404">Pattern</span></span>

<span data-ttu-id="44a77-405">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-406">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-406">Checksum</span></span>

<span data-ttu-id="44a77-407">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-408">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-408">Definition</span></span>

<span data-ttu-id="44a77-409">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-410">A expressão `Regex_greece_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-411">Uma palavra- `Keywords_greece_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44a77-412">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="44a77-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-414">AFM</span><span class="sxs-lookup"><span data-stu-id="44a77-414">afm</span></span>
  
<span data-ttu-id="44a77-415">Tin</span><span class="sxs-lookup"><span data-stu-id="44a77-415">tin</span></span>
  
<span data-ttu-id="44a77-416">n º de ID de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-416">tax id no.</span></span>
  
<span data-ttu-id="44a77-417">ID de imposto não</span><span class="sxs-lookup"><span data-stu-id="44a77-417">tax id no</span></span>
  
<span data-ttu-id="44a77-418">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-418">tax identification number</span></span>
  
<span data-ttu-id="44a77-419">número do registro de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-419">tax registry number</span></span>
  
<span data-ttu-id="44a77-420">n º do registro de impostos</span><span class="sxs-lookup"><span data-stu-id="44a77-420">tax registry no.</span></span>
  
<span data-ttu-id="44a77-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="44a77-421">afm#</span></span>
  
<span data-ttu-id="44a77-422">Tin #</span><span class="sxs-lookup"><span data-stu-id="44a77-422">tin#</span></span>
  
<span data-ttu-id="44a77-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="44a77-423">taxidno#</span></span>
  
<span data-ttu-id="44a77-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="44a77-424">taxregistryno#</span></span>
  
<span data-ttu-id="44a77-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="44a77-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="44a77-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="44a77-426">aφμ</span></span>
  
<span data-ttu-id="44a77-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="44a77-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="44a77-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="44a77-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="44a77-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="44a77-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="44a77-430">Hungria</span><span class="sxs-lookup"><span data-stu-id="44a77-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="44a77-431">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-431">Format</span></span>

<span data-ttu-id="44a77-432">Dez dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-433">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-433">Pattern</span></span>

<span data-ttu-id="44a77-434">Dez dígitos:</span><span class="sxs-lookup"><span data-stu-id="44a77-434">Ten digits:</span></span>
  
-  <span data-ttu-id="44a77-435">Um dígito que deve ser "8"</span><span class="sxs-lookup"><span data-stu-id="44a77-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="44a77-436">Cinco dígitos que correspondem ao número de dias entre a data 01/01/1867 e a data do nascimento da pessoa</span><span class="sxs-lookup"><span data-stu-id="44a77-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="44a77-437">Três dígitos que correspondem ao número gerado pela chance de diferenciar as pessoas nasceu no mesmo dia</span><span class="sxs-lookup"><span data-stu-id="44a77-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="44a77-438">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-439">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-439">Checksum</span></span>

<span data-ttu-id="44a77-440">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-441">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-441">Definition</span></span>

<span data-ttu-id="44a77-442">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-443">A função `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-444">Uma palavra- `Keywords_hungary_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-445">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-446">A função `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-447">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="44a77-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-449">número de identificação do imposto húngaro</span><span class="sxs-lookup"><span data-stu-id="44a77-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="44a77-450">Tin húngaro</span><span class="sxs-lookup"><span data-stu-id="44a77-450">hungarian tin</span></span>
  
<span data-ttu-id="44a77-451">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-451">tax id number</span></span>
  
<span data-ttu-id="44a77-452">número de IVA</span><span class="sxs-lookup"><span data-stu-id="44a77-452">vat number</span></span>
  
<span data-ttu-id="44a77-453">autoridade de imposto não</span><span class="sxs-lookup"><span data-stu-id="44a77-453">tax authority no</span></span>
  
<span data-ttu-id="44a77-454">número de identidade do imposto ID do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-454">tax id tax identity number</span></span>
  
<span data-ttu-id="44a77-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-455">taxidnumber#</span></span>
  
<span data-ttu-id="44a77-456">Tin #</span><span class="sxs-lookup"><span data-stu-id="44a77-456">tin#</span></span>
  
<span data-ttu-id="44a77-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="44a77-457">hungatiantin#</span></span>
  
<span data-ttu-id="44a77-458">identificação de imposto não</span><span class="sxs-lookup"><span data-stu-id="44a77-458">tax identification no</span></span>
  
<span data-ttu-id="44a77-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="44a77-459">taxidno#</span></span>
  
<span data-ttu-id="44a77-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="44a77-460">adóazonosító szám</span></span>
  
<span data-ttu-id="44a77-461">adószám</span><span class="sxs-lookup"><span data-stu-id="44a77-461">adószám</span></span>
  
<span data-ttu-id="44a77-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="44a77-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="44a77-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="44a77-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="44a77-464">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-464">Format</span></span>

<span data-ttu-id="44a77-465">Sete dígitos seguidos de uma letra sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-466">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-466">Pattern</span></span>

<span data-ttu-id="44a77-467">Sete dígitos seguidos de uma letra:</span><span class="sxs-lookup"><span data-stu-id="44a77-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="44a77-468">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44a77-468">Seven digits</span></span> 
    
- <span data-ttu-id="44a77-469">Uma letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-470">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-470">Checksum</span></span>

<span data-ttu-id="44a77-471">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-472">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-472">Definition</span></span>

<span data-ttu-id="44a77-473">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-474">A função `Func_ireland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-475">Uma palavra- `Keywords_ireland_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-476">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-477">A função `Func_ireland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-478">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="44a77-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-480">serviço público não</span><span class="sxs-lookup"><span data-stu-id="44a77-480">public service no</span></span>
  
<span data-ttu-id="44a77-481">serviço público pessoal não</span><span class="sxs-lookup"><span data-stu-id="44a77-481">personal public service no</span></span>
  
<span data-ttu-id="44a77-482">PPS não</span><span class="sxs-lookup"><span data-stu-id="44a77-482">pps no</span></span>
  
<span data-ttu-id="44a77-483">serviço pessoal não</span><span class="sxs-lookup"><span data-stu-id="44a77-483">personal service no</span></span>
  
<span data-ttu-id="44a77-484">serviço PPS não</span><span class="sxs-lookup"><span data-stu-id="44a77-484">pps service no</span></span>
  
<span data-ttu-id="44a77-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="44a77-485">ppsno#</span></span>
  
<span data-ttu-id="44a77-486">número do PPS do irlandês</span><span class="sxs-lookup"><span data-stu-id="44a77-486">irish pps no</span></span>
  
<span data-ttu-id="44a77-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="44a77-487">publicserviceno#</span></span>
  
<span data-ttu-id="44a77-488">número de serviço público pessoal</span><span class="sxs-lookup"><span data-stu-id="44a77-488">personal public service number</span></span>
  
<span data-ttu-id="44a77-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="44a77-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="44a77-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="44a77-490">pps uimh</span></span>
  
<span data-ttu-id="44a77-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="44a77-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="44a77-492">Itália</span><span class="sxs-lookup"><span data-stu-id="44a77-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="44a77-493">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-493">Format</span></span>

<span data-ttu-id="44a77-494">16 letras e dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="44a77-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-495">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-495">Pattern</span></span>

<span data-ttu-id="44a77-496">16 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="44a77-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="44a77-497">Três letras que correspondem às três primeiras consoantes no nome da família</span><span class="sxs-lookup"><span data-stu-id="44a77-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="44a77-498">Três letras que correspondem à primeira, terceira e quarta consoantes no primeiro nome</span><span class="sxs-lookup"><span data-stu-id="44a77-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="44a77-499">Dois dígitos que correspondem aos últimos dígitos do ano de nascimento</span><span class="sxs-lookup"><span data-stu-id="44a77-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="44a77-500">Um dígito que corresponde ao mês de nascimento-as letras são usadas em ordem alfabética, mas apenas as letras de a a E, H, L, M, P, R a T são usadas (portanto, Janeiro é A e outubro é R)</span><span class="sxs-lookup"><span data-stu-id="44a77-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="44a77-501">Dois dígitos que correspondem ao dia do mês de nascimento, onde 40 é adicionado ao dia de nascimento de mulheres para diferenciar da homens</span><span class="sxs-lookup"><span data-stu-id="44a77-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="44a77-502">Quatro dígitos que correspondem a um código de área específico para o município onde a pessoa nasceu — códigos em todo o país são usados para países estrangeiros</span><span class="sxs-lookup"><span data-stu-id="44a77-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="44a77-503">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-504">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-504">Checksum</span></span>

<span data-ttu-id="44a77-505">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-506">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-506">Definition</span></span>

<span data-ttu-id="44a77-507">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-508">A função `Func_italy_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-509">Uma palavra- `Keywords_italy_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-510">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-511">A função `Func_italy_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-512">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="44a77-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-514">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-514">tax number</span></span>
  
<span data-ttu-id="44a77-515">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-515">tax no.</span></span>
  
<span data-ttu-id="44a77-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-516">taxno#</span></span>
  
<span data-ttu-id="44a77-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-517">taxnumber#</span></span>
  
<span data-ttu-id="44a77-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="44a77-518">taxnumber</span></span>
  
<span data-ttu-id="44a77-519">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-519">tax id</span></span>
  
<span data-ttu-id="44a77-520">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-520">taxid#</span></span>
  
<span data-ttu-id="44a77-521">código fiscal</span><span class="sxs-lookup"><span data-stu-id="44a77-521">fiscal code</span></span>
  
<span data-ttu-id="44a77-522">fiscalização codice</span><span class="sxs-lookup"><span data-stu-id="44a77-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="44a77-523">Letônia</span><span class="sxs-lookup"><span data-stu-id="44a77-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="44a77-524">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-524">Format</span></span>

<span data-ttu-id="44a77-525">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-526">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-526">Pattern</span></span>

<span data-ttu-id="44a77-527">11 dígitos no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="44a77-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="44a77-528">Seis dígitos que correspondem à data de nascimento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="44a77-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="44a77-529">Um dígito que corresponde ao século de nascimento onde "0" corresponde ao século 19, "1" corresponde a 20 Century e "2" corresponde ao século 21</span><span class="sxs-lookup"><span data-stu-id="44a77-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="44a77-530">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-531">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-531">Checksum</span></span>

<span data-ttu-id="44a77-532">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-533">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-533">Definition</span></span>

<span data-ttu-id="44a77-534">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-535">A função `Func_latvia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-536">Uma palavra- `Keywords_latvia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-537">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-538">A função `Func_latvia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-539">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="44a77-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-541">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-541">tax number</span></span>
  
<span data-ttu-id="44a77-542">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-542">tax no.</span></span>
  
<span data-ttu-id="44a77-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-543">taxno#</span></span>
  
<span data-ttu-id="44a77-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-544">taxnumber#</span></span>
  
<span data-ttu-id="44a77-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="44a77-545">taxnumber</span></span>
  
<span data-ttu-id="44a77-546">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-546">tax id</span></span>
  
<span data-ttu-id="44a77-547">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-547">taxid#</span></span>
  
<span data-ttu-id="44a77-548">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-548">tax identification number</span></span>
  
<span data-ttu-id="44a77-549">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-549">tax identification no.</span></span>
  
<span data-ttu-id="44a77-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="44a77-550">nodokļa numurs</span></span>
  
<span data-ttu-id="44a77-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="44a77-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="44a77-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="44a77-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="44a77-553">Lituânia</span><span class="sxs-lookup"><span data-stu-id="44a77-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="44a77-554">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-554">Format</span></span>

<span data-ttu-id="44a77-555">11 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-556">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-556">Pattern</span></span>

<span data-ttu-id="44a77-557">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-558">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-558">Checksum</span></span>

<span data-ttu-id="44a77-559">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-560">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-560">Definition</span></span>

<span data-ttu-id="44a77-561">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-562">A função `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-563">Uma palavra- `Keywords_lithuania_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-564">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-565">A função `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-566">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="44a77-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-568">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-568">tax number</span></span>
  
<span data-ttu-id="44a77-569">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-569">tax no.</span></span>
  
<span data-ttu-id="44a77-570">n º do imposto #</span><span class="sxs-lookup"><span data-stu-id="44a77-570">tax no#</span></span>
  
<span data-ttu-id="44a77-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-571">taxnumber#</span></span>
  
<span data-ttu-id="44a77-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="44a77-572">taxnumber</span></span>
  
<span data-ttu-id="44a77-573">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-573">tax id</span></span>
  
<span data-ttu-id="44a77-574">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-574">taxid#</span></span>
  
<span data-ttu-id="44a77-575">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-575">tax identification number</span></span>
  
<span data-ttu-id="44a77-576">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-576">tax identification no.</span></span>
  
<span data-ttu-id="44a77-577">ID mokesčių</span><span class="sxs-lookup"><span data-stu-id="44a77-577">mokesčių id</span></span>
  
<span data-ttu-id="44a77-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="44a77-578">mokesčių numeris</span></span>
  
<span data-ttu-id="44a77-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="44a77-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="44a77-580">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="44a77-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="44a77-581">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-581">Format</span></span>

<span data-ttu-id="44a77-582">13 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-583">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-583">Pattern</span></span>

<span data-ttu-id="44a77-584">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="44a77-584">13 digits:</span></span>
  
-  <span data-ttu-id="44a77-585">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-585">11 digits</span></span> 
    
- <span data-ttu-id="44a77-586">Dois dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-587">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-587">Checksum</span></span>

<span data-ttu-id="44a77-588">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-589">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-589">Definition</span></span>

<span data-ttu-id="44a77-590">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-591">A função `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-592">Uma palavra- `Keywords_luxemburg_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-593">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-594">A função `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-595">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="44a77-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-597">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-597">tax number</span></span>
  
<span data-ttu-id="44a77-598">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-598">tax no.</span></span>
  
<span data-ttu-id="44a77-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-599">taxno#</span></span>
  
<span data-ttu-id="44a77-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-600">taxnumber#</span></span>
  
<span data-ttu-id="44a77-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="44a77-601">taxnumber</span></span>
  
<span data-ttu-id="44a77-602">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-602">tax id</span></span>
  
<span data-ttu-id="44a77-603">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-603">taxid#</span></span>
  
<span data-ttu-id="44a77-604">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-604">tax identification number</span></span>
  
<span data-ttu-id="44a77-605">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-605">tax identification no.</span></span>
  
<span data-ttu-id="44a77-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="44a77-606">steuernummer</span></span>
  
<span data-ttu-id="44a77-607">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="44a77-607">steuer id</span></span>
  
<span data-ttu-id="44a77-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="44a77-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="44a77-609">Malta</span><span class="sxs-lookup"><span data-stu-id="44a77-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="44a77-610">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-610">Format</span></span>

<span data-ttu-id="44a77-611">Para as nacionalidades maltês: 7 dígitos e uma letra no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="44a77-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="44a77-612">Entidades nacionais e Maltês não-maltês: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-613">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-613">Pattern</span></span>

<span data-ttu-id="44a77-614">Nacionalidades maltês: 7 dígitos e uma letra</span><span class="sxs-lookup"><span data-stu-id="44a77-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="44a77-615">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44a77-615">Seven digits</span></span> 
    
- <span data-ttu-id="44a77-616">Uma letra (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="44a77-617">Entidades nacionais e Maltês não-maltês: 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="44a77-618">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="44a77-619">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-619">Checksum</span></span>

<span data-ttu-id="44a77-620">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-621">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-621">Definition</span></span>

<span data-ttu-id="44a77-622">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-623">A função `Func_malta_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-624">Uma palavra- `Keywords_malta_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-625">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-626">A função `Func_malta_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-627">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="44a77-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-629">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-629">tax number</span></span>
  
<span data-ttu-id="44a77-630">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-630">tax no.</span></span>
  
<span data-ttu-id="44a77-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-631">taxno#</span></span>
  
<span data-ttu-id="44a77-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-632">taxnumber#</span></span>
  
<span data-ttu-id="44a77-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="44a77-633">taxnumber</span></span>
  
<span data-ttu-id="44a77-634">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-634">tax id</span></span>
  
<span data-ttu-id="44a77-635">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-635">taxid#</span></span>
  
<span data-ttu-id="44a77-636">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-636">tax identification number</span></span>
  
<span data-ttu-id="44a77-637">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-637">tax identification no.</span></span>
  
<span data-ttu-id="44a77-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="44a77-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="44a77-639">ID tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="44a77-639">id tat-taxxa</span></span>
  
<span data-ttu-id="44a77-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="44a77-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="44a77-641">Países Baixos</span><span class="sxs-lookup"><span data-stu-id="44a77-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="44a77-642">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-642">Format</span></span>

<span data-ttu-id="44a77-643">Nove dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-644">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-644">Pattern</span></span>

<span data-ttu-id="44a77-645">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="44a77-646">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-646">Checksum</span></span>

<span data-ttu-id="44a77-647">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-648">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-648">Definition</span></span>

<span data-ttu-id="44a77-649">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-650">A função `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-651">Uma palavra- `Keywords_netherlands_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-652">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-653">A função `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-654">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="44a77-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-656">número de identificação do imposto Holanda</span><span class="sxs-lookup"><span data-stu-id="44a77-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="44a77-657">identificação de imposto Holanda</span><span class="sxs-lookup"><span data-stu-id="44a77-657">netherlands tax identification</span></span>
  
<span data-ttu-id="44a77-658">número de identificação de imposto do Netherland</span><span class="sxs-lookup"><span data-stu-id="44a77-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="44a77-659">identificação de imposto do Netherland</span><span class="sxs-lookup"><span data-stu-id="44a77-659">netherland's tax identification</span></span>
  
<span data-ttu-id="44a77-660">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-660">tax identification number</span></span>
  
<span data-ttu-id="44a77-661">ID de imposto holandês</span><span class="sxs-lookup"><span data-stu-id="44a77-661">dutch tax id</span></span>
  
<span data-ttu-id="44a77-662">número de identificação do imposto holandês</span><span class="sxs-lookup"><span data-stu-id="44a77-662">dutch tax identification number</span></span>
  
<span data-ttu-id="44a77-663">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-663">tax id</span></span>
  
<span data-ttu-id="44a77-664">ID de imposto #</span><span class="sxs-lookup"><span data-stu-id="44a77-664">tax id#</span></span>
  
<span data-ttu-id="44a77-665">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-665">tax number</span></span>
  
<span data-ttu-id="44a77-666">n º do imposto #</span><span class="sxs-lookup"><span data-stu-id="44a77-666">tax no#</span></span>
  
<span data-ttu-id="44a77-667">imposto #</span><span class="sxs-lookup"><span data-stu-id="44a77-667">tax#</span></span>
  
<span data-ttu-id="44a77-668">Tin</span><span class="sxs-lookup"><span data-stu-id="44a77-668">tin</span></span>
  
<span data-ttu-id="44a77-669">Tin #</span><span class="sxs-lookup"><span data-stu-id="44a77-669">tin#</span></span>
  
<span data-ttu-id="44a77-670">Tin Holanda</span><span class="sxs-lookup"><span data-stu-id="44a77-670">netherlands tin</span></span>
  
<span data-ttu-id="44a77-671">Tin do Netherland</span><span class="sxs-lookup"><span data-stu-id="44a77-671">netherland's tin</span></span>
  
<span data-ttu-id="44a77-672">Países Baixos identificatienummer</span><span class="sxs-lookup"><span data-stu-id="44a77-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="44a77-673">identificatienummer Van é última</span><span class="sxs-lookup"><span data-stu-id="44a77-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="44a77-674">identificatienummer a última</span><span class="sxs-lookup"><span data-stu-id="44a77-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="44a77-675">Países Baixos identificatie</span><span class="sxs-lookup"><span data-stu-id="44a77-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="44a77-676">Países Baixos Nummer ID da última vez</span><span class="sxs-lookup"><span data-stu-id="44a77-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="44a77-677">Países Baixos belastingnummer</span><span class="sxs-lookup"><span data-stu-id="44a77-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="44a77-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="44a77-678">btw nummer</span></span>
  
<span data-ttu-id="44a77-679">Nederlandse identificatie</span><span class="sxs-lookup"><span data-stu-id="44a77-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="44a77-680">Polônia</span><span class="sxs-lookup"><span data-stu-id="44a77-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="44a77-681">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-681">Format</span></span>

<span data-ttu-id="44a77-682">Onze dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-683">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-683">Pattern</span></span>

<span data-ttu-id="44a77-684">Onze dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-685">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-685">Checksum</span></span>

<span data-ttu-id="44a77-686">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-687">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-687">Definition</span></span>

<span data-ttu-id="44a77-688">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-689">A função `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-690">Uma palavra- `Keywords_poland_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-691">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-692">A função `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-693">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="44a77-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-695">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-695">tax number</span></span>
  
<span data-ttu-id="44a77-696">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-696">tax no.</span></span>
  
<span data-ttu-id="44a77-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-697">taxno#</span></span>
  
<span data-ttu-id="44a77-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-698">taxnumber#</span></span>
  
<span data-ttu-id="44a77-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="44a77-699">taxnumber</span></span>
  
<span data-ttu-id="44a77-700">nip</span><span class="sxs-lookup"><span data-stu-id="44a77-700">nip</span></span>
  
<span data-ttu-id="44a77-701">nip #</span><span class="sxs-lookup"><span data-stu-id="44a77-701">nip#</span></span>
  
<span data-ttu-id="44a77-702">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-702">tax id</span></span>
  
<span data-ttu-id="44a77-703">ID de imposto #</span><span class="sxs-lookup"><span data-stu-id="44a77-703">tax id#</span></span>
  
<span data-ttu-id="44a77-704">ID Nip</span><span class="sxs-lookup"><span data-stu-id="44a77-704">nip id</span></span>
  
<span data-ttu-id="44a77-705">ID Nip #</span><span class="sxs-lookup"><span data-stu-id="44a77-705">nip id#</span></span>
  
<span data-ttu-id="44a77-706">número de identificação do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-706">tax identification number</span></span>
  
<span data-ttu-id="44a77-707">n º de identificação de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-707">tax identification no.</span></span>
  
<span data-ttu-id="44a77-708">número de IVA</span><span class="sxs-lookup"><span data-stu-id="44a77-708">vat number</span></span>
  
<span data-ttu-id="44a77-709">IVA não.</span><span class="sxs-lookup"><span data-stu-id="44a77-709">vat no.</span></span>
  
<span data-ttu-id="44a77-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="44a77-710">vatno#</span></span>
  
<span data-ttu-id="44a77-711">ID de IVA</span><span class="sxs-lookup"><span data-stu-id="44a77-711">vat id</span></span>
  
<span data-ttu-id="44a77-712">ID de IVA #</span><span class="sxs-lookup"><span data-stu-id="44a77-712">vat id#</span></span>
  
<span data-ttu-id="44a77-713">numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="44a77-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="44a77-714">polski numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="44a77-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="44a77-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="44a77-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="44a77-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="44a77-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="44a77-717">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-717">Format</span></span>

<span data-ttu-id="44a77-718">Nove dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-719">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-719">Pattern</span></span>

<span data-ttu-id="44a77-720">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-721">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-721">Checksum</span></span>

<span data-ttu-id="44a77-722">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-723">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-723">Definition</span></span>

<span data-ttu-id="44a77-724">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-725">A função `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-726">Uma palavra- `Keywords_portugal_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-727">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-728">A função `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-729">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="44a77-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-731">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-731">tax number</span></span>
  
<span data-ttu-id="44a77-732">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-732">tax no.</span></span>
  
<span data-ttu-id="44a77-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-733">taxno#</span></span>
  
<span data-ttu-id="44a77-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="44a77-734">taxnumber#</span></span>
  
<span data-ttu-id="44a77-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="44a77-735">taxnumber</span></span>
  
<span data-ttu-id="44a77-736">nse</span><span class="sxs-lookup"><span data-stu-id="44a77-736">nif</span></span>
  
<span data-ttu-id="44a77-737">nse #</span><span class="sxs-lookup"><span data-stu-id="44a77-737">nif#</span></span>
  
<span data-ttu-id="44a77-738">fiscal numero</span><span class="sxs-lookup"><span data-stu-id="44a77-738">numero fiscal</span></span>
  
<span data-ttu-id="44a77-739">número de identificação fiscal</span><span class="sxs-lookup"><span data-stu-id="44a77-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="44a77-740">Romênia</span><span class="sxs-lookup"><span data-stu-id="44a77-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="44a77-741">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-741">Format</span></span>

<span data-ttu-id="44a77-742">13 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-743">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-743">Pattern</span></span>

<span data-ttu-id="44a77-744">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-745">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-745">Checksum</span></span>

<span data-ttu-id="44a77-746">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-747">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-747">Definition</span></span>

<span data-ttu-id="44a77-748">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-749">A expressão `Regex_romania_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-750">Uma palavra- `Keywords_romania_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44a77-751">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="44a77-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-753">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-753">tax id</span></span>
  
<span data-ttu-id="44a77-754">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-754">tax id number</span></span>
  
<span data-ttu-id="44a77-755">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="44a77-755">tax file no</span></span>
  
<span data-ttu-id="44a77-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="44a77-756">tax file number</span></span>
  
<span data-ttu-id="44a77-757">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-757">tax no</span></span>
  
<span data-ttu-id="44a77-758">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-758">tax number</span></span>
  
<span data-ttu-id="44a77-759">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-759">taxid#</span></span>
  
<span data-ttu-id="44a77-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-760">taxno#</span></span>
  
<span data-ttu-id="44a77-761">ID-UL Taxei</span><span class="sxs-lookup"><span data-stu-id="44a77-761">id-ul taxei</span></span>
  
<span data-ttu-id="44a77-762">numărul de identificare Fiscală</span><span class="sxs-lookup"><span data-stu-id="44a77-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="44a77-763">Eslováquia</span><span class="sxs-lookup"><span data-stu-id="44a77-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="44a77-764">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-764">Format</span></span>

<span data-ttu-id="44a77-765">10 dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-766">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-766">Pattern</span></span>

<span data-ttu-id="44a77-767">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-768">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-768">Checksum</span></span>

<span data-ttu-id="44a77-769">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="44a77-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-770">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-770">Definition</span></span>

<span data-ttu-id="44a77-771">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-772">A expressão `Regex_slovakia_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-773">Uma palavra- `Keywords_slovakia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44a77-774">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="44a77-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-776">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-776">tax id</span></span>
  
<span data-ttu-id="44a77-777">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-777">tax id number</span></span>
  
<span data-ttu-id="44a77-778">ID do Tin</span><span class="sxs-lookup"><span data-stu-id="44a77-778">tin id</span></span>
  
<span data-ttu-id="44a77-779">Tin não</span><span class="sxs-lookup"><span data-stu-id="44a77-779">tin no</span></span>
  
<span data-ttu-id="44a77-780">ID de Tin de eslovaco</span><span class="sxs-lookup"><span data-stu-id="44a77-780">slovakian tin id</span></span>
  
<span data-ttu-id="44a77-781">Tin</span><span class="sxs-lookup"><span data-stu-id="44a77-781">tin</span></span>
  
<span data-ttu-id="44a77-782">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="44a77-782">tax file no</span></span>
  
<span data-ttu-id="44a77-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="44a77-783">tax file number</span></span>
  
<span data-ttu-id="44a77-784">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-784">tax no</span></span>
  
<span data-ttu-id="44a77-785">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-785">tax number</span></span>
  
<span data-ttu-id="44a77-786">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-786">taxid#</span></span>
  
<span data-ttu-id="44a77-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-787">taxno#</span></span>
  
<span data-ttu-id="44a77-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="44a77-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="44a77-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="44a77-789">daňové číslo</span></span>
  
<span data-ttu-id="44a77-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="44a77-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="44a77-791">Eslovênia</span><span class="sxs-lookup"><span data-stu-id="44a77-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="44a77-792">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-792">Format</span></span>

<span data-ttu-id="44a77-793">Oito dígitos sem espaços ou delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-794">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-794">Pattern</span></span>

<span data-ttu-id="44a77-795">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-796">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-796">Checksum</span></span>

<span data-ttu-id="44a77-797">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-798">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-798">Definition</span></span>

<span data-ttu-id="44a77-799">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-800">A função `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-801">Uma palavra- `Keywords_slovenia_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-802">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-803">A função `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-804">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="44a77-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-806">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-806">tax id</span></span>
  
<span data-ttu-id="44a77-807">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-807">tax id number</span></span>
  
<span data-ttu-id="44a77-808">ID do Tin</span><span class="sxs-lookup"><span data-stu-id="44a77-808">tin id</span></span>
  
<span data-ttu-id="44a77-809">Tin não</span><span class="sxs-lookup"><span data-stu-id="44a77-809">tin no</span></span>
  
<span data-ttu-id="44a77-810">ID de Tin esloveno</span><span class="sxs-lookup"><span data-stu-id="44a77-810">slovenian tin id</span></span>
  
<span data-ttu-id="44a77-811">Tin</span><span class="sxs-lookup"><span data-stu-id="44a77-811">tin</span></span>
  
<span data-ttu-id="44a77-812">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="44a77-812">tax file no</span></span>
  
<span data-ttu-id="44a77-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="44a77-813">tax file number</span></span>
  
<span data-ttu-id="44a77-814">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-814">tax no</span></span>
  
<span data-ttu-id="44a77-815">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-815">tax number</span></span>
  
<span data-ttu-id="44a77-816">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-816">taxid#</span></span>
  
<span data-ttu-id="44a77-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-817">taxno#</span></span>
  
<span data-ttu-id="44a77-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="44a77-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="44a77-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="44a77-819">davčna številka</span></span>
  
<span data-ttu-id="44a77-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="44a77-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="44a77-821">Espanha</span><span class="sxs-lookup"><span data-stu-id="44a77-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="44a77-822">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-822">Format</span></span>

<span data-ttu-id="44a77-823">Sete ou oito dígitos e uma ou duas letras no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="44a77-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-824">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-824">Pattern</span></span>

<span data-ttu-id="44a77-825">Pessoas naturais do espanhol com um cartão de identidade nacional da Espanha:</span><span class="sxs-lookup"><span data-stu-id="44a77-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="44a77-826">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-826">Eight digits</span></span> 
    
- <span data-ttu-id="44a77-827">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="44a77-828">Spaniards não residente sem um cartão de identidade nacional da Espanha</span><span class="sxs-lookup"><span data-stu-id="44a77-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="44a77-829">Uma letra maiúscula "L" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="44a77-830">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44a77-830">Seven digits</span></span>
    
- <span data-ttu-id="44a77-831">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="44a77-832">Spaniards residentes sob a idade de 14 anos sem um cartão de identidade nacional da Espanha:</span><span class="sxs-lookup"><span data-stu-id="44a77-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="44a77-833">Uma letra maiúscula "K" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="44a77-834">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44a77-834">Seven digits</span></span> 
    
- <span data-ttu-id="44a77-835">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="44a77-836">Foreigners com o número de identificação do estrangeiro</span><span class="sxs-lookup"><span data-stu-id="44a77-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="44a77-837">Uma letra maiúscula que é "X", "Y" ou "Z" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="44a77-838">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44a77-838">Seven digits</span></span>
    
- <span data-ttu-id="44a77-839">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="44a77-840">Foreigners sem um número de identificação do estrangeiro</span><span class="sxs-lookup"><span data-stu-id="44a77-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="44a77-841">Uma letra maiúscula que é "M" (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="44a77-842">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="44a77-842">Seven digits</span></span>
    
- <span data-ttu-id="44a77-843">Uma letra maiúscula (diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="44a77-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="44a77-844">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-844">Checksum</span></span>

<span data-ttu-id="44a77-845">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-846">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-846">Definition</span></span>

<span data-ttu-id="44a77-847">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-848">A função `Func_spain_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-849">Uma palavra- `Keywords_spain_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-850">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-851">A função `Func_spain_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-852">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="44a77-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-854">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-854">tax id</span></span>
  
<span data-ttu-id="44a77-855">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-855">tax id number</span></span>
  
<span data-ttu-id="44a77-856">ID de CIF</span><span class="sxs-lookup"><span data-stu-id="44a77-856">cif id</span></span>
  
<span data-ttu-id="44a77-857">Não CIF</span><span class="sxs-lookup"><span data-stu-id="44a77-857">cif no</span></span>
  
<span data-ttu-id="44a77-858">ID de CIF espanhol</span><span class="sxs-lookup"><span data-stu-id="44a77-858">spanish cif id</span></span>
  
<span data-ttu-id="44a77-859">CIF</span><span class="sxs-lookup"><span data-stu-id="44a77-859">cif</span></span>
  
<span data-ttu-id="44a77-860">arquivo de imposto não</span><span class="sxs-lookup"><span data-stu-id="44a77-860">tax file no</span></span>
  
<span data-ttu-id="44a77-861">número de CIF espanhol</span><span class="sxs-lookup"><span data-stu-id="44a77-861">spanish cif number</span></span>
  
<span data-ttu-id="44a77-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="44a77-862">tax file number</span></span>
  
<span data-ttu-id="44a77-863">Não CIF espanhol</span><span class="sxs-lookup"><span data-stu-id="44a77-863">spanish cif no</span></span>
  
<span data-ttu-id="44a77-864">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-864">tax no</span></span>
  
<span data-ttu-id="44a77-865">número do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-865">tax number</span></span>
  
<span data-ttu-id="44a77-866">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-866">taxid#</span></span>
  
<span data-ttu-id="44a77-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="44a77-867">taxno#</span></span>
  
<span data-ttu-id="44a77-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="44a77-868">cifid#</span></span>
  
<span data-ttu-id="44a77-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="44a77-869">spanishcifid#</span></span>
  
<span data-ttu-id="44a77-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="44a77-870">spanishcifno#</span></span>
  
<span data-ttu-id="44a77-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="44a77-871">número de contribuyente</span></span>
  
<span data-ttu-id="44a77-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="44a77-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="44a77-873">número de Identificación fiscal</span><span class="sxs-lookup"><span data-stu-id="44a77-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="44a77-874">número CIF</span><span class="sxs-lookup"><span data-stu-id="44a77-874">cif número</span></span>
  
<span data-ttu-id="44a77-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="44a77-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="44a77-876">Suécia</span><span class="sxs-lookup"><span data-stu-id="44a77-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="44a77-877">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-877">Format</span></span>

<span data-ttu-id="44a77-878">Dez dígitos e um símbolo no padrão especificado</span><span class="sxs-lookup"><span data-stu-id="44a77-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-879">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-879">Pattern</span></span>

<span data-ttu-id="44a77-880">Dez dígitos e um símbolo:</span><span class="sxs-lookup"><span data-stu-id="44a77-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="44a77-881">Seis dígitos que correspondem à data de nascimento (AAMMDD)</span><span class="sxs-lookup"><span data-stu-id="44a77-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="44a77-882">Um sinal de adição, sinal de menos ou barra invertida</span><span class="sxs-lookup"><span data-stu-id="44a77-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="44a77-883">Três dígitos que tornam o número de identificação exclusivo, onde:</span><span class="sxs-lookup"><span data-stu-id="44a77-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="44a77-884">Para números emitidos antes de 1990, o sétimo e oitavo dígito identificam o Condado de nascimento ou pessoas de nasceu</span><span class="sxs-lookup"><span data-stu-id="44a77-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="44a77-885">O dígito na nona posição indica sexo por tanto ímpar para masculino ou par para fêmea</span><span class="sxs-lookup"><span data-stu-id="44a77-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="44a77-886">Um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="44a77-887">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-887">Checksum</span></span>

<span data-ttu-id="44a77-888">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-889">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-889">Definition</span></span>

<span data-ttu-id="44a77-890">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-891">A função `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-892">Uma palavra- `Keywords_sweden_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="44a77-893">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-894">A função `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="44a77-895">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="44a77-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-897">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-897">tax id</span></span>
  
<span data-ttu-id="44a77-898">n º de ID de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-898">tax id no.</span></span>
  
<span data-ttu-id="44a77-899">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-899">tax id number</span></span>
  
<span data-ttu-id="44a77-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="44a77-900">tax identification</span></span>
  
<span data-ttu-id="44a77-901">identificação de imposto #</span><span class="sxs-lookup"><span data-stu-id="44a77-901">tax identification#</span></span>
  
<span data-ttu-id="44a77-902">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-902">tax no.</span></span>
  
<span data-ttu-id="44a77-903">imposto #</span><span class="sxs-lookup"><span data-stu-id="44a77-903">tax#</span></span>
  
<span data-ttu-id="44a77-904">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-904">taxid#</span></span>
  
<span data-ttu-id="44a77-905">arquivo de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-905">tax file</span></span>
  
<span data-ttu-id="44a77-906">arquivo de impostos não.</span><span class="sxs-lookup"><span data-stu-id="44a77-906">tax file no.</span></span>
  
<span data-ttu-id="44a77-907">número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="44a77-907">personal id number</span></span>
  
<span data-ttu-id="44a77-908">skatt ID Nummer</span><span class="sxs-lookup"><span data-stu-id="44a77-908">skatt id nummer</span></span>
  
<span data-ttu-id="44a77-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="44a77-909">skatt identifikation</span></span>
  
<span data-ttu-id="44a77-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="44a77-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="44a77-911">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="44a77-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="44a77-912">Formatar</span><span class="sxs-lookup"><span data-stu-id="44a77-912">Format</span></span>

<span data-ttu-id="44a77-913">Referência de contribuidor exclusivo (UTR): 10 dígitos sem espaços e delimitadores</span><span class="sxs-lookup"><span data-stu-id="44a77-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="44a77-914">Número de seguro nacional (NINO): para obter detalhes, consulte a seção "Reino Unido</span><span class="sxs-lookup"><span data-stu-id="44a77-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="44a77-915">Número de seguro nacional (NINO) "em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44a77-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="44a77-916">Padrão</span><span class="sxs-lookup"><span data-stu-id="44a77-916">Pattern</span></span>

<span data-ttu-id="44a77-917">Referência de contribuidor exclusivo (UTR): 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="44a77-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="44a77-918">Número de seguro nacional (NINO): para obter detalhes, consulte a seção "Reino Unido</span><span class="sxs-lookup"><span data-stu-id="44a77-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="44a77-919">Número de seguro nacional (NINO) "em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="44a77-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="44a77-920">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="44a77-920">Checksum</span></span>

<span data-ttu-id="44a77-921">Sim</span><span class="sxs-lookup"><span data-stu-id="44a77-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="44a77-922">Definição</span><span class="sxs-lookup"><span data-stu-id="44a77-922">Definition</span></span>

<span data-ttu-id="44a77-923">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="44a77-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="44a77-924">A função `Func_uk_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="44a77-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="44a77-925">Uma palavra- `Keywords_uk_eu_tax_file_number` chave de foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="44a77-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="44a77-926">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44a77-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="44a77-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="44a77-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="44a77-928">tax id</span><span class="sxs-lookup"><span data-stu-id="44a77-928">tax id</span></span>
  
<span data-ttu-id="44a77-929">n º de ID de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-929">tax id no.</span></span>
  
<span data-ttu-id="44a77-930">número de ID do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-930">tax id number</span></span>
  
<span data-ttu-id="44a77-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="44a77-931">tax identification</span></span>
  
<span data-ttu-id="44a77-932">identificação de imposto #</span><span class="sxs-lookup"><span data-stu-id="44a77-932">tax identification#</span></span>
  
<span data-ttu-id="44a77-933">n º do imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-933">tax no.</span></span>
  
<span data-ttu-id="44a77-934">imposto #</span><span class="sxs-lookup"><span data-stu-id="44a77-934">tax#</span></span>
  
<span data-ttu-id="44a77-935">táxi #</span><span class="sxs-lookup"><span data-stu-id="44a77-935">taxid#</span></span>
  
<span data-ttu-id="44a77-936">arquivo de imposto</span><span class="sxs-lookup"><span data-stu-id="44a77-936">tax file</span></span>
  
<span data-ttu-id="44a77-937">arquivo de impostos não.</span><span class="sxs-lookup"><span data-stu-id="44a77-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44a77-938">Confira também</span><span class="sxs-lookup"><span data-stu-id="44a77-938">See also</span></span>

[<span data-ttu-id="44a77-939">O que os tipos de informações confidenciais procuram</span><span class="sxs-lookup"><span data-stu-id="44a77-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

