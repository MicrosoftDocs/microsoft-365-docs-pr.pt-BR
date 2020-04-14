---
title: O que os tipos de informações confidenciais procuram
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: A prevenção de perda de dados (DLP) no centro &amp; de conformidade de segurança do Office 365 80 inclui tipos de informações confidenciais que estão prontos para uso nas suas políticas de DLP. Este tópico lista todos os tipos de informações confidenciais e mostra o que uma política de DLP procura ao detectar cada tipo.
ms.openlocfilehash: aa3a08961ccad92c9986db16c1d8180d9b0cd17e
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240274"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="a1757-104">O que os tipos de informações confidenciais procuram</span><span class="sxs-lookup"><span data-stu-id="a1757-104">What the sensitive information types look for</span></span>

<span data-ttu-id="a1757-105">A prevenção de perda de dados (DLP) no centro &amp; de conformidade de segurança do Office 365 inclui muitos tipos de informações confidenciais que estão prontos para uso nas suas políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="a1757-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="a1757-106">Este tópico lista todos os tipos de informações confidenciais e mostra o que uma política de DLP procura ao detectar cada tipo.</span><span class="sxs-lookup"><span data-stu-id="a1757-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="a1757-107">Um tipo de informação confidencial é definido por um padrão que pode ser identificado por uma função ou uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="a1757-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="a1757-108">Além disso, evidências corroborativas, como palavras-chave e somas de verificação, podem ser usadas para identificar um tipo de informação confidencial.</span><span class="sxs-lookup"><span data-stu-id="a1757-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="a1757-109">O nível de confiança e a proximidade também são usados no processo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="a1757-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="a1757-110">Número de roteamento ABA</span><span class="sxs-lookup"><span data-stu-id="a1757-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-111">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-111">Format</span></span>

<span data-ttu-id="a1757-112">9 dígitos que podem estar em um padrão formatado ou não formatado</span><span class="sxs-lookup"><span data-stu-id="a1757-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-113">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-113">Pattern</span></span>

<span data-ttu-id="a1757-114">Binário</span><span class="sxs-lookup"><span data-stu-id="a1757-114">Formatted:</span></span>
- <span data-ttu-id="a1757-115">Quatro dígitos, começando com 0, 1, 2, 3, 6, 7 ou 8</span><span class="sxs-lookup"><span data-stu-id="a1757-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="a1757-116">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-116">A hyphen</span></span>
- <span data-ttu-id="a1757-117">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-117">Four digits</span></span>
- <span data-ttu-id="a1757-118">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-118">A hyphen</span></span>
- <span data-ttu-id="a1757-119">Um dígito</span><span class="sxs-lookup"><span data-stu-id="a1757-119">A digit</span></span>

<span data-ttu-id="a1757-120">Não formatado: 9 dígitos consecutivos começando com 0, 1, 2, 3, 6, 7 ou 8</span><span class="sxs-lookup"><span data-stu-id="a1757-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="a1757-121">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-121">Checksum</span></span>

<span data-ttu-id="a1757-122">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-123">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-123">Definition</span></span>

<span data-ttu-id="a1757-124">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-125">A função Func_aba_routing localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-126">Uma palavra-chave de Keyword_ABA_Routing for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="a1757-127">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="a1757-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="a1757-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="a1757-129">aba</span><span class="sxs-lookup"><span data-stu-id="a1757-129">aba</span></span>
- <span data-ttu-id="a1757-130">aba #</span><span class="sxs-lookup"><span data-stu-id="a1757-130">aba #</span></span>
- <span data-ttu-id="a1757-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="a1757-131">aba routing #</span></span>
- <span data-ttu-id="a1757-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="a1757-132">aba routing number</span></span>
- <span data-ttu-id="a1757-133">aba #</span><span class="sxs-lookup"><span data-stu-id="a1757-133">aba#</span></span>
- <span data-ttu-id="a1757-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="a1757-134">abarouting#</span></span>
- <span data-ttu-id="a1757-135">aba number</span><span class="sxs-lookup"><span data-stu-id="a1757-135">aba number</span></span>
- <span data-ttu-id="a1757-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-136">abaroutingnumber</span></span>
- <span data-ttu-id="a1757-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="a1757-137">american bank association routing #</span></span>
- <span data-ttu-id="a1757-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="a1757-138">american bank association routing number</span></span>
- <span data-ttu-id="a1757-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="a1757-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="a1757-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="a1757-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="a1757-141">bank routing number</span></span>
- <span data-ttu-id="a1757-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="a1757-142">bankrouting#</span></span>
- <span data-ttu-id="a1757-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-143">bankroutingnumber</span></span>
- <span data-ttu-id="a1757-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="a1757-144">routing transit number</span></span>
- <span data-ttu-id="a1757-145">RTN</span><span class="sxs-lookup"><span data-stu-id="a1757-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="a1757-146">Número de Identidade Nacional (DNI) da Argentina</span><span class="sxs-lookup"><span data-stu-id="a1757-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-147">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-147">Format</span></span>

<span data-ttu-id="a1757-148">Oito dígitos separados por pontos</span><span class="sxs-lookup"><span data-stu-id="a1757-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-149">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-149">Pattern</span></span>

<span data-ttu-id="a1757-150">Oito dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-150">Eight digits:</span></span>
- <span data-ttu-id="a1757-151">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-151">Two digits</span></span>
- <span data-ttu-id="a1757-152">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-152">A period</span></span>
- <span data-ttu-id="a1757-153">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-153">Three digits</span></span>
- <span data-ttu-id="a1757-154">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-154">A period</span></span>
- <span data-ttu-id="a1757-155">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-156">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-156">Checksum</span></span>

<span data-ttu-id="a1757-157">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-158">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-158">Definition</span></span>

<span data-ttu-id="a1757-159">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-160">A expressão regular Regex_argentina_national_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-161">Uma palavra-chave de Keyword_argentina_national_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-162">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="a1757-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="a1757-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="a1757-164">Número de Identidade Nacional da Argentina</span><span class="sxs-lookup"><span data-stu-id="a1757-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="a1757-165">Identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-165">Identity</span></span> 
- <span data-ttu-id="a1757-166">Identificar cartão de identidade nacional</span><span class="sxs-lookup"><span data-stu-id="a1757-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="a1757-167">DNI</span><span class="sxs-lookup"><span data-stu-id="a1757-167">DNI</span></span> 
- <span data-ttu-id="a1757-168">Registro Nacional de pessoas da NIC</span><span class="sxs-lookup"><span data-stu-id="a1757-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="a1757-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="a1757-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="a1757-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="a1757-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="a1757-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="a1757-171">Identidad</span></span> 
- <span data-ttu-id="a1757-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="a1757-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="a1757-173">Número de conta de banco da Austrália</span><span class="sxs-lookup"><span data-stu-id="a1757-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-174">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-174">Format</span></span>

<span data-ttu-id="a1757-175">6 a 10 dígitos com ou sem um número BSB</span><span class="sxs-lookup"><span data-stu-id="a1757-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-176">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-176">Pattern</span></span>

<span data-ttu-id="a1757-177">Número de conta é 6 de 10 dígitos.</span><span class="sxs-lookup"><span data-stu-id="a1757-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="a1757-178">Número BSB da Austrália:</span><span class="sxs-lookup"><span data-stu-id="a1757-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="a1757-179">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-179">Three digits</span></span> 
- <span data-ttu-id="a1757-180">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-180">A hyphen</span></span> 
- <span data-ttu-id="a1757-181">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-182">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-182">Checksum</span></span>

<span data-ttu-id="a1757-183">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-184">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-184">Definition</span></span>

<span data-ttu-id="a1757-185">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-186">A expressão regular Regex_australia_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a1757-187">Uma palavra-chave de Keyword_australia_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="a1757-188">A expressão regular Regex_australia_bank_account_number_bsb localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="a1757-189">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-190">A expressão regular Regex_australia_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a1757-191">Uma palavra-chave de Keyword_australia_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-192">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="a1757-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a1757-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="a1757-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="a1757-194">swift bank code</span></span>
- <span data-ttu-id="a1757-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="a1757-195">correspondent bank</span></span>
- <span data-ttu-id="a1757-196">base currency</span><span class="sxs-lookup"><span data-stu-id="a1757-196">base currency</span></span>
- <span data-ttu-id="a1757-197">usa account</span><span class="sxs-lookup"><span data-stu-id="a1757-197">usa account</span></span>
- <span data-ttu-id="a1757-198">holder address</span><span class="sxs-lookup"><span data-stu-id="a1757-198">holder address</span></span>
- <span data-ttu-id="a1757-199">bank address</span><span class="sxs-lookup"><span data-stu-id="a1757-199">bank address</span></span>
- <span data-ttu-id="a1757-200">information account</span><span class="sxs-lookup"><span data-stu-id="a1757-200">information account</span></span>
- <span data-ttu-id="a1757-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="a1757-201">fund transfers</span></span>
- <span data-ttu-id="a1757-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="a1757-202">bank charges</span></span>
- <span data-ttu-id="a1757-203">bank details</span><span class="sxs-lookup"><span data-stu-id="a1757-203">bank details</span></span>
- <span data-ttu-id="a1757-204">banking information</span><span class="sxs-lookup"><span data-stu-id="a1757-204">banking information</span></span>
- <span data-ttu-id="a1757-205">full names</span><span class="sxs-lookup"><span data-stu-id="a1757-205">full names</span></span>
- <span data-ttu-id="a1757-206">iaea</span><span class="sxs-lookup"><span data-stu-id="a1757-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="a1757-207">Número de carteira de motorista da Austrália</span><span class="sxs-lookup"><span data-stu-id="a1757-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-208">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-208">Format</span></span>

<span data-ttu-id="a1757-209">Nove letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-210">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-210">Pattern</span></span>

<span data-ttu-id="a1757-211">Nove letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="a1757-212">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-213">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-213">Two digits</span></span> 
- <span data-ttu-id="a1757-214">Cinco dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="a1757-215">OU</span><span class="sxs-lookup"><span data-stu-id="a1757-215">OR</span></span>

- <span data-ttu-id="a1757-216">1 a 2 letras opcionais (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-217">4 a 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-217">4-9 digits</span></span>

<span data-ttu-id="a1757-218">OU</span><span class="sxs-lookup"><span data-stu-id="a1757-218">OR</span></span>

- <span data-ttu-id="a1757-219">Nove dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-220">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-220">Checksum</span></span>

<span data-ttu-id="a1757-221">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-222">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-222">Definition</span></span>

<span data-ttu-id="a1757-223">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-224">A expressão regular Regex_australia_drivers_license_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-225">Uma palavra-chave de Keyword_australia_drivers_license_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="a1757-226">Nenhuma palavra-chave de Keyword_australia_drivers_license_number_exclusions for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-227">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="a1757-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a1757-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="a1757-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="a1757-229">international driving permits</span></span>
- <span data-ttu-id="a1757-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="a1757-230">australian automobile association</span></span>
- <span data-ttu-id="a1757-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="a1757-231">international driving permit</span></span>
- <span data-ttu-id="a1757-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="a1757-232">DriverLicence</span></span>
- <span data-ttu-id="a1757-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a1757-233">DriverLicences</span></span>
- <span data-ttu-id="a1757-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-234">Driver Lic</span></span>
- <span data-ttu-id="a1757-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-235">Driver Licence</span></span>
- <span data-ttu-id="a1757-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-236">Driver Licences</span></span>
- <span data-ttu-id="a1757-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a1757-237">DriversLic</span></span>
- <span data-ttu-id="a1757-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="a1757-238">DriversLicence</span></span>
- <span data-ttu-id="a1757-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a1757-239">DriversLicences</span></span>
- <span data-ttu-id="a1757-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-240">Drivers Lic</span></span>
- <span data-ttu-id="a1757-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-241">Drivers Lics</span></span>
- <span data-ttu-id="a1757-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-242">Drivers Licence</span></span>
- <span data-ttu-id="a1757-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-243">Drivers Licences</span></span>
- <span data-ttu-id="a1757-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-244">Driver'Lic</span></span>
- <span data-ttu-id="a1757-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-245">Driver'Lics</span></span>
- <span data-ttu-id="a1757-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-246">Driver'Licence</span></span>
- <span data-ttu-id="a1757-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-247">Driver'Licences</span></span>
- <span data-ttu-id="a1757-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-248">Driver' Lic</span></span>
- <span data-ttu-id="a1757-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-249">Driver' Lics</span></span>
- <span data-ttu-id="a1757-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-250">Driver' Licence</span></span>
- <span data-ttu-id="a1757-251">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-251">Driver' Licences</span></span>
- <span data-ttu-id="a1757-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a1757-252">Driver'sLic</span></span>
- <span data-ttu-id="a1757-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a1757-253">Driver'sLics</span></span>
- <span data-ttu-id="a1757-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="a1757-254">Driver'sLicence</span></span>
- <span data-ttu-id="a1757-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a1757-255">Driver'sLicences</span></span>
- <span data-ttu-id="a1757-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-256">Driver's Lic</span></span>
- <span data-ttu-id="a1757-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-257">Driver's Lics</span></span>
- <span data-ttu-id="a1757-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-258">Driver's Licence</span></span>
- <span data-ttu-id="a1757-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-259">Driver's Licences</span></span>
- <span data-ttu-id="a1757-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="a1757-260">DriverLic#</span></span>
- <span data-ttu-id="a1757-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="a1757-261">DriverLics#</span></span>
- <span data-ttu-id="a1757-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="a1757-262">DriverLicence#</span></span>
- <span data-ttu-id="a1757-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="a1757-263">DriverLicences#</span></span>
- <span data-ttu-id="a1757-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-264">Driver Lic#</span></span>
- <span data-ttu-id="a1757-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-265">Driver Lics#</span></span>
- <span data-ttu-id="a1757-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="a1757-266">Driver Licence#</span></span>
- <span data-ttu-id="a1757-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="a1757-267">Driver Licences#</span></span>
- <span data-ttu-id="a1757-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="a1757-268">DriversLic#</span></span>
- <span data-ttu-id="a1757-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="a1757-269">DriversLics#</span></span>
- <span data-ttu-id="a1757-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="a1757-270">DriversLicence#</span></span>
- <span data-ttu-id="a1757-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="a1757-271">DriversLicences#</span></span>
- <span data-ttu-id="a1757-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-272">Drivers Lic#</span></span>
- <span data-ttu-id="a1757-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-273">Drivers Lics#</span></span>
- <span data-ttu-id="a1757-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="a1757-274">Drivers Licence#</span></span>
- <span data-ttu-id="a1757-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="a1757-275">Drivers Licences#</span></span>
- <span data-ttu-id="a1757-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="a1757-276">Driver'Lic#</span></span>
- <span data-ttu-id="a1757-277">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="a1757-277">Driver'Lics#</span></span>
- <span data-ttu-id="a1757-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="a1757-278">Driver'Licence#</span></span>
- <span data-ttu-id="a1757-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="a1757-279">Driver'Licences#</span></span>
- <span data-ttu-id="a1757-280">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-280">Driver' Lic#</span></span>
- <span data-ttu-id="a1757-281">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-281">Driver' Lics#</span></span>
- <span data-ttu-id="a1757-282">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="a1757-282">Driver' Licence#</span></span>
- <span data-ttu-id="a1757-283">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="a1757-283">Driver' Licences#</span></span>
- <span data-ttu-id="a1757-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="a1757-284">Driver'sLic#</span></span>
- <span data-ttu-id="a1757-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="a1757-285">Driver'sLics#</span></span>
- <span data-ttu-id="a1757-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="a1757-286">Driver'sLicence#</span></span>
- <span data-ttu-id="a1757-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="a1757-287">Driver'sLicences#</span></span>
- <span data-ttu-id="a1757-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-288">Driver's Lic#</span></span>
- <span data-ttu-id="a1757-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-289">Driver's Lics#</span></span>
- <span data-ttu-id="a1757-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="a1757-290">Driver's Licence#</span></span>
- <span data-ttu-id="a1757-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="a1757-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="a1757-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a1757-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="a1757-293">AAA</span><span class="sxs-lookup"><span data-stu-id="a1757-293">aaa</span></span>
- <span data-ttu-id="a1757-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a1757-294">DriverLicense</span></span>
- <span data-ttu-id="a1757-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a1757-295">DriverLicenses</span></span>
- <span data-ttu-id="a1757-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="a1757-296">Driver License</span></span>
- <span data-ttu-id="a1757-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-297">Driver Licenses</span></span>
- <span data-ttu-id="a1757-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="a1757-298">DriversLicense</span></span>
- <span data-ttu-id="a1757-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a1757-299">DriversLicenses</span></span>
- <span data-ttu-id="a1757-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="a1757-300">Drivers License</span></span>
- <span data-ttu-id="a1757-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-301">Drivers Licenses</span></span>
- <span data-ttu-id="a1757-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a1757-302">Driver'License</span></span>
- <span data-ttu-id="a1757-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-303">Driver'Licenses</span></span>
- <span data-ttu-id="a1757-304">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a1757-304">Driver' License</span></span>
- <span data-ttu-id="a1757-305">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-305">Driver' Licenses</span></span>
- <span data-ttu-id="a1757-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a1757-306">Driver'sLicense</span></span>
- <span data-ttu-id="a1757-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a1757-307">Driver'sLicenses</span></span>
- <span data-ttu-id="a1757-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="a1757-308">Driver's License</span></span>
- <span data-ttu-id="a1757-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-309">Driver's Licenses</span></span>
- <span data-ttu-id="a1757-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="a1757-310">DriverLicense#</span></span>
- <span data-ttu-id="a1757-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-311">DriverLicenses#</span></span>
- <span data-ttu-id="a1757-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="a1757-312">Driver License#</span></span>
- <span data-ttu-id="a1757-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-313">Driver Licenses#</span></span>
- <span data-ttu-id="a1757-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="a1757-314">DriversLicense#</span></span>
- <span data-ttu-id="a1757-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-315">DriversLicenses#</span></span>
- <span data-ttu-id="a1757-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="a1757-316">Drivers License#</span></span>
- <span data-ttu-id="a1757-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-317">Drivers Licenses#</span></span>
- <span data-ttu-id="a1757-318">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="a1757-318">Driver'License#</span></span>
- <span data-ttu-id="a1757-319">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-319">Driver'Licenses#</span></span>
- <span data-ttu-id="a1757-320">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="a1757-320">Driver' License#</span></span>
- <span data-ttu-id="a1757-321">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-321">Driver' Licenses#</span></span>
- <span data-ttu-id="a1757-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="a1757-322">Driver'sLicense#</span></span>
- <span data-ttu-id="a1757-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="a1757-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="a1757-324">Driver's License#</span></span>
- <span data-ttu-id="a1757-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="a1757-326">Número de conta médica da Austrália</span><span class="sxs-lookup"><span data-stu-id="a1757-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-327">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-327">Format</span></span>

<span data-ttu-id="a1757-328">10 a 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-329">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-329">Pattern</span></span>

<span data-ttu-id="a1757-330">10 a 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-330">10-11 digits:</span></span>
- <span data-ttu-id="a1757-331">Primeiro dígito está no intervalo de 2 a 6</span><span class="sxs-lookup"><span data-stu-id="a1757-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="a1757-332">O nono dígito é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="a1757-333">O décimo dígito é o dígito do problema</span><span class="sxs-lookup"><span data-stu-id="a1757-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="a1757-334">O décimo primeiro dígito (opcional) é o número individual</span><span class="sxs-lookup"><span data-stu-id="a1757-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-335">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-335">Checksum</span></span>

<span data-ttu-id="a1757-336">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-337">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-337">Definition</span></span>

<span data-ttu-id="a1757-338">Uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-339">A função Func_australian_medical_account_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-340">Uma palavra-chave de Keyword_Australia_Medical_Account_Number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="a1757-341">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-341">The checksum passes.</span></span>

<span data-ttu-id="a1757-342">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-343">A função Func_australian_medical_account_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-344">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-344">The checksum passes.</span></span>

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-345">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="a1757-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="a1757-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="a1757-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="a1757-347">bank account details</span></span>
- <span data-ttu-id="a1757-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="a1757-348">medicare payments</span></span>
- <span data-ttu-id="a1757-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="a1757-349">mortgage account</span></span>
- <span data-ttu-id="a1757-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="a1757-350">bank payments</span></span>
- <span data-ttu-id="a1757-351">information branch</span><span class="sxs-lookup"><span data-stu-id="a1757-351">information branch</span></span>
- <span data-ttu-id="a1757-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="a1757-352">credit card loan</span></span>
- <span data-ttu-id="a1757-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="a1757-353">department of human services</span></span>
- <span data-ttu-id="a1757-354">local service</span><span class="sxs-lookup"><span data-stu-id="a1757-354">local service</span></span>
- <span data-ttu-id="a1757-355">medicare</span><span class="sxs-lookup"><span data-stu-id="a1757-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="a1757-356">Número de passaporte da Austrália</span><span class="sxs-lookup"><span data-stu-id="a1757-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-357">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-357">Format</span></span>

<span data-ttu-id="a1757-358">Uma letra seguida por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-359">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-359">Pattern</span></span>

<span data-ttu-id="a1757-360">Uma letra (não diferencia maiúsculas de minúsculas) seguida de sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-361">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-361">Checksum</span></span>

<span data-ttu-id="a1757-362">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-363">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-363">Definition</span></span>

<span data-ttu-id="a1757-364">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-365">A expressão regular Regex_australia_passport_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-366">Uma palavra-chave de Keyword_passport ou Keyword_australia_passport_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="a1757-367">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a1757-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a1757-368">Keyword_passport</span></span>

- <span data-ttu-id="a1757-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a1757-369">Passport Number</span></span>
- <span data-ttu-id="a1757-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="a1757-370">Passport No</span></span>
- <span data-ttu-id="a1757-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="a1757-371">Passport #</span></span>
- <span data-ttu-id="a1757-372">Passaport #</span><span class="sxs-lookup"><span data-stu-id="a1757-372">Passport#</span></span>
- <span data-ttu-id="a1757-373">Passportid</span><span class="sxs-lookup"><span data-stu-id="a1757-373">PassportID</span></span>
- <span data-ttu-id="a1757-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="a1757-374">Passportno</span></span>
- <span data-ttu-id="a1757-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-375">passportnumber</span></span>
- <span data-ttu-id="a1757-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="a1757-376">パスポート</span></span>
- <span data-ttu-id="a1757-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a1757-377">パスポート番号</span></span>
- <span data-ttu-id="a1757-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a1757-378">パスポートのNum</span></span>
- <span data-ttu-id="a1757-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="a1757-379">パスポート ＃</span></span> 
- <span data-ttu-id="a1757-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a1757-380">Numéro de passeport</span></span>
- <span data-ttu-id="a1757-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a1757-381">Passeport n °</span></span>
- <span data-ttu-id="a1757-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a1757-382">Passeport Non</span></span>
- <span data-ttu-id="a1757-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-383">Passeport #</span></span>
- <span data-ttu-id="a1757-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-384">Passeport#</span></span>
- <span data-ttu-id="a1757-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a1757-385">PasseportNon</span></span>
- <span data-ttu-id="a1757-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a1757-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="a1757-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="a1757-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="a1757-388">Passaport</span><span class="sxs-lookup"><span data-stu-id="a1757-388">passport</span></span>
- <span data-ttu-id="a1757-389">passport details</span><span class="sxs-lookup"><span data-stu-id="a1757-389">passport details</span></span>
- <span data-ttu-id="a1757-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="a1757-390">immigration and citizenship</span></span>
- <span data-ttu-id="a1757-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="a1757-391">commonwealth of australia</span></span>
- <span data-ttu-id="a1757-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="a1757-392">department of immigration</span></span>
- <span data-ttu-id="a1757-393">residential address</span><span class="sxs-lookup"><span data-stu-id="a1757-393">residential address</span></span>
- <span data-ttu-id="a1757-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="a1757-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="a1757-395">cartões</span><span class="sxs-lookup"><span data-stu-id="a1757-395">visa</span></span>
- <span data-ttu-id="a1757-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="a1757-396">national identity card</span></span>
- <span data-ttu-id="a1757-397">passport number</span><span class="sxs-lookup"><span data-stu-id="a1757-397">passport number</span></span>
- <span data-ttu-id="a1757-398">travel document</span><span class="sxs-lookup"><span data-stu-id="a1757-398">travel document</span></span>
- <span data-ttu-id="a1757-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="a1757-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="a1757-400">Número de imposto de renda da Austrália</span><span class="sxs-lookup"><span data-stu-id="a1757-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-401">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-401">Format</span></span>

<span data-ttu-id="a1757-402">8 a 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-403">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-403">Pattern</span></span>

<span data-ttu-id="a1757-404">8 a 9 dígitos normalmente apresentados com espaços, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a1757-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="a1757-405">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-405">Three digits</span></span> 
- <span data-ttu-id="a1757-406">Um espaço opcional</span><span class="sxs-lookup"><span data-stu-id="a1757-406">An optional space</span></span> 
- <span data-ttu-id="a1757-407">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-407">Three digits</span></span> 
- <span data-ttu-id="a1757-408">Um espaço opcional</span><span class="sxs-lookup"><span data-stu-id="a1757-408">An optional space</span></span> 
- <span data-ttu-id="a1757-409">2 a 3 dígitos em que o último dígito é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-410">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-410">Checksum</span></span>

<span data-ttu-id="a1757-411">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-412">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-412">Definition</span></span>

<span data-ttu-id="a1757-413">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-414">A função Func_australian_tax_file_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-415">Nenhuma palavra-chave de Keyword_Australia_Tax_File_Number ou Keyword_number_exclusions for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="a1757-416">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-417">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="a1757-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="a1757-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="a1757-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="a1757-419">australian business number</span></span>
- <span data-ttu-id="a1757-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="a1757-420">marginal tax rate</span></span>
- <span data-ttu-id="a1757-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="a1757-421">medicare levy</span></span>
- <span data-ttu-id="a1757-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="a1757-422">portfolio number</span></span>
- <span data-ttu-id="a1757-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="a1757-423">service veterans</span></span>
- <span data-ttu-id="a1757-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="a1757-424">withholding tax</span></span>
- <span data-ttu-id="a1757-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="a1757-425">individual tax return</span></span>
- <span data-ttu-id="a1757-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="a1757-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="a1757-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a1757-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="a1757-428">00000000</span><span class="sxs-lookup"><span data-stu-id="a1757-428">00000000</span></span>
- <span data-ttu-id="a1757-429">11111111</span><span class="sxs-lookup"><span data-stu-id="a1757-429">11111111</span></span>
- <span data-ttu-id="a1757-430">22222222</span><span class="sxs-lookup"><span data-stu-id="a1757-430">22222222</span></span>
- <span data-ttu-id="a1757-431">33333333</span><span class="sxs-lookup"><span data-stu-id="a1757-431">33333333</span></span>
- <span data-ttu-id="a1757-432">44444444</span><span class="sxs-lookup"><span data-stu-id="a1757-432">44444444</span></span>
- <span data-ttu-id="a1757-433">55555555</span><span class="sxs-lookup"><span data-stu-id="a1757-433">55555555</span></span>
- <span data-ttu-id="a1757-434">66666666</span><span class="sxs-lookup"><span data-stu-id="a1757-434">66666666</span></span>
- <span data-ttu-id="a1757-435">77777777</span><span class="sxs-lookup"><span data-stu-id="a1757-435">77777777</span></span>
- <span data-ttu-id="a1757-436">88888888</span><span class="sxs-lookup"><span data-stu-id="a1757-436">88888888</span></span>
- <span data-ttu-id="a1757-437">99999999</span><span class="sxs-lookup"><span data-stu-id="a1757-437">99999999</span></span>
- <span data-ttu-id="a1757-438">000000000</span><span class="sxs-lookup"><span data-stu-id="a1757-438">000000000</span></span>
- <span data-ttu-id="a1757-439">111111111</span><span class="sxs-lookup"><span data-stu-id="a1757-439">111111111</span></span>
- <span data-ttu-id="a1757-440">222222222</span><span class="sxs-lookup"><span data-stu-id="a1757-440">222222222</span></span>
- <span data-ttu-id="a1757-441">333333333</span><span class="sxs-lookup"><span data-stu-id="a1757-441">333333333</span></span>
- <span data-ttu-id="a1757-442">444444444</span><span class="sxs-lookup"><span data-stu-id="a1757-442">444444444</span></span>
- <span data-ttu-id="a1757-443">555555555</span><span class="sxs-lookup"><span data-stu-id="a1757-443">555555555</span></span>
- <span data-ttu-id="a1757-444">666666666</span><span class="sxs-lookup"><span data-stu-id="a1757-444">666666666</span></span>
- <span data-ttu-id="a1757-445">777777777</span><span class="sxs-lookup"><span data-stu-id="a1757-445">777777777</span></span>
- <span data-ttu-id="a1757-446">888888888</span><span class="sxs-lookup"><span data-stu-id="a1757-446">888888888</span></span>
- <span data-ttu-id="a1757-447">999999999</span><span class="sxs-lookup"><span data-stu-id="a1757-447">999999999</span></span>
- <span data-ttu-id="a1757-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="a1757-448">0000000000</span></span>
- <span data-ttu-id="a1757-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="a1757-449">1111111111</span></span>
- <span data-ttu-id="a1757-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="a1757-450">2222222222</span></span>
- <span data-ttu-id="a1757-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="a1757-451">3333333333</span></span>
- <span data-ttu-id="a1757-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="a1757-452">4444444444</span></span>
- <span data-ttu-id="a1757-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="a1757-453">5555555555</span></span>
- <span data-ttu-id="a1757-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="a1757-454">6666666666</span></span>
- <span data-ttu-id="a1757-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="a1757-455">7777777777</span></span>
- <span data-ttu-id="a1757-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="a1757-456">8888888888</span></span>
- <span data-ttu-id="a1757-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="a1757-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="a1757-458">Chave de autenticação do Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="a1757-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="a1757-459">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-459">Format</span></span>

<span data-ttu-id="a1757-460">A cadeia de caracteres "DocumentDb" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo.</span><span class="sxs-lookup"><span data-stu-id="a1757-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-461">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-461">Pattern</span></span>

- <span data-ttu-id="a1757-462">A cadeia de caracteres "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="a1757-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="a1757-463">Qualquer combinação entre 3-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-464">Um símbolo maior que (>), um sinal de igual (=), uma aspa (") ou um apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="a1757-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="a1757-465">Qualquer combinação de 86 letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="a1757-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a1757-466">Dois sinais de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-467">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-467">Checksum</span></span>

<span data-ttu-id="a1757-468">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-469">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-469">Definition</span></span>

<span data-ttu-id="a1757-470">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-471">A expressão regular CEP_Regex_AzureDocumentDBAuthKey localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-472">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-473">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a1757-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a1757-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a1757-475">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-476">contoso</span><span class="sxs-lookup"><span data-stu-id="a1757-476">contoso</span></span>
- <span data-ttu-id="a1757-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="a1757-477">fabrikam</span></span>
- <span data-ttu-id="a1757-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="a1757-478">northwind</span></span>
- <span data-ttu-id="a1757-479">área restrita</span><span class="sxs-lookup"><span data-stu-id="a1757-479">sandbox</span></span>
- <span data-ttu-id="a1757-480">onebox</span><span class="sxs-lookup"><span data-stu-id="a1757-480">onebox</span></span>
- <span data-ttu-id="a1757-481">localhost</span><span class="sxs-lookup"><span data-stu-id="a1757-481">localhost</span></span>
- <span data-ttu-id="a1757-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a1757-482">127.0.0.1</span></span>
- <span data-ttu-id="a1757-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="a1757-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-484">suplementos</span><span class="sxs-lookup"><span data-stu-id="a1757-484">com</span></span>
- <span data-ttu-id="a1757-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="a1757-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-486">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="a1757-487">Cadeia de conexão de banco de dados Azure IAAS e cadeia de conexão do Azure SQL</span><span class="sxs-lookup"><span data-stu-id="a1757-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a1757-488">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-488">Format</span></span>

<span data-ttu-id="a1757-489">A cadeia de caracteres "Server", "Server" ou "Data Source" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="a1757-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-490">com "ou" cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="a1757-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-491">NET "ou" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="a1757-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-492">NET ", e a cadeia de caracteres" password "ou" password "ou" pwd ".</span><span class="sxs-lookup"><span data-stu-id="a1757-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-493">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-493">Pattern</span></span>

- <span data-ttu-id="a1757-494">A cadeia de caracteres "Server", "Server" ou "Data Source"</span><span class="sxs-lookup"><span data-stu-id="a1757-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="a1757-495">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-496">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-496">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-497">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-498">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-499">A cadeia de caracteres "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="a1757-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-500">com "," cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="a1757-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-501">NET "ou" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="a1757-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-502">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-502">net"</span></span>
- <span data-ttu-id="a1757-503">Qualquer combinação entre 1-300 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-504">A cadeia de caracteres "password", "password" ou "pwd"</span><span class="sxs-lookup"><span data-stu-id="a1757-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="a1757-505">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-506">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-506">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-507">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-508">Um ou mais caracteres que não são ponto-e-vírgula (;), aspas (") ou apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="a1757-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="a1757-509">Um ponto e vírgula (;), aspas (") ou apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="a1757-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-510">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-510">Checksum</span></span>

<span data-ttu-id="a1757-511">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-512">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-512">Definition</span></span>

<span data-ttu-id="a1757-513">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-514">A expressão regular CEP_Regex_AzureConnectionString localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-515">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-516">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a1757-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a1757-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a1757-518">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-519">contoso</span><span class="sxs-lookup"><span data-stu-id="a1757-519">contoso</span></span>
- <span data-ttu-id="a1757-520">fabrikam</span><span class="sxs-lookup"><span data-stu-id="a1757-520">fabrikam</span></span>
- <span data-ttu-id="a1757-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="a1757-521">northwind</span></span>
- <span data-ttu-id="a1757-522">área restrita</span><span class="sxs-lookup"><span data-stu-id="a1757-522">sandbox</span></span>
- <span data-ttu-id="a1757-523">onebox</span><span class="sxs-lookup"><span data-stu-id="a1757-523">onebox</span></span>
- <span data-ttu-id="a1757-524">localhost</span><span class="sxs-lookup"><span data-stu-id="a1757-524">localhost</span></span>
- <span data-ttu-id="a1757-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a1757-525">127.0.0.1</span></span>
- <span data-ttu-id="a1757-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="a1757-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-527">suplementos</span><span class="sxs-lookup"><span data-stu-id="a1757-527">com</span></span>
- <span data-ttu-id="a1757-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="a1757-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-529">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="a1757-530">Cadeia de conexão IoT do Azure</span><span class="sxs-lookup"><span data-stu-id="a1757-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a1757-531">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-531">Format</span></span>

<span data-ttu-id="a1757-532">A cadeia de caracteres "HostName" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo as cadeias de caracteres "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="a1757-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-533">NET "e" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="a1757-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-534">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-534">Pattern</span></span>

- <span data-ttu-id="a1757-535">A cadeia de caracteres "HostName"</span><span class="sxs-lookup"><span data-stu-id="a1757-535">The string "HostName"</span></span>
- <span data-ttu-id="a1757-536">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-537">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-537">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-538">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-539">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-540">A cadeia de caracteres "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="a1757-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-541">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-541">net"</span></span>
- <span data-ttu-id="a1757-542">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-543">A cadeia de caracteres "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="a1757-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="a1757-544">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-545">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-545">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-546">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-547">Qualquer combinação de 43 letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="a1757-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a1757-548">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-549">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-549">Checksum</span></span>

<span data-ttu-id="a1757-550">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-551">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-551">Definition</span></span>

<span data-ttu-id="a1757-552">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-553">A expressão regular CEP_Regex_AzureIoTConnectionString localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-554">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-555">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a1757-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a1757-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a1757-557">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-558">contoso</span><span class="sxs-lookup"><span data-stu-id="a1757-558">contoso</span></span>
- <span data-ttu-id="a1757-559">fabrikam</span><span class="sxs-lookup"><span data-stu-id="a1757-559">fabrikam</span></span>
- <span data-ttu-id="a1757-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="a1757-560">northwind</span></span>
- <span data-ttu-id="a1757-561">área restrita</span><span class="sxs-lookup"><span data-stu-id="a1757-561">sandbox</span></span>
- <span data-ttu-id="a1757-562">onebox</span><span class="sxs-lookup"><span data-stu-id="a1757-562">onebox</span></span>
- <span data-ttu-id="a1757-563">localhost</span><span class="sxs-lookup"><span data-stu-id="a1757-563">localhost</span></span>
- <span data-ttu-id="a1757-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a1757-564">127.0.0.1</span></span>
- <span data-ttu-id="a1757-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="a1757-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-566">suplementos</span><span class="sxs-lookup"><span data-stu-id="a1757-566">com</span></span>
- <span data-ttu-id="a1757-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="a1757-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-568">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="a1757-569">Senha de configuração de publicação do Azure</span><span class="sxs-lookup"><span data-stu-id="a1757-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="a1757-570">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-570">Format</span></span>

<span data-ttu-id="a1757-571">A cadeia de caracteres "userpwd =" seguida de uma cadeia de caracteres alfanumérica.</span><span class="sxs-lookup"><span data-stu-id="a1757-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-572">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-572">Pattern</span></span>

- <span data-ttu-id="a1757-573">A cadeia de caracteres "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="a1757-573">The string "userpwd="</span></span>
- <span data-ttu-id="a1757-574">Qualquer combinação de letras minúsculas ou dígitos de 60</span><span class="sxs-lookup"><span data-stu-id="a1757-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="a1757-575">Aspas (")</span><span class="sxs-lookup"><span data-stu-id="a1757-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-576">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-576">Checksum</span></span>

<span data-ttu-id="a1757-577">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-578">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-578">Definition</span></span>

<span data-ttu-id="a1757-579">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-580">A expressão regular CEP_Regex_AzurePublishSettingPasswords localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-581">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-582">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a1757-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a1757-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a1757-584">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-585">contoso</span><span class="sxs-lookup"><span data-stu-id="a1757-585">contoso</span></span>
- <span data-ttu-id="a1757-586">fabrikam</span><span class="sxs-lookup"><span data-stu-id="a1757-586">fabrikam</span></span>
- <span data-ttu-id="a1757-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="a1757-587">northwind</span></span>
- <span data-ttu-id="a1757-588">área restrita</span><span class="sxs-lookup"><span data-stu-id="a1757-588">sandbox</span></span>
- <span data-ttu-id="a1757-589">onebox</span><span class="sxs-lookup"><span data-stu-id="a1757-589">onebox</span></span>
- <span data-ttu-id="a1757-590">localhost</span><span class="sxs-lookup"><span data-stu-id="a1757-590">localhost</span></span>
- <span data-ttu-id="a1757-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a1757-591">127.0.0.1</span></span>
- <span data-ttu-id="a1757-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="a1757-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-593">suplementos</span><span class="sxs-lookup"><span data-stu-id="a1757-593">com</span></span>
- <span data-ttu-id="a1757-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="a1757-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-595">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="a1757-596">Cadeia de conexão do cache do Redis do Azure</span><span class="sxs-lookup"><span data-stu-id="a1757-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a1757-597">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-597">Format</span></span>

<span data-ttu-id="a1757-598">A cadeia de caracteres "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="a1757-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-599">NET "seguido pelos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres" password "ou" pwd ".</span><span class="sxs-lookup"><span data-stu-id="a1757-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-600">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-600">Pattern</span></span>

- <span data-ttu-id="a1757-601">A cadeia de caracteres "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="a1757-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-602">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-602">net"</span></span>
- <span data-ttu-id="a1757-603">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-604">A cadeia de caracteres "password" ou "pwd"</span><span class="sxs-lookup"><span data-stu-id="a1757-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="a1757-605">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-606">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-606">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-607">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-608">Qualquer combinação de 43 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="a1757-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a1757-609">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-610">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-610">Checksum</span></span>

<span data-ttu-id="a1757-611">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-612">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-612">Definition</span></span>

<span data-ttu-id="a1757-613">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-614">A expressão regular CEP_Regex_AzureRedisCacheConnectionString localiza o conteúdo que corresponde ao padrão..</span><span class="sxs-lookup"><span data-stu-id="a1757-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="a1757-615">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-616">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a1757-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a1757-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a1757-618">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-619">contoso</span><span class="sxs-lookup"><span data-stu-id="a1757-619">contoso</span></span>
- <span data-ttu-id="a1757-620">fabrikam</span><span class="sxs-lookup"><span data-stu-id="a1757-620">fabrikam</span></span>
- <span data-ttu-id="a1757-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="a1757-621">northwind</span></span>
- <span data-ttu-id="a1757-622">área restrita</span><span class="sxs-lookup"><span data-stu-id="a1757-622">sandbox</span></span>
- <span data-ttu-id="a1757-623">onebox</span><span class="sxs-lookup"><span data-stu-id="a1757-623">onebox</span></span>
- <span data-ttu-id="a1757-624">localhost</span><span class="sxs-lookup"><span data-stu-id="a1757-624">localhost</span></span>
- <span data-ttu-id="a1757-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a1757-625">127.0.0.1</span></span>
- <span data-ttu-id="a1757-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="a1757-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-627">suplementos</span><span class="sxs-lookup"><span data-stu-id="a1757-627">com</span></span>
- <span data-ttu-id="a1757-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="a1757-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-629">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="a1757-630">SAS do Azure</span><span class="sxs-lookup"><span data-stu-id="a1757-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="a1757-631">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-631">Format</span></span>

<span data-ttu-id="a1757-632">A cadeia de caracteres "SIG" seguida pelos caracteres e cadeias de caracteres descritos no padrão abaixo.</span><span class="sxs-lookup"><span data-stu-id="a1757-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-633">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-633">Pattern</span></span>

- <span data-ttu-id="a1757-634">A cadeia de caracteres "SIG"</span><span class="sxs-lookup"><span data-stu-id="a1757-634">The string "sig"</span></span>
- <span data-ttu-id="a1757-635">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-636">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-636">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-637">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-638">Qualquer combinação entre 43-53 caracteres que são letras minúsculas ou maiúsculas, dígitos ou o sinal de porcentagem (%)</span><span class="sxs-lookup"><span data-stu-id="a1757-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="a1757-639">A cadeia de caracteres "% 3D"</span><span class="sxs-lookup"><span data-stu-id="a1757-639">The string "%3d"</span></span>
- <span data-ttu-id="a1757-640">Qualquer caractere que não seja letras minúsculas, dígitos ou sinal de porcentagem (%)</span><span class="sxs-lookup"><span data-stu-id="a1757-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-641">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-641">Checksum</span></span>

<span data-ttu-id="a1757-642">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-643">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-643">Definition</span></span>

<span data-ttu-id="a1757-644">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-645">A expressão regular CEP_Regex_AzureSAS localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="a1757-646">Cadeia de conexão do barramento de serviço do Azure</span><span class="sxs-lookup"><span data-stu-id="a1757-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a1757-647">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-647">Format</span></span>

<span data-ttu-id="a1757-648">A cadeia de caracteres "EndPoint" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo as cadeias de caracteres "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="a1757-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-649">NET "e" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="a1757-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-650">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-650">Pattern</span></span>

- <span data-ttu-id="a1757-651">A cadeia de caracteres "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="a1757-651">The string "EndPoint"</span></span>
- <span data-ttu-id="a1757-652">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-653">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-653">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-654">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-655">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-656">A cadeia de caracteres "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="a1757-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-657">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-657">net"</span></span>
- <span data-ttu-id="a1757-658">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-659">A cadeia de caracteres "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="a1757-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="a1757-660">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-661">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-661">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-662">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-663">Qualquer combinação de 43 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="a1757-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a1757-664">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-665">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-665">Checksum</span></span>

<span data-ttu-id="a1757-666">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-667">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-667">Definition</span></span>

<span data-ttu-id="a1757-668">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-669">A expressão regular CEP_Regex_AzureServiceBusConnectionString localiza o conteúdo que corresponde ao padrão..</span><span class="sxs-lookup"><span data-stu-id="a1757-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="a1757-670">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-671">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a1757-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a1757-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a1757-673">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-674">contoso</span><span class="sxs-lookup"><span data-stu-id="a1757-674">contoso</span></span>
- <span data-ttu-id="a1757-675">fabrikam</span><span class="sxs-lookup"><span data-stu-id="a1757-675">fabrikam</span></span>
- <span data-ttu-id="a1757-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="a1757-676">northwind</span></span>
- <span data-ttu-id="a1757-677">área restrita</span><span class="sxs-lookup"><span data-stu-id="a1757-677">sandbox</span></span>
- <span data-ttu-id="a1757-678">onebox</span><span class="sxs-lookup"><span data-stu-id="a1757-678">onebox</span></span>
- <span data-ttu-id="a1757-679">localhost</span><span class="sxs-lookup"><span data-stu-id="a1757-679">localhost</span></span>
- <span data-ttu-id="a1757-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a1757-680">127.0.0.1</span></span>
- <span data-ttu-id="a1757-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="a1757-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-682">suplementos</span><span class="sxs-lookup"><span data-stu-id="a1757-682">com</span></span>
- <span data-ttu-id="a1757-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="a1757-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-684">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="a1757-685">Chave da conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="a1757-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="a1757-686">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-686">Format</span></span>

<span data-ttu-id="a1757-687">A cadeia de caracteres "DefaultEndpointsProtocol" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="a1757-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-688">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-688">Pattern</span></span>

- <span data-ttu-id="a1757-689">A cadeia de caracteres "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="a1757-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="a1757-690">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-691">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-691">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-692">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-693">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-694">A cadeia de caracteres "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="a1757-694">The string "AccountKey"</span></span>
- <span data-ttu-id="a1757-695">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-696">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-696">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-697">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="a1757-698">Qualquer combinação de 86 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="a1757-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a1757-699">Dois sinais de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-700">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-700">Checksum</span></span>

<span data-ttu-id="a1757-701">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-702">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-702">Definition</span></span>

<span data-ttu-id="a1757-703">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-704">A expressão regular CEP_Regex_AzureStorageAccountKey localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-705">A expressão regular CEP_AzureEmulatorStorageAccountFilter não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-706">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-707">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="a1757-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="a1757-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="a1757-709">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="a1757-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a1757-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a1757-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a1757-712">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-713">contoso</span><span class="sxs-lookup"><span data-stu-id="a1757-713">contoso</span></span>
- <span data-ttu-id="a1757-714">fabrikam</span><span class="sxs-lookup"><span data-stu-id="a1757-714">fabrikam</span></span>
- <span data-ttu-id="a1757-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="a1757-715">northwind</span></span>
- <span data-ttu-id="a1757-716">área restrita</span><span class="sxs-lookup"><span data-stu-id="a1757-716">sandbox</span></span>
- <span data-ttu-id="a1757-717">onebox</span><span class="sxs-lookup"><span data-stu-id="a1757-717">onebox</span></span>
- <span data-ttu-id="a1757-718">localhost</span><span class="sxs-lookup"><span data-stu-id="a1757-718">localhost</span></span>
- <span data-ttu-id="a1757-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a1757-719">127.0.0.1</span></span>
- <span data-ttu-id="a1757-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="a1757-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-721">suplementos</span><span class="sxs-lookup"><span data-stu-id="a1757-721">com</span></span>
- <span data-ttu-id="a1757-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="a1757-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-723">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="a1757-724">Chave da conta de armazenamento do Azure (genérico)</span><span class="sxs-lookup"><span data-stu-id="a1757-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-725">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-725">Format</span></span>

<span data-ttu-id="a1757-726">Qualquer combinação de letras maiúsculas ou minúsculas de 86, dígitos, barra (/) ou sinal de adição (+), precedida ou seguida dos caracteres descritos no padrão abaixo.</span><span class="sxs-lookup"><span data-stu-id="a1757-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-727">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-727">Pattern</span></span>

- <span data-ttu-id="a1757-728">0-1 do símbolo maior que (>), apóstrofo ('), sinal de igual (=), aspas (") ou sinal de número (#)</span><span class="sxs-lookup"><span data-stu-id="a1757-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="a1757-729">Qualquer combinação de 86 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, a barra (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="a1757-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a1757-730">Dois sinais de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="a1757-731">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-731">Checksum</span></span>

<span data-ttu-id="a1757-732">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-733">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-733">Definition</span></span>

<span data-ttu-id="a1757-734">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-735">A expressão regular CEP_Regex_AzureStorageAccountKeyGeneric localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="a1757-736">Número Nacional da Bélgica</span><span class="sxs-lookup"><span data-stu-id="a1757-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-737">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-737">Format</span></span>

<span data-ttu-id="a1757-738">11 dígitos mais delimitadores</span><span class="sxs-lookup"><span data-stu-id="a1757-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-739">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-739">Pattern</span></span>

<span data-ttu-id="a1757-740">11 dígitos mais delimitadores.</span><span class="sxs-lookup"><span data-stu-id="a1757-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="a1757-741">Seis dígitos e dois pontos no formato AA.MM.DD da data de nascimento </span><span class="sxs-lookup"><span data-stu-id="a1757-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="a1757-742">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-742">A hyphen</span></span> 
- <span data-ttu-id="a1757-743">Três dígitos sequenciais (ímpares para homens, pares para mulheres) </span><span class="sxs-lookup"><span data-stu-id="a1757-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="a1757-744">Um ponto</span><span class="sxs-lookup"><span data-stu-id="a1757-744">A period</span></span> 
- <span data-ttu-id="a1757-745">Dois dígitos que são um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-746">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-746">Checksum</span></span>

<span data-ttu-id="a1757-747">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-748">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-748">Definition</span></span>

<span data-ttu-id="a1757-749">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-750">A função Func_belgium_national_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-751">Uma palavra-chave de Keyword_belgium_national_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="a1757-752">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-753">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="a1757-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="a1757-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="a1757-755">Identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-755">Identity</span></span>
- <span data-ttu-id="a1757-756">Registro</span><span class="sxs-lookup"><span data-stu-id="a1757-756">Registration</span></span>
- <span data-ttu-id="a1757-757">Identificador</span><span class="sxs-lookup"><span data-stu-id="a1757-757">Identification</span></span> 
- <span data-ttu-id="a1757-758">ID</span><span class="sxs-lookup"><span data-stu-id="a1757-758">ID</span></span> 
- <span data-ttu-id="a1757-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="a1757-759">Identiteitskaart</span></span>
- <span data-ttu-id="a1757-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="a1757-760">Registratie nummer</span></span> 
- <span data-ttu-id="a1757-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="a1757-761">Identificatie nummer</span></span> 
- <span data-ttu-id="a1757-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="a1757-762">Identiteit</span></span>
- <span data-ttu-id="a1757-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="a1757-763">Registratie</span></span>
- <span data-ttu-id="a1757-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="a1757-764">Identificatie</span></span> 
- <span data-ttu-id="a1757-765">D'identité carte</span><span class="sxs-lookup"><span data-stu-id="a1757-765">Carte d'identité</span></span> 
- <span data-ttu-id="a1757-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="a1757-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="a1757-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="a1757-767">numéro d'identification</span></span>
- <span data-ttu-id="a1757-768">identité</span><span class="sxs-lookup"><span data-stu-id="a1757-768">identité</span></span> 
- <span data-ttu-id="a1757-769">inscription</span><span class="sxs-lookup"><span data-stu-id="a1757-769">inscription</span></span> 
- <span data-ttu-id="a1757-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a1757-770">Identifikation</span></span>
- <span data-ttu-id="a1757-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="a1757-771">Identifizierung</span></span>
- <span data-ttu-id="a1757-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-772">Identifikationsnummer</span></span>
- <span data-ttu-id="a1757-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a1757-773">Personalausweis</span></span>
- <span data-ttu-id="a1757-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="a1757-774">Registrierung</span></span>
- <span data-ttu-id="a1757-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="a1757-776">Número de CPF do Brasil</span><span class="sxs-lookup"><span data-stu-id="a1757-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-777">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-777">Format</span></span>

<span data-ttu-id="a1757-778">11 dígitos que incluem um dígito de verificação e podem ser formatados ou não formatados</span><span class="sxs-lookup"><span data-stu-id="a1757-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-779">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-779">Pattern</span></span>

<span data-ttu-id="a1757-780">Binário</span><span class="sxs-lookup"><span data-stu-id="a1757-780">Formatted:</span></span>
- <span data-ttu-id="a1757-781">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-781">Three digits</span></span> 
- <span data-ttu-id="a1757-782">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-782">A period</span></span> 
- <span data-ttu-id="a1757-783">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-783">Three digits</span></span> 
- <span data-ttu-id="a1757-784">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-784">A period</span></span> 
- <span data-ttu-id="a1757-785">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-785">Three digits</span></span> 
- <span data-ttu-id="a1757-786">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-786">A hyphen</span></span> 
- <span data-ttu-id="a1757-787">Dois dígitos que são dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-787">Two digits which are check digits</span></span>

<span data-ttu-id="a1757-788">Não formatado</span><span class="sxs-lookup"><span data-stu-id="a1757-788">Unformatted:</span></span>
- <span data-ttu-id="a1757-789">11 dígitos em que os dois últimos dígitos são dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-790">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-790">Checksum</span></span>

<span data-ttu-id="a1757-791">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-792">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-792">Definition</span></span>

<span data-ttu-id="a1757-793">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-794">A função Func_brazil_cpf localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-795">Uma palavra-chave de Keyword_brazil_cpf for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="a1757-796">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-796">The checksum passes.</span></span>

<span data-ttu-id="a1757-797">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-798">A função Func_brazil_cpf localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-799">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-799">The checksum passes.</span></span>

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-800">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="a1757-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="a1757-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="a1757-802">CPF</span><span class="sxs-lookup"><span data-stu-id="a1757-802">CPF</span></span>
- <span data-ttu-id="a1757-803">Identificador</span><span class="sxs-lookup"><span data-stu-id="a1757-803">Identification</span></span>
- <span data-ttu-id="a1757-804">Registro</span><span class="sxs-lookup"><span data-stu-id="a1757-804">Registration</span></span>
- <span data-ttu-id="a1757-805">Participação</span><span class="sxs-lookup"><span data-stu-id="a1757-805">Revenue</span></span>
- <span data-ttu-id="a1757-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="a1757-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="a1757-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="a1757-807">Imposto</span></span> 
- <span data-ttu-id="a1757-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="a1757-808">Identificação</span></span> 
- <span data-ttu-id="a1757-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="a1757-809">Inscrição</span></span> 
- <span data-ttu-id="a1757-810">Receita</span><span class="sxs-lookup"><span data-stu-id="a1757-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="a1757-811">Número de Pessoa Jurídica (CNPJ) do Brasil</span><span class="sxs-lookup"><span data-stu-id="a1757-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-812">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-812">Format</span></span>

<span data-ttu-id="a1757-813">14 dígitos que incluem um número de registro, o número da ramificação e dígitos de verificação, além de delimitadores de seleção</span><span class="sxs-lookup"><span data-stu-id="a1757-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-814">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-814">Pattern</span></span>
<span data-ttu-id="a1757-815">14 dígitos mais delimitadores:</span><span class="sxs-lookup"><span data-stu-id="a1757-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="a1757-816">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-816">Two digits</span></span> 
- <span data-ttu-id="a1757-817">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-817">A period</span></span> 
- <span data-ttu-id="a1757-818">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-818">Three digits</span></span> 
- <span data-ttu-id="a1757-819">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-819">A period</span></span> 
- <span data-ttu-id="a1757-820">Três dígitos (esses primeiros oito dígitos são o número de registro) </span><span class="sxs-lookup"><span data-stu-id="a1757-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="a1757-821">Uma barra</span><span class="sxs-lookup"><span data-stu-id="a1757-821">A forward slash</span></span> 
- <span data-ttu-id="a1757-822">Número da ramificação de quatro dígitos </span><span class="sxs-lookup"><span data-stu-id="a1757-822">Four-digit branch number</span></span> 
- <span data-ttu-id="a1757-823">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-823">A hyphen</span></span> 
- <span data-ttu-id="a1757-824">Dois dígitos que são dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-825">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-825">Checksum</span></span>

<span data-ttu-id="a1757-826">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-827">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-827">Definition</span></span>

<span data-ttu-id="a1757-828">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-829">A função Func_brazil_cnpj localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-830">Uma palavra-chave de Keyword_brazil_cnpj for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="a1757-831">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-831">The checksum passes.</span></span>

<span data-ttu-id="a1757-832">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-833">A função Func_brazil_cnpj localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-834">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-834">The checksum passes.</span></span>

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-835">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="a1757-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="a1757-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="a1757-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="a1757-837">CNPJ</span></span> 
- <span data-ttu-id="a1757-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="a1757-838">CNPJ/MF</span></span> 
- <span data-ttu-id="a1757-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="a1757-839">CNPJ-MF</span></span> 
- <span data-ttu-id="a1757-840">Registro Nacional de Pessoas Jurídicas</span><span class="sxs-lookup"><span data-stu-id="a1757-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="a1757-841">Registro de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="a1757-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="a1757-842">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="a1757-842">Legal entity</span></span> 
- <span data-ttu-id="a1757-843">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="a1757-843">Legal entities</span></span> 
- <span data-ttu-id="a1757-844">Status do Registro</span><span class="sxs-lookup"><span data-stu-id="a1757-844">Registration Status</span></span> 
- <span data-ttu-id="a1757-845">Negócio</span><span class="sxs-lookup"><span data-stu-id="a1757-845">Business</span></span> 
- <span data-ttu-id="a1757-846">Empresa</span><span class="sxs-lookup"><span data-stu-id="a1757-846">Company</span></span>
- <span data-ttu-id="a1757-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="a1757-847">CNPJ</span></span> 
- <span data-ttu-id="a1757-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="a1757-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="a1757-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="a1757-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="a1757-850">CGC</span><span class="sxs-lookup"><span data-stu-id="a1757-850">CGC</span></span> 
- <span data-ttu-id="a1757-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="a1757-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="a1757-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="a1757-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="a1757-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="a1757-853">Situação cadastral</span></span> 
- <span data-ttu-id="a1757-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="a1757-854">Inscrição</span></span> 
- <span data-ttu-id="a1757-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="a1757-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="a1757-856">	Cartão de Identidade Nacional (RG) do Brasil</span><span class="sxs-lookup"><span data-stu-id="a1757-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-857">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-857">Format</span></span>

<span data-ttu-id="a1757-858">Registro geral (formato antigo): nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="a1757-859">Registro de identidade (RIC) (novo formato): 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-860">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-860">Pattern</span></span>

<span data-ttu-id="a1757-861">Registro Geral (formato antigo):</span><span class="sxs-lookup"><span data-stu-id="a1757-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="a1757-862">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-862">Two digits</span></span> 
- <span data-ttu-id="a1757-863">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-863">A period</span></span> 
- <span data-ttu-id="a1757-864">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-864">Three digits</span></span> 
- <span data-ttu-id="a1757-865">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-865">A period</span></span> 
- <span data-ttu-id="a1757-866">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-866">Three digits</span></span> 
- <span data-ttu-id="a1757-867">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-867">A hyphen</span></span> 
- <span data-ttu-id="a1757-868">Um dígito que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-868">One digit which is a check digit</span></span>

<span data-ttu-id="a1757-869">Registro de identidade (RIC) (novo formato):</span><span class="sxs-lookup"><span data-stu-id="a1757-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="a1757-870">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-870">10 digits</span></span> 
- <span data-ttu-id="a1757-871">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-871">A hyphen</span></span> 
- <span data-ttu-id="a1757-872">Um dígito que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-873">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-873">Checksum</span></span>

<span data-ttu-id="a1757-874">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-875">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-875">Definition</span></span>

<span data-ttu-id="a1757-876">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-877">A função Func_brazil_rg localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-878">Uma palavra-chave de Keyword_brazil_rg for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="a1757-879">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-879">The checksum passes.</span></span>

<span data-ttu-id="a1757-880">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-881">A função Func_brazil_rg localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-882">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-882">The checksum passes.</span></span>

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-883">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="a1757-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="a1757-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="a1757-885">Cédula de identidade ID nacional número de registro registro de identidade registro de geral RG (esta palavra-chave diferencia maiúsculas de minúsculas) RIC (essa palavra-chave diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="a1757-886">Número de conta bancária do Canadá</span><span class="sxs-lookup"><span data-stu-id="a1757-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-887">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-887">Format</span></span>

<span data-ttu-id="a1757-888">Sete ou doze dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-889">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-889">Pattern</span></span>

<span data-ttu-id="a1757-890">Um número de conta bancária do Canadá tem sete ou doze dígitos.</span><span class="sxs-lookup"><span data-stu-id="a1757-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="a1757-891">Um número de trânsito de conta bancária do Canadá tem:</span><span class="sxs-lookup"><span data-stu-id="a1757-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="a1757-892">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-892">Five digits</span></span> 
- <span data-ttu-id="a1757-893">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-893">A hyphen</span></span> 
- <span data-ttu-id="a1757-894">Três dígitos ou</span><span class="sxs-lookup"><span data-stu-id="a1757-894">Three digits OR</span></span>
- <span data-ttu-id="a1757-895">Um zero "0"</span><span class="sxs-lookup"><span data-stu-id="a1757-895">A zero "0"</span></span> 
- <span data-ttu-id="a1757-896">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-897">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-897">Checksum</span></span>

<span data-ttu-id="a1757-898">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-899">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-899">Definition</span></span>

<span data-ttu-id="a1757-900">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-901">A expressão regular Regex_canada_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-902">Uma palavra-chave de Keyword_canada_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="a1757-903">A expressão regular Regex_canada_bank_account_transit_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="a1757-904">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-905">A expressão regular Regex_canada_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-906">Uma palavra-chave de Keyword_canada_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-907">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="a1757-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a1757-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="a1757-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="a1757-909">canada savings bonds</span></span>
- <span data-ttu-id="a1757-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="a1757-910">canada revenue agency</span></span>
- <span data-ttu-id="a1757-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="a1757-911">canadian financial institution</span></span>
- <span data-ttu-id="a1757-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="a1757-912">direct deposit form</span></span>
- <span data-ttu-id="a1757-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="a1757-913">canadian citizen</span></span>
- <span data-ttu-id="a1757-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="a1757-914">legal representative</span></span>
- <span data-ttu-id="a1757-915">notary public</span><span class="sxs-lookup"><span data-stu-id="a1757-915">notary public</span></span>
- <span data-ttu-id="a1757-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="a1757-916">commissioner for oaths</span></span>
- <span data-ttu-id="a1757-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="a1757-917">child care benefit</span></span>
- <span data-ttu-id="a1757-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="a1757-918">universal child care</span></span>
- <span data-ttu-id="a1757-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="a1757-919">canada child tax benefit</span></span>
- <span data-ttu-id="a1757-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="a1757-920">income tax benefit</span></span>
- <span data-ttu-id="a1757-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="a1757-921">harmonized sales tax</span></span>
- <span data-ttu-id="a1757-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a1757-922">social insurance number</span></span>
- <span data-ttu-id="a1757-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="a1757-923">income tax refund</span></span>
- <span data-ttu-id="a1757-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="a1757-924">child tax benefit</span></span>
- <span data-ttu-id="a1757-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="a1757-925">territorial payments</span></span>
- <span data-ttu-id="a1757-926">institution number</span><span class="sxs-lookup"><span data-stu-id="a1757-926">institution number</span></span>
- <span data-ttu-id="a1757-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="a1757-927">deposit request</span></span>
- <span data-ttu-id="a1757-928">banking information</span><span class="sxs-lookup"><span data-stu-id="a1757-928">banking information</span></span>
- <span data-ttu-id="a1757-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="a1757-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="a1757-930">Número de carteira de motorista do Canadá</span><span class="sxs-lookup"><span data-stu-id="a1757-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-931">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-931">Format</span></span>

<span data-ttu-id="a1757-932">Varia por província</span><span class="sxs-lookup"><span data-stu-id="a1757-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-933">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-933">Pattern</span></span>

<span data-ttu-id="a1757-934">Vários padrões que abrangem Alberta, Columbia Britânica, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Escócia, Ontário, Ilha do Príncipe Eduardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="a1757-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-935">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-935">Checksum</span></span>

<span data-ttu-id="a1757-936">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-937">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-937">Definition</span></span>

<span data-ttu-id="a1757-938">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-939">A função Func_[province_name]_drivers_license_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-940">Uma palavra-chave de Keyword_[province_name]_drivers_license_name for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a1757-941">Uma palavra-chave de Keyword_canada_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-942">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="a1757-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a1757-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="a1757-944">A abreviação da província, por exemplo AB</span><span class="sxs-lookup"><span data-stu-id="a1757-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="a1757-945">O nome da província, por exemplo, Alberta</span><span class="sxs-lookup"><span data-stu-id="a1757-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="a1757-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a1757-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="a1757-947">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a1757-947">DL</span></span>
- <span data-ttu-id="a1757-948">DL</span><span class="sxs-lookup"><span data-stu-id="a1757-948">DLS</span></span>
- <span data-ttu-id="a1757-949">CDL</span><span class="sxs-lookup"><span data-stu-id="a1757-949">CDL</span></span>
- <span data-ttu-id="a1757-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="a1757-950">CDLS</span></span>
- <span data-ttu-id="a1757-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="a1757-951">DriverLic</span></span>
- <span data-ttu-id="a1757-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="a1757-952">DriverLics</span></span>
- <span data-ttu-id="a1757-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a1757-953">DriverLicense</span></span>
- <span data-ttu-id="a1757-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a1757-954">DriverLicenses</span></span>
- <span data-ttu-id="a1757-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="a1757-955">DriverLicence</span></span>
- <span data-ttu-id="a1757-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a1757-956">DriverLicences</span></span>
- <span data-ttu-id="a1757-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-957">Driver Lic</span></span>
- <span data-ttu-id="a1757-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-958">Driver Lics</span></span>
- <span data-ttu-id="a1757-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="a1757-959">Driver License</span></span>
- <span data-ttu-id="a1757-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-960">Driver Licenses</span></span>
- <span data-ttu-id="a1757-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-961">Driver Licence</span></span>
- <span data-ttu-id="a1757-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-962">Driver Licences</span></span>
- <span data-ttu-id="a1757-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a1757-963">DriversLic</span></span>
- <span data-ttu-id="a1757-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="a1757-964">DriversLics</span></span>
- <span data-ttu-id="a1757-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="a1757-965">DriversLicence</span></span>
- <span data-ttu-id="a1757-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a1757-966">DriversLicences</span></span>
- <span data-ttu-id="a1757-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="a1757-967">DriversLicense</span></span>
- <span data-ttu-id="a1757-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a1757-968">DriversLicenses</span></span>
- <span data-ttu-id="a1757-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-969">Drivers Lic</span></span>
- <span data-ttu-id="a1757-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-970">Drivers Lics</span></span>
- <span data-ttu-id="a1757-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="a1757-971">Drivers License</span></span>
- <span data-ttu-id="a1757-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-972">Drivers Licenses</span></span>
- <span data-ttu-id="a1757-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-973">Drivers Licence</span></span>
- <span data-ttu-id="a1757-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-974">Drivers Licences</span></span>
- <span data-ttu-id="a1757-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-975">Driver'Lic</span></span>
- <span data-ttu-id="a1757-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-976">Driver'Lics</span></span>
- <span data-ttu-id="a1757-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a1757-977">Driver'License</span></span>
- <span data-ttu-id="a1757-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-978">Driver'Licenses</span></span>
- <span data-ttu-id="a1757-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-979">Driver'Licence</span></span>
- <span data-ttu-id="a1757-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-980">Driver'Licences</span></span>
- <span data-ttu-id="a1757-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-981">Driver' Lic</span></span>
- <span data-ttu-id="a1757-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-982">Driver' Lics</span></span>
- <span data-ttu-id="a1757-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="a1757-983">Driver' License</span></span>
- <span data-ttu-id="a1757-984">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-984">Driver' Licenses</span></span>
- <span data-ttu-id="a1757-985">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-985">Driver' Licence</span></span>
- <span data-ttu-id="a1757-986">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-986">Driver' Licences</span></span>
- <span data-ttu-id="a1757-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a1757-987">Driver'sLic</span></span>
- <span data-ttu-id="a1757-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a1757-988">Driver'sLics</span></span>
- <span data-ttu-id="a1757-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a1757-989">Driver'sLicense</span></span>
- <span data-ttu-id="a1757-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a1757-990">Driver'sLicenses</span></span>
- <span data-ttu-id="a1757-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="a1757-991">Driver'sLicence</span></span>
- <span data-ttu-id="a1757-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a1757-992">Driver'sLicences</span></span>
- <span data-ttu-id="a1757-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-993">Driver's Lic</span></span>
- <span data-ttu-id="a1757-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-994">Driver's Lics</span></span>
- <span data-ttu-id="a1757-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="a1757-995">Driver's License</span></span>
- <span data-ttu-id="a1757-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-996">Driver's Licenses</span></span>
- <span data-ttu-id="a1757-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-997">Driver's Licence</span></span>
- <span data-ttu-id="a1757-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-998">Driver's Licences</span></span>
- <span data-ttu-id="a1757-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="a1757-999">Permis de Conduire</span></span>
- <span data-ttu-id="a1757-1000">id</span><span class="sxs-lookup"><span data-stu-id="a1757-1000">id</span></span>
- <span data-ttu-id="a1757-1001">ids</span><span class="sxs-lookup"><span data-stu-id="a1757-1001">ids</span></span>
- <span data-ttu-id="a1757-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="a1757-1002">idcard number</span></span>
- <span data-ttu-id="a1757-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="a1757-1003">idcard numbers</span></span>
- <span data-ttu-id="a1757-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="a1757-1004">idcard #</span></span>
- <span data-ttu-id="a1757-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="a1757-1005">idcard #s</span></span>
- <span data-ttu-id="a1757-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="a1757-1006">idcard card</span></span>
- <span data-ttu-id="a1757-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1007">idcard cards</span></span>
- <span data-ttu-id="a1757-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="a1757-1008">idcard</span></span>
- <span data-ttu-id="a1757-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="a1757-1009">identification number</span></span>
- <span data-ttu-id="a1757-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="a1757-1010">identification numbers</span></span>
- <span data-ttu-id="a1757-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="a1757-1011">identification #</span></span>
- <span data-ttu-id="a1757-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="a1757-1012">identification #s</span></span>
- <span data-ttu-id="a1757-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="a1757-1013">identification card</span></span>
- <span data-ttu-id="a1757-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1014">identification cards</span></span>
- <span data-ttu-id="a1757-1015">identificador</span><span class="sxs-lookup"><span data-stu-id="a1757-1015">identification</span></span> 
- <span data-ttu-id="a1757-1016">DISTRIBUIÇÃO #</span><span class="sxs-lookup"><span data-stu-id="a1757-1016">DL#</span></span>
- <span data-ttu-id="a1757-1017">DL #</span><span class="sxs-lookup"><span data-stu-id="a1757-1017">DLS#</span></span> 
- <span data-ttu-id="a1757-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="a1757-1018">CDL#</span></span> 
- <span data-ttu-id="a1757-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="a1757-1019">CDLS#</span></span> 
- <span data-ttu-id="a1757-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="a1757-1020">DriverLic#</span></span> 
- <span data-ttu-id="a1757-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="a1757-1021">DriverLics#</span></span> 
- <span data-ttu-id="a1757-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="a1757-1022">DriverLicense#</span></span> 
- <span data-ttu-id="a1757-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="a1757-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="a1757-1024">DriverLicence#</span></span> 
- <span data-ttu-id="a1757-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="a1757-1025">DriverLicences#</span></span> 
- <span data-ttu-id="a1757-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-1026">Driver Lic#</span></span>
- <span data-ttu-id="a1757-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-1027">Driver Lics#</span></span> 
- <span data-ttu-id="a1757-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="a1757-1028">Driver License#</span></span> 
- <span data-ttu-id="a1757-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="a1757-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="a1757-1030">Driver License#</span></span> 
- <span data-ttu-id="a1757-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="a1757-1031">Driver Licences#</span></span> 
- <span data-ttu-id="a1757-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="a1757-1032">DriversLic#</span></span> 
- <span data-ttu-id="a1757-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="a1757-1033">DriversLics#</span></span> 
- <span data-ttu-id="a1757-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="a1757-1034">DriversLicense#</span></span> 
- <span data-ttu-id="a1757-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="a1757-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="a1757-1036">DriversLicence#</span></span> 
- <span data-ttu-id="a1757-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="a1757-1037">DriversLicences#</span></span> 
- <span data-ttu-id="a1757-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="a1757-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="a1757-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="a1757-1040">Drivers License#</span></span> 
- <span data-ttu-id="a1757-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="a1757-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="a1757-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="a1757-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="a1757-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="a1757-1044">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="a1757-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="a1757-1045">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="a1757-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="a1757-1046">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="a1757-1046">Driver'License#</span></span> 
- <span data-ttu-id="a1757-1047">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="a1757-1048">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="a1757-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="a1757-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="a1757-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="a1757-1050">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="a1757-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="a1757-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="a1757-1052">Driver' License#</span></span> 
- <span data-ttu-id="a1757-1053">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="a1757-1054">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="a1757-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="a1757-1055">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="a1757-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="a1757-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="a1757-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="a1757-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="a1757-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="a1757-1058">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="a1757-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="a1757-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a1757-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="a1757-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="a1757-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="a1757-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="a1757-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="a1757-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="a1757-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="a1757-1064">Driver's License#</span></span> 
- <span data-ttu-id="a1757-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="a1757-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="a1757-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="a1757-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="a1757-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="a1757-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="a1757-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="a1757-1069">ID #</span><span class="sxs-lookup"><span data-stu-id="a1757-1069">id#</span></span> 
- <span data-ttu-id="a1757-1070">código #</span><span class="sxs-lookup"><span data-stu-id="a1757-1070">ids#</span></span> 
- <span data-ttu-id="a1757-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="a1757-1071">idcard card#</span></span> 
- <span data-ttu-id="a1757-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="a1757-1072">idcard cards#</span></span> 
- <span data-ttu-id="a1757-1073">idcard #</span><span class="sxs-lookup"><span data-stu-id="a1757-1073">idcard#</span></span> 
- <span data-ttu-id="a1757-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="a1757-1074">identification card#</span></span> 
- <span data-ttu-id="a1757-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="a1757-1075">identification cards#</span></span> 
- <span data-ttu-id="a1757-1076">identificador #</span><span class="sxs-lookup"><span data-stu-id="a1757-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="a1757-1077">Número de serviço de saúde do Canadá</span><span class="sxs-lookup"><span data-stu-id="a1757-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1078">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1078">Format</span></span>

<span data-ttu-id="a1757-1079">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1080">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1080">Pattern</span></span>

<span data-ttu-id="a1757-1081">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1082">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1082">Checksum</span></span>

<span data-ttu-id="a1757-1083">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1084">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1084">Definition</span></span>

<span data-ttu-id="a1757-1085">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1086">A expressão regular Regex_canada_health_service_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1087">Uma palavra-chave de Keyword_canada_health_service_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1088">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="a1757-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="a1757-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="a1757-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="a1757-1090">personal health number</span></span>
- <span data-ttu-id="a1757-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="a1757-1091">patient information</span></span>
- <span data-ttu-id="a1757-1092">health services</span><span class="sxs-lookup"><span data-stu-id="a1757-1092">health services</span></span>
- <span data-ttu-id="a1757-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="a1757-1093">speciality services</span></span>
- <span data-ttu-id="a1757-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="a1757-1094">automobile accident</span></span>
- <span data-ttu-id="a1757-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="a1757-1095">patient hospital</span></span>
- <span data-ttu-id="a1757-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="a1757-1096">psychiatrist</span></span>
- <span data-ttu-id="a1757-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="a1757-1097">workers compensation</span></span>
- <span data-ttu-id="a1757-1098">Deficiência</span><span class="sxs-lookup"><span data-stu-id="a1757-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="a1757-1099">Número de passaporte do Canadá</span><span class="sxs-lookup"><span data-stu-id="a1757-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1100">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1100">Format</span></span>

<span data-ttu-id="a1757-1101">Duas letras maiúsculas, seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1102">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1102">Pattern</span></span>

<span data-ttu-id="a1757-1103">Duas letras maiúsculas, seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1104">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1104">Checksum</span></span>

<span data-ttu-id="a1757-1105">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1106">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1106">Definition</span></span>

<span data-ttu-id="a1757-1107">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1108">A expressão regular Regex_canada_passport_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1109">Uma palavra-chave de Keyword_canada_passport_number ou Keyword_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1110">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="a1757-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="a1757-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="a1757-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="a1757-1112">canadian citizenship</span></span>
- <span data-ttu-id="a1757-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="a1757-1113">canadian passport</span></span>
- <span data-ttu-id="a1757-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="a1757-1114">passport application</span></span>
- <span data-ttu-id="a1757-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="a1757-1115">passport photos</span></span>
- <span data-ttu-id="a1757-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="a1757-1116">certified translator</span></span>
- <span data-ttu-id="a1757-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="a1757-1117">canadian citizens</span></span>
- <span data-ttu-id="a1757-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="a1757-1118">processing times</span></span>
- <span data-ttu-id="a1757-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="a1757-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a1757-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a1757-1120">Keyword_passport</span></span>

- <span data-ttu-id="a1757-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a1757-1121">Passport Number</span></span>
- <span data-ttu-id="a1757-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="a1757-1122">Passport No</span></span>
- <span data-ttu-id="a1757-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="a1757-1123">Passport #</span></span>
- <span data-ttu-id="a1757-1124">Passaport #</span><span class="sxs-lookup"><span data-stu-id="a1757-1124">Passport#</span></span>
- <span data-ttu-id="a1757-1125">Passportid</span><span class="sxs-lookup"><span data-stu-id="a1757-1125">PassportID</span></span>
- <span data-ttu-id="a1757-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="a1757-1126">Passportno</span></span>
- <span data-ttu-id="a1757-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-1127">passportnumber</span></span>
- <span data-ttu-id="a1757-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="a1757-1128">パスポート</span></span>
- <span data-ttu-id="a1757-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a1757-1129">パスポート番号</span></span>
- <span data-ttu-id="a1757-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a1757-1130">パスポートのNum</span></span>
- <span data-ttu-id="a1757-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a1757-1131">パスポート＃</span></span>
- <span data-ttu-id="a1757-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a1757-1132">Numéro de passeport</span></span>
- <span data-ttu-id="a1757-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a1757-1133">Passeport n °</span></span>
- <span data-ttu-id="a1757-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a1757-1134">Passeport Non</span></span>
- <span data-ttu-id="a1757-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-1135">Passeport #</span></span>
- <span data-ttu-id="a1757-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-1136">Passeport#</span></span>
- <span data-ttu-id="a1757-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a1757-1137">PasseportNon</span></span>
- <span data-ttu-id="a1757-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a1757-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="a1757-1139">Número de identificação pessoal de saúde do Canadá (PHIN)</span><span class="sxs-lookup"><span data-stu-id="a1757-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1140">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1140">Format</span></span>

<span data-ttu-id="a1757-1141">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1142">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1142">Pattern</span></span>

<span data-ttu-id="a1757-1143">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1144">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1144">Checksum</span></span>

<span data-ttu-id="a1757-1145">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1146">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1146">Definition</span></span>

<span data-ttu-id="a1757-1147">Uma política de DLP é de 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a expressão regular Regex_canada_phin localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="a1757-1148">São encontradas pelo menos duas palavras-chave de Keyword_canada_phin ou Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="a1757-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1149">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="a1757-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="a1757-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="a1757-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a1757-1151">social insurance number</span></span>
- <span data-ttu-id="a1757-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="a1757-1152">health information act</span></span>
- <span data-ttu-id="a1757-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="a1757-1153">income tax information</span></span>
- <span data-ttu-id="a1757-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="a1757-1154">manitoba health</span></span>
- <span data-ttu-id="a1757-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="a1757-1155">health registration</span></span>
- <span data-ttu-id="a1757-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="a1757-1156">prescription purchases</span></span>
- <span data-ttu-id="a1757-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="a1757-1157">benefit eligibility</span></span>
- <span data-ttu-id="a1757-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="a1757-1158">personal health</span></span>
- <span data-ttu-id="a1757-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="a1757-1159">power of attorney</span></span>
- <span data-ttu-id="a1757-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="a1757-1160">registration number</span></span>
- <span data-ttu-id="a1757-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="a1757-1161">personal health number</span></span>
- <span data-ttu-id="a1757-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="a1757-1162">practitioner referral</span></span>
- <span data-ttu-id="a1757-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="a1757-1163">wellness professional</span></span>
- <span data-ttu-id="a1757-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="a1757-1164">patient referral</span></span>
- <span data-ttu-id="a1757-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="a1757-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="a1757-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="a1757-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="a1757-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="a1757-1167">Nunavut</span></span>
- <span data-ttu-id="a1757-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="a1757-1168">Quebec</span></span>
- <span data-ttu-id="a1757-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="a1757-1169">Northwest Territories</span></span>
- <span data-ttu-id="a1757-1170">Ontário</span><span class="sxs-lookup"><span data-stu-id="a1757-1170">Ontario</span></span>
- <span data-ttu-id="a1757-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="a1757-1171">British Columbia</span></span>
- <span data-ttu-id="a1757-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="a1757-1172">Alberta</span></span>
- <span data-ttu-id="a1757-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="a1757-1173">Saskatchewan</span></span>
- <span data-ttu-id="a1757-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="a1757-1174">Manitoba</span></span>
- <span data-ttu-id="a1757-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="a1757-1175">Yukon</span></span>
- <span data-ttu-id="a1757-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="a1757-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="a1757-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="a1757-1177">New Brunswick</span></span>
- <span data-ttu-id="a1757-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="a1757-1178">Nova Scotia</span></span>
- <span data-ttu-id="a1757-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="a1757-1179">Prince Edward Island</span></span>
- <span data-ttu-id="a1757-1180">Canadá</span><span class="sxs-lookup"><span data-stu-id="a1757-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="a1757-1181">Número de seguro social do Canadá</span><span class="sxs-lookup"><span data-stu-id="a1757-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1182">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1182">Format</span></span>

<span data-ttu-id="a1757-1183">Nove dígitos com espaços ou hífens opcionais</span><span class="sxs-lookup"><span data-stu-id="a1757-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1184">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1184">Pattern</span></span>

<span data-ttu-id="a1757-1185">Binário</span><span class="sxs-lookup"><span data-stu-id="a1757-1185">Formatted:</span></span>
- <span data-ttu-id="a1757-1186">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1186">Three digits</span></span> 
- <span data-ttu-id="a1757-1187">Um hífen ou espaço</span><span class="sxs-lookup"><span data-stu-id="a1757-1187">A hyphen or space</span></span> 
- <span data-ttu-id="a1757-1188">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1188">Three digits</span></span> 
- <span data-ttu-id="a1757-1189">Um hífen ou espaço</span><span class="sxs-lookup"><span data-stu-id="a1757-1189">A hyphen or space</span></span> 
- <span data-ttu-id="a1757-1190">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1190">Three digits</span></span>

<span data-ttu-id="a1757-1191">Não formatado: nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1192">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1192">Checksum</span></span>

<span data-ttu-id="a1757-1193">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1194">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1194">Definition</span></span>

<span data-ttu-id="a1757-1195">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1196">A função Func_canadian_sin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1197">Pelo menos duas de qualquer combinação do seguinte:</span><span class="sxs-lookup"><span data-stu-id="a1757-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="a1757-1198">Uma palavra-chave de Keyword_sin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="a1757-1199">Uma palavra-chave de Keyword_sin_collaborative for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="a1757-1200">A função Func_eu_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a1757-1201">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1201">The checksum passes.</span></span>

<span data-ttu-id="a1757-1202">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1203">A função Func_unformatted_canadian_sin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1204">Uma palavra-chave de Keyword_sin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="a1757-1205">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1205">The checksum passes.</span></span>

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1206">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="a1757-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="a1757-1207">Keyword_sin</span></span>

- <span data-ttu-id="a1757-1208">sin</span><span class="sxs-lookup"><span data-stu-id="a1757-1208">sin</span></span> 
- <span data-ttu-id="a1757-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="a1757-1209">social insurance</span></span> 
- <span data-ttu-id="a1757-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="a1757-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="a1757-1211">capitais</span><span class="sxs-lookup"><span data-stu-id="a1757-1211">sins</span></span> 
- <span data-ttu-id="a1757-1212">es</span><span class="sxs-lookup"><span data-stu-id="a1757-1212">ssn</span></span> 
- <span data-ttu-id="a1757-1213">CPFs</span><span class="sxs-lookup"><span data-stu-id="a1757-1213">ssns</span></span> 
- <span data-ttu-id="a1757-1214">social security</span><span class="sxs-lookup"><span data-stu-id="a1757-1214">social security</span></span> 
- <span data-ttu-id="a1757-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="a1757-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="a1757-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="a1757-1216">national identification number</span></span> 
- <span data-ttu-id="a1757-1217">national id</span><span class="sxs-lookup"><span data-stu-id="a1757-1217">national id</span></span> 
- <span data-ttu-id="a1757-1218">Sin #</span><span class="sxs-lookup"><span data-stu-id="a1757-1218">sin#</span></span> 
- <span data-ttu-id="a1757-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="a1757-1219">soc ins</span></span> 
- <span data-ttu-id="a1757-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="a1757-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="a1757-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a1757-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="a1757-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="a1757-1222">driver's license</span></span> 
- <span data-ttu-id="a1757-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="a1757-1223">drivers license</span></span> 
- <span data-ttu-id="a1757-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="a1757-1224">driver's licence</span></span> 
- <span data-ttu-id="a1757-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a1757-1225">drivers licence</span></span> 
- <span data-ttu-id="a1757-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="a1757-1226">DOB</span></span> 
- <span data-ttu-id="a1757-1227">Data de Nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-1227">Birthdate</span></span> 
- <span data-ttu-id="a1757-1228">Aniversário</span><span class="sxs-lookup"><span data-stu-id="a1757-1228">Birthday</span></span> 
- <span data-ttu-id="a1757-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="a1757-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="a1757-1230">	Número do Cartão de Identidade do Chile</span><span class="sxs-lookup"><span data-stu-id="a1757-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1231">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1231">Format</span></span>

<span data-ttu-id="a1757-1232">7-8 dígitos mais delimitadores um dígito ou letra de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1233">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1233">Pattern</span></span>

<span data-ttu-id="a1757-1234">7 a 8 dígitos mais delimitadores:</span><span class="sxs-lookup"><span data-stu-id="a1757-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="a1757-1235">1 a 2 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1235">1-2 digits</span></span> 
- <span data-ttu-id="a1757-1236">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-1236">A period</span></span> 
- <span data-ttu-id="a1757-1237">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1237">Three digits</span></span> 
- <span data-ttu-id="a1757-1238">Um ponto </span><span class="sxs-lookup"><span data-stu-id="a1757-1238">A period</span></span> 
- <span data-ttu-id="a1757-1239">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1239">Three digits</span></span> 
- <span data-ttu-id="a1757-1240">Um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-1240">A dash</span></span> 
- <span data-ttu-id="a1757-1241">Um dígito ou letra (não diferencia maiúscula de minúscula) que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1242">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1242">Checksum</span></span>

<span data-ttu-id="a1757-1243">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1244">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1244">Definition</span></span>

<span data-ttu-id="a1757-1245">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1246">A função Func_chile_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1247">Uma palavra-chave de Keyword_chile_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="a1757-1248">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1248">The checksum passes.</span></span>

<span data-ttu-id="a1757-1249">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1250">A função Func_chile_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1251">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1251">The checksum passes.</span></span>

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1252">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="a1757-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="a1757-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="a1757-1254">Número de Identificação Nacional</span><span class="sxs-lookup"><span data-stu-id="a1757-1254">National Identification Number</span></span> 
- <span data-ttu-id="a1757-1255">Cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-1255">Identity card</span></span> 
- <span data-ttu-id="a1757-1256">ID</span><span class="sxs-lookup"><span data-stu-id="a1757-1256">ID</span></span> 
- <span data-ttu-id="a1757-1257">Identificador</span><span class="sxs-lookup"><span data-stu-id="a1757-1257">Identification</span></span> 
- <span data-ttu-id="a1757-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="a1757-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="a1757-1259">SEJAM</span><span class="sxs-lookup"><span data-stu-id="a1757-1259">RUN</span></span> 
- <span data-ttu-id="a1757-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="a1757-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="a1757-1261">ROTINA</span><span class="sxs-lookup"><span data-stu-id="a1757-1261">RUT</span></span> 
- <span data-ttu-id="a1757-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="a1757-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="a1757-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="a1757-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="a1757-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="a1757-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="a1757-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="a1757-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="a1757-1266">	Número do Cartão de Identidade de Residentes (PRC) da China</span><span class="sxs-lookup"><span data-stu-id="a1757-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1267">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1267">Format</span></span>

<span data-ttu-id="a1757-1268">18 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1269">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1269">Pattern</span></span>

<span data-ttu-id="a1757-1270">18 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-1270">18 digits:</span></span>
- <span data-ttu-id="a1757-1271">Seis dígitos que são um código de endereço </span><span class="sxs-lookup"><span data-stu-id="a1757-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="a1757-1272">Oito dígitos no formato AAAAMMDD que são a data de nascimento </span><span class="sxs-lookup"><span data-stu-id="a1757-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a1757-1273">Três dígitos que são um código de pedido </span><span class="sxs-lookup"><span data-stu-id="a1757-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="a1757-1274">Um dígito que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1275">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1275">Checksum</span></span>

<span data-ttu-id="a1757-1276">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1277">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1277">Definition</span></span>

<span data-ttu-id="a1757-1278">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1279">A função Func_china_resident_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1280">Uma palavra-chave de Keyword_china_resident_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="a1757-1281">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1281">The checksum passes.</span></span>

<span data-ttu-id="a1757-1282">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1283">A função Func_china_resident_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1284">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1284">The checksum passes.</span></span>

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1285">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="a1757-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="a1757-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="a1757-1287">Cartão de Identidade da Polônia</span><span class="sxs-lookup"><span data-stu-id="a1757-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="a1757-1288">POPULAR</span><span class="sxs-lookup"><span data-stu-id="a1757-1288">PRC</span></span> 
- <span data-ttu-id="a1757-1289">Cartão de Identificação Nacional</span><span class="sxs-lookup"><span data-stu-id="a1757-1289">National Identification Card</span></span> 
- <span data-ttu-id="a1757-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="a1757-1290">身份证</span></span> 
- <span data-ttu-id="a1757-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="a1757-1291">居民 身份证</span></span> 
- <span data-ttu-id="a1757-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="a1757-1292">居民身份证</span></span> 
- <span data-ttu-id="a1757-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="a1757-1293">鉴定</span></span> 
- <span data-ttu-id="a1757-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="a1757-1294">身分證</span></span> 
- <span data-ttu-id="a1757-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-1295">居民 身份證</span></span>
- <span data-ttu-id="a1757-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="a1757-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="a1757-1297">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="a1757-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1298">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1298">Format</span></span>

<span data-ttu-id="a1757-1299">14 a 16 dígitos que podem ser formatados ou não formatados (dddddddddddddddd) e que devem passar no teste Luhn.</span><span class="sxs-lookup"><span data-stu-id="a1757-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1300">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1300">Pattern</span></span>

<span data-ttu-id="a1757-1301">Padrão muito complexo e robusto que detecta cartões de todas as principais marcas em todo o mundo, incluindo Visa, MasterCard, Discover Card, JCB, American Express, vales-presentes e cartões diner.</span><span class="sxs-lookup"><span data-stu-id="a1757-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1302">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1302">Checksum</span></span>

<span data-ttu-id="a1757-1303">Sim, a soma de verificação Luhn</span><span class="sxs-lookup"><span data-stu-id="a1757-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1304">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1304">Definition</span></span>

<span data-ttu-id="a1757-1305">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1306">A função Func_credit_card localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1307">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-1307">One of the following is true:</span></span>
    - <span data-ttu-id="a1757-1308">Uma palavra-chave de Keyword_cc_verification for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="a1757-1309">Uma palavra-chave de Keyword_cc_name for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="a1757-1310">A função Func_expiration_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a1757-1311">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1311">The checksum passes.</span></span>

<span data-ttu-id="a1757-1312">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1313">A função Func_credit_card localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1314">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1314">The checksum passes.</span></span>

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1315">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="a1757-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="a1757-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="a1757-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="a1757-1317">card verification</span></span>
- <span data-ttu-id="a1757-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="a1757-1318">card identification number</span></span>
- <span data-ttu-id="a1757-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="a1757-1319">cvn</span></span>
- <span data-ttu-id="a1757-1320">CID</span><span class="sxs-lookup"><span data-stu-id="a1757-1320">cid</span></span>
- <span data-ttu-id="a1757-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="a1757-1321">cvc2</span></span>
- <span data-ttu-id="a1757-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="a1757-1322">cvv2</span></span>
- <span data-ttu-id="a1757-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="a1757-1323">pin block</span></span>
- <span data-ttu-id="a1757-1324">security code</span><span class="sxs-lookup"><span data-stu-id="a1757-1324">security code</span></span>
- <span data-ttu-id="a1757-1325">security number</span><span class="sxs-lookup"><span data-stu-id="a1757-1325">security number</span></span>
- <span data-ttu-id="a1757-1326">security no</span><span class="sxs-lookup"><span data-stu-id="a1757-1326">security no</span></span>
- <span data-ttu-id="a1757-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="a1757-1327">issue number</span></span>
- <span data-ttu-id="a1757-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="a1757-1328">issue no</span></span>
- <span data-ttu-id="a1757-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="a1757-1329">cryptogramme</span></span>
- <span data-ttu-id="a1757-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="a1757-1330">numéro de sécurité</span></span>
- <span data-ttu-id="a1757-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="a1757-1331">numero de securite</span></span>
- <span data-ttu-id="a1757-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="a1757-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="a1757-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="a1757-1334">prüfziffer</span></span>
- <span data-ttu-id="a1757-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="a1757-1335">prufziffer</span></span>
- <span data-ttu-id="a1757-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="a1757-1336">sicherheits Kode</span></span>
- <span data-ttu-id="a1757-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="a1757-1337">sicherheitscode</span></span>
- <span data-ttu-id="a1757-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="a1757-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="a1757-1339">verfalldatum</span></span>
- <span data-ttu-id="a1757-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="a1757-1340">codice di verifica</span></span>
- <span data-ttu-id="a1757-1341">COD.</span><span class="sxs-lookup"><span data-stu-id="a1757-1341">cod.</span></span> <span data-ttu-id="a1757-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1757-1342">sicurezza</span></span>
- <span data-ttu-id="a1757-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1757-1343">cod sicurezza</span></span>
- <span data-ttu-id="a1757-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a1757-1344">n autorizzazione</span></span>
- <span data-ttu-id="a1757-1345">CFOP</span><span class="sxs-lookup"><span data-stu-id="a1757-1345">código</span></span>
- <span data-ttu-id="a1757-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="a1757-1346">codigo</span></span>
- <span data-ttu-id="a1757-1347">COD.</span><span class="sxs-lookup"><span data-stu-id="a1757-1347">cod.</span></span> <span data-ttu-id="a1757-1348">seg</span><span class="sxs-lookup"><span data-stu-id="a1757-1348">seg</span></span>
- <span data-ttu-id="a1757-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="a1757-1349">cod seg</span></span>
- <span data-ttu-id="a1757-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1350">código de segurança</span></span>
- <span data-ttu-id="a1757-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1351">codigo de seguranca</span></span>
- <span data-ttu-id="a1757-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1352">codigo de segurança</span></span>
- <span data-ttu-id="a1757-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1353">código de seguranca</span></span>
- <span data-ttu-id="a1757-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="a1757-1354">cód.</span></span> <span data-ttu-id="a1757-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1355">segurança</span></span>
- <span data-ttu-id="a1757-1356">COD.</span><span class="sxs-lookup"><span data-stu-id="a1757-1356">cod.</span></span> <span data-ttu-id="a1757-1357">seguranca Cod.</span><span class="sxs-lookup"><span data-stu-id="a1757-1357">seguranca cod.</span></span> <span data-ttu-id="a1757-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1358">segurança</span></span>
- <span data-ttu-id="a1757-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="a1757-1359">cód.</span></span> <span data-ttu-id="a1757-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1360">seguranca</span></span>
- <span data-ttu-id="a1757-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1361">cód segurança</span></span>
- <span data-ttu-id="a1757-1362">COD seguranca COD segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="a1757-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1363">cód seguranca</span></span>
- <span data-ttu-id="a1757-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1364">número de verificação</span></span>
- <span data-ttu-id="a1757-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="a1757-1365">numero de verificacao</span></span>
- <span data-ttu-id="a1757-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="a1757-1366">ablauf</span></span>
- <span data-ttu-id="a1757-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="a1757-1367">gültig bis</span></span>
- <span data-ttu-id="a1757-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a1757-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="a1757-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="a1757-1369">gultig bis</span></span>
- <span data-ttu-id="a1757-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a1757-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="a1757-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="a1757-1371">scadenza</span></span>
- <span data-ttu-id="a1757-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="a1757-1372">data scad</span></span>
- <span data-ttu-id="a1757-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="a1757-1373">fecha de expiracion</span></span>
- <span data-ttu-id="a1757-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="a1757-1374">fecha de venc</span></span>
- <span data-ttu-id="a1757-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="a1757-1375">vencimiento</span></span>
- <span data-ttu-id="a1757-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="a1757-1376">válido hasta</span></span>
- <span data-ttu-id="a1757-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="a1757-1377">valido hasta</span></span>
- <span data-ttu-id="a1757-1378">vto</span><span class="sxs-lookup"><span data-stu-id="a1757-1378">vto</span></span>
- <span data-ttu-id="a1757-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="a1757-1379">data de expiração</span></span>
- <span data-ttu-id="a1757-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="a1757-1380">data de expiracao</span></span>
- <span data-ttu-id="a1757-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="a1757-1381">data em que expira</span></span>
- <span data-ttu-id="a1757-1382">validade</span><span class="sxs-lookup"><span data-stu-id="a1757-1382">validade</span></span>
- <span data-ttu-id="a1757-1383">coragem</span><span class="sxs-lookup"><span data-stu-id="a1757-1383">valor</span></span>
- <span data-ttu-id="a1757-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="a1757-1384">vencimento</span></span>
- <span data-ttu-id="a1757-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="a1757-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="a1757-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="a1757-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="a1757-1387">amex</span><span class="sxs-lookup"><span data-stu-id="a1757-1387">amex</span></span>
- <span data-ttu-id="a1757-1388">american express</span><span class="sxs-lookup"><span data-stu-id="a1757-1388">american express</span></span>
- <span data-ttu-id="a1757-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="a1757-1389">americanexpress</span></span>
- <span data-ttu-id="a1757-1390">Cartões</span><span class="sxs-lookup"><span data-stu-id="a1757-1390">Visa</span></span>
- <span data-ttu-id="a1757-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="a1757-1391">mastercard</span></span>
- <span data-ttu-id="a1757-1392">master card</span><span class="sxs-lookup"><span data-stu-id="a1757-1392">master card</span></span>
- <span data-ttu-id="a1757-1393">MC</span><span class="sxs-lookup"><span data-stu-id="a1757-1393">mc</span></span> 
- <span data-ttu-id="a1757-1394">MasterCards</span><span class="sxs-lookup"><span data-stu-id="a1757-1394">mastercards</span></span>
- <span data-ttu-id="a1757-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1395">master cards</span></span>
- <span data-ttu-id="a1757-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="a1757-1396">diner's Club</span></span>
- <span data-ttu-id="a1757-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="a1757-1397">diners club</span></span>
- <span data-ttu-id="a1757-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="a1757-1398">dinersclub</span></span>
- <span data-ttu-id="a1757-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="a1757-1399">discover card</span></span>
- <span data-ttu-id="a1757-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="a1757-1400">discovercard</span></span>
- <span data-ttu-id="a1757-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1401">discover cards</span></span>
- <span data-ttu-id="a1757-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="a1757-1402">JCB</span></span>
- <span data-ttu-id="a1757-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="a1757-1403">japanese card bureau</span></span>
- <span data-ttu-id="a1757-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="a1757-1404">carte blanche</span></span>
- <span data-ttu-id="a1757-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="a1757-1405">carteblanche</span></span>
- <span data-ttu-id="a1757-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="a1757-1406">credit card</span></span>
- <span data-ttu-id="a1757-1407">colocado #</span><span class="sxs-lookup"><span data-stu-id="a1757-1407">cc#</span></span>
- <span data-ttu-id="a1757-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="a1757-1408">cc#:</span></span>
- <span data-ttu-id="a1757-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="a1757-1409">expiration date</span></span>
- <span data-ttu-id="a1757-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="a1757-1410">exp date</span></span>
- <span data-ttu-id="a1757-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="a1757-1411">expiry date</span></span>
- <span data-ttu-id="a1757-1412">Data de d'expiration</span><span class="sxs-lookup"><span data-stu-id="a1757-1412">date d'expiration</span></span>
- <span data-ttu-id="a1757-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="a1757-1413">date d'exp</span></span>
- <span data-ttu-id="a1757-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="a1757-1414">date expiration</span></span>
- <span data-ttu-id="a1757-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="a1757-1415">bank card</span></span>
- <span data-ttu-id="a1757-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="a1757-1416">bankcard</span></span>
- <span data-ttu-id="a1757-1417">card number</span><span class="sxs-lookup"><span data-stu-id="a1757-1417">card number</span></span>
- <span data-ttu-id="a1757-1418">card num</span><span class="sxs-lookup"><span data-stu-id="a1757-1418">card num</span></span>
- <span data-ttu-id="a1757-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-1419">cardnumber</span></span>
- <span data-ttu-id="a1757-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="a1757-1420">cardnumbers</span></span>
- <span data-ttu-id="a1757-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="a1757-1421">card numbers</span></span>
- <span data-ttu-id="a1757-1422">CreditCard</span><span class="sxs-lookup"><span data-stu-id="a1757-1422">creditcard</span></span>
- <span data-ttu-id="a1757-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1423">credit cards</span></span>
- <span data-ttu-id="a1757-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="a1757-1424">creditcards</span></span>
- <span data-ttu-id="a1757-1425">CCN</span><span class="sxs-lookup"><span data-stu-id="a1757-1425">ccn</span></span>
- <span data-ttu-id="a1757-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="a1757-1426">card holder</span></span>
- <span data-ttu-id="a1757-1427">aos</span><span class="sxs-lookup"><span data-stu-id="a1757-1427">cardholder</span></span>
- <span data-ttu-id="a1757-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="a1757-1428">card holders</span></span>
- <span data-ttu-id="a1757-1429">titulares de cartões</span><span class="sxs-lookup"><span data-stu-id="a1757-1429">cardholders</span></span>
- <span data-ttu-id="a1757-1430">check card</span><span class="sxs-lookup"><span data-stu-id="a1757-1430">check card</span></span>
- <span data-ttu-id="a1757-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="a1757-1431">checkcard</span></span>
- <span data-ttu-id="a1757-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1432">check cards</span></span>
- <span data-ttu-id="a1757-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="a1757-1433">checkcards</span></span>
- <span data-ttu-id="a1757-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="a1757-1434">debit card</span></span>
- <span data-ttu-id="a1757-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="a1757-1435">debitcard</span></span>
- <span data-ttu-id="a1757-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1436">debit cards</span></span>
- <span data-ttu-id="a1757-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="a1757-1437">debitcards</span></span>
- <span data-ttu-id="a1757-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="a1757-1438">atm card</span></span>
- <span data-ttu-id="a1757-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="a1757-1439">atmcard</span></span>
- <span data-ttu-id="a1757-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1440">atm cards</span></span>
- <span data-ttu-id="a1757-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="a1757-1441">atmcards</span></span>
- <span data-ttu-id="a1757-1442">encaminhar</span><span class="sxs-lookup"><span data-stu-id="a1757-1442">enroute</span></span>
- <span data-ttu-id="a1757-1443">en route</span><span class="sxs-lookup"><span data-stu-id="a1757-1443">en route</span></span>
- <span data-ttu-id="a1757-1444">card type</span><span class="sxs-lookup"><span data-stu-id="a1757-1444">card type</span></span>
- <span data-ttu-id="a1757-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="a1757-1445">carte bancaire</span></span>
- <span data-ttu-id="a1757-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="a1757-1446">carte de crédit</span></span>
- <span data-ttu-id="a1757-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="a1757-1447">carte de credit</span></span>
- <span data-ttu-id="a1757-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="a1757-1448">numéro de carte</span></span>
- <span data-ttu-id="a1757-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="a1757-1449">numero de carte</span></span>
- <span data-ttu-id="a1757-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="a1757-1450">nº de la carte</span></span>
- <span data-ttu-id="a1757-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="a1757-1451">nº de carte</span></span>
- <span data-ttu-id="a1757-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="a1757-1452">kreditkarte</span></span>
- <span data-ttu-id="a1757-1453">karte</span><span class="sxs-lookup"><span data-stu-id="a1757-1453">karte</span></span>
- <span data-ttu-id="a1757-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="a1757-1454">karteninhaber</span></span>
- <span data-ttu-id="a1757-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a1757-1455">karteninhabers</span></span>
- <span data-ttu-id="a1757-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="a1757-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="a1757-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="a1757-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="a1757-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="a1757-1458">kreditkartentyp</span></span>
- <span data-ttu-id="a1757-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="a1757-1459">eigentümername</span></span>
- <span data-ttu-id="a1757-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="a1757-1460">kartennr</span></span> 
- <span data-ttu-id="a1757-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1461">kartennummer</span></span>
- <span data-ttu-id="a1757-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1462">kreditkartennummer</span></span>
- <span data-ttu-id="a1757-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="a1757-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1464">carta di credito</span></span>
- <span data-ttu-id="a1757-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1465">carta credito</span></span>
- <span data-ttu-id="a1757-1466">carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1466">carta</span></span>
- <span data-ttu-id="a1757-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1467">n carta</span></span>
- <span data-ttu-id="a1757-1468">nr.</span><span class="sxs-lookup"><span data-stu-id="a1757-1468">nr.</span></span> <span data-ttu-id="a1757-1469">carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1469">carta</span></span>
- <span data-ttu-id="a1757-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1470">nr carta</span></span>
- <span data-ttu-id="a1757-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1471">numero carta</span></span>
- <span data-ttu-id="a1757-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1472">numero della carta</span></span>
- <span data-ttu-id="a1757-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1473">numero di carta</span></span>
- <span data-ttu-id="a1757-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1474">tarjeta credito</span></span>
- <span data-ttu-id="a1757-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1475">tarjeta de credito</span></span>
- <span data-ttu-id="a1757-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="a1757-1476">tarjeta crédito</span></span>
- <span data-ttu-id="a1757-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="a1757-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="a1757-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="a1757-1478">tarjeta de atm</span></span>
- <span data-ttu-id="a1757-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="a1757-1479">tarjeta atm</span></span>
- <span data-ttu-id="a1757-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1480">tarjeta debito</span></span>
- <span data-ttu-id="a1757-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1481">tarjeta de debito</span></span>
- <span data-ttu-id="a1757-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="a1757-1482">tarjeta débito</span></span>
- <span data-ttu-id="a1757-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="a1757-1483">tarjeta de débito</span></span>
- <span data-ttu-id="a1757-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1484">nº de tarjeta</span></span>
- <span data-ttu-id="a1757-1485">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-1485">no.</span></span> <span data-ttu-id="a1757-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1486">de tarjeta</span></span>
- <span data-ttu-id="a1757-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1487">no de tarjeta</span></span>
- <span data-ttu-id="a1757-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1488">numero de tarjeta</span></span>
- <span data-ttu-id="a1757-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1489">número de tarjeta</span></span>
- <span data-ttu-id="a1757-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="a1757-1490">tarjeta no</span></span>
- <span data-ttu-id="a1757-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="a1757-1491">tarjetahabiente</span></span>
- <span data-ttu-id="a1757-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="a1757-1492">cartão de crédito</span></span>
- <span data-ttu-id="a1757-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1493">cartão de credito</span></span>
- <span data-ttu-id="a1757-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="a1757-1494">cartao de crédito</span></span>
- <span data-ttu-id="a1757-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1495">cartao de credito</span></span>
- <span data-ttu-id="a1757-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="a1757-1496">cartão de débito</span></span>
- <span data-ttu-id="a1757-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="a1757-1497">cartao de débito</span></span>
- <span data-ttu-id="a1757-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1498">cartão de debito</span></span>
- <span data-ttu-id="a1757-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1499">cartao de debito</span></span>
- <span data-ttu-id="a1757-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="a1757-1500">débito automático</span></span>
- <span data-ttu-id="a1757-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="a1757-1501">debito automatico</span></span>
- <span data-ttu-id="a1757-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1502">número do cartão</span></span>
- <span data-ttu-id="a1757-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1503">numero do cartão</span></span> 
- <span data-ttu-id="a1757-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1504">número do cartao</span></span>
- <span data-ttu-id="a1757-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1505">numero do cartao</span></span>
- <span data-ttu-id="a1757-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1506">número de cartão</span></span>
- <span data-ttu-id="a1757-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1507">numero de cartão</span></span>
- <span data-ttu-id="a1757-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1508">número de cartao</span></span>
- <span data-ttu-id="a1757-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1509">numero de cartao</span></span>
- <span data-ttu-id="a1757-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1510">nº do cartão</span></span>
- <span data-ttu-id="a1757-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1511">nº do cartao</span></span>
- <span data-ttu-id="a1757-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="a1757-1512">nº.</span></span> <span data-ttu-id="a1757-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1513">do cartão</span></span>
- <span data-ttu-id="a1757-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1514">no do cartão</span></span>
- <span data-ttu-id="a1757-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1515">no do cartao</span></span>
- <span data-ttu-id="a1757-1516">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-1516">no.</span></span> <span data-ttu-id="a1757-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1517">do cartão</span></span>
- <span data-ttu-id="a1757-1518">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-1518">no.</span></span> <span data-ttu-id="a1757-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="a1757-1520">	Número do Cartão de Identidade da Croácia</span><span class="sxs-lookup"><span data-stu-id="a1757-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1521">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1521">Format</span></span>

<span data-ttu-id="a1757-1522">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1523">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1523">Pattern</span></span>

<span data-ttu-id="a1757-1524">Nove dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1525">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1525">Checksum</span></span>

<span data-ttu-id="a1757-1526">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1527">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1527">Definition</span></span>

<span data-ttu-id="a1757-1528">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1529">A função Func_croatia_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1530">Uma palavra-chave de Keyword_croatia_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1531">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="a1757-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="a1757-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="a1757-1533">Cartão de identidade croata</span><span class="sxs-lookup"><span data-stu-id="a1757-1533">Croatian identity card</span></span>
- <span data-ttu-id="a1757-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="a1757-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="a1757-1535">	Número de Identificação Pessoal (OIB) da Croácia</span><span class="sxs-lookup"><span data-stu-id="a1757-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1536">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1536">Format</span></span>

<span data-ttu-id="a1757-1537">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1538">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1538">Pattern</span></span>

<span data-ttu-id="a1757-1539">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-1539">11 digits:</span></span>
- <span data-ttu-id="a1757-1540">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1540">10 digits</span></span> 
- <span data-ttu-id="a1757-1541">O dígito final é um dígito de verificação para os fins de troca de dados internacionais, as letras de RH são adicionadas antes dos onze dígitos.</span><span class="sxs-lookup"><span data-stu-id="a1757-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1542">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1542">Checksum</span></span>

<span data-ttu-id="a1757-1543">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1544">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1544">Definition</span></span>

<span data-ttu-id="a1757-1545">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1546">A função Func_croatia_oib_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1547">Uma palavra-chave de Keyword_croatia_oib_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="a1757-1548">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1548">The checksum passes.</span></span>

<span data-ttu-id="a1757-1549">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1550">A função Func_croatia_oib_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1551">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1551">The checksum passes.</span></span>

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1552">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="a1757-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="a1757-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="a1757-1554">Número de Identificação Pessoal</span><span class="sxs-lookup"><span data-stu-id="a1757-1554">Personal Identification Number</span></span>
- <span data-ttu-id="a1757-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="a1757-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="a1757-1556">NIB</span><span class="sxs-lookup"><span data-stu-id="a1757-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="a1757-1557">Número de identidade pessoal tcheco</span><span class="sxs-lookup"><span data-stu-id="a1757-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1558">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1558">Format</span></span>

<span data-ttu-id="a1757-1559">Nove dígitos com barra de avanço opcional (formato antigo) 10 dígitos com barra de avanço opcional (novo formato)</span><span class="sxs-lookup"><span data-stu-id="a1757-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1560">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1560">Pattern</span></span>

<span data-ttu-id="a1757-1561">Nove dígitos (formato antigo):</span><span class="sxs-lookup"><span data-stu-id="a1757-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="a1757-1562">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1562">Nine digits</span></span>

<span data-ttu-id="a1757-1563">OU</span><span class="sxs-lookup"><span data-stu-id="a1757-1563">OR</span></span>

- <span data-ttu-id="a1757-1564">Seis dígitos que representam a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="a1757-1565">Uma barra</span><span class="sxs-lookup"><span data-stu-id="a1757-1565">A forward slash</span></span>
- <span data-ttu-id="a1757-1566">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1566">Three digits</span></span>

<span data-ttu-id="a1757-1567">10 dígitos (novo formato):</span><span class="sxs-lookup"><span data-stu-id="a1757-1567">10 digits (new format):</span></span>
- <span data-ttu-id="a1757-1568">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1568">10 digits</span></span>

<span data-ttu-id="a1757-1569">OU</span><span class="sxs-lookup"><span data-stu-id="a1757-1569">OR</span></span>

- <span data-ttu-id="a1757-1570">Seis dígitos que representam a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="a1757-1571">Uma barra</span><span class="sxs-lookup"><span data-stu-id="a1757-1571">A forward slash</span></span> 
- <span data-ttu-id="a1757-1572">Quatro dígitos onde o último dígito é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1573">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1573">Checksum</span></span>

<span data-ttu-id="a1757-1574">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1575">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1575">Definition</span></span>

<span data-ttu-id="a1757-1576">Uma política de DLP é de 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a função Func_czech_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="a1757-1577">Uma palavra-chave de Keyword_czech_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="a1757-1578">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="a1757-1579">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1579">Keywords</span></span>

- <span data-ttu-id="a1757-1580">número de identidade pessoal tcheco</span><span class="sxs-lookup"><span data-stu-id="a1757-1580">czech personal identity number</span></span>
- <span data-ttu-id="a1757-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="a1757-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="a1757-1582">	Número de Identificação Pessoal da Dinamarca</span><span class="sxs-lookup"><span data-stu-id="a1757-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1583">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1583">Format</span></span>

<span data-ttu-id="a1757-1584">10 dígitos que contêm um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1585">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1585">Pattern</span></span>

<span data-ttu-id="a1757-1586">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-1586">10 digits:</span></span>
- <span data-ttu-id="a1757-1587">Seis dígitos no formato DDMMAA que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a1757-1588">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-1588">A hyphen</span></span> 
- <span data-ttu-id="a1757-1589">Quatro dígitos em que o último é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1590">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1590">Checksum</span></span>

<span data-ttu-id="a1757-1591">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1592">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1592">Definition</span></span>

<span data-ttu-id="a1757-1593">Uma política de DLP é de 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a expressão regular Regex_denmark_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="a1757-1594">Uma palavra-chave de Keyword_denmark_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="a1757-1595">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1596">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="a1757-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="a1757-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="a1757-1598">Número de Identificação Pessoal</span><span class="sxs-lookup"><span data-stu-id="a1757-1598">Personal Identification Number</span></span>
- <span data-ttu-id="a1757-1599">PEDIR</span><span class="sxs-lookup"><span data-stu-id="a1757-1599">CPR</span></span>
- <span data-ttu-id="a1757-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="a1757-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="a1757-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="a1757-1602">Número da Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="a1757-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1603">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1603">Format</span></span>

<span data-ttu-id="a1757-1604">Duas letras seguidas por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1605">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1605">Pattern</span></span>

<span data-ttu-id="a1757-1606">O padrão deve incluir todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="a1757-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a1757-1607">Uma letra (não diferencia maiúscula de minúscula) deste conjunto de letras possíveis: abcdefghjklmnprstux, que é um código de inscrito</span><span class="sxs-lookup"><span data-stu-id="a1757-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="a1757-1608">Uma letra (não diferencia maiúscula de minúscula), que é a primeira letra do sobrenome do inscrito</span><span class="sxs-lookup"><span data-stu-id="a1757-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="a1757-1609">Sete dígitos, dos quais o último é o dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1610">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1610">Checksum</span></span>

<span data-ttu-id="a1757-1611">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1612">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1612">Definition</span></span>

<span data-ttu-id="a1757-1613">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1614">A função Func_dea_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1615">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1616">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1616">Keywords</span></span>

<span data-ttu-id="a1757-1617">None</span><span class="sxs-lookup"><span data-stu-id="a1757-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="a1757-1618">Número de cartão de débito da UE</span><span class="sxs-lookup"><span data-stu-id="a1757-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1619">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1619">Format</span></span>

<span data-ttu-id="a1757-1620">16 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1621">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1621">Pattern</span></span>

<span data-ttu-id="a1757-1622">Padrão muito complexo e robusto</span><span class="sxs-lookup"><span data-stu-id="a1757-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1623">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1623">Checksum</span></span>

<span data-ttu-id="a1757-1624">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1625">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1625">Definition</span></span>

<span data-ttu-id="a1757-1626">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1627">A função Func_eu_debit_card localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1628">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="a1757-1629">Uma palavra-chave de Keyword_eu_debit_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="a1757-1630">Uma palavra-chave de Keyword_card_terms_dict for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="a1757-1631">Uma palavra-chave de Keyword_card_security_terms_dict for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="a1757-1632">Uma palavra-chave de Keyword_card_expiration_terms_dict for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="a1757-1633">A função Func_expiration_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a1757-1634">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1634">The checksum passes.</span></span>

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1635">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="a1757-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="a1757-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="a1757-1637">account number</span><span class="sxs-lookup"><span data-stu-id="a1757-1637">account number</span></span> 
- <span data-ttu-id="a1757-1638">card number</span><span class="sxs-lookup"><span data-stu-id="a1757-1638">card number</span></span> 
- <span data-ttu-id="a1757-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="a1757-1639">card no.</span></span> 
- <span data-ttu-id="a1757-1640">security number</span><span class="sxs-lookup"><span data-stu-id="a1757-1640">security number</span></span> 
- <span data-ttu-id="a1757-1641">colocado #</span><span class="sxs-lookup"><span data-stu-id="a1757-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="a1757-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a1757-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="a1757-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="a1757-1643">acct nbr</span></span> 
- <span data-ttu-id="a1757-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="a1757-1644">acct num</span></span> 
- <span data-ttu-id="a1757-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="a1757-1645">acct no</span></span> 
- <span data-ttu-id="a1757-1646">american express</span><span class="sxs-lookup"><span data-stu-id="a1757-1646">american express</span></span> 
- <span data-ttu-id="a1757-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="a1757-1647">americanexpress</span></span> 
- <span data-ttu-id="a1757-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="a1757-1648">americano espresso</span></span> 
- <span data-ttu-id="a1757-1649">amex</span><span class="sxs-lookup"><span data-stu-id="a1757-1649">amex</span></span> 
- <span data-ttu-id="a1757-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="a1757-1650">atm card</span></span> 
- <span data-ttu-id="a1757-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1651">atm cards</span></span> 
- <span data-ttu-id="a1757-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="a1757-1652">atm kaart</span></span> 
- <span data-ttu-id="a1757-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="a1757-1653">atmcard</span></span> 
- <span data-ttu-id="a1757-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="a1757-1654">atmcards</span></span> 
- <span data-ttu-id="a1757-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="a1757-1655">atmkaart</span></span> 
- <span data-ttu-id="a1757-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="a1757-1656">atmkaarten</span></span> 
- <span data-ttu-id="a1757-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="a1757-1657">bancontact</span></span> 
- <span data-ttu-id="a1757-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="a1757-1658">bank card</span></span> 
- <span data-ttu-id="a1757-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="a1757-1659">bankkaart</span></span> 
- <span data-ttu-id="a1757-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="a1757-1660">card holder</span></span> 
- <span data-ttu-id="a1757-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="a1757-1661">card holders</span></span> 
- <span data-ttu-id="a1757-1662">card num</span><span class="sxs-lookup"><span data-stu-id="a1757-1662">card num</span></span> 
- <span data-ttu-id="a1757-1663">card number</span><span class="sxs-lookup"><span data-stu-id="a1757-1663">card number</span></span> 
- <span data-ttu-id="a1757-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="a1757-1664">card numbers</span></span> 
- <span data-ttu-id="a1757-1665">card type</span><span class="sxs-lookup"><span data-stu-id="a1757-1665">card type</span></span> 
- <span data-ttu-id="a1757-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="a1757-1666">cardano numerico</span></span> 
- <span data-ttu-id="a1757-1667">aos</span><span class="sxs-lookup"><span data-stu-id="a1757-1667">cardholder</span></span> 
- <span data-ttu-id="a1757-1668">titulares de cartões</span><span class="sxs-lookup"><span data-stu-id="a1757-1668">cardholders</span></span> 
- <span data-ttu-id="a1757-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-1669">cardnumber</span></span> 
- <span data-ttu-id="a1757-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="a1757-1670">cardnumbers</span></span> 
- <span data-ttu-id="a1757-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="a1757-1671">carta bianca</span></span> 
- <span data-ttu-id="a1757-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1672">carta credito</span></span> 
- <span data-ttu-id="a1757-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1673">carta di credito</span></span> 
- <span data-ttu-id="a1757-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1674">cartao de credito</span></span> 
- <span data-ttu-id="a1757-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="a1757-1675">cartao de crédito</span></span> 
- <span data-ttu-id="a1757-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1676">cartao de debito</span></span> 
- <span data-ttu-id="a1757-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="a1757-1677">cartao de débito</span></span> 
- <span data-ttu-id="a1757-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="a1757-1678">carte bancaire</span></span> 
- <span data-ttu-id="a1757-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="a1757-1679">carte blanche</span></span> 
- <span data-ttu-id="a1757-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="a1757-1680">carte bleue</span></span> 
- <span data-ttu-id="a1757-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="a1757-1681">carte de credit</span></span> 
- <span data-ttu-id="a1757-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="a1757-1682">carte de crédit</span></span> 
- <span data-ttu-id="a1757-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1683">carte di credito</span></span> 
- <span data-ttu-id="a1757-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="a1757-1684">carteblanche</span></span> 
- <span data-ttu-id="a1757-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1685">cartão de credito</span></span> 
- <span data-ttu-id="a1757-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="a1757-1686">cartão de crédito</span></span> 
- <span data-ttu-id="a1757-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1687">cartão de debito</span></span> 
- <span data-ttu-id="a1757-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="a1757-1688">cartão de débito</span></span> 
- <span data-ttu-id="a1757-1689">cb</span><span class="sxs-lookup"><span data-stu-id="a1757-1689">cb</span></span> 
- <span data-ttu-id="a1757-1690">CCN</span><span class="sxs-lookup"><span data-stu-id="a1757-1690">ccn</span></span> 
- <span data-ttu-id="a1757-1691">check card</span><span class="sxs-lookup"><span data-stu-id="a1757-1691">check card</span></span> 
- <span data-ttu-id="a1757-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1692">check cards</span></span> 
- <span data-ttu-id="a1757-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="a1757-1693">checkcard</span></span>
- <span data-ttu-id="a1757-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="a1757-1694">checkcards</span></span> 
- <span data-ttu-id="a1757-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="a1757-1695">chequekaart</span></span> 
- <span data-ttu-id="a1757-1696">Cirrus</span><span class="sxs-lookup"><span data-stu-id="a1757-1696">cirrus</span></span> 
- <span data-ttu-id="a1757-1697">Cirrus-EDC-maestro</span><span class="sxs-lookup"><span data-stu-id="a1757-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="a1757-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="a1757-1698">controlekaart</span></span> 
- <span data-ttu-id="a1757-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="a1757-1699">controlekaarten</span></span> 
- <span data-ttu-id="a1757-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="a1757-1700">credit card</span></span> 
- <span data-ttu-id="a1757-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1701">credit cards</span></span> 
- <span data-ttu-id="a1757-1702">CreditCard</span><span class="sxs-lookup"><span data-stu-id="a1757-1702">creditcard</span></span> 
- <span data-ttu-id="a1757-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="a1757-1703">creditcards</span></span> 
- <span data-ttu-id="a1757-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="a1757-1704">debetkaart</span></span> 
- <span data-ttu-id="a1757-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="a1757-1705">debetkaarten</span></span> 
- <span data-ttu-id="a1757-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="a1757-1706">debit card</span></span> 
- <span data-ttu-id="a1757-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1707">debit cards</span></span> 
- <span data-ttu-id="a1757-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="a1757-1708">debitcard</span></span> 
- <span data-ttu-id="a1757-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="a1757-1709">debitcards</span></span> 
- <span data-ttu-id="a1757-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="a1757-1710">debito automatico</span></span> 
- <span data-ttu-id="a1757-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="a1757-1711">diners club</span></span> 
- <span data-ttu-id="a1757-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="a1757-1712">dinersclub</span></span> 
- <span data-ttu-id="a1757-1713">tect</span><span class="sxs-lookup"><span data-stu-id="a1757-1713">discover</span></span> 
- <span data-ttu-id="a1757-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="a1757-1714">discover card</span></span> 
- <span data-ttu-id="a1757-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1715">discover cards</span></span> 
- <span data-ttu-id="a1757-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="a1757-1716">discovercard</span></span> 
- <span data-ttu-id="a1757-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="a1757-1717">discovercards</span></span> 
- <span data-ttu-id="a1757-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="a1757-1718">débito automático</span></span>
- <span data-ttu-id="a1757-1719">edc</span><span class="sxs-lookup"><span data-stu-id="a1757-1719">edc</span></span> 
- <span data-ttu-id="a1757-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="a1757-1720">eigentümername</span></span> 
- <span data-ttu-id="a1757-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="a1757-1721">european debit card</span></span> 
- <span data-ttu-id="a1757-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="a1757-1722">hoofdkaart</span></span> 
- <span data-ttu-id="a1757-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="a1757-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="a1757-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="a1757-1724">in viaggio</span></span> 
- <span data-ttu-id="a1757-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="a1757-1725">japanese card bureau</span></span> 
- <span data-ttu-id="a1757-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="a1757-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="a1757-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="a1757-1727">jcb</span></span> 
- <span data-ttu-id="a1757-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="a1757-1728">kaart</span></span> 
- <span data-ttu-id="a1757-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="a1757-1729">kaart num</span></span> 
- <span data-ttu-id="a1757-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="a1757-1730">kaartaantal</span></span> 
- <span data-ttu-id="a1757-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="a1757-1731">kaartaantallen</span></span> 
- <span data-ttu-id="a1757-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="a1757-1732">kaarthouder</span></span> 
- <span data-ttu-id="a1757-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="a1757-1733">kaarthouders</span></span> 
- <span data-ttu-id="a1757-1734">karte</span><span class="sxs-lookup"><span data-stu-id="a1757-1734">karte</span></span>  
- <span data-ttu-id="a1757-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="a1757-1735">karteninhaber</span></span> 
- <span data-ttu-id="a1757-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a1757-1736">karteninhabers</span></span>
- <span data-ttu-id="a1757-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="a1757-1737">kartennr</span></span> 
- <span data-ttu-id="a1757-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1738">kartennummer</span></span> 
- <span data-ttu-id="a1757-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="a1757-1739">kreditkarte</span></span> 
- <span data-ttu-id="a1757-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="a1757-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="a1757-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="a1757-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="a1757-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="a1757-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="a1757-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="a1757-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="a1757-1745">Maestro</span><span class="sxs-lookup"><span data-stu-id="a1757-1745">maestro</span></span> 
- <span data-ttu-id="a1757-1746">master card</span><span class="sxs-lookup"><span data-stu-id="a1757-1746">master card</span></span> 
- <span data-ttu-id="a1757-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="a1757-1747">master cards</span></span> 
- <span data-ttu-id="a1757-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="a1757-1748">mastercard</span></span> 
- <span data-ttu-id="a1757-1749">MasterCards</span><span class="sxs-lookup"><span data-stu-id="a1757-1749">mastercards</span></span> 
- <span data-ttu-id="a1757-1750">MC</span><span class="sxs-lookup"><span data-stu-id="a1757-1750">mc</span></span> 
- <span data-ttu-id="a1757-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="a1757-1751">mister cash</span></span> 
- <span data-ttu-id="a1757-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1752">n carta</span></span> 
- <span data-ttu-id="a1757-1753">carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1753">carta</span></span> 
- <span data-ttu-id="a1757-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1754">no de tarjeta</span></span> 
- <span data-ttu-id="a1757-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1755">no do cartao</span></span> 
- <span data-ttu-id="a1757-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1756">no do cartão</span></span> 
- <span data-ttu-id="a1757-1757">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-1757">no.</span></span> <span data-ttu-id="a1757-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1758">de tarjeta</span></span> 
- <span data-ttu-id="a1757-1759">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-1759">no.</span></span> <span data-ttu-id="a1757-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1760">do cartao</span></span> 
- <span data-ttu-id="a1757-1761">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-1761">no.</span></span> <span data-ttu-id="a1757-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1762">do cartão</span></span> 
- <span data-ttu-id="a1757-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1763">nr carta</span></span> 
- <span data-ttu-id="a1757-1764">nr.</span><span class="sxs-lookup"><span data-stu-id="a1757-1764">nr.</span></span> <span data-ttu-id="a1757-1765">carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1765">carta</span></span> 
- <span data-ttu-id="a1757-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="a1757-1766">numeri di scheda</span></span> 
- <span data-ttu-id="a1757-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1767">numero carta</span></span> 
- <span data-ttu-id="a1757-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1768">numero de cartao</span></span> 
- <span data-ttu-id="a1757-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="a1757-1769">numero de carte</span></span> 
- <span data-ttu-id="a1757-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1770">numero de cartão</span></span> 
- <span data-ttu-id="a1757-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1771">numero de tarjeta</span></span>
- <span data-ttu-id="a1757-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1772">numero della carta</span></span> 
- <span data-ttu-id="a1757-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1773">numero di carta</span></span> 
- <span data-ttu-id="a1757-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="a1757-1774">numero di scheda</span></span> 
- <span data-ttu-id="a1757-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1775">numero do cartao</span></span> 
- <span data-ttu-id="a1757-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1776">numero do cartão</span></span> 
- <span data-ttu-id="a1757-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="a1757-1777">numéro de carte</span></span> 
- <span data-ttu-id="a1757-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="a1757-1778">nº carta</span></span> 
- <span data-ttu-id="a1757-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="a1757-1779">nº de carte</span></span> 
- <span data-ttu-id="a1757-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="a1757-1780">nº de la carte</span></span> 
- <span data-ttu-id="a1757-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="a1757-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1782">nº do cartao</span></span> 
- <span data-ttu-id="a1757-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1783">nº do cartão</span></span> 
- <span data-ttu-id="a1757-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="a1757-1784">nº.</span></span> <span data-ttu-id="a1757-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1785">do cartão</span></span> 
- <span data-ttu-id="a1757-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1786">número de cartao</span></span> 
- <span data-ttu-id="a1757-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="a1757-1787">número de cartão</span></span> 
- <span data-ttu-id="a1757-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a1757-1788">número de tarjeta</span></span> 
- <span data-ttu-id="a1757-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="a1757-1789">número do cartao</span></span> 
- <span data-ttu-id="a1757-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="a1757-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="a1757-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="a1757-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a1757-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="a1757-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a1757-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="a1757-1793">scheda della banca</span></span> 
- <span data-ttu-id="a1757-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="a1757-1794">scheda di controllo</span></span> 
- <span data-ttu-id="a1757-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1795">scheda di debito</span></span> 
- <span data-ttu-id="a1757-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="a1757-1796">scheda matrice</span></span> 
- <span data-ttu-id="a1757-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="a1757-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="a1757-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="a1757-1798">schede di controllo</span></span> 
- <span data-ttu-id="a1757-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1799">schede di debito</span></span> 
- <span data-ttu-id="a1757-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="a1757-1800">schede matrici</span></span> 
- <span data-ttu-id="a1757-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="a1757-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="a1757-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="a1757-1802">scoprono le schede</span></span> 
- <span data-ttu-id="a1757-1803">individual</span><span class="sxs-lookup"><span data-stu-id="a1757-1803">solo</span></span> 
- <span data-ttu-id="a1757-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="a1757-1804">supporti di scheda</span></span> 
- <span data-ttu-id="a1757-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="a1757-1805">supporto di scheda</span></span> 
- <span data-ttu-id="a1757-1806">Vá</span><span class="sxs-lookup"><span data-stu-id="a1757-1806">switch</span></span> 
- <span data-ttu-id="a1757-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="a1757-1807">tarjeta atm</span></span> 
- <span data-ttu-id="a1757-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1808">tarjeta credito</span></span> 
- <span data-ttu-id="a1757-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="a1757-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="a1757-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="a1757-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="a1757-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="a1757-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="a1757-1812">tarjeta debito</span></span> 
- <span data-ttu-id="a1757-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="a1757-1813">tarjeta no</span></span>
- <span data-ttu-id="a1757-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="a1757-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="a1757-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="a1757-1815">tipo della scheda</span></span> 
- <span data-ttu-id="a1757-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="a1757-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="a1757-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="a1757-1817">scheda</span></span> 
- <span data-ttu-id="a1757-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="a1757-1818">v pay</span></span> 
- <span data-ttu-id="a1757-1819">v-Pay</span><span class="sxs-lookup"><span data-stu-id="a1757-1819">v-pay</span></span> 
- <span data-ttu-id="a1757-1820">cartões</span><span class="sxs-lookup"><span data-stu-id="a1757-1820">visa</span></span> 
- <span data-ttu-id="a1757-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="a1757-1821">visa plus</span></span> 
- <span data-ttu-id="a1757-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="a1757-1822">visa electron</span></span> 
- <span data-ttu-id="a1757-1823">previsto</span><span class="sxs-lookup"><span data-stu-id="a1757-1823">visto</span></span> 
- <span data-ttu-id="a1757-1824">visum</span><span class="sxs-lookup"><span data-stu-id="a1757-1824">visum</span></span> 
- <span data-ttu-id="a1757-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="a1757-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="a1757-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a1757-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="a1757-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="a1757-1827">card identification number</span></span>
- <span data-ttu-id="a1757-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="a1757-1828">card verification</span></span> 
- <span data-ttu-id="a1757-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="a1757-1829">cardi la verifica</span></span> 
- <span data-ttu-id="a1757-1830">CID</span><span class="sxs-lookup"><span data-stu-id="a1757-1830">cid</span></span> 
- <span data-ttu-id="a1757-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="a1757-1831">cod seg</span></span> 
- <span data-ttu-id="a1757-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1832">cod seguranca</span></span> 
- <span data-ttu-id="a1757-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1833">cod segurança</span></span> 
- <span data-ttu-id="a1757-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1757-1834">cod sicurezza</span></span> 
- <span data-ttu-id="a1757-1835">COD.</span><span class="sxs-lookup"><span data-stu-id="a1757-1835">cod.</span></span> <span data-ttu-id="a1757-1836">seg</span><span class="sxs-lookup"><span data-stu-id="a1757-1836">seg</span></span> 
- <span data-ttu-id="a1757-1837">COD.</span><span class="sxs-lookup"><span data-stu-id="a1757-1837">cod.</span></span> <span data-ttu-id="a1757-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1838">seguranca</span></span> 
- <span data-ttu-id="a1757-1839">COD.</span><span class="sxs-lookup"><span data-stu-id="a1757-1839">cod.</span></span> <span data-ttu-id="a1757-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1840">segurança</span></span> 
- <span data-ttu-id="a1757-1841">COD.</span><span class="sxs-lookup"><span data-stu-id="a1757-1841">cod.</span></span> <span data-ttu-id="a1757-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1757-1842">sicurezza</span></span> 
- <span data-ttu-id="a1757-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1757-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="a1757-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="a1757-1844">codice di verifica</span></span> 
- <span data-ttu-id="a1757-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="a1757-1845">codigo</span></span> 
- <span data-ttu-id="a1757-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="a1757-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1847">codigo de segurança</span></span> 
- <span data-ttu-id="a1757-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="a1757-1848">crittogramma</span></span> 
- <span data-ttu-id="a1757-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="a1757-1849">cryptogram</span></span> 
- <span data-ttu-id="a1757-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="a1757-1850">cryptogramme</span></span> 
- <span data-ttu-id="a1757-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="a1757-1851">cv2</span></span> 
- <span data-ttu-id="a1757-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="a1757-1852">cvc</span></span> 
- <span data-ttu-id="a1757-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="a1757-1853">cvc2</span></span> 
- <span data-ttu-id="a1757-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="a1757-1854">cvn</span></span> 
- <span data-ttu-id="a1757-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="a1757-1855">cvv</span></span> 
- <span data-ttu-id="a1757-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="a1757-1856">cvv2</span></span> 
- <span data-ttu-id="a1757-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1857">cód seguranca</span></span> 
- <span data-ttu-id="a1757-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1858">cód segurança</span></span> 
- <span data-ttu-id="a1757-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="a1757-1859">cód.</span></span> <span data-ttu-id="a1757-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1860">seguranca</span></span> 
- <span data-ttu-id="a1757-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="a1757-1861">cód.</span></span> <span data-ttu-id="a1757-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1862">segurança</span></span> 
- <span data-ttu-id="a1757-1863">CFOP</span><span class="sxs-lookup"><span data-stu-id="a1757-1863">código</span></span> 
- <span data-ttu-id="a1757-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="a1757-1864">código de seguranca</span></span> 
- <span data-ttu-id="a1757-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="a1757-1865">código de segurança</span></span> 
- <span data-ttu-id="a1757-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="a1757-1866">de kaart controle</span></span> 
- <span data-ttu-id="a1757-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="a1757-1867">geeft nr uit</span></span> 
- <span data-ttu-id="a1757-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="a1757-1868">issue no</span></span> 
- <span data-ttu-id="a1757-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="a1757-1869">issue number</span></span> 
- <span data-ttu-id="a1757-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="a1757-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="a1757-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="a1757-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="a1757-1873">kwestieaantal</span></span> 
- <span data-ttu-id="a1757-1874">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-1874">no.</span></span> <span data-ttu-id="a1757-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="a1757-1875">dell'edizione</span></span> 
- <span data-ttu-id="a1757-1876">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-1876">no.</span></span> <span data-ttu-id="a1757-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1757-1877">di sicurezza</span></span> 
- <span data-ttu-id="a1757-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="a1757-1878">numero de securite</span></span> 
- <span data-ttu-id="a1757-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="a1757-1879">numero de verificacao</span></span> 
- <span data-ttu-id="a1757-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="a1757-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="a1757-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="a1757-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="a1757-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="a1757-1882">scheda</span></span> 
- <span data-ttu-id="a1757-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1757-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="a1757-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="a1757-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="a1757-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="a1757-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="a1757-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a1757-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="a1757-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1887">número de verificação</span></span> 
- <span data-ttu-id="a1757-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="a1757-1888">perno il blocco</span></span> 
- <span data-ttu-id="a1757-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="a1757-1889">pin block</span></span> 
- <span data-ttu-id="a1757-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="a1757-1890">prufziffer</span></span> 
- <span data-ttu-id="a1757-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="a1757-1891">prüfziffer</span></span> 
- <span data-ttu-id="a1757-1892">security code</span><span class="sxs-lookup"><span data-stu-id="a1757-1892">security code</span></span> 
- <span data-ttu-id="a1757-1893">security no</span><span class="sxs-lookup"><span data-stu-id="a1757-1893">security no</span></span> 
- <span data-ttu-id="a1757-1894">security number</span><span class="sxs-lookup"><span data-stu-id="a1757-1894">security number</span></span> 
- <span data-ttu-id="a1757-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="a1757-1895">sicherheits kode</span></span> 
- <span data-ttu-id="a1757-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="a1757-1896">sicherheitscode</span></span> 
- <span data-ttu-id="a1757-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="a1757-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="a1757-1898">speldblok</span></span> 
- <span data-ttu-id="a1757-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="a1757-1899">veiligheid nr</span></span> 
- <span data-ttu-id="a1757-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="a1757-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="a1757-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="a1757-1901">veiligheidscode</span></span> 
- <span data-ttu-id="a1757-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="a1757-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="a1757-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="a1757-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a1757-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="a1757-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="a1757-1905">ablauf</span></span> 
- <span data-ttu-id="a1757-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="a1757-1906">data de expiracao</span></span> 
- <span data-ttu-id="a1757-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="a1757-1907">data de expiração</span></span> 
- <span data-ttu-id="a1757-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="a1757-1908">data del exp</span></span> 
- <span data-ttu-id="a1757-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="a1757-1909">data di exp</span></span> 
- <span data-ttu-id="a1757-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="a1757-1910">data di scadenza</span></span> 
- <span data-ttu-id="a1757-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="a1757-1911">data em que expira</span></span> 
- <span data-ttu-id="a1757-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="a1757-1912">data scad</span></span> 
- <span data-ttu-id="a1757-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="a1757-1913">data scadenza</span></span> 
- <span data-ttu-id="a1757-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="a1757-1914">date de validité</span></span> 
- <span data-ttu-id="a1757-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="a1757-1915">datum afloop</span></span> 
- <span data-ttu-id="a1757-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="a1757-1916">datum van exp</span></span> 
- <span data-ttu-id="a1757-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="a1757-1917">de afloop</span></span> 
- <span data-ttu-id="a1757-1918">espira</span><span class="sxs-lookup"><span data-stu-id="a1757-1918">espira</span></span> 
- <span data-ttu-id="a1757-1919">espira</span><span class="sxs-lookup"><span data-stu-id="a1757-1919">espira</span></span> 
- <span data-ttu-id="a1757-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="a1757-1920">exp date</span></span> 
- <span data-ttu-id="a1757-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="a1757-1921">exp datum</span></span> 
- <span data-ttu-id="a1757-1922">validade</span><span class="sxs-lookup"><span data-stu-id="a1757-1922">expiration</span></span> 
- <span data-ttu-id="a1757-1923">expirar</span><span class="sxs-lookup"><span data-stu-id="a1757-1923">expire</span></span> 
- <span data-ttu-id="a1757-1924">expira</span><span class="sxs-lookup"><span data-stu-id="a1757-1924">expires</span></span> 
- <span data-ttu-id="a1757-1925">expiração</span><span class="sxs-lookup"><span data-stu-id="a1757-1925">expiry</span></span> 
- <span data-ttu-id="a1757-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="a1757-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="a1757-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="a1757-1927">fecha de venc</span></span> 
- <span data-ttu-id="a1757-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="a1757-1928">gultig bis</span></span> 
- <span data-ttu-id="a1757-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a1757-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="a1757-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="a1757-1930">gültig bis</span></span> 
- <span data-ttu-id="a1757-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a1757-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="a1757-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="a1757-1932">la scadenza</span></span> 
- <span data-ttu-id="a1757-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="a1757-1933">scadenza</span></span> 
- <span data-ttu-id="a1757-1934">valable</span><span class="sxs-lookup"><span data-stu-id="a1757-1934">valable</span></span> 
- <span data-ttu-id="a1757-1935">validade</span><span class="sxs-lookup"><span data-stu-id="a1757-1935">validade</span></span> 
- <span data-ttu-id="a1757-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="a1757-1936">valido hasta</span></span> 
- <span data-ttu-id="a1757-1937">coragem</span><span class="sxs-lookup"><span data-stu-id="a1757-1937">valor</span></span> 
- <span data-ttu-id="a1757-1938">venc</span><span class="sxs-lookup"><span data-stu-id="a1757-1938">venc</span></span> 
- <span data-ttu-id="a1757-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="a1757-1939">vencimento</span></span> 
- <span data-ttu-id="a1757-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="a1757-1940">vencimiento</span></span> 
- <span data-ttu-id="a1757-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="a1757-1941">verloopt</span></span> 
- <span data-ttu-id="a1757-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="a1757-1942">vervaldag</span></span> 
- <span data-ttu-id="a1757-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="a1757-1943">vervaldatum</span></span> 
- <span data-ttu-id="a1757-1944">vto</span><span class="sxs-lookup"><span data-stu-id="a1757-1944">vto</span></span> 
- <span data-ttu-id="a1757-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="a1757-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="a1757-1946">Número da carteira de motorista da UE</span><span class="sxs-lookup"><span data-stu-id="a1757-1946">EU Driver's License Number</span></span>

<span data-ttu-id="a1757-1947">Para saber mais, confira o [tipo de informação confidencial do número da carteira de motorista da UE](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="a1757-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="a1757-1948">Número de identificação nacional da UE</span><span class="sxs-lookup"><span data-stu-id="a1757-1948">EU National Identification Number</span></span>

<span data-ttu-id="a1757-1949">Para saber mais, confira [tipo de informação confidencial do número de identificação nacional da UE](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="a1757-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="a1757-1950">Número do Passport da UE</span><span class="sxs-lookup"><span data-stu-id="a1757-1950">EU Passport Number</span></span>

<span data-ttu-id="a1757-1951">Para saber mais, veja [tipo de informações confidenciais do número do Passport da UE](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="a1757-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="a1757-1952">Número de seguro social da UE ou ID equivalente</span><span class="sxs-lookup"><span data-stu-id="a1757-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="a1757-1953">Para saber mais, confira [número de seguridade social da UE ou tipo de informação confidencial de ID equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="a1757-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="a1757-1954">Número de identificação do imposto da UE</span><span class="sxs-lookup"><span data-stu-id="a1757-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="a1757-1955">Para saber mais, confira [número de identificação de imposto da UE tipo de informação confidencial](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="a1757-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="a1757-1956">ID nacional da Finlândia</span><span class="sxs-lookup"><span data-stu-id="a1757-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1957">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1957">Format</span></span>

<span data-ttu-id="a1757-1958">Seis dígitos mais um caractere indicando um século mais três dígitos mais um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1959">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1959">Pattern</span></span>

<span data-ttu-id="a1757-1960">O padrão deve incluir todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="a1757-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a1757-1961">Seis dígitos no formato DDMMAA que é uma data de nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="a1757-1962">Marcador do século (qualquer '-', '+' ou 'a')</span><span class="sxs-lookup"><span data-stu-id="a1757-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="a1757-1963">Número de identificação pessoal de três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="a1757-1964">Um dígito ou letra (não diferencia maiúscula de minúscula), que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1965">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1965">Checksum</span></span>

<span data-ttu-id="a1757-1966">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1967">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1967">Definition</span></span>

<span data-ttu-id="a1757-1968">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1969">A função Func_finnish_national_id localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1970">Uma palavra-chave de Keyword_finnish_national_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="a1757-1971">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-1972">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1972">Keywords</span></span>

- <span data-ttu-id="a1757-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="a1757-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="a1757-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="a1757-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="a1757-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="a1757-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="a1757-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="a1757-1976">Personbeteckning</span></span>
- <span data-ttu-id="a1757-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="a1757-1978">Número de Passaporte da Finlândia</span><span class="sxs-lookup"><span data-stu-id="a1757-1978">Finland Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1979">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1979">Format</span></span>
<span data-ttu-id="a1757-1980">Uma combinação de nove letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1980">Combination of nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1981">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1981">Pattern</span></span>
<span data-ttu-id="a1757-1982">Combinação de nove letras e dígitos: duas letras (não diferencia maiúsculas de minúsculas) sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1982">Combination of nine letters and digits: Two letters (not case sensitive) Seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1983">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1983">Checksum</span></span>
<span data-ttu-id="a1757-1984">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-1984">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-1985">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-1985">Definition</span></span>
<span data-ttu-id="a1757-1986">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-1986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-1987">A expressão regular Regex_finland_passport_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-1987">The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-1988">Uma palavra-chave de Keyword_finland_passport_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-1988">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
```xml
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="a1757-1989">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-1989">Keywords</span></span>
- <span data-ttu-id="a1757-1990">Keyword_finland_passport_number</span><span class="sxs-lookup"><span data-stu-id="a1757-1990">Keyword_finland_passport_number</span></span>
- <span data-ttu-id="a1757-1991">Passaport</span><span class="sxs-lookup"><span data-stu-id="a1757-1991">Passport</span></span>
- <span data-ttu-id="a1757-1992">Passi</span><span class="sxs-lookup"><span data-stu-id="a1757-1992">Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="a1757-1993">Número de carteira de motorista da França</span><span class="sxs-lookup"><span data-stu-id="a1757-1993">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-1994">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-1994">Format</span></span>

<span data-ttu-id="a1757-1995">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-1995">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-1996">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-1996">Pattern</span></span>

<span data-ttu-id="a1757-1997">12 dígitos com a validação para descontar padrões similares, como números de telefone em francês</span><span class="sxs-lookup"><span data-stu-id="a1757-1997">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-1998">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-1998">Checksum</span></span>

<span data-ttu-id="a1757-1999">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-1999">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2000">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2000">Definition</span></span>

<span data-ttu-id="a1757-2001">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2001">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2002">A função Func_french_drivers_license localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2002">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2003">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-2003">At least one of the following is true:</span></span>
- <span data-ttu-id="a1757-2004">Uma palavra-chave de Keyword_french_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2004">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="a1757-2005">A função Func_eu_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-2005">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2006">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2006">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="a1757-2007">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a1757-2007">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="a1757-2008">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a1757-2008">drivers licence</span></span>
- <span data-ttu-id="a1757-2009">drivers license</span><span class="sxs-lookup"><span data-stu-id="a1757-2009">drivers license</span></span>
- <span data-ttu-id="a1757-2010">driving licence</span><span class="sxs-lookup"><span data-stu-id="a1757-2010">driving licence</span></span>
- <span data-ttu-id="a1757-2011">driving licence</span><span class="sxs-lookup"><span data-stu-id="a1757-2011">driving license</span></span>
- <span data-ttu-id="a1757-2012">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="a1757-2012">permis de conduire</span></span>
- <span data-ttu-id="a1757-2013">licence number</span><span class="sxs-lookup"><span data-stu-id="a1757-2013">licence number</span></span>
- <span data-ttu-id="a1757-2014">license number</span><span class="sxs-lookup"><span data-stu-id="a1757-2014">license number</span></span>
- <span data-ttu-id="a1757-2015">licence numbers</span><span class="sxs-lookup"><span data-stu-id="a1757-2015">licence numbers</span></span>
- <span data-ttu-id="a1757-2016">license numbers</span><span class="sxs-lookup"><span data-stu-id="a1757-2016">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="a1757-2017">Cartão de identificação nacional da França (CNI)</span><span class="sxs-lookup"><span data-stu-id="a1757-2017">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2018">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2018">Format</span></span>

<span data-ttu-id="a1757-2019">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2019">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2020">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2020">Pattern</span></span>

<span data-ttu-id="a1757-2021">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2021">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2022">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2022">Checksum</span></span>

<span data-ttu-id="a1757-2023">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2023">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2024">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2024">Definition</span></span>

<span data-ttu-id="a1757-2025">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2025">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2026">A expressão regular Regex_france_cni localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2026">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2027">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2027">Keywords</span></span>

<span data-ttu-id="a1757-2028">None</span><span class="sxs-lookup"><span data-stu-id="a1757-2028">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="a1757-2029">Número de passaporte da França</span><span class="sxs-lookup"><span data-stu-id="a1757-2029">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2030">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2030">Format</span></span>

<span data-ttu-id="a1757-2031">Nove letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2031">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2032">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2032">Pattern</span></span>

<span data-ttu-id="a1757-2033">Nove letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-2033">Nine digits and letters:</span></span>
- <span data-ttu-id="a1757-2034">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2034">Two digits</span></span> 
- <span data-ttu-id="a1757-2035">Duas letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-2035">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-2036">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2036">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2037">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2037">Checksum</span></span>

<span data-ttu-id="a1757-2038">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2038">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2039">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2039">Definition</span></span>

<span data-ttu-id="a1757-2040">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2040">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2041">A função Func_fr_passport localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2041">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2042">Uma palavra-chave de Keyword_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2042">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2043">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2043">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a1757-2044">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a1757-2044">Keyword_passport</span></span>

- <span data-ttu-id="a1757-2045">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2045">Passport Number</span></span>
- <span data-ttu-id="a1757-2046">Passport No</span><span class="sxs-lookup"><span data-stu-id="a1757-2046">Passport No</span></span>
- <span data-ttu-id="a1757-2047">Passport #</span><span class="sxs-lookup"><span data-stu-id="a1757-2047">Passport #</span></span>
- <span data-ttu-id="a1757-2048">Passaport #</span><span class="sxs-lookup"><span data-stu-id="a1757-2048">Passport#</span></span>
- <span data-ttu-id="a1757-2049">Passportid</span><span class="sxs-lookup"><span data-stu-id="a1757-2049">PassportID</span></span>
- <span data-ttu-id="a1757-2050">Passportno</span><span class="sxs-lookup"><span data-stu-id="a1757-2050">Passportno</span></span>
- <span data-ttu-id="a1757-2051">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-2051">passportnumber</span></span>
- <span data-ttu-id="a1757-2052">パスポート</span><span class="sxs-lookup"><span data-stu-id="a1757-2052">パスポート</span></span>
- <span data-ttu-id="a1757-2053">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2053">パスポート番号</span></span>
- <span data-ttu-id="a1757-2054">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a1757-2054">パスポートのNum</span></span>
- <span data-ttu-id="a1757-2055">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="a1757-2055">パスポート ＃</span></span> 
- <span data-ttu-id="a1757-2056">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a1757-2056">Numéro de passeport</span></span>
- <span data-ttu-id="a1757-2057">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a1757-2057">Passeport n °</span></span>
- <span data-ttu-id="a1757-2058">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a1757-2058">Passeport Non</span></span>
- <span data-ttu-id="a1757-2059">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-2059">Passeport #</span></span>
- <span data-ttu-id="a1757-2060">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-2060">Passeport#</span></span>
- <span data-ttu-id="a1757-2061">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a1757-2061">PasseportNon</span></span>
- <span data-ttu-id="a1757-2062">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a1757-2062">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="a1757-2063">Número de seguridade social da França (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a1757-2063">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2064">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2064">Format</span></span>

<span data-ttu-id="a1757-2065">15 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2065">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2066">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2066">Pattern</span></span>

<span data-ttu-id="a1757-2067">Deve corresponder a um dos dois padrões:</span><span class="sxs-lookup"><span data-stu-id="a1757-2067">Must match one of two patterns:</span></span>
- <span data-ttu-id="a1757-2068">13 dígitos seguidos de um espaço seguido de dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2068">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="a1757-2069">ou</span><span class="sxs-lookup"><span data-stu-id="a1757-2069">or</span></span>
- <span data-ttu-id="a1757-2070">15 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-2070">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2071">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2071">Checksum</span></span>

<span data-ttu-id="a1757-2072">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2072">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2073">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2073">Definition</span></span>

<span data-ttu-id="a1757-2074">Uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2074">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2075">A função Func_french_insee ou Func_fr_insee localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2075">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2076">Uma palavra-chave de Keyword_fr_insee for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2076">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a1757-2077">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2077">The checksum passes.</span></span>

<span data-ttu-id="a1757-2078">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2078">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2079">A função Func_french_insee ou Func_fr_insee localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2079">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2080">Nenhuma palavra-chave de Keyword_fr_insee for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2080">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a1757-2081">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2081">The checksum passes.</span></span>

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2082">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2082">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="a1757-2083">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="a1757-2083">Keyword_fr_insee</span></span>

- <span data-ttu-id="a1757-2084">INSEE</span><span class="sxs-lookup"><span data-stu-id="a1757-2084">insee</span></span>
- <span data-ttu-id="a1757-2085">securité sociale</span><span class="sxs-lookup"><span data-stu-id="a1757-2085">securité sociale</span></span>
- <span data-ttu-id="a1757-2086">securite sociale</span><span class="sxs-lookup"><span data-stu-id="a1757-2086">securite sociale</span></span>
- <span data-ttu-id="a1757-2087">national id</span><span class="sxs-lookup"><span data-stu-id="a1757-2087">national id</span></span>
- <span data-ttu-id="a1757-2088">national identification</span><span class="sxs-lookup"><span data-stu-id="a1757-2088">national identification</span></span>
- <span data-ttu-id="a1757-2089">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="a1757-2089">numéro d'identité</span></span>
- <span data-ttu-id="a1757-2090">no d'identité</span><span class="sxs-lookup"><span data-stu-id="a1757-2090">no d'identité</span></span>
- <span data-ttu-id="a1757-2091">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-2091">no.</span></span> <span data-ttu-id="a1757-2092">d'identité</span><span class="sxs-lookup"><span data-stu-id="a1757-2092">d'identité</span></span>
- <span data-ttu-id="a1757-2093">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="a1757-2093">numero d'identite</span></span>
- <span data-ttu-id="a1757-2094">no d'identite</span><span class="sxs-lookup"><span data-stu-id="a1757-2094">no d'identite</span></span>
- <span data-ttu-id="a1757-2095">Não.</span><span class="sxs-lookup"><span data-stu-id="a1757-2095">no.</span></span> <span data-ttu-id="a1757-2096">d'identite</span><span class="sxs-lookup"><span data-stu-id="a1757-2096">d'identite</span></span>
- <span data-ttu-id="a1757-2097">social security number</span><span class="sxs-lookup"><span data-stu-id="a1757-2097">social security number</span></span>
- <span data-ttu-id="a1757-2098">social security code</span><span class="sxs-lookup"><span data-stu-id="a1757-2098">social security code</span></span>
- <span data-ttu-id="a1757-2099">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a1757-2099">social insurance number</span></span>
- <span data-ttu-id="a1757-2100">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="a1757-2100">le numéro d'identification nationale</span></span>
- <span data-ttu-id="a1757-2101">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="a1757-2101">d'identité nationale</span></span>
- <span data-ttu-id="a1757-2102">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a1757-2102">numéro de sécurité sociale</span></span>
- <span data-ttu-id="a1757-2103">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a1757-2103">le code de la sécurité sociale</span></span>
- <span data-ttu-id="a1757-2104">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="a1757-2104">numéro d'assurance sociale</span></span>
- <span data-ttu-id="a1757-2105">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="a1757-2105">numéro de sécu</span></span>
- <span data-ttu-id="a1757-2106">code sécu</span><span class="sxs-lookup"><span data-stu-id="a1757-2106">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="a1757-2107">Número de carteira de motorista da Alemanha</span><span class="sxs-lookup"><span data-stu-id="a1757-2107">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2108">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2108">Format</span></span>

<span data-ttu-id="a1757-2109">Combinação de 11 dígitos e letras</span><span class="sxs-lookup"><span data-stu-id="a1757-2109">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2110">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2110">Pattern</span></span>

<span data-ttu-id="a1757-2111">11 dígitos e letras (não diferenciam maiúsculas de minúsculas):</span><span class="sxs-lookup"><span data-stu-id="a1757-2111">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="a1757-2112">Um dígito ou letra</span><span class="sxs-lookup"><span data-stu-id="a1757-2112">A digit or letter</span></span> 
- <span data-ttu-id="a1757-2113">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2113">Two digits</span></span> 
- <span data-ttu-id="a1757-2114">Seis dígitos ou letras</span><span class="sxs-lookup"><span data-stu-id="a1757-2114">Six digits or letters</span></span> 
- <span data-ttu-id="a1757-2115">Um dígito</span><span class="sxs-lookup"><span data-stu-id="a1757-2115">A digit</span></span> 
- <span data-ttu-id="a1757-2116">Um dígito ou letra</span><span class="sxs-lookup"><span data-stu-id="a1757-2116">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2117">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2117">Checksum</span></span>

<span data-ttu-id="a1757-2118">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2118">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2119">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2119">Definition</span></span>

<span data-ttu-id="a1757-2120">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2120">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2121">A função Func_german_drivers_license localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2121">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2122">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-2122">At least one of the following is true:</span></span>
    - <span data-ttu-id="a1757-2123">Uma palavra-chave de Keyword_german_drivers_license_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2123">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="a1757-2124">Uma palavra-chave de Keyword_german_drivers_license_collaborative for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2124">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="a1757-2125">Uma palavra-chave de Keyword_german_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2125">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="a1757-2126">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2126">The checksum passes.</span></span>

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2127">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2127">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="a1757-2128">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2128">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="a1757-2129">Führerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2129">Führerschein</span></span>
- <span data-ttu-id="a1757-2130">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2130">Fuhrerschein</span></span>
- <span data-ttu-id="a1757-2131">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2131">Fuehrerschein</span></span>
- <span data-ttu-id="a1757-2132">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2132">Führerscheinnummer</span></span>
- <span data-ttu-id="a1757-2133">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2133">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="a1757-2134">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2134">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="a1757-2135">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="a1757-2135">Führerschein-</span></span> 
- <span data-ttu-id="a1757-2136">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="a1757-2136">Fuhrerschein-</span></span> 
- <span data-ttu-id="a1757-2137">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="a1757-2137">Fuehrerschein-</span></span> 
- <span data-ttu-id="a1757-2138">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a1757-2138">FührerscheinnummerNr</span></span>
- <span data-ttu-id="a1757-2139">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a1757-2139">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="a1757-2140">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a1757-2140">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="a1757-2141">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2141">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="a1757-2142">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2142">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a1757-2143">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2143">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a1757-2144">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a1757-2144">Führerschein- Nr</span></span>
- <span data-ttu-id="a1757-2145">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a1757-2145">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="a1757-2146">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a1757-2146">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a1757-2147">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2147">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a1757-2148">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2148">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a1757-2149">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2149">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="a1757-2150">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a1757-2150">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="a1757-2151">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a1757-2151">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="a1757-2152">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a1757-2152">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="a1757-2153">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2153">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a1757-2154">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2154">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a1757-2155">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2155">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a1757-2156">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a1757-2156">Führerschein- Nr</span></span> 
- <span data-ttu-id="a1757-2157">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a1757-2157">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="a1757-2158">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="a1757-2158">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a1757-2159">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2159">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a1757-2160">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2160">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a1757-2161">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2161">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="a1757-2162">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a1757-2162">DL</span></span> 
- <span data-ttu-id="a1757-2163">DL</span><span class="sxs-lookup"><span data-stu-id="a1757-2163">DLS</span></span>
- <span data-ttu-id="a1757-2164">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-2164">Driv Lic</span></span> 
- <span data-ttu-id="a1757-2165">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="a1757-2165">Driv Licen</span></span> 
- <span data-ttu-id="a1757-2166">Driv License</span><span class="sxs-lookup"><span data-stu-id="a1757-2166">Driv License</span></span>
- <span data-ttu-id="a1757-2167">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-2167">Driv Licenses</span></span> 
- <span data-ttu-id="a1757-2168">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-2168">Driv Licence</span></span> 
- <span data-ttu-id="a1757-2169">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-2169">Driv Licences</span></span> 
- <span data-ttu-id="a1757-2170">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-2170">Driv Lic</span></span> 
- <span data-ttu-id="a1757-2171">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="a1757-2171">Driver Licen</span></span> 
- <span data-ttu-id="a1757-2172">Driver License</span><span class="sxs-lookup"><span data-stu-id="a1757-2172">Driver License</span></span> 
- <span data-ttu-id="a1757-2173">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-2173">Driver Licenses</span></span> 
- <span data-ttu-id="a1757-2174">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-2174">Driver Licence</span></span> 
- <span data-ttu-id="a1757-2175">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-2175">Driver Licences</span></span> 
- <span data-ttu-id="a1757-2176">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-2176">Drivers Lic</span></span> 
- <span data-ttu-id="a1757-2177">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="a1757-2177">Drivers Licen</span></span> 
- <span data-ttu-id="a1757-2178">Drivers License</span><span class="sxs-lookup"><span data-stu-id="a1757-2178">Drivers License</span></span> 
- <span data-ttu-id="a1757-2179">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-2179">Drivers Licenses</span></span> 
- <span data-ttu-id="a1757-2180">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-2180">Drivers Licence</span></span> 
- <span data-ttu-id="a1757-2181">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-2181">Drivers Licences</span></span> 
- <span data-ttu-id="a1757-2182">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-2182">Driver's Lic</span></span> 
- <span data-ttu-id="a1757-2183">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="a1757-2183">Driver's Licen</span></span> 
- <span data-ttu-id="a1757-2184">Driver's License</span><span class="sxs-lookup"><span data-stu-id="a1757-2184">Driver's License</span></span> 
- <span data-ttu-id="a1757-2185">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-2185">Driver's Licenses</span></span> 
- <span data-ttu-id="a1757-2186">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-2186">Driver's Licence</span></span> 
- <span data-ttu-id="a1757-2187">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-2187">Driver's Licences</span></span> 
- <span data-ttu-id="a1757-2188">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-2188">Driving Lic</span></span> 
- <span data-ttu-id="a1757-2189">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="a1757-2189">Driving Licen</span></span> 
- <span data-ttu-id="a1757-2190">Driving License</span><span class="sxs-lookup"><span data-stu-id="a1757-2190">Driving License</span></span> 
- <span data-ttu-id="a1757-2191">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-2191">Driving Licenses</span></span> 
- <span data-ttu-id="a1757-2192">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="a1757-2192">Driving Licence</span></span> 
- <span data-ttu-id="a1757-2193">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="a1757-2193">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="a1757-2194">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="a1757-2194">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="a1757-2195">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2195">Nr-Führerschein</span></span> 
- <span data-ttu-id="a1757-2196">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2196">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a1757-2197">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2197">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a1757-2198">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2198">No-Führerschein</span></span> 
- <span data-ttu-id="a1757-2199">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2199">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a1757-2200">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2200">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a1757-2201">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2201">N-Führerschein</span></span> 
- <span data-ttu-id="a1757-2202">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2202">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a1757-2203">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2203">N-Fuehrerschein</span></span>
- <span data-ttu-id="a1757-2204">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2204">Nr-Führerschein</span></span> 
- <span data-ttu-id="a1757-2205">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2205">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a1757-2206">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2206">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a1757-2207">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2207">No-Führerschein</span></span> 
- <span data-ttu-id="a1757-2208">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2208">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a1757-2209">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2209">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a1757-2210">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2210">N-Führerschein</span></span> 
- <span data-ttu-id="a1757-2211">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2211">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a1757-2212">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a1757-2212">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="a1757-2213">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a1757-2213">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="a1757-2214">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a1757-2214">ausstellungsdatum</span></span>
- <span data-ttu-id="a1757-2215">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a1757-2215">ausstellungsort</span></span>
- <span data-ttu-id="a1757-2216">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="a1757-2216">ausstellende behöde</span></span>
- <span data-ttu-id="a1757-2217">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="a1757-2217">ausstellende behorde</span></span>
- <span data-ttu-id="a1757-2218">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="a1757-2218">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="a1757-2219">Número de passaporte da Alemanha</span><span class="sxs-lookup"><span data-stu-id="a1757-2219">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2220">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2220">Format</span></span>

<span data-ttu-id="a1757-2221">10 dígitos ou letras</span><span class="sxs-lookup"><span data-stu-id="a1757-2221">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2222">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2222">Pattern</span></span>

<span data-ttu-id="a1757-2223">O padrão deve incluir todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="a1757-2223">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a1757-2224">Primeiro caractere é um dígito ou uma letra desse conjunto (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="a1757-2224">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="a1757-2225">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2225">Three digits</span></span> 
- <span data-ttu-id="a1757-2226">Cinco dígitos ou letras a partir desse conjunto (C, -H, J N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="a1757-2226">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="a1757-2227">Um dígito</span><span class="sxs-lookup"><span data-stu-id="a1757-2227">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2228">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2228">Checksum</span></span>

<span data-ttu-id="a1757-2229">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2229">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2230">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2230">Definition</span></span>

<span data-ttu-id="a1757-2231">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2231">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2232">A função Func_german_passport localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2232">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2233">Uma palavra-chave de qualquer uma das cinco listas de palavras-chave for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2233">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a1757-2234">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2234">The checksum passes.</span></span>

<span data-ttu-id="a1757-2235">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2236">A função Func_german_passport_data localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2236">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2237">Uma palavra-chave de qualquer uma das cinco listas de palavras-chave for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2237">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a1757-2238">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2238">The checksum passes.</span></span>

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2239">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2239">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="a1757-2240">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="a1757-2240">Keyword_german_passport</span></span>

- <span data-ttu-id="a1757-2241">reisepass</span><span class="sxs-lookup"><span data-stu-id="a1757-2241">reisepass</span></span>
- <span data-ttu-id="a1757-2242">reisepasse</span><span class="sxs-lookup"><span data-stu-id="a1757-2242">reisepasse</span></span>
- <span data-ttu-id="a1757-2243">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2243">reisepassnummer</span></span>
- <span data-ttu-id="a1757-2244">Passaport</span><span class="sxs-lookup"><span data-stu-id="a1757-2244">passport</span></span>
- <span data-ttu-id="a1757-2245">Passports</span><span class="sxs-lookup"><span data-stu-id="a1757-2245">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="a1757-2246">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="a1757-2246">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="a1757-2247">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="a1757-2247">geburtsdatum</span></span>
- <span data-ttu-id="a1757-2248">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a1757-2248">ausstellungsdatum</span></span>
- <span data-ttu-id="a1757-2249">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a1757-2249">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="a1757-2250">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2250">Keyword_german_passport_number</span></span>

<span data-ttu-id="a1757-2251">No-Reisepass NR-Reisepass</span><span class="sxs-lookup"><span data-stu-id="a1757-2251">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="a1757-2252">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="a1757-2252">Keyword_german_passport1</span></span>

<span data-ttu-id="a1757-2253">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="a1757-2253">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="a1757-2254">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="a1757-2254">Keyword_german_passport2</span></span>

<span data-ttu-id="a1757-2255">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="a1757-2255">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="a1757-2256">Número da carteira de identidade alemã</span><span class="sxs-lookup"><span data-stu-id="a1757-2256">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2257">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2257">Format</span></span>

<span data-ttu-id="a1757-2258">Desde 1 de novembro de 2010: nove letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2258">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="a1757-2259">De 1 de abril de 1987 até 31 de outubro de 2010:10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2259">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2260">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2260">Pattern</span></span>

<span data-ttu-id="a1757-2261">Desde 1º de novembro de 2010:</span><span class="sxs-lookup"><span data-stu-id="a1757-2261">Since 1 November 2010:</span></span>
- <span data-ttu-id="a1757-2262">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="a1757-2262">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-2263">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2263">Eight digits</span></span>

<span data-ttu-id="a1757-2264">De 1 de abril de 1987 até 31 de outubro de 2010:</span><span class="sxs-lookup"><span data-stu-id="a1757-2264">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="a1757-2265">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2265">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2266">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2266">Checksum</span></span>

<span data-ttu-id="a1757-2267">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2267">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2268">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2268">Definition</span></span>

<span data-ttu-id="a1757-2269">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2269">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2270">A expressão regular Regex_germany_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2270">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2271">Uma palavra-chave de Keyword_germany_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2271">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2272">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2272">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="a1757-2273">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="a1757-2273">Keyword_germany_id_card</span></span>

- <span data-ttu-id="a1757-2274">Cartão de Identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-2274">Identity Card</span></span>
- <span data-ttu-id="a1757-2275">ID</span><span class="sxs-lookup"><span data-stu-id="a1757-2275">ID</span></span>
- <span data-ttu-id="a1757-2276">Identificador</span><span class="sxs-lookup"><span data-stu-id="a1757-2276">Identification</span></span>
- <span data-ttu-id="a1757-2277">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a1757-2277">Personalausweis</span></span>
- <span data-ttu-id="a1757-2278">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2278">Identifizierungsnummer</span></span>
- <span data-ttu-id="a1757-2279">Ausweis</span><span class="sxs-lookup"><span data-stu-id="a1757-2279">Ausweis</span></span>
- <span data-ttu-id="a1757-2280">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a1757-2280">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="a1757-2281">Cartão de Identificação Nacional da Grécia</span><span class="sxs-lookup"><span data-stu-id="a1757-2281">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2282">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2282">Format</span></span>

<span data-ttu-id="a1757-2283">Combinação de 7 a 8 letras e números mais um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-2283">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2284">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2284">Pattern</span></span>

<span data-ttu-id="a1757-2285">Sete letras e números (formato antigo):</span><span class="sxs-lookup"><span data-stu-id="a1757-2285">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="a1757-2286">Uma letra (qualquer letra do alfabeto grego) </span><span class="sxs-lookup"><span data-stu-id="a1757-2286">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="a1757-2287">Um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-2287">A dash</span></span> 
- <span data-ttu-id="a1757-2288">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2288">Six digits</span></span>

<span data-ttu-id="a1757-2289">Oito letras e números (novo formato):</span><span class="sxs-lookup"><span data-stu-id="a1757-2289">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="a1757-2290">Duas letras cujos caracteres maiúsculos ocorre em alfabetos latino e grego (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="a1757-2290">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="a1757-2291">Um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-2291">A dash</span></span> 
- <span data-ttu-id="a1757-2292">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2292">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2293">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2293">Checksum</span></span>

<span data-ttu-id="a1757-2294">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2294">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2295">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2295">Definition</span></span>

<span data-ttu-id="a1757-2296">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2297">A expressão regular Regex_greece_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2297">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2298">Uma palavra-chave de Keyword_greece_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2298">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2299">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2299">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="a1757-2300">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="a1757-2300">Keyword_greece_id_card</span></span>

- <span data-ttu-id="a1757-2301">Cartão de identidade grego</span><span class="sxs-lookup"><span data-stu-id="a1757-2301">Greek identity Card</span></span>
- <span data-ttu-id="a1757-2302">Tautotita</span><span class="sxs-lookup"><span data-stu-id="a1757-2302">Tautotita</span></span>
- <span data-ttu-id="a1757-2303">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="a1757-2303">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="a1757-2304">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="a1757-2304">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="a1757-2305">Número do Cartão de Identidade de Hong Kong (HKID)</span><span class="sxs-lookup"><span data-stu-id="a1757-2305">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2306">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2306">Format</span></span>

<span data-ttu-id="a1757-2307">Combinação de 8 a 9 letras e números mais parênteses opcionais ao redor do caractere final</span><span class="sxs-lookup"><span data-stu-id="a1757-2307">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2308">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2308">Pattern</span></span>

<span data-ttu-id="a1757-2309">Combinação de 8 a 9 letras:</span><span class="sxs-lookup"><span data-stu-id="a1757-2309">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="a1757-2310">1 a 2 letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-2310">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-2311">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2311">Six digits</span></span> 
- <span data-ttu-id="a1757-2312">O caractere final (qualquer dígito ou a letra A), que é o dígito de verificação e é opcionalmente colocado entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="a1757-2312">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2313">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2313">Checksum</span></span>

<span data-ttu-id="a1757-2314">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2314">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2315">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2315">Definition</span></span>

<span data-ttu-id="a1757-2316">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2317">A função Func_hong_kong_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2317">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2318">Uma palavra-chave de Keyword_hong_kong_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2318">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="a1757-2319">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2319">The checksum passes.</span></span>

<span data-ttu-id="a1757-2320">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2320">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2321">A função Func_hong_kong_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2321">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2322">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2322">The checksum passes.</span></span>

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2323">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2323">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="a1757-2324">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="a1757-2324">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="a1757-2325">cartão de identidade de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="a1757-2325">hong kong identity card</span></span>
- <span data-ttu-id="a1757-2326">HKIDC</span><span class="sxs-lookup"><span data-stu-id="a1757-2326">HKIDC</span></span>
- <span data-ttu-id="a1757-2327">id card</span><span class="sxs-lookup"><span data-stu-id="a1757-2327">id card</span></span>
- <span data-ttu-id="a1757-2328">cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-2328">identity card</span></span>
- <span data-ttu-id="a1757-2329">cartão de identidade HK</span><span class="sxs-lookup"><span data-stu-id="a1757-2329">hk identity card</span></span>
- <span data-ttu-id="a1757-2330">ID de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="a1757-2330">hong kong id</span></span>
- <span data-ttu-id="a1757-2331">香港身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-2331">香港身份證</span></span>
- <span data-ttu-id="a1757-2332">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-2332">香港永久性居民身份證</span></span>
- <span data-ttu-id="a1757-2333">身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-2333">身份證</span></span>
- <span data-ttu-id="a1757-2334">身份証</span><span class="sxs-lookup"><span data-stu-id="a1757-2334">身份証</span></span>
- <span data-ttu-id="a1757-2335">身分證</span><span class="sxs-lookup"><span data-stu-id="a1757-2335">身分證</span></span>
- <span data-ttu-id="a1757-2336">身分証</span><span class="sxs-lookup"><span data-stu-id="a1757-2336">身分証</span></span>
- <span data-ttu-id="a1757-2337">香港身份証</span><span class="sxs-lookup"><span data-stu-id="a1757-2337">香港身份証</span></span>
- <span data-ttu-id="a1757-2338">香港身分證</span><span class="sxs-lookup"><span data-stu-id="a1757-2338">香港身分證</span></span>
- <span data-ttu-id="a1757-2339">香港身分証</span><span class="sxs-lookup"><span data-stu-id="a1757-2339">香港身分証</span></span>
- <span data-ttu-id="a1757-2340">香港身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-2340">香港身份證</span></span>
- <span data-ttu-id="a1757-2341">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-2341">香港居民身份證</span></span>
- <span data-ttu-id="a1757-2342">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="a1757-2342">香港居民身份証</span></span>
- <span data-ttu-id="a1757-2343">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="a1757-2343">香港居民身分證</span></span>
- <span data-ttu-id="a1757-2344">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="a1757-2344">香港居民身分証</span></span>
- <span data-ttu-id="a1757-2345">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a1757-2345">香港永久性居民身份証</span></span>
- <span data-ttu-id="a1757-2346">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a1757-2346">香港永久性居民身分證</span></span>
- <span data-ttu-id="a1757-2347">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a1757-2347">香港永久性居民身分証</span></span>
- <span data-ttu-id="a1757-2348">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-2348">香港永久性居民身份證</span></span>
- <span data-ttu-id="a1757-2349">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-2349">香港非永久性居民身份證</span></span>
- <span data-ttu-id="a1757-2350">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a1757-2350">香港非永久性居民身份証</span></span>
- <span data-ttu-id="a1757-2351">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a1757-2351">香港非永久性居民身分證</span></span>
- <span data-ttu-id="a1757-2352">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a1757-2352">香港非永久性居民身分証</span></span>
- <span data-ttu-id="a1757-2353">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-2353">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="a1757-2354">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a1757-2354">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="a1757-2355">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a1757-2355">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="a1757-2356">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a1757-2356">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="a1757-2357">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-2357">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="a1757-2358">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a1757-2358">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="a1757-2359">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a1757-2359">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="a1757-2360">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a1757-2360">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="a1757-2361">Número da Conta Permanente da Índia (PAN)</span><span class="sxs-lookup"><span data-stu-id="a1757-2361">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2362">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2362">Format</span></span>

<span data-ttu-id="a1757-2363">10 letras ou dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2363">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2364">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2364">Pattern</span></span>

<span data-ttu-id="a1757-2365">10 letras ou dígitos.</span><span class="sxs-lookup"><span data-stu-id="a1757-2365">10 letters or digits:</span></span>
- <span data-ttu-id="a1757-2366">Cinco letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-2366">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-2367">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2367">Four digits</span></span> 
- <span data-ttu-id="a1757-2368">Uma letra que é um dígito de verificação alfabético</span><span class="sxs-lookup"><span data-stu-id="a1757-2368">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2369">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2369">Checksum</span></span>

<span data-ttu-id="a1757-2370">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2370">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2371">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2371">Definition</span></span>

<span data-ttu-id="a1757-2372">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2372">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2373">A expressão regular Regex_india_permanent_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2373">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2374">Uma palavra-chave de Keyword_india_permanent_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2374">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="a1757-2375">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2375">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2376">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2376">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="a1757-2377">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2377">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="a1757-2378">Número da Conta Permanente</span><span class="sxs-lookup"><span data-stu-id="a1757-2378">Permanent Account Number</span></span> 
- <span data-ttu-id="a1757-2379">APLICAR</span><span class="sxs-lookup"><span data-stu-id="a1757-2379">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="a1757-2380">Número de Identificação Exclusivo da Índia (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="a1757-2380">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2381">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2381">Format</span></span>

<span data-ttu-id="a1757-2382">12 dígitos contendo espaços opcionais ou traços</span><span class="sxs-lookup"><span data-stu-id="a1757-2382">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2383">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2383">Pattern</span></span>

<span data-ttu-id="a1757-2384">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-2384">12 digits:</span></span>
- <span data-ttu-id="a1757-2385">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2385">Four digits</span></span> 
- <span data-ttu-id="a1757-2386">Um espaço ou um traço opcional </span><span class="sxs-lookup"><span data-stu-id="a1757-2386">An optional space or dash</span></span> 
- <span data-ttu-id="a1757-2387">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2387">Four digits</span></span> 
- <span data-ttu-id="a1757-2388">Um espaço ou um traço opcional </span><span class="sxs-lookup"><span data-stu-id="a1757-2388">An optional space or dash</span></span> 
- <span data-ttu-id="a1757-2389">O dígito final que é o dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2389">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2390">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2390">Checksum</span></span>

<span data-ttu-id="a1757-2391">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2391">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2392">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2392">Definition</span></span>

<span data-ttu-id="a1757-2393">Uma política de DLP é de 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a função Func_india_aadhaar localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2393">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="a1757-2394">Uma palavra-chave de Keyword_india_aadhar for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2394">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="a1757-2395">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2395">The checksum passes.</span></span>
<span data-ttu-id="a1757-2396">Uma política de DLP é de 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a função Func_india_aadhaar localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="a1757-2397">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2397">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="a1757-2398">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2398">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="a1757-2399">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="a1757-2399">Keyword_india_aadhar</span></span>
- <span data-ttu-id="a1757-2400">Aadhar</span><span class="sxs-lookup"><span data-stu-id="a1757-2400">Aadhar</span></span>
- <span data-ttu-id="a1757-2401">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="a1757-2401">Aadhaar</span></span>
- <span data-ttu-id="a1757-2402">UID</span><span class="sxs-lookup"><span data-stu-id="a1757-2402">UID</span></span>
- <span data-ttu-id="a1757-2403">आधार</span><span class="sxs-lookup"><span data-stu-id="a1757-2403">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="a1757-2404">Número do Cartão de Identidade da Indonésia (KTP)</span><span class="sxs-lookup"><span data-stu-id="a1757-2404">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2405">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2405">Format</span></span>

<span data-ttu-id="a1757-2406">16 dígitos contendo pontos opcionais</span><span class="sxs-lookup"><span data-stu-id="a1757-2406">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2407">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2407">Pattern</span></span>

<span data-ttu-id="a1757-2408">16 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-2408">16 digits:</span></span>
- <span data-ttu-id="a1757-2409">Código de província de dois dígitos </span><span class="sxs-lookup"><span data-stu-id="a1757-2409">Two-digit province code</span></span> 
- <span data-ttu-id="a1757-2410">Um ponto (opcional) </span><span class="sxs-lookup"><span data-stu-id="a1757-2410">A period (optional)</span></span> 
- <span data-ttu-id="a1757-2411">Código de dois dígitos da regência ou da cidade </span><span class="sxs-lookup"><span data-stu-id="a1757-2411">Two-digit regency or city code</span></span> 
- <span data-ttu-id="a1757-2412">Código de dois dígitos do subdistrito </span><span class="sxs-lookup"><span data-stu-id="a1757-2412">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="a1757-2413">Um ponto (opcional) </span><span class="sxs-lookup"><span data-stu-id="a1757-2413">A period (optional)</span></span> 
- <span data-ttu-id="a1757-2414">Seis dígitos no formato DDMMAA que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-2414">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a1757-2415">Um ponto (opcional) </span><span class="sxs-lookup"><span data-stu-id="a1757-2415">A period (optional)</span></span> 
- <span data-ttu-id="a1757-2416">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2416">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2417">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2417">Checksum</span></span>

<span data-ttu-id="a1757-2418">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2419">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2419">Definition</span></span>

<span data-ttu-id="a1757-2420">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2421">A expressão regular Regex_indonesia_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2421">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2422">Uma palavra-chave de Keyword_indonesia_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2422">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="a1757-2423">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2423">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2424">A expressão regular Regex_indonesia_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2424">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2425">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2425">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="a1757-2426">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="a1757-2426">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="a1757-2427">KTP</span><span class="sxs-lookup"><span data-stu-id="a1757-2427">KTP</span></span>
- <span data-ttu-id="a1757-2428">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="a1757-2428">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="a1757-2429">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="a1757-2429">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="a1757-2430">Número da Conta Bancária Internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="a1757-2430">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2431">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2431">Format</span></span>

<span data-ttu-id="a1757-2432">Código do país (duas letras) mais dígitos de verificação (dois dígitos) mais Bban número (até 30 caracteres)</span><span class="sxs-lookup"><span data-stu-id="a1757-2432">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2433">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2433">Pattern</span></span>

<span data-ttu-id="a1757-2434">O padrão deve incluir todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="a1757-2434">Pattern must include all of the following:</span></span>

- <span data-ttu-id="a1757-2435">Código de país de duas letras</span><span class="sxs-lookup"><span data-stu-id="a1757-2435">Two-letter country code</span></span>
- <span data-ttu-id="a1757-2436">Dois dígitos de verificação (seguidos por um espaço opcional)</span><span class="sxs-lookup"><span data-stu-id="a1757-2436">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="a1757-2437">1-7 grupos de quatro letras ou dígitos (podem ser separados por espaços)</span><span class="sxs-lookup"><span data-stu-id="a1757-2437">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="a1757-2438">1 a 3 letras ou dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2438">1-3 letters or digits</span></span>

<span data-ttu-id="a1757-2439">O formato de cada país é um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="a1757-2439">The format for each country is slightly different.</span></span> <span data-ttu-id="a1757-2440">O tipo de informação confidencial do IBAN cobre estes 60 países:</span><span class="sxs-lookup"><span data-stu-id="a1757-2440">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="a1757-2441">AD, AE, Al, at, AZ, BA, or, BG, BH, ch, CR, Cy, cz, de, DK, do, EE, es, Fi, fo, FR, GB, GE, GI, GL, GA, HR, Hu, IE, Il, is, it, kW, KZ, lb, li, lt, Lu, LV, MC, MD, me, MK, Sr, MT, MU, NL, não, pl, pt,, RS, SK, SM, TN</span><span class="sxs-lookup"><span data-stu-id="a1757-2441">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2442">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2442">Checksum</span></span>

<span data-ttu-id="a1757-2443">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2443">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2444">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2444">Definition</span></span>

<span data-ttu-id="a1757-2445">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2445">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2446">A função Func_iban localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2446">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2447">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2447">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2448">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2448">Keywords</span></span>

<span data-ttu-id="a1757-2449">None</span><span class="sxs-lookup"><span data-stu-id="a1757-2449">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="a1757-2450">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="a1757-2450">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2451">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2451">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="a1757-2452">IPv4</span><span class="sxs-lookup"><span data-stu-id="a1757-2452">IPv4:</span></span>
<span data-ttu-id="a1757-2453">Padrão complexo que é responsável por versões formatadas (pontos) e não formatadas (sem pontos) dos endereços IPv4</span><span class="sxs-lookup"><span data-stu-id="a1757-2453">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="a1757-2454">IPv6</span><span class="sxs-lookup"><span data-stu-id="a1757-2454">IPv6:</span></span>
<span data-ttu-id="a1757-2455">Padrão complexo que é responsável por números IPv6 formatados (que incluem dois pontos)</span><span class="sxs-lookup"><span data-stu-id="a1757-2455">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2456">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2456">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2457">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2457">Checksum</span></span>

<span data-ttu-id="a1757-2458">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2458">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2459">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2459">Definition</span></span>

<span data-ttu-id="a1757-2460">Para IPv6, uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2460">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2461">A expressão regular Regex_ipv6_address localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2461">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2462">Nenhuma palavra-chave de Keyword_ipaddress for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2462">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a1757-2463">Para IPv4, uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2463">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2464">A expressão regular Regex_ipv4_address localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2464">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2465">Uma palavra-chave de Keyword_ipaddress for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2465">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a1757-2466">Para IPv6, uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2466">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2467">A expressão regular Regex_ipv6_address localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2467">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2468">Nenhuma palavra-chave de Keyword_ipaddress for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2468">No keyword from Keyword_ipaddress is found.</span></span>

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2469">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2469">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="a1757-2470">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="a1757-2470">Keyword_ipaddress</span></span>

- <span data-ttu-id="a1757-2471">IP (esta palavra-chave diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-2471">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="a1757-2472">ip address</span><span class="sxs-lookup"><span data-stu-id="a1757-2472">ip address</span></span> 
- <span data-ttu-id="a1757-2473">endereços ip</span><span class="sxs-lookup"><span data-stu-id="a1757-2473">ip addresses</span></span>
- <span data-ttu-id="a1757-2474">internet protocol</span><span class="sxs-lookup"><span data-stu-id="a1757-2474">internet protocol</span></span>
- <span data-ttu-id="a1757-2475">IP כתובת ה</span><span class="sxs-lookup"><span data-stu-id="a1757-2475">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="a1757-2476">Classificação internacional do Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="a1757-2476">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2477">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2477">Format</span></span>

<span data-ttu-id="a1757-2478">Dictionary</span><span class="sxs-lookup"><span data-stu-id="a1757-2478">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2479">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2479">Pattern</span></span>

<span data-ttu-id="a1757-2480">Palavra-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2480">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2481">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2481">Checksum</span></span>

<span data-ttu-id="a1757-2482">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2482">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2483">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2483">Definition</span></span>

<span data-ttu-id="a1757-2484">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2485">Uma palavra-chave de Dictionary_icd_10_updated for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2485">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="a1757-2486">Uma palavra-chave de Dictionary_icd_10_codes for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2486">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="a1757-2487">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2487">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2488">Uma palavra-chave de Dictionary_icd_10_ atualizada é encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2488">A keyword from Dictionary_icd_10_ updated is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

<span data-ttu-id="a1757-2489">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2489">Keywords</span></span>

<span data-ttu-id="a1757-2490">Qualquer termo do dicionário de palavra-chave Dictionary_icd_10_updated, que se baseia na [classificação internacional do Diseases, décimo revisão, modificação clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="a1757-2490">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="a1757-2491">Esse tipo procura apenas o termo, não os códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="a1757-2491">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="a1757-2492">Qualquer termo do dicionário de palavra-chave Dictionary_icd_10_codes, que se baseia na [classificação internacional do Diseases, décimo revisão, modificação clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="a1757-2492">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="a1757-2493">Este tipo procura apenas por códigos de seguro, não a descrição.</span><span class="sxs-lookup"><span data-stu-id="a1757-2493">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="a1757-2494">Classificação internacional do Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="a1757-2494">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2495">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2495">Format</span></span>

<span data-ttu-id="a1757-2496">Dictionary</span><span class="sxs-lookup"><span data-stu-id="a1757-2496">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2497">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2497">Pattern</span></span>

<span data-ttu-id="a1757-2498">Palavra-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2498">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2499">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2499">Checksum</span></span>

<span data-ttu-id="a1757-2500">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2500">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2501">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2501">Definition</span></span>

<span data-ttu-id="a1757-2502">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2502">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2503">Uma palavra-chave de Dictionary_icd_9_updated for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2503">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="a1757-2504">Uma palavra-chave de Dictionary_icd_9_codes for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2504">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="a1757-2505">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2505">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2506">Uma palavra-chave de Dictionary_icd_9_updated for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2506">A keyword from Dictionary_icd_9_updated is found.</span></span>

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2507">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2507">Keywords</span></span>

<span data-ttu-id="a1757-2508">Qualquer termo do dicionário de palavra-chave Dictionary_icd_9_updated, que se baseia na [classificação internacional do Diseases, Nona revisão, modificação clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="a1757-2508">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="a1757-2509">Esse tipo procura apenas o termo, não os códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="a1757-2509">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="a1757-2510">Qualquer termo do dicionário de palavra-chave Dictionary_icd_9_codes, que se baseia na [classificação internacional do Diseases, Nona revisão, modificação clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="a1757-2510">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="a1757-2511">Este tipo procura apenas por códigos de seguro, não a descrição.</span><span class="sxs-lookup"><span data-stu-id="a1757-2511">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="a1757-2512">Número de Serviço Público Pessoal (PPS) da Irlanda</span><span class="sxs-lookup"><span data-stu-id="a1757-2512">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2513">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2513">Format</span></span>

<span data-ttu-id="a1757-2514">Formato antigo (até 31 de dezembro de 2012):</span><span class="sxs-lookup"><span data-stu-id="a1757-2514">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a1757-2515">Sete dígitos seguidos de 1 a 2 letras </span><span class="sxs-lookup"><span data-stu-id="a1757-2515">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="a1757-2516">Novo formato (1 Jan 2013 e posterior):</span><span class="sxs-lookup"><span data-stu-id="a1757-2516">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a1757-2517">Sete dígitos seguidos de duas letras</span><span class="sxs-lookup"><span data-stu-id="a1757-2517">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2518">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2518">Pattern</span></span>

<span data-ttu-id="a1757-2519">Formato antigo (até 31 de dezembro de 2012):</span><span class="sxs-lookup"><span data-stu-id="a1757-2519">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a1757-2520">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="a1757-2520">Seven digits</span></span> 
- <span data-ttu-id="a1757-2521">1 a 2 letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-2521">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="a1757-2522">Novo formato (1 Jan 2013 e posterior):</span><span class="sxs-lookup"><span data-stu-id="a1757-2522">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a1757-2523">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="a1757-2523">Seven digits</span></span> 
- <span data-ttu-id="a1757-2524">Uma letra (não diferencia maiúsculas de minúsculas) que é um dígito de verificação alfabético </span><span class="sxs-lookup"><span data-stu-id="a1757-2524">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="a1757-2525">A letra "A" ou "H" (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-2525">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2526">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2526">Checksum</span></span>

<span data-ttu-id="a1757-2527">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2527">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2528">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2528">Definition</span></span>

<span data-ttu-id="a1757-2529">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2530">A função Func_ireland_pps localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2530">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2531">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-2531">One of the following is true:</span></span>
    - <span data-ttu-id="a1757-2532">Uma palavra-chave de Keyword_ireland_pps for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2532">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="a1757-2533">A função Func_eu_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-2533">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a1757-2534">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2534">The checksum passes.</span></span>

<span data-ttu-id="a1757-2535">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2535">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2536">A função Func_ireland_pps localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2536">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2537">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2537">The checksum passes.</span></span>

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2538">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2538">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="a1757-2539">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="a1757-2539">Keyword_ireland_pps</span></span>

- <span data-ttu-id="a1757-2540">Número do Serviço Público Pessoal</span><span class="sxs-lookup"><span data-stu-id="a1757-2540">Personal Public Service Number</span></span> 
- <span data-ttu-id="a1757-2541">Número PPS</span><span class="sxs-lookup"><span data-stu-id="a1757-2541">PPS Number</span></span> 
- <span data-ttu-id="a1757-2542">Núm PPS</span><span class="sxs-lookup"><span data-stu-id="a1757-2542">PPS Num</span></span> 
- <span data-ttu-id="a1757-2543">Nº PPS</span><span class="sxs-lookup"><span data-stu-id="a1757-2543">PPS No.</span></span> 
- <span data-ttu-id="a1757-2544"># PPS</span><span class="sxs-lookup"><span data-stu-id="a1757-2544">PPS #</span></span> 
- <span data-ttu-id="a1757-2545">PPS #</span><span class="sxs-lookup"><span data-stu-id="a1757-2545">PPS#</span></span> 
- <span data-ttu-id="a1757-2546">PPSN</span><span class="sxs-lookup"><span data-stu-id="a1757-2546">PPSN</span></span> 
- <span data-ttu-id="a1757-2547">Cartão dos Serviços Públicos</span><span class="sxs-lookup"><span data-stu-id="a1757-2547">Public Services Card</span></span> 
- <span data-ttu-id="a1757-2548">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="a1757-2548">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="a1757-2549">Uimh.</span><span class="sxs-lookup"><span data-stu-id="a1757-2549">Uimh.</span></span> <span data-ttu-id="a1757-2550">PSP</span><span class="sxs-lookup"><span data-stu-id="a1757-2550">PSP</span></span> 
- <span data-ttu-id="a1757-2551">PSP</span><span class="sxs-lookup"><span data-stu-id="a1757-2551">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="a1757-2552">Número de conta bancária de Israel</span><span class="sxs-lookup"><span data-stu-id="a1757-2552">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2553">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2553">Format</span></span>

<span data-ttu-id="a1757-2554">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2554">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2555">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2555">Pattern</span></span>

<span data-ttu-id="a1757-2556">Binário</span><span class="sxs-lookup"><span data-stu-id="a1757-2556">Formatted:</span></span>
- <span data-ttu-id="a1757-2557">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2557">Two digits</span></span> 
- <span data-ttu-id="a1757-2558">Um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-2558">A dash</span></span> 
- <span data-ttu-id="a1757-2559">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2559">Three digits</span></span> 
- <span data-ttu-id="a1757-2560">Um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-2560">A dash</span></span> 
- <span data-ttu-id="a1757-2561">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2561">Eight digits</span></span>

<span data-ttu-id="a1757-2562">Não formatado</span><span class="sxs-lookup"><span data-stu-id="a1757-2562">Unformatted:</span></span>
- <span data-ttu-id="a1757-2563">13 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-2563">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2564">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2564">Checksum</span></span>

<span data-ttu-id="a1757-2565">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2565">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2566">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2566">Definition</span></span>

<span data-ttu-id="a1757-2567">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2568">A expressão regular Regex_israel_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2568">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2569">Uma palavra-chave de Keyword_israel_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2569">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2570">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2570">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="a1757-2571">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2571">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="a1757-2572">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2572">Bank Account Number</span></span> 
- <span data-ttu-id="a1757-2573">Bank Account</span><span class="sxs-lookup"><span data-stu-id="a1757-2573">Bank Account</span></span> 
- <span data-ttu-id="a1757-2574">Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2574">Account Number</span></span> 
- <span data-ttu-id="a1757-2575">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="a1757-2575">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="a1757-2576">ID nacional de Israel</span><span class="sxs-lookup"><span data-stu-id="a1757-2576">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2577">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2577">Format</span></span>

<span data-ttu-id="a1757-2578">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2578">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2579">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2579">Pattern</span></span>

<span data-ttu-id="a1757-2580">Nove dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-2580">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2581">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2581">Checksum</span></span>

<span data-ttu-id="a1757-2582">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2582">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2583">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2583">Definition</span></span>

<span data-ttu-id="a1757-2584">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2585">A função Func_israeli_national_id_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2585">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2586">Uma palavra-chave de Keyword_Israel_National_ID for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2586">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="a1757-2587">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2587">The checksum passes.</span></span>

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2588">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2588">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="a1757-2589">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="a1757-2589">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="a1757-2590">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="a1757-2590">מספר זהות</span></span> 
- <span data-ttu-id="a1757-2591">Número de identificação nacional</span><span class="sxs-lookup"><span data-stu-id="a1757-2591">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="a1757-2592">Número de carteira de motorista da Itália</span><span class="sxs-lookup"><span data-stu-id="a1757-2592">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2593">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2593">Format</span></span>

<span data-ttu-id="a1757-2594">Uma combinação de 10 letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2594">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2595">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2595">Pattern</span></span>

- <span data-ttu-id="a1757-2596">Uma combinação de 10 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-2596">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="a1757-2597">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="a1757-2597">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-2598">A letra "A" ou "V" (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="a1757-2598">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-2599">Sete letras (não diferenciam maiúsculas de minúsculas), dígitos ou o caractere de sublinhado</span><span class="sxs-lookup"><span data-stu-id="a1757-2599">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="a1757-2600">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="a1757-2600">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2601">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2601">Checksum</span></span>

<span data-ttu-id="a1757-2602">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2602">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2603">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2603">Definition</span></span>

<span data-ttu-id="a1757-2604">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2604">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2605">A expressão regular Regex_italy_drivers_license_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2605">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2606">Uma palavra-chave de Keyword_italy_drivers_license_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2606">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2607">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2607">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="a1757-2608">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2608">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="a1757-2609">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="a1757-2609">numero di patente di guida</span></span> 
- <span data-ttu-id="a1757-2610">patente di guida</span><span class="sxs-lookup"><span data-stu-id="a1757-2610">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="a1757-2611">Número de conta bancária do Japão</span><span class="sxs-lookup"><span data-stu-id="a1757-2611">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2612">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2612">Format</span></span>

<span data-ttu-id="a1757-2613">Sete ou oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2613">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2614">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2614">Pattern</span></span>

<span data-ttu-id="a1757-2615">Número da Conta Bancária:</span><span class="sxs-lookup"><span data-stu-id="a1757-2615">Bank account number:</span></span>
- <span data-ttu-id="a1757-2616">Sete ou oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2616">Seven or eight digits</span></span>
- <span data-ttu-id="a1757-2617">Código da agência de conta bancária:</span><span class="sxs-lookup"><span data-stu-id="a1757-2617">Bank account branch code:</span></span>
- <span data-ttu-id="a1757-2618">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2618">Four digits</span></span> 
- <span data-ttu-id="a1757-2619">Um espaço ou um traço (opcional)</span><span class="sxs-lookup"><span data-stu-id="a1757-2619">A space or dash (optional)</span></span> 
- <span data-ttu-id="a1757-2620">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2620">Three digits</span></span>

<span data-ttu-id="a1757-2621">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2621">Checksum</span></span>

<span data-ttu-id="a1757-2622">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2622">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2623">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2623">Definition</span></span>

<span data-ttu-id="a1757-2624">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2625">A função Func_jp_bank_account localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2625">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2626">Uma palavra-chave de Keyword_jp_bank_account for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2626">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="a1757-2627">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-2627">One of the following is true:</span></span>
- <span data-ttu-id="a1757-2628">A função Func_jp_bank_account_branch_code localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2628">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2629">Uma palavra-chave de Keyword_jp_bank_branch_code for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2629">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="a1757-2630">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2631">A função Func_jp_bank_account localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2631">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2632">Uma palavra-chave de Keyword_jp_bank_account for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2632">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2633">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2633">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="a1757-2634">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="a1757-2634">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="a1757-2635">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2635">Checking Account Number</span></span> 
- <span data-ttu-id="a1757-2636">Checking Account</span><span class="sxs-lookup"><span data-stu-id="a1757-2636">Checking Account</span></span> 
- <span data-ttu-id="a1757-2637">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="a1757-2637">Checking Account #</span></span> 
- <span data-ttu-id="a1757-2638">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2638">Checking Acct Number</span></span> 
- <span data-ttu-id="a1757-2639">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="a1757-2639">Checking Acct #</span></span> 
- <span data-ttu-id="a1757-2640">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2640">Checking Acct No.</span></span> 
- <span data-ttu-id="a1757-2641">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2641">Checking Account No.</span></span> 
- <span data-ttu-id="a1757-2642">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2642">Bank Account Number</span></span> 
- <span data-ttu-id="a1757-2643">Bank Account</span><span class="sxs-lookup"><span data-stu-id="a1757-2643">Bank Account</span></span> 
- <span data-ttu-id="a1757-2644">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="a1757-2644">Bank Account #</span></span> 
- <span data-ttu-id="a1757-2645">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2645">Bank Acct Number</span></span> 
- <span data-ttu-id="a1757-2646">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="a1757-2646">Bank Acct #</span></span> 
- <span data-ttu-id="a1757-2647">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2647">Bank Acct No.</span></span> 
- <span data-ttu-id="a1757-2648">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2648">Bank Account No.</span></span> 
- <span data-ttu-id="a1757-2649">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2649">Savings Account Number</span></span> 
- <span data-ttu-id="a1757-2650">Savings Account</span><span class="sxs-lookup"><span data-stu-id="a1757-2650">Savings Account</span></span> 
- <span data-ttu-id="a1757-2651">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="a1757-2651">Savings Account #</span></span> 
- <span data-ttu-id="a1757-2652">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2652">Savings Acct Number</span></span> 
- <span data-ttu-id="a1757-2653">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="a1757-2653">Savings Acct #</span></span> 
- <span data-ttu-id="a1757-2654">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2654">Savings Acct No.</span></span> 
- <span data-ttu-id="a1757-2655">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2655">Savings Account No.</span></span> 
- <span data-ttu-id="a1757-2656">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2656">Debit Account Number</span></span> 
- <span data-ttu-id="a1757-2657">Debit Account</span><span class="sxs-lookup"><span data-stu-id="a1757-2657">Debit Account</span></span> 
- <span data-ttu-id="a1757-2658">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="a1757-2658">Debit Account #</span></span> 
- <span data-ttu-id="a1757-2659">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2659">Debit Acct Number</span></span> 
- <span data-ttu-id="a1757-2660">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="a1757-2660">Debit Acct #</span></span> 
- <span data-ttu-id="a1757-2661">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2661">Debit Acct No.</span></span> 
- <span data-ttu-id="a1757-2662">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2662">Debit Account No.</span></span> 
- <span data-ttu-id="a1757-2663">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="a1757-2663">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="a1757-2664">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="a1757-2664">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="a1757-2665">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="a1757-2665">＃勘定の確認</span></span> 
- <span data-ttu-id="a1757-2666">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="a1757-2666">勘定番号の確認</span></span> 
- <span data-ttu-id="a1757-2667">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="a1757-2667">口座番号の確認</span></span> 
- <span data-ttu-id="a1757-2668">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2668">銀行口座番号</span></span> 
- <span data-ttu-id="a1757-2669">銀行口座</span><span class="sxs-lookup"><span data-stu-id="a1757-2669">銀行口座</span></span> 
- <span data-ttu-id="a1757-2670">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="a1757-2670">銀行口座＃</span></span> 
- <span data-ttu-id="a1757-2671">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2671">銀行の勘定番号</span></span> 
- <span data-ttu-id="a1757-2672">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="a1757-2672">銀行のacct＃</span></span> 
- <span data-ttu-id="a1757-2673">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="a1757-2673">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="a1757-2674">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2674">銀行口座番号</span></span>
- <span data-ttu-id="a1757-2675">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2675">普通預金口座番号</span></span> 
- <span data-ttu-id="a1757-2676">預金口座</span><span class="sxs-lookup"><span data-stu-id="a1757-2676">預金口座</span></span> 
- <span data-ttu-id="a1757-2677">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="a1757-2677">貯蓄口座＃</span></span> 
- <span data-ttu-id="a1757-2678">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="a1757-2678">貯蓄勘定の数</span></span> 
- <span data-ttu-id="a1757-2679">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="a1757-2679">貯蓄勘定＃</span></span> 
- <span data-ttu-id="a1757-2680">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2680">貯蓄勘定番号</span></span> 
- <span data-ttu-id="a1757-2681">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2681">普通預金口座番号</span></span> 
- <span data-ttu-id="a1757-2682">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2682">引き落とし口座番号</span></span> 
- <span data-ttu-id="a1757-2683">口座番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2683">口座番号</span></span> 
- <span data-ttu-id="a1757-2684">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="a1757-2684">口座番号＃</span></span> 
- <span data-ttu-id="a1757-2685">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2685">デビットのacct番号</span></span> 
- <span data-ttu-id="a1757-2686">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="a1757-2686">デビット勘定＃</span></span> 
- <span data-ttu-id="a1757-2687">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2687">デビットACCTの番号</span></span> 
- <span data-ttu-id="a1757-2688">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2688">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="a1757-2689">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="a1757-2689">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="a1757-2690">Otemachi</span><span class="sxs-lookup"><span data-stu-id="a1757-2690">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="a1757-2691">Número de carteira de motorista do Japão</span><span class="sxs-lookup"><span data-stu-id="a1757-2691">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2692">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2692">Format</span></span>

<span data-ttu-id="a1757-2693">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2693">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2694">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2694">Pattern</span></span>

<span data-ttu-id="a1757-2695">12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-2695">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2696">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2696">Checksum</span></span>

<span data-ttu-id="a1757-2697">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2697">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2698">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2698">Definition</span></span>

<span data-ttu-id="a1757-2699">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2699">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2700">A função Func_jp_drivers_license_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2700">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2701">Uma palavra-chave de Keyword_jp_drivers_license_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2701">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2702">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2702">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="a1757-2703">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2703">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="a1757-2704">distribuição #</span><span class="sxs-lookup"><span data-stu-id="a1757-2704">dl#</span></span> 
- <span data-ttu-id="a1757-2705">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a1757-2705">DL＃</span></span> 
- <span data-ttu-id="a1757-2706">DL #</span><span class="sxs-lookup"><span data-stu-id="a1757-2706">dls#</span></span> 
- <span data-ttu-id="a1757-2707">DL</span><span class="sxs-lookup"><span data-stu-id="a1757-2707">DLS＃</span></span> 
- <span data-ttu-id="a1757-2708">driver license</span><span class="sxs-lookup"><span data-stu-id="a1757-2708">driver license</span></span> 
- <span data-ttu-id="a1757-2709">driver licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-2709">driver licenses</span></span> 
- <span data-ttu-id="a1757-2710">drivers license</span><span class="sxs-lookup"><span data-stu-id="a1757-2710">drivers license</span></span> 
- <span data-ttu-id="a1757-2711">driver's license</span><span class="sxs-lookup"><span data-stu-id="a1757-2711">driver's license</span></span> 
- <span data-ttu-id="a1757-2712">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-2712">drivers licenses</span></span> 
- <span data-ttu-id="a1757-2713">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-2713">driver's licenses</span></span> 
- <span data-ttu-id="a1757-2714">driving licence</span><span class="sxs-lookup"><span data-stu-id="a1757-2714">driving licence</span></span> 
- <span data-ttu-id="a1757-2715">driver'lic #</span><span class="sxs-lookup"><span data-stu-id="a1757-2715">lic#</span></span> 
- <span data-ttu-id="a1757-2716">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="a1757-2716">LIC＃</span></span> 
- <span data-ttu-id="a1757-2717">driver'lics #</span><span class="sxs-lookup"><span data-stu-id="a1757-2717">lics#</span></span> 
- <span data-ttu-id="a1757-2718">state id</span><span class="sxs-lookup"><span data-stu-id="a1757-2718">state id</span></span> 
- <span data-ttu-id="a1757-2719">state identification</span><span class="sxs-lookup"><span data-stu-id="a1757-2719">state identification</span></span> 
- <span data-ttu-id="a1757-2720">state identification number</span><span class="sxs-lookup"><span data-stu-id="a1757-2720">state identification number</span></span> 
- <span data-ttu-id="a1757-2721">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="a1757-2721">低所得国＃</span></span> 
- <span data-ttu-id="a1757-2722">免許証</span><span class="sxs-lookup"><span data-stu-id="a1757-2722">免許証</span></span> 
- <span data-ttu-id="a1757-2723">状態ID</span><span class="sxs-lookup"><span data-stu-id="a1757-2723">状態ID</span></span>
- <span data-ttu-id="a1757-2724">状態の識別</span><span class="sxs-lookup"><span data-stu-id="a1757-2724">状態の識別</span></span> 
- <span data-ttu-id="a1757-2725">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2725">状態の識別番号</span></span> 
- <span data-ttu-id="a1757-2726">運転免許</span><span class="sxs-lookup"><span data-stu-id="a1757-2726">運転免許</span></span> 
- <span data-ttu-id="a1757-2727">運転免許証</span><span class="sxs-lookup"><span data-stu-id="a1757-2727">運転免許証</span></span> 
- <span data-ttu-id="a1757-2728">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2728">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="a1757-2729">Número de passaporte do Japão</span><span class="sxs-lookup"><span data-stu-id="a1757-2729">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2730">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2730">Format</span></span>

<span data-ttu-id="a1757-2731">Duas letras seguidas por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2731">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2732">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2732">Pattern</span></span>

<span data-ttu-id="a1757-2733">Duas letras (não diferencia maiúsculas de minúsculas) seguidas de sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2733">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2734">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2734">Checksum</span></span>

<span data-ttu-id="a1757-2735">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2736">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2736">Definition</span></span>

<span data-ttu-id="a1757-2737">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2738">A função Func_jp_passport localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2738">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2739">Uma palavra-chave de Keyword_jp_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2739">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2740">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2740">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="a1757-2741">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="a1757-2741">Keyword_jp_passport</span></span>

- <span data-ttu-id="a1757-2742">パスポート</span><span class="sxs-lookup"><span data-stu-id="a1757-2742">パスポート</span></span> 
- <span data-ttu-id="a1757-2743">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2743">パスポート番号</span></span> 
- <span data-ttu-id="a1757-2744">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a1757-2744">パスポートのNum</span></span> 
- <span data-ttu-id="a1757-2745">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a1757-2745">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="a1757-2746">Número de registro de residente do Japão</span><span class="sxs-lookup"><span data-stu-id="a1757-2746">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2747">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2747">Format</span></span>

<span data-ttu-id="a1757-2748">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2748">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2749">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2749">Pattern</span></span>

<span data-ttu-id="a1757-2750">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-2750">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2751">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2751">Checksum</span></span>

<span data-ttu-id="a1757-2752">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2752">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2753">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2753">Definition</span></span>

<span data-ttu-id="a1757-2754">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2755">A função Func_jp_resident_registration_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2755">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2756">Uma palavra-chave de Keyword_jp_resident_registration_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2756">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2757">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2757">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="a1757-2758">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2758">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="a1757-2759">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2759">Resident Registration Number</span></span>
- <span data-ttu-id="a1757-2760">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2760">Resident Register Number</span></span> 
- <span data-ttu-id="a1757-2761">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2761">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="a1757-2762">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2762">Resident Registration No.</span></span> 
- <span data-ttu-id="a1757-2763">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2763">Resident Register No.</span></span> 
- <span data-ttu-id="a1757-2764">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2764">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="a1757-2765">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2765">Basic Resident Register No.</span></span> 
- <span data-ttu-id="a1757-2766">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="a1757-2766">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="a1757-2767">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2767">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="a1757-2768">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="a1757-2768">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="a1757-2769">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2769">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="a1757-2770">Número de seguro social do Japão (SIN)</span><span class="sxs-lookup"><span data-stu-id="a1757-2770">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2771">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2771">Format</span></span>

<span data-ttu-id="a1757-2772">7 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2772">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2773">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2773">Pattern</span></span>

<span data-ttu-id="a1757-2774">7 a 12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-2774">7-12 digits:</span></span>
- <span data-ttu-id="a1757-2775">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2775">Four digits</span></span> 
- <span data-ttu-id="a1757-2776">Um hífen (opcional)</span><span class="sxs-lookup"><span data-stu-id="a1757-2776">A hyphen (optional)</span></span> 
- <span data-ttu-id="a1757-2777">Seis dígitos ou</span><span class="sxs-lookup"><span data-stu-id="a1757-2777">Six digits OR</span></span>
- <span data-ttu-id="a1757-2778">7 a 12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-2778">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2779">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2779">Checksum</span></span>

<span data-ttu-id="a1757-2780">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2780">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2781">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2781">Definition</span></span>

<span data-ttu-id="a1757-2782">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2782">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2783">A função Func_jp_sin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2783">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2784">Uma palavra-chave de Keyword_jp_sin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2784">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="a1757-2785">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2785">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2786">A função Func_jp_sin_pre_1997 localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2786">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2787">Uma palavra-chave de Keyword_jp_sin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2787">A keyword from Keyword_jp_sin is found.</span></span>

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2788">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2788">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="a1757-2789">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="a1757-2789">Keyword_jp_sin</span></span>

- <span data-ttu-id="a1757-2790">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="a1757-2790">Social Insurance No.</span></span> 
- <span data-ttu-id="a1757-2791">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="a1757-2791">Social Insurance Num</span></span> 
- <span data-ttu-id="a1757-2792">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="a1757-2792">Social Insurance Number</span></span> 
- <span data-ttu-id="a1757-2793">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="a1757-2793">社会保険のテンキー</span></span> 
- <span data-ttu-id="a1757-2794">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2794">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="a1757-2795">Número do cartão de residência japonês</span><span class="sxs-lookup"><span data-stu-id="a1757-2795">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2796">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2796">Format</span></span>

<span data-ttu-id="a1757-2797">12 letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2797">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2798">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2798">Pattern</span></span>

<span data-ttu-id="a1757-2799">12 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-2799">12 letters and digits:</span></span>
- <span data-ttu-id="a1757-2800">Duas letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-2800">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="a1757-2801">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2801">Eight digits</span></span> 
- <span data-ttu-id="a1757-2802">Duas letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-2802">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2803">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2803">Checksum</span></span>

<span data-ttu-id="a1757-2804">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2804">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2805">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2805">Definition</span></span>

<span data-ttu-id="a1757-2806">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2807">A expressão regular Regex_jp_residence_card_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2807">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2808">Uma palavra-chave de Keyword_jp_residence_card_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2808">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2809">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2809">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="a1757-2810">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2810">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="a1757-2811">Número do cartão de residência</span><span class="sxs-lookup"><span data-stu-id="a1757-2811">Residence card number</span></span>
- <span data-ttu-id="a1757-2812">Número do cartão de residência</span><span class="sxs-lookup"><span data-stu-id="a1757-2812">Residence card no</span></span>
- <span data-ttu-id="a1757-2813">Cartão de residência #</span><span class="sxs-lookup"><span data-stu-id="a1757-2813">Residence card #</span></span>
- <span data-ttu-id="a1757-2814">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="a1757-2814">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="a1757-2815">Número do Cartão de Identificação da Malásia</span><span class="sxs-lookup"><span data-stu-id="a1757-2815">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2816">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2816">Format</span></span>

<span data-ttu-id="a1757-2817">12 dígitos contendo hifens opcionais</span><span class="sxs-lookup"><span data-stu-id="a1757-2817">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2818">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2818">Pattern</span></span>

<span data-ttu-id="a1757-2819">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-2819">12 digits:</span></span>
- <span data-ttu-id="a1757-2820">Seis dígitos no formato AAMMDD que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-2820">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a1757-2821">Um traço (opcional)</span><span class="sxs-lookup"><span data-stu-id="a1757-2821">A dash (optional)</span></span> 
- <span data-ttu-id="a1757-2822">Código do local de nascimento de duas letras </span><span class="sxs-lookup"><span data-stu-id="a1757-2822">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="a1757-2823">Um traço (opcional)</span><span class="sxs-lookup"><span data-stu-id="a1757-2823">A dash (optional)</span></span> 
- <span data-ttu-id="a1757-2824">Três dígitos aleatórios </span><span class="sxs-lookup"><span data-stu-id="a1757-2824">Three random digits</span></span> 
- <span data-ttu-id="a1757-2825">Código de sexo de um dígito</span><span class="sxs-lookup"><span data-stu-id="a1757-2825">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2826">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2826">Checksum</span></span>

<span data-ttu-id="a1757-2827">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2827">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2828">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2828">Definition</span></span>

<span data-ttu-id="a1757-2829">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2829">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2830">A expressão regular Regex_malaysia_id_card_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2830">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2831">Uma palavra-chave de Keyword_malaysia_id_card_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2831">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2832">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2832">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="a1757-2833">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2833">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="a1757-2834">cartão de aplicativo digital</span><span class="sxs-lookup"><span data-stu-id="a1757-2834">digital application card</span></span>
- <span data-ttu-id="a1757-2835">e/c</span><span class="sxs-lookup"><span data-stu-id="a1757-2835">i/c</span></span>
- <span data-ttu-id="a1757-2836">e/c não</span><span class="sxs-lookup"><span data-stu-id="a1757-2836">i/c no</span></span>
- <span data-ttu-id="a1757-2837">Liga</span><span class="sxs-lookup"><span data-stu-id="a1757-2837">ic</span></span>
- <span data-ttu-id="a1757-2838">IC não</span><span class="sxs-lookup"><span data-stu-id="a1757-2838">ic no</span></span>
- <span data-ttu-id="a1757-2839">id card</span><span class="sxs-lookup"><span data-stu-id="a1757-2839">id card</span></span>
- <span data-ttu-id="a1757-2840">Cartão de identificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2840">identification Card</span></span>
- <span data-ttu-id="a1757-2841">cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-2841">identity card</span></span>
- <span data-ttu-id="a1757-2842">k/p</span><span class="sxs-lookup"><span data-stu-id="a1757-2842">k/p</span></span>
- <span data-ttu-id="a1757-2843">n/p não</span><span class="sxs-lookup"><span data-stu-id="a1757-2843">k/p no</span></span>
- <span data-ttu-id="a1757-2844">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="a1757-2844">kad akuan diri</span></span>
- <span data-ttu-id="a1757-2845">kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="a1757-2845">kad aplikasi digital</span></span>
- <span data-ttu-id="a1757-2846">kad pengenalan Malásia</span><span class="sxs-lookup"><span data-stu-id="a1757-2846">kad pengenalan malaysia</span></span>
- <span data-ttu-id="a1757-2847">KP</span><span class="sxs-lookup"><span data-stu-id="a1757-2847">kp</span></span>
- <span data-ttu-id="a1757-2848">KP não</span><span class="sxs-lookup"><span data-stu-id="a1757-2848">kp no</span></span>
- <span data-ttu-id="a1757-2849">mykad</span><span class="sxs-lookup"><span data-stu-id="a1757-2849">mykad</span></span>
- <span data-ttu-id="a1757-2850">mykas</span><span class="sxs-lookup"><span data-stu-id="a1757-2850">mykas</span></span>
- <span data-ttu-id="a1757-2851">mykid</span><span class="sxs-lookup"><span data-stu-id="a1757-2851">mykid</span></span>
- <span data-ttu-id="a1757-2852">mypr</span><span class="sxs-lookup"><span data-stu-id="a1757-2852">mypr</span></span>
- <span data-ttu-id="a1757-2853">mytentera</span><span class="sxs-lookup"><span data-stu-id="a1757-2853">mytentera</span></span>
- <span data-ttu-id="a1757-2854">cartão de identidade da Malásia</span><span class="sxs-lookup"><span data-stu-id="a1757-2854">malaysia identity card</span></span>
- <span data-ttu-id="a1757-2855">cartão de identidade do Malasiano</span><span class="sxs-lookup"><span data-stu-id="a1757-2855">malaysian identity card</span></span>
- <span data-ttu-id="a1757-2856">nric</span><span class="sxs-lookup"><span data-stu-id="a1757-2856">nric</span></span>
- <span data-ttu-id="a1757-2857">cartão de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="a1757-2857">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="a1757-2858">Número do Serviço do Cidadão (BSN) da Holland</span><span class="sxs-lookup"><span data-stu-id="a1757-2858">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2859">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2859">Format</span></span>

<span data-ttu-id="a1757-2860">8 a 9 dígitos contendo espaços opcionais</span><span class="sxs-lookup"><span data-stu-id="a1757-2860">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2861">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2861">Pattern</span></span>

<span data-ttu-id="a1757-2862">8 a 9 dígitos.</span><span class="sxs-lookup"><span data-stu-id="a1757-2862">8-9 digits:</span></span>
- <span data-ttu-id="a1757-2863">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2863">Three digits</span></span> 
- <span data-ttu-id="a1757-2864">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="a1757-2864">A space (optional)</span></span> 
- <span data-ttu-id="a1757-2865">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2865">Three digits</span></span> 
- <span data-ttu-id="a1757-2866">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="a1757-2866">A space (optional)</span></span> 
- <span data-ttu-id="a1757-2867">2 a 3 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2867">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2868">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2868">Checksum</span></span>

<span data-ttu-id="a1757-2869">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2869">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2870">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2870">Definition</span></span>

<span data-ttu-id="a1757-2871">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2871">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2872">A função Func_netherlands_bsn localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2872">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2873">Uma palavra-chave de Keyword_netherlands_bsn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2873">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="a1757-2874">A função Func_eu_date2 localiza uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-2874">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="a1757-2875">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2875">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2876">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2876">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="a1757-2877">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="a1757-2877">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="a1757-2878">Número do serviço do cidadão</span><span class="sxs-lookup"><span data-stu-id="a1757-2878">Citizen service number</span></span> 
- <span data-ttu-id="a1757-2879">BSN</span><span class="sxs-lookup"><span data-stu-id="a1757-2879">BSN</span></span> 
- <span data-ttu-id="a1757-2880">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2880">Burgerservicenummer</span></span> 
- <span data-ttu-id="a1757-2881">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2881">Sofinummer</span></span> 
- <span data-ttu-id="a1757-2882">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2882">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="a1757-2883">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2883">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="a1757-2884">Número do Ministério da Saúde da Nova Zelândia</span><span class="sxs-lookup"><span data-stu-id="a1757-2884">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2885">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2885">Format</span></span>

<span data-ttu-id="a1757-2886">Três letras, um espaço (opcional) e quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2886">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2887">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2887">Pattern</span></span>

<span data-ttu-id="a1757-2888">Três letras (não diferencia maiúsculas de minúsculas) um espaço (opcional) quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2888">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2889">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2889">Checksum</span></span>

<span data-ttu-id="a1757-2890">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2890">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2891">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2891">Definition</span></span>

<span data-ttu-id="a1757-2892">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2892">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2893">A função Func_new_zealand_ministry_of_health_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2893">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2894">Uma palavra-chave de Keyword_nz_terms for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2894">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="a1757-2895">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2895">The checksum passes.</span></span>

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="a1757-2896">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2896">Keywords</span></span>

<span data-ttu-id="a1757-2897">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="a1757-2897">Keyword_nz_terms</span></span>

- <span data-ttu-id="a1757-2898">NHI</span><span class="sxs-lookup"><span data-stu-id="a1757-2898">NHI</span></span> 
- <span data-ttu-id="a1757-2899">Nova Zelândia</span><span class="sxs-lookup"><span data-stu-id="a1757-2899">New Zealand</span></span> 
- <span data-ttu-id="a1757-2900">Integridade</span><span class="sxs-lookup"><span data-stu-id="a1757-2900">Health</span></span> 
- <span data-ttu-id="a1757-2901">tratamento</span><span class="sxs-lookup"><span data-stu-id="a1757-2901">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="a1757-2902">Número de Identificação da Noruega</span><span class="sxs-lookup"><span data-stu-id="a1757-2902">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2903">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2903">Format</span></span>

<span data-ttu-id="a1757-2904">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2905">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2905">Pattern</span></span>

<span data-ttu-id="a1757-2906">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-2906">11 digits:</span></span>
- <span data-ttu-id="a1757-2907">Seis dígitos no formato DDMMAA que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-2907">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a1757-2908">Número individual de três dígitos </span><span class="sxs-lookup"><span data-stu-id="a1757-2908">Three-digit individual number</span></span> 
- <span data-ttu-id="a1757-2909">Dois dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2909">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2910">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2910">Checksum</span></span>

<span data-ttu-id="a1757-2911">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2912">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2912">Definition</span></span>

<span data-ttu-id="a1757-2913">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2913">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2914">A função Func_norway_id_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2914">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2915">Uma palavra-chave de Keyword_norway_id_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2915">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="a1757-2916">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2916">The checksum passes.</span></span>
- <span data-ttu-id="a1757-2917">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2917">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2918">A função Func_norway_id_numbe localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2918">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2919">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2919">The checksum passes.</span></span>

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2920">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2920">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="a1757-2921">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2921">Keyword_norway_id_number</span></span>

- <span data-ttu-id="a1757-2922">Número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="a1757-2922">Personal identification number</span></span>
- <span data-ttu-id="a1757-2923">Número de Identificação Norueguês</span><span class="sxs-lookup"><span data-stu-id="a1757-2923">Norwegian ID Number</span></span>
- <span data-ttu-id="a1757-2924">Número de Identificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2924">ID Number</span></span>
- <span data-ttu-id="a1757-2925">Identificador</span><span class="sxs-lookup"><span data-stu-id="a1757-2925">Identification</span></span>
- <span data-ttu-id="a1757-2926">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2926">Personnummer</span></span>
- <span data-ttu-id="a1757-2927">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="a1757-2927">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="a1757-2928">Número de Identificação Multiuso Unificada das Filipinas</span><span class="sxs-lookup"><span data-stu-id="a1757-2928">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2929">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2929">Format</span></span>

<span data-ttu-id="a1757-2930">12 dígitos separados por hifens</span><span class="sxs-lookup"><span data-stu-id="a1757-2930">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2931">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2931">Pattern</span></span>

<span data-ttu-id="a1757-2932">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-2932">12 digits:</span></span>
- <span data-ttu-id="a1757-2933">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2933">Four digits</span></span> 
- <span data-ttu-id="a1757-2934">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-2934">A hyphen</span></span> 
- <span data-ttu-id="a1757-2935">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="a1757-2935">Seven digits</span></span> 
- <span data-ttu-id="a1757-2936">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-2936">A hyphen</span></span> 
- <span data-ttu-id="a1757-2937">Um dígito</span><span class="sxs-lookup"><span data-stu-id="a1757-2937">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2938">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2938">Checksum</span></span>

<span data-ttu-id="a1757-2939">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-2939">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2940">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2940">Definition</span></span>

<span data-ttu-id="a1757-2941">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2942">A expressão regular Regex_philippines_unified_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2942">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2943">Uma palavra-chave de Keyword_philippines_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2943">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2944">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2944">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="a1757-2945">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="a1757-2945">Keyword_philippines_id</span></span>

- <span data-ttu-id="a1757-2946">Identificação Multiuso Unificada</span><span class="sxs-lookup"><span data-stu-id="a1757-2946">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="a1757-2947">UMID</span><span class="sxs-lookup"><span data-stu-id="a1757-2947">UMID</span></span> 
- <span data-ttu-id="a1757-2948">Cartão de Identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-2948">Identity Card</span></span> 
- <span data-ttu-id="a1757-2949">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="a1757-2949">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="a1757-2950">Cartão de Identificação da Polônia</span><span class="sxs-lookup"><span data-stu-id="a1757-2950">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2951">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2951">Format</span></span>

<span data-ttu-id="a1757-2952">Três letras e seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2952">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2953">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2953">Pattern</span></span>

<span data-ttu-id="a1757-2954">Três letras (não diferenciam maiúsculas de minúsculas) seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2954">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2955">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2955">Checksum</span></span>

<span data-ttu-id="a1757-2956">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2956">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2957">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2957">Definition</span></span>

<span data-ttu-id="a1757-2958">Uma política de DLP é de 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a função Func_polish_national_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2958">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="a1757-2959">Uma palavra-chave de Keyword_polish_national_id_passport_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2959">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="a1757-2960">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2960">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2961">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2961">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="a1757-2962">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2962">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a1757-2963">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="a1757-2963">Dowód osobisty</span></span>
- <span data-ttu-id="a1757-2964">Numer dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a1757-2964">Numer dowodu osobistego</span></span>
- <span data-ttu-id="a1757-2965">Nazwa i numer dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a1757-2965">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="a1757-2966">Nazwa i NR dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a1757-2966">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="a1757-2967">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="a1757-2967">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="a1757-2968">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="a1757-2968">Dowód Tożsamości</span></span>
- <span data-ttu-id="a1757-2969">Dow.</span><span class="sxs-lookup"><span data-stu-id="a1757-2969">dow.</span></span> <span data-ttu-id="a1757-2970">Opera.</span><span class="sxs-lookup"><span data-stu-id="a1757-2970">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="a1757-2971">ID nacional da Polônia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a1757-2971">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2972">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2972">Format</span></span>

<span data-ttu-id="a1757-2973">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2973">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2974">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2974">Pattern</span></span>

<span data-ttu-id="a1757-2975">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-2975">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2976">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2976">Checksum</span></span>

<span data-ttu-id="a1757-2977">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2977">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2978">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2978">Definition</span></span>

<span data-ttu-id="a1757-2979">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2979">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2980">A função Func_pesel_identification_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2980">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2981">Uma palavra-chave de Keyword_pesel_identification_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2981">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="a1757-2982">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2982">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2983">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2983">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="a1757-2984">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="a1757-2984">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="a1757-2985">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="a1757-2985">Nr PESEL</span></span>
- <span data-ttu-id="a1757-2986">PESEL</span><span class="sxs-lookup"><span data-stu-id="a1757-2986">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="a1757-2987">Passaporte da Polônia</span><span class="sxs-lookup"><span data-stu-id="a1757-2987">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="a1757-2988">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-2988">Format</span></span>

<span data-ttu-id="a1757-2989">Duas letras e sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2989">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-2990">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-2990">Pattern</span></span>

<span data-ttu-id="a1757-2991">Duas letras (não diferencia maiúsculas de minúsculas) seguidas de sete dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-2991">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-2992">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-2992">Checksum</span></span>

<span data-ttu-id="a1757-2993">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-2993">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-2994">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-2994">Definition</span></span>

<span data-ttu-id="a1757-2995">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-2995">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-2996">A função Func_polish_passport_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-2996">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-2997">Uma palavra-chave de Keyword_polish_national_id_passport_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-2997">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="a1757-2998">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-2998">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="a1757-2999">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-2999">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="a1757-3000">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a1757-3000">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a1757-3001">Numer paszportu</span><span class="sxs-lookup"><span data-stu-id="a1757-3001">Numer paszportu</span></span>
- <span data-ttu-id="a1757-3002">Nr.</span><span class="sxs-lookup"><span data-stu-id="a1757-3002">Nr.</span></span> <span data-ttu-id="a1757-3003">Paszportu</span><span class="sxs-lookup"><span data-stu-id="a1757-3003">Paszportu</span></span>
- <span data-ttu-id="a1757-3004">Paszport</span><span class="sxs-lookup"><span data-stu-id="a1757-3004">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="a1757-3005">Número do Cartão de Cidadão de Portugal</span><span class="sxs-lookup"><span data-stu-id="a1757-3005">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3006">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3006">Format</span></span>

<span data-ttu-id="a1757-3007">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3007">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3008">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3008">Pattern</span></span>

<span data-ttu-id="a1757-3009">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3009">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3010">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3010">Checksum</span></span>

<span data-ttu-id="a1757-3011">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3011">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3012">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3012">Definition</span></span>

<span data-ttu-id="a1757-3013">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3013">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3014">A expressão regular Regex_portugal_citizen_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3014">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3015">Uma palavra-chave de Keyword_portugal_citizen_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3015">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3016">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3016">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="a1757-3017">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="a1757-3017">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="a1757-3018">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="a1757-3018">Citizen Card</span></span>
- <span data-ttu-id="a1757-3019">Cartão de Identidade Nacional</span><span class="sxs-lookup"><span data-stu-id="a1757-3019">National ID Card</span></span>
- <span data-ttu-id="a1757-3020">CC</span><span class="sxs-lookup"><span data-stu-id="a1757-3020">CC</span></span>
- <span data-ttu-id="a1757-3021">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="a1757-3021">Cartão de Cidadão</span></span>
- <span data-ttu-id="a1757-3022">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-3022">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="a1757-3023">ID nacional da Arábia Saudita</span><span class="sxs-lookup"><span data-stu-id="a1757-3023">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3024">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3024">Format</span></span>

<span data-ttu-id="a1757-3025">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3025">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3026">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3026">Pattern</span></span>

<span data-ttu-id="a1757-3027">10 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-3027">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3028">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3028">Checksum</span></span>

<span data-ttu-id="a1757-3029">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3029">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3030">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3030">Definition</span></span>

<span data-ttu-id="a1757-3031">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3031">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3032">A expressão regular Regex_saudi_arabia_national_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3032">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3033">Uma palavra-chave de Keyword_saudi_arabia_national_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3033">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3034">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3034">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="a1757-3035">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="a1757-3035">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="a1757-3036">Identification Card</span><span class="sxs-lookup"><span data-stu-id="a1757-3036">Identification Card</span></span> 
- <span data-ttu-id="a1757-3037">I card number</span><span class="sxs-lookup"><span data-stu-id="a1757-3037">I card number</span></span> 
- <span data-ttu-id="a1757-3038">ID number</span><span class="sxs-lookup"><span data-stu-id="a1757-3038">ID number</span></span> 
- <span data-ttu-id="a1757-3039">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="a1757-3039">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="a1757-3040">Número do Cartão de Identidade do Registro Nacional (NRIC) de Cingapura</span><span class="sxs-lookup"><span data-stu-id="a1757-3040">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3041">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3041">Format</span></span>

<span data-ttu-id="a1757-3042">Nove letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3042">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3043">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3043">Pattern</span></span>

- <span data-ttu-id="a1757-3044">Nove letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3044">Nine letters and digits:</span></span>
- <span data-ttu-id="a1757-3045">A letra "F", "G", "S" ou "T" (não diferenciam maiúsculas de minúsculas) </span><span class="sxs-lookup"><span data-stu-id="a1757-3045">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-3046">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="a1757-3046">Seven digits</span></span> 
- <span data-ttu-id="a1757-3047">Um dígito de verificação alfabético</span><span class="sxs-lookup"><span data-stu-id="a1757-3047">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3048">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3048">Checksum</span></span>

<span data-ttu-id="a1757-3049">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3049">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3050">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3050">Definition</span></span>

<span data-ttu-id="a1757-3051">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3051">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3052">A expressão regular Regex_singapore_nric localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3052">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3053">Uma palavra-chave de Keyword_singapore_nric for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3053">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="a1757-3054">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3054">The checksum passes.</span></span>

<span data-ttu-id="a1757-3055">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3055">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3056">A expressão regular Regex_singapore_nric localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3056">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3057">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3057">The checksum passes.</span></span>

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3058">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3058">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="a1757-3059">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="a1757-3059">Keyword_singapore_nric</span></span>

- <span data-ttu-id="a1757-3060">Número do Cartão de Identidade do Registro Nacional</span><span class="sxs-lookup"><span data-stu-id="a1757-3060">National Registration Identity Card</span></span> 
- <span data-ttu-id="a1757-3061">Número do Cartão de Identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-3061">Identity Card Number</span></span> 
- <span data-ttu-id="a1757-3062">NRIC</span><span class="sxs-lookup"><span data-stu-id="a1757-3062">NRIC</span></span> 
- <span data-ttu-id="a1757-3063">Liga</span><span class="sxs-lookup"><span data-stu-id="a1757-3063">IC</span></span> 
- <span data-ttu-id="a1757-3064">Número de Identificação Estrangeira</span><span class="sxs-lookup"><span data-stu-id="a1757-3064">Foreign Identification Number</span></span> 
- <span data-ttu-id="a1757-3065">ALETA</span><span class="sxs-lookup"><span data-stu-id="a1757-3065">FIN</span></span> 
- <span data-ttu-id="a1757-3066">身份证</span><span class="sxs-lookup"><span data-stu-id="a1757-3066">身份证</span></span> 
- <span data-ttu-id="a1757-3067">身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-3067">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="a1757-3068">Número de Identificação da África do Sul</span><span class="sxs-lookup"><span data-stu-id="a1757-3068">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3069">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3069">Format</span></span>

<span data-ttu-id="a1757-3070">13 dígitos que podem conter espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-3070">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3071">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3071">Pattern</span></span>

<span data-ttu-id="a1757-3072">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3072">13 digits:</span></span>
- <span data-ttu-id="a1757-3073">Seis dígitos no formato AAMMDD que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-3073">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a1757-3074">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3074">Four digits</span></span> 
- <span data-ttu-id="a1757-3075">Indicador de cidadania de um dígito </span><span class="sxs-lookup"><span data-stu-id="a1757-3075">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="a1757-3076">O dígito "8" ou "9" </span><span class="sxs-lookup"><span data-stu-id="a1757-3076">The digit "8" or "9"</span></span> 
- <span data-ttu-id="a1757-3077">Um dígito que é um dígito de soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3077">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3078">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3078">Checksum</span></span>

<span data-ttu-id="a1757-3079">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3079">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3080">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3080">Definition</span></span>

<span data-ttu-id="a1757-3081">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3082">A função Func_south_africa_identification_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3082">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3083">Uma palavra-chave de Keyword_south_africa_identification_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3083">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="a1757-3084">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3084">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3085">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3085">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="a1757-3086">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="a1757-3086">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="a1757-3087">Cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="a1757-3087">Identity card</span></span>
- <span data-ttu-id="a1757-3088">ID</span><span class="sxs-lookup"><span data-stu-id="a1757-3088">ID</span></span>
- <span data-ttu-id="a1757-3089">Identificador</span><span class="sxs-lookup"><span data-stu-id="a1757-3089">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="a1757-3090">Número do Registro de Residentes da Coreia do Sul</span><span class="sxs-lookup"><span data-stu-id="a1757-3090">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3091">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3091">Format</span></span>

<span data-ttu-id="a1757-3092">13 dígitos que contém um hifen</span><span class="sxs-lookup"><span data-stu-id="a1757-3092">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3093">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3093">Pattern</span></span>

<span data-ttu-id="a1757-3094">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3094">13 digits:</span></span>
- <span data-ttu-id="a1757-3095">Seis dígitos no formato AAMMDD que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-3095">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a1757-3096">Um hífen</span><span class="sxs-lookup"><span data-stu-id="a1757-3096">A hyphen</span></span> 
- <span data-ttu-id="a1757-3097">Um dígito determinado pelo século e pelo sexo </span><span class="sxs-lookup"><span data-stu-id="a1757-3097">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="a1757-3098">Código da região de nascimento de quatro dígitos </span><span class="sxs-lookup"><span data-stu-id="a1757-3098">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="a1757-3099">Um dígito usado para diferenciar as pessoas para as quais os números anteriores são idênticos </span><span class="sxs-lookup"><span data-stu-id="a1757-3099">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="a1757-3100">Um dígito de verificação.</span><span class="sxs-lookup"><span data-stu-id="a1757-3100">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3101">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3101">Checksum</span></span>

<span data-ttu-id="a1757-3102">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3102">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3103">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3103">Definition</span></span>

<span data-ttu-id="a1757-3104">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3104">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3105">A função Func_south_korea_resident_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3105">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3106">Uma palavra-chave de Keyword_south_korea_resident_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3106">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="a1757-3107">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3107">The checksum passes.</span></span>

<span data-ttu-id="a1757-3108">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3108">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3109">A função Func_south_korea_resident_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3109">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3110">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3110">The checksum passes.</span></span>

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3111">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3111">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="a1757-3112">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="a1757-3112">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="a1757-3113">Cartão de identidade nacional</span><span class="sxs-lookup"><span data-stu-id="a1757-3113">National ID card</span></span> 
- <span data-ttu-id="a1757-3114">Número de Registro do Cidadão</span><span class="sxs-lookup"><span data-stu-id="a1757-3114">Citizen's Registration Number</span></span> 
- <span data-ttu-id="a1757-3115">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="a1757-3115">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="a1757-3116">RRN</span><span class="sxs-lookup"><span data-stu-id="a1757-3116">RRN</span></span> 
- <span data-ttu-id="a1757-3117">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="a1757-3117">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="a1757-3118">Número de seguridade social da Espanha (SSN)</span><span class="sxs-lookup"><span data-stu-id="a1757-3118">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3119">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3119">Format</span></span>

<span data-ttu-id="a1757-3120">11 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3120">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3121">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3121">Pattern</span></span>

<span data-ttu-id="a1757-3122">11-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3122">11-12 digits:</span></span>
- <span data-ttu-id="a1757-3123">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3123">Two digits</span></span> 
- <span data-ttu-id="a1757-3124">Uma barra (opcional)</span><span class="sxs-lookup"><span data-stu-id="a1757-3124">A forward slash (optional)</span></span> 
- <span data-ttu-id="a1757-3125">7 a 8 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3125">7-8 digits</span></span> 
- <span data-ttu-id="a1757-3126">Uma barra (opcional)</span><span class="sxs-lookup"><span data-stu-id="a1757-3126">A forward slash (optional)</span></span> 
- <span data-ttu-id="a1757-3127">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3127">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3128">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3128">Checksum</span></span>

<span data-ttu-id="a1757-3129">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3129">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3130">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3130">Definition</span></span>

<span data-ttu-id="a1757-3131">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3132">A função Func_spanish_social_security_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3132">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3133">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3133">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3134">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3134">Keywords</span></span>

<span data-ttu-id="a1757-3135">None</span><span class="sxs-lookup"><span data-stu-id="a1757-3135">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="a1757-3136">Cadeia de caracteres de conexão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1757-3136">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3137">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3137">Format</span></span>

<span data-ttu-id="a1757-3138">A cadeia de caracteres "User ID", "User ID", "UID" ou "UserId" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo.</span><span class="sxs-lookup"><span data-stu-id="a1757-3138">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3139">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3139">Pattern</span></span>

- <span data-ttu-id="a1757-3140">A cadeia de caracteres "User ID", "User ID", "UID" ou "UserId"</span><span class="sxs-lookup"><span data-stu-id="a1757-3140">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="a1757-3141">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-3141">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a1757-3142">A cadeia de caracteres "password" ou "pwd", onde "pwd" não é precedida por uma letra minúscula</span><span class="sxs-lookup"><span data-stu-id="a1757-3142">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="a1757-3143">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-3143">An equal sign (=)</span></span>
- <span data-ttu-id="a1757-3144">Qualquer caractere que não seja um cifrão ($), símbolo de porcentagem (%), maior que símbolo (>), no símbolo (@), aspas ("), ponto e vírgula (;), chave esquerda ([) ou colchete esquerdo ({)</span><span class="sxs-lookup"><span data-stu-id="a1757-3144">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="a1757-3145">Qualquer combinação de 7-128 caracteres que não seja um ponto-e-vírgula (;), barra (/) ou aspas (")</span><span class="sxs-lookup"><span data-stu-id="a1757-3145">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="a1757-3146">Um ponto e vírgula (;) ou aspas (")</span><span class="sxs-lookup"><span data-stu-id="a1757-3146">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3147">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3147">Checksum</span></span>

<span data-ttu-id="a1757-3148">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3148">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3149">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3149">Definition</span></span>

<span data-ttu-id="a1757-3150">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3150">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3151">A expressão regular CEP_Regex_SQLServerConnectionString localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3151">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3152">Uma palavra-chave de CEP_GlobalFilter **não** é encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3152">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="a1757-3153">A expressão regular CEP_PasswordPlaceHolder não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3153">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3154">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3154">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3155">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3155">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="a1757-3156">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="a1757-3156">CEP_GlobalFilter</span></span>

- <span data-ttu-id="a1757-3157">algumas-senha</span><span class="sxs-lookup"><span data-stu-id="a1757-3157">some-password</span></span>
- <span data-ttu-id="a1757-3158">somepassword</span><span class="sxs-lookup"><span data-stu-id="a1757-3158">somepassword</span></span>
- <span data-ttu-id="a1757-3159">secretPassword</span><span class="sxs-lookup"><span data-stu-id="a1757-3159">secretPassword</span></span>
- <span data-ttu-id="a1757-3160">ISV</span><span class="sxs-lookup"><span data-stu-id="a1757-3160">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="a1757-3161">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="a1757-3161">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="a1757-3162">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-3162">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-3163">Senha ou pwd seguidos por 0-2 espaços, um sinal de igual (=), 0-2 espaços e um asterisco (\*)--ou--</span><span class="sxs-lookup"><span data-stu-id="a1757-3163">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="a1757-3164">Senha ou pwd seguido por:</span><span class="sxs-lookup"><span data-stu-id="a1757-3164">Password or pwd followed by:</span></span>
    - <span data-ttu-id="a1757-3165">Sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="a1757-3165">Equal sign (=)</span></span>
    - <span data-ttu-id="a1757-3166">Sinal de menor que (<)</span><span class="sxs-lookup"><span data-stu-id="a1757-3166">Less than symbol (<)</span></span>
    - <span data-ttu-id="a1757-3167">Qualquer combinação de 1-200 caracteres que sejam letras maiúsculas ou minúsculas, dígitos, um asterisco (\*), hífen (-), sublinhado (_) ou caractere de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a1757-3167">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="a1757-3168">Símbolo maior que (>)</span><span class="sxs-lookup"><span data-stu-id="a1757-3168">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a1757-3169">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a1757-3169">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a1757-3170">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="a1757-3170">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a1757-3171">contoso</span><span class="sxs-lookup"><span data-stu-id="a1757-3171">contoso</span></span>
- <span data-ttu-id="a1757-3172">fabrikam</span><span class="sxs-lookup"><span data-stu-id="a1757-3172">fabrikam</span></span>
- <span data-ttu-id="a1757-3173">Northwind</span><span class="sxs-lookup"><span data-stu-id="a1757-3173">northwind</span></span>
- <span data-ttu-id="a1757-3174">área restrita</span><span class="sxs-lookup"><span data-stu-id="a1757-3174">sandbox</span></span>
- <span data-ttu-id="a1757-3175">onebox</span><span class="sxs-lookup"><span data-stu-id="a1757-3175">onebox</span></span>
- <span data-ttu-id="a1757-3176">localhost</span><span class="sxs-lookup"><span data-stu-id="a1757-3176">localhost</span></span>
- <span data-ttu-id="a1757-3177">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a1757-3177">127.0.0.1</span></span>
- <span data-ttu-id="a1757-3178">testacs.</span><span class="sxs-lookup"><span data-stu-id="a1757-3178">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-3179">suplementos</span><span class="sxs-lookup"><span data-stu-id="a1757-3179">com</span></span>
- <span data-ttu-id="a1757-3180">s-int.</span><span class="sxs-lookup"><span data-stu-id="a1757-3180">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a1757-3181">Netlogon</span><span class="sxs-lookup"><span data-stu-id="a1757-3181">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="a1757-3182">ID nacional da Suécia</span><span class="sxs-lookup"><span data-stu-id="a1757-3182">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3183">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3183">Format</span></span>

<span data-ttu-id="a1757-3184">10 ou 12 dígitos e um delimitador opcional</span><span class="sxs-lookup"><span data-stu-id="a1757-3184">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3185">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3185">Pattern</span></span>

<span data-ttu-id="a1757-3186">10 ou 12 dígitos e um delimitador opcional:</span><span class="sxs-lookup"><span data-stu-id="a1757-3186">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="a1757-3187">2 a 4 dígitos (opcionais)</span><span class="sxs-lookup"><span data-stu-id="a1757-3187">2-4 digits (optional)</span></span> 
- <span data-ttu-id="a1757-3188">Seis dígitos no formato de data AAMMDD</span><span class="sxs-lookup"><span data-stu-id="a1757-3188">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="a1757-3189">Um delimitador de "-" ou "+" (opcional), mais</span><span class="sxs-lookup"><span data-stu-id="a1757-3189">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="a1757-3190">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3190">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3191">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3191">Checksum</span></span>

<span data-ttu-id="a1757-3192">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3192">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3193">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3193">Definition</span></span>

<span data-ttu-id="a1757-3194">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3194">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3195">A função Func_swedish_national_identifier localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3195">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3196">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3196">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3197">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3197">Keywords</span></span>

<span data-ttu-id="a1757-3198">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3198">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="a1757-3199">Número de passaporte da Suécia</span><span class="sxs-lookup"><span data-stu-id="a1757-3199">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3200">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3200">Format</span></span>

<span data-ttu-id="a1757-3201">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3201">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3202">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3202">Pattern</span></span>

<span data-ttu-id="a1757-3203">Oito dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-3203">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3204">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3204">Checksum</span></span>

<span data-ttu-id="a1757-3205">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3205">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3206">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3206">Definition</span></span>

<span data-ttu-id="a1757-3207">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3208">A expressão regular Regex_sweden_passport_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3208">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3209">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-3209">One of the following is true:</span></span>
    - <span data-ttu-id="a1757-3210">Uma palavra-chave de Keyword_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3210">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="a1757-3211">Uma palavra-chave de Keyword_sweden_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3211">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3212">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3212">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="a1757-3213">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="a1757-3213">Keyword_sweden_passport</span></span>

- <span data-ttu-id="a1757-3214">visa requirements</span><span class="sxs-lookup"><span data-stu-id="a1757-3214">visa requirements</span></span> 
- <span data-ttu-id="a1757-3215">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="a1757-3215">Alien Registration Card</span></span> 
- <span data-ttu-id="a1757-3216">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="a1757-3216">Schengen visas</span></span> 
- <span data-ttu-id="a1757-3217">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="a1757-3217">Schengen visa</span></span> 
- <span data-ttu-id="a1757-3218">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="a1757-3218">Visa Processing</span></span> 
- <span data-ttu-id="a1757-3219">Visa Type</span><span class="sxs-lookup"><span data-stu-id="a1757-3219">Visa Type</span></span> 
- <span data-ttu-id="a1757-3220">Single Entry</span><span class="sxs-lookup"><span data-stu-id="a1757-3220">Single Entry</span></span> 
- <span data-ttu-id="a1757-3221">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="a1757-3221">Multiple Entry</span></span> 
- <span data-ttu-id="a1757-3222">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="a1757-3222">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="a1757-3223">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a1757-3223">Keyword_passport</span></span>

- <span data-ttu-id="a1757-3224">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3224">Passport Number</span></span> 
- <span data-ttu-id="a1757-3225">Passport No</span><span class="sxs-lookup"><span data-stu-id="a1757-3225">Passport No</span></span> 
- <span data-ttu-id="a1757-3226">Passport #</span><span class="sxs-lookup"><span data-stu-id="a1757-3226">Passport #</span></span> 
- <span data-ttu-id="a1757-3227">Passaport #</span><span class="sxs-lookup"><span data-stu-id="a1757-3227">Passport#</span></span> 
- <span data-ttu-id="a1757-3228">Passportid</span><span class="sxs-lookup"><span data-stu-id="a1757-3228">PassportID</span></span> 
- <span data-ttu-id="a1757-3229">Passportno</span><span class="sxs-lookup"><span data-stu-id="a1757-3229">Passportno</span></span> 
- <span data-ttu-id="a1757-3230">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-3230">passportnumber</span></span> 
- <span data-ttu-id="a1757-3231">パスポート</span><span class="sxs-lookup"><span data-stu-id="a1757-3231">パスポート</span></span> 
- <span data-ttu-id="a1757-3232">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a1757-3232">パスポート番号</span></span> 
- <span data-ttu-id="a1757-3233">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a1757-3233">パスポートのNum</span></span> 
- <span data-ttu-id="a1757-3234">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a1757-3234">パスポート＃</span></span> 
- <span data-ttu-id="a1757-3235">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a1757-3235">Numéro de passeport</span></span> 
- <span data-ttu-id="a1757-3236">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a1757-3236">Passeport n °</span></span> 
- <span data-ttu-id="a1757-3237">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a1757-3237">Passeport Non</span></span> 
- <span data-ttu-id="a1757-3238">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-3238">Passeport #</span></span> 
- <span data-ttu-id="a1757-3239">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-3239">Passeport#</span></span> 
- <span data-ttu-id="a1757-3240">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a1757-3240">PasseportNon</span></span> 
- <span data-ttu-id="a1757-3241">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a1757-3241">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="a1757-3242">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="a1757-3242">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3243">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3243">Format</span></span>

<span data-ttu-id="a1757-3244">Quatro letras seguidas por 5 a 31 letras ou dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3244">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3245">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3245">Pattern</span></span>

<span data-ttu-id="a1757-3246">Quatro letras seguidas por 5 a 31 letras ou dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3246">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="a1757-3247">Código bancário de quatro letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-3247">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-3248">Um espaço opcional</span><span class="sxs-lookup"><span data-stu-id="a1757-3248">An optional space</span></span> 
- <span data-ttu-id="a1757-3249">4 a 28 letras ou dígitos (o número de conta bancária básica (BBAN))</span><span class="sxs-lookup"><span data-stu-id="a1757-3249">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="a1757-3250">Um espaço opcional</span><span class="sxs-lookup"><span data-stu-id="a1757-3250">An optional space</span></span> 
- <span data-ttu-id="a1757-3251">1 a 3 letras ou dígitos (restante do BBAN)</span><span class="sxs-lookup"><span data-stu-id="a1757-3251">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3252">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3252">Checksum</span></span>

<span data-ttu-id="a1757-3253">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3253">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3254">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3254">Definition</span></span>

<span data-ttu-id="a1757-3255">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3256">A expressão regular Regex_swift localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3256">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3257">Uma palavra-chave de Keyword_swift for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3257">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3258">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3258">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="a1757-3259">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="a1757-3259">Keyword_swift</span></span>

- <span data-ttu-id="a1757-3260">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="a1757-3260">international organization for standardization 9362</span></span> 
- <span data-ttu-id="a1757-3261">iso 9362</span><span class="sxs-lookup"><span data-stu-id="a1757-3261">iso 9362</span></span> 
- <span data-ttu-id="a1757-3262">iso9362</span><span class="sxs-lookup"><span data-stu-id="a1757-3262">iso9362</span></span> 
- <span data-ttu-id="a1757-3263">Swift\#</span><span class="sxs-lookup"><span data-stu-id="a1757-3263">swift\#</span></span> 
- <span data-ttu-id="a1757-3264">swiftcode</span><span class="sxs-lookup"><span data-stu-id="a1757-3264">swiftcode</span></span> 
- <span data-ttu-id="a1757-3265">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-3265">swiftnumber</span></span> 
- <span data-ttu-id="a1757-3266">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-3266">swiftroutingnumber</span></span> 
- <span data-ttu-id="a1757-3267">swift code</span><span class="sxs-lookup"><span data-stu-id="a1757-3267">swift code</span></span> 
- <span data-ttu-id="a1757-3268">swift number #</span><span class="sxs-lookup"><span data-stu-id="a1757-3268">swift number #</span></span> 
- <span data-ttu-id="a1757-3269">swift routing number</span><span class="sxs-lookup"><span data-stu-id="a1757-3269">swift routing number</span></span> 
- <span data-ttu-id="a1757-3270">bic number</span><span class="sxs-lookup"><span data-stu-id="a1757-3270">bic number</span></span> 
- <span data-ttu-id="a1757-3271">bic code</span><span class="sxs-lookup"><span data-stu-id="a1757-3271">bic code</span></span> 
- <span data-ttu-id="a1757-3272">bic\#</span><span class="sxs-lookup"><span data-stu-id="a1757-3272">bic \#</span></span> 
- <span data-ttu-id="a1757-3273">bic\#</span><span class="sxs-lookup"><span data-stu-id="a1757-3273">bic\#</span></span> 
- <span data-ttu-id="a1757-3274">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="a1757-3274">bank identifier code</span></span> 
- <span data-ttu-id="a1757-3275">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="a1757-3275">標準化9362</span></span> 
- <span data-ttu-id="a1757-3276">迅速＃</span><span class="sxs-lookup"><span data-stu-id="a1757-3276">迅速＃</span></span> 
- <span data-ttu-id="a1757-3277">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="a1757-3277">SWIFTコード</span></span> 
- <span data-ttu-id="a1757-3278">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="a1757-3278">SWIFT番号</span></span> 
- <span data-ttu-id="a1757-3279">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="a1757-3279">迅速なルーティング番号</span></span> 
- <span data-ttu-id="a1757-3280">BIC番号</span><span class="sxs-lookup"><span data-stu-id="a1757-3280">BIC番号</span></span> 
- <span data-ttu-id="a1757-3281">BICコード</span><span class="sxs-lookup"><span data-stu-id="a1757-3281">BICコード</span></span> 
- <span data-ttu-id="a1757-3282">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="a1757-3282">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="a1757-3283">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="a1757-3283">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="a1757-3284">rápida\#</span><span class="sxs-lookup"><span data-stu-id="a1757-3284">rapide \#</span></span> 
- <span data-ttu-id="a1757-3285">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="a1757-3285">code SWIFT</span></span> 
- <span data-ttu-id="a1757-3286">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="a1757-3286">le numéro de swift</span></span> 
- <span data-ttu-id="a1757-3287">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="a1757-3287">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="a1757-3288">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="a1757-3288">le numéro BIC</span></span> 
- <span data-ttu-id="a1757-3289">\#BIC</span><span class="sxs-lookup"><span data-stu-id="a1757-3289">\# BIC</span></span> 
- <span data-ttu-id="a1757-3290">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="a1757-3290">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="a1757-3291">ID nacional de Taiwan</span><span class="sxs-lookup"><span data-stu-id="a1757-3291">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3292">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3292">Format</span></span>

<span data-ttu-id="a1757-3293">Uma letra (em inglês) seguida de nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3293">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3294">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3294">Pattern</span></span>

<span data-ttu-id="a1757-3295">Uma letra (em inglês) seguida de nove dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3295">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="a1757-3296">Uma letra (em inglês, não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="a1757-3296">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="a1757-3297">O dígito "1" ou "2"</span><span class="sxs-lookup"><span data-stu-id="a1757-3297">The digit "1" or "2"</span></span> 
- <span data-ttu-id="a1757-3298">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3298">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3299">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3299">Checksum</span></span>

<span data-ttu-id="a1757-3300">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3300">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3301">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3301">Definition</span></span>

<span data-ttu-id="a1757-3302">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3302">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3303">A função Func_taiwanese_national_id localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3303">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3304">Uma palavra-chave de Keyword_taiwanese_national_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3304">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="a1757-3305">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3305">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3306">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3306">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="a1757-3307">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="a1757-3307">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="a1757-3308">身份證字號</span><span class="sxs-lookup"><span data-stu-id="a1757-3308">身份證字號</span></span> 
- <span data-ttu-id="a1757-3309">身份證</span><span class="sxs-lookup"><span data-stu-id="a1757-3309">身份證</span></span> 
- <span data-ttu-id="a1757-3310">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="a1757-3310">身份證號碼</span></span> 
- <span data-ttu-id="a1757-3311">身份證號</span><span class="sxs-lookup"><span data-stu-id="a1757-3311">身份證號</span></span> 
- <span data-ttu-id="a1757-3312">身分證字號</span><span class="sxs-lookup"><span data-stu-id="a1757-3312">身分證字號</span></span> 
- <span data-ttu-id="a1757-3313">身分證</span><span class="sxs-lookup"><span data-stu-id="a1757-3313">身分證</span></span> 
- <span data-ttu-id="a1757-3314">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="a1757-3314">身分證號碼</span></span> 
- <span data-ttu-id="a1757-3315">身份證號</span><span class="sxs-lookup"><span data-stu-id="a1757-3315">身份證號</span></span> 
- <span data-ttu-id="a1757-3316">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="a1757-3316">身分證統一編號</span></span> 
- <span data-ttu-id="a1757-3317">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="a1757-3317">國民身分證統一編號</span></span> 
- <span data-ttu-id="a1757-3318">簽名</span><span class="sxs-lookup"><span data-stu-id="a1757-3318">簽名</span></span> 
- <span data-ttu-id="a1757-3319">蓋章</span><span class="sxs-lookup"><span data-stu-id="a1757-3319">蓋章</span></span> 
- <span data-ttu-id="a1757-3320">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="a1757-3320">簽名或蓋章</span></span> 
- <span data-ttu-id="a1757-3321">簽章</span><span class="sxs-lookup"><span data-stu-id="a1757-3321">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="a1757-3322">	Número de passaporte de Taiwan</span><span class="sxs-lookup"><span data-stu-id="a1757-3322">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3323">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3323">Format</span></span>

- <span data-ttu-id="a1757-3324">Número de passaporte biométrico: nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3324">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="a1757-3325">Número de passaporte não biométrico: nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3325">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3326">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3326">Pattern</span></span>
<span data-ttu-id="a1757-3327">Número de passaporte biométrico:</span><span class="sxs-lookup"><span data-stu-id="a1757-3327">Biometric passport number:</span></span>
- <span data-ttu-id="a1757-3328">O dígito "3" </span><span class="sxs-lookup"><span data-stu-id="a1757-3328">The digit "3"</span></span> 
- <span data-ttu-id="a1757-3329">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3329">Eight digits</span></span>

<span data-ttu-id="a1757-3330">Número de passaporte não biométrico:</span><span class="sxs-lookup"><span data-stu-id="a1757-3330">Non-biometric passport number:</span></span>
- <span data-ttu-id="a1757-3331">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3331">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3332">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3332">Checksum</span></span>

<span data-ttu-id="a1757-3333">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3333">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3334">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3334">Definition</span></span>

<span data-ttu-id="a1757-3335">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3336">A expressão regular Regex_taiwan_passport localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3336">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3337">Uma palavra-chave de Keyword_taiwan_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3337">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3338">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3338">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="a1757-3339">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="a1757-3339">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="a1757-3340">Número de passaporte ROC</span><span class="sxs-lookup"><span data-stu-id="a1757-3340">ROC passport number</span></span> 
- <span data-ttu-id="a1757-3341">Número de passaporte</span><span class="sxs-lookup"><span data-stu-id="a1757-3341">Passport number</span></span> 
- <span data-ttu-id="a1757-3342">Nº de passaporte</span><span class="sxs-lookup"><span data-stu-id="a1757-3342">Passport no</span></span> 
- <span data-ttu-id="a1757-3343">Núm de Passaporte</span><span class="sxs-lookup"><span data-stu-id="a1757-3343">Passport Num</span></span> 
- <span data-ttu-id="a1757-3344">Passport #</span><span class="sxs-lookup"><span data-stu-id="a1757-3344">Passport #</span></span> 
- <span data-ttu-id="a1757-3345">护照</span><span class="sxs-lookup"><span data-stu-id="a1757-3345">护照</span></span> 
- <span data-ttu-id="a1757-3346">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="a1757-3346">中華民國護照</span></span> 
- <span data-ttu-id="a1757-3347">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="a1757-3347">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="a1757-3348">Número do Certificado de residente de Taiwan (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="a1757-3348">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3349">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3349">Format</span></span>

<span data-ttu-id="a1757-3350">10 letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3350">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3351">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3351">Pattern</span></span>

<span data-ttu-id="a1757-3352">10 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3352">10 letters and digits:</span></span>
- <span data-ttu-id="a1757-3353">Duas letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-3353">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a1757-3354">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3354">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3355">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3355">Checksum</span></span>

<span data-ttu-id="a1757-3356">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3356">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3357">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3357">Definition</span></span>

<span data-ttu-id="a1757-3358">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3358">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3359">A expressão regular Regex_taiwan_resident_certificate localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3359">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3360">Uma palavra-chave de Keyword_taiwan_resident_certificate for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3360">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3361">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3361">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="a1757-3362">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="a1757-3362">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="a1757-3363">Certificado de Residente</span><span class="sxs-lookup"><span data-stu-id="a1757-3363">Resident Certificate</span></span> 
- <span data-ttu-id="a1757-3364">Cert de Residente</span><span class="sxs-lookup"><span data-stu-id="a1757-3364">Resident Cert</span></span> 
- <span data-ttu-id="a1757-3365">Cert. de Residente
</span><span class="sxs-lookup"><span data-stu-id="a1757-3365">Resident Cert.</span></span> 
- <span data-ttu-id="a1757-3366">Cartão de identificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3366">Identification card</span></span> 
- <span data-ttu-id="a1757-3367">Certificado de Residente Alien</span><span class="sxs-lookup"><span data-stu-id="a1757-3367">Alien Resident Certificate</span></span> 
- <span data-ttu-id="a1757-3368">ARC</span><span class="sxs-lookup"><span data-stu-id="a1757-3368">ARC</span></span> 
- <span data-ttu-id="a1757-3369">Certificado de Residente da Área de Taiwan</span><span class="sxs-lookup"><span data-stu-id="a1757-3369">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="a1757-3370">TARC</span><span class="sxs-lookup"><span data-stu-id="a1757-3370">TARC</span></span> 
- <span data-ttu-id="a1757-3371">居留證</span><span class="sxs-lookup"><span data-stu-id="a1757-3371">居留證</span></span> 
- <span data-ttu-id="a1757-3372">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="a1757-3372">外僑居留證</span></span> 
- <span data-ttu-id="a1757-3373">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="a1757-3373">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="a1757-3374">Código de identificação de população em tailandês</span><span class="sxs-lookup"><span data-stu-id="a1757-3374">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3375">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3375">Format</span></span>

<span data-ttu-id="a1757-3376">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3376">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3377">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3377">Pattern</span></span>

<span data-ttu-id="a1757-3378">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3378">13 digits:</span></span>
- <span data-ttu-id="a1757-3379">O primeiro dígito não é 0 ou 9</span><span class="sxs-lookup"><span data-stu-id="a1757-3379">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="a1757-3380">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3380">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3381">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3381">Checksum</span></span>

<span data-ttu-id="a1757-3382">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3382">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3383">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3383">Definition</span></span>

<span data-ttu-id="a1757-3384">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3384">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3385">A função Func_Thai_Citizen_Id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3385">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3386">Uma palavra-chave de Keyword_Thai_Citizen_Id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3386">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="a1757-3387">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3387">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3388">A função Func_Thai_Citizen_Id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3388">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3389">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3389">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="a1757-3390">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="a1757-3390">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="a1757-3391">Número de Identificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3391">ID Number</span></span>
- <span data-ttu-id="a1757-3392">Número de identificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3392">Identification Number</span></span>
- <span data-ttu-id="a1757-3393">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a1757-3393">บัตรประชาชน</span></span>
- <span data-ttu-id="a1757-3394">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a1757-3394">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="a1757-3395">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a1757-3395">บัตรประชาชน</span></span>
- <span data-ttu-id="a1757-3396">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a1757-3396">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="a1757-3397">Número de identificação nacional turco</span><span class="sxs-lookup"><span data-stu-id="a1757-3397">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3398">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3398">Format</span></span>

<span data-ttu-id="a1757-3399">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3399">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3400">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3400">Pattern</span></span>

<span data-ttu-id="a1757-3401">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3401">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3402">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3402">Checksum</span></span>

<span data-ttu-id="a1757-3403">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3403">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3404">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3404">Definition</span></span>

<span data-ttu-id="a1757-3405">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3405">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3406">A função Func_Turkish_National_Id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3406">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3407">Uma palavra-chave de Keyword_Turkish_National_Id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3407">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="a1757-3408">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3408">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3409">A função Func_Turkish_National_Id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3409">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3410">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3410">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="a1757-3411">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="a1757-3411">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="a1757-3412">Kimlik TC não</span><span class="sxs-lookup"><span data-stu-id="a1757-3412">TC Kimlik No</span></span>
- <span data-ttu-id="a1757-3413">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="a1757-3413">TC Kimlik numarası</span></span>
- <span data-ttu-id="a1757-3414">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="a1757-3414">Vatandaşlık numarası</span></span>
- <span data-ttu-id="a1757-3415">Vatandaşlık não</span><span class="sxs-lookup"><span data-stu-id="a1757-3415">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="a1757-p142">Número de carteira de motorista do Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a1757-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3418">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3418">Format</span></span>

<span data-ttu-id="a1757-3419">Combinação de 18 letras e dígitos no formato especificado</span><span class="sxs-lookup"><span data-stu-id="a1757-3419">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3420">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3420">Pattern</span></span>

<span data-ttu-id="a1757-3421">18 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3421">18 letters and digits:</span></span>
- <span data-ttu-id="a1757-3422">Cinco letras (não diferenciam maiúsculas de minúsculas) ou o dígito "9" em vez de uma letra</span><span class="sxs-lookup"><span data-stu-id="a1757-3422">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a1757-3423">Um dígito</span><span class="sxs-lookup"><span data-stu-id="a1757-3423">One digit</span></span> 
- <span data-ttu-id="a1757-3424">Cinco dígitos no formato de data MMDDY para data de nascimento (o sétimo caractere é incrementado por 50 se o driver for fêmea, ou seja, 51 a 62 em vez de 01 a 12)</span><span class="sxs-lookup"><span data-stu-id="a1757-3424">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="a1757-3425">Duas letras (não diferenciam maiúsculas de minúsculas) ou o dígito "9" em vez de uma letra</span><span class="sxs-lookup"><span data-stu-id="a1757-3425">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a1757-3426">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3426">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3427">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3427">Checksum</span></span>

<span data-ttu-id="a1757-3428">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3428">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3429">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3429">Definition</span></span>

<span data-ttu-id="a1757-3430">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3430">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3431">A função Func_uk_drivers_license localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3431">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3432">Uma palavra-chave de Keyword_uk_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3432">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="a1757-3433">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3433">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3434">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3434">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="a1757-3435">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a1757-3435">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="a1757-3436">DVLA</span><span class="sxs-lookup"><span data-stu-id="a1757-3436">DVLA</span></span> 
- <span data-ttu-id="a1757-3437">light vans</span><span class="sxs-lookup"><span data-stu-id="a1757-3437">light vans</span></span> 
- <span data-ttu-id="a1757-3438">quadbikes</span><span class="sxs-lookup"><span data-stu-id="a1757-3438">quadbikes</span></span> 
- <span data-ttu-id="a1757-3439">motor cars</span><span class="sxs-lookup"><span data-stu-id="a1757-3439">motor cars</span></span> 
- <span data-ttu-id="a1757-3440">125cc</span><span class="sxs-lookup"><span data-stu-id="a1757-3440">125cc</span></span> 
- <span data-ttu-id="a1757-3441">sidecar</span><span class="sxs-lookup"><span data-stu-id="a1757-3441">sidecar</span></span> 
- <span data-ttu-id="a1757-3442">tricycles</span><span class="sxs-lookup"><span data-stu-id="a1757-3442">tricycles</span></span> 
- <span data-ttu-id="a1757-3443">motorcycles</span><span class="sxs-lookup"><span data-stu-id="a1757-3443">motorcycles</span></span> 
- <span data-ttu-id="a1757-3444">photocard licence</span><span class="sxs-lookup"><span data-stu-id="a1757-3444">photocard licence</span></span> 
- <span data-ttu-id="a1757-3445">learner drivers</span><span class="sxs-lookup"><span data-stu-id="a1757-3445">learner drivers</span></span> 
- <span data-ttu-id="a1757-3446">licence holder</span><span class="sxs-lookup"><span data-stu-id="a1757-3446">licence holder</span></span> 
- <span data-ttu-id="a1757-3447">licence holders</span><span class="sxs-lookup"><span data-stu-id="a1757-3447">licence holders</span></span> 
- <span data-ttu-id="a1757-3448">driving licences</span><span class="sxs-lookup"><span data-stu-id="a1757-3448">driving licences</span></span> 
- <span data-ttu-id="a1757-3449">driving licence</span><span class="sxs-lookup"><span data-stu-id="a1757-3449">driving licence</span></span> 
- <span data-ttu-id="a1757-3450">dual control car</span><span class="sxs-lookup"><span data-stu-id="a1757-3450">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="a1757-p143">Número de Título de Eleitor do Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a1757-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3453">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3453">Format</span></span>

<span data-ttu-id="a1757-3454">Duas letras seguidas por 1 a 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3454">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3455">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3455">Pattern</span></span>

<span data-ttu-id="a1757-3456">Duas letras (não diferencia maiúsculas de minúsculas) seguidas de 1 a 4 anos</span><span class="sxs-lookup"><span data-stu-id="a1757-3456">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3457">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3457">Checksum</span></span>

<span data-ttu-id="a1757-3458">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3459">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3459">Definition</span></span>

<span data-ttu-id="a1757-3460">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3460">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3461">A expressão regular Regex_uk_electoral localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3461">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3462">Uma palavra-chave de Keyword_uk_electoral for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3462">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3463">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3463">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="a1757-3464">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="a1757-3464">Keyword_uk_electoral</span></span>

- <span data-ttu-id="a1757-3465">council nomination</span><span class="sxs-lookup"><span data-stu-id="a1757-3465">council nomination</span></span> 
- <span data-ttu-id="a1757-3466">nomination form</span><span class="sxs-lookup"><span data-stu-id="a1757-3466">nomination form</span></span> 
- <span data-ttu-id="a1757-3467">electoral register</span><span class="sxs-lookup"><span data-stu-id="a1757-3467">electoral register</span></span> 
- <span data-ttu-id="a1757-3468">electoral roll</span><span class="sxs-lookup"><span data-stu-id="a1757-3468">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="a1757-p144">Número do serviço de saúde nacional do Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a1757-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3471">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3471">Format</span></span>

<span data-ttu-id="a1757-3472">10 a 17 dígitos separados por espaços</span><span class="sxs-lookup"><span data-stu-id="a1757-3472">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3473">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3473">Pattern</span></span>

<span data-ttu-id="a1757-3474">10 a 17 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a1757-3474">10-17 digits:</span></span>
- <span data-ttu-id="a1757-3475">3 ou 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3475">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="a1757-3476">Um espaço</span><span class="sxs-lookup"><span data-stu-id="a1757-3476">A space</span></span> 
- <span data-ttu-id="a1757-3477">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3477">Three digits</span></span> 
- <span data-ttu-id="a1757-3478">Um espaço</span><span class="sxs-lookup"><span data-stu-id="a1757-3478">A space</span></span> 
- <span data-ttu-id="a1757-3479">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3479">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3480">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3480">Checksum</span></span>

<span data-ttu-id="a1757-3481">Sim</span><span class="sxs-lookup"><span data-stu-id="a1757-3481">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3482">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3482">Definition</span></span>

<span data-ttu-id="a1757-3483">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3483">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3484">A função Func_uk_nhs_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3484">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3485">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-3485">One of the following is true:</span></span>
    - <span data-ttu-id="a1757-3486">Uma palavra-chave de Keyword_uk_nhs_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3486">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="a1757-3487">Uma palavra-chave de Keyword_uk_nhs_number1 for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3487">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="a1757-3488">Uma palavra-chave de Keyword_uk_nhs_number_dob for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3488">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="a1757-3489">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="a1757-3489">The checksum passes.</span></span>

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3490">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3490">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="a1757-3491">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="a1757-3491">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="a1757-3492">national health service</span><span class="sxs-lookup"><span data-stu-id="a1757-3492">national health service</span></span> 
- <span data-ttu-id="a1757-3493">NHS</span><span class="sxs-lookup"><span data-stu-id="a1757-3493">nhs</span></span> 
- <span data-ttu-id="a1757-3494">health services authority</span><span class="sxs-lookup"><span data-stu-id="a1757-3494">health services authority</span></span> 
- <span data-ttu-id="a1757-3495">health authority</span><span class="sxs-lookup"><span data-stu-id="a1757-3495">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="a1757-3496">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="a1757-3496">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="a1757-3497">patient id</span><span class="sxs-lookup"><span data-stu-id="a1757-3497">patient id</span></span> 
- <span data-ttu-id="a1757-3498">patient identification</span><span class="sxs-lookup"><span data-stu-id="a1757-3498">patient identification</span></span> 
- <span data-ttu-id="a1757-3499">patient no</span><span class="sxs-lookup"><span data-stu-id="a1757-3499">patient no</span></span> 
- <span data-ttu-id="a1757-3500">patient number</span><span class="sxs-lookup"><span data-stu-id="a1757-3500">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="a1757-3501">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="a1757-3501">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="a1757-3502">GP</span><span class="sxs-lookup"><span data-stu-id="a1757-3502">GP</span></span> 
- <span data-ttu-id="a1757-3503">DOB</span><span class="sxs-lookup"><span data-stu-id="a1757-3503">DOB</span></span> 
- <span data-ttu-id="a1757-3504">D. O. B</span><span class="sxs-lookup"><span data-stu-id="a1757-3504">D.O.B</span></span> 
- <span data-ttu-id="a1757-3505">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="a1757-3505">Date of Birth</span></span> 
- <span data-ttu-id="a1757-3506">Birth Date</span><span class="sxs-lookup"><span data-stu-id="a1757-3506">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="a1757-p145">Número de seguro nacional do Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="a1757-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3509">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3509">Format</span></span>

<span data-ttu-id="a1757-3510">7 caracteres ou 9 caracteres separados por espaços ou traços</span><span class="sxs-lookup"><span data-stu-id="a1757-3510">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3511">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3511">Pattern</span></span>

<span data-ttu-id="a1757-3512">Dois padrões possíveis:</span><span class="sxs-lookup"><span data-stu-id="a1757-3512">Two possible patterns:</span></span>

- <span data-ttu-id="a1757-3513">Duas letras (NINOs válidas usam apenas determinados caracteres neste prefixo, que esse padrão valida; não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-3513">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="a1757-3514">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3514">Six digits</span></span>
- <span data-ttu-id="a1757-3515">"A", "B", "C" ou "(como o prefixo, apenas determinados caracteres são permitidos no sufixo; não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="a1757-3515">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="a1757-3516">OU</span><span class="sxs-lookup"><span data-stu-id="a1757-3516">OR</span></span>

- <span data-ttu-id="a1757-3517">Duas letras</span><span class="sxs-lookup"><span data-stu-id="a1757-3517">Two letters</span></span>
- <span data-ttu-id="a1757-3518">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-3518">A space or dash</span></span>
- <span data-ttu-id="a1757-3519">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3519">Two digits</span></span>
- <span data-ttu-id="a1757-3520">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-3520">A space or dash</span></span>
- <span data-ttu-id="a1757-3521">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3521">Two digits</span></span>
- <span data-ttu-id="a1757-3522">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-3522">A space or dash</span></span>
- <span data-ttu-id="a1757-3523">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3523">Two digits</span></span>
- <span data-ttu-id="a1757-3524">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-3524">A space or dash</span></span>
- <span data-ttu-id="a1757-3525">' A ', ' B ', ' C' ou ' d'</span><span class="sxs-lookup"><span data-stu-id="a1757-3525">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3526">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3526">Checksum</span></span>

<span data-ttu-id="a1757-3527">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3527">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3528">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3528">Definition</span></span>

<span data-ttu-id="a1757-3529">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3530">A função Func_uk_nino localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3530">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3531">Uma palavra-chave de Keyword_uk_nino for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3531">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="a1757-3532">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3532">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3533">A função Func_uk_nino localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3533">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3534">Nenhuma palavra-chave de Keyword_uk_nino for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3534">No keyword from Keyword_uk_nino is found.</span></span>

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3535">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3535">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="a1757-3536">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="a1757-3536">Keyword_uk_nino</span></span>

- <span data-ttu-id="a1757-3537">national insurance number</span><span class="sxs-lookup"><span data-stu-id="a1757-3537">national insurance number</span></span> 
- <span data-ttu-id="a1757-3538">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="a1757-3538">national insurance contributions</span></span> 
- <span data-ttu-id="a1757-3539">protection act</span><span class="sxs-lookup"><span data-stu-id="a1757-3539">protection act</span></span> 
- <span data-ttu-id="a1757-3540">seguro</span><span class="sxs-lookup"><span data-stu-id="a1757-3540">insurance</span></span> 
- <span data-ttu-id="a1757-3541">social security number</span><span class="sxs-lookup"><span data-stu-id="a1757-3541">social security number</span></span> 
- <span data-ttu-id="a1757-3542">insurance application</span><span class="sxs-lookup"><span data-stu-id="a1757-3542">insurance application</span></span> 
- <span data-ttu-id="a1757-3543">medical application</span><span class="sxs-lookup"><span data-stu-id="a1757-3543">medical application</span></span> 
- <span data-ttu-id="a1757-3544">social insurance</span><span class="sxs-lookup"><span data-stu-id="a1757-3544">social insurance</span></span> 
- <span data-ttu-id="a1757-3545">medical attention</span><span class="sxs-lookup"><span data-stu-id="a1757-3545">medical attention</span></span> 
- <span data-ttu-id="a1757-3546">social security</span><span class="sxs-lookup"><span data-stu-id="a1757-3546">social security</span></span> 
- <span data-ttu-id="a1757-3547">great britain</span><span class="sxs-lookup"><span data-stu-id="a1757-3547">great britain</span></span> 
- <span data-ttu-id="a1757-3548">seguro</span><span class="sxs-lookup"><span data-stu-id="a1757-3548">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="a1757-p146">Número de passaporte dos EUA/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="a1757-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3551">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3551">Format</span></span>

<span data-ttu-id="a1757-3552">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3552">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3553">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3553">Pattern</span></span>

<span data-ttu-id="a1757-3554">Nove dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-3554">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3555">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3555">Checksum</span></span>

<span data-ttu-id="a1757-3556">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3556">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3557">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3557">Definition</span></span>

<span data-ttu-id="a1757-3558">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3558">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3559">A função Func_usa_uk_passport localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3559">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3560">Uma palavra-chave de Keyword_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3560">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3561">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3561">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a1757-3562">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a1757-3562">Keyword_passport</span></span>

- <span data-ttu-id="a1757-3563">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3563">Passport Number</span></span> 
- <span data-ttu-id="a1757-3564">Passport No</span><span class="sxs-lookup"><span data-stu-id="a1757-3564">Passport No</span></span> 
- <span data-ttu-id="a1757-3565">Passport #</span><span class="sxs-lookup"><span data-stu-id="a1757-3565">Passport #</span></span> 
- <span data-ttu-id="a1757-3566">Passaport #</span><span class="sxs-lookup"><span data-stu-id="a1757-3566">Passport#</span></span> 
- <span data-ttu-id="a1757-3567">Passportid</span><span class="sxs-lookup"><span data-stu-id="a1757-3567">PassportID</span></span> 
- <span data-ttu-id="a1757-3568">Passportno</span><span class="sxs-lookup"><span data-stu-id="a1757-3568">Passportno</span></span> 
- <span data-ttu-id="a1757-3569">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a1757-3569">passportnumber</span></span> 
- <span data-ttu-id="a1757-3570">パスポート</span><span class="sxs-lookup"><span data-stu-id="a1757-3570">パスポート</span></span> 
- <span data-ttu-id="a1757-3571">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a1757-3571">パスポート番号</span></span> 
- <span data-ttu-id="a1757-3572">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a1757-3572">パスポートのNum</span></span> 
- <span data-ttu-id="a1757-3573">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a1757-3573">パスポート＃</span></span> 
- <span data-ttu-id="a1757-3574">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a1757-3574">Numéro de passeport</span></span> 
- <span data-ttu-id="a1757-3575">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a1757-3575">Passeport n °</span></span> 
- <span data-ttu-id="a1757-3576">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="a1757-3576">Passeport Non</span></span> 
- <span data-ttu-id="a1757-3577">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-3577">Passeport #</span></span> 
- <span data-ttu-id="a1757-3578">Passeport #</span><span class="sxs-lookup"><span data-stu-id="a1757-3578">Passeport#</span></span> 
- <span data-ttu-id="a1757-3579">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a1757-3579">PasseportNon</span></span> 
- <span data-ttu-id="a1757-3580">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a1757-3580">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="a1757-3581">Número de conta bancária dos EUA</span><span class="sxs-lookup"><span data-stu-id="a1757-3581">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3582">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3582">Format</span></span>

<span data-ttu-id="a1757-3583">8 a 17 dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3583">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3584">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3584">Pattern</span></span>

<span data-ttu-id="a1757-3585">8 a 17 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="a1757-3585">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3586">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3586">Checksum</span></span>

<span data-ttu-id="a1757-3587">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3587">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3588">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3588">Definition</span></span>

<span data-ttu-id="a1757-3589">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3589">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3590">A expressão regular Regex_usa_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3590">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3591">Uma palavra-chave de Keyword_usa_Bank_Account for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3591">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3592">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3592">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="a1757-3593">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="a1757-3593">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="a1757-3594">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3594">Checking Account Number</span></span> 
- <span data-ttu-id="a1757-3595">Checking Account</span><span class="sxs-lookup"><span data-stu-id="a1757-3595">Checking Account</span></span> 
- <span data-ttu-id="a1757-3596">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="a1757-3596">Checking Account #</span></span> 
- <span data-ttu-id="a1757-3597">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3597">Checking Acct Number</span></span> 
- <span data-ttu-id="a1757-3598">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="a1757-3598">Checking Acct #</span></span> 
- <span data-ttu-id="a1757-3599">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="a1757-3599">Checking Acct No.</span></span> 
- <span data-ttu-id="a1757-3600">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="a1757-3600">Checking Account No.</span></span> 
- <span data-ttu-id="a1757-3601">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3601">Bank Account Number</span></span> 
- <span data-ttu-id="a1757-3602">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="a1757-3602">Bank Account #</span></span> 
- <span data-ttu-id="a1757-3603">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3603">Bank Acct Number</span></span> 
- <span data-ttu-id="a1757-3604">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="a1757-3604">Bank Acct #</span></span> 
- <span data-ttu-id="a1757-3605">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="a1757-3605">Bank Acct No.</span></span> 
- <span data-ttu-id="a1757-3606">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="a1757-3606">Bank Account No.</span></span> 
- <span data-ttu-id="a1757-3607">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3607">Savings Account Number</span></span> 
- <span data-ttu-id="a1757-3608">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="a1757-3608">Savings Account.</span></span> 
- <span data-ttu-id="a1757-3609">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="a1757-3609">Savings Account #</span></span> 
- <span data-ttu-id="a1757-3610">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3610">Savings Acct Number</span></span> 
- <span data-ttu-id="a1757-3611">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="a1757-3611">Savings Acct #</span></span> 
- <span data-ttu-id="a1757-3612">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="a1757-3612">Savings Acct No.</span></span> 
- <span data-ttu-id="a1757-3613">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="a1757-3613">Savings Account No.</span></span> 
- <span data-ttu-id="a1757-3614">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3614">Debit Account Number</span></span> 
- <span data-ttu-id="a1757-3615">Debit Account</span><span class="sxs-lookup"><span data-stu-id="a1757-3615">Debit Account</span></span> 
- <span data-ttu-id="a1757-3616">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="a1757-3616">Debit Account #</span></span> 
- <span data-ttu-id="a1757-3617">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="a1757-3617">Debit Acct Number</span></span> 
- <span data-ttu-id="a1757-3618">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="a1757-3618">Debit Acct #</span></span> 
- <span data-ttu-id="a1757-3619">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="a1757-3619">Debit Acct No.</span></span> 
- <span data-ttu-id="a1757-3620">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="a1757-3620">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="a1757-3621">Número de carteira de motorista dos EUA</span><span class="sxs-lookup"><span data-stu-id="a1757-3621">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3622">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3622">Format</span></span>

<span data-ttu-id="a1757-3623">Depende do estado</span><span class="sxs-lookup"><span data-stu-id="a1757-3623">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3624">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3624">Pattern</span></span>

<span data-ttu-id="a1757-3625">Depende do estado – por exemplo, Nova York:</span><span class="sxs-lookup"><span data-stu-id="a1757-3625">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="a1757-3626">Nove dígitos formatados como DDD DDD DDD corresponderão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3626">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="a1757-3627">Nove dígitos como ddddddddd não serão correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a1757-3627">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3628">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3628">Checksum</span></span>

<span data-ttu-id="a1757-3629">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3629">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3630">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3630">Definition</span></span>

<span data-ttu-id="a1757-3631">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3631">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3632">A função Func_new_york_drivers_license_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3632">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3633">Uma palavra-chave de Keyword_[state_name]_drivers_license_name for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3633">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a1757-3634">Uma palavra-chave de Keyword_us_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3634">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="a1757-3635">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3635">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3636">A função Func_new_york_drivers_license_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3636">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3637">Uma palavra-chave de Keyword_[state_name]_drivers_license_name for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3637">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a1757-3638">Uma palavra-chave de Keyword_us_drivers_license_abbreviations for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3638">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="a1757-3639">Nenhuma palavra-chave de Keyword_us_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3639">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3640">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3640">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="a1757-3641">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="a1757-3641">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="a1757-3642">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a1757-3642">DL</span></span> 
- <span data-ttu-id="a1757-3643">DL</span><span class="sxs-lookup"><span data-stu-id="a1757-3643">DLS</span></span> 
- <span data-ttu-id="a1757-3644">CDL</span><span class="sxs-lookup"><span data-stu-id="a1757-3644">CDL</span></span> 
- <span data-ttu-id="a1757-3645">CDLS</span><span class="sxs-lookup"><span data-stu-id="a1757-3645">CDLS</span></span> 
- <span data-ttu-id="a1757-3646">ID</span><span class="sxs-lookup"><span data-stu-id="a1757-3646">ID</span></span> 
- <span data-ttu-id="a1757-3647">Código</span><span class="sxs-lookup"><span data-stu-id="a1757-3647">IDs</span></span> 
- <span data-ttu-id="a1757-3648">DISTRIBUIÇÃO #</span><span class="sxs-lookup"><span data-stu-id="a1757-3648">DL#</span></span> 
- <span data-ttu-id="a1757-3649">DL #</span><span class="sxs-lookup"><span data-stu-id="a1757-3649">DLS#</span></span> 
- <span data-ttu-id="a1757-3650">CDL #</span><span class="sxs-lookup"><span data-stu-id="a1757-3650">CDL#</span></span> 
- <span data-ttu-id="a1757-3651">CDLS #</span><span class="sxs-lookup"><span data-stu-id="a1757-3651">CDLS#</span></span> 
- <span data-ttu-id="a1757-3652">ID #</span><span class="sxs-lookup"><span data-stu-id="a1757-3652">ID#</span></span>
- <span data-ttu-id="a1757-3653">Código #</span><span class="sxs-lookup"><span data-stu-id="a1757-3653">IDs#</span></span> 
- <span data-ttu-id="a1757-3654">ID number</span><span class="sxs-lookup"><span data-stu-id="a1757-3654">ID number</span></span> 
- <span data-ttu-id="a1757-3655">ID numbers</span><span class="sxs-lookup"><span data-stu-id="a1757-3655">ID numbers</span></span> 
- <span data-ttu-id="a1757-3656">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="a1757-3656">LIC</span></span> 
- <span data-ttu-id="a1757-3657">DRIVER'LIC #</span><span class="sxs-lookup"><span data-stu-id="a1757-3657">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="a1757-3658">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a1757-3658">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="a1757-3659">DriverLic</span><span class="sxs-lookup"><span data-stu-id="a1757-3659">DriverLic</span></span> 
- <span data-ttu-id="a1757-3660">DriverLics</span><span class="sxs-lookup"><span data-stu-id="a1757-3660">DriverLics</span></span> 
- <span data-ttu-id="a1757-3661">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a1757-3661">DriverLicense</span></span> 
- <span data-ttu-id="a1757-3662">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a1757-3662">DriverLicenses</span></span> 
- <span data-ttu-id="a1757-3663">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-3663">Driver Lic</span></span> 
- <span data-ttu-id="a1757-3664">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-3664">Driver Lics</span></span> 
- <span data-ttu-id="a1757-3665">Driver License</span><span class="sxs-lookup"><span data-stu-id="a1757-3665">Driver License</span></span> 
- <span data-ttu-id="a1757-3666">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-3666">Driver Licenses</span></span> 
- <span data-ttu-id="a1757-3667">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a1757-3667">DriversLic</span></span> 
- <span data-ttu-id="a1757-3668">DriversLics</span><span class="sxs-lookup"><span data-stu-id="a1757-3668">DriversLics</span></span> 
- <span data-ttu-id="a1757-3669">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="a1757-3669">DriversLicense</span></span> 
- <span data-ttu-id="a1757-3670">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a1757-3670">DriversLicenses</span></span> 
- <span data-ttu-id="a1757-3671">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-3671">Drivers Lic</span></span> 
- <span data-ttu-id="a1757-3672">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-3672">Drivers Lics</span></span> 
- <span data-ttu-id="a1757-3673">Drivers License</span><span class="sxs-lookup"><span data-stu-id="a1757-3673">Drivers License</span></span> 
- <span data-ttu-id="a1757-3674">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-3674">Drivers Licenses</span></span> 
- <span data-ttu-id="a1757-3675">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-3675">Driver'Lic</span></span> 
- <span data-ttu-id="a1757-3676">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-3676">Driver'Lics</span></span> 
- <span data-ttu-id="a1757-3677">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a1757-3677">Driver'License</span></span> 
- <span data-ttu-id="a1757-3678">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-3678">Driver'Licenses</span></span> 
- <span data-ttu-id="a1757-3679">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-3679">Driver' Lic</span></span> 
- <span data-ttu-id="a1757-3680">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-3680">Driver' Lics</span></span> 
- <span data-ttu-id="a1757-3681">Driver' License</span><span class="sxs-lookup"><span data-stu-id="a1757-3681">Driver' License</span></span> 
- <span data-ttu-id="a1757-3682">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-3682">Driver' Licenses</span></span>
- <span data-ttu-id="a1757-3683">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a1757-3683">Driver'sLic</span></span> 
- <span data-ttu-id="a1757-3684">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a1757-3684">Driver'sLics</span></span> 
- <span data-ttu-id="a1757-3685">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a1757-3685">Driver'sLicense</span></span> 
- <span data-ttu-id="a1757-3686">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a1757-3686">Driver'sLicenses</span></span> 
- <span data-ttu-id="a1757-3687">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="a1757-3687">Driver's Lic</span></span> 
- <span data-ttu-id="a1757-3688">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="a1757-3688">Driver's Lics</span></span> 
- <span data-ttu-id="a1757-3689">Driver's License</span><span class="sxs-lookup"><span data-stu-id="a1757-3689">Driver's License</span></span> 
- <span data-ttu-id="a1757-3690">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="a1757-3690">Driver's Licenses</span></span> 
- <span data-ttu-id="a1757-3691">identification number</span><span class="sxs-lookup"><span data-stu-id="a1757-3691">identification number</span></span> 
- <span data-ttu-id="a1757-3692">identification numbers</span><span class="sxs-lookup"><span data-stu-id="a1757-3692">identification numbers</span></span> 
- <span data-ttu-id="a1757-3693">identification #</span><span class="sxs-lookup"><span data-stu-id="a1757-3693">identification #</span></span> 
- <span data-ttu-id="a1757-3694">id card</span><span class="sxs-lookup"><span data-stu-id="a1757-3694">id card</span></span> 
- <span data-ttu-id="a1757-3695">id cards</span><span class="sxs-lookup"><span data-stu-id="a1757-3695">id cards</span></span> 
- <span data-ttu-id="a1757-3696">identification card</span><span class="sxs-lookup"><span data-stu-id="a1757-3696">identification card</span></span> 
- <span data-ttu-id="a1757-3697">identification cards</span><span class="sxs-lookup"><span data-stu-id="a1757-3697">identification cards</span></span> 
- <span data-ttu-id="a1757-3698">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="a1757-3698">DriverLic#</span></span> 
- <span data-ttu-id="a1757-3699">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="a1757-3699">DriverLics#</span></span> 
- <span data-ttu-id="a1757-3700">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="a1757-3700">DriverLicense#</span></span> 
- <span data-ttu-id="a1757-3701">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-3701">DriverLicenses#</span></span> 
- <span data-ttu-id="a1757-3702">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-3702">Driver Lic#</span></span> 
- <span data-ttu-id="a1757-3703">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-3703">Driver Lics#</span></span> 
- <span data-ttu-id="a1757-3704">Driver License#</span><span class="sxs-lookup"><span data-stu-id="a1757-3704">Driver License#</span></span> 
- <span data-ttu-id="a1757-3705">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-3705">Driver Licenses#</span></span> 
- <span data-ttu-id="a1757-3706">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="a1757-3706">DriversLic#</span></span> 
- <span data-ttu-id="a1757-3707">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="a1757-3707">DriversLics#</span></span> 
- <span data-ttu-id="a1757-3708">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="a1757-3708">DriversLicense#</span></span> 
- <span data-ttu-id="a1757-3709">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-3709">DriversLicenses#</span></span> 
- <span data-ttu-id="a1757-3710">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-3710">Drivers Lic#</span></span> 
- <span data-ttu-id="a1757-3711">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-3711">Drivers Lics#</span></span> 
- <span data-ttu-id="a1757-3712">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="a1757-3712">Drivers License#</span></span> 
- <span data-ttu-id="a1757-3713">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-3713">Drivers Licenses#</span></span> 
- <span data-ttu-id="a1757-3714">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="a1757-3714">Driver'Lic#</span></span> 
- <span data-ttu-id="a1757-3715">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="a1757-3715">Driver'Lics#</span></span> 
- <span data-ttu-id="a1757-3716">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="a1757-3716">Driver'License#</span></span> 
- <span data-ttu-id="a1757-3717">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-3717">Driver'Licenses#</span></span> 
- <span data-ttu-id="a1757-3718">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-3718">Driver' Lic#</span></span> 
- <span data-ttu-id="a1757-3719">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-3719">Driver' Lics#</span></span> 
- <span data-ttu-id="a1757-3720">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="a1757-3720">Driver' License#</span></span> 
- <span data-ttu-id="a1757-3721">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-3721">Driver' Licenses#</span></span> 
- <span data-ttu-id="a1757-3722">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="a1757-3722">Driver'sLic#</span></span> 
- <span data-ttu-id="a1757-3723">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="a1757-3723">Driver'sLics#</span></span> 
- <span data-ttu-id="a1757-3724">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="a1757-3724">Driver'sLicense#</span></span> 
- <span data-ttu-id="a1757-3725">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="a1757-3725">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a1757-3726">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="a1757-3726">Driver's Lic#</span></span> 
- <span data-ttu-id="a1757-3727">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="a1757-3727">Driver's Lics#</span></span> 
- <span data-ttu-id="a1757-3728">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="a1757-3728">Driver's License#</span></span> 
- <span data-ttu-id="a1757-3729">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="a1757-3729">Driver's Licenses#</span></span> 
- <span data-ttu-id="a1757-3730">id card#</span><span class="sxs-lookup"><span data-stu-id="a1757-3730">id card#</span></span> 
- <span data-ttu-id="a1757-3731">id cards#</span><span class="sxs-lookup"><span data-stu-id="a1757-3731">id cards#</span></span> 
- <span data-ttu-id="a1757-3732">identification card#</span><span class="sxs-lookup"><span data-stu-id="a1757-3732">identification card#</span></span> 
- <span data-ttu-id="a1757-3733">identification cards#</span><span class="sxs-lookup"><span data-stu-id="a1757-3733">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="a1757-3734">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a1757-3734">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="a1757-3735">Abreviação do estado (por exemplo, "NY")</span><span class="sxs-lookup"><span data-stu-id="a1757-3735">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="a1757-3736">Nome do estado (por exemplo, "Nova York")</span><span class="sxs-lookup"><span data-stu-id="a1757-3736">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="a1757-3737">Número de identificação de contribuinte individual (ITIN) dos EUA</span><span class="sxs-lookup"><span data-stu-id="a1757-3737">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3738">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3738">Format</span></span>

<span data-ttu-id="a1757-3739">Nove dígitos que começam com "9" e contêm um "7" ou "8" como o quarto dígito, opcionalmente formatado com espaços ou traços</span><span class="sxs-lookup"><span data-stu-id="a1757-3739">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3740">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3740">Pattern</span></span>

<span data-ttu-id="a1757-3741">Binário</span><span class="sxs-lookup"><span data-stu-id="a1757-3741">Formatted:</span></span>
- <span data-ttu-id="a1757-3742">O dígito "9"</span><span class="sxs-lookup"><span data-stu-id="a1757-3742">The digit "9"</span></span> 
- <span data-ttu-id="a1757-3743">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3743">Two digits</span></span> 
- <span data-ttu-id="a1757-3744">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-3744">A space or dash</span></span> 
- <span data-ttu-id="a1757-3745">Um "7" ou "8"</span><span class="sxs-lookup"><span data-stu-id="a1757-3745">A "7" or "8"</span></span> 
- <span data-ttu-id="a1757-3746">Um dígito</span><span class="sxs-lookup"><span data-stu-id="a1757-3746">A digit</span></span> 
- <span data-ttu-id="a1757-3747">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="a1757-3747">A space, or dash</span></span> 
- <span data-ttu-id="a1757-3748">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3748">Four digits</span></span>

<span data-ttu-id="a1757-3749">Não formatado</span><span class="sxs-lookup"><span data-stu-id="a1757-3749">Unformatted:</span></span>
- <span data-ttu-id="a1757-3750">O dígito "9"</span><span class="sxs-lookup"><span data-stu-id="a1757-3750">The digit "9"</span></span> 
- <span data-ttu-id="a1757-3751">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3751">Two digits</span></span> 
- <span data-ttu-id="a1757-3752">Um "7" ou "8"</span><span class="sxs-lookup"><span data-stu-id="a1757-3752">A "7" or "8"</span></span> 
- <span data-ttu-id="a1757-3753">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="a1757-3753">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3754">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3754">Checksum</span></span>

<span data-ttu-id="a1757-3755">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3755">No</span></span>

### <a name="definition"></a><span data-ttu-id="a1757-3756">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3756">Definition</span></span>

<span data-ttu-id="a1757-3757">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3757">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3758">A função Func_formatted_itin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3758">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3759">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-3759">At least one of the following is true:</span></span>
    - <span data-ttu-id="a1757-3760">Uma palavra-chave de Keyword_itin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3760">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="a1757-3761">A função Func_us_address encontrar um endereço no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-3761">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a1757-3762">A função Func_us_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-3762">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="a1757-3763">Uma palavra-chave de Keyword_itin_collaborative for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3763">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="a1757-3764">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3765">A função Func_unformatted_itin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3765">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3766">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="a1757-3766">At least one of the following is true:</span></span>
    - <span data-ttu-id="a1757-3767">Uma palavra-chave de Keyword_itin_collaborative for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3767">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="a1757-3768">A função Func_us_address encontrar um endereço no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-3768">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a1757-3769">A função Func_us_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="a1757-3769">The function Func_us_date finds a date in the right date format.</span></span>

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3770">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3770">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="a1757-3771">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="a1757-3771">Keyword_itin</span></span>

- <span data-ttu-id="a1757-3772">contribui</span><span class="sxs-lookup"><span data-stu-id="a1757-3772">taxpayer</span></span> 
- <span data-ttu-id="a1757-3773">tax id</span><span class="sxs-lookup"><span data-stu-id="a1757-3773">tax id</span></span> 
- <span data-ttu-id="a1757-3774">tax identification</span><span class="sxs-lookup"><span data-stu-id="a1757-3774">tax identification</span></span> 
- <span data-ttu-id="a1757-3775">itin</span><span class="sxs-lookup"><span data-stu-id="a1757-3775">itin</span></span> 
- <span data-ttu-id="a1757-3776">es</span><span class="sxs-lookup"><span data-stu-id="a1757-3776">ssn</span></span> 
- <span data-ttu-id="a1757-3777">Tin</span><span class="sxs-lookup"><span data-stu-id="a1757-3777">tin</span></span> 
- <span data-ttu-id="a1757-3778">social security</span><span class="sxs-lookup"><span data-stu-id="a1757-3778">social security</span></span> 
- <span data-ttu-id="a1757-3779">tax payer</span><span class="sxs-lookup"><span data-stu-id="a1757-3779">tax payer</span></span> 
- <span data-ttu-id="a1757-3780">itins</span><span class="sxs-lookup"><span data-stu-id="a1757-3780">itins</span></span> 
- <span data-ttu-id="a1757-3781">táxi</span><span class="sxs-lookup"><span data-stu-id="a1757-3781">taxid</span></span> 
- <span data-ttu-id="a1757-3782">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="a1757-3782">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="a1757-3783">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a1757-3783">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="a1757-3784">Licença</span><span class="sxs-lookup"><span data-stu-id="a1757-3784">License</span></span> 
- <span data-ttu-id="a1757-3785">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a1757-3785">DL</span></span> 
- <span data-ttu-id="a1757-3786">DOB</span><span class="sxs-lookup"><span data-stu-id="a1757-3786">DOB</span></span> 
- <span data-ttu-id="a1757-3787">Data de Nascimento</span><span class="sxs-lookup"><span data-stu-id="a1757-3787">Birthdate</span></span> 
- <span data-ttu-id="a1757-3788">Aniversário</span><span class="sxs-lookup"><span data-stu-id="a1757-3788">Birthday</span></span> 
- <span data-ttu-id="a1757-3789">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="a1757-3789">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="a1757-3790">Número de seguridade social dos EUA (SSN)</span><span class="sxs-lookup"><span data-stu-id="a1757-3790">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a1757-3791">Formatar</span><span class="sxs-lookup"><span data-stu-id="a1757-3791">Format</span></span>

<span data-ttu-id="a1757-3792">9 dígitos que podem estar em um padrão formatado ou não formatado</span><span class="sxs-lookup"><span data-stu-id="a1757-3792">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="a1757-3793">Se emitido antes de meados de 2011, um SSN tem uma formatação forte, onde determinadas partes do número devem estar dentro de determinados intervalos para serem válidos (mas não há nenhum checksum).</span><span class="sxs-lookup"><span data-stu-id="a1757-3793">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="a1757-3794">Padrão</span><span class="sxs-lookup"><span data-stu-id="a1757-3794">Pattern</span></span>

<span data-ttu-id="a1757-3795">Quatro funções procuram CPFs em quatro padrões diferentes:</span><span class="sxs-lookup"><span data-stu-id="a1757-3795">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="a1757-3796">Func_ssn localiza CPFs com formatação forte de 2011 formatada com traços ou espaços (DDD-DD-dddd ou DDD DD dddd)</span><span class="sxs-lookup"><span data-stu-id="a1757-3796">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a1757-3797">Func_unformatted_ssn localiza CPFs com uma formatação forte anterior à 2011 que não são formatadas como nove dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="a1757-3797">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="a1757-3798">Func_randomized_formatted_ssn localiza CPFs post-2011 que são formatados com traços ou espaços (DDD-DD-dddd ou DDD DD dddd)</span><span class="sxs-lookup"><span data-stu-id="a1757-3798">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a1757-3799">Func_randomized_unformatted_ssn localiza CPFs post-2011 que não estão formatados como nove dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="a1757-3799">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="a1757-3800">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="a1757-3800">Checksum</span></span>

<span data-ttu-id="a1757-3801">Não</span><span class="sxs-lookup"><span data-stu-id="a1757-3801">No</span></span>


### <a name="definition"></a><span data-ttu-id="a1757-3802">Definição</span><span class="sxs-lookup"><span data-stu-id="a1757-3802">Definition</span></span>

<span data-ttu-id="a1757-3803">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3803">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3804">A função Func_ssn localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3804">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3805">Uma palavra-chave de Keyword_ssn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3805">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a1757-3806">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3807">A função Func_unformatted_ssn localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3807">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3808">Uma palavra-chave de Keyword_ssn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3808">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a1757-3809">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3809">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3810">A função Func_randomized_formatted_ssn localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3810">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3811">Uma palavra-chave de Keyword_ssn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3811">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a1757-3812">Uma política de DLP tem 55% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="a1757-3812">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a1757-3813">A função Func_randomized_unformatted_ssn localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="a1757-3813">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a1757-3814">Uma palavra-chave de Keyword_ssn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="a1757-3814">A keyword from Keyword_ssn is found.</span></span>


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a1757-3815">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a1757-3815">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="a1757-3816">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="a1757-3816">Keyword_ssn</span></span>

- <span data-ttu-id="a1757-3817">Social Security</span><span class="sxs-lookup"><span data-stu-id="a1757-3817">Social Security</span></span> 
- <span data-ttu-id="a1757-3818">Social Security#</span><span class="sxs-lookup"><span data-stu-id="a1757-3818">Social Security#</span></span> 
- <span data-ttu-id="a1757-3819">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="a1757-3819">Soc Sec</span></span> 
- <span data-ttu-id="a1757-3820">ES</span><span class="sxs-lookup"><span data-stu-id="a1757-3820">SSN</span></span> 
- <span data-ttu-id="a1757-3821">CPFs</span><span class="sxs-lookup"><span data-stu-id="a1757-3821">SSNS</span></span> 
- <span data-ttu-id="a1757-3822">ES #</span><span class="sxs-lookup"><span data-stu-id="a1757-3822">SSN#</span></span> 
- <span data-ttu-id="a1757-3823">PLANILHA #</span><span class="sxs-lookup"><span data-stu-id="a1757-3823">SS#</span></span> 
- <span data-ttu-id="a1757-3824">SSID</span><span class="sxs-lookup"><span data-stu-id="a1757-3824">SSID</span></span> 
   
